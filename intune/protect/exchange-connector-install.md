---
title: Nastavení konektoru Microsoft Intune Exchange
titleSuffix: Microsoft Intune
description: Pomocí on-premises Intune Exchange Connector můžete spravovat přístup zařízení k poštovním schránkám Exchange na základě registrace v Intune a Exchange ActiveSync (EAS).
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
ms.openlocfilehash: f4751b77362567ad18f5b775e5bda9c1081dd181
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71911211"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Nastavení místního Intune Exchange Connectoru
Aby se chránil přístup k Exchangi, Intune spoléhá na místní komponentu, která se označuje jako konektor Microsoft Intune Exchange. Tento konektor se také označuje jako *konektor Exchange ActiveSync On-Premises Connector* v některých umístěních konzoly Intune. 

Informace v tomto článku vám pomůžou nainstalovat a monitorovat konektor Intune Exchange Connector. Konektor se [zásadami podmíněného přístupu](conditional-access-exchange-create.md) můžete použít k povolení nebo blokování přístupu k místním poštovním schránkám Exchange. 

Konektor se nainstaluje a spustí na místním hardwaru. Zjišťuje zařízení, která se připojují k Exchangi, a komunikuje informace o zařízení do služby Intune. Konektor povolí nebo zablokuje zařízení na základě toho, jestli jsou zařízení zaregistrovaná a kompatibilní. Tato komunikace používá protokol HTTPS.

Když se zařízení pokusí o přístup k místnímu Exchange serveru, Exchange Connector mapuje záznamy Exchange ActiveSync (EAS) v Exchange serveru na záznamy Intune, aby se ujistili, že je zařízení zaregistrované v Intune a vyhovuje zásadám vašeho zařízení. V závislosti na zásadách podmíněného přístupu se může zařízení povolit nebo zablokovat. Další informace najdete v tématu [co jsou běžné způsoby použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md) .

Operace *zjišťování* i *povolování i blokování* jsou prováděny pomocí standardních rutin prostředí Exchange PowerShell. Tyto operace používají účet služby, který je k dispozici při počáteční instalaci softwaru Exchange Connector. 

Intune podporuje instalaci více konektorů Intune Exchange pro každé předplatné. Pokud máte více než jednu místní organizaci Exchange, můžete pro každý z nich nastavit samostatný konektor. Pro každou organizaci Exchange se ale dá nainstalovat jenom jeden konektor.  

Při nastavování připojení, které Intune umožňuje komunikaci s místním Exchange serverem, postupujte podle těchto obecných kroků:

1. Stáhněte si konektor On-Premises Connector z portálu Intune.
2. Nainstalujte a nakonfigurujte Exchange Connector na počítači v organizaci místního Exchange.
3. Ověřte připojení k systému Exchange.
4. Tento postup opakujte pro každou další organizaci Exchange, kterou chcete připojit k Intune.

## <a name="intune-exchange-connector-requirements"></a>Požadavky Intune Exchange Connectoru

Pokud se chcete připojit k Exchangi, potřebujete účet, který má licenci Intune, kterou může konektor používat. Účet určíte při instalaci konektoru.  

V následující tabulce jsou uvedené požadavky na počítač, na který nainstalujete Intune Exchange Connector.  

|  Požadavek  |   Další informace     |
|---------------|------------------------|
|  Operační systémy        | Intune podporuje Intune Exchange Connector na počítači, na kterém běží libovolná edice Windows serveru 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 nebo Windows Server 2016.<br /><br />Konektor není podporován v žádné instalaci jádra serveru.  |
| Microsoft Exchange          | Místní konektory vyžadují Microsoft Exchange 2010 SP3 nebo novější nebo starší Exchange Online vyhrazené. Pokud chcete zjistit, jestli je vyhrazené prostředí Exchange Online v *nové* nebo *starší* konfiguraci, kontaktujte svého správce účtů. |
| Autorita pro správu mobilních zařízení           | [Nastavte autoritu pro správu mobilních zařízení na Intune](../fundamentals/mdm-authority-set.md). |
| Hardware              | Počítač, na který konektor instalujete, vyžaduje procesor 1,6 GHz s 2 GB paměti RAM a 10 GB volného místa na disku. |
|  Synchronizace služby Active Directory             | Před použitím konektoru k připojení Intune k serveru Exchange [nastavte synchronizaci služby Active Directory](../fundamentals/users-add.md). Místní uživatelé a skupiny zabezpečení se musí synchronizovat s vaší instancí Azure Active Directory. |
| Další software         | Počítač, který je hostitelem konektoru, musí mít úplnou instalaci Microsoft .NET Framework 4,5 a Windows PowerShell 2,0. |
| Sítě               | Počítač, na který instalujete konektor, musí být v doméně, která má vztah důvěryhodnosti s doménou, která hostuje server Exchange.<br /><br />Nakonfigurujte počítač tak, aby umožňoval přístup ke službě Intune přes brány firewall a proxy servery přes porty 80 a 443. Intune tyto domény používá: <br> – manage.microsoft.com <br> @no__t -0\*manage.microsoft.com<br> @no__t -0\*.manage.microsoft.com <br><br> Intune Exchange Connector komunikuje s následujícími službami: <br> – Služba Intune: port HTTPS 443 <br> – Exchange Client Access Server (CAS): port služby WinRM 443<br> – Exchange # 443<br> – Webové služby Exchange (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin Exchange

