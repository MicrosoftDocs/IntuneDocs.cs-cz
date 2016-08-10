---
title: "Exchange Connector pro místní EAS | Microsoft Intune"
description: "Použijte nástroj Connector k umožnění komunikace mezi konzolou správce Intune a místním Exchange Serverem pro Exchange ActiveSync MDM."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 18614cc272323b8031c94b8e582f80aa5c06d9d3


---

# Instalace místního konektoru Intune Exchange Connector


Pokud chcete nastavit připojení umožňující komunikaci Microsoft Intune s Exchange Serverem, který je hostitelem poštovních schránek mobilních zařízení, musíte si z konzoly pro správu Intune stáhnout software On-Premises Connector a nakonfigurovat ho. Intune podporuje pro každé předplatné jenom jedno připojení konektoru Exchange libovolného typu.

## Požadavky na konektor On-Premises Connector
V následující tabulce jsou uvedené požadavky na počítač, na který instalujete místní Exchange Connector.

|Požadavek|Další informace|
|---------------|--------------------|
|operační systémy;|Intune podporuje místní Exchange Connector na počítači, na kterém běží kterákoli edice systému Windows Server 2008 SP2 (64bitová verze), Windows Server 2008 R2, Windows Server 2012 nebo Windows Server 2012 R2.<br /><br />Konektor není podporovaný v žádné instalaci jádra serveru.|
|Verze Microsoft Exchange|On-Premises Connector vyžaduje Microsoft Exchange 2010 SP1 nebo novější, nebo starší Exchange Online Dedicated. Pokud chcete zjistit, jestli je vaše prostředí Exchange Online Dedicated v **nové** nebo **starší** konfiguraci, kontaktujte vašeho account manažera.|
|Autorita pro správu mobilních zařízení| [Nastavte autoritu pro správu mobilních zařízení na Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority).|
|Hardware|Počítač, na který nainstaluje konektor, musí mít minimálně 1,6GHz procesor s 2 GB paměti RAM a 10 GB volného místa na disku.|
|Synchronizace se službou Active Directory|Než použijete některý z konektorů k připojení Intune ke svému Exchange Serveru, je potřeba [nastavit synchronizaci služby Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory.|
|Další software|Počítač hostující konektor musí mít úplnou instalaci rozhraní Microsoft .NET Framework 4 a musí na něm být nainstalované prostředí Windows PowerShell 2.0.|
|Síť|Počítač, na který jste nainstalovali konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall nebo proxy servery přes porty 80 a 443. Mezi domény používané službu Intune patří tyto: manage.microsoft.com, &#42;manage.microsoft.com a &#42;.manage.microsoft.com.|
|Nakonfigurovaný a spuštěný hostovaný systém Exchange|Další informace najdete v tématu [Exchange Server 2016](https://technet.microsoft.com/library/mt170645.aspx). |

### Požadavky rutin systému Exchange

Musíte vytvořit uživatelský účet služby Active Directory, který bude konektor Intune Exchange Connector používat. Tento účet musí mít oprávnění ke spouštění těchto požadovaných rutin prostředí Windows PowerShell:


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

## Stažení instalačního balíčku softwaru On-Premises Exchange Connector

1. V podporovaném operačním systému Windows Serveru pro místní Exchange Connector otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com) (http://manage.microsoft.com) pomocí uživatelského účtu, který je správcem klienta Exchange s licencí k používání systému Exchange Server.
![Otevření nastaveného připojení k systému Exchange](../media/ExchangeConnector.gif)

2.  V podokně zástupců pracovních prostorů zvolte **Správce**, zvolte **Správa mobilních zařízení** > **Microsoft Exchange**, a pak zvolte **Nastavit připojení k systému Exchange**.

3.  Na stránce **Nastavit připojení k systému Exchange** vyberte **Stáhnout software On-Premises Connector**.

4.  Software On-Premises Exchange Connector je v komprimované složce (.zip), která se dá otevřít nebo uložit. V dialogovém okně **Stažení souboru** vyberte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.

> [!IMPORTANT]
> Soubory ve složce softwaru On-Premises Exchange Connector nepřejmenovávejte ani nepřesouvejte. Přesunutím nebo přejmenováním obsahu složky instalaci porušíte.

## Instalace a konfigurace softwaru Intune On-Premises Exchange Connector
Při instalaci softwaru Intune On-Premises Connector použijte následující postup. Software On-Premises Exchange Connector se dá nainstalovat jenom jednou pro každé předplatné Intune a jenom na jeden počítač. Když zkusíte nakonfigurovat další software On-Premises Exchange Connector, nahradí se původní připojení tímto novým připojením.

1.  V podporovaném operačním systému pro On-Premises Exchange Connector extrahujte soubory v balíčku **Exchange_Connector_Setup.zip** do zabezpečeného umístění.

2.  Po extrahování souborů otevřete extrahovanou složku a dvojím kliknutím na **Exchange_Connector_Setup.exe** nainstalujte software On-Premises Exchange Connector.

    > [!IMPORTANT]
    > Pokud cílová složka není v zabezpečeném umístění, měli byste po instalaci konektoru On-Premises Connector odstranit soubor certifikátu **WindowsIntune.accountcert**.

3.  V poli **Server Exchange** vyberte typ prostředí serveru Exchange, tedy **Místní Microsoft Exchange Server** nebo **Hostovaný Microsoft Exchange Server**.

  ![Vyberte typ systému Exchange Server](../media/IntuneSA1dconfigureExchConnector.png)

  V případě místního serveru Exchange zadejte název serveru nebo plně kvalifikovaný název domény serveru Exchange, který je hostitelem role **Server pro klientský přístup**.

  U hostovaného serveru Exchange zadejte adresu serveru Exchange. Adresu URL hostovaného serveru Exchange najdete takto:

      1.  Otevřete Outlook Web App pro Office 365.

      2.  Vyberte ikonu ? v levém horním rohu a vyberte **O aplikaci**.

      3.  Najděte hodnotu **Externí nastavení POP** .

      4.  Vyberte **Proxy server** a zadejte nastavení proxy serveru pro svůj hostovaný server Exchange.
        1.  Vyberte **Používat proxy server při synchronizaci informací mobilních zařízení**.

        2.  Zadejte **název proxy serveru** a **číslo portu** pro přístup na server.

        3.  Pokud je potřeba zadat přihlašovací údaje uživatele pro přístup na proxy server, vyberte Použít pověření k připojení k proxy serveru a zadejte položku **doména\uživatel** a **heslo**.

        4.  Vyberte **OK**.

5.  Zadejte uživatelské údaje a položky **Uživatel (doména\uživatel)** a **Heslo** potřebné k připojení k serveru Exchange.

6.  Zadejte přihlašovací údaje správce potřebné pro odesílání oznámení do poštovní schránky Exchange uživatele. Tato oznámení se dají konfigurovat prostřednictvím zásad podmíněného přístupu v Intune.

    Zkontrolujte, že je na serveru Exchange pro klientský přístup nainstalovaná služba Automatická konfigurace a Webové služby systému Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

7.  Do pole **Heslo** zadejte heslo pro tento účet, aby měla služba Intune přístup k systému Exchange Server.

8. Vyberte **Připojit**.

    Nastavení připojení může pár minut trvat.

Software Exchange Connector během konfigurace uloží vaše nastavení proxy serveru, aby byl zajištěný přístup na internet. Pokud se vaše nastavení proxy serveru změní, budete muset software Exchange Connector překonfigurovat tak, aby používal aktualizované nastavení proxy serveru.

Až Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v softwaru Exchange Connector se automaticky synchronizují a přidají se do softwaru Exchange Connector. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud máte nainstalovaný software On-Premises Exchange Connector a odstraníte připojení k systému Exchange, musíte software On-Premises Exchange Connector z počítače, na kterém je nainstalovaný, odinstalovat.

## Ověření připojení k systému Exchange

Po úspěšné konfiguraci softwaru Exchange Connector můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) zvolte pracovní prostor **SPRÁVCE**, v části **Správa mobilních zařízení** zvolte **Microsoft Exchange** a ověřte, že se v části **Informace o připojení systému Exchange** zobrazují podrobnosti, které jste zadali.


Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.



<!--HONumber=Jul16_HO5-->


