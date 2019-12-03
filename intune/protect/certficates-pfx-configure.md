---
title: Použití privátních certifikátů a certifikátů veřejných klíčů v Microsoft Intune – Azure | Microsoft Docs
description: Použijte certifikáty PKCS (Public Key Cryptography Standards) s Microsoft Intune. To zahrnuje práci s kořenovými certifikáty a šablonami certifikátů, instalaci konektoru Intune Certificate Connector (NDES) a profilů konfigurace zařízení pro certifikát PKCS.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3db085e6e88f8f57eb0276afa77290df8574568f
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801718"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurace a používání certifikátů PKCS pomocí Intune

Intune podporuje použití privátních certifikátů a certifikátů PKCS (Public Key párové). Tento článek vám může při konfiguraci požadované infrastruktury, jako jsou místní Certificate connectory, exportovat certifikát PKCS a pak certifikát přidat do profilu konfigurace zařízení v Intune.

Microsoft Intune zahrnuje vestavěná nastavení pro používání certifikátů PKCS pro přístup k prostředkům vaší organizace a jejich ověřování. Certifikáty ověřují a zabezpečují přístup k podnikovým prostředkům, jako je síť VPN nebo Wi-Fi. Tato nastavení nasadíte do zařízení pomocí profilů konfigurace zařízení v Intune.

Informace o použití importovaných certifikátů PKCS najdete v tématu [importované certifikáty PFX](certificates-imported-pfx-configure.md).


## <a name="requirements"></a>požadavky

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

- **Microsoft Intune Certificate Connector** (označovaný také jako *konektor pro NDES Certificate Connector*):  
  Na portálu Intune přejděte na **Konfigurace zařízení** > **konektory certifikátů** > **Přidat**a postupujte podle pokynů pro *instalaci konektoru pro PKCS #12*. Pomocí odkazu ke stažení na portálu začněte stahovat instalační program konektoru Certificate Connector **NDESConnectorSetup. exe**.  

  Intune podporuje až 100 instancí tohoto konektoru na každého tenanta. Každá instance připojení musí být na samostatném Windows serveru. Instanci tohoto konektoru můžete nainstalovat na stejný server jako instanci konektoru certifikátů PFX pro Microsoft Intune. Když použijete více konektorů, infrastruktura konektoru podporuje vysokou dostupnost a vyrovnávání zatížení, protože kterákoli dostupná instance konektoru může zpracovávat žádosti o certifikát PKCS. 

  Tento konektor zpracovává žádosti o certifikát PKCS používané pro ověřování nebo podepisování e-mailu S/MIME.

  Microsoft Intune Certificate Connector podporuje také režim FIPS (Federal Information Processing Standard). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Konektor certifikátu PFX pro Microsoft Intune**:  
  Pokud plánujete používat e-mailové šifrování S/MIME, Stáhněte si pomocí portálu Intune *Certificate Connector* , který podporuje import certifikátů PFX.  Přejděte na **Konfigurace zařízení** > **konektory certifikátů** > **Přidat**a postupujte podle *pokynů k instalaci konektoru pro importované certifikáty PFX*. Pomocí odkazu ke stažení na portálu začněte stahovat instalační program **PfxCertificateConnectorBootstrapper. exe**. 

  Každý tenant Intune podporuje jednu instanci tohoto konektoru. Tento konektor můžete nainstalovat na stejný server jako instanci konektoru Microsoft Intune Certificate Connector.

  Tento konektor zpracovává požadavky na soubory PFX importované do Intune pro šifrování e-mailu S/MIME pro konkrétního uživatele.  

  Tento konektor se může automaticky aktualizovat, jakmile budou k dispozici nové verze. Chcete-li použít možnost aktualizace, je nutné:
  - Nainstalujte na server konektor PFX Certificate Connector pro Microsoft Intune.  
  - Chcete-li automaticky přijímat důležité aktualizace, zajistěte, aby byly brány firewall otevřené, aby konektor mohl kontaktovat **AutoUpdate.msappproxy.NET** na portu **443**.   

  Další informace o koncových bodech sítě, které Intune a přístup k konektoru získáte, najdete v tématu [koncové body sítě pro Microsoft Intune](../fundamentals/intune-endpoints.md).