Vytvořte uživatelský účet služby Active Directory pro Intune Exchange Connector. Tento účet musí mít oprávnění ke spuštění následujících rutin Windows PowerShellu pro Exchange:  

- `Get-ActiveSyncOrganizationSettings`, `Set-ActiveSyncOrganizationSettings`
- `Get-CasMailbox`, `Set-CasMailbox`
- `Get-ActiveSyncMailboxPolicy`, `Set-ActiveSyncMailboxPolicy` `New-ActiveSyncMailboxPolicy`, `Remove-ActiveSyncMailboxPolicy`
- `Get-ActiveSyncDeviceAccessRule`, `Set-ActiveSyncDeviceAccessRule` `New-ActiveSyncDeviceAccessRule`, `Remove-ActiveSyncDeviceAccessRule`
- `Get-ActiveSyncDeviceStatistics`
- `Get-ActiveSyncDevice`
- `Get-ExchangeServer`
- `Get-ActiveSyncDeviceClass`
- `Get-Recipient`
- `Clear-ActiveSyncDevice`, `Remove-ActiveSyncDevice`
- `Set-ADServerSettings`
- `Get-Command`

## <a name="download-the-installation-package"></a>Stažení instalačního balíčku

1. Na Windows serveru, který může podporovat Intune Exchange Connector, se přihlaste k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Použijte účet, který je správcem místního Exchange serveru a který má licenci k používání Exchange serveru.

2. Přejděte do **Intune**@no__t přístup k**systému Exchange**1.  

3. V části **Nastavení**zvolte **Exchange ActiveSync On-Premises Connector** a pak vyberte **Přidat**.

4. Na stránce **Přidat konektor** vyberte **Stáhnout konektor On-Premises Connector**. Intune Exchange Connector je v komprimované složce (. zip), která se dá otevřít nebo Uložit. V dialogovém okně **Stažení souboru** klikněte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.


## <a name="install-and-configure-the-intune-exchange-connector"></a>Instalace a konfigurace Intune Exchange Connectoru

Pomocí těchto kroků nainstalujete Intune Exchange Connector. Pokud máte více organizací Exchange, opakujte postup u každého konektoru Exchange, který chcete nastavit.

1. V podporovaném operačním systému pro Intune Exchange Connector extrahujte soubory v souboru **Exchange_Connector_Setup. zip** do zabezpečeného umístění.
   > [!IMPORTANT]
   > Neprovádějte přejmenování ani přesun souborů, které jsou ve složce *Exchange_Connector_Setup* . Tyto změny by způsobily selhání instalace konektoru.

2. Po extrahování souborů otevřete extrahovanou složku a dvojím kliknutím na **Exchange_Connector_Setup. exe** nainstalujte konektor.

   > [!IMPORTANT]
   > Pokud cílová složka není v zabezpečeném umístění, po dokončení instalace místních konektorů odstraňte soubor certifikátu *MicrosoftIntune. accountcert* .

