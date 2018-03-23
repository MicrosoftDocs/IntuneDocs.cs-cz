---
title: Vydání certifikátů PKCS Symantec pomocí Microsoft Intune
titlesuffix: ''
description: Instalace a konfigurace nástroje Intune Certificate Connector k vydávání certifikátů PKCS Symantec z webové služby správce infrastruktury veřejných klíčů Symantec do zařízení spravovaných pomocí Intune
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fbb0ccd21ff15cf86656d7badf08002f1e42bb3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Nastavení nástroje Intune Certificate Connector pro webovou službu správce infrastruktury veřejných klíčů Symantec

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V tomto článku se dozvíte, jak nainstalovat a nakonfigurovat nástroj Intune Certificate Connector k vydávání certifikátů PKCS Symantec z webové služby správce infrastruktury veřejných klíčů Symantec do zařízení spravovaných pomocí Intune.

V tomto článku se bude webová služba správce infrastruktury veřejných klíčů Symantec dále nazývat CA Symantec. Pokud jste již nakonfigurovali Intune Certificate Connector k vydávání certifikátů PKCS a certifikátů SCEP z certifikační autority Microsoft (CA), můžete stejný konektor použít ke konfiguraci a vystavování certifikátů PKCS od certifikační autority Symantec. V takovém případě může Intune Certificate Connector vydat následující certifikáty:

* Certifikáty PKCS od CA Microsoft
* Certifikáty SCEP od CA Microsoft
* Certifikáty PKCS od CA Symantec

Pokud chcete používat Intune Certificate Connector pro CA Microsoft a CA Symantec, musíte nejprve provést konfiguraci nástroje Intune Certificate Connector pro CA Microsoft a potom podle těchto kroků nástroj nakonfigurovat pro CA Symantec.  Další podrobnosti o konfiguraci nástroje Intune Certificate Connector pro certifikační autoritu Microsoft najdete v tématu [Konfigurace certifikátů v Microsoft Intune](certificates-configure.md).

## <a name="prepare-to-install-intune-certificate-connector"></a>Příprava k instalaci nástroje Intune Certificate Connector

Pokud už používáte Intune Certificate Connector pro stávající CA Microsoft a chcete přidat podporu CA Symantec, přeskočte tento krok pokračujte zbývajícími kroky po instalaci nejnovějšího nástroje Intune Certificate Connector z portálu pro správu Intune. Tento krok je nutný jenom v případě, že chcete používat Intune Certificate Connector pro samostatnou certifikační autoritu Symantec.

1. Zvolte jednu z verzí operačního systému Windows z následujícího seznamu a nainstalujte ho do počítače:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Vytvořte uživatele s oprávněními správce a použijte ho k dokončení následujících kroků.

3. Doplňte nejnovější aktualizace Windows a nainstalujte je, pokud jsou k dispozici.

   > [!IMPORTANT]
   > Po instalaci aktualizací Windows restartujte počítač.

4. Instalace .NET Framework 3.5:

    a. Otevřete **Ovládací panely** > **Programy a funkce** > **Zapnout nebo vypnout funkce systému Windows**.

    b. Vyberte možnost **.NET Framework 3.5** a rozhraní nainstalujte.

## <a name="install-the-symantec-registration-authorization-certificate"></a>Instalace certifikátu RA Symantec

Následující postup použijte k získání certifikátu RA od certifikační autority Symantec. K získání certifikátu RA musíte mít aktivní předplatné certifikační autority Symantec.

1. Uložte následující fragment kódu jako soubor s názvem **certreq.ini** a doplňte podle potřeby (například: *Název subjektu ve formátu CN*).

   ```
    [Version] 
    Signature="$Windows NT$" 

    [NewRequest] 
    ;Change to your,country code, company name and common name 
    Subject = "Subject Name in CN format"

    KeySpec = 1 
    KeyLength = 2048 
    Exportable = TRUE 
    MachineKeySet = TRUE 
    SMIME = False 
    PrivateKeyArchive = FALSE 
    UserProtected = FALSE 
    UseExistingKeySet = FALSE 
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
    ProviderType = 12 
    RequestType = PKCS10 
    KeyUsage = 0xa0 

    [EnhancedKeyUsageExtension] 
    OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication

    ;----------------------------------------------- 
   ```

