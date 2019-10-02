---
title: Nastavení místního Exchange Connectoru pro Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí místního konektor Exchange můžete spravovat přístup zařízení k poštovním schránkám Exchange na základě registrace do Intune a Exchange Active Sync (EAS).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26b6b884d2a21b15e2946e4ea591054bd478fa7b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729226"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Nastavení místního Exchange Connectoru Intune v Microsoft Intune
Informace v tomto článku vám pomůžou nainstalovat a potom monitorovat konektor Exchange Active Sync On-Premises Connector pro Intune.  Pomocí místního Exchange Connectoru v Intune se [zásadami podmíněného přístupu povolíte nebo zablokujete přístup k místním poštovním schránkám Exchange](conditional-access-exchange-create.md). 

Když se zařízení pokusí o přístup k místnímu Exchangi, protokol Exchange Connector Maps Exchange Active Sync (EAS) záznamů v Exchange serveru na Intune, aby kontroloval registraci zařízení v Intune a dodržoval vaše zásady dodržování předpisů pro zařízení. V závislosti na zásadách podmíněného přístupu může být zařízení povolený přístup nebo blokováno. Další informace najdete v tématu [co jsou běžné způsoby použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md) .

Intune podporuje instalaci několika místních konektorů Exchange na předplatné. Pokud máte více než jednu místní organizaci Exchange, můžete pro každý z nich nastavit samostatný konektor. Je však možné nainstalovat pouze jeden konektor pro použití v jednotlivých organizacích Exchange. 

V následujícím seznamu najdete obecné kroky pro nastavení připojení, které Intune umožňuje komunikaci s místním Exchange serverem:

1. Stáhněte si místní Exchange Connector Intune z portálu Intune.
2. Nainstalujte a nakonfigurujte Exchange Connector na počítači v místní organizaci Exchange.
3. Ověřte připojení k Exchangi.
4. Tento postup opakujte pro každou další organizaci Exchange, kterou chcete připojit k Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Požadavky na místní Exchange Connector pro Intune
Budete potřebovat účet s licencí služby Intune, kterou může konektor použít pro připojení k Exchangi. Účet se zadává při instalaci konektoru.  

V následující tabulce jsou uvedené požadavky na počítač, na který instalujete místní Exchange Connector.  

|  Požadavek  |   Další informace     |
|---------------|------------------------|
|  operační systémy;        | Intune podporuje místní Exchange Connector na počítači, na kterém běží kterákoli edice systému Windows Server 2008 SP2 (64bitová verze), Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 nebo Windows Server 2016.<br /><br />Konektor není podporován v žádné instalaci jádra serveru.  |
| Microsoft Exchange          | Místní konektory vyžadují Microsoft Exchange 2010 SP3 nebo novější, nebo starší Exchange Online Dedicated. Pokud chcete zjistit, jestli je vaše prostředí Exchange Online Dedicated v <strong>nové</strong> nebo <strong>starší</strong> konfiguraci, kontaktujte svého správce účtů. |
| Autorita pro správu mobilních zařízení           | [Nastavte autoritu pro správu mobilních zařízení na Intune](../fundamentals/mdm-authority-set.md). |
| Hardware              | Počítač, na který nainstaluje konektor, musí mít minimálně 1,6GHz procesor s 2 GB paměti RAM a 10 GB volného místa na disku. |
|  Synchronizace se službou Active Directory             | Než použijete konektor k připojení Intune ke svému Exchange Serveru, je potřeba [nastavit synchronizaci služby Active Directory](../fundamentals/users-add.md) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory. |
| Další software         | Počítač hostující konektor musí mít úplnou instalaci rozhraní Microsoft .NET Framework 4.5 a musí na něm být nainstalované prostředí Windows PowerShell 2.0. |
| Síť               | Počítač, na který jste nainstalovali konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall nebo proxy servery přes porty 80 a 443. Mezi domény používané službou Intune patří tyto: manage.microsoft.com, &#42;manage.microsoft.com a &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

Vytvořte uživatelský účet služby Active Directory, který bude používat místní Exchange Connector. Tento účet musí mít oprávnění ke spouštění těchto požadovaných rutin prostředí Windows PowerShell:


- Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
- Get-CasMailbox, Set-CasMailbox
- Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
- Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
- Get-ActiveSyncDeviceStatistics
- Get-ActiveSyncDevice
- Get-ExchangeServer
- Get-ActiveSyncDeviceClass
- Get-Recipient
- Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
- Set-ADServerSettings
- Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Stažení instalačního balíčku místního Exchange Connectoru

