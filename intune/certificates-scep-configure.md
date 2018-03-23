---
title: Konfigurace a správa certifikátů SCEP pomocí Microsoft Intune
description: Přečtěte si, jak v Microsoft Intune konfigurovat infrastrukturu a pak vytvořit a přiřadit profily certifikátů Intune SCEP (Simple Certificate Enrollment Protocol).
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88109f1dc4543a5c71f36378fddb110c03afa08f
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="configure-and-manage-scep-certificates-with-microsoft-intune"></a>Konfigurace a správa certifikátů SCEP pomocí Microsoft Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje, jak pomocí Intune konfigurovat infrastrukturu a pak vytvořit a přiřadit profily certifikátů SCEP (Simple Certificate Enrollment Protocol).

## <a name="configure-on-premises-infrastructure"></a>Konfigurace místní infrastruktury

-    **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

-  **Certifikační autorita** (CA): Označuje se jako vydávající certifikační autorita. Musíte mít certifikační autoritu organizace, která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novějšího. Samostatná certifikační autorita není podporovaná. Podrobnosti najdete v tématu [Instalace certifikační autority](http://technet.microsoft.com/library/jj125375.aspx).
    Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Server NDES**: Na serveru, na kterém běží Windows Server 2012 R2 nebo novější, musíte nastavit službu zápisu síťových zařízení (NDES). Intune nepodporuje používání služby zápisu síťových zařízení, pokud běží na serveru, na kterém běží taky certifikační autorita organizace. Pokyny k tomu, jak konfigurovat Windows Server 2012 R2 k hostování služby zápisu síťových zařízení, najdete v tématu [Doprovodné materiály ke službě zápisu síťových zařízení](http://technet.microsoft.com/library/hh831498.aspx).
Server NDES musí být připojený k doméně, která je hostitelem certifikační autority, a nesmí být na stejném serveru jako tato autorita. Další informace o nasazení serveru NDES v samostatné doménové struktuře, izolované síti nebo interní doméně najdete v tématu [Použití modulu zásad se Službou zápisu síťových zařízení](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune Certificate Connector**: Prostřednictvím Azure Portalu stáhněte instalační program **Certificate Connectoru** (**ndesconnectorssetup.exe**). Pak můžete soubor **ndesconnectorssetup.exe** spustit na serveru hostujícím roli Služba zápisu síťových zařízení (NDES), na který chcete Certificate Connector nainstalovat. 
-  **Proxy server webových aplikací** (volitelné): Jako server služby Proxy webových aplikací (WAP) použijte server se systémem Windows Server 2012 R2 nebo novějším. Tato konfigurace:
    -  Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
    -  Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.

 > [!NOTE]           
> -    Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení. Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](http://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Server hostující službu WAP musí mít také certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.
    Informace o certifikátech pro službu WAP najdete v části **Plánování certifikátů** tématu [Plánování publikování aplikací pomocí serveru proxy webových aplikací](https://technet.microsoft.com/library/dn383650.aspx). Obecné informace o serverech WAP najdete v tématu [Práce se serverem proxy webových aplikací](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Požadavky sítě

Z internetu do hraniční sítě povolte port 443 ze všech hostitelů nebo IP adres na internetu k serveru NDES.

Z hraniční sítě do důvěryhodné sítě povolte všechny porty a protokoly nutné pro doménový přístup k serveru NDES připojenému k doméně. Server NDES potřebuje přístup k serverům certifikátů, serverům DNS, serverům nástroje Configuration Manager a řadičům domény.

Doporučujeme publikování serveru NDES prostřednictvím proxy serveru, jako je například [Azure AD Application Proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) nebo proxy server jiného výrobce.


### <a name="certificates-and-templates"></a>Certifikáty a šablony

|Objekt|Podrobnosti|
|----------|-----------|
|**Šablona certifikátu**|Tuto šablonu nakonfigurujte na své vydávající certifikační autoritě.|
|**Certifikát pro ověřování klientů**|Tento certifikát vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte na server NDES.|
|**Ověřovací certifikát serverů**|Tento certifikát SSL vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte a připojte ve službě IIS na serveru NDES.|
|**Certifikát důvěryhodné kořenové certifikační autority**|Tento certifikát exportujete jako soubor **.cer** z kořenové certifikační autority nebo jakéhokoli zařízení, které důvěřuje kořenové certifikační autoritě, a přiřadíte ho k zařízením pomocí profilu certifikátu důvěryhodné certifikační autority.<br /><br />Použijete jeden certifikát důvěryhodné kořenové certifikační autority na každou platformu operačního systému a přidružíte ho ke každému profilu důvěryhodného kořenového certifikátu, který vytvoříte.<br /><br />Pokud potřebujete, můžete vytvořit další certifikáty důvěryhodné kořenové certifikační autority. Můžete to třeba udělat, abyste vytvořili vztah důvěryhodnosti k certifikační autoritě, která podepisuje ověřovací certifikáty serverů pro vaše přístupové body Wi-Fi.|

### <a name="accounts"></a>Účty

|Název|Podrobnosti|
|--------|-----------|
|**Účet služby NDES**|Zadejte účet uživatele domény, který chcete použít jako účet služby NDES.|

## <a name="configure-your-infrastructure"></a>Konfigurace infrastruktury
Před konfigurací profilů certifikátů musíte provést následující úlohy, které vyžadují znalosti systému Windows Server 2012 R2 a služby AD CD (Active Directory Certificate Services):

**Krok 1**: Vytvoření účtu služby NDES

**Krok 2**: Konfigurace šablon certifikátů v certifikační autoritě

**Krok 3**: Konfigurace požadavků na serveru NDES

**Krok 4**: Konfigurace NDES pro použití s Intune

**Krok 5**: Povolení, instalace a konfigurace Intune Certificate Connectoru

#### <a name="step-1---create-an-ndes-service-account"></a>Krok 1: Vytvoření účtu služby NDES

Vytvořte účet uživatele domény, který chcete použít jako účet služby NDES. Tento účet zadáte při konfiguraci šablon ve vydávající certifikační autoritě před instalací a konfigurací NDES. Ověřte, že uživatel má výchozí práva **Povolit místní přihlášení**, **Přihlásit jako službu** a **Přihlásit jako dávkovou úlohu**. Některé organizace mají zásady posílení zabezpečení, které tato práva zakazují.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2: Konfigurace šablon certifikátů v certifikační autoritě
V této úloze:

-   Konfigurujete šablonu certifikátu pro NDES

-   Publikujete šablonu certifikátu pro NDES

##### <a name="to-configure-the-certification-authority"></a>Konfigurace certifikační autority

1.  Přihlaste se jako správce podnikové sítě.

2.  Ve vydávající certifikační autoritě použijte modul snap-in Šablony certifikátů k vytvoření nové vlastní šablony nebo zkopírování existující šablony a následnému upravení existující šablony (jako je šablona Uživatel) pro použití s NDES.

    >[!NOTE]
    > Šablona certifikátu NDES musí být založena na modulu snap-in Šablony certifikátů verze 2 (kvůli kompatibilitě s Windows 2003).

    Šablona musí obsahovat následující konfigurace:

    -   Zadejte popisný **zobrazovaný název šablony** .

    -   Na kartě **Název subjektu** vyberte možnost **Dodán v žádosti**. (Zabezpečení je vynucené modulem zásad Intune pro NDES).

    -   Na kartě **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

        > [!IMPORTANT]
        > V případě šablon certifikátů pro iOS a macOS na kartě **Rozšíření** upravte **použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu**.

    -   Na kartě **Zabezpečení** přidejte účet služby NDES a poskytněte šabloně oprávnění k **zápisu**. Správci služby Intune, kteří vytvoří profily SCEP, vyžadují práva pro **čtení**, aby při vytváření profilů SCEP mohli procházet šablony.

    > [!NOTE]
    > K odvolání certifikátů vyžaduje účet služby NDES oprávnění *Vydávat a spravovat certifikáty* ke každé šabloně certifikátu používané profilem certifikátu.

3.  Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Máte ale možnost konfigurovat, aby certifikační autorita žadateli umožňovala určit jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

    > [!IMPORTANT]
    > iOS a macOS vždy používá hodnotu nastavenou v šabloně bez ohledu na ostatní konfigurace, které provedete.

Tady jsou snímky obrazovky ukázkové konfigurace šablony.

![Šablona, karta Vyřízení žádosti](.\media\scep_ndes_request_handling.png)

![Šablona, karta Název subjektu](.\media\scep_ndes_subject_name.jpg)

![Šablona, karta Zabezpečení](.\media\scep_ndes_security.jpg)

![Šablona, karta Rozšíření](.\media\scep_ndes_extensions.jpg)

![Šablona, karta Požadavky na vystavování](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Do pole Zásady použití přidejte jenom požadované zásady použití. Správnost zadaných voleb zkontrolujte se správci zabezpečení.



Pokud chcete certifikační autoritu konfigurovat, aby žadateli umožňovala určit dobu platnosti:

1. V certifikační autoritě spusťte tyto příkazy:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Ve vydávající certifikační autoritě použijte modul snap-in Certifikační autorita k publikování šablony certifikátu.
    Vyberte uzel **Šablony certifikátů**, klikněte na **Akce**-&gt; **Nové** &gt; **Vystavovaná šablona certifikátu** a potom vyberte šablonu, kterou jste vytvořili v kroku 2.
3. Ověřte, že je šablona publikovaná, jejím zobrazením ve složce **Šablony certifikátů** .


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Krok 3: Konfigurace požadavků na serveru NDES
V této úloze:

-   Přidáte NDES do Windows Serveru a konfigurujete službu IIS pro podporu NDES

-   Přidáte účet služby NDES do skupiny IIS_IUSR

-   Nastavíte hlavní název služby (SPN) pro účet služby NDES




   1.  Na serveru, který je hostitelem NDES, se přihlaste jako **Správce podnikové sítě** a pak pomocí [Průvodce přidáním rolí a funkcí](https://technet.microsoft.com/library/hh831809.aspx) instalujte NDES:

    1.  V průvodci vyberte možnost **Služba AD CS (Active Directory Certificate Services)** , abyste získali přístup ke službám rolí ve službě AD CS. Vyberte **Službu zápisu síťových zařízení**, zrušte zaškrtnutí políčka **Certifikační autorita**a pak dokončete průvodce.

        > [!TIP]
        > Na stránce průvodce **Průběh instalace** neklikejte na **Zavřít**. Místo toho klikněte na odkaz **Konfigurovat službu AD CS (Active Directory Certificate Services) na cílovém serveru**. Tím se otevře průvodce **Konfigurace služby AD CS** , který použijete pro další krok. Po otevření Konfigurace služby AD CS můžete zavřít Průvodce přidáním rolí a funkcí.

    2.  Když se na server přidá NDES, průvodce nainstaluje taky službu IIS. Ujistěte se, že má služba IIS následující konfigurace:

        -   **Webový server** &gt; **Zabezpečení** &gt; **Filtrování požadavků**

        -   **Webový server** &gt; **Vývoj aplikací** &gt; **ASP.NET 3.5**. Instalace technologie ASP.NET 3.5 nainstaluje rozhraní .NET Framework 3.5. Při instalaci rozhraní .NET Framework 3.5 nainstalujte základní **rozhraní .NET Framework 3.5** i **Aktivaci protokolem HTTP**.

        -   **Webový server** &gt; **Vývoj aplikací** &gt; **ASP.NET 4.5**. Instalace technologie ASP.NET 4.5 nainstaluje rozhraní .NET Framework 4.5. Při instalaci .NET Framework 4.5 nainstalujte základní rozhraní **.NET Framework 4.5**, **ASP.NET 4.5** a funkci **Služby WCF** &gt; **Aktivace protokolem HTTP**.

        -   **Nástroje pro správu** &gt; **Kompatibilita správy služby IIS 6** &gt; **Kompatibilita metabáze služby IIS 6**

        -   **Nástroje pro správu** &gt; **Kompatibilita správy služby IIS 6** &gt; **Kompatibilita metabáze služby IIS 6 WMI**

  2.  Na serveru přidejte účet služby NDES jako člena skupiny **IIS_IUSR**.

   3.  Na příkazovém řádku se zvýšenými oprávněními spusťte následující příkaz pro nastavení hlavního názvu služby (SPN) účtu služby NDES:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Například pokud je název serveru NDES **Server01**, vaše doména je **Contoso.com**a účet služby je **NDESService**, použijte:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4: Konfigurace NDES pro použití s Intune
V této úloze:

-   Nakonfigurujete NDES pro použití s vydávající certifikační autoritou

-   Vytvoříte vazbu certifikátu serveru ověřování (SSL) ve službě IIS

-   Konfigurujete filtrování požadavků ve službě IIS


1.  Na serveru NDES otevřete průvodce Konfigurace služby AD CS a pak proveďte následující konfigurace.

    > [!TIP]
    > Pokud jste klikli na odkaz v předchozí úloze, je už tento průvodce otevřený. Jinak spusťte Správce serveru, abyste získali přístup ke konfiguraci po nasazení pro službu AD CS (Active Directory Certificate Services).

    -   Na stránce **Služby rolí** vyberte **Služba zápisu síťových zařízení**.

    -   Na stránce **Účet Služby zápisu síťových zařízení** zadejte účet služby NDES.

    -   Na stránce **Certifikační autorita pro Službu zápisu síťových zařízení** klikněte na **Vybrat**a pak vyberte vydávající certifikační autoritu, kam jste nakonfigurovali šablonu certifikátu.

    -   Na stránce **Kryptografie pro Službu zápisu síťových zařízení** nastavte délku klíče podle požadavků vaší společnosti.

    Na stránce **Potvrzení** klikněte na **Konfigurovat** a dokončete průvodce.

2.  Po dokončení průvodce upravte následující klíč registru na serveru NDES:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Pokud tento klíč chcete upravit, identifikujte **Účel** šablony certifikátu, jak je uvedený na kartě **Vyřízení žádosti**, a potom upravte odpovídající položku v registru nahrazením stávajících dat názvem šablony certifikátu (ne zobrazovaným názvem šablony), který jste zadali v úloze 1. Následující tabulka mapuje účel šablony certifikátu na hodnoty v registru:

    |Účel šablony certifikátu (na kartě Vyřízení žádosti)|Upravovaná hodnota registru|Hodnota zobrazená v konzole pro správu Intune pro profil SCEP|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Podpis|SignatureTemplate|Digitální podpis|
    |Šifrování|EncryptionTemplate|Šifrování klíče|
    |Podpis a šifrování|GeneralPurposeTemplate|Šifrování klíče<br /><br />Digitální podpis|
    Pokud je třeba účelem šablony certifikátu **Šifrování**, pak upravte hodnotu **EncryptionTemplate** , aby byla názvem vaší šablony certifikátu.

3. Server NDES obdrží dvě dlouhé adresy URL (dotazy), které vyžadují, abyste přidali dvě položky registru:

    |Umístění|Hodnota|Typ|Data|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (desítkově)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (desítkově)|


4. V modulu Správce služby IIS manager zvolte **Výchozí web** -> **Filtrování požadavků** -> **Upravit nastavení funkcí** a změňte nastavení **Maximální délka adresy URL** a **Maximální délka řetězce dotazu** na *65534* (viz obrázek).

    ![Maximální délka dotazu a adresy URL ve službě IIS](.\media\SCEP_IIS_max_URL.png)

5.  Restartujte server. Spuštění **iisreset** na serveru k dokončení těchto změn nestačí.
6. Přejděte k souboru http://*plně_kvalifikovaný_název_domény*/certsrv/mscep/mscep.dll. Měla by se zobrazit stránka NDES podobná následující stránce:

    ![Test NDES](.\media\SCEP_NDES_URL.png)

    Pokud se zobrazí **503 - Služba není k dispozici** , zkontrolujte prohlížeč událostí. Je pravděpodobné, že se fond aplikací zastavil kvůli chybějícímu oprávnění pro uživatele NDES. Tato práva jsou popsaná v úloze 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Instalace a vytvoření vazby certifikátů na serveru NDES

1.  Na serveru NDES vyžádejte a nainstalujte **ověřovací certifikát serveru** z vaší interní nebo veřejné certifikační autority. Pro tento certifikát SSL pak vytvoříte vazbu ve službě IIS.

    > [!TIP]
    > Po vytvoření vazby certifikátu SSL ve službě IIS nainstalujte certifikát pro ověřování klientů. Tento certifikát může být vydaný certifikační autoritou, která je důvěryhodná pro server NDES. I když se nejedná o osvědčený postup, můžete použít stejný certifikát pro ověřování serverů i klientů, pokud má obě rozšířená použití klíče (EKU). Informace o těchto ověřovacích certifikátech najdete v následujících krocích.

    1.  Po obdržení ověřovacího certifikátu serverů otevřete **Správce služby IIS**, vyberte **Výchozí webový server** v podokně **Připojení** a pak klikněte na **Vazby** v podokně **Akce** .

    2.  Klikněte na **Přidat**, nastavte **Typ** na **https**a pak se ujistěte, že port je **443**. (Pro samostatnou službu Intune je podporovaný jenom port 443.

    3.  Jako **Certifikát SSL**zadejte ověřovací certifikát serverů.

        > [!NOTE]
        > Pokud server NDES používá externí i interní název pro jednu síťovou adresu, musí mít ověřovací certifikát serverů **Název subjektu** s názvem externího veřejného serveru a **Alternativní název subjektu** , který obsahuje název interního serveru.

2.  Na serveru NDES vyžádejte a nainstalujte certifikát pro **ověřování klientů** z vaší interní certifikační autority nebo z veřejné certifikační autority. Může to být stejný certifikát jako ověřovací certifikát serverů, pokud má tento certifikát obě schopnosti.

    Certifikát pro ověřování klientů musí mít následující vlastnosti:

    **Rozšířené použití klíče** – musí zahrnovat **Ověření klienta**.

    **Název subjektu** – musí být stejný jako název DNS serveru, na který instalujete certifikát (server NDES).

##### <a name="to-configure-iis-request-filtering"></a>Konfigurace filtrování požadavků služby IIS

1.  Na serveru NDES otevřete **Správce služby IIS**, vyberte **Výchozí webový server** v podokně **Připojení** a pak otevřete **Filtrování požadavků**.

2.  Klikněte na **Upravit nastavení funkce**a pak nastavte tyto hodnoty:

    **řetězec dotazu (bajty)** = **65534**

    **Maximální délka adresy URL (bajty)** = **65534**

3.  Zkontrolujte následující klíč registru:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Ujistěte se, že následující hodnoty jsou nastavené jako položky DWORD:

    Název: **MaxFieldLength**, s desetinnou hodnotou **65534**

    Název: **MaxRequestBytes**, s desetinnou hodnotou **65534**

4. Restartujte server NDES. Server je teď připravený na podporu konektoru Certificate Connector.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5: Povolení, instalace a konfigurace Intune Certificate Connectoru
V této úloze:

- Povolíte podporu NDES ve službě Intune.
- Stáhnete Certificate Connector a pak ho nainstalujete a nakonfigurujete na serveru, který je hostitelem role Služba zápisu síťových zařízení (NDES) ve vašem prostředí. Pokud chcete zvýšit škálovatelnost implementace NDES, můžete nainstalovat více serverů NDES s Microsoft Intune Certificate Connectorem.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace Certificate Connectoru
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
4. V podokně **Konfigurace zařízení** vyberte **Certifikační autorita**.
5. Klikněte na **Přidat** a vyberte **Stáhnout soubor konektoru**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který ho budete instalovat. 
6.  Po dokončení stahování spusťte stažený instalační program (**ndesconnectorssetup.exe**) na serveru, který je hostitelem role Služba zápisu síťových zařízení (NDES). Tento instalační program nainstaluje taky modul zásad pro NDES a webovou službu CRP. (Webová služba CRP, CertificateRegistrationSvc, běží ve službě ve službě IIS jako aplikace).

    > [!NOTE]
    > Při instalaci NDES pro samostatnou službu Intune se s konektorem Certificate Connector automaticky nainstaluje služba CRP. Při použití služby Intune se Správcem konfigurace nainstalujete bod registrace certifikátu (CRP) jako samostatnou roli serveru.

3.  Pokud se zobrazí výzva k zadání klientského certifikátu pro konektor Certificate Connector, klikněte na **Vybrat** a vyberte certifikát pro **ověřování klientů**, který jste nainstalovali na server NDES v úloze 3.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, kliknutím na **Další** zobrazte vlastnosti certifikátu. Pak klikněte na **Další**a pak klikněte na **Nainstalovat**.

4.  Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP]
    > Pokud průvodce zavřete před spuštěním uživatelského rozhraní konektoru Certificate Connector, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > **&lt;cesta_k_instalaci&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  V uživatelském rozhraní **Certificate Connectoru** :

    Klikněte na **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu.

    > [!IMPORTANT]
    > K uživatelskému účtu musí být přiřazená platná licence pro Intune. Pokud daný uživatelský účet nemá platnou licenci pro Intune, spuštění příkazu NDESConnectorUI.exe se nezdaří.

    Pokud vaše organizace používá proxy server a ten je vyžadovaný pro přístup serveru NDES k internetu, klikněte na **Použít proxy server** a potom zadejte název proxy serveru, port a přihlašovací údaje účtu pro připojení.

    Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **Vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě, a pak klikněte na **Použít**.

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

6.  Otevřete příkazový řádek, zadejte **services.msc** a potom stiskněte **Enter**, klikněte pravým tlačítkem na **Intune Certificate Connector** a nakonec klikněte na **Restartovat**.

Pokud chcete ověřit, jestli je služba spuštěná, spusťte prohlížeč a zadejte následující adresu URL, která by měla vrátit chybu **403** :

**http:// &lt;Název_FQDN_serveru_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1. Na portálu Azure Portal vyberte úlohu **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** vyberte **Spravovat** > **Profily**.
3. V podokně profilů zvolte **Vytvořit profil**.
4. V podokně **Vytvořit profil** zadejte **Název** a **Popis** profilu certifikátu SCEP.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento certifikát SCEP. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
    - **Androidemem**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Certifikát SCEP**.
7. V podokně **Certifikát SCEP** nakonfigurujte tato nastavení:
    - **Období platnosti certifikátu** – Pokud jste na vydávající CA spustili příkaz **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**, který umožňuje nastavit vlastní období platnosti, můžete zadat dobu zbývající do vypršení platnosti certifikátu.<br>Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vydávající CA. 
    - **Zprostředkovatel úložiště klíčů (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) – Určete, kam se má uložit klíč k certifikátu. Vyberte jednu z těchto hodnot:
        - **Zapsat do KSP na čipu TPM (Trusted Platform Module), pokud existuje, jinak zapsat do softwarového KSP**
        - **Zapsat do KSP na čipu TPM (Trusted Platform Module), jinak chyba**
        - **Zapsat do služby Passport, jinak chyba (Windows 10 a novější)**
        - **Zapsat do softwarového KSP**
    - **Formát názvu subjektu** – Ze seznamu vyberte způsob, jak má Intune automaticky vytvořit název subjektu v žádosti o certifikát. Pokud je certifikát určený pro uživatele, můžete do názvu subjektu zahrnout taky e-mailovou adresu uživatele. Vybírejte z těchto možností:
        - **Není nakonfigurováno**
        - **Běžný název**
        - **Běžný název včetně e-mailové adresy**
        - **Běžný název jako e-mail**
        - **IMEI (International Mobile Equipment Identity)**
        - **Sériové číslo**
        - **Vlastní** – když vyberete tuto možnost, zobrazí se další pole rozevíracího seznamu. V tomto poli můžete zadat vlastní formát názvu subjektu. Dvě proměnné, které jsou aktuálně podporované pro vlastní formát, jsou **Běžný název (CN)** a **E-mail (E)**. Pomocí kombinace jedné této proměnné nebo mnoha proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu jako například tento: **CN={{UserName}},E={{EmailAddress}},OU=Mobilni,O=Finance,L=Brno,C=CZ**. V tomto příkladu jste vytvořili formát názvu subjektu, který kromě proměnných CN a E využívá řetězce pro organizační jednotku, organizaci, umístění a zemi. V [tomto tématu](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) si můžete přečíst další informace o funkci **CertStrToName** a jejích podporovaných řetězcích.
        
    - **Alternativní název subjektu** – Určete způsob, jak má Intune automaticky vytvořit hodnoty pro alternativní název subjektu (SAN) v žádosti o certifikát. Pokud jste zvolili třeba uživatelský typ certifikátu, můžete do alternativního názvu subjektu zahrnout hlavní název uživatele (UPN). Pokud klientský certifikát slouží k ověřování na server NPS (Network Policy Server), musíte alternativní název subjektu nastavit na UPN. 
    - **Použití klíče** – Zadejte možnosti použití klíče pro certifikát. Vybírat můžete z těchto možností: 
        - **Šifrování klíče** – Umožňuje výměnu klíče jenom v případě, že je klíč zašifrovaný. 
        - **Digitální podpis** – Umožňuje výměnu klíče jenom v případě, že se k ochraně klíče využívá digitální podpis. 
    - **Velikost klíče (bity)** – Vyberte počet bitů, které klíč obsahuje. 
    - **Algoritmus hash** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) – Vyberte jeden z dostupných typů algoritmu hash, který chcete s tímto certifikátem použít. Vyberte nejsilnější úroveň zabezpečení, kterou připojované zařízení podporuje. 
    - **Kořenový certifikát** – Zvolte profil certifikátu kořenové CA, který jste nakonfigurovali a přiřadili pro uživatele nebo zařízení. Tento certifikát certifikační autority musí být kořenovým certifikátem pro certifikační autoritu, která vydává certifikát konfigurovaný v tomto profilu. 
    - **Rozšířené použití klíče** – Zvolte **Přidat** a přidejte hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje **Ověření klienta**, aby se mohl uživatel nebo zařízení ověřit na serveru. Můžete ale přidat jakákoli další použití klíče podle potřeby. 
    - **Nastavení registrace**
        - **Prahová hodnota obnovení (%)** – Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
        - **Serverové adresy URL pro SCEP** – Zadejte jednu nebo více adres URL pro servery NDES, které vystavují certifikáty prostřednictvím SCEP. 
8. Vyberte **OK** a pak přejděte zpátky do podokna **Vytvořit profil** a vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.

## <a name="how-to-assign-the-certificate-profile"></a>Přiřazení profilu certifikátu

Před přiřazením profilů certifikátů ke skupinám vezměte v úvahu následující:

- Při přiřazení profilů certifikátů ke skupinám se soubor certifikátu z profilu certifikátu důvěryhodné CA nainstaluje na zařízení. Zařízení profil certifikátu SCEP použije k vytvoření vlastní žádosti o certifikát.
- Profily certifikátů se nainstalují jenom na zařízení s tou platformou, kterou jste použili při vytváření profilu.
- Profily certifikátů můžete přiřadit ke kolekcím uživatelů nebo ke kolekcím zařízení.
- Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, přiřaďte profil certifikátu ke skupině uživatelů (ne zařízení). Pokud ho přiřadíte ke skupině zařízení, budete je muset před obdržením zásad plně zaregistrovat.
- I když se každý profil přiřazuje samostatně, je třeba přiřadit jak důvěryhodnou kořenovou certifikační autoritu, tak profil SCEP nebo PKCS. Jinak zásady certifikátu SCEP nebo PKCS nebudou fungovat.

Informace o tom, jak přiřadit profily, najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).

