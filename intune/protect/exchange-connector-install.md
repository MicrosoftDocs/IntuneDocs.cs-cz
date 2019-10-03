---
title: Nastavit Microsoft Intune Exchange Connector
titleSuffix: Microsoft Intune
description: Pomocí místního Intune Exchange Connectoru můžete spravovat přístup zařízení k poštovním schránkám Exchange na základě registrace a Exchange Active Sync (EAS) služby Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/28/2019
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
ms.openlocfilehash: 12c190cad923569e15fd32fe7e5f7f6bd2a45302
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814130"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Nastavení místního Intune Exchange Connectoru
V zájmu ochrany přístupu k Exchangi se Intune spoléhá na místní komponentu, která se označuje jako Microsoft Intune Exchange Connector. V některých umístěních konzoly Intune se to taky označuje jako *On-Premises Connector Exchange ActiveSync* . Informace v tomto článku vám pomůžou nainstalovat a potom monitorovat konektor Intune Exchange Connector, který používáte se [zásadami podmíněného přístupu, abyste povolili nebo zablokovali přístup k místním poštovním schránkám Exchange](conditional-access-exchange-create.md). 

Konektor se nainstaluje a spustí na místním hardwaru a zodpovídá za zjišťování zařízení, která se připojují k Exchangi, předávání informací o zařízení službě Intune a povolení nebo blokování zařízení na základě toho, jestli jsou zařízení zaregistrovaná. a kompatibilní. Tato komunikace se provádí pomocí protokolu HTTPS.

Když se zařízení pokusí o přístup k místnímu Exchangi, protokol Exchange Connector Maps Exchange Active Sync (EAS) záznamů v Exchange serveru na Intune, aby kontroloval registraci zařízení v Intune a dodržoval vaše zásady dodržování předpisů pro zařízení. V závislosti na zásadách podmíněného přístupu může být zařízení povolený přístup nebo blokováno. Další informace najdete v tématu [co jsou běžné způsoby použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md) .

Operace *zjišťování* i *povolování i blokování* jsou prováděny pomocí standardních rutin prostředí Exchange PowerShell. Tyto oOperations používají účet služby, který je k dispozici při počáteční instalaci softwaru Exchange Connector. 

Intune podporuje instalaci více konektorů Intune Exchange pro každé předplatné. Pokud máte více než jednu místní organizaci Exchange, můžete pro každý z nich nastavit samostatný konektor. Je však možné nainstalovat pouze jeden konektor pro použití s každou jednotlivou organizací Exchange.  

V následujícím seznamu najdete obecné kroky pro nastavení připojení, které Intune umožňuje komunikaci s místním Exchange serverem:

1. Stáhněte si konektor On-Premises Connector z portálu Intune.
2. Nainstalujte a nakonfigurujte Exchange Connector na počítači v organizaci místního Exchange.
3. Ověřte připojení k systému Exchange.
4. Tento postup opakujte pro každou další organizaci Exchange, kterou chcete připojit k Intune.

## <a name="intune-exchange-connector-requirements"></a>Požadavky Intune Exchange Connectoru

Budete potřebovat účet s licencí služby Intune, kterou může konektor použít pro připojení k Exchangi. Účet se zadává při instalaci konektoru.  

V následující tabulce jsou uvedené požadavky na počítač, na který nainstalujete Intune Exchange Connector.  

|  Požadavek  |   Další informace     |
|---------------|------------------------|
|  Operační systémy        | Intune podporuje Intune Exchange Connector na počítači, na kterém běží libovolná edice Windows serveru 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 nebo Windows Server 2016.<br /><br />Konektor není podporován v žádné instalaci jádra serveru.  |
| Microsoft Exchange          | Místní konektory vyžadují Microsoft Exchange 2010 SP3 nebo novější nebo starší Exchange Online vyhrazené. Pokud chcete zjistit, jestli je vyhrazené prostředí Exchange Online v <strong>nové</strong> nebo <strong>starší</strong> konfiguraci, kontaktujte svého správce účtů. |
| Autorita pro správu mobilních zařízení           | [Nastavte autoritu pro správu mobilních zařízení na Intune](../fundamentals/mdm-authority-set.md). |
| Hardware              | Počítač, na který konektor instalujete, vyžaduje procesor 1,6 GHz s 2 GB paměti RAM a 10 GB volného místa na disku. |
|  Synchronizace služby Active Directory             | Než budete moct pomocí konektoru připojit Intune k Exchange serveru, musíte [nastavit synchronizaci služby Active Directory](../fundamentals/users-add.md) tak, aby místní uživatelé a skupiny zabezpečení byly synchronizované s vaší instancí Azure Active Directory. |
| Další software         | V počítači, který je hostitelem konektoru, musí být nainstalovaná úplná instalace Microsoft .NET Framework 4,5 a prostředí Windows PowerShell 2,0. |
| Síť               | Počítač, na který instalujete konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall a proxy servery přes porty 80 a 443. Mezi domény používané v Intune patří: <br> **-** Manage.Microsoft.com <br> **-** &#42;Manage.Microsoft.com<br> **-** &#42;. manage.Microsoft.com <br><br> Intune Exchange Connector komunikuje s následujícími službami: <br> **-** Služba Intune: port HTTPS 443 <br> **-** Server Exchange Client Access Server (CAS): port služby WinRM 443<br> **-** Exchange pro automatické 443<br> **-** WebService Exchange (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin Exchange

Vytvořte uživatelský účet služby Active Directory, který bude používán konektorem Intune Exchange Connector. Tento účet musí mít oprávnění ke spuštění následujících rutin Windows PowerShellu pro Exchange:  

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

## <a name="download-the-intune-exchange-connector-software-installation-package"></a>Stažení instalačního balíčku softwaru Intune Exchange Connector

1. Na Windows serveru, který podporuje Intune Exchange Connector, se přihlaste k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) pomocí uživatelského účtu, který je správcem místního Exchange serveru a který má licenci k používání Exchange serveru.

2. Přejít na **Intune**@no__t přístup k**systému Exchange** 1  

3. V části **Nastavení**zvolte **Exchange ActiveSync On-Premises Connector**a pak vyberte **Přidat**.

4. Na stránce **Přidat konektor** vyberte **Stáhnout konektor On-Premises Connector**. Intune Exchange Connector je v komprimované složce (. zip), která se dá otevřít nebo Uložit. V dialogovém okně **Stažení souboru** klikněte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.


## <a name="install-and-configure-the-intune-exchange-connector"></a>Instalace a konfigurace Intune Exchange Connectoru

Chcete-li nainstalovat Intune Exchange Connector, proveďte následující kroky. Pokud máte více organizací Exchange, opakujte tento postup pro každý další Exchange Connector, který chcete nastavit.

1. V podporovaném operačním systému pro Intune Exchange Connector extrahujte soubory v souboru **Exchange_Connector_Setup. zip** do zabezpečeného umístění.
   > [!IMPORTANT]
   > Neměňte název ani Nepřesouvat soubory, které se nacházejí ve složce Exchange_Connector_Setup. Přesunutí nebo přejmenování obsahu složky způsobí selhání instalace konektoru.

2. Po extrahování souborů otevřete extrahovanou složku a dvojím kliknutím na **Exchange_Connector_Setup. exe** nainstalujte konektor.

   > [!IMPORTANT]
   > Pokud cílová složka není v zabezpečeném umístění, měli byste po dokončení instalace místních konektorů odstranit soubor certifikátu **MicrosoftIntune. accountcert** .