1. V podporovaném operačním systému Windows Server pro místní Exchange Connector otevřete web [Azure Portal](https://portal.azure.com) a přihlaste se uživatelským účtem, který je správcem místního Exchange Serveru a který má licenci k používání Exchange Serveru.

2. Přejít na **Intune**@no__t přístup k**systému Exchange** 1  

3. V části **Nastavení**zvolte **Exchange ActiveSync On-Premises Connector**a pak vyberte **Přidat**.

4. Na stránce **Přidat konektor** vyberte **Stáhnout konektor On-Premises Connector**. Místní Exchange Connector je v komprimované složce (. zip), která se dá otevřít nebo Uložit. V dialogovém okně **Stažení souboru** vyberte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.

    > [!IMPORTANT]
    > Soubory ve složce místního Exchange Connectoru nepřejmenovávejte ani nepřesouvejte. Přesunutí nebo přejmenování obsahu složky způsobí selhání instalace Exchange Connectoru.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalace a konfigurace místního Exchange Connectoru pro Intune
Při instalaci místního Exchange Connectoru pro Intune použijte tento postup. Pokud máte více organizací Exchange, opakujte tento postup pro každý další Exchange Connector, který chcete nastavit.

1. V podporovaném operačním systému pro místní Exchange Connector extrahujte soubory v balíčku **Exchange_Connector_Setup.zip** do zabezpečeného umístění.

2. Po extrahování souborů otevřete extrahovanou složku a poklikáním na **Exchange_Connector_Setup.exe** nainstalujte místní Exchange Connector.

   > [!IMPORTANT]
   > Pokud cílová složka není v zabezpečeném umístění, měli byste po dokončení instalace místních konektorů odstranit soubor certifikátu **MicrosoftIntune.accountcert**.

3. V dialogovém okně **Microsoft Intune Exchange Connector** vyberte **On-premises Microsoft Exchange Server** nebo **Hostovaný Microsoft Exchange Server**.

   ![Obrázek znázorňující, kde vybrat typ Exchange Serveru](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

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

5. Zadejte přihlašovací údaje potřebné pro odesílání oznámení do poštovní schránky Exchange Serveru uživatele. Tento uživatel může být vyhrazený jenom pro oznámení. Uživatel oznámení potřebuje poštovní schránku Exchange k odesílání oznámení e-mailem. Tato oznámení můžete nakonfigurovat díky zásadám podmíněného přístupu v Intune.  

   Zkontrolujte, že je na serveru Exchange pro klientský přístup nainstalovaná služba Automatická konfigurace a Webové služby systému Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

6. Do pole **Heslo** zadejte heslo pro tento účet, aby měla služba Intune přístup k systému Exchange Server.

   > [!NOTE]
   > Aby připojení proběhlo úspěšně, musí být účet, který používáte pro přihlášení ke klientovi, aspoň Správce služby Intune. Bez toho se zobrazí chyba připojení s chybou: "vzdálený server vrátil chybu: (400) chybný požadavek.

7. Vyberte **Připojit**.

   > [!NOTE]
   > Konfigurace připojení může zabrat několik minut.

Exchange Connector během konfigurace uloží vaše nastavení proxy serveru, aby byl zajištěný přístup na internet. Pokud se vaše nastavení proxy serveru změní, budete muset konektor Exchange Connector překonfigurovat tak, aby na konektoru Exchange Connector mohl použít aktualizované nastavení proxy serveru.

Až Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v Exchangi se automaticky synchronizují a přidají se do Exchange Connectoru. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud máte nainstalovaný místní Exchange Connector a odstraníte připojení k Exchangi, musíte místní Exchange Connector z počítače, na kterém je nainstalovaný, odinstalovat.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalace konektorů pro více organizací Exchange
Intune podporuje více místních Exchange Connectorů pro každé předplatné. Pro tenanta s více organizacemi Exchange můžete pro každou organizaci Exchange nastavit konektor, ale jenom jeden konektor pro každou jednotlivou organizaci. 

Pokud budete instalovat konektory pro připojení k více organizacím systému Exchange, Stáhněte složku. zip jednou a pak znovu použijte stejné stažení pro každý konektor, který nainstalujete. Pro každý další konektor použijte postup v předchozí části k extrakci a spuštění instalačního programu na serveru v organizaci Exchange.

Funkce pro vysokou dostupnost, monitorování a ruční synchronizaci popsané v následujících oddílech jsou podporovány pro každou organizaci Exchange, která se připojuje k Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Podpora vysoké dostupnosti místního konektoru Exchange 
Vysoká dostupnost pro místní Exchange Connector znamená, že pokud se server Exchange Client Access (CAS), který konektor používá, stane nedostupným, konektor může přepnout na používání různých certifikačních autorit pro tuto organizaci Exchange. Samotný Exchange Connector nepodporuje vysokou dostupnost. Pokud konektor selhává, neexistuje žádné automatické převzetí služeb při selhání a tento konektor musíte nahradit [instalací nového konektoru](#reinstall-the-on-premises-exchange-connector). 

Aby bylo možné provést převzetí služeb při selhání, poté, co konektor vytvoří úspěšné připojení k Exchangi pomocí zadaných certifikačních autorit, vyhledá konektor další servery CAS pro tuto organizaci Exchange. Znalost dalších servery CAS umožňuje konektoru převzetí služeb při selhání pro jiné certifikační autority, pokud je k dispozici, dokud nebudou primární CA k dispozici. Ve výchozím nastavení je povoleno zjišťování dalších servery CAS. Převzetí služeb při selhání můžete vypnout pomocí následujícího postupu:  
1. Na serveru, na kterém je nainstalovaný Exchange Connector, navštivte%*Složka ProgramData*% \ Microsoft\Windows Intune Exchange Connector. 
2. V textovém editoru otevřete soubor **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Pokud chcete funkci vypnout, změňte parametr &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; na &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;.  
 
## <a name="optional-performance-tuning-for-the-exchange-connector"></a>Volitelné ladění výkonu pro Exchange Connector  

Pokud podporujete 5 000 nebo více zařízení s Exchange ActiveSync, můžete nakonfigurovat volitelné nastavení pro zlepšení výkonu konektoru. Zvýšení výkonu dosáhnete tak, že zapnete Exchange k použití více instancí běhového prostředí příkazu PowerShellu. 

Než tuto změnu provedete, ujistěte se, že účet, který používáte ke spuštění Exchange Connectoru, se nepoužije pro jiné účely správy Exchange. Je to proto, že Exchange má omezený počet Run-Spaces na účet, který bude konektor používat. 

Tato změna výkonu není vhodná pro konektory, které běží na starším nebo pomalejším hardwaru.  

1. Na serveru, na kterém je nainstalovaný konektor, otevřete instalační adresář konektorů.  Výchozí umístění je *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*. 
2. Upravte soubor *OnPremisesExchangeConnectorServiceConfiguration. XML*.
3. Vyhledejte **EnableParallelCommandSupport** a nastavte hodnotu na **true**:  
     
   \<EnableParallelCommandSupport > true @ no__t-1/EnableParallelCommandSupport >
4. Uložte soubor a pak restartujte službu Microsoft Intune Exchange Connector.

## <a name="reinstall-the-on-premises-exchange-connector"></a>Opětovná instalace místního konektoru Exchange
Je možné, že budete muset nainstalovat Exchange Connector. Vzhledem k tomu, že jeden konektor je podporován pro připojení ke každé organizaci Exchange, pokud nainstalujete druhý konektor pro organizaci, nový konektor, který nainstalujete, nahradí původní konektor.

1. Pomocí kroků v části [instalace a konfigurace místního Exchange Connectoru Intune](#install-and-configure-the-intune-on-premises-exchange-connector) spusťte instalaci nového konektoru. 
2. Po zobrazení výzvy vyberte **nahradit** a nainstalujte nový konektor.  
   ![Configuration výzvu k nahrazení konektoru @ no__t-1

3. Pokračujte v postupu pomocí předchozího postupu a znovu se přihlaste do Intune.
4. Až se zobrazí poslední obrazovka, vyberte **Zavřít** a dokončete instalaci.  
   @no__t 0Complete nastavení @ no__t-1
 

## <a name="monitor-the-exchange-connector-activity"></a>Monitorování aktivity Exchange Connectoru

Po úspěšné konfiguraci softwaru Exchange Connector můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. Ověření připojení konektoru Exchange Connector:

1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
2. Vyberte možnost **přístup k místnímu Exchangi** a ověřte stav připojení jednotlivých konektorů Exchange.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.
--> 

### <a name="system-center-operations-manager-management-pack"></a>System Center Operations Manager Management Pack

Od verze Intune 1710 můžete použít [Management Pack Operations Manager pro Exchange Connector a Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Použití Management Pack poskytuje různé způsoby monitorování Exchange Connectoru, pokud potřebujete řešit problémy.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ruční vynucení rychlé synchronizace nebo úplné synchronizace
Místní Exchange Connector automaticky synchronizuje záznamy zařízení EAS a Intune. Pokud se stav dodržování předpisů změní na zařízení, proces automatické synchronizace pravidelně aktualizuje záznamy, aby bylo možné zablokovat nebo povolit přístup k zařízení.

- **Rychlá synchronizace** se provádí pravidelně několikrát za den. Rychlá synchronizace načte informace o zařízení pro uživatele s licencí pro Intune a cílené na místní Exchange, které se od poslední synchronizace změnily.

- **Úplná synchronizace** se ve výchozím nastavení provádí jednou za den. Úplná synchronizace načte informace o zařízení pro všechny cílové uživatele Intune s oprávněním pro podmíněného přístupu a místní Exchange. Při úplné synchronizaci se načítají také informace Exchange Serveru a zajišťuje se, aby se na Exchange Serveru aktualizovala konfigurace zadaná pomocí Intune na webu Azure Portal. 


Následujícím postupem na řídicím panelu Intune můžete vynutit, aby konektor spustil synchronizaci pomocí možnosti **Rychlá synchronizace** nebo **Úplná synchronizace**:

   1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
   2. Vyberte **přístup pro místní Exchange**.
   3. Vyberte konektor, který chcete synchronizovat, a pak zvolte **Rychlá synchronizace** nebo **Úplná synchronizace**.

## <a name="next-steps"></a>Další kroky
[Vytvoření zásady podmíněného přístupu pro místní Exchange](conditional-access-exchange-create.md)
