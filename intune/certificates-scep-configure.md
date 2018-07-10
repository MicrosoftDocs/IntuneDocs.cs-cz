---
title: Používání certifikátů SCEP s Microsoft Intune – Azure | Microsoft Docs
description: Pokud chcete v Microsoft Intune používat certifikáty SCEP, nakonfigurujte místní doménu AD, vytvořte certifikační autoritu, nastavte server NDES a nainstalujte Intune Certificate Connector. Potom vytvořte profil certifikátu SCEP a přiřaďte ho ke skupinám. Podívejte se také na ID různých událostí a jejich popisy a na diagnostické kódy služby konektoru Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d42500b9476e0b6c7bc9aaaba1ea4333fd136c6
ms.sourcegitcommit: 29914cc467e69711483b9e2ccef887196e1314ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36297901"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Konfigurace a používání certifikátů SCEP s Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jak pomocí Intune nakonfigurovat infrastrukturu a pak vytvořit a přiřadit profily certifikátů SCEP (Simple Certificate Enrollment Protocol).

## <a name="configure-on-premises-infrastructure"></a>Konfigurace místní infrastruktury

- **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

- **Certifikační autorita** (CA): Označuje se jako vydávající certifikační autorita. Musíte mít certifikační autoritu organizace, která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novějšího. Samostatná certifikační autorita není podporovaná. Podrobnosti najdete v tématu [Instalace certifikační autority](http://technet.microsoft.com/library/jj125375.aspx).
    Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).