2. Otevřete příkazový řádek se zvýšenými oprávněními a pomocí následujícího příkazu vygenerujte obsah CSR:

   `Certreq.exe -new certreq.ini request.csr`

3. Otevřete soubor request.csr v programu Poznámkový blok a zkopírujte jeho obsah CSR, který má následující formát:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Přihlaste se k certifikační autoritě Symantec a v úkolech přejděte do části **Get an RA Cert** (Získat certifikát RA).

   a. Zadejte obsah CSR z kroku 3 do určeného textového pole.

   b. Zadejte název certifikátu do určeného textového pole.

   c. Klikněte na **Continue** (Pokračovat).

      Zobrazí se odkaz ke stažení certifikátu RA.

   d. Stáhněte certifikát RA do místního počítače.

5. Importujte certifikát RA do úložiště certifikátů Windows:

    a. Otevřete konzolu MMC.

    b. Klikněte na příkaz **Soubor** > **Přidat nebo odebrat moduly snap-in** > **Certifikáty** a potom klikněte na možnost **Přidat**.

    c. Vyberte položku **Účet počítače** a pak klikněte na tlačítko **Další**.

    d. Vyberte položku **Místní počítač** a pak klikněte na tlačítko **Dokončit**.

    e. V okně **Přidat nebo odebrat moduly snap-in** klikněte na tlačítko **OK**. Rozbalte položku **Certifikáty (místní počítač)** > **Osobní** > **Certifikáty**.

    f. Klikněte pravým tlačítkem myši na uzel **Certifikáty** a vyberte možnost **Všechny úkoly** > **Importovat**.

    g. Vyberte umístění certifikátu RA, který jste si stáhli z CA Symantec, a klikněte na tlačítko **Další**.

    h. Vyberte **Osobní úložiště certifikátů** a pak klikněte na tlačítko **Další**.

    i. Klikněte na tlačítko **Dokončit**. Tím certifikát RA naimportujete do osobního úložiště místního počítače společně s jeho privátním klíčem.  

6. Export a import certifikátu privátního klíče:

    a. Rozbalte položku **Certifikáty (místní počítač)** > **Osobní** > **Certifikáty**.

    b. Vyberte certifikát naimportovaný v předchozím kroku.

    c. Klikněte pravým tlačítkem na certifikát a zvolte **Všechny úkoly** > **Exportovat**.

    d. Klikněte na tlačítko **Další** a zadejte heslo.

    e. Vyberte umístění pro export a klikněte na tlačítko **Dokončit**.

    f. Postupujte stejným způsobem jako v kroku 5 a naimportujte certifikát privátního klíče do osobního úložiště místního počítače.

7. Zkopírujte kryptografický otisk certifikátu RA bez mezer.  Následuje příklad kryptografického otisku:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Pokud při získávání certifikátu RA z certifikační autority Symantec nastanou problémy, obraťte se na oddělení podpory zákazníků Symantec.

## <a name="install-intune-certificate-connector"></a>Instalace nástroje Intune Certificate Connector

Pokud už používáte nejnovější nástroj Intune Certificate Connector pro stávající CA Microsoft a chcete přidat podporu CA Symantec, tento krok přeskočte. Jinak stáhněte nejnovější Intune Certificate Connector z portálu pro správu Intune a postupujte podle následujících pokynů.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
4. V podokně **Konfigurace zařízení** vyberte **Certifikační autorita**.
5. Klikněte na **Přidat** a vyberte **Stáhnout soubor konektoru**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který ho budete instalovat. 
3. Soubor NDESConnectorSetup.exe spusťte se zvýšenými oprávněními.

    a. Na obrazovce **Možnosti instalace** vyberte možnost **Distribuce PFX**, jak je znázorněno na následujícím snímku obrazovky.  Zbytek instalace dokončete s výchozími nastaveními.

   > [!IMPORTANT]
   > Pokud chcete nakonfigurovat Intune Certificate Connector k vystavování certifikátů z CA Microsoft a CA Symantec, vyberte možnost **Distribuce profilů SCEP a PFX**. Zbytek instalace dokončete s výchozími nastaveními.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>Konfigurace nástroje Intune Certificate Connector

Intune Certificate Connector se ve výchozím nastavení nainstaluje do `%ProgramFiles%\Microsoft Intune`.

1. Otevřete soubor %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config v programu Poznámkový blok.

    a. Aktualizujte hodnotu klíče RACertThumbprint hodnotou kryptografického otisku certifikátu, kterou jste zkopírovali v předchozím oddílu.  Například:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Uložte a zavřete soubor.

2. Otevřete soubor services.msc.

    a. Vyberte službu **Intune Connector Service**.

    b. Zastavte službu a pak ji zase spusťte.

    c. Zavřete okno Služby.

## <a name="setup-the-intune-administrator-account"></a>Nastavení účtu správce Intune

Pokud už používáte nástroj Intune Certificate Connector pro stávající CA Microsoft a chcete přidat podporu CA Symantec, přeskočte tento krok a pokračujte zbývajícími kroky. 

1. Spuštění uživatelského rozhraní nástroje NDES Connector z umístění ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `

    a. Klikněte na kartu **Zápis** a pak na možnost **Přihlásit se**.

    b. Zadejte přihlašovací údaje správce tenanta Intune do určených textových polí.

    c. Klikněte na **Přihlásit se**.  Zobrazí se potvrzovací dialogové okno se zprávou **Registrace byla úspěšná**, jak je znázorněno na následujícím snímku obrazovky.
2. Zavřete uživatelské rozhraní nástroje NDES Connector.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

Certifikáty PKCS nasazené pro zařízení spravovaná pomocí Intune musí být zřetězené s důvěryhodným kořenovým certifikátem. Proto musíte vytvořit profil důvěryhodného certifikátu Intune s důvěryhodným kořenovým certifikátem získaným od certifikační autority Symantec.

1. Získání důvěryhodného kořenového certifikátu od CA Symantec:

    a. Přihlaste se k portálu správce CA Symantec.

    b. V části Tasks (Úkoly) klikněte na možnost Manage CAs (Spravovat certifikační autority):

    c. Vyberte příslušnou certifikační autoritu ze seznamu certifikačních autorit.

    d. Kliknutím na možnost Download root certificate (Stáhnout kořenový certifikát) stáhněte důvěryhodný kořenový certifikát.

2. Vytvoření profilu důvěryhodného certifikátu na portálu pro správu Intune:

    a. Přihlaste se k [Azure Portal](https://portal.azure.com) pomocí přihlašovacích údajů správce tenanta Intune a vyhledejte prostředky Intune.

    b. Vytvořte profil důvěryhodného certifikátu v části **Microsoft Intune** > **Konfigurace zařízení** > **Profily**  >  **Vytvořit profil**.

    c. Zadejte požadované informace do polí **Název** a **Popis** a potom vyberte cílovou platformu. 

    d. V rozevíracím seznamu Typ profilu zvolte profil důvěryhodného certifikátu.

    e. Nahrajte důvěryhodný kořenový certifikát, který jste získali od CA Symantec v předchozím kroku.

    f. Dokončete zbývající kroky k vytvoření profilu. 

    g. Klikněte na **Přiřazení** a vyberte příslušnou skupinu.  Aspoň jeden uživatel nebo zařízení musí být součástí přiřazené skupiny.

## <a name="get-the-certificate-profile-oid"></a>Získání identifikátoru objektu profilu certifikátu

Identifikátor objektu profilu certifikátu je přidružený k šabloně profilu certifikátu v certifikační autoritě Symantec.  Pokud chcete vytvořit profil certifikátu PKCS na portálu pro správu Intune, je třeba zadat název šablony certifikátu ve formě identifikátoru objektu profilu certifikátu, který je přidružený k šabloně certifikátu v CA Symantec.

1. Přihlaste se k portálu správce CA Symantec.
2. Klikněte na možnost Manage Certificate Profiles (Spravovat profily certifikátů).
3. Vyberte profil certifikátu, který chcete použít.
4. Zkopírujte identifikátor objektu profilu certifikátu. Vypadá podobně jako v následujícím příkladu:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Pokud nastanou problémy se získáním identifikátoru objektu profilu certifikátu, obraťte se na zákaznickou podporu Symantec.

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Přihlaste se k portálu [Azure Portal](https://portal.azure.com) pomocí přihlašovacích údajů správce tenanta Intune a vyhledejte prostředky Intune.
2. Vytvořte profil certifikátu PKCS v části **Microsoft Intune** > **Konfigurace zařízení > Profily** > **Vytvořit profil**.

    a. Zadejte požadované informace do pole **Název** a **Popis** a potom vyberte cílovou platformu.

    b. V rozevíracím seznamu **Typ profilu** zvolte **Profil certifikátu PKCS**.  

    c. Dokončete zbývající kroky k vytvoření profilu.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > Následující parametry profilu certifikátu PKCS musí být nakonfigurované podle hodnot zadaných v následující tabulce, jak je znázorněno na snímku obrazovky k vydávání certifikátů PKCS prostřednictvím nástroje Intune Certificate Connector z CA Symantec. 

    |Parametr certifikátu PKCS | Hodnota | Popis |
    | --- | --- | --- |
    | Certifikační autorita | pki-ws.symauth.com | Tato hodnota musí být základní plně kvalifikovaný název domény služby CA Symantec bez koncových lomítek.  Pokud si nejste jistí, jestli máte pro svoje předplatné CA Symantec správný základní plně kvalifikovaný název domény služby, obraťte se na oddělení podpory zákazníků Symantec. <br><br> Pokud je tento plně kvalifikovaný název domény nesprávný, nevydá Intune Certificate Connector certifikáty PKCS z certifikační autority Symantec.| 
    | Název certifikační autority | Symantec | Tato hodnota musí být řetězec **Symantec**. <br><br> Pokud se tato hodnota jakkoli změní, nevydá Intune Certificate Connector certifikáty PKCS z certifikační autority Symantec.|
    | Název šablony certifikátu | Identifikátor objektu profilu certifikátu z certifikační autority Symantec <br><br> Například: `2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Tato hodnota musí být identifikátor objektu profilu certifikátu získaný v předchozím oddílu ze šablony profilu certifikátu CA Symantec. <br><br> Pokud nemůže Intune Certificate Connector najít šablonu certifikátu přidruženou k tomuto identifikátoru objektu profilu certifikátu v certifikační autoritě Symantec, nevydá PKCS certifikáty z CA Symantec.|

   > [!NOTE]
   > Profily certifikátů PKCS na platformách Windows nemusí být přidružené k profilu důvěryhodného certifikátu. V jiných systémech než Windows, jako je například Android, je však nutný.

3. Klikněte na **Přiřazení** a vyberte příslušnou skupinu.  Aspoň jeden uživatel nebo zařízení musí být součástí přiřazené skupiny.
 
Po dokončení předchozích kroků vydá Intune Certificate Connector certifikáty PKCS z CA Symantec do zařízení spravovaných pomocí Intune v přiřazené skupině. Tyto certifikáty budou k dispozici v osobním úložišti úložiště certifikátů aktuálního uživatele na zařízení spravovaném pomocí Intune.

### <a name="pkcs-certificate-profile-supported-attributes"></a>Podporované atributy profilu certifikátu PKCS

|Atribut | Formáty podporované Intune | Formáty podporované certifikační autoritou Symantec Cloud | Výsledek |
| --- | --- | --- | --- |
| Název subjektu |Intune podporuje název subjektu pouze ve třech následujících formátech: <br><br> 1. Běžný název <br> 2. Běžný název obsahující e-mail <br> 3. Běžný název jako e-mail <br><br> Například: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | CA Symantec podporuje další atributy.  Pokud chcete vybrat další atributy, musí být definované s pevnými hodnotami v šabloně profilu certifikátu Symantec.| Používá se běžný název nebo e-mail z žádosti o certifikát PKCS. <br><br> Jakákoli neshoda ve výběru atributů mezi profilem certifikátu Intune a šablonou profilu certifikátu Symantec bude znamenat, že CA Symantec nevydá žádné certifikáty.|
| Alternativní název subjektu | Intune podporuje pouze následující hodnoty polí alternativního názvu subjektu: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (šifrovaná hodnota) | Certifikační autorita Symantec Cloud také podporuje tyto parametry. Pokud chcete vybrat další atributy, musí být definované s pevnými hodnotami v šabloně profilu certifikátu Symantec. <br><br> AltNameTypeEmail: Pokud nelze tento typ nalézt v alternativním názvu subjektu, použije se hodnota z AltNameTypeUpn.  Pokud nelze v alternativním názvu subjektu nalézt ani AltNameTypeUpn, použije se hodnota z názvu subjektu, pokud má formát e-mailu.  Jestliže ani poté nelze název subjektu nalézt, nepodaří se nástroji Intune Certificate Connector vydat certifikáty. <br><br> Například: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: Pokud nelze tento typ nalézt v alternativním názvu subjektu, použije se hodnota z AltNameTypeEmail. Pokud nelze v alternativním názvu subjektu nalézt ani AltNameTypeEmail, použije se hodnota z názvu subjektu, pokud má formát e-mailu.  Jestliže ani poté nelze název subjektu nalézt, nepodaří se nástroji Intune Certificate Connector vydat certifikáty.  <br><br> Například: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: Pokud nelze tento typ nalézt v alternativním názvu subjektu, nepodaří se nástroji Intune Certificate Connector vydat certifikáty. <br><br> Například: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Důležité upozornění:** CA Symantec podporuje hodnotu tohoto pole pouze v zakódovaném formátu (šestnáctková hodnota). Jakoukoli hodnotu v tomto poli převede nástroj Intune Certificate Connector před odesláním žádosti o certifikát do kódování Base 64. **Intune Certificate Connector neověřuje, jestli už je hodnota zakódovaná.** | Žádné |

## <a name="troubleshooting"></a>Odstraňování potíží

Protokoly služby Intune Certificate Connector jsou k dispozici ve složce `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` v počítači NDES Connector. Otevřete protokoly v nástroji [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) a vyhledejte výjimky nebo chybové zprávy.

| Problém nebo chybová zpráva | Kroky řešení |
| --- | --- |
| Nelze se přihlásit do uživatelského rozhraní NDES Connector pomocí účtu správce tenanta Intune. | Může se to stát v případě, že místní Certificate Connector není povolený v portálu pro správu Intune. Tento problém vyřešíte následujícím postupem: <br><br> Z uživatelského rozhraní Silverlight: <br> 1. Přihlaste se k [portálu pro správu Intune](https://admin.manage.microsoft.com). <br> 2. Klikněte na možnost Správce. <br> 3. Vyberte položku Správa mobilních zařízení > Certificate Connector <br> 4. Klikněte na možnost **Konfigurace místního Certificate Connectoru**. <br> 5. Zaškrtněte políčko **Zapnout Certificate Connector**. <br> 6. Klikněte na **OK**. <br><br>nebo <br><br> Z uživatelského rozhraní Azure: <br> 1. Přihlaste se k portálu [Azure Portal](https://portal.azure.com). <br> 2. Přejděte do Microsoft Intune. <br> 3. Vyberte možnost **Konfigurace zařízení** > **Certifikační autorita**. <br> 4. Klikněte na **Povolit**. <br><br> Po dokončení předchozích kroků z rozhraní Silverlight nebo portálu Azure Portal se zkuste přihlásit pomocí stejného účtu správce tenanta Intune do uživatelského rozhraní NDES Connector. |
| Certifikát konektoru NDES Connector se nepodařilo nalézt. <br><br> System.ArgumentNullException: Hodnota nemůže být null. | Intune Certificate Connector zobrazuje tuto chybu, pokud se účet správce tenanta Intune nikdy nepřihlásil k uživatelskému rozhraní NDES Connector. <br><br> Pokud s tím budou dál problémy, restartujte Intune Service Connector. <br><br> 1. Otevřete konzolu services.msc. <br> 2. Vyberte službu **Intune Connector Service**. <br> 3. Klikněte pravým tlačítkem a vyberte možnost **Restartovat**.|
| NDES Connector – IssuePfx – obecná výjimka: <br> System.NullReferenceException: Odkaz na objekt není nastavený na instanci objektu. | Tato chyba je přechodná. Restartujte službu Intune Connector Service. <br><br> 1. Otevřete konzolu services.msc. <br> 2. Vyberte službu **Intune Connector Service**. <br> 3. Klikněte pravým tlačítkem a vyberte možnost **Restartovat**. |
| Poskytovatel Symantec – nepodařilo se získat zásady Symantec pro časový limit operace. | Intune Certificate Connector přijal při komunikaci s certifikační autoritou Symantec chybu časového limitu operace. Pokud tato chyba přetrvává, zvyšte hodnotu časového limitu připojení a zkuste to znovu. <br><br> Postup zvýšení časového limitu připojení: <br> 1. Přejděte do počítače konektoru NDES Connector. <br>2. Otevřete soubor `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` v aplikaci Poznámkový blok. <br> 3. Zvyšte časový limit u následujícího parametru: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Restartujte službu Intune Connector Service. <br><br> Pokud potíže potrvají, obraťte se na zákaznickou podporu Symantec. |
| Poskytovatel Symantec – nepodařilo se získat certifikát klienta. | V nástroji Intune Certificate Connector se nepodařilo načíst certifikát RA z osobního úložiště certifikátů místního počítače. Pokud chcete vyřešit tento problém, ujistěte se, že jste nainstalovali certifikát RA v osobním úložišti certifikátů místního počítače společně s jeho privátním klíčem. <br><br> **Poznámka:** Certifikát RA je třeba získat z CA Symantec. Další podrobnosti získáte na zákaznické podpoře Symantec. | 
| Poskytovatel Symantec – nepodařilo se získat zásady Symantec pro přerušení žádosti z důvodu nevytvoření zprostředkovatele Schannel SSL/TLS. | K této chybě dochází v následujících případech: <br><br> 1. Služba Intune Certificate Connector nemá dostatečná oprávnění k načtení certifikátu RA spolu s jeho privátním klíčem z osobního úložiště certifikátů v místním počítači. Pokud chcete vyřešit tento problém, zkontrolujte kontext účtu, pod kterým běží v konzole services.msc služba konektoru. Služba konektoru musí běžet v kontextu NT AUTHORITY\SYSTEM. <br><br> 2. Profil certifikátu PKCS na portálu pro správu Intune může být nakonfigurovaný s neplatným plně kvalifikovaným názvem domény základní služby CA Symantec. Plně kvalifikovaný název domény je podobný názvu `pki-ws.symauth.com`. Pokud chcete vyřešit tento problém, ověřte na zákaznické podpoře Symantec správnost adresy URL pro vaše předplatné. <br><br> 3. V nástroji Intune Certificate Connector se nedaří dokončit ověření s CA Symantec pomocí certifikátu RA, protože nelze načíst jeho privátní klíč. Pokud chcete vyřešit tento problém, ujistěte se, že jste nainstalovali certifikát RA v osobním úložišti certifikátů místního počítače společně s jeho privátním klíčem. <br><br> Pokud potíže potrvají, obraťte se na zákaznickou podporu Symantec. |
| Poskytovatel Symantec – nepodařilo se získat zásady Symantec pro nesrozumitelný prvek žádosti. | V nástroji Intune Certificate Connector se nepodařilo získat šablonu profilu certifikátu Symantec, protože identifikátor objektu profilu klienta neodpovídá profilu certifikátu Intune. Další možnost je, že nástroj Intune Certificate Connector nemůže najít šablonu profilu certifikátu přidruženou k danému identifikátoru objektu profilu klienta v CA Symantec. <br><br> Pokud chcete vyřešit tento problém, získejte správný identifikátor objektu profilu klienta z šablony certifikátu Symantec v CA Symantec. Potom aktualizujte profil certifikátu PKCS na portálu pro správu Intune. <br><br> Získání identifikátoru objektu profilu klienta z certifikační autority Symantec: <br> 1. Přihlaste se k portálu správce CA Symantec. <br> 2. Klikněte na možnost Manage Certificate Profiles (Spravovat profily certifikátů). <br> 3. Vyberte profil certifikátu, který chcete použít. <br> 4. Získejte identifikátor objektu profilu certifikátu. Vypadá podobně jako v následujícím příkladu: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Aktualizace profilu certifikátu PKCS pomocí správného identifikátoru objektu profilu certifikátu: <br>1. Přihlaste se k portálu pro správu Intune. <br> 2. Přejděte na profil certifikátu PKCS a klikněte na **Upravit**. <br> 3. Aktualizujte identifikátor objektu profilu certifikátu v poli Název šablony certifikátu. <br> 4. Uložte profil certifikátu PKCS. |
| Poskytovatel Symantec – ověření zásad se nezdařilo. <br><br> Atribut nespadá do seznamu atributů šablony certifikátů podporovaných společností Symantec. | Certifikační autorita Symantec zobrazuje tuto zprávu, když dojde k neshodě mezi šablonou profilu certifikátu Symantec a profilem certifikátu Intune. Tento problém pravděpodobně nastal v důsledku neshody atributů v polích SubjectName nebo SubjectAltName. <br><br> Pokud chcete tento problém vyřešit, je nutné vybrat atributy, které Intune podporuje v polích SubjectName a SubjectAltName v dané šabloně profilu certifikátu Symantec. Další informace najdete v tématu Atributy podporované v Intune v oddílu parametrů certifikátu. |
| Některá zařízení uživatelů nedostávají certifikáty PKCS z certifikační autority Symantec. | Tento problém nastane, když hlavní název uživatele (UPN) obsahuje speciální znaky, jako je podtržítko (například `global_admin@intune.onmicrosoft.com`). <br><br> CA Symantec nepodporuje speciální znaky v polích mail_firstname a mail_lastname. <br><br> Tento problém vyřešíte následujícím postupem: <br><br> 1.   Přihlaste se k portálu správce CA Symantec. <br> 2. Přejděte na Manage Certificate Profiles (Spravovat profily certifikátů). <br> 3.   Klikněte na profil certifikátu použitý pro Intune. <br> 4.  Klikněte na odkaz Customize options (Upravit možnosti). <br> 5.   Klikněte na tlačítko Advanced options (Upřesnit). <br> 6.  V části polí certifikátu pro rozlišující název subjektu přidejte pole Běžný název (CN) a odstraňte existující pole Běžný název (CN). Přidání a odstranění je nutné provést najednou. <br> 7.    Klikněte na Uložit. <br><br> Na základě předchozí změny vyžádá profil certifikátu Symantec název CN=<upn> namísto mail_firstname a mail_lastname. |
| Uživatel ručně odstranil již nasazený certifikát ze zařízení. | Intune znovu nasadí stejný certifikát při dalším ohlášení nebo vynucení zásad. V takovém případě NDES Connector neobdrží žádost o certifikát PKCS. |

## <a name="next-steps"></a>Další kroky

- Informace uvedené v tomto článku využijte spolu s informacemi v tématu [Co jsou profily zařízení Microsoft Intune?](device-profiles.md) ke správě zařízení organizace a jejich certifikátů.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Instalace nástroje Intune Certificate Connector a výběr distribuce PFX"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Konfigurace nástroje Intune Certificate Connector"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "Vytvoření profilu certifikátu PKCS na portálu Azure Portal"
