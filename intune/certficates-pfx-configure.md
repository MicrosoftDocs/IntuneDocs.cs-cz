---
title: Použití privátních a veřejných klíčů certifikátů v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidejte nebo vytvořte Public Key Cryptography Standards (PKCS) certifikáty pomocí Microsoft Intune, včetně postupu jak vyexportovat kořenový certifikát, nakonfigurujte šablonu certifikátu, stáhněte a nainstalujte Intune Certificate Connector (NDES), vytvořit zařízení Konfigurační profil a vytvořit profil certifikátu PKCS v Azure a vaší certifikační autority.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e6af5a7d7911d7e8ba12e9fd15ad72ca1e51c74
ms.sourcegitcommit: e23e78a563928ed2b2cbc588f2aa65678f7bb409
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2019
ms.locfileid: "58618469"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurace a používání certifikátů PKCS pomocí Intune

Intune podporuje použití certifikátů pár klíčů privátní a veřejné (PKCS). V tomto článku můžete nakonfigurovat požadované infrastruktury, jako jsou místní konektory certifikát exportovat certifikát PKCS a pak ho přidat do profilu konfigurace zařízení Intune.

Microsoft Intune zahrnuje předdefinované nastavení používat certifikáty PKCS č. pro přístup a ověřování k prostředkům vaší organizace. Ověření certifikátů a zabezpečený přístup k firemním prostředkům, jako je síť VPN nebo Wi-Fi síti. Nasazení těchto nastavení na zařízení pomocí konfiguračních profilů zařízení v Intune.


## <a name="requirements"></a>Požadavky

Používání certifikátů PKCS pomocí Intune, budete potřebovat následující infrastrukturu:

- **Doména služby Active Directory**: Všechny servery uvedené v této části musí být připojené k doméně služby Active Directory.

  Další informace o instalaci a konfiguraci služby Active Directory Domain Services (AD DS) najdete v tématu [návrhu služby AD DS a plánování](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Certifikační autorita**: Certifikační autorita organizace (CA).

  Informace o instalaci a konfiguraci služby Active Directory Certificate Services (AD CS) najdete v tématu [Active Directory podrobném průvodci](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Intune vyžaduje, abyste službu AD CS spustili pomocí certifikační autority (CA) organizace, nikoli pomocí samostatné certifikační autority.

- **Klient**: Pro připojení k certifikační autority organizace.

- **Kořenový certifikát**: Je třeba mít vyexportovanou kopii kořenového certifikátu z vaší certifikační autority organizace.

- **Microsoft Intune Certificate Connector**: Na portálu Intune přejděte na **konfigurace zařízení** > **konektory Certificate Connectors** > **přidat**a postupujte podle pokynů *kroky Instalace konektoru pro PKCS #12*. Použijte odkaz ke stažení portálu a zahájit stahování instalačního programu pro konektor certificate **NDESConnectorSetup.exe**.  
- 
  Tento konektor zpracuje žádosti o certifikát PKCS použitý pro ověřování nebo podepisování e-mailů S/MIME.

  Certifikát konektoru ndes služby také podporuje režim federální informace o zpracování Standard (FIPS). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Importovat konektoru certifikátů PFX pro Microsoft Intune**: Pokud máte v plánu používat šifrování S/MIME e-mailu, použít portál Intune ke stažení je konektor pro *certifikáty PFX importovat*.  Přejděte na **konfigurace zařízení** > **konektory Certificate Connectors** > **přidat**a postupujte podle pokynů *postup instalace konektoru pro Importovat certifikáty PFX*. Použijte odkaz ke stažení na portálu pro stažení instalačního programu spusťte **PfxCertificateConnectorBootstrapper.exe**. 

  Tento konektor zpracovává požadavky na soubory PFX, které jsou importovány do Intune pro šifrování S/MIME e-mailu pro konkrétního uživatele.  

  Tento konektor můžete automaticky aktualizovat při zpřístupnění nových verzí. Funkce aktualizace musíte mít:
  - Instalace konektoru importu certifikátů PFX pro Microsoft Intune na serveru.
  - Automaticky dostávat důležité aktualizace, zajištění brány firewall otevřít, díky kterým můžou konektoru ke kontaktování **autoupdate.msappproxy.net** na portu **443**.  


- **Windows Server**: Můžete použít Windows Server na hostitele:

  - Microsoft Intune Certificate Connectoru – pro ověřování a podpis scénáře e-mailu S/MIME
  - Konektor certifikátu PFX pro Microsoft Intune – pro scénáře šifrování e-mailu S/MIME.

  Oba typy konektorů můžete nainstalovat (*Microsoft Intune Certificate Connector* a *importovat konektor certifikáty PFX*) na stejném serveru.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

K ověření zařízení s VPN, WiFi nebo jiných prostředků, bude nutné zařízení kořenový nebo zprostředkující certifikát CA. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

**Použijte příkazový řádek**:  
1. Přihlaste se ke kořenové certifikační autority serveru pomocí účtu správce.
 
2. Přejděte na **Start** > **spustit**a pak zadejte **Cmd** otevřít příkazový řádek. 
    
3. Zadejte **certutil-ca.cert ca_name.cer** exportovat kořenový certifikát jako soubor s názvem *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Konfigurace šablon certifikátů v certifikační Autoritě

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete konzolu **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů** a vyberte **Spravovat**.
3. Vyhledejte šablonu certifikátu **Uživatel**, klikněte pravým tlačítkem myši a zvolte **Duplikovat šablonu**. Otevřou se **Vlastnosti nové šablony**.

    > [!NOTE]
    > K podepisování a šifrování e-mailů pomocí S/MIME používá mnoho správců samostatné certifikáty pro podepisování a šifrování. Pokud používáte službu Microsoft Active Directory Certificate Services, můžete pro podpisové certifikáty e-mailu S/MIME použít šablonu **Pouze podpis serveru Exchange** a pro šifrovací certifikáty S/MIME můžete použít šablonu **Uživatel serveru Exchange**.  Pokud používáte 3. stran certifikační autority, doporučuje se zkontrolujte jejich pokyny k nastavení šablony Podepisování a šifrování.

4. Na kartě **Kompatibilita**:

    - Nastavte pole **Certifikační autorita** na **Windows Server 2008 R2**.
    - Nastavte pole **Příjemce certifikátu** na **Windows 7 / Server 2008 R2**.

5. Na kartě **Obecné** nastavte **Zobrazovaný název šablony**. Použijte popisný název.

    > [!WARNING]
    > **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*. Poznamenejte si název šablony, budete ho potřebovat později.

6. Ve **Vyřízení žádosti** vyberte **Umožnit export soukromého klíče**.
7. V **Kryptografii** zkontrolujte, že je **Minimální velikost klíče** nastavená na hodnotu 2048.
8. V **Názvu subjektu** zvolte **Dodat v žádosti**.
9. V **Rozšíření** zkontrolujte, jestli jsou v rozšíření **Zásady použití** položky Šifrování systému souborů, Zabezpečení e-mailu a Ověření klienta.

    > [!IMPORTANT]
    > V případě šablon certifikátů pro iOS přejděte na kartu **Rozšíření**, aktualizujte **Použití klíče** a zkontrolujte, že není vybraná možnost **Podpis je důkazem původu**.

10. V **Zabezpečení** přidejte účet počítače pro server, na který instalujete Microsoft Intune Certificate Connector. Pro tento účet povolte oprávnění **Číst** a **Zaregistrovat**.
11. Vyberte **Použít** > **OK** a šablonu certifikátu uložte. Zavřete **konzolu šablon certifikátů**.
12. V konzole **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů** > **Nová** > **Vystavovaná šablona certifikátu**. Zvolte šablonu, kterou jste vytvořili v předchozím postupu. Vyberte **OK**.
13. Server pro správu certifikátů pro zaregistrovaná zařízení a uživatele použijte následující kroky:

    1. Klikněte pravým tlačítkem na certifikační autoritu a potom vyberte **Vlastnosti**.
    2. Na kartě Zabezpečení přidejte účet počítače pro server, na kterém konektory (**Microsoft Intune Certificate Connector** nebo **konektor certifikátu PFX pro Microsoft Intune**) běží. 
    3. Udělte oprávnění účtu počítače, která povolují **Vydávat a spravovat certifikáty** a **Vyžádat certifikáty**.

14. Odhlaste se z certifikační autority organizace.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Stažení, instalace a konfigurace konektorů Certificate Connector

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune Certificate Connecnar

> [!IMPORTANT]  
> Microsoft Intune Certificate Connector se nedá nainstalovat na vydávající certifikační autoritu (CA) a místo toho musí být nainstalován na samostatném serveru Windows.  

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby**, vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **konfigurace zařízení** > **certifikace konektorů** > **přidat**.
3. Stáhněte a uložte soubor konektor na umístění máte přístup ze serveru, kam se chcete dostat k instalaci konektoru.

    ![Stáhnout konektor NDES](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework nebo novější, protože ho NDES Certificate Connector vyžaduje. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Spusťte instalační program (NDESConnectorSetup.exe) a potvrďte výchozí umístění. Konektor se nainstaluje do `\Program Files\Microsoft Intune\NDESConnectorUI`. V možnostech instalačního programu vyberte **distribuci PFX**. Pokračujte až do konce instalace.
    3. Ve výchozím nastavení služba konektoru běží pod místním systémovým účtem. Pokud pro přístup k internetu vyžaduje proxy, ověřte, že účet místní služby má na serveru přístup k nastavení proxy serveru.

5. NDES Connector otevře kartu **registrace**. Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce.
6. Na kartě **Rozšířené** doporučujeme ponechat vybranou možnost **Použít účet SYSTEM tohoto počítače (výchozí)**.
7. **Použít** > **Zavřít**
8. Přejděte zpět na portálu Intune (**Intune** > **konfigurace zařízení** > **certifikace konektorů**). Po chvíli se zobrazí zelená značka zaškrtnutí a **stav připojení** je **aktivní**. Váš server konektoru teď může komunikovat s Intune.
9. Pokud máte webový proxy server v síťovém prostředí, můžete potřebovat další konfigurace, které umožňují fungování konektoru. Další informace najdete v tématu [práce s existující místní proxy servery](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) v dokumentaci k Azure Active Directory.

> [!NOTE]  
> Microsoft Intune Certificate Connector podporuje TLS 1.2. Pokud je protokol TLS 1.2 nainstalovaná na serveru, který je hostitelem konektoru, konektor používá TLS 1.2. V opačném případě se používá protokol TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Konektor certifikátu PFX pro Microsoft Intune

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **konfigurace zařízení** > **certifikace konektorů** > **přidat**
3. Stáhněte a uložte konektor certifikátu PFX pro Microsoft Intune. Uložte ho do umístění přístupného ze serveru, na který chcete konektor nainstalovat.
4. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.6 Framework nebo novější, protože ho konektor certifikátu PFX pro Microsoft Intune vyžaduje. Pokud rozhraní .NET Framework 4.6 nainstalované není, instalační program ho nainstaluje automaticky.
    2. Spusťte instalační program (PfxCertificateConnectorBootstrapper.exe) a přijměte výchozí umístění, která konektor se nainstaluje do `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. Služba konektoru běží pod místním systémovým účtem. Pokud pro přístup k internetu vyžaduje proxy, ověřte, že účet místní služby má na serveru přístup k nastavení proxy serveru.

5. Konektor certifikátu PFX pro Microsoft Intune se po instalaci otevře na kartě **Zápis**. Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce pro Azure nebo s oprávněním správce pro Intune.
6. Okno zavřete.
7. Přejděte zpět na webu Azure portal (**Intune** > **konfigurace zařízení** > **certifikace konektorů**). Po chvíli se zobrazí zelená značka zaškrtnutí a **stav připojení** je **aktivní**. Váš server konektoru teď může komunikovat s Intune.

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1. Na webu [Azure Portal](https://portal.azure.com) přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
    ![Přejděte do Intune a vytvoření nového profilu důvěryhodného certifikátu](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Zadejte tyto vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

3. Přejděte na **Nastavení** a zadejte soubor .cer kořenového certifikátu CA, který jste předtím vyexportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 3**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

   ![Vytvoření profilu a nahrání důvěryhodného certifikátu](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Vyberte **OK** > **Vytvořit** a profil uložte.
5. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Na webu [Azure Portal](https://portal.azure.com) přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
2. Zadejte tyto vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Certifikát PKCS**.

3. Přejděte na **Nastavení** a zadejte tyto vlastnosti:

    - **Prahová hodnota obnovení (%)**: Doporučuje se 20 %.
    - **Období platnosti certifikátu**: Pokud jste nezměnili šablonu certifikátu, může být tato možnost nastavená na jeden rok.
    - **Zprostředkovatel úložiště klíčů (KSP)**: Pro Windows vyberte, kam chcete ukládat klíče v zařízení.
    - **Certifikační autorita**: Zobrazí interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.
    - **Název certifikační autority**: Uvádí název vaší certifikační autority organizace, jako je například "Certifikační autority společnosti Contoso".
    - **Název šablony certifikátu**: Název šablony vytvořili dříve. Pamatujte, že **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*.
    - **Formát názvu subjektu**: Tuto možnost nastavte na **běžný název** Pokud není potřeba jiný.
    - **Alternativní název subjektu**: Tuto možnost nastavte na **hlavní název uživatele (UPN)** Pokud není potřeba jiný.

4. Vyberte **OK** > **Vytvořit** a profil uložte.
5. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Vytvoření importovaného profilu certifikátu PKCS

Můžete importovat certifikáty dříve vydané pro konkrétního uživatele z jakékoli certifikační Autority v Intune. Importované certifikáty se nainstalují na každé zařízení, které si uživatel zaregistruje. Šifrování e-mailu pomocí S/MIME je nejběžnějším scénářem pro import existujících certifikátů PFX do Intune. Uživatel může mít mnoho certifikátů k šifrování e-mailu. Privátní klíče těchto certifikátů se musí nacházet na všech zařízeních uživatele, aby bylo možné dešifrovat dříve šifrované e-maily.

Pokud chcete certifikáty importovat do Intune, můžete použít [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access).

Po importování certifikátů do Intune vytvořte profil **importovaného certifikátu PKCS** a přiřaďte ho ke skupinám Azure Active Directory.

1. Na webu [Azure Portal](https://portal.azure.com) přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
2. Zadejte tyto vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Importovaný certifikát PKCS**.

3. Přejděte na **Nastavení** a zadejte tyto vlastnosti:

    - **Zamýšlený účel**: Zamýšlený účel certifikáty, které jsou importovány pro tento profil. Správce může certifikáty importovat pod různými zamýšlenými účely (například ověřování, podepisování pomocí S/MIME nebo šifrování pomocí S/MIME). Zamýšlený účel vybraný v profilu certifikátu odpovídá profilu certifikátu se správně importovanými certifikáty.
    - **Období platnosti certifikátu**: Pokud jste nezměnili šablonu certifikátu, může být tato možnost nastavená na jeden rok.
    - **Zprostředkovatel úložiště klíčů (KSP)**: Pro Windows vyberte, kam chcete ukládat klíče v zařízení.

4. Vyberte **OK** > **Vytvořit** a profil uložte.
5. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

[Používání certifikátů SCEP](certificates-scep-configure.md), nebo [vydávání certifikátů PKCS od společnosti Symantec PKI manager webová služba](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Přechod do Intune na webu Azure Portal a vytvoření nového profilu důvěryhodného certifikátu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Vytvoření profilu a nahrání důvěryhodného certifikátu"
[ConnectorDownload]: ./media/certificates-download-connector.png "Stažení konektoru certifikátu z portálu Azure Portal"  