3. V dialogovém okně **Microsoft Intune Exchange Connector** vyberte možnost **místní Microsoft Exchange Server** nebo **hostovaný Microsoft Exchange Server**.

   ![Obrázek znázorňující, kde zvolit typ serveru Exchange](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   V případě místního serveru Exchange zadejte název serveru nebo plně kvalifikovaný název domény serveru Exchange, který je hostitelem role **serveru klientský přístup** .

   U hostovaného serveru Exchange zadejte adresu serveru Exchange. Vyhledání adresy URL hostovaného serveru Exchange:

   1. Otevřete Outlook na webu pro Office 365.

   2. Vyberte **?** v levém horním rohu a pak vyberte **o**.

   3. Vyhledejte hodnotu **externí server POP** .

   4. Zvolte **proxy server** a zadejte proxy server nastavení pro hostovaný Exchange Server.
       1. Vyberte možnost **při synchronizaci informací mobilních zařízení použít proxy server**.

       2. Zadejte **proxy server název** a **číslo portu** , který se má použít pro přístup k serveru.

       3. Pokud je potřeba zadat přihlašovací údaje uživatele pro přístup k proxy server, vyberte **použít přihlašovací údaje pro připojení k proxy server**. Pak zadejte **doména \ uživatel** a **heslo**.

       4. Zvolte **OK**.

4. Do polí **uživatel (doména \ Uživatel)** a **heslo** zadejte přihlašovací údaje, které jsou nezbytné pro připojení k serveru Exchange. Účet, který zadáte, musí mít licenci k používání Intune. 

5. Zadejte potřebné přihlašovací údaje pro odesílání oznámení do poštovní schránky Exchange serveru uživatele. Tento uživatel může být vyhrazený jenom pro oznámení. Uživatel oznámení potřebuje poštovní schránku Exchange k odesílání oznámení e-mailem. Tato oznámení můžete nakonfigurovat pomocí zásad podmíněného přístupu v Intune.  

   Ujistěte se, že je na serveru Exchange Client Access nakonfigurovaná služba automatické konfigurace a webové služby Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

6. Do pole **heslo** zadejte heslo pro tento účet, aby měl Intune přístup k systému Exchange Server.

   > [!NOTE]
   > Aby připojení proběhlo úspěšně, musí být účet, který používáte pro přihlášení ke klientovi, aspoň Správce služby Intune. Bez toho se zobrazí chyba připojení s chybou: "vzdálený server vrátil chybu: (400) chybný požadavek.

7. Zvolte **Připojit**.

   > [!NOTE]
   > Konfigurace připojení může trvat několik minut.

V průběhu konfigurace konektor Exchange Connector ukládá vaše nastavení proxy serveru, aby mohl mít přístup k Internetu. Pokud se vaše nastavení proxy serveru změní, překonfigurujte Exchange Connector tak, aby na konektoru Exchange použili aktualizované nastavení proxy serveru.

Jakmile Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v Exchangi se automaticky synchronizují a přidají do konektoru Exchange. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud jste nainstalovali Intune Exchange Connector a odstraníte připojení k systému Exchange, musíte konektor z počítače, na kterém je nainstalovaný, odinstalovat.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalace konektorů pro několik organizací Exchange

Intune podporuje několik konektorů Intune Exchange pro každé předplatné. Pro tenanta s více organizacemi Exchange můžete pro každou organizaci Exchange nastavit konektor, ale jenom jeden konektor pro každou jednotlivou organizaci. 

Pokud budete instalovat konektory pro připojení k více organizacím systému Exchange, Stáhněte složku. zip jednou a pak znovu použijte stejné stažení pro každý konektor, který nainstalujete. Pro každý další konektor použijte postup v předchozí části k extrakci a spuštění instalačního programu na serveru v organizaci Exchange.

Funkce pro vysokou dostupnost, monitorování a ruční synchronizaci popsané v následujících oddílech jsou podporovány pro každou organizaci Exchange, která se připojuje k Intune.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Podpora vysoké dostupnosti místní služby Intune Exchange Connector 

Vysoká dostupnost konektoru On-Premises Connector znamená, že pokud se server Exchange Client Access (CAS), který konektor používá, stane nedostupným, konektor může přepnout na používání různých certifikačních autorit pro tuto organizaci Exchange. Exchange Connector sám nepodporuje vysokou dostupnost. Pokud konektor selhává, neexistuje žádné automatické převzetí služeb při selhání a tento konektor je potřeba nahradit [instalací nového konektoru](#reinstall-the-intune-exchange-connector). 

Aby bylo možné provést převzetí služeb při selhání, poté, co konektor vytvoří úspěšné připojení k Exchangi pomocí zadaných certifikačních autorit, vyhledá konektor další servery CAS pro tuto organizaci Exchange. Znalost dalších servery CAS umožňuje konektoru převzetí služeb při selhání pro jiné certifikační autority, pokud je k dispozici, dokud nebudou primární CA k dispozici. Ve výchozím nastavení je povoleno zjišťování dalších servery CAS. Převzetí služeb při selhání můžete vypnout pomocí následujícího postupu:  
1. Na serveru, na kterém je nainstalovaný Exchange Connector, navštivte%*Složka ProgramData*% \ Microsoft\Windows Intune Exchange Connector. 
2. Pomocí textového editoru otevřete **soubor OnPremisesExchangeConnectorServiceConfiguration. XML**.
3. Pokud chcete funkci zakázat, změňte &lt;IsCasFailoverEnabled @ no__t-1**true**&lt;/IsCasFailoverEnabled @ no__t-4 na &lt;IsCasFailoverEnabled @ no__t-6**false**&lt;/IsCasFailoverEnabled @ no__t-9.  
 
## <a name="optional-performance-tuning-for-the-exchange-connector"></a>Volitelné ladění výkonu pro Exchange Connector  

Pokud podporujete 5 000 nebo více zařízení s Exchange ActiveSync, můžete nakonfigurovat volitelné nastavení pro zlepšení výkonu konektoru. Zvýšení výkonu dosáhnete tak, že zapnete Exchange k použití více instancí běhového prostředí příkazu PowerShellu. 

Než tuto změnu provedete, ujistěte se, že účet, který používáte ke spuštění Exchange Connectoru, se nepoužije pro jiné účely správy Exchange. Je to proto, že Exchange má omezený počet Run-Spaces na účet, přičemž většina z nich je využívána konektorem. 

Tato změna výkonu není vhodná pro konektory, které běží na starším nebo pomalejším hardwaru.  

1. Na serveru, na kterém je nainstalovaný konektor, otevřete instalační adresář konektorů.  Výchozí umístění je *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*. 
2. Upravte soubor *OnPremisesExchangeConnectorServiceConfiguration. XML*.
3. Vyhledejte **EnableParallelCommandSupport** a nastavte hodnotu na **true**:  
     
   \<EnableParallelCommandSupport > true @ no__t-1/EnableParallelCommandSupport >
4. Uložte soubor a pak restartujte službu Microsoft Intune Exchange Connector.

## <a name="reinstall-the-intune-exchange-connector"></a>Opětovná instalace Intune Exchange Connectoru

Možná budete muset přeinstalovat konektor Intune Exchange. Vzhledem k tomu, že jeden konektor je podporován pro připojení ke každé organizaci Exchange, pokud nainstalujete druhý konektor pro organizaci, nový konektor, který nainstalujete, nahradí původní konektor.

1. Pomocí kroků v části [instalace a konfigurace Intune Exchange Connectoru](#install-and-configure-the-intune-exchange-connector) spusťte instalaci nového konektoru. 
2. Po zobrazení výzvy vyberte **nahradit** a nainstalujte nový konektor.  
   ![Configuration výzvu k nahrazení konektoru @ no__t-1

3. Pokračujte v postupu pomocí předchozího postupu a znovu se přihlaste do Intune.
4. Až se zobrazí poslední obrazovka, vyberte **Zavřít** a dokončete instalaci.  
   @no__t 0Complete nastavení @ no__t-1
 

## <a name="monitor-the-exchange-connector-activity"></a>Monitorování aktivity softwaru Exchange Connector

Po úspěšné konfiguraci softwaru Exchange Connector můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. Ověření připojení konektoru Exchange Connector:

1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
2. Vyberte možnost **přístup k místnímu Exchangi** a ověřte stav připojení jednotlivých konektorů Exchange.

Můžete také zjistit datum a čas posledního úspěšného pokusu o synchronizaci.
--> 

### <a name="system-center-operations-manager-management-pack"></a>System Center Operations Manager Management Pack

Od verze Intune 1710 můžete použít [Management Pack Operations Manager pro Exchange Connector a Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Použití Management Pack poskytuje různé způsoby monitorování Exchange Connectoru, pokud potřebujete řešit problémy.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ruční vynutit rychlou synchronizaci nebo úplnou synchronizaci

Intune Exchange Connector automaticky synchronizuje záznamy zařízení EAS a Intune. Pokud se stav dodržování předpisů změní na zařízení, proces automatické synchronizace pravidelně aktualizuje záznamy, aby bylo možné zablokovat nebo povolit přístup k zařízení.

- **Rychlá synchronizace** probíhá pravidelně, několikrát denně. Rychlá synchronizace načte informace o zařízení pro uživatele s licencí pro Intune a cílené na místní Exchange, které se od poslední synchronizace změnily.

- Ve výchozím nastavení se **Úplná synchronizace** koná jednou denně. Úplná synchronizace načte informace o zařízení pro všechny cílové uživatele Intune s oprávněním pro podmíněného přístupu a místní Exchange. Úplná synchronizace taky načte informace Exchange serveru a zajistí, že se konfigurace určená službou Intune v Azure Portal aktualizace na serveru Exchange. 


Konektor můžete vynutit ke spuštění synchronizace pomocí možností **rychlá synchronizace** nebo **úplné synchronizace** na řídicím panelu Intune, a to pomocí následujících kroků:

   1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
   2. Vyberte **přístup pro místní Exchange**.
   3. Vyberte konektor, který chcete synchronizovat, a pak zvolte **rychlá synchronizace** nebo **Úplná synchronizace**.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásady podmíněného přístupu pro místní Exchange](conditional-access-exchange-create.md)
