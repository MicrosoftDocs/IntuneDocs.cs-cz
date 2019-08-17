---
title: Použití privátních certifikátů a certifikátů veřejných klíčů v Microsoft Intune – Azure | Microsoft Docs
description: Přidání nebo vytvoření certifikátů PKCS (Public Key Cryptography Standards) pomocí Microsoft Intune, včetně postupu exportu kořenového certifikátu, konfigurace šablony certifikátu, stažení a instalace Intune Certificate Connectoru (NDES), vytvoření zařízení konfigurační profil a vytvořte profil certifikátu PKCS v Azure a certifikační autoritě.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6cc5b26001c9ceacd5781fc8164ce141c5e42de3
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550153"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurace a používání certifikátů PKCS pomocí Intune

Intune podporuje použití privátních certifikátů a certifikátů PKCS (Public Key párové). Tento článek vám může při konfiguraci požadované infrastruktury, jako jsou místní Certificate connectory, exportovat certifikát PKCS a pak certifikát přidat do profilu konfigurace zařízení v Intune.

Microsoft Intune zahrnuje vestavěná nastavení pro používání certifikátů PKCS pro přístup k prostředkům vaší organizace a jejich ověřování. Certifikáty ověřují a zabezpečují přístup k podnikovým prostředkům, jako je síť VPN nebo Wi-Fi. Tato nastavení nasadíte do zařízení pomocí profilů konfigurace zařízení v Intune.


## <a name="requirements"></a>Požadavky

Pokud chcete používat certifikáty PKCS s Intune, musíte mít následující infrastrukturu:

