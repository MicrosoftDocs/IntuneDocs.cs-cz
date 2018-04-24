---
title: Konfigurace infrastruktury certifikátů pro SCEP
description: Infrastruktura pro vytvoření a nasazení profilů certifikátů SCEP
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e7b266bcc47ae229a200f0b690429f505a59603
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-certificate-infrastructure-for-scep"></a>Konfigurace infrastruktury certifikátů pro SCEP

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Toto téma popisuje, jakou infrastrukturu potřebujete k vytvoření a nasazení profilů certifikátů SCEP.

### <a name="on-premises-infrastructure"></a>Místní infrastruktura

- **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

- **Certifikační autorita** (CA): Označuje se jako vydávající certifikační autorita. Musíte mít certifikační autoritu organizace, která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novějšího. Samostatná certifikační autorita není podporovaná. Návod, jak nastavit certifikační autoritu, najdete v tématu [Instalace certifikační autority](http://technet.microsoft.com/library/jj125375.aspx).
   Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).
  I
- **Server NDES**: Na serveru, na kterém běží Windows Server 2012 R2 nebo novější, musíte nastavit službu zápisu síťových zařízení (NDES). Intune nepodporuje používání služby zápisu síťových zařízení, pokud běží na serveru, na kterém běží taky certifikační autorita organizace. Pokyny k tomu, jak konfigurovat Windows Server 2012 R2 k hostování služby zápisu síťových zařízení, najdete v tématu [Doprovodné materiály ke službě zápisu síťových zařízení](http://technet.microsoft.com/library/hh831498.aspx). Server NDES musí být připojený k doméně, která je hostitelem certifikační autority, a nesmí být na stejném serveru jako tato autorita. Další informace o nasazení serveru NDES v samostatné doménové struktuře, izolované síti nebo interní doméně najdete v tématu věnovaném [použití modulu zásad se službou zápisu síťových zařízení](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector**: Prostřednictvím konzoly pro správu Intune můžete stáhnout instalační program konektoru **Certificate Connector** (**ndesconnectorssetup.exe**). Pak můžete soubor **ndesconnectorssetup.exe** spustit na počítači, kde chcete konektor Certificate Connector nainstalovat.
- **Proxy server webových aplikací** (volitelné): Jako server služby Proxy webových aplikací (WAP) můžete použít server se systémem Windows Server 2012 R2 nebo novějším. Tato konfigurace:
   -  Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
   -  Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.

  > [!NOTE]           
  > -    Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení. Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](https://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](https://support.microsoft.com/kb/3011135).
  >-  Server hostující službu WAP musí mít také certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.
   Informace o certifikátech pro službu WAP najdete v části **Plánování certifikátů** tématu [Plánování publikování aplikací pomocí serveru proxy webových aplikací](https://technet.microsoft.com/library/dn383650.aspx). Obecné informace o serverech WAP najdete v tématu [Práce se serverem proxy webových aplikací](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>Požadavky sítě

Z internetu do hraniční sítě povolte port 443 ze všech hostitelů nebo IP adres na internetu k serveru NDES.

Z hraniční sítě do důvěryhodné sítě povolte všechny porty a protokoly nutné pro doménový přístup k serveru NDES připojenému k doméně. Server NDES potřebuje přístup k serverům certifikátů, serverům DNS, serverům nástroje Configuration Manager a řadičům domény.

Doporučujeme publikování serveru NDES prostřednictvím proxy serveru, jako je například [Azure AD Application Proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) nebo proxy server jiného výrobce.


### <a name="BKMK_CertsAndTemplates"></a>Certifikáty a šablony

|Objekt|Podrobnosti|
|----------|-----------|
|**Šablona certifikátu**|Tuto šablonu konfigurujete na své vydávající certifikační autoritě.|
|**Certifikát pro ověřování klientů**|Tento certifikát vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte na server NDES.|
|**Ověřovací certifikát serverů**|Tento certifikát SSL vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte a připojte ve službě IIS na serveru NDES.|
|**Certifikát důvěryhodné kořenové certifikační autority**|Ten exportujete jako soubor **.cer** z kořenové certifikační autority nebo jakéhokoli zařízení, které důvěřuje kořenové certifikační autoritě, a nasadíte ho do zařízení pomocí profilu certifikátu důvěryhodné certifikační autority.<br /><br />Použijete jeden certifikát důvěryhodné kořenové certifikační autority na každou platformu operačního systému a přidružíte ho ke každému profilu důvěryhodného kořenového certifikátu, který vytvoříte.<br /><br />Pokud potřebujete, můžete vytvořit další certifikáty důvěryhodné kořenové certifikační autority. Můžete to třeba udělat, abyste vytvořili vztah důvěryhodnosti k certifikační autoritě, která podepisuje ověřovací certifikáty serverů pro vaše přístupové body Wi-Fi.|

### <a name="BKMK_Accounts"></a>Účty

|Název|Podrobnosti|
|--------|-----------|
|**Účet služby NDES**|Zadáte účet uživatele domény, který chcete použít jako účet služby NDES.|

## <a name="BKMK_ConfigureInfrastructure"></a>Konfigurace infrastruktury
Před konfigurací profilů certifikátů musíte provést následující úlohy, které vyžadují znalosti systému Windows Server 2012 R2 a služby AD CD (Active Directory Certificate Services):

**Úloha 1**: Vytvoření účtu služby NDES

**Úloha 2**: Konfigurace šablon certifikátů v certifikační autoritě

**Úloha 3**: Konfigurace požadavků na serveru NDES

**Úloha 4**: Konfigurace NDES pro použití se službou Intune

**Úloha 5**: Povolení, instalace a konfigurace Intune Certificate Connectoru

### <a name="task-1---create-an-ndes-service-account"></a>Úloha 1: Vytvoření účtu služby NDES

Vytvořte účet uživatele domény, který chcete použít jako účet služby NDES. Tento účet zadáte při konfiguraci šablon ve vydávající certifikační autoritě před instalací a konfigurací NDES. Ověřte, že uživatel má výchozí práva **Povolit místní přihlášení**, **Přihlásit jako službu** a **Přihlásit jako dávkovou úlohu**. Některé organizace mají zásady posílení zabezpečení, které tato práva zakazují.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>Úloha 2: Konfigurace šablon certifikátů v certifikační autoritě
V této úloze:

-   Konfigurujete šablonu certifikátu pro NDES

-   Publikujete šablonu certifikátu pro NDES

##### <a name="to-configure-the-certification-authority"></a>Konfigurace certifikační autority

1.  Přihlaste se jako správce podnikové sítě.

2.  Ve vydávající certifikační autoritě použijte modul snap-in Šablony certifikátů k vytvoření nové vlastní šablony nebo zkopírování existující šablony a následnému upravení existující šablony (jako je šablona Uživatel) pro použití s NDES.

    Šablona musí obsahovat následující konfigurace:

    -   Zadejte popisný **zobrazovaný název šablony** .

    -   Na kartě **Název subjektu** vyberte možnost **Dodán v žádosti**. (Zabezpečení je vynucené modulem zásad Intune pro NDES).

    -   Na kartě **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

        > [!IMPORTANT]
        > V případě šablon certifikátů pro iOS a Mac OS X na kartě **Rozšíření** upravte **Použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu** .

    -   Na kartě **Zabezpečení** přidejte účet služby NDES a poskytněte šabloně oprávnění k **zápisu**. Správci služby Intune, kteří vytvoří profily SCEP, vyžaduje práva pro **čtení**, aby při vytváření profilů SCEP mohli procházet šablony.

    > [!NOTE]
    > K odvolání certifikátů vyžaduje účet služby NDES oprávnění *Vydávat a spravovat certifikáty* ke každé šabloně certifikátu používané profilem certifikátu.

3.  Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Máte ale možnost konfigurovat, aby certifikační autorita žadateli umožňovala určit jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

    > [!IMPORTANT]
    > Platformy iOS a Mac OS X vždycky používají hodnotu nastavenou v šabloně bez ohledu na ostatní konfigurace, které provedete.

Tady jsou snímky obrazovky ukázkové konfigurace šablony.

![Šablona, karta Vyřízení žádosti](../media/scep_ndes_request_handling.png)

![Šablona, karta Název subjektu](../media/scep_ndes_subject_name.jpg)

![Šablona, karta Zabezpečení](../media/scep_ndes_security.jpg)

![Šablona, karta Rozšíření](../media/scep_ndes_extensions.jpg)

![Šablona, karta Požadavky na vystavování](../media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> Do pole Zásady použití (na 4. snímku obrazovky) zadejte jenom požadované zásady použití. Správnost zadaných voleb zkontrolujte se správci zabezpečení.



Pokud chcete certifikační autoritu konfigurovat, aby žadateli umožňovala určit dobu platnosti, spusťte v certifikační autoritě následující příkazy:

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  Ve vydávající certifikační autoritě použijte modul snap-in Certifikační autorita k publikování šablony certifikátu.

    1.  Vyberte uzel **Šablony certifikátů**, klikněte na **Akce**-&gt; **Nové** &gt; **Vystavovaná šablona certifikátu** a potom vyberte šablonu, kterou jste vytvořili v kroku 2.

    2.  Ověřte, že je šablona publikovaná, jejím zobrazením ve složce **Šablony certifikátů** .


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>Úloha 3: Konfigurace požadavků na serveru NDES
V této úloze:

-   Přidáte NDES do Windows Serveru a konfigurujete službu IIS pro podporu NDES

-   Přidáte účet služby NDES do skupiny IIS_IUSR

-   Nastavíte hlavní název služby (SPN) pro účet služby NDES




1. Na serveru, který bude hostitelem NDES, se musíte přihlásit jako **Správce podnikové sítě**a potom pomocí [Průvodce přidáním rolí a funkcí](https://technet.microsoft.com/library/hh831809.aspx) instalovat NDES:

   1. V průvodci vyberte možnost **Služba AD CS (Active Directory Certificate Services)** , abyste získali přístup ke službám rolí ve službě AD CS. Vyberte **Službu zápisu síťových zařízení**, zrušte zaškrtnutí políčka **Certifikační autorita**a pak dokončete průvodce.

      > [!TIP]
      > Na stránce průvodce **Průběh instalace** neklikejte na **Zavřít**. Místo toho klikněte na odkaz **Konfigurovat službu AD CS (Active Directory Certificate Services) na cílovém serveru**. Tím se otevře průvodce **Konfigurace služby AD CS** , který použijete pro další krok. Po otevření Konfigurace služby AD CS můžete zavřít Průvodce přidáním rolí a funkcí.

   2. Když se na server přidá NDES, průvodce nainstaluje taky službu IIS. Ujistěte se, že má služba IIS následující konfigurace:

      -   **Webový server** &gt; **Zabezpečení** &gt; **Filtrování požadavků**

      -   **Webový server** &gt; **Vývoj aplikací** &gt; **ASP.NET 3.5**. Instalace technologie ASP.NET 3.5 nainstaluje rozhraní .NET Framework 3.5. Při instalaci rozhraní .NET Framework 3.5 nainstalujte základní **rozhraní .NET Framework 3.5** i **Aktivaci protokolem HTTP**.

      -   **Webový server** &gt; **Vývoj aplikací** &gt; **ASP.NET 4.5**. Instalace technologie ASP.NET 4.5 nainstaluje rozhraní .NET Framework 4.5. Při instalaci .NET Framework 4.5 nainstalujte základní rozhraní **.NET Framework 4.5**, **ASP.NET 4.5** a funkci **Služby WCF** &gt; **Aktivace protokolem HTTP**.

      -   **Nástroje pro správu** &gt; **Kompatibilita správy služby IIS 6** &gt; **Kompatibilita metabáze služby IIS 6**

      -   **Nástroje pro správu** &gt; **Kompatibilita správy služby IIS 6** &gt; **Kompatibilita metabáze služby IIS 6 WMI**

   3. Na serveru přidejte účet služby NDES jako člena skupiny **IIS_IUSR**.

2. Na příkazovém řádku se zvýšenými oprávněními spusťte následující příkaz pro nastavení hlavního názvu služby (SPN) účtu služby NDES:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Například pokud je název serveru NDES **Server01**, vaše doména je **Contoso.com**a účet služby je **NDESService**, použijte:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a>Úloha 4: Konfigurace NDES pro použití se službou Intune
V této úloze:

-   Nakonfigurujete NDES pro použití s vydávající certifikační autoritou

-   Vytvoříte vazbu certifikátu serveru ověřování (SSL) ve službě IIS

-   Konfigurujete filtrování požadavků ve službě IIS

##### <a name="to-configure-ndes-for-use-with-intune"></a>Konfigurace NDES pro použití se službou Intune

1. Na serveru NDES otevřete průvodce Konfigurace služby AD CS a pak proveďte následující konfigurace.

   > [!TIP]
   > Pokud jste klikli na odkaz v předchozí úloze, je už tento průvodce otevřený. Jinak spusťte Správce serveru, abyste získali přístup ke konfiguraci po nasazení pro službu AD CS (Active Directory Certificate Services).

   -   Na stránce **Služby rolí** vyberte **Služba zápisu síťových zařízení**.

   -   Na stránce **Účet Služby zápisu síťových zařízení** zadejte účet služby NDES.

   -   Na stránce **Certifikační autorita pro Službu zápisu síťových zařízení** klikněte na **Vybrat**a pak vyberte vydávající certifikační autoritu, kam jste nakonfigurovali šablonu certifikátu.

   -   Na stránce **Kryptografie pro Službu zápisu síťových zařízení** nastavte délku klíče podle požadavků vaší společnosti.

   Na stránce **Potvrzení** klikněte na **Konfigurovat** a dokončete průvodce.

2. Po dokončení průvodce upravte následující klíč registru na serveru NDES:

   - <strong>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\</strong>

   Pokud tento klíč chcete upravit, identifikujte **Účel** šablony certifikátu, jak je uvedený na kartě **Vyřízení žádosti**, a potom upravte odpovídající položku v registru nahrazením stávajících dat názvem šablony certifikátu (ne zobrazovaným názvem šablony), který jste zadali v úloze 1. Následující tabulka mapuje účel šablony certifikátu na hodnoty v registru:


   | Účel šablony certifikátu (na kartě Vyřízení žádosti) | Upravovaná hodnota registru | Hodnota zobrazená v konzole pro správu Intune pro profil SCEP |
   |------------------------------------------------------------|------------------------|-------------------------------------------------------------|
   |                         Podpis                          |   SignatureTemplate    |                      Digitální podpis                      |
   |                         Šifrování                         |   EncryptionTemplate   |                      Šifrování klíče                       |
   |                  Podpis a šifrování                  | GeneralPurposeTemplate |        Šifrování klíče<br /><br />Digitální podpis        |

   Pokud je třeba účelem šablony certifikátu **Šifrování**, pak upravte hodnotu **EncryptionTemplate** , aby byla názvem vaší šablony certifikátu.

3. Server NDES obdrží dvě velmi dlouhé adresy URL (dotazy), které vyžadují, abyste přidali dvě položky registru:

    |Umístění|Hodnota|Typ|Data|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (desítkově)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (desítkově)|


4. Ve modulu Správce služby IIS manager zvolte **Výchozí web** -> **Filtrování požadavků** -> **Upravit nastavení funkcí** a změňte **Maximální délka adresy URL** a **Maximální délka řetězce dotazu** na *65534* (viz obrázek).

    ![Maximální délka dotazu a adresy URL ve službě IIS](../media/SCEP_IIS_max_URL.png)

5. Restartujte server. Spuštění **iisreset** na serveru k dokončení těchto změn nestačí.
6. Přejděte k souboru http://<em>plně_kvalifikovaný_název_domény</em>/certsrv/mscep/mscep.dll. Měla by se zobrazit stránka NDES podobná následující stránce:

    ![Test NDES](../media/SCEP_NDES_URL.png)

    Pokud se zobrazí **503 Služba nedostupná**, zkontrolujte eventviewer. Je pravděpodobné, že se fond aplikací zastavil kvůli chybějícímu oprávnění pro uživatele NDES. Tato práva jsou popsaná v úloze 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Instalace a vytvoření vazby certifikátů na serveru NDES

1.  Na serveru NDES vyžádejte a nainstalujte **ověřovací certifikát serveru** z vaší interní nebo veřejné certifikační autority. Pro tento certifikát SSL pak vytvoříte vazbu ve službě IIS.

    > [!TIP]
    > Po vytvoření vazby certifikátu SSL ve službě IIS nainstalujete taky certifikát pro ověřování klientů. Tento certifikát může být vydaný certifikační autoritou, která je důvěryhodná pro server NDES. I když se nejedná o osvědčený postup, můžete použít stejný certifikát pro ověřování serverů i klientů, pokud má obě rozšířená použití klíče (EKU). Informace o těchto ověřovacích certifikátech najdete v následujících krocích.

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

2.  Klikněte na **Upravit nastavení funkce**a pak nastavte tohle:

    **řetězec dotazu (bajty)** = **65534**

    **Maximální délka adresy URL (bajty)** = **65534**

3.  Zkontrolujte následující klíč registru:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Ujistěte se, že následující hodnoty jsou nastavené jako položky DWORD:

    Název: **MaxFieldLength**, s desetinnou hodnotou **65534**

    Název: **MaxRequestBytes**, s desetinnou hodnotou **65534**

4.  Restartujte server NDES. Server je teď připravený na podporu konektoru Certificate Connector.

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>Úloha 5: Povolení, instalace a konfigurace Intune Certificate Connectoru
V této úloze:

Povolíte podporu NDES ve službě Intune.

Stáhnete, nainstalujete a nakonfigurujete Certificate Connector na serveru NDES.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Povolení podpory pro Certificate Connector

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a klikněte na **Správce** &gt; **Certificate Connector**.

2.  Klikněte na **Konfigurace místního Certificate Connectoru**.

3.  Vyberte **Zapnout Certificate Connector**a potom klikněte na **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace konektoru Certificate Connector

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a potom klikněte na **Správce** &gt; **Správa mobilních zařízení** &gt; **Certificate Connector** &gt; **Stáhnout Certificate Connector**.

2.  Po dokončení stahování spusťte stažený instalační program (**ndesconnectorssetup.exe**) na serveru se systémem Windows Server 2012 R2. Tento instalační program nainstaluje taky modul zásad pro NDES a webovou službu CRP. (Webová služba CRP, CertificateRegistrationSvc, běží ve službě ve službě IIS jako aplikace).

    > [!NOTE]
    > Při instalaci NDES pro samostatnou službu Intune se s konektorem Certificate Connector automaticky nainstaluje služba CRP. Při použití služby Intune se Správcem konfigurace nainstalujete bod registrace certifikátu (CRP) jako samostatnou roli serveru.

3.  Pokud budete vyzváni k zadání klientského certifikátu pro konektor Certificate Connector, klikněte na **Vybrat**a vyberte certifikát pro **ověřování klientů** , který jste nainstalovali na server NDES v úloze 3.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, kliknutím na **Další** zobrazte vlastnosti certifikátu. Pak klikněte na **Další**a pak klikněte na **Nainstalovat**.

4.  Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP]
    > Pokud průvodce zavřete před spuštěním uživatelského rozhraní konektoru Certificate Connector, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > **&lt;cesta_k_instalaci&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  V uživatelském rozhraní **Certificate Connectoru** :

    Klikněte na **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu.

    > [!NOTE]
    > Pokud se vám při přihlašování do NDESConnectorUI.exe zobrazí chybová zpráva o tom, že **se nepovedlo rozpoznat uživatelské jméno**, obvykle to znamená, že jste použili účet, který nemá platnou licenci Intune. Přiřaďte k účtu licenci Intune nebo EMS a zkuste operaci zopakovat.

    Pokud vaše organizace používá proxy server a ten je vyžadovaný pro přístup serveru NDES k internetu, klikněte na **Použít proxy server** a potom zadejte název proxy serveru, port a přihlašovací údaje účtu pro připojení.

    Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **Vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě, a pak klikněte na **Použít**.

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

6.  Otevřete příkazový řádek, zadejte **services.msc** a potom stiskněte **Enter**, klikněte pravým tlačítkem na **Intune Certificate Connector** a nakonec klikněte na **Restartovat**.

Pokud chcete ověřit, jestli je služba spuštěná, spusťte prohlížeč a zadejte následující adresu URL, která by měla vrátit chybu **403** :

**https:// &lt;plně_kvalifikovaný_název_domény_serveru_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>Další kroky
Teď jste připravení konfigurovat profily certifikátů podle návodu v tématu [Konfigurace profilů certifikátů](Configure-Intune-certificate-profiles.md).