- **Windows Server**:  
  Používáte Windows Server k hostování:

  - Scénáře ověřování a podepisování e-mailů S Microsoft Intune Certificate Connector – pro ověřování a kódování MIME
  - Konektor certifikátů PFX pro scénáře šifrování e-mailu S/MIME pro Microsoft Intune –.

  Intune podporuje instalaci *konektoru PFX Certificate* na stejném serveru jako *Microsoft Intune Certificate Connector*.
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

K ověření zařízení pomocí sítě VPN, Wi-Fi nebo jiných prostředků potřebuje zařízení kořenový certifikát nebo certifikát zprostředkující certifikační autority. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

**Použijte příkazový řádek**:  
1. Přihlaste se ke kořenovému serveru certifikační autority pomocí účtu správce.
 
2. Přejděte na **Start** > **Spustit**a pak zadejte **cmd** pro otevření příkazového řádku. 
    
3. Zadáním **příkazu certutil-CA. cert CA_NAME. cer** exportujte kořenový certifikát jako soubor s názvem *CA_NAME. cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Konfigurace šablon certifikátů v certifikační autoritě

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete konzolu **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů** a vyberte **Spravovat**.
3. Vyhledejte šablonu certifikátu **uživatel** , klikněte na ni pravým tlačítkem myši a vyberte možnost **Duplikovat šablonu** , čímž otevřete **Vlastnosti nové šablony**.

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

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Stažení, instalace a konfigurace Microsoft Intune Certificate Connector

> [!IMPORTANT]  
> Microsoft Intune Certificate Connector nejde nainstalovat na vydávající certifikační autoritu (CA) a místo toho se musí nainstalovat na samostatný Windows Server.  

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte možnost **Správa tenanta** > **konektory a tokeny** > **konektory certifikátů** >  **+ Přidat**.

3. Klikněte na *Stáhnout software Certificate Connector* pro konektor pro PKCS #12 a uložte soubor do umístění, ke kterému máte přístup ze serveru, na který budete konektor instalovat.

   ![Stažení Microsoft Intune Certificate Connector](./media/certficates-pfx-configure/download-ndes-connector.png)
 
4. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework nebo novější, protože ho NDES Certificate Connector vyžaduje. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Spusťte instalační program (NDESConnectorSetup.exe) a potvrďte výchozí umístění. Konektor se nainstaluje do `\Program Files\Microsoft Intune\NDESConnectorUI`. V možnostech instalačního programu vyberte **distribuci PFX**. Pokračujte až do konce instalace.
    3. Ve výchozím nastavení služba konektoru běží pod místním systémovým účtem. Pokud pro přístup k internetu vyžaduje proxy, ověřte, že účet místní služby má na serveru přístup k nastavení proxy serveru.

5. Microsoft Intune Certificate Connector otevře kartu **registrace** . Pokud chcete povolit připojení k Intune, **přihlaste**se a zadejte účet s globálním oprávněním správce.
6. Na kartě **Rozšířené** doporučujeme ponechat vybranou možnost **Použít účet SYSTEM tohoto počítače (výchozí)** .
7. **Použít** > **Zavřít**
8. Vraťte se na portál Intune (konfiguracezařízení  > **Konfigurace zařízení** > **certifikační konektory**). Po chvíli se zobrazí zelená značka zaškrtnutí a **stav připojení** je **aktivní**. Váš server konektoru teď může komunikovat s Intune.
9. Pokud máte webový proxy server ve vašem síťovém prostředí, možná budete potřebovat další konfigurace, aby konektor mohl fungovat. Další informace najdete v tématu [práce se stávajícími místními proxy servery](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) v dokumentaci k Azure Active Directory.

