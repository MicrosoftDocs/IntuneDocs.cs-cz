---
title: Nastavení Microsoft Intune – místní Exchange connector | Microsoft Intune
description: Pomocí místního konektor Exchange můžete spravovat přístup zařízení k poštovním schránkám Exchange na základě registrace do Intune a Exchange Active Sync (EAS).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: deb3e57876dffdc19129a5d845872d90d5833aaf
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394698"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Nastavit konektor Intune pro místní Exchange v Microsoft Intune
Informace v tomto článku vám pomůže při instalaci a následně monitorovat místní konektor Exchange Active Sync pro Intune.  Používáte místní Exchange connector Intune s vaší [zásady podmíněného přístupu povolit nebo zablokovat přístup k Exchange v místním poštovním schránkám](conditional-access-exchange-create.md). 

Když zařízení došlo k pokusu o přístup k vaší místní Exchange, konektor Exchange mapuje Exchange Active Sync (EAS) zaznamenává v systému Exchange Server záznamů Intune kontroluje registrace zařízení v Intune a dodržování předpisů pro zařízení zásady dodržování předpisů. V závislosti na zásad podmíněného přístupu zařízení může být povolený přístup, nebo zablokované. Další informace najdete v tématu [jaké jsou běžné způsoby použití podmíněného přístupu v Intune?](conditional-access-intune-common-ways-use.md)

Intune podporuje instalaci více Exchange connectorů lokálně na jedno předplatné. Pokud máte více než jedné organizace v místním systému Exchange, můžete nastavit samostatný konektor pro každý. Však může být jenom jeden konektor nainstalovaný, každé jednotlivé organizace Exchange. 

Toto jsou obecné kroky, které chcete nastavit připojení umožňující komunikaci Intune s místní Exchange Server:

1. Stáhněte si místní Exchange connector pro Intune z portálu Intune.
2. Nainstalujte a nakonfigurujte Exchange Connector na počítači v místní organizaci Exchange.
3. Ověřte připojení k Exchangi.
4. Tento postup opakujte pro každou další organizaci Exchange, kterou chcete připojit k Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Požadavky na místní Exchange Connector pro Intune
Budete potřebovat účet s licencí Intune, který lze použít konektor pro připojení k serveru Exchange. Účet je zadán při instalaci konektoru.  

V následující tabulce jsou uvedené požadavky na počítač, na který instalujete místní Exchange Connector.  

|  Požadavek  |   Další informace     |
|---------------|------------------------|
|  Operační systémy        | Intune podporuje místní Exchange Connector na počítači, na kterém běží kterákoli edice systému Windows Server 2008 SP2 (64bitová verze), Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 nebo Windows Server 2016.<br /><br />Konektor není podporovaný v žádné instalaci jádra serveru.  |
| Microsoft Exchange          | Místní konektory vyžadují Microsoft Exchange 2010 SP3 nebo novější, nebo starší Exchange Online Dedicated. Pokud chcete zjistit, jestli je vaše prostředí Exchange Online Dedicated v <strong>nové</strong> nebo <strong>starší</strong> konfiguraci, kontaktujte svého správce účtů. |
| Autorita pro správu mobilních zařízení           | [Nastavte autoritu pro správu mobilních zařízení na Intune](mdm-authority-set.md). |
| Hardware              | Počítač, na který nainstaluje konektor, musí mít minimálně 1,6GHz procesor s 2 GB paměti RAM a 10 GB volného místa na disku. |
|  Synchronizace se službou Active Directory             | Než použijete konektor k připojení Intune ke svému Exchange Serveru, je potřeba [nastavit synchronizaci služby Active Directory](users-add.md) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory. |
| Další software         | Počítač hostující konektor musí mít úplnou instalaci rozhraní Microsoft .NET Framework 4.5 a musí na něm být nainstalované prostředí Windows PowerShell 2.0. |
| Síť               | Počítač, na který jste nainstalovali konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall nebo proxy servery přes porty 80 a 443. Mezi domény používané službou Intune patří tyto: manage.microsoft.com, &#42;manage.microsoft.com a &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

Vytvoření účtu uživatele služby Active Directory, který se použije místní Exchange connector. Tento účet musí mít oprávnění ke spouštění těchto požadovaných rutin prostředí Windows PowerShell:


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

2. Přejděte na **Intune** > **přístup k Exchangi**  

3. V části **nastavení**, zvolte **Exchange ActiveSync místní konektor**a pak vyberte **přidat**.

4. Na **konektoru přidat** stránce **stáhnout software on-premises connector**. Místní Exchange connector je v komprimované složce (.zip), který můžete otevřít nebo uložit. V dialogovém okně **Stažení souboru** vyberte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.

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

   V případě místního serveru Exchange zadejte název serveru nebo plně kvalifikovaný název domény serveru Exchange, který je hostitelem role **Server pro klientský přístup**.

   U hostovaného serveru Exchange zadejte adresu serveru Exchange. Adresu URL hostovaného serveru Exchange najdete takto:

   1. Otevřete Outlook na webu pro Office 365.

   2. Zvolte ikonu **?** vlevo nahoře a pak vyberte **O aplikaci**.

   3. Najděte hodnotu **Externí nastavení POP**.

   4. Vyberte **Proxy server** a zadejte nastavení proxy serveru pro svůj hostovaný server Exchange.
       1. Vyberte **Používat proxy server při synchronizaci informací mobilních zařízení**.

       2. Zadejte **název proxy serveru** a **číslo portu** pro přístup na server.

       3. Pokud je potřeba zadat přihlašovací údaje uživatele pro přístup na proxy server, vyberte **Použít pověření k připojení k proxy serveru**. Zadejte **doménu\uživatele** a **heslo**.

       4. Vyberte **OK**.

4. Do polí **Uživatel (doména\uživatel)** a **Heslo** zadejte přihlašovací údaje potřebné k připojení k Exchange serveru. Účet, který zadáte, musí mít licenci k používání Intune. 

5. Zadejte přihlašovací údaje potřebné pro odesílání oznámení do poštovní schránky Exchange Serveru uživatele. Tento uživatel může být vyhrazený jenom pro oznámení. Uživatel pro oznámení potřebuje poštovní schránku Exchange k odesílání oznámení e-mailem. Tato oznámení můžete nakonfigurovat díky zásadám podmíněného přístupu v Intune.  

       Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

6. Do pole **Heslo** zadejte heslo pro tento účet, aby měla služba Intune přístup k systému Exchange Server.

7. Vyberte **Připojit**.

   > [!NOTE]
   > Konfigurace připojení může zabrat několik minut.

Exchange Connector během konfigurace uloží vaše nastavení proxy serveru, aby byl zajištěný přístup na internet. Pokud se vaše nastavení proxy serveru změní, budete muset změnit konfiguraci Exchange Connectoru použít aktualizované nastavení proxy serveru konektoru serveru Exchange.

Až Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v Exchangi se automaticky synchronizují a přidají se do Exchange Connectoru. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud máte nainstalovaný místní Exchange Connector a odstraníte připojení k Exchangi, musíte místní Exchange Connector z počítače, na kterém je nainstalovaný, odinstalovat.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalace konektorů pro více organizací Exchange
Intune podporuje více místních Exchange Connectorů pro každé předplatné. Pro tenanta s více organizacemi Exchange můžete nastavit konektor pro každou organizaci Exchange, ale pouze jeden konektor pro jakékoli jedné organizace. 

Pokud nainstalujete konektorů pro připojení k více organizací Exchange, stáhněte si složku .zip jednou a pak znovu použít stejné stáhnout pro každý konektor, kterou instalujete. Pro každý další konektor postupujte podle kroků v předchozí části extrahovat a spusťte instalační program na serveru v organizaci Exchange.