3. V dialogovém okně **Microsoft Intune Exchange Connector** vyberte možnost **místní Microsoft Exchange Server** nebo **hostovaný Microsoft Exchange Server**.

   ![Obrázek znázorňující, kde zvolit typ serveru Exchange](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   V případě místního serveru Exchange zadejte název serveru nebo plně kvalifikovaný název domény serveru Exchange, který je hostitelem role **serveru klientský přístup** .

   U hostovaného serveru Exchange zadejte adresu serveru Exchange. Vyhledání adresy URL hostovaného serveru Exchange:

   1. Otevřete Outlook pro Office 365.

   2. Vyberte **?** v levém horním rohu a pak vyberte **o**.

   3. Vyhledejte hodnotu **externí server POP** .

   4. Zvolte **proxy server** a zadejte proxy server nastavení pro hostovaný Exchange Server.

       1. Vyberte možnost **při synchronizaci informací mobilních zařízení použít proxy server**.

       1. Zadejte **proxy server název** a **číslo portu** , který se má použít pro přístup k serveru.

       1. Pokud jsou pro přístup k proxy server vyžadovány přihlašovací údaje uživatele, vyberte **použít pověření pro připojení k proxy server**. Pak zadejte **doména \ uživatel** a **heslo**.

       1. Klikněte na **tlačítko OK**.

4. Do polí **uživatel (doména \ Uživatel)** a **heslo** zadejte přihlašovací údaje pro připojení k serveru Exchange. Účet, který zadáte, musí mít licenci k používání Intune. 

5. Zadejte přihlašovací údaje pro odesílání oznámení do poštovní schránky Exchange serveru uživatele. Tento uživatel může být vyhrazený jenom pro oznámení. Uživatel oznámení potřebuje poštovní schránku Exchange k odesílání oznámení e-mailem. Tato oznámení můžete nakonfigurovat pomocí zásad podmíněného přístupu v Intune.  

   Ujistěte se, že je služba Automatická konfigurace a webové služby systému Exchange nakonfigurované na certifikačních autoritách Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

6. Do pole **heslo** zadejte heslo pro tento účet, aby měl Intune přístup k systému Exchange Server.

   > [!NOTE]
   > Účet, pomocí kterého se přihlašujete ke klientovi, musí být aspoň Správce služby Intune. Bez tohoto účtu správce obdržíte neúspěšné připojení s chybou "vzdálený server vrátil chybu: (400) chybný požadavek.

7. Vyberte **připojit**.

   > [!NOTE]
   > Konfigurace připojení může trvat několik minut.

V průběhu konfigurace konektor Exchange Connector ukládá vaše nastavení proxy serveru, aby mohl mít přístup k Internetu. Pokud se vaše nastavení proxy serveru změní, překonfigurujte Exchange Connector tak, aby na konektoru Exchange použili aktualizované nastavení proxy serveru.

Jakmile Exchange Connector nastaví připojení, mobilní zařízení přidružená k uživatelům spravovaným systémem Exchange budou automaticky synchronizována a přidána do konektoru Exchange. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud nainstalujete Intune Exchange Connector a později potřebujete odstranit připojení k Exchangi, musíte konektor odinstalovat z počítače, na kterém je nainstalovaný.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalace konektorů pro několik organizací Exchange

Intune podporuje několik konektorů Intune Exchange pro každé předplatné. U tenanta s více organizacemi Exchange můžete pro každou organizaci Exchange nastavit jenom jeden konektor. 

Chcete-li nainstalovat konektory pro připojení k více organizacím systému Exchange, Stáhněte složku. zip jednou. Pro každý konektor, který nainstalujete, znovu použijte stejné soubory ke stažení. Pro každý další konektor použijte postup v předchozí části k extrakci a spuštění instalačního programu na serveru v organizaci Exchange.

Každá organizace Exchange, která se připojuje k Intune, podporuje vysokou dostupnost, monitorování a ruční synchronizaci. Tyto funkce jsou popsány v následujících částech.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Podpora vysoké dostupnosti místní služby Intune Exchange Connector  

U konektoru On-Premises Connector to znamená, že pokud CAS serveru Exchange, kterou konektor používá, nebude k dispozici, konektor může pro tuto organizaci Exchange přejít na jiné certifikační autority. Exchange Connector sám nepodporuje vysokou dostupnost. Pokud konektor selhává, neexistuje žádné automatické převzetí služeb při selhání. Je nutné [nainstalovat nový konektor](#reinstall-the-intune-exchange-connector) , aby se neúspěšný konektor nahradil. 

Pro převzetí služeb při selhání konektor pomocí zadaných certifikačních autorit vytvoří úspěšné připojení k Exchangi. Pak zjistí další servery CAS pro tuto organizaci Exchange. Toto zjišťování umožňuje konektoru převzít služby při selhání jiné certifikační autority, pokud je k dispozici, dokud nebudou primární CA k dispozici. 

Ve výchozím nastavení je povoleno zjišťování dalších servery CAS. Pokud potřebujete vypnout převzetí služeb při selhání:  
1. Na serveru, na kterém je nainstalovaný Exchange Connector, navštivte **%*Složka ProgramData*% \ Microsoft\Windows Intune Exchange Connector**. 
2. Pomocí textového editoru otevřete **soubor OnPremisesExchangeConnectorServiceConfiguration. XML**.
3. Změňte **\<IsCasFailoverEnabled >*true*\</IsCasFailoverEnabled >** na **\<IsCasFailoverEnabled >*false*\</IsCasFailoverEnabled >** .  
 
## <a name="performance-tune-the-exchange-connector-optional"></a>Výkon – ladění Exchange Connectoru (volitelné)

Když Exchange ActiveSync podporuje 5 000 nebo více zařízení, můžete nakonfigurovat volitelné nastavení pro zlepšení výkonu konektoru. Můžete zvýšit výkon tím, že povolíte serveru Exchange používat více instancí prostředí PowerShellového místa pro spuštění. 

Než tuto změnu provedete, ujistěte se, že účet, který používáte ke spuštění Exchange Connectoru, se nepoužije pro jiné účely správy Exchange. Účet systému Exchange má omezený počet mezer za běhu a konektor bude používat většinu z nich. 

Ladění výkonu není vhodné pro konektory, které běží na starším nebo pomalejším hardwaru.  

Zlepšení výkonu konektoru Exchange Connector: 

1. Na serveru, na kterém je nainstalovaný konektor, otevřete instalační adresář konektoru.  Výchozí umístění je *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*. 
2. Upravte soubor *OnPremisesExchangeConnectorServiceConfiguration. XML*.
3. Vyhledejte **EnableParallelCommandSupport** a nastavte hodnotu na **true**:  
     
   \<EnableParallelCommandSupport > true @ no__t-1/EnableParallelCommandSupport >
4. Uložte soubor a pak restartujte službu Microsoft Intune Exchange Connector.

## <a name="reinstall-the-intune-exchange-connector"></a>Opětovná instalace Intune Exchange Connectoru

Možná budete muset přeinstalovat konektor Intune Exchange. Vzhledem k tomu, že se ke každé organizaci Exchange může připojit jenom jeden konektor, pokud pro organizaci nainstalujete druhý konektor, nový konektor, který nainstalujete, nahradí původní konektor.

1. Pokud chcete nainstalovat nový konektor, postupujte podle pokynů v části [instalace a konfigurace konektoru Exchange](#install-and-configure-the-intune-exchange-connector) . 
2. Po zobrazení výzvy vyberte **nahradit** a nainstalujte nový konektor.  
   ![Configuration upozornění na nahrazení konektoru @ no__t-1

3. Pokračujte postupem v části [instalace a konfigurace konektoru Intune Exchange](#install-and-configure-the-intune-exchange-connector) a znovu se přihlaste k Intune.
4. V posledním okně vyberte **Zavřít** a dokončete instalaci.  
   @no__t 0Finish nastavení @ no__t-1
 

## <a name="monitor-an-exchange-connector"></a>Monitorování konektoru softwaru Exchange

Po úspěšné konfiguraci softwaru Exchange Connector můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. 

Ověření připojení konektoru Exchange Connector:

1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
2. Vyberte možnost **přístup k místnímu Exchangi** a ověřte stav připojení jednotlivých konektorů Exchange.

Můžete také zjistit datum a čas posledního úspěšného pokusu o synchronizaci.

Od verze Intune 1710 můžete použít [Management Pack System Center Operations Manager pro Exchange Connector a Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Management Pack nabízí různé způsoby, jak monitorovat Exchange Connector, pokud potřebujete řešit problémy.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ruční vynutit rychlou synchronizaci nebo úplnou synchronizaci

Intune Exchange Connector automaticky synchronizuje záznamy zařízení EAS a Intune. Pokud se stav dodržování předpisů změní na zařízení, proces automatické synchronizace pravidelně aktualizuje záznamy, aby bylo možné zablokovat nebo povolit přístup k zařízení.

- **Rychlá synchronizace** probíhá pravidelně, několikrát za den. Rychlá synchronizace načte informace o zařízení pro uživatele s licencí na Intune a na místní Exchange, které jsou cílené na podmíněný přístup a které se od poslední synchronizace změnily.

- **Úplná synchronizace** probíhá ve výchozím nastavení jednou denně. Úplná synchronizace načte informace o zařízení pro všechny uživatele licencované pro Intune a místní Exchange, na které cílí podmíněný přístup. Úplná synchronizace také načte informace Exchange serveru a zajistí, že konfigurace, kterou Intune určí v Azure Portal, bude aktualizována na serveru Exchange. 


Konektor můžete vynutit ke spuštění synchronizace pomocí možností **rychlá synchronizace** nebo **úplné synchronizace** na řídicím panelu Intune:

   1. Na řídicím panelu Intune vyberte **přístup k Exchangi**.
   2. Vyberte **přístup pro místní Exchange**.
   3. Vyberte konektor, který chcete synchronizovat, a pak zvolte **rychlá synchronizace** nebo **Úplná synchronizace**.

## <a name="next-steps"></a>Další kroky

Vytvořte [zásady podmíněného přístupu pro místní Exchange servery](conditional-access-exchange-create.md).
