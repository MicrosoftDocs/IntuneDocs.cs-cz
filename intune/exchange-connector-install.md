---
title: Nastavení Microsoft Intune – místní Exchange connector | Microsoft Intune
description: Pomocí místního konektor Exchange můžete spravovat přístup zařízení k poštovním schránkám Exchange na základě registrace do Intune a Exchange Active Sync (EAS).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 28886382da00f5c07129f4e69e0bbadf97634420
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817258"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Nastavení místního Exchange Connectoru pro Intune v Microsoft Intune Azure

V prostředí místního Exchange Serveru lze pomocí podmíněného přístupu Intune povolit nebo blokovat přístup k místním poštovním schránkám Exchange. Pomocí místních konektorů s protokolem Exchange Active Sync připojte Intune k vašim organizacím Exchange a nastavte podmíněný přístup Intune spolu se zásadami dodržování předpisů pro zařízení. Když se pak nějaké zařízení pokusí připojit k Exchangi, Intune určí, jestli je dané zařízení registrované v Intune a jestli splňuje požadavky. Aby se dalo určit, která zařízení jsou registrovaná v Intune, místní Exchange Connector namapuje záznamy Exchange Active Sync (EAS) v Exchange Serveru na záznamy Intune. Další informace o tom, jak to funguje, najdete v části [Jaké jsou běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md).

> [!IMPORTANT]
> Intune teď podporuje více místních Exchange Connectorů pro každé předplatné. Pokud máte více než jednu místní organizaci Exchange, můžete pro každou organizaci Exchange nastavit samostatný konektor.

Pokud chcete nastavit připojení, které umožňuje komunikaci Microsoft Intune s místním Exchange Serverem, tady je obecný postup:

1.  Stáhněte si místní Exchange Connector pro Intune z webu Azure Portal.
2.  Nainstalujte a nakonfigurujte Exchange Connector na počítači v místní organizaci Exchange.
3.  Ověřte připojení k Exchangi.
4. Opakujte tento postup pro každou organizaci Exchange, kterou chcete připojit k Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Požadavky na místní Exchange Connector pro Intune
V následující tabulce jsou uvedené požadavky na počítač, na který instalujete místní Exchange Connector.


|            Požadavek             |                                                                                                                                                                                                        Další informace                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Operační systémy          |                                                               Intune podporuje místní Exchange Connector na počítači, na kterém běží kterákoli edice systému Windows Server 2008 SP2 (64bitová verze), Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 nebo Windows Server 2016.<br /><br />Konektor není podporovaný v žádné instalaci jádra serveru.                                                                |
|         Microsoft Exchange         |                                                                           Místní konektory vyžadují Microsoft Exchange 2010 SP3 nebo novější, nebo starší Exchange Online Dedicated. Pokud chcete zjistit, jestli je vaše prostředí Exchange Online Dedicated v <strong>nové</strong> nebo <strong>starší</strong> konfiguraci, kontaktujte svého správce účtů.                                                                           |
| Autorita pro správu mobilních zařízení |                                                                                                                              [Nastavte autoritu pro správu mobilních zařízení na Intune](mdm-authority-set.md).                                                                                                                               |
|              Hardware              |                                                                                                                                                     Počítač, na který nainstaluje konektor, musí mít minimálně 1,6GHz procesor s 2 GB paměti RAM a 10 GB volného místa na disku.                                                                                                                                                      |
|  Synchronizace se službou Active Directory  |                                                                                      Než použijete konektor k připojení Intune ke svému Exchange Serveru, je potřeba [nastavit synchronizaci služby Active Directory](users-add.md) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory.                                                                                      |
|        Další software         |                                                                                                                                           Počítač hostující konektor musí mít úplnou instalaci rozhraní Microsoft .NET Framework 4.5 a musí na něm být nainstalované prostředí Windows PowerShell 2.0.                                                                                                                                           |
|              Síť               | Počítač, na který jste nainstalovali konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall nebo proxy servery přes porty 80 a 443. Mezi domény používané službou Intune patří tyto: manage.microsoft.com, &#42;manage.microsoft.com a &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

Musíte vytvořit uživatelský účet služby Active Directory, který bude místní Exchange Connector používat. Tento účet musí mít oprávnění ke spouštění těchto požadovaných rutin prostředí Windows PowerShell:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Stažení instalačního balíčku místního Exchange Connectoru