- **Server NDES**: Na serveru, na kterém běží Windows Server 2012 R2 nebo novější, musíte nastavit službu zápisu síťových zařízení (NDES). Intune nepodporuje používání služby zápisu síťových zařízení, pokud běží na serveru, na kterém běží taky certifikační autorita organizace. Pokyny k tomu, jak konfigurovat Windows Server 2012 R2 k hostování služby zápisu síťových zařízení, najdete v tématu [Doprovodné materiály ke službě zápisu síťových zařízení](http://technet.microsoft.com/library/hh831498.aspx).
Server NDES musí být připojený k doméně, která je hostitelem certifikační autority, a nesmí být na stejném serveru jako tato autorita. Další informace o nasazení serveru NDES v samostatné doménové struktuře, izolované síti nebo interní doméně najdete v tématu [Použití modulu zásad se Službou zápisu síťových zařízení](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector**: Instalační program **Certificate Connectoru** (**NDESConnectorSetup.exe**) si můžete stáhnout z webu Azure Portal. Pak můžete soubor **NDESConnectorSetup.exe** spustit na serveru hostujícím roli NDES (Network Device Enrollment Service), na který chcete nainstalovat Certificate Connector.

  - Certificate Connector pro NDES také podporuje režim FIPS (Federal Information Processing Standard). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Proxy server webových aplikací** (volitelné): Jako server služby Proxy webových aplikací (WAP) použijte server se systémem Windows Server 2012 R2 nebo novějším. Tato konfigurace:
  - Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
  - Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.

#### <a name="additional"></a>Další

- Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení. Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](http://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](http://support.microsoft.com/kb/3011135).
- Server WAP musí mít certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.

Další informace najdete v [plánování certifikátů pro WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) a [obecných informacích o serverech WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

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
Před konfigurací profilů certifikátů proveďte následující kroky. Pro tyto kroky je potřeba znát Windows Server 2012 R2 nebo novější verzi a službu AD CS (Active Directory Certificate Services):

#### <a name="step-1---create-an-ndes-service-account"></a>Krok 1: Vytvoření účtu služby NDES

Vytvořte účet uživatele domény, který chcete použít jako účet služby NDES. Tento účet zadáte při konfiguraci šablon ve vydávající certifikační autoritě před instalací a konfigurací NDES. Ověřte, že uživatel má výchozí práva **Povolit místní přihlášení**, **Přihlásit jako službu** a **Přihlásit jako dávkovou úlohu**. Některé organizace mají zásady posílení zabezpečení, které tato práva zakazují.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2: Konfigurace šablon certifikátů v certifikační autoritě
V této úloze:

- Konfigurujete šablonu certifikátu pro NDES
- Publikujete šablonu certifikátu pro NDES

##### <a name="configure-the-certification-authority"></a>Konfigurace certifikační autority

1. Přihlaste se jako správce podnikové sítě.

2. Ve vydávající certifikační autoritě použijte modul snap-in Šablony certifikátů a vytvořte novou vlastní šablonu. Můžete také zkopírovat existující šablonu a potom existující šablonu (například šablonu Uživatel) aktualizovat tak, aby ji bylo možné používat s NDES.

   >[!NOTE]
   > Šablona certifikátu NDES musí být založena na modulu snap-in Šablony certifikátů verze 2 (kvůli kompatibilitě s Windows 2003).

   Šablona musí obsahovat následující konfigurace:

   - Zadejte popisný **zobrazovaný název šablony**.

   - Na kartě **Název subjektu** vyberte **Dodat v žádosti**. (Zabezpečení je vynucené modulem zásad Intune pro NDES).

   - V části **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

     > [!IMPORTANT]
     > V případě šablon certifikátů pro iOS a macOS na kartě **Rozšíření** upravte **použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu**.

   - V části **Zabezpečení** přidejte účet služby NDES a udělte mu oprávnění k **registraci** šablony. Správci služby Intune, kteří vytvoří profily SCEP, vyžadují práva pro **čtení**, aby při vytváření profilů SCEP mohli procházet šablony.

     > [!NOTE]
     > K odvolání certifikátů vyžaduje účet služby NDES oprávnění *Vydávat a spravovat certifikáty* ke každé šabloně certifikátu používané profilem certifikátu.

3. Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Máte ale možnost nakonfigurovat, aby certifikační autorita žadateli umožňovala zadat jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

   > [!IMPORTANT]
   > iOS a macOS vždy používá hodnotu nastavenou v šabloně bez ohledu na ostatní konfigurace, které provedete.

Příklad konfigurace šablony:

![Šablona, karta Vyřízení žádosti](./media/scep_ndes_request_handling.png)

![Šablona, karta Název subjektu](./media/scep_ndes_subject_name.jpg)

![Šablona, karta Zabezpečení](./media/scep_ndes_security.jpg)

![Šablona, karta Rozšíření](./media/scep_ndes_extensions.jpg)

![Šablona, karta Požadavky na vystavování](./media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> Do pole Zásady použití přidejte jenom požadované zásady použití. Správnost zadaných voleb zkontrolujte se správci zabezpečení.

Konfigurace certifikační autority, aby žadateli umožňovala zadat dobu platnosti:

1. V certifikační autoritě spusťte tyto příkazy:
   - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   - **net stop certsvc**
   - **net start certsvc**

2. Ve vydávající certifikační autoritě použijte modul snap-in Certifikační autorita k publikování šablony certifikátu.
   Vyberte uzel **Šablony certifikátů**, klikněte na **Akce** > **Nové** > **Vystavovaná šablona certifikátu** a potom vyberte šablonu, kterou jste vytvořili v kroku 2.

3. Ověřte, že je šablona publikovaná, jejím zobrazením ve složce **Šablony certifikátů** .

#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Krok 3: Konfigurace požadavků na serveru NDES
V této úloze:

- Přidáte NDES do Windows Serveru a konfigurujete službu IIS pro podporu NDES
- Přidáte účet služby NDES do skupiny IIS_IUSR
- Nastavíte hlavní název služby (SPN) pro účet služby NDES

1. Na serveru, který je hostitelem NDES, se přihlaste jako **Správce podnikové sítě** a potom pomocí [Průvodce přidáním rolí a funkcí](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) nainstalujte NDES:

   1. V průvodci vyberte možnost **Služba AD CS (Active Directory Certificate Services)** , abyste získali přístup ke službám rolí ve službě AD CS. Vyberte **Službu zápisu síťových zařízení**, zrušte zaškrtnutí políčka **Certifikační autorita**a pak dokončete průvodce.

      > [!TIP]
      > V části **Průběh instalace** nezaškrtávejte políčko **Zavřít**. Místo toho vyberte odkaz **Konfigurovat službu AD CS (Active Directory Certificate Services) na cílovém serveru**. Otevře se průvodce **konfigurací služby AD CS**, který použijete pro další krok. Po otevření Konfigurace služby AD CS můžete zavřít Průvodce přidáním rolí a funkcí.

   2. Když se na server přidá NDES, průvodce nainstaluje taky službu IIS. Ujistěte se, že má služba IIS následující konfigurace:

   3. **Webový server** > **Zabezpečení** > **Filtrování požadavků**

   4. **Webový server** > **Vývoj aplikací** > **ASP.NET 3.5**. Instalace technologie ASP.NET 3.5 nainstaluje rozhraní .NET Framework 3.5. Při instalaci rozhraní .NET Framework 3.5 nainstalujte základní **rozhraní .NET Framework 3.5** i **Aktivaci protokolem HTTP**.

   5. **Webový server** > **Vývoj aplikací** > **ASP.NET 4.5**. Instalace technologie ASP.NET 4.5 nainstaluje rozhraní .NET Framework 4.5. Při instalaci rozhraní .NET Framework 4.5 nainstalujte základní funkci rozhraní **.NET Framework 4.5**, **ASP.NET 4.5** a funkci **Služby WCF** > **Aktivace protokolem HTTP**.

   6. **Nástroje pro správu** > **Kompatibilita správy služby IIS 6** > **Kompatibilita metabáze služby IIS 6**

   7. **Nástroje pro správu** > **Kompatibilita správy služby IIS 6** > **Kompatibilita rozhraní WMI služby IIS 6**

   8. Na serveru přidejte účet služby NDES jako člena skupiny **IIS_IUSR**.

2. Na příkazovém řádku se zvýšenými oprávněními spusťte následující příkaz pro nastavení hlavního názvu služby (SPN) účtu služby NDES:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Například pokud je název serveru NDES **Server01**, vaše doména je **Contoso.com**a účet služby je **NDESService**, použijte:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4: Konfigurace NDES pro použití s Intune
V této úloze:

- Nakonfigurujete NDES pro použití s vydávající certifikační autoritou
- Vytvoříte vazbu certifikátu serveru ověřování (SSL) ve službě IIS
- Konfigurujete filtrování požadavků ve službě IIS

1. Na serveru NDES otevřete průvodce konfigurací služby AD CS a pak proveďte následující aktualizace:

    > [!TIP]
    > Pokud jste klikli na odkaz v předchozí úloze, je už tento průvodce otevřený. Jinak spusťte Správce serveru, abyste získali přístup ke konfiguraci po nasazení pro službu AD CS (Active Directory Certificate Services).

   - Na stránce **Služby rolí** vyberte **Služba zápisu síťových zařízení**.
   - V části **Účet Služby zápisu síťových zařízení** zadejte účet služby NDES.
   - V části **CA pro službu NDES** klikněte na **Vybrat** a pak vyberte vydávající certifikační autoritu, kde jste nakonfigurovali šablonu certifikátu.
   - V části **Kryptografie pro službu NDES** nastavte délku klíče podle požadavků vaší společnosti.
   - V části **Potvrzení** vyberte **Konfigurovat** a dokončete průvodce.

2. Po dokončení průvodce aktualizujte následující klíč registru na serveru NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Pokud chcete aktualizovat tento klíč, určete **účel** šablony certifikátu (najdete ho na kartě **Vyřízení žádosti**). Potom aktualizujte odpovídající položku registru tak, že existující data nahradíte názvem šablony certifikátu (nikoli zobrazovaným názvem šablony), kterou jste zadali v úloze 1. Následující tabulka mapuje účel šablony certifikátu na hodnoty v registru:

    |Účel šablony certifikátu (na kartě Vyřízení žádosti)|Upravovaná hodnota registru|Hodnota zobrazená v konzole pro správu Intune pro profil SCEP|
    |---|---|---|
    |Podpis|SignatureTemplate|Digitální podpis|
    |Šifrování|EncryptionTemplate|Šifrování klíče|
    |Podpis a šifrování|GeneralPurposeTemplate|Šifrování klíče<br/>Digitální podpis|

    Pokud je třeba účelem šablony certifikátu **Šifrování**, pak upravte hodnotu **EncryptionTemplate** , aby byla názvem vaší šablony certifikátu.

3. Server NDES získává dlouhé adresy URL (dotazy), které vyžadují, abyste přidali dvě položky registru:


   |                        Umístění                        |      Hodnota      | Typ  |      Data       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (desítkově) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (desítkově) |

4. Ve správci služby IIS vyberte **Výchozí web** > **Filtrování požadavků** > **Upravit nastavení funkce**. Změňte **maximální délku adresy URL** a **maximální řetězec dotazu** na *65534*, jak je znázorněno níže:

    ![Maximální délka dotazu a adresy URL ve službě IIS](./media/SCEP_IIS_max_URL.png)

5. Restartujte server. Spuštění **iisreset** na serveru k dokončení těchto změn nestačí.
6. Přejděte na `http://*FQDN*/certsrv/mscep/mscep.dll`. Měla by se zobrazit stránka NDES podobná následující stránce:

    ![Test NDES](./media/SCEP_NDES_URL.png)

    Pokud se zobrazí **503 - Služba není k dispozici** , zkontrolujte prohlížeč událostí. Je pravděpodobné, že se fond aplikací zastavil kvůli chybějícímu oprávnění pro uživatele NDES. Tato práva jsou popsaná v úloze 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Instalace a vytvoření vazby certifikátů na serveru NDES

1. Na serveru NDES vyžádejte a nainstalujte **ověřovací certifikát serveru** z vaší interní nebo veřejné certifikační autority. Pro tento certifikát SSL pak vytvoříte vazbu ve službě IIS.

    > [!TIP]
    > Po vytvoření vazby certifikátu SSL ve službě IIS nainstalujte certifikát pro ověřování klientů. Tento certifikát může být vydaný certifikační autoritou, která je důvěryhodná pro server NDES. I když se nejedná o osvědčený postup, můžete použít stejný certifikát pro ověřování serverů i klientů, pokud má obě rozšířená použití klíče (EKU). Informace o těchto ověřovacích certifikátech najdete v následujících krocích.

   1. Jakmile získáte ověřovací certifikátu serverů, otevřete **Správce IIS** a vyberte **Výchozí web**. V podokně **Akce** vyberte **Vazby**.

   2. Vyberte **Přidat**, nastavte **Typ** na **https** a potom zkontrolujte, že port je **443**. Pro samostatnou službu Intune se podporuje jenom port 443.

   3. Jako **Certifikát SSL** zadejte ověřovací certifikát serverů.

      > [!NOTE]
      > Pokud server NDES používá pro jednu síťovou adresu externí a interní název, musí ověřovací certifikát serverů mít:
      > - **Název subjektu** s externím veřejným názvem serveru
      > - **Alternativní název subjektu**, který obsahuje interní název serveru

2. Na serveru NDES vyžádejte a nainstalujte certifikát pro **ověřování klientů** z vaší interní certifikační autority nebo z veřejné certifikační autority. Může to být stejný certifikát jako ověřovací certifikát serverů, pokud má tento certifikát obě schopnosti.

    Certifikát pro ověřování klientů musí mít následující vlastnosti:

    - **Rozšířené použití klíče**: Tato hodnota musí zahrnovat **Ověření klienta**.

    - **Název subjektu**: Tato hodnota musí být stejná jako název DNS serveru, na který instalujete certifikát (server NDES).

##### <a name="configure-iis-request-filtering"></a>Konfigurace filtrování požadavků služby IIS

1. Na serveru NDES otevřete **Správce služby IIS**, vyberte **Výchozí webový server** v podokně **Připojení** a pak otevřete **Filtrování požadavků**.

2. Vyberte **Upravit nastavení funkce**a pak nastavte tyto hodnoty:

    - **řetězec dotazu (bajty)** = **65534**
    - **Maximální délka adresy URL (bajty)** = **65534**

3. Zkontrolujte následující klíč registru:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Zkontrolujte, že následující hodnoty jsou nastavené jako položky DWORD:

    - Název: **MaxFieldLength**, s desetinnou hodnotou **65534**
    - Název: **MaxRequestBytes**, s desetinnou hodnotou **65534**

4. Restartujte server NDES. Server je teď připravený na podporu konektoru Certificate Connector.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5: Povolení, instalace a konfigurace Intune Certificate Connectoru
V této úloze:

- Povolíte podporu NDES ve službě Intune.
- Stáhnete Certificate Connector a pak ho nainstalujete a nakonfigurujete na serveru, který je hostitelem role Služba zápisu síťových zařízení (NDES) ve vašem prostředí. Pokud chcete zvýšit škálování implementace NDES, můžete nainstalovat více serverů NDES s Microsoft Intune Certificate Connectorem.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace Certificate Connectoru

![ConnectorDownload](./media/certificates-download-connector.png)

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** a potom **Certifikační autorita**.
4. Vyberte **Přidat** a **Stáhnout soubor konektoru**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který ho budete instalovat.
5. Jakmile se soubor stáhne, přejděte na server hostující roli NDES (Network Device Enrollment Service). Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework, protože ho vyžaduje NDES Certificate Connector. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Spusťte instalační program (**NDESConnectorSetup.exe**). Tento instalační program nainstaluje taky modul zásad pro NDES a webovou službu CRP. Webová služba CRP, která má označení CertificateRegistrationSvc, běží ve službě IIS jako aplikace.

    > [!NOTE]
    > Při instalaci NDES pro samostatnou službu Intune se s konektorem Certificate Connector automaticky nainstaluje služba CRP. Při použití služby Intune se Správcem konfigurace nainstalujete bod registrace certifikátu (CRP) jako samostatnou roli serveru.

6. Pokud se zobrazí výzva k zadání klientského certifikátu pro konektor Certificate Connector, klikněte na **Vybrat** a vyberte certifikát pro **ověřování klientů**, který jste nainstalovali na server NDES v úloze 3.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, vyberte **Další** a zobrazte vlastnosti certifikátu. Vyberte **Další** a potom **Nainstalovat**.

    > [!IMPORTANT]
    > Intune Certificate Connector nejde zaregistrovat na zařízení s povolenou konfigurací rozšířeného zabezpečení aplikace Internet Explorer. Pokud chcete použít Intune Certificate Connector, [zakažte konfiguraci rozšířeného zabezpečení aplikace Internet Explorer](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx).

7. Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP]
    > Pokud průvodce zavřete před spuštěním uživatelského rozhraní konektoru Certificate Connector, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > <instalační_cesta>\NDESConnectorUI\NDESConnectorUI.exe

8. V uživatelském rozhraní **Certificate Connectoru** :

    Vyberte **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu.

    > [!IMPORTANT]
    > K uživatelskému účtu musí být přiřazená platná licence pro Intune. Pokud daný uživatelský účet nemá platnou licenci pro Intune, spuštění příkazu NDESConnectorUI.exe se nezdaří.

    Pokud vaše organizace používá proxy server a ten je vyžadovaný pro přístup serveru NDES k internetu, vyberte **Použít proxy server** a potom zadejte název proxy serveru, port a přihlašovací údaje účtu pro připojení.

    Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě. Provedené změny **použijte**.

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

9. Otevřete příkazový řádek, zadejte **services.msc** a stiskněte **Enter**. Pravým tlačítkem myši klikněte na **Služba konektoru Intune** a na **Restartovat**.

Pokud chcete ověřit, že je služba spuštěná, spusťte prohlížeč a zadejte následující adresu URL. Měla by vrátit chybu **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> NDES Certificate Connector podporuje také protokol TLS 1.2. Pokud server s nainstalovaným NDES Certificate Connectorem podporuje TLS 1.2, použije se TLS 1.2. Pokud server nepodporuje TLS 1.2, použije se TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

## <a name="create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1. Na portálu Azure Portal otevřete Microsoft Intune.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu certifikátu SCEP.
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento certifikát SCEP. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
   - **Androidem**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 a novější**
   - **Windows 10 a novější**
5. V rozevíracím seznamu **Typ profilu** zvolte **Certifikát SCEP**.
6. V podokně **Certifikát SCEP** nakonfigurujte tato nastavení:

   - **Období platnosti certifikátu**: Pokud jste spustili příkaz `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` na vydávající CA, která umožňuje nastavit vlastní období platnosti certifikátu, můžete zadat dobu zbývající do vypršení platnosti certifikátu.<br>Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vydávající CA. 
   - **Zprostředkovatel úložiště klíčů (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): Zadejte, kam se má uložit klíč k certifikátu. Vyberte jednu z těchto hodnot:
     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), pokud existuje, jinak zapsat do softwarového KSP**
     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), jinak chyba**
     - **Zapsat do služby Passport, jinak chyba (Windows 10 a novější)**
     - **Zapsat do softwarového KSP**

   - **Formát názvu subjektu**: Ze seznamu vyberte způsob, jak má Intune automaticky vytvořit název subjektu v žádosti o certifikát. Pokud je certifikát určený pro uživatele, můžete do názvu subjektu zahrnout taky e-mailovou adresu uživatele. Vybírejte z těchto možností:
     - **Není nakonfigurováno**
     - **Běžný název**
     - **Běžný název včetně e-mailové adresy**
     - **Běžný název jako e-mail**
     - **IMEI (International Mobile Equipment Identity)**
     - **Sériové číslo**
     - **Vlastní**: Když vyberete tuto možnost, zobrazí se další pole rozevíracího seznamu. V tomto poli můžete zadat vlastní formát názvu subjektu. Vlastní formát podporuje dvě proměnné: **Běžný název (CN)** a **E-mail (E)**. **Běžný název (CN)** můžete nastavit na některou z těchto proměnných:
       - **CN={{UserName}}**: Hlavní název uživatele, například janedoe@contoso.com
       - **CN={{AAD_Device_ID}}**: ID přiřazené při registraci zařízení ve službě AD (Azure Active Directory). Toto ID se obvykle používá k ověření ve službě Azure AD.
       - **CN={{SERIALNUMBER}}**: Jedinečné sériové číslo (SN), které obvykle používá výrobce k identifikaci zařízení
       - **CN={{IMEINumber}}**: Jedinečné číslo IMEI (International Mobile Equipment Identity), které slouží k identifikaci mobilního telefonu
       - **CN={{OnPrem_Distinguished_Name}}**: Posloupnost relativních rozlišujících názvů oddělených čárkami, například `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

          Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, nezapomeňte synchronizovat atribut uživatele `onpremisesdistingishedname` pomocí služby [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

       - **CN={{onPremisesSamAccountName}}**: Správci můžou synchronizovat atribut samAccountName z Active Directory do Azure AD pomocí Azure AD Connect do atributu zvaného `onPremisesSamAccountName`. Intune může tuto proměnnou nahradit v rámci žádosti o vystavení certifikátu v předmětu certifikátu SCEP.  Atribut samAccountName je přihlašovací jméno uživatele, které slouží pro podporu klientů a serverů z předchozí verze Windows (před Windows 2000). Formát přihlašovacího jména uživatele je: `DomainName\testUser` nebo jenom `testUser`.

          Pokud chcete použít proměnnou `{{onPremisesSamAccountName}}`, nezapomeňte synchronizovat atribut uživatele `onPremisesSamAccountName` pomocí služby [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

       Použitím kombinace jedné či více těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu, například: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**. <br/> V tomto příkladu jste vytvořili formát názvu subjektu, který kromě proměnných CN a E používá řetězce pro hodnoty Organizační jednotka (OU), Organizace (O), Umístění (L), Oblast (S) a Země (C). Článek [Funkce CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) popisuje tuto funkci a její podporované řetězce.

- **Alternativní název subjektu**: Zadejte způsob, jak má Intune automaticky vytvořit hodnoty pro alternativní název subjektu (SAN) v žádosti o certifikát. Pokud vyberete třeba uživatelský typ certifikátu, můžete do alternativního názvu subjektu zahrnout hlavní název uživatele (UPN). Pokud klientský certifikát slouží k ověřování na server NPS (Network Policy Server), musíte alternativní název subjektu nastavit na UPN.
- **Použití klíče**: Zadejte možnosti použití klíče pro certifikát. Možnosti:
  - **Šifrování klíče**: Umožňuje výměnu klíče jenom v případě, že je klíč zašifrovaný.
  - **Digitální podpis**: Umožňuje výměnu klíče jenom v případě, že se k ochraně klíče využívá digitální podpis.
- **Velikost klíče (bity)**: Vyberte počet bitů, které klíč obsahuje.
- **Hashovací algoritmus** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): Vyberte jeden z dostupných typů hashovacího algoritmu, který chcete s tímto certifikátem použít. Vyberte nejsilnější úroveň zabezpečení, kterou připojované zařízení podporuje.
- **Kořenový certifikát**: Zvolte profil certifikátu kořenové CA, který jste už nakonfigurovali a přiřadili pro uživatele nebo zařízení. Tento certifikát certifikační autority musí být kořenovým certifikátem pro certifikační autoritu, která vydává certifikát konfigurovaný v tomto profilu.
- **Rozšířené použití klíče**: **Přidejte** hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje **Ověření klienta**, aby se mohl uživatel nebo zařízení ověřit na serveru. Můžete ale přidat jakákoli další použití klíče podle potřeby.
- **Nastavení registrace**
  - **Prahová hodnota obnovení (%)**: Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
  - **Serverové adresy URL pro SCEP**: Zadejte jednu nebo více adres URL pro servery NDES, které vystavují certifikáty prostřednictvím SCEP.
  - Vyberte **OK** a **vytvořte** profil.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.

## <a name="assign-the-certificate-profile"></a>Přiřazení profilu certifikátu

Před přiřazením profilů certifikátů ke skupinám vezměte v úvahu následující:

- Při přiřazení profilů certifikátů ke skupinám se soubor certifikátu z profilu certifikátu důvěryhodné CA nainstaluje na zařízení. Zařízení profil certifikátu SCEP použije k vytvoření vlastní žádosti o certifikát.
- Profily certifikátů se nainstalují jenom na zařízení s tou platformou, kterou jste použili při vytváření profilu.
- Profily certifikátů můžete přiřadit ke kolekcím uživatelů nebo ke kolekcím zařízení.
- Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, přiřaďte profil certifikátu ke skupině uživatelů (ne zařízení). Pokud ho přiřadíte ke skupině zařízení, budete je muset před obdržením zásad plně zaregistrovat.
- I když se každý profil přiřazuje samostatně, je třeba přiřadit jak důvěryhodnou kořenovou certifikační autoritu, tak profil SCEP nebo PKCS. Jinak zásady certifikátu SCEP nebo PKCS nebudou fungovat.

    > [!NOTE]
    > U iOSu byste měli počítat s tím, že se v profilu správy zobrazí více kopií certifikátu, pokud nasadíte více profilů prostředků, které používají stejný profil certifikátu.

Informace o přiřazení profilů najdete v článku o [přiřazení profilů zařízení](device-profile-assign.md).

## <a name="intune-connector-setup-verification-and-troubleshooting"></a>Ověření nastavení Intune Connectoru a řešení potíží

Pokud chcete řešit potíže nebo ověřit nastavení Intune Connectoru, podívejte se na [ukázkové skripty certifikační autority](https://aka.ms/intuneconnectorverificationscript).

## <a name="intune-connector-events-and-diagnostic-codes"></a>Události a diagnostické kódy konektoru Intune

Služba Intune Connector od verze 6.1806.x.x zaznamenává události do **Prohlížeče událostí** (**Protokoly aplikací a služeb** > **Microsoft Intune Connector**). Tyto události vám můžou pomoct při řešení možných problémů v konfiguraci konektoru Intune. Tyto události zaznamenávají úspěšné a neúspěšné operace a obsahují také diagnostické kódy se zprávami, které můžou správci IT usnadnit řešení problémů.

### <a name="event-ids-and-descriptions"></a>ID událostí a jejich popisy

> [!NOTE]
> Podrobné informace o souvisejících diagnostických kódech pro jednotlivé události najdete v tabulce **Diagnostické kódy** (v tomto článku).

| ID události      | Název události    | Popis události | Související diagnostické kódy |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Služba konektoru se spustila. | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Služba konektoru se zastavila. | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Certifikát registrace konektoru se úspěšně obnovil. | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Certifikát registrace konektoru se nepodařilo obnovit. Přeinstalujte konektor. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Certifikát registrace konektoru se nepodařilo načíst z registru. V podrobnostech události zkontrolujte kryptografický otisk certifikátu, který se vztahuje k této události. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | V podrobnostech události zkontrolujte diagnostické informace. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Certifikát PKCS se úspěšně vystavil. V podrobnostech události zkontrolujte ID zařízení, ID uživatele, název certifikační autority, název šablony certifikátu a kryptografický otisk certifikátu, které se vztahují k této události. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Certifikát PKCS se nepodařilo vystavit. V podrobnostech události zkontrolujte ID zařízení, ID uživatele, název certifikační autority, název šablony certifikátu a kryptografický otisk certifikátu, které se vztahují k této události. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Certifikát se úspěšně odvolal. V podrobnostech události zkontrolujte ID zařízení, ID uživatele, název certifikační autority a sériové číslo certifikátu, které se vztahují k této události. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Certifikát se nepovedlo odvolat. V podrobnostech události zkontrolujte ID zařízení, ID uživatele, název certifikační autority a sériové číslo certifikátu, které se vztahují k této události. Další informace najdete v protokolech SVC NDES.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Žádost o certifikát nebo údaje o odvolání certifikátu se úspěšně nahrály. V podrobnostech události zkontrolujte podrobnosti o nahrání. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Žádost o certifikát nebo údaje o odvolání certifikátu se nepodařilo nahrát. V podrobnostech události zkontrolujte stav nahrávání, abyste zjistili, kde došlo k chybě.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Žádost o podepsání certifikátu se úspěšně stáhla, stáhněte si klientský certifikát nebo odvolejte certifikát. V podrobnostech události zkontrolujte podrobnosti o stažení.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Žádost o podepsání certifikátu se nepodařilo stáhnout, stáhněte si klientský certifikát nebo odvolejte certifikát. V podrobnostech události zkontrolujte podrobnosti o stažení. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Bod registrace certifikátu úspěšně dokončil ověřovací test klienta. | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Bod registrace certifikátu se dokončil, ale žádost se zamítla. Další podrobnosti poskytne diagnostický kód a zpráva. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Bodu registrace certifikátu se nepodařilo ověřovací test klienta úspěšně dokončit. Další podrobnosti poskytne diagnostický kód a zpráva. V podrobnostech zprávy o události vyhledejte ID zařízení, které se vztahuje k tomuto ověřovacímu testu. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Bod registrace certifikátu úspěšně dokončil proces oznamování a odeslal certifikát do klientského zařízení. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Bodu registrace certifikátu se nepodařilo dokončit proces oznamování. V podrobnostech zprávy o události vyhledejte informace o této žádosti. Ověřte připojení mezi serverem NDES a certifikační autoritou. | 0x00000000, 0x0FFFFFFF |

### <a name="diagnostic-codes"></a>Diagnostické kódy

| Diagnostický kód | Název diagnostiky | Diagnostická zpráva |
| -------------   | -------------   | -------------      |
| 0x00000000 | Úspěch  | Úspěch |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Certifikační autorita není platná nebo není dostupná. Ověřte, že je certifikační autorita dostupná a že s ní váš server může komunikovat. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Certifikát ověřování klienta Symantec se v místním úložišti certifikátů nenašel. Další informace najdete v článku o [instalaci certifikátu RA Symantec](https://docs.microsoft.com/en-us/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate).  |
| 0x00000402 | RevokeCert_AccessDenied  | Zadaný účet nemá oprávnění k odvolání certifikátu z certifikační autority. V podrobnostech zprávy o události vyhledejte pole Název certifikační autority, abyste zjistili vydávající certifikační autoritu.  |
| 0x00000403 | CertThumbprint_NotFound  | Certifikát odpovídající vašemu vstupu se nepodařilo najít. Zaregistrujte si Certificate Connector a zkuste to znovu. |
| 0x00000404 | Certificate_NotFound  | Certifikát odpovídající zadanému vstupu se nepodařilo najít. Zaregistrujte si znovu Certificate Connector a zkuste to znovu. |
| 0x00000405 | Certificate_Expired  | Platnost certifikátu vypršela. Zaregistrujte si znovu Certificate Connector, aby se certifikát obnovil, a zkuste to znovu. |
| 0x00000408 | CRPSCEPCert_NotFound  | Certifikát šifrování CRP se nepodařilo najít. Ověřte správné nastavení NDES a konektoru Intune. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Podpisový certifikát se nepodařilo načíst. Ověřte, že je služba konektoru Intune správně nakonfigurovaná a že je spuštěná. Ověřte také, že se úspěšně dokončily události stažení certifikátu. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Žádost ověřovacího testu SCEP se nepodařilo deserializovat. Ověřte správné nastavení NDES a konektoru Intune. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Žádost se zamítla kvůli vypršení platnosti ověřovacího testu certifikátu. Po načtení nového ověřovacího testu ze serveru pro správu může klientské zařízení pokus opakovat. |
| 0x0FFFFFFFF | Unknown_Error  | Vaši žádost nemůžeme dokončit, protože došlo k chybě na straně serveru. Zkuste to prosím znovu. |

## <a name="next-steps"></a>Další kroky
[Použijte certifikáty PKCS](certficates-pfx-configure.md) nebo [vystavte certifikáty PKCS z webové služby správce infrastruktury veřejných klíčů Symantec](certificates-symantec-configure.md).