- **Doména služby Active Directory**:  
  Všechny servery uvedené v této části se musí připojit k doméně služby Active Directory.

  Další informace o instalaci a konfiguraci Active Directory Domain Services (služba AD DS) najdete v článku [Služba AD DS návrh a plánování](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Certifikační autorita**:  
   Certifikační autorita organizace (CA).

  Informace o tom, jak nainstalovat a nakonfigurovat službu AD CS (Active Directory Certificate Services), najdete v [podrobné příručce ke službě Active Directory Certificate Services](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Intune vyžaduje, abyste službu AD CS spustili pomocí certifikační autority (CA) organizace, nikoli pomocí samostatné certifikační autority.

- **Klient**:  
  Pro připojení k certifikační autoritě organizace.

- **Kořenový certifikát**:  
  Je třeba mít vyexportovanou kopii kořenového certifikátu z vaší certifikační autority organizace.

- **Microsoft Intune Certificate Connector** (označuje se taky jako *konektor certifikátů NDES*):  
  Na portálu Intune přejděte na **Konfigurace** > zařízení**konektory** > certifikátů**Přidat**a postupujte podle *pokynů k instalaci konektoru pro PKCS #12*. Pomocí odkazu ke stažení na portálu začněte stahovat instalační program konektoru Certificate Connector **NDESConnectorSetup. exe**.  

  Intune podporuje až 100 instancí tohoto konektoru na každého tenanta, přičemž každá instance je na samostatném Windows serveru. Instanci tohoto konektoru můžete nainstalovat na stejný server jako instanci konektoru certifikátů PFX pro Microsoft Intune. Pokud používáte více konektorů, podporuje infrastruktura konektoru vysokou dostupnost a vyrovnávání zatížení, protože kterákoli dostupná instance konektoru může zpracovávat žádosti o certifikát PKCS. 

  Tento konektor zpracovává žádosti o certifikát PKCS používané pro ověřování nebo podepisování e-mailu S/MIME.

  Microsoft Intune Certificate Connector podporuje také režim FIPS (Federal Information Processing Standard). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Konektor certifikátu PFX pro Microsoft Intune**:  
  Pokud máte v plánu používat šifrování e-mailů S/MIME, Stáhněte konektor pro *importované certifikáty PFX*pomocí portálu Intune.  Přejděte na **Konfigurace** > zařízení**konektory** > certifikátů**Přidat**a postupujte podle *pokynů k instalaci konektoru pro importované certifikáty PFX*. Pomocí odkazu ke stažení na portálu začněte stahovat instalační program **PfxCertificateConnectorBootstrapper. exe**. 

  Každý tenant Intune podporuje jednu instanci tohoto konektoru. Tento konektor můžete nainstalovat na stejný server jako instanci konektoru Microsoft Intune Certificate Connector.

  Tento konektor zpracovává požadavky na soubory PFX importované do Intune pro šifrování e-mailu S/MIME pro konkrétního uživatele.  

  Tento konektor se může automaticky aktualizovat, jakmile budou k dispozici nové verze. Chcete-li použít možnost aktualizace, je nutné:
  - Nainstalujte importovaný konektor PFX Certificate pro Microsoft Intune na vašem serveru.
  - Chcete-li automaticky přijímat důležité aktualizace, zajistěte, aby byly brány firewall otevřené, aby konektor mohl kontaktovat **AutoUpdate.msappproxy.NET** na portu **443**.  


- **Windows Server**:  
  Používáte Windows Server k hostování:

  - Scénáře ověřování a podepisování e-mailů S Microsoft Intune Certificate Connector – pro ověřování a kódování MIME
  - Konektor certifikátů PFX pro scénáře šifrování e-mailu S/MIME pro Microsoft Intune –.

  Na stejný server můžete nainstalovat oba konektory (*Microsoft Intune Certificate Connector* a *PFX Certificate Connector*).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

K ověření zařízení pomocí sítě VPN, Wi-Fi nebo jiných prostředků potřebuje zařízení kořenový certifikát nebo certifikát zprostředkující certifikační autority. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

**Použijte příkazový řádek**:  
1. Přihlaste se ke kořenovému serveru certifikační autority pomocí účtu správce.
 
2. Přejděte na **Spustit** > **běh**a pak zadáním **cmd** otevřete příkazový řádek. 
    
3. Zadáním **příkazu certutil-CA. CERT CA_NAME. cer** exportujte kořenový certifikát jako soubor s názvem *CA_NAME. cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Konfigurace šablon certifikátů v certifikační autoritě

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete konzolu **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů** a vyberte **Spravovat**.
3. Vyhledejte šablonu certifikátu **Uživatel**, klikněte pravým tlačítkem myši a zvolte **Duplikovat šablonu**. Otevřou se **Vlastnosti nové šablony**.

    > [!NOTE]
    > K podepisování a šifrování e-mailů pomocí S/MIME používá mnoho správců samostatné certifikáty pro podepisování a šifrování. Pokud používáte službu Microsoft Active Directory Certificate Services, můžete pro podpisové certifikáty e-mailu S/MIME použít šablonu **Pouze podpis serveru Exchange** a pro šifrovací certifikáty S/MIME můžete použít šablonu **Uživatel serveru Exchange**.  Pokud používáte certifikační autoritu třetí strany, doporučujeme vám projít si pokyny k nastavení podpisových a šifrovacích šablon.

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
13. Aby server spravoval certifikáty pro zaregistrovaná zařízení a uživatele, použijte následující postup:

    1. Klikněte pravým tlačítkem na certifikační autoritu a potom vyberte **Vlastnosti**.
    2. Na kartě Zabezpečení přidejte účet počítače pro server, na kterém konektory (**Microsoft Intune Certificate Connector** nebo **konektor certifikátu PFX pro Microsoft Intune**) běží. 
    3. Udělte oprávnění účtu počítače, která povolují **Vydávat a spravovat certifikáty** a **Vyžádat certifikáty**.

14. Odhlaste se z certifikační autority organizace.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Stažení, instalace a konfigurace konektorů Certificate Connector

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune Certificate Connecnar

> [!IMPORTANT]  
> Microsoft Intune Certificate Connector nejde nainstalovat na vydávající certifikační autoritu (CA) a místo toho se musí nainstalovat na samostatný Windows Server.  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace** > zařízení**certifikační konektory** > **Přidat**.
3. Stáhněte a uložte soubor konektoru do umístění, ke kterému máte přístup ze serveru, na který budete konektor instalovat.

    ![Stažení Microsoft Intune Certificate Connector](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework nebo novější, protože ho NDES Certificate Connector vyžaduje. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Spusťte instalační program (NDESConnectorSetup.exe) a potvrďte výchozí umístění. Konektor se nainstaluje do `\Program Files\Microsoft Intune\NDESConnectorUI`. V možnostech instalačního programu vyberte **distribuci PFX**. Pokračujte až do konce instalace.
    3. Ve výchozím nastavení služba konektoru běží pod místním systémovým účtem. Pokud pro přístup k internetu vyžaduje proxy, ověřte, že účet místní služby má na serveru přístup k nastavení proxy serveru.

5. Microsoft Intune Certificate Connector otevře kartu **registrace** . Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce.
6. Na kartě **Rozšířené** doporučujeme ponechat vybranou možnost **Použít účet SYSTEM tohoto počítače (výchozí)** .
7. **Použít** > **Zavřít**
8. Vraťte se na portál Intune (**certifikační konektory** **Konfigurace** > zařízení v Intune > ). Po chvíli se zobrazí zelená značka zaškrtnutí a **stav připojení** je **aktivní**. Váš server konektoru teď může komunikovat s Intune.
9. Pokud máte webový proxy server ve vašem síťovém prostředí, možná budete potřebovat další konfigurace, aby konektor mohl fungovat. Další informace najdete v tématu [práce se stávajícími místními proxy servery](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) v dokumentaci k Azure Active Directory.

> [!NOTE]  
> Microsoft Intune Certificate Connector podporuje TLS 1,2. Pokud je na serveru, který je hostitelem konektoru, nainstalovaný protokol TLS 1,2, konektor používá TLS 1,2. V opačném případě se používá TLS 1,1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Konektor certifikátu PFX pro Microsoft Intune

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace** > zařízení**certifikační konektory** > **Přidat**
3. Stáhněte a uložte konektor certifikátu PFX pro Microsoft Intune. Uložte ho do umístění přístupného ze serveru, na který chcete konektor nainstalovat.
4. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.6 Framework nebo novější, protože ho konektor certifikátu PFX pro Microsoft Intune vyžaduje. Pokud rozhraní .NET Framework 4.6 nainstalované není, instalační program ho nainstaluje automaticky.
    2. Spusťte instalační program (PfxCertificateConnectorBootstrapper. exe) a přijměte výchozí umístění, které nainstaluje konektor na `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. Služba konektoru běží pod místním systémovým účtem. Pokud pro přístup k internetu vyžaduje proxy, ověřte, že účet místní služby má na serveru přístup k nastavení proxy serveru.

5. Konektor certifikátu PFX pro Microsoft Intune se po instalaci otevře na kartě **Zápis**. Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce pro Azure nebo s oprávněním správce pro Intune.
6. Okno zavřete.
7. Vraťte se do Azure Portal (**certifikační konektory**pro**konfiguraci** > zařízení v Intune > ). Po chvíli se zobrazí zelená značka zaškrtnutí a **stav připojení** je **aktivní**. Váš server konektoru teď může komunikovat s Intune.

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1. Na webu [Azure Portal](https://portal.azure.com) přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
    ![Přejděte na Intune a vytvořte nový profil důvěryhodného certifikátu.](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Zadejte tyto vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

3. Přejděte na **Nastavení** a zadejte soubor .cer kořenového certifikátu CA, který jste předtím vyexportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 2**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

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

    - **Prahová hodnota obnovení (%)** : Doporučuje se 20%.
    - **Období platnosti certifikátu**: Pokud jste šablonu certifikátu nezměnili, může být tato možnost nastavená na jeden rok.
    - **Zprostředkovatel úložiště klíčů (KSP)** : V případě systému Windows vyberte místo, kam chcete uložit klíče na zařízení.
    - **Certifikační autorita**: Zobrazuje interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.
    - **Název certifikační autority**: Zobrazuje název vaší certifikační autority organizace, například "certifikační autorita společnosti Contoso".
    - **Název šablony certifikátu**: Název šablony, kterou jste vytvořili dříve. Pamatujte, že **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*.
    - **Formát názvu subjektu**: Pokud není vyžadováno jinak, nastavte tuto možnost na **běžný název** .
    - **Alternativní název subjektu**: Pokud není vyžadováno jinak, nastavte tuto možnost na **hlavní název uživatele (UPN)** .

4. Vyberte **OK** > **Vytvořit** a profil uložte.
5. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Vytvoření importovaného profilu certifikátu PKCS

Certifikáty, které se dřív vystavily pro konkrétního uživatele, můžete importovat z libovolné certifikační autority v nástroji do Intune. Importované certifikáty se nainstalují na každé zařízení, které si uživatel zaregistruje. Šifrování e-mailu pomocí S/MIME je nejběžnějším scénářem pro import existujících certifikátů PFX do Intune. Uživatel může mít k šifrování e-mailů mnoho certifikátů. Privátní klíče těchto certifikátů se musí nacházet na všech zařízeních uživatele, aby bylo možné dešifrovat dříve šifrované e-maily.

Pokud chcete certifikáty importovat do Intune, můžete použít [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access).

Po importování certifikátů do Intune vytvořte profil **importovaného certifikátu PKCS** a přiřaďte ho ke skupinám Azure Active Directory.

1. Na webu [Azure Portal](https://portal.azure.com) přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
2. Zadejte tyto vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Importovaný certifikát PKCS**.

3. Přejděte na **Nastavení** a zadejte tyto vlastnosti:

    - **Zamýšlený účel**: Zamýšlený účel certifikátů, které jsou naimportovány pro tento profil. Správce může certifikáty importovat pod různými zamýšlenými účely (například ověřování, podepisování pomocí S/MIME nebo šifrování pomocí S/MIME). Zamýšlený účel vybraný v profilu certifikátu odpovídá profilu certifikátu se správně importovanými certifikáty.
    - **Období platnosti certifikátu**: Pokud jste šablonu certifikátu nezměnili, může být tato možnost nastavená na jeden rok.
    - **Zprostředkovatel úložiště klíčů (KSP)** : V případě systému Windows vyberte místo, kam chcete uložit klíče na zařízení.

4. Vyberte **OK** > **Vytvořit** a profil uložte.
5. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="whats-new-for-connectors"></a>Co je nového u konektorů
Aktualizace pro dvě konektory certifikátů jsou vydávány pravidelně. Když aktualizujeme konektor, můžete si přečíst o těchto změnách. 

*Konektor certifikátů PFX pro Microsoft Intune* [podporuje automatické aktualizace](#requirements), zatímco je *konektor Intune Certificate Connector* aktualizovaný ručně.

### <a name="may-17-2019"></a>17. května 2019  
- **Konektor certifikátů PFX pro Microsoft Intune verze 6.1905.0.404**  
  Změny v této verzi:  
  - Opravili jsme problém, kdy se stávající certifikáty PFX budou dál zpracovávat, což způsobí, že konektor přestane zpracovávat nové požadavky. 

### <a name="may-6-2019"></a>6\. května 2019  
- **Konektor certifikátů PFX pro Microsoft Intune verze 6.1905.0.402**  
  Změny v této verzi:  
  - Interval dotazování konektoru se zkracuje z 5 minut na 30 sekund.
 
### <a name="april-2-2019"></a>2\. dubna 2019  
- **Intune Certificate Connector – verze 6.1904.1.0**  
  Změny v této verzi:  
  - Opravili jsme problém, kdy se konektoru nepodaří zaregistrovat se do Intune po přihlášení ke konektoru s globálním účtem správce.  
  - Zahrnuje opravy spolehlivosti při odvolání certifikátu.  
  - Zahrnuje opravy výkonu, které zvyšují rychlost zpracování požadavků certifikátů PKCS.  

- **Konektor certifikátů PFX pro Microsoft Intune verze 6.1904.0.401**
  > [!NOTE]  
  > Automatické aktualizace této verze konektoru PFX nejsou k dispozici do 11. dubna 2019.  

  Změny v této verzi:  
  - Opravili jsme problém, kdy se konektoru nepodaří zaregistrovat se do Intune po přihlášení ke konektoru s globálním účtem správce.  


## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

[Používejte certifikáty SCEP](certificates-scep-configure.md)nebo vystavte [certifikáty PKCS z webové služby správce PKI DigiCert](certificates-digicert-configure.md).