1. V podporovaném operačním systému Windows Server pro místní Exchange Connector otevřete [Azure Portal](https://portal.azure.com) a přihlaste se uživatelským účtem, který je správcem místního serveru Exchange a který má licenci k používání Exchange Serveru.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune** a po otevření řídicího panelu Intune zvolte **Místní přístup**.

4. V části **Nastavení** zvolte **Konektory Exchange ActiveSync** a pak zvolte **Stáhnout software On-Premises Connector**.

5.  Místní Exchange Connector je v komprimované složce (.zip), která se dá otevřít nebo uložit. V dialogovém okně **Stažení souboru** vyberte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.

    > [!IMPORTANT]
    > Soubory ve složce místního Exchange Connectoru nepřejmenovávejte ani nepřesouvejte. Přesunutí nebo přejmenování obsahu složky způsobí selhání instalace Exchange Connectoru.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalace a konfigurace místního Exchange Connectoru pro Intune
Při instalaci místního Exchange Connectoru pro Intune použijte tento postup. Pokud máte více organizací Exchange, opakujte tento postup pro každý další Exchange Connector, který chcete nastavit.

1. V podporovaném operačním systému pro místní Exchange Connector extrahujte soubory v balíčku **Exchange_Connector_Setup.zip** do zabezpečeného umístění.

2. Po extrahování souborů otevřete extrahovanou složku a poklikáním na **Exchange_Connector_Setup.exe** nainstalujte místní Exchange Connector.

   > [!IMPORTANT]
   > Pokud cílová složka není v zabezpečeném umístění, měli byste po dokončení instalace místních konektorů odstranit soubor certifikátu **MicrosoftIntune.accountcert**.

3. V dialogovém okně **Microsoft Intune Exchange Connector** vyberte **On-premises Microsoft Exchange Server** nebo **Hostovaný Microsoft Exchange Server**.

   ![Obrázek znázorňující, kde vybrat typ Exchange Serveru](./media/intune-sa-exchange-connector-config.png)

   V případě místního Exchange Serveru zadejte název serveru nebo plně kvalifikovaný název domény Exchange Serveru, který je hostitelem role **Server pro klientský přístup**.

   U hostovaného serveru Exchange zadejte adresu serveru Exchange. Adresu URL hostovaného serveru Exchange najdete takto:

   1. Otevřete Outlook na webu pro Office 365.

   2. Zvolte ikonu **?** vlevo nahoře a pak vyberte **O aplikaci**.

   3. Najděte hodnotu **Externí nastavení POP**.

   4. Vyberte **Proxy server** a zadejte nastavení proxy serveru pro svůj hostovaný server Exchange.
       1. Vyberte **Používat proxy server při synchronizaci informací mobilních zařízení**.

       2. Zadejte **název proxy serveru** a **číslo portu** pro přístup na server.

       3. Pokud je potřeba zadat přihlašovací údaje uživatele pro přístup na proxy server, vyberte **Použít pověření k připojení k proxy serveru**. Zadejte **doménu\uživatele** a **heslo**.

       4. Vyberte **OK**.

   5. Do polí **Uživatel (doména\uživatel)** a **Heslo** zadejte přihlašovací údaje potřebné k připojení k Exchange serveru.

   6.  Zadejte přihlašovací údaje potřebné pro odesílání oznámení do poštovní schránky Exchange Serveru uživatele. Tento uživatel může být vyhrazený jenom pro oznámení. Uživatel pro oznámení potřebuje poštovní schránku Exchange, aby mohl odesílat oznámení e-mailem. Tato oznámení můžete nakonfigurovat díky zásadám podmíněného přístupu v Intune.  

       Zkontrolujte, že je na serveru Exchange pro klientský přístup nainstalovaná služba Automatická konfigurace a Webové služby systému Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

   7.  Do pole **Heslo** zadejte heslo pro tento účet, aby měla služba Intune přístup k systému Exchange Server.

   8. Vyberte **Připojit**.

   > [!NOTE]
   > Konfigurace připojení může zabrat několik minut.

Exchange Connector během konfigurace uloží vaše nastavení proxy serveru, aby byl zajištěný přístup na internet. Pokud se vaše nastavení proxy serveru změní, budete muset Exchange Connector překonfigurovat tak, aby používal aktualizované nastavení proxy serveru.

Až Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v Exchangi se automaticky synchronizují a přidají se do Exchange Connectoru. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud máte nainstalovaný místní Exchange Connector a odstraníte připojení k Exchangi, musíte místní Exchange Connector z počítače, na kterém je nainstalovaný, odinstalovat.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalace konektorů pro více organizací Exchange
Intune podporuje více místních Exchange Connectorů pro každé předplatné. U tenanta s více organizacemi Exchange můžete pro každou organizaci Exchange nastavit jeden konektor. Stáhněte si jednou složku .zip a pak pro každou organizaci Exchange extrahujte a spusťte instalační program na serveru v příslušné organizaci podle postupu uvedeného v předchozí části.

Funkce vysoké dostupnosti, monitorování a ruční synchronizace, které jsou popsané v následujících částech, jsou podporované pro každou organizaci Exchange, která je připojená k Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Podpora vysoké dostupnosti místního konektoru Exchange 
Jakmile konektor Exchange vytvoří připojení k Exchangi pomocí určeného serveru CAS může konektor zjišťovat další servery CAS. Pokud primární server CAS není dostupný, přepne konektor na další server CAS (pokud je k dispozici), až bude primární server CAS znovu dostupný. Tato funkce je ve výchozím nastavení zapnutá. K jejímu vypnutí použijte následující postup:
1. Na serveru s nainstalovaným Exchange Connectorem přejděte ke složce %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. V textovém editoru otevřete soubor **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Pokud chcete funkci vypnout, změňte parametr &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; na &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;.    


## <a name="monitor-the-exchange-connector-activity"></a>Monitorování aktivity Exchange Connectoru

Po úspěšné konfiguraci Exchange Connectorů můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. Ověření připojení Exchange Connectoru:

1. Na řídicím panelu Intune zvolte **Místní přístup**.
2. V části **Nastavení** vyberte **Konektory Exchange ActiveSync** a ověřte stav připojení pro každý Exchange Connector.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.

### <a name="system-center-operations-manager-scom-management-pack"></a>Sada System Center Operations Manager (SCOM) Management Pack

Od verze Intune 1710 můžete používat [sadu SCOM Management Pack pro Exchange Connector a Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). V případě potřeby řešení potíží tak máte různé možnosti monitorování Exchange Connectoru.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ruční vynucení rychlé synchronizace nebo úplné synchronizace
Místní Exchange Connector automaticky synchronizuje záznamy EAS a zařízení Intune v pravidelných intervalech. Pokud se stav dodržování předpisů nějakého zařízení změní, proces automatické synchronizace pravidelně aktualizuje záznamy, takže přístup daného zařízení je možné následně blokovat nebo povolit.

   - **Rychlá synchronizace** se provádí pravidelně několikrát za den. Při rychlé synchronizaci se načítají informace o zařízeních pro uživatele s licencí Intune a cílením podmíněného přístupu pro místní Exchange, kteří se od poslední synchronizace změnily.

   - **Úplná synchronizace** se ve výchozím nastavení provádí jednou za den. Při úplné synchronizaci se načítají informace o zařízeních pro všechny uživatele s licencí Intune a cílením podmíněného přístupu pro místní Exchange. Při úplné synchronizaci se načítají také informace Exchange Serveru a zajišťuje se, aby se na Exchange Serveru aktualizovala konfigurace zadaná pomocí Intune na webu Azure Portal. 

Následujícím postupem na řídicím panelu Intune můžete vynutit, aby konektor spustil synchronizaci pomocí možnosti **Rychlá synchronizace** nebo **Úplná synchronizace**:

   1. Na řídicím panelu Intune zvolte **Místní přístup**.
   2. V části **Nastavení** zvolte **Konektory Exchange ActiveSync**.
   3. Vyberte konektor, který chcete synchronizovat, a pak zvolte **Rychlá synchronizace** nebo **Úplná synchronizace**.

## <a name="next-steps"></a>Další postup
[Vytvoření zásady podmíněného přístupu pro místní Exchange](conditional-access-exchange-create.md)