> [!NOTE]  
> Microsoft Intune Certificate Connector podporuje TLS 1,2. Pokud je na serveru, který je hostitelem konektoru, nainstalovaný protokol TLS 1,2, konektor používá TLS 1,2. V opačném případě se používá TLS 1,1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.

   ![Přejděte na Intune a vytvořte nový profil důvěryhodného certifikátu.](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Zadejte následující vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

4. Vyberte **Nastavení**a zadejte soubor. cer kořenový certifikát certifikační autority, který jste předtím exportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 2**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

   ![Vytvoření profilu a nahrání důvěryhodného certifikátu](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png)

5. Vyberte **OK** > **Vytvořit** a profil uložte.

6. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](../configuration/device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfigurační profily** > **vytvořit profil**.

3. Zadejte následující vlastnosti:

    - Zadejte **Název** profilu.
    - Volitelně můžete nastavit popis.
    - Zadejte **Platformu**, na kterou se má profil nasadit.
    - Nastavte **Typ profilu** na **Certifikát PKCS**.

4. Vyberte **Nastavení**a nakonfigurujte vlastnosti, které se vztahují na vybranou platformu:
   
   |Nastavení     | Platforma     | Details   |
   |------------|------------|------------|
   |**Prahová hodnota obnovení (%)**        |Vše         |Doporučuje se 20%  | 
   |**Období platnosti certifikátu**  |Vše         |Pokud jste šablonu certifikátu nezměnili, může být tato možnost nastavená na jeden rok. |
   |**Zprostředkovatel úložiště klíčů (KSP)**   |Windows 10  | V případě systému Windows vyberte místo, kam chcete uložit klíče na zařízení. |
   |**Certifikační autorita**      |Vše         |Zobrazuje interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.  |
   |**Název certifikační autority** |Vše         |Zobrazuje název vaší certifikační autority organizace, například "certifikační autorita společnosti Contoso". |
   |**Typ certifikátu**             |macOS       |Vyberte typ: <br> **-** **uživatelské** certifikáty mohou v předmětu a síti SAN certifikátu obsahovat atributy uživatele i zařízení. <br><br>**-** certifikáty **zařízení** mohou obsahovat pouze atributy zařízení v předmětu a San certifikátu. Použijte zařízení pro scénáře, jako jsou například zařízení bez uživatele, jako jsou veřejné terminály nebo jiná sdílená zařízení.  <br><br> Tento výběr má vliv na formát názvu subjektu. |
   |**Formát názvu subjektu**          |Vše         |U většiny platforem nastavte tuto možnost na **běžný název** , pokud není vyžadováno jinak.<br><br>Pro macOS se formát názvu subjektu určuje podle typu certifikátu. Další informace najdete v části [Formát názvu subjektu pro MacOS](#subject-name-format-for-macos) dále v tomto článku. |
   |**Alternativní název subjektu**     |Vše         |Pokud není vyžadováno jinak, nastavte tuto možnost na **hlavní název uživatele (UPN)** . |
   |**Rozšířené použití klíče**           |**-** Správce zařízení s Androidem <br>**-** Android Enterprise (*vlastník zařízení*, *pracovní profil*) <br> **-** Windows 10 |Certifikáty obvykle vyžadují *ověření klienta* , aby se mohl uživatel nebo zařízení ověřit na serveru. |
   |**Povolí všem aplikacím přístup k privátnímu klíči.** |macOS  |Nastavením této vlastnosti **povolíte** aplikacím, které jsou nakonfigurované pro přidružené zařízení Mac, přístup k privátnímu klíči certifikátů PKCS. <br><br> Další informace o tomto nastavení najdete v tématu *AllowAllAppsAccess* v části referenční část certifikátu [konfiguračního profilu](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) v dokumentaci pro vývojáře Apple. |
   |**Kořenový certifikát**             |**-** Správce zařízení s Androidem <br> **-** Android Enterprise (*vlastník zařízení*, *pracovní profil*) |Vyberte profil certifikátu od kořenové certifikační autority, který byl dříve přiřazen. |

5. Vyberte **OK** > **Vytvořit** a profil uložte.

6. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](../configuration/device-profile-assign.md).

   > [!NOTE]
   > V zařízeních s profilem podnikového systému Android nejsou v zařízení vidět certifikáty nainstalované pomocí profilu certifikátu PKCS. Pokud chcete potvrdit úspěšné nasazení certifikátu, zkontrolujte stav profilu v konzole Intune.

### <a name="subject-name-format-for-macos"></a>Formát názvu subjektu pro macOS

Když vytváříte profil certifikátu macOS PKCS, možnosti pro formát názvu subjektu závisí na zvoleném typu certifikátu. buď na **uživatele** , nebo na **zařízení**.  

> [!NOTE]  
> K dispozici je známý problém s používáním PKCS k získání certifikátů, [které mají stejný problém jako u protokolu SCEP](certificates-profile-scep.md#avoid-certificate-signing-requests-with-escaped-special-characters) , když název subjektu ve výsledné žádosti o podepsání certifikátu (CSR) obsahuje jeden z následujících znaků jako řídicí znak (následovaný zpětné lomítko \\):
> - \+
> - ;
> - ,
> - =

- **Typ uživatelského certifikátu**  
  Možnosti formátu pro *Formát názvu subjektu* zahrnují dvě proměnné: **běžný název (CN)** a **e-mail (e)** . **Běžný název (CN)** můžete nastavit na některou z těchto proměnných:

  - **CN = {{username}}** : hlavní název uživatele (UPN), například janedoe@contoso.com.
  - **CN={{AAD_Device_ID}}** : ID přiřazené při registraci zařízení ve službě AD (Azure Active Directory). Toto ID se obvykle používá k ověření ve službě Azure AD.
  - **CN = {{sériové}}** : jedinečné sériové číslo (SN) obvykle používané výrobcem k identifikaci zařízení.
  - **CN = {{IMEINumber}}** : jedinečné číslo IMEI (International Mobile Equipment Identity), které se používá k identifikaci mobilního telefonu.
  - **CN = {{OnPrem_Distinguished_Name}}** : sekvence relativních rozlišujících názvů oddělená čárkou, například *CN = Jana Karásek, OU = UserAccounts, DC = Corp, DC = contoso, DC = com*.

    Pokud chcete použít proměnnou *{{OnPrem_Distinguished_Name}}* , proveďte synchronizaci atributu uživatele *onpremisesdistinguishedname* pomocí [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) do služby Azure AD.

  - **CN = {{onPremisesSamAccountName}}** : Správci můžou synchronizovat atribut sAMAccountName ze služby Active Directory do Azure AD pomocí služby Azure AD Connect do atributu s názvem *onPremisesSamAccountName*. Intune může tuto proměnnou nahradit jako součást žádosti o vystavení certifikátu v předmětu certifikátu. Atribut samAccountName je přihlašovací jméno uživatele používané k podpoře klientů a serverů z předchozí verze Windows (Pre-Windows 2000). Formát přihlašovacího jména uživatele je: *DomainName\testUser*nebo pouze *testUser*.

    Pokud chcete použít proměnnou *{{onPremisesSamAccountName}}* , nezapomeňte synchronizovat atribut uživatele *onPremisesSamAccountName* pomocí [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) do Azure AD.

  Kombinací jedné nebo několika těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu, jako třeba:  
  - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
  
  Tento příklad zahrnuje formát názvu subjektu, který používá proměnné CN a E a řetězce pro hodnoty organizační jednotky, organizace, umístění, stav a země. Článek [Funkce CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) popisuje tuto funkci a její podporované řetězce.

- **Typ certifikátu zařízení**  
  Možnosti formátu pro formát názvu subjektu zahrnují následující proměnné: 
  - **{{AAD_Device_ID}}**
  - **{{Device_Serial}}**
  - **{{Device_IMEI}}**
  - **{{Sériové}}**
  - **{{IMEINumber}}**
  - **{{AzureADDeviceId}}**
  - **{{WiFiMacAddress}}**
  - **{{IMEI}}**
  - **{{Název_zařízení}}**
  - **{{FullyQualifiedDomainName}}** *(platí jenom pro zařízení se systémem Windows a zařízení připojená k doméně)*
  - **{{MEID}}**

  Tyto proměnné můžete zadat následovaný textem pro proměnnou v textovém poli. Například běžný název pro zařízení s názvem *zařízení1* se dá přidat jako **CN = {{název_zařízení}} zařízení1**.

  > [!IMPORTANT]  
  > - Když zadáte proměnnou, uveďte její název do složených závorek {}, jak je vidět v příkladu, aby nedošlo k chybě.  
  > - Vlastnosti zařízení používané v *předmětu* nebo *síti SAN* certifikátu zařízení, jako jsou **IMEI**, **sériové**a **FullyQualifiedDomainName**, jsou vlastnosti, které by mohly být falešné osobou, která by mohla mít přístup k zařízení.
  > - Zařízení musí podporovat všechny proměnné určené v profilu certifikátu pro daný profil k instalaci na toto zařízení.  Pokud se například používá **{{IMEI}}** v názvu subjektu profilu SCEP a je přiřazeno k zařízení, které nemá číslo IMEI, profil se nepodaří nainstalovat.  
 


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

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](../configuration/device-profile-assign.md) a [sledujte jeho stav](../configuration/device-profile-monitor.md).

[Použijte SCEP pro certifikáty](certificates-scep-configure.md)nebo [vydejte certifikáty PKCS z webové služby správce infrastruktury veřejných klíčů Symantec](certificates-digicert-configure.md).