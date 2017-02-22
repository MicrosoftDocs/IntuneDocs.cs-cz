---
title: "Exchange Connector pro místní EAS | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Exchange ActiveSync MDM – použijte nástroj Connector k umožnění komunikace mezi konzolou správce Intune a místním Exchange Serverem."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2871136fc15f945fe5b757a6e4364d3980832e37
ms.openlocfilehash: 92e4a15630c70ac80dd07684baafbbd15cd2f38c


---

# <a name="install-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure-preview"></a>Instalace místního Exchange Connectoru Intune v Microsoft Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Pokud chcete nastavit připojení umožňující komunikaci Microsoft Intune s Exchange Serverem, který je hostitelem poštovních schránek mobilních zařízení, musíte si z konzoly pro správu Intune stáhnout místní Exchange Connector a nakonfigurovat ho. Intune podporuje pro každé předplatné jenom jedno připojení Exchange Connectoru libovolného typu.

## <a name="on-premises-exchange-connector-requirements"></a>Požadavky na místní Exchange Connector
V následující tabulce jsou uvedené požadavky na počítač, na který instalujete místní Exchange Connector.

|Požadavek|Další informace|
|---------------|--------------------|
|operační systémy;|Intune podporuje místní Exchange Connector na počítači, na kterém běží kterákoli edice Windows Serveru 2008 SP2 (64bitová verze), Windows Serveru 2008 R2, Windows Serveru 2012 nebo Windows Serveru 2012 R2.<br /><br />Connector není podporovaný v žádné instalaci jádra serveru.|
|Microsoft Exchange|Místní Connectory vyžadují Microsoft Exchange 2010 SP1 nebo novější, nebo starší Exchange Online Dedicated. Pokud chcete zjistit, jestli je vaše prostředí Exchange Online Dedicated v **nové** nebo **starší** konfiguraci, kontaktujte svého správce účtů.|
|Autorita pro správu mobilních zařízení| [Nastavte autoritu pro správu mobilních zařízení na Intune](https://docs.microsoft.com/en-us/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).|
|Hardware|Počítač, na který nainstaluje konektor, musí mít minimálně 1,6GHz procesor s 2 GB paměti RAM a 10 GB volného místa na disku.|
|Synchronizace se službou Active Directory|Než použijete Connector k připojení Intune ke svému Exchange Serveru, je potřeba [nastavit synchronizaci služby Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory.|
|Další software|Počítač hostující konektor musí mít úplnou instalaci rozhraní Microsoft .NET Framework 4.5 a musí na něm být nainstalované prostředí Windows PowerShell 2.0.|
|Síť|Počítač, na který jste nainstalovali konektor, musí být v doméně, která má vztah důvěryhodnosti k doméně hostující váš Exchange Server.<br /><br />Počítač vyžaduje konfigurace, které mu umožňují přístup ke službě Intune přes brány firewall nebo proxy servery přes porty 80 a 443. Mezi domény používané službou Intune patří tyto: manage.microsoft.com, &#42;manage.microsoft.com a &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Stažení instalačního balíčku místního Exchange Connectoru

1. V podporovaném operačním systému Windows Server pro místní Exchange Connector otevřete [portál Azure Portal](http://portal.azure.com) z uživatelského účtu, který je správcem klienta Exchange a který má licenci k používání Exchange Serveru.

2.  Zvolte úlohu **Podmíněný přístup**.
3.  Zvolte úlohu **Podmíněný přístup** na portálu Azure Portal a otevřete tak okno **Místní**.

4. V části **Nastavení** zvolte **Exchange ActiveSync On-premises Connector** a pak zvolte **Stáhnout software On-Premises Connector**.

4.  Místní Exchange Connector je v komprimované složce (.zip), která se dá otevřít nebo uložit. V dialogovém okně **Stažení souboru** vyberte na **Uložit** a uložte komprimovanou složku do zabezpečeného umístění.

> [!IMPORTANT]
> Soubory ve složce místního Exchange Connectoru nepřejmenovávejte ani nepřesouvejte. Přesunutí nebo přejmenování obsahu složky způsobí selhání instalace.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalace a konfigurace místního Intune Exchange Connectoru
Při instalaci místního Intune Exchange Connectoru použijte tento postup. Místní Exchange Connector se dá nainstalovat jenom jednou pro každé předplatné Intune a jenom na jeden počítač. Když zkusíte nakonfigurovat další místní Exchange Connector, nahradí se původní připojení tímto novým připojením.

1.  V podporovaném operačním systému pro místní Exchange Connector extrahujte soubory v balíčku **Exchange_Connector_Setup.zip** do zabezpečeného umístění.

2.  Po extrahování souborů otevřete extrahovanou složku a dvojím kliknutím na **Exchange_Connector_Setup.exe** nainstalujte místní Exchange Connector.

    > [!IMPORTANT]
    > Pokud cílová složka není v zabezpečeném umístění, měli byste po instalaci místního Connectoru odstranit soubor certifikátu **WindowsIntune.accountcert**.

3.  V dialogovém okně **Microsoft Intune Exchange Connector** vyberte **On-premises Microsoft Exchange Server** nebo **Hostovaný Microsoft Exchange Server**.

  ![Vyberte typ systému Exchange Server](../media/intune-sa-exchange-connector-config.png)

  V případě místního Exchange zadejte název serveru nebo plně kvalifikovaný název domény Exchange serveru, který je hostitelem role **Server pro klientský přístup**.

  U hostovaného serveru Exchange zadejte adresu serveru Exchange. Adresu URL hostovaného serveru Exchange najdete takto:

    1. Otevřete Outlook Web App pro Office 365.

    2. Zvolte ikonu **?** vlevo nahoře a pak vyberte **O aplikaci**.

    3. Najděte hodnotu **Externí nastavení POP**.

    4. Vyberte **Proxy server** a zadejte nastavení proxy serveru pro svůj hostovaný server Exchange.
        1. Vyberte **Používat proxy server při synchronizaci informací mobilních zařízení**.

        2. Zadejte **název proxy serveru** a **číslo portu** pro přístup na server.

        3. Pokud je potřeba zadat přihlašovací údaje uživatele pro přístup na proxy server, vyberte **Použít pověření k připojení k proxy serveru**. Zadejte **doménu\uživatele** a **heslo**.

        4. Vyberte **OK**.

    5. Do polí **Uživatel (doména\uživatel)** a **Heslo** zadejte přihlašovací údaje potřebné k připojení k Exchange serveru.

    6.  Zadejte přihlašovací údaje správce potřebné pro odesílání oznámení do poštovní schránky Exchange Serveru uživatele. Tato oznámení můžete nakonfigurovat díky zásadám podmíněného přístupu v Intune.

        Zkontrolujte, že je na serveru Exchange pro klientský přístup nainstalovaná služba Automatická konfigurace a Webové služby systému Exchange. Další informace najdete v tématu [Server pro klientský přístup](https://technet.microsoft.com/library/dd298114.aspx).

    7.  Do pole **Heslo** zadejte heslo pro tento účet, aby měla služba Intune přístup k systému Exchange Server.

    8. Vyberte **Připojit**.

Konfigurace připojení může zabrat několik minut.

Software Exchange Connector během konfigurace uloží vaše nastavení proxy serveru, aby byl zajištěný přístup na internet. Pokud se vaše nastavení proxy serveru změní, budete muset Exchange Connector překonfigurovat tak, aby používal aktualizované nastavení proxy serveru.

Až Exchange Connector připojení nastaví, mobilní zařízení přidružená k uživatelům spravovaným v Exchange Connectoru se automaticky synchronizují a přidají se do Exchange Connectoru. Dokončení této synchronizace může chvíli trvat.

> [!NOTE]
> Pokud máte nainstalovaný místní Exchange Connector a odstraníte připojení k systému Exchange, musíte místní Exchange Connector z počítače, na kterém je nainstalovaný, odinstalovat.

## <a name="validate-the-exchange-connection"></a>Ověření připojení k systému Exchange

Po úspěšné konfiguraci softwaru Exchange Connector můžete zobrazit stav připojení a poslední úspěšný pokus o synchronizaci. Na [portálu Azure Portal](http://portal.azure.com) zvolte úlohu **Intune** > **Podmíněný přístup**. V části **Nastavení** vyberte možnost **Exchange On-Premises Connector** a ověřte, že se připojení zobrazí jako aktivní.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.

## <a name="next-steps"></a>Další kroky
[Vytvoření zásady podmíněného přístupu pro místní Exchange](create-conditional-access-policy-for-exchange-on-premises.md)



<!--HONumber=Feb17_HO1-->