Vysokou dostupnost, monitorování a ruční synchronizaci, funkce popsané v následujících částech jsou podporovány pro každou organizaci Exchange, který se připojuje k Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Podpora vysoké dostupnosti místního konektoru Exchange 
Vysoká dostupnost pro místní Exchange connector znamená, že by měl Exchange serveru pro klientský přístup (CAS), která používá konektor přestanou být dostupné konektoru můžete přepnout použití různých certifikačních Autorit pro danou organizaci Exchange. Samotný software Exchange connector nepodporuje vysokou dostupnost. Pokud se konektoru nepodaří, neexistuje žádné automatické převzetí služeb při selhání a je třeba nahradit tento konektor podle [instalace nový konektor](#reinstall-the-on-premises-exchange-connector). 

K provedení převzetí služeb při selhání, jakmile konektor vytvoří úspěšné připojení k Exchangi pomocí určeného serveru CAS, konektor umožňuje zjistit další servery CAS pro danou organizaci Exchange. Znalost další servery CAS umožňuje konektor k převzetí služeb při selhání na jiný server CAS, pokud je k dispozici, dokud nebude primární server CAS přestane být k dispozici. Ve výchozím nastavení je povoleno zjišťování další servery CAS. Převzetí služeb při selhání můžete vypnout pomocí následujícího postupu:  
1. Na serveru, kde je nainstalován software Exchange connector, přejděte na %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. V textovém editoru otevřete soubor **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Pokud chcete funkci vypnout, změňte parametr &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; na &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;.    
 

## <a name="reinstall-the-on-premises-exchange-connector"></a>Znovu nainstalujte místní Exchange connector
Můžete potřebovat k opětovné instalaci konektoru serveru Exchange. Vzhledem k tomu, že jeden konektor je podporovaná pro připojení pro každou organizaci Exchange, pokud nainstalujete druhý konektor v organizaci, nahradí nový konektor, který nainstalujete v původní konektor.

1. Pomocí postupu z [nainstalovat a nakonfigurovat konektor Intune pro místní Exchange](#install-and-configure-the-intune-on-premises-exchange-connector) postup spuštění instalace nového konektoru. 
2. Po zobrazení výzvy vyberte **nahradit** k instalaci nového konektoru.  
   ![Konfigurace výzvy k nahrazení konektoru](./media/exchange-connector-install/prompt-to-replace.png)

3. Pokračujte v používání kroky tvoří z předchozího postupu a přihlášení do Intune znovu.
4. Při poslední obrazovka zobrazí, vyberte **Zavřít** pro dokončení instalace.  
   ![Dokončit nastavení](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>Monitorování aktivity Exchange Connectoru

Po úspěšné konfiguraci konektoru serveru Exchange, můžete zobrazit stav připojení a poslední úspěšné synchronizace. Ověření připojení Exchange connector:

1. Na řídicím panelu Intune zvolte **přístup k Exchangi**.
2. Vyberte **Exchange přístup k místnímu** ověření stavu připojení pro každý konektor Exchange connector.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.
--> 

### <a name="system-center-operations-manager-management-pack"></a>Sada System Center Operations Manager management pack

Počínaje verzí Intune 1710 můžete použít [nástroje Operations Manager management pack pro Exchange connector a Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Použití sady management pack poskytuje různé možnosti monitorování Exchange Connectoru, když budete potřebovat k řešení potíží.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ruční vynucení rychlé synchronizace nebo úplné synchronizace
V místním konektorem Exchange automaticky synchronizuje zařízení záznamy EAS a Intune pravidelně. Pokud se změní stav dodržování předpisů zařízením procesu automatické synchronizace pravidelně aktualizují záznamy tak, aby přístup k zařízení můžete blokované nebo povolené.

   - **Rychlá synchronizace** se provádí pravidelně několikrát za den. Při rychlé synchronizaci se načítají informace o zařízeních pro uživatele s licencí Intune a cílením podmíněného přístupu pro místní Exchange, kteří se od poslední synchronizace změnily.

   - **Úplná synchronizace** se ve výchozím nastavení provádí jednou za den. Při úplné synchronizaci se načítají informace o zařízeních pro všechny uživatele s licencí Intune a cílením podmíněného přístupu pro místní Exchange. Při úplné synchronizaci se načítají také informace Exchange Serveru a zajišťuje se, aby se na Exchange Serveru aktualizovala konfigurace zadaná pomocí Intune na webu Azure Portal. 


Následujícím postupem na řídicím panelu Intune můžete vynutit, aby konektor spustil synchronizaci pomocí možnosti **Rychlá synchronizace** nebo **Úplná synchronizace**:

   1. Na řídicím panelu Intune zvolte **přístup k Exchangi**.
   2. Vyberte **Exchange přístup k místnímu**.
   3. Vyberte konektor, který chcete synchronizovat, a pak zvolte **Rychlá synchronizace** nebo **Úplná synchronizace**.

## <a name="next-steps"></a>Další postup
[Vytvoření zásady podmíněného přístupu pro místní Exchange](conditional-access-exchange-create.md)
