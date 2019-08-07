---
title: Používání certifikátů SCEP s Microsoft Intune – Azure | Microsoft Docs
description: Pokud chcete v Microsoft Intune používat certifikáty SCEP, nakonfigurujte místní doménu AD, vytvořte certifikační autoritu, nastavte server NDES a nainstalujte Intune Certificate Connector. Potom vytvořte profil certifikátu SCEP a přiřaďte ho ke skupinám. Podívejte se také na ID různých událostí a jejich popisy a na diagnostické kódy služby konektoru Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/28/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 47c2e509c9eb032dae67dbb5a44839f88fa5de4b
ms.sourcegitcommit: e6edfbfd63dd7c2500ce1123205aa2af9a7e8e2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68783079"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Konfigurace a používání certifikátů SCEP s Intune

Tento článek popisuje, jak pomocí Intune nakonfigurovat infrastrukturu a pak vytvořit a přiřadit profily certifikátů SCEP (Simple Certificate Enrollment Protocol).

## <a name="configure-on-premises-infrastructure"></a>Konfigurace místní infrastruktury

- **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

- **Certifikační autorita** (CA): Musí se jednat o certifikační autoritu rozlehlé sítě (CA) společnosti Microsoft, která je spuštěna v edici Enterprise systému Windows Server 2008 R2 nebo novější. Samostatná certifikační autorita není podporovaná. Podrobnosti najdete v tématu [Instalace certifikační autority](https://technet.microsoft.com/library/jj125375.aspx).
    Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).

- **Server NDES**: V systému Windows Server 2012 R2 nebo novějším nastavte roli serveru Služba zápisu síťových zařízení (NDES). Intune nepodporuje používání služby zápisu síťových zařízení na serveru, na kterém se provozuje také certifikační autorita organizace. Pokyny ke konfiguraci Windows Serveru 2012 R2 pro hostování této služby najdete v [doprovodných materiálech ke službě zápisu síťových zařízení](https://technet.microsoft.com/library/hh831498.aspx).
Server NDES musí být připojený k doméně ve stejné doménové struktuře jako certifikační autorita organizace. Další informace o nasazení serveru NDES v samostatné doménové struktuře, izolované síti nebo interní doméně najdete v tématu [Použití modulu zásad se Službou zápisu síťových zařízení](https://technet.microsoft.com/library/dn473016.aspx). Není možné použít server NDES, který se už používá s jinou MDM.

- **Microsoft Intune Certificate Connector**: Na portálu Intune přejděte na **Konfigurace** > zařízení**konektory** > certifikátů**Přidat**a postupujte podle *pokynů k instalaci konektoru pro SCEP*. Pomocí odkazu ke stažení na portálu začněte stahovat instalační program konektoru Certificate Connector **NDESConnectorSetup. exe**.  Tento instalační program spustíte na serveru s rolí NDES.  

Tento konektor certifikátů NDES podporuje také režim FIPS (Federal Information Processing Standard). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Server služby Proxy webových aplikací** (volitelné): Jako server proxy webové aplikace (WAP) použijte server, na kterém běží Windows Server 2012 R2 nebo novější. Tato konfigurace:
  - Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
  - Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.
  
- **Proxy aplikací služby AD Azure** (volitelné): K publikování serveru NDES na internetu se dá použít Azure Proxy aplikací služby AD místo vyhrazeného serveru proxy webových aplikací (WAP). Další informace najdete v tématu [Jak poskytnout zabezpečený vzdálený přístup k místním aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

### <a name="additional"></a>Další

- Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení. Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](http://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](http://support.microsoft.com/kb/3011135).
- Server WAP musí mít certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.

Další informace najdete v [plánování certifikátů pro WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) a [obecných informacích o serverech WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="network-requirements"></a>Síťové požadavky

Pokud nepoužíváte reverzní proxy, jako je například WAP nebo Proxy aplikací služby Azure AD, povolte provoz TCP na portu 443 ze všech hostitelů nebo IP adres v internetu na server NDES.

Povolte všechny potřebné porty a protokoly mezi serverem NDES a jakoukoli podpůrnou infrastrukturou. Server NDES například potřebuje komunikovat s certifikační autoritou, servery DNS, servery Configuration Manageru, řadiči domény a dalšími možnými službami ve vašem prostředí.

Důrazně doporučujeme publikování serveru NDES prostřednictvím reverzního proxy, jako je například [Proxy aplikací služby Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) nebo proxy jiného výrobce.

### <a name="certificates-and-templates"></a>Certifikáty a šablony  

|Object|Podrobnosti|
|----------|-----------|
|**Šablona certifikátu**|Tuto šablonu nakonfigurujte na své vydávající certifikační autoritě.|
|**Certifikát pro ověřování klientů**|Tento certifikát vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte na server NDES.|
|**Ověřovací certifikát serverů**|Tento certifikát SSL vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte a připojte ve službě IIS na serveru NDES. Pokud tento certifikát obsahuje sadu použití klíče pro ověřování klienta a serveru (**rozšířené použití klíče**), můžete použít stejný certifikát.|
|**Certifikát důvěryhodné kořenové certifikační autority**|Exportujte tento certifikát jako soubor **.cer** z kořenové certifikační autority nebo jakéhokoli zařízení, které kořenové certifikační agentuře důvěřuje. Pak ji přiřaďte uživatelům, zařízením nebo oběma způsoby pomocí profilu certifikátu důvěryhodné certifikační autority.<br /> **Poznámka:<br />při přiřazení profilu certifikátu SCEP nezapomeňte přiřadit *profil důvěryhodného kořenového certifikátu* , na který je odkazováno v profilu certifikátu SCEP, stejnému uživateli nebo skupině zařízení.  Chcete-li vytvořit tento profil, přečtěte si téma [Vytvoření profilu důvěryhodného certifikátu](certficates-pfx-configure.md#create-a-trusted-certificate-profile), který je popsán v článku o profilech certifikátů PKCS.** <br/><br />Použijete jeden certifikát důvěryhodné kořenové certifikační autority na každou platformu operačního systému a přidružíte ho ke každému profilu důvěryhodného kořenového certifikátu, který vytvoříte. <br /><br />Pokud potřebujete, můžete vytvořit další certifikáty důvěryhodné kořenové certifikační autority. Můžete to třeba udělat, abyste vytvořili vztah důvěryhodnosti k certifikační autoritě, která podepisuje ověřovací certifikáty serverů pro vaše přístupové body Wi-Fi.|

### <a name="accounts"></a>Účty

|Name|Podrobnosti|
|--------|-----------|
|**Účet služby NDES**|Zadejte účet uživatele domény, který chcete použít jako účet služby NDES. |

## <a name="configure-your-infrastructure"></a>Konfigurace infrastruktury
Před konfigurací profilů certifikátů proveďte následující kroky. Tento postup vyžaduje znalost Windows Serveru 2012 R2 nebo novější verze a služby AD CS (Active Directory Certificate Services):

### <a name="step-1---create-an-ndes-service-account"></a>Krok 1: Vytvoření účtu služby NDES

Vytvořte účet uživatele domény, který chcete použít jako účet služby NDES. Tento účet zadáte při konfiguraci šablon ve vydávající certifikační autoritě před instalací a konfigurací NDES. Ověřte, že uživatel má výchozí práva **Povolit místní přihlášení**, **Přihlásit jako službu** a **Přihlásit jako dávkovou úlohu**. Některé organizace mají zásady posílení zabezpečení, které tato práva zakazují.

### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Krok 2: Konfigurace šablon certifikátů v certifikační autoritě
Činnosti uskutečněné v tomto kroku:

- Konfigurujete šablonu certifikátu pro NDES
- Publikujete šablonu certifikátu pro NDES

#### <a name="configure-the-certification-authority"></a>Konfigurace certifikační autority

1. Přihlaste se jako správce podnikové sítě.

2. Ve vydávající certifikační autoritě použijte modul snap-in Šablony certifikátů a vytvořte novou vlastní šablonu. Můžete také zkopírovat existující šablonu a potom existující šablonu (například šablonu Uživatel) aktualizovat tak, aby ji bylo možné používat s NDES.

   >[!NOTE]
   > Šablona certifikátu NDES musí být založena na modulu snap-in Šablony certifikátů verze 2 (kvůli kompatibilitě s Windows 2003).

   Šablona musí obsahovat následující konfigurace:

   - Na kartě **Obecné**:
   
       - Ověřte, že vlastnost **Publikovat certifikát do Active Directory** **není** zaškrtnutá.
       - Zadejte popisný **zobrazovaný název šablony**.

   - Na kartě **Název subjektu** vyberte **Dodat v žádosti**. (Zabezpečení je vynucené modulem zásad Intune pro NDES).

   - V části **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

     > [!IMPORTANT]
     > V případě šablon certifikátů pro iOS a macOS na kartě **Rozšíření** upravte **použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu**.

   - V části **Zabezpečení** přidejte účet služby NDES a udělte mu oprávnění k **registraci** šablony. Správci služby Intune, kteří vytvoří profily SCEP, vyžadují práva pro **čtení**, aby při vytváření profilů SCEP mohli procházet šablony.

     > [!NOTE]
     > K odvolání certifikátů vyžaduje účet služby NDES oprávnění vydávat *a spravovat certifikáty* certifikační autority. Chcete-li toto oprávnění delegovat, otevřete konzolu pro správu certifikační autority a klikněte pravým tlačítkem myši na název certifikační autority. Pak na kartě zabezpečení přidejte nebo vyberte účet a potom zaškrtněte políčko pro vystavení **a správu certifikátů**.


3. Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Můžete ale nakonfigurovat, aby certifikační autorita žadateli umožňovala zadat jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

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

### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Krok 3: Konfigurace požadavků na serveru NDES
Činnosti uskutečněné v tomto kroku:

- Přidáte NDES do Windows Serveru a konfigurujete službu IIS pro podporu NDES
- Přidáte účet služby NDES do skupiny IIS_IUSR
- Nastavíte hlavní název služby (SPN) pro účet služby NDES

1. Na serveru, který je hostitelem NDES, se přihlaste jako **Správce podnikové sítě** a potom pomocí [Průvodce přidáním rolí a funkcí](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) nainstalujte NDES:

   1. V průvodci vyberte možnost **Služba AD CS (Active Directory Certificate Services)** , abyste získali přístup ke službám rolí ve službě AD CS. Vyberte **Službu zápisu síťových zařízení**, zrušte zaškrtnutí políčka **Certifikační autorita**a pak dokončete průvodce.

      > [!TIP]
      > V části **Průběh instalace** nezaškrtávejte políčko **Zavřít**. Místo toho vyberte odkaz **Konfigurovat službu AD CS (Active Directory Certificate Services) na cílovém serveru**. Otevře se průvodce **Konfigurace služby AD CS**, který použijete pro další krok. Po otevření Konfigurace služby AD CS můžete zavřít Průvodce přidáním rolí a funkcí.

   2. Když se na server přidá NDES, průvodce nainstaluje taky službu IIS. Ověřte, že služba IIS má následující konfiguraci:

       - **Webový server** > **Zabezpečení** > **Filtrování požadavků**

       - **Webový server** > **Vývoj aplikací** > **ASP.NET 3.5** 

            Instalace technologie ASP.NET 3.5 nainstaluje rozhraní .NET Framework 3.5. Při instalaci rozhraní .NET Framework 3.5 nainstalujte základní **rozhraní .NET Framework 3.5** i **Aktivaci protokolem HTTP**.

       - **Webový server** > **Vývoj aplikací** > **ASP.NET 4.5** 

            Instalace technologie ASP.NET 4.5 nainstaluje rozhraní .NET Framework 4.5. Při instalaci rozhraní .NET Framework 4.5 nainstalujte základní funkci rozhraní **.NET Framework 4.5**, **ASP.NET 4.5** a funkci **Služby WCF** > **Aktivace protokolem HTTP**.

       - **Nástroje pro správu** > **Kompatibilita správy služby IIS 6** > **Kompatibilita metabáze služby IIS 6**

       - **Nástroje pro správu** > **Kompatibilita správy služby IIS 6** > **Kompatibilita rozhraní WMI služby IIS 6**

       - Na serveru přidejte účet služby NDES jako člena místní skupiny **IIS_IUSR**.

2. Na příkazovém řádku se zvýšenými oprávněními spusťte následující příkaz pro nastavení hlavního názvu služby (SPN) účtu služby NDES:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Například pokud je název serveru NDES **Server01**, vaše doména je **Contoso.com**a účet služby je **NDESService**, použijte:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

### <a name="step-4---configure-ndes-for-use-with-intune"></a>Krok 4: Konfigurace NDES pro použití s Intune
Činnosti uskutečněné v tomto kroku:

- Nakonfigurujete NDES pro použití s vydávající certifikační autoritou
- Vytvoříte vazbu certifikátu serveru ověřování (SSL) ve službě IIS
- Konfigurujete filtrování požadavků ve službě IIS

1. Na serveru NDES otevřete průvodce konfigurací služby AD CS a pak proveďte následující aktualizace:

    > [!TIP]
    > Pokud jste klikli na odkaz v předchozím kroku, je už tento průvodce otevřený. Jinak spusťte Správce serveru, abyste získali přístup ke konfiguraci po nasazení pro službu AD CS (Active Directory Certificate Services).

   - Na stránce **Služby rolí** vyberte **Služba zápisu síťových zařízení**.
   - V části **Účet Služby zápisu síťových zařízení** zadejte účet služby NDES.
   - V části **CA pro službu NDES** klikněte na **Vybrat** a pak vyberte vydávající certifikační autoritu, kde jste nakonfigurovali šablonu certifikátu.
   - V části **Kryptografie pro službu NDES** nastavte délku klíče podle požadavků vaší společnosti.
   - V části **Potvrzení** vyberte **Konfigurovat** a dokončete průvodce.

2. Po dokončení průvodce aktualizujte následující klíč registru na serveru NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Pokud chcete aktualizovat tento klíč, určete **účel** šablony certifikátu (najdete ho na kartě **Vyřízení žádosti**). Potom aktualizujte odpovídající položku registru tak, že existující data nahradíte názvem šablony certifikátu (nikoli zobrazovaným názvem šablony), který jste určili v kroku 2. Následující tabulka mapuje účel šablony certifikátu na hodnoty v registru:

    |Účel šablony certifikátu (na kartě Vyřízení žádosti)|Upravovaná hodnota registru|Hodnota zobrazená v konzole pro správu Intune pro profil SCEP|
    |---|---|---|
    |Podpis|SignatureTemplate|Digitální podpis|
    |Šifrování|EncryptionTemplate|Šifrování klíče|
    |Podpis a šifrování|GeneralPurposeTemplate|Šifrování klíče<br/>Digitální podpis|

    Pokud je třeba účelem šablony certifikátu **Šifrování**, pak upravte hodnotu **EncryptionTemplate** , aby byla názvem vaší šablony certifikátu.

3. Server NDES získává dlouhé adresy URL (dotazy), které vyžadují, abyste přidali dvě položky registru:


   |                        Location                        |      Hodnota      | type  |      Data       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (desítkově) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (desítkově) |

4. Ve správci služby IIS vyberte **Výchozí web** > **Filtrování požadavků** > **Upravit nastavení funkce**. Změňte **maximální délku adresy URL** a **maximální řetězec dotazu** na *65534*, jak je znázorněno níže:

    ![Maximální délka dotazu a adresy URL ve službě IIS](./media/SCEP_IIS_max_URL.png)

5. Restartujte server. Nepoužívejte příkaz **iisreset**. Tento příkaz k dokončení těchto změn nestačí.
6. Přejděte do `http://*FQDN*/certsrv/mscep/mscep.dll`. Měla by se zobrazit stránka NDES podobná následující stránce:

    ![Test NDES](./media/SCEP_NDES_URL.png)

    Pokud se zobrazí **503 - Služba není k dispozici** , zkontrolujte prohlížeč událostí. Je pravděpodobné, že se fond aplikací zastavil kvůli chybějícímu oprávnění pro uživatele NDES. Tato práva jsou popsaná v kroku 1.

#### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Instalace a vytvoření vazby certifikátů na serveru NDES

1. Na serveru NDES vyžádejte a nainstalujte **ověřovací certifikát serveru** z vaší interní nebo veřejné certifikační autority. Pro tento certifikát SSL pak vytvoříte vazbu ve službě IIS.

    > [!TIP]
    > Po vytvoření vazby certifikátu SSL ve službě IIS nainstalujte certifikát pro ověřování klientů. Tento certifikát může být vydaný certifikační autoritou, která je důvěryhodná pro server NDES. Stejný certifikát lze použít, pokud tento certifikát obsahuje sadu použití klíče pro ověřování klienta a serveru (**rozšířené použití klíče**). Informace o těchto ověřovacích certifikátech najdete v následujících krocích.

   1. Jakmile získáte ověřovací certifikátu serverů, otevřete **Správce IIS** a vyberte **Výchozí web**. V podokně **Akce** vyberte **Vazby**.

   2. Vyberte **Přidat**, nastavte **Typ** na **https** a potom zkontrolujte, že port je **443**. Pro samostatnou službu Intune se podporuje jenom port 443.

   3. Jako **Certifikát SSL** zadejte ověřovací certifikát serverů.

      > [!NOTE]
      > Pokud server NDES používá pro jednu síťovou adresu externí a interní název, musí ověřovací certifikát serverů mít:
      > - **Název subjektu** s externím veřejným názvem serveru
      > - **Alternativní název subjektu**, který obsahuje interní název serveru

2. Na serveru NDES vyžádejte a nainstalujte certifikát pro **ověřování klientů** z vaší interní certifikační autority nebo z veřejné certifikační autority. Tento certifikát může být stejný jako ověřovací certifikát serverů, pokud má tento certifikát obě schopnosti.

    Certifikát pro ověřování klientů musí mít následující vlastnosti:

    - **Rozšířené použití klíče**: Tato hodnota musí zahrnovat **ověřování klientů** .

    - **Název předmětu**: Hodnota musí být stejná jako název DNS serveru, na který instalujete certifikát (Server NDES).

#### <a name="configure-iis-request-filtering"></a>Konfigurace filtrování požadavků služby IIS

1. Na serveru NDES otevřete **Správce služby IIS**, vyberte **Výchozí webový server** v podokně **Připojení** a pak otevřete **Filtrování požadavků**.

2. Vyberte **Upravit nastavení funkce**a pak nastavte tyto hodnoty:

    - **řetězec dotazu (bajty)**  = **65534**
    - **Maximální délka adresy URL (bajty)**  = **65534**

3. Zkontrolujte následující klíč registru:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Zkontrolujte, že následující hodnoty jsou nastavené jako položky DWORD:

    - Název: **MaxFieldLength**, s desetinnou hodnotou **65534**
    - Název: **MaxRequestBytes**, s desetinnou hodnotou **65534**

4. Restartujte server NDES. Server je teď připravený na podporu konektoru Certificate Connector.

### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Krok 5: Povolení, instalace a konfigurace Intune Certificate Connectoru
Činnosti uskutečněné v tomto kroku:

- Povolíte podporu NDES ve službě Intune.
- Stáhnete Certificate Connector a pak ho nainstalujete a nakonfigurujete na serveru, který je hostitelem role Služba zápisu síťových zařízení (NDES) ve vašem prostředí. Pokud chcete zvýšit škálování implementace NDES, můžete nainstalovat více serverů NDES s Microsoft Intune Certificate Connectorem.

#### <a name="download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace Certificate Connectoru

> [!IMPORTANT] 
> Microsoft Intune Certificate Connector **musí** být nainstalovaný na samostatném serveru Windows. Nemůžete ho nainstalovat na vystavující certifikační autoritu. **Musí** být také nainstalovaný na stejném serveru jako role Služba zápisu síťových zařízení (NDES).

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Konfigurace** > zařízení**certifikační konektory** > **Přidat**.
3. Stáhněte a uložte konektor pro soubor SCEP. Uložte ho do umístění přístupného ze serveru NDES, na který budete konektor instalovat.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)


4. Po dokončení stahování přejdete na server NDES, který je hostitelem služby zápisu síťových zařízení (NDES). Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework, protože ho vyžaduje NDES Certificate Connector. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Pro spuštění instalačního programu (**NDESConnectorSetup. exe**) použijte účet s právy správce k serveru. Tento instalační program nainstaluje taky modul zásad pro NDES a webovou službu CRP. Webová služba CRP, která má označení CertificateRegistrationSvc, běží ve službě IIS jako aplikace.

    > [!NOTE]
    > Při instalaci NDES pro samostatnou službu Intune se s konektorem Certificate Connector automaticky nainstaluje služba CRP. Při použití služby Intune se Správcem konfigurace nainstalujete bod registrace certifikátu (CRP) jako samostatnou roli serveru.

5. Pokud se zobrazí výzva k zadání klientského certifikátu pro konektor Certificate Connector, klikněte na **Vybrat** a vyberte certifikát pro **ověřování klientů**, který jste nainstalovali na server NDES v kroku 4.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, vyberte **Další** a zobrazte vlastnosti certifikátu. Vyberte **Další** a potom **Nainstalovat**.

    > [!IMPORTANT]
    > Konfigurace rozšířeného zabezpečení Internet Exploreru[ musí být na serveru NDES](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx), který hostuje Intune Certificate Connector, zakázaná.

6. Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP]
    > Pokud průvodce zavřete před spuštěním uživatelského rozhraní konektoru Certificate Connector, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > < install_Path > \NDESConnectorUI\NDESConnectorUI.exe

7. V uživatelském rozhraní **Certificate Connectoru** :

    Vyberte **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu. Až se přihlásíte, stáhne Intune Certificate Connector certifikát z Intune. Tento certifikát se používá k ověřování mezi konektorem a Intune.

    > [!IMPORTANT]
    > K uživatelskému účtu musí být přiřazená platná licence pro Intune. Pokud daný uživatelský účet nemá platnou licenci pro Intune, spuštění příkazu NDESConnectorUI.exe se nezdaří.

    Pokud vaše organizace používá proxy server a ten je vyžadovaný pro přístup serveru NDES k internetu, vyberte **Použít proxy server**. Pak zadejte název proxy serveru, port a přihlašovací údaje účtu pro připojení.

    Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě. Provedené změny **použijte**. Pokud jste toto oprávnění přidělili účtu služby NDES při [konfiguraci certifikační autority](#configure-the-certification-authority), zadejte tento účet zde. 

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

8. Otevřete příkazový řádek, zadejte **services.msc** a stiskněte **Enter**. Pravým tlačítkem myši klikněte na **Služba konektoru Intune** > **Restartovat**.

Pokud chcete ověřit, že je služba spuštěná, spusťte prohlížeč a zadejte následující adresu URL. Měla by vrátit chybu **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> NDES Certificate Connector podporuje také protokol TLS 1.2. Pokud server s nainstalovaným NDES Certificate Connectorem podporuje TLS 1.2, použije se TLS 1.2. Pokud server nepodporuje TLS 1.2, použije se TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

## <a name="create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu certifikátu SCEP.
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento certifikát SCEP. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 a novější**
   - **Windows 10 a novější**
5. V rozevíracím seznamu **Typ profilu** zvolte **Certifikát SCEP**.
6. Zadejte následující nastavení:

   - **Typ certifikátu**: Pro uživatelské certifikáty vyberte možnost **uživatel** . Typ **uživatelského** certifikátu může v předmětu a síti SAN certifikátu obsahovat atributy uživatele i zařízení.  Vyberte **zařízení** pro scénáře, jako jsou například zařízení bez uživatele, jako jsou veřejné terminály nebo pro zařízení s Windows, a umístěte certifikát do úložiště certifikátů místního počítače. Certifikáty **zařízení** mohou obsahovat pouze atributy zařízení v předmětu a San certifikátu.  Certifikáty **Zařízení** jsou dostupné pro tyto platformy:  
     - Android Enterprise – pracovní profil
     - iOS
     - macOS
     - Windows 8.1 a vyšší
     - Windows 10 a novější


   - **Formát názvu subjektu**: Vyberte, jak má Intune automaticky vytvořit název subjektu v žádosti o certifikát. Možnosti se změní, pokud vyberete typ certifikátu **Uživatel** nebo typ certifikátu **Zařízení**.  

     > [!NOTE]  
     > K dispozici je [známý problém](#avoid-certificate-signing-requests-with-escaped-special-characters) pro použití SCEP k získání certifikátů, když název subjektu v výsledné žádosti o podepsání certifikátu (CSR) obsahuje jeden z následujících znaků jako řídicí znak (pokračuje zpětným lomítkem \\):
     > - \+
     > - ;
     > - ,
     > - =

        **Typ uživatelského certifikátu**  

        Do názvu subjektu můžete zahrnout e-mailovou adresu uživatele. Vybírejte z těchto možností:

        - **Není nakonfigurováno**
        - **Běžný název**
        - **Běžný název včetně e-mailové adresy**
        - **Běžný název jako e-mail**
        - **IMEI (International Mobile Equipment Identity)**
        - **Sériové číslo**
        - **Vlastní**: Když vyberete tuto možnost, zobrazí se také **vlastní** textové pole. V tomto poli můžete zadat vlastní formát názvu subjektu, včetně proměnných. Vlastní formát podporuje dvě proměnné: **Běžný název (CN)** a **e-mail (e)** . **Běžný název (CN)** můžete nastavit na některou z těchto proměnných:

            - **CN={{UserName}}** : Hlavní název uživatele (UPN), napříkladjanedoe@contoso.com
            - **CN={{AAD_Device_ID}}** : ID přiřazené při registraci zařízení v Azure Active Directory (AD). Toto ID se obvykle používá k ověření ve službě Azure AD.
            - **CN={{SERIALNUMBER}}** : Jedinečné sériové číslo (SN) obvykle používané výrobcem k identifikaci zařízení
            - **CN={{IMEINumber}}** : Jedinečné číslo IMEI (International Mobile Equipment Identity) používané k identifikaci mobilního telefonu
            - **CN={{OnPrem_Distinguished_Name}}** : Posloupnost relativních rozlišujících názvů oddělených čárkou, například`CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

                Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, nezapomeňte synchronizovat atribut uživatele `onpremisesdistingishedname` pomocí služby [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

            - **CN={{onPremisesSamAccountName}}** : Správci mohou synchronizovat atribut samAccountName ze služby Active Directory do služby Azure AD pomocí služby Azure AD Connect do atributu `onPremisesSamAccountName`s názvem. Intune může tuto proměnnou nahradit v rámci žádosti o vystavení certifikátu v předmětu certifikátu SCEP.  Atribut samAccountName je přihlašovací jméno uživatele, které slouží pro podporu klientů a serverů z předchozí verze Windows (před Windows 2000). Formát přihlašovacího jména uživatele je: `DomainName\testUser` nebo jenom `testUser`.

                Pokud chcete použít proměnnou `{{onPremisesSamAccountName}}`, nezapomeňte synchronizovat atribut uživatele `onPremisesSamAccountName` pomocí služby [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

            Kombinací jedné nebo několika těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu, jako třeba:  

            **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

            V tomto příkladu jste vytvořili formát názvu subjektu, který kromě proměnných CN a E používá řetězce pro hodnoty organizační jednotky, organizace, umístění, stav a země/oblast. Článek [Funkce CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) popisuje tuto funkci a její podporované řetězce.

        **Typ certifikátu zařízení**  

        Když použijete typ certifikátu **Zařízení**, můžete také použít následující proměnné certifikátu zařízení pro hodnotu:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Tyto proměnné můžete přidat jako statický text do textového pole s vlastní hodnotou. Například běžný název můžete přidat jako `CN = {{DeviceName}}text`.

        > [!IMPORTANT]
        >  - Ve statickém textu subjektu se složené závorky **{}** , které neuzavírají proměnnou, vyhodnotí jako chyba. 
        >  - Když používáte proměnné certifikátu zařízení, uzavřete proměnnou do složených závorek **{ }** .
        >  - `{{FullyQualifiedDomainName}}` funguje jenom pro Windows a zařízení připojená k doméně. 
        >  - Když v subjektu nebo alternativním názvu subjektu (SAN) pro certifikát zařízení používáte vlastnosti zařízení, jako je IMEI, sériové číslo a plně kvalifikovaný název domény, uvědomte si, že osoba, která má k zařízení přístup, může tyto vlastnosti zfalšovat.
        >  - Pokud zadané proměnné zařízení nejsou podporované, profil se na zařízení nenainstaluje. Pokud se například v názvu subjektu profilu SCEP přiřazeného k zařízení, které nemá číslo IMEI, použije {{IMEI}}, instalace profilu se nezdaří. 


   - **Alternativní název subjektu**: Zadejte způsob, jakým Intune automaticky vytvoří hodnoty pro alternativní název subjektu (SAN) v žádosti o certifikát. Možnosti se změní, pokud vyberete typ certifikátu **Uživatel** nebo typ certifikátu **Zařízení**. 

        **Typ uživatelského certifikátu**  

        K dispozici jsou následující atributy:

        - E-mailová adresa
        - hlavní název uživatele (UPN)

            Pokud vyberete třeba uživatelský typ certifikátu, můžete do alternativního názvu subjektu zahrnout hlavní název uživatele (UPN). Pokud slouží klientský certifikát k ověřování na serveru NPS (Network Policy Server), nastavte pro alternativní název subjektu hodnotu UPN. 

        **Typ certifikátu zařízení**  

        Textové pole ve formátu tabulky, které můžete upravit. K dispozici jsou následující atributy:

        - DNS

        S typem certifikátu **Zařízení** můžete použít následující proměnné certifikátu zařízení pro hodnotu:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Tyto proměnné můžete přidat jako statický text do textového pole s vlastní hodnotou. Například atribut DNS můžete přidat jako `DNS name = {{AzureADDeviceId}}.domain.com`.

        > [!IMPORTANT]
        >  - Ve statickém textu alternativního názvu subjektu (SAN) nejdou použít složené závorky **{ }** , středníky **;** ani svislé čáry **|** . 
        >  - Když používáte proměnné certifikátu zařízení, uzavřete proměnnou do složených závorek **{ }** .
        >  - `{{FullyQualifiedDomainName}}` funguje jenom pro Windows a zařízení připojená k doméně. 
        >  - Když v subjektu nebo alternativním názvu subjektu (SAN) pro certifikát zařízení používáte vlastnosti zařízení, jako je IMEI, sériové číslo a plně kvalifikovaný název domény, uvědomte si, že osoba, která má k zařízení přístup, může tyto vlastnosti zfalšovat.
        >  - Pokud zadané proměnné zařízení nejsou podporované, profil se na zařízení nenainstaluje. Pokud se například v alternativním názvu subjektu profilu SCEP přiřazeného k zařízení, které nemá číslo IMEI, použije {{IMEI}}, instalace profilu se nezdaří.  

   - **Období platnosti certifikátu**: Pokud jste `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` příkaz spustili u vydávající certifikační autority, která umožňuje vlastní období platnosti, můžete zadat dobu zbývající do vypršení platnosti certifikátu.<br>Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vydávající CA. 
   - **Zprostředkovatel úložiště klíčů (KSP)** (Windows Phone 8,1, Windows 8.1, Windows 10): Zadejte, kam se má uložit klíč k certifikátu. Vyberte jednu z těchto hodnot:
     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), pokud existuje, jinak zapsat do softwarového KSP**
     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), jinak chyba**
     - **Zapsat do služby Passport, jinak chyba (Windows 10 a novější)**
     - **Zapsat do softwarového KSP**

   - **Použití klíče**: Zadejte možnosti použití klíče pro certifikát. Možnosti:
     - **Šifrování klíče**: Umožňuje výměnu klíče jenom v případě, že je klíč zašifrovaný.
     - **Digitální podpis**: Umožňuje výměnu klíče jenom v případě, že digitální podpis pomáhá chránit klíč.
   - **Velikost klíče (bity)** : Vyberte počet bitů obsažených v klíči.
   - **Algoritmus hash** (Android, Windows Phone 8,1, Windows 8.1, Windows 10): Vyberte jeden z dostupných typů hashovacího algoritmu, který chcete s tímto certifikátem použít. Vyberte nejsilnější úroveň zabezpečení, kterou připojované zařízení podporuje.
   - **Kořenový certifikát**: Vyberte [profil důvěryhodného kořenového certifikátu](certficates-pfx-configure.md#create-a-trusted-certificate-profile) , který jste vytvořili dříve, a přiřazený uživateli nebo zařízení. Tento certifikát certifikační autority musí být kořenovým certifikátem pro certifikační autoritu, která vydává certifikát konfigurovaný v tomto profilu. Nezapomeňte tento profil důvěryhodných kořenových certifikátů přiřadit ke stejné skupině, která je přiřazená v profilu certifikátu SCEP.
   - **Rozšířené použití klíče**: **Přidejte** hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje **Ověření klienta**, aby se mohl uživatel nebo zařízení ověřit na serveru. Můžete ale přidat jakákoli další použití klíče podle potřeby.
   - **Nastavení registrace**
     - **Prahová hodnota obnovení (%)** : Zadejte procento doby životnosti certifikátu zbývající v době, kdy zařízení požádá o obnovení certifikátu.
     - **Adresy URL serveru SCEP**: Zadejte jednu nebo více adres URL pro servery NDES, které vystavují certifikáty prostřednictvím SCEP. Zadejte například text podobný řetězci `https://ndes.contoso.com/certsrv/mscep/mscep.dll`.
     - Vyberte **OK** a **vytvořte** profil.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Vyhnout se žádostem o podepsání certifikátu pomocí řídicích speciálních znaků
Existuje známý problém pro žádosti certifikátu SCEP, které obsahují název subjektu (CN) s jedním nebo více následujícími speciálními znaky jako řídicí znak. Názvy subjektů, které obsahují jeden ze speciálních znaků jako znak řídicího znaku, mají za následek nesprávný název subjektu, který zase vede k selhání ověřování výzvou SCEP služby Intune a nevystavuje certifikát.  

Speciální znaky jsou:
- \+
- ,
- ;
- =

Pokud název předmětu obsahuje jeden ze speciálních znaků, použijte k vyřešení tohoto omezení jednu z následujících možností:  
- Zapouzdří hodnotu CN, která obsahuje speciální znak, s uvozovkami.  
- Odeberte speciální znak z hodnoty CN.  

Máte **například**název subjektu, který se zobrazí jako *testovací uživatel (TestCompany, LLC)* .  ZÁSTUPCE, který obsahuje CN s čárkou mezi *TestCompany* a *LLC* , představuje problém.  Problém se může vyhnout vložením nabídek kolem celé propojené sítě nebo odebráním čárky z *TestCompany* a *LLC*:
- **Přidat uvozovky**: *CN =* "testovací uživatel (TESTCOMPANY, LLC)", OU = USERACCOUNTS, DC = Corp, DC = contoso, DC = com *
- **Odeberte čárku**: *CN = testovací uživatel (TestCompany LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

 Pokusy o odložení čárky pomocí zpětného lomítka se však nezdaří s chybou v protokolech CRP:  
- **Řídicí čárka**: *CN = testovací uživatel (TestCompany\\, LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

Tato chyba se podobá následující chybě: 

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```



## <a name="assign-the-certificate-profile"></a>Přiřazení profilu certifikátu

Před přiřazením profilů certifikátů ke skupinám vezměte v úvahu následující:

- Při přiřazení profilů certifikátů ke skupinám se soubor certifikátu z profilu certifikátu důvěryhodné CA nainstaluje na zařízení. Zařízení profil certifikátu SCEP použije k vytvoření vlastní žádosti o certifikát.
- Profily certifikátů se nainstalují jenom na zařízení s tou platformou, kterou jste použili při vytváření profilu.
- Profily certifikátů můžete přiřadit ke kolekcím uživatelů nebo ke kolekcím zařízení.
- Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, přiřaďte profil certifikátu ke skupině uživatelů (ne zařízení). Pokud ho přiřadíte ke skupině zařízení, budete je muset před obdržením zásad plně zaregistrovat.
- I když se každý profil přiřazuje samostatně, je třeba přiřadit jak důvěryhodnou kořenovou certifikační autoritu, tak profil SCEP nebo PKCS. Jinak zásady certifikátu SCEP nebo PKCS nebudou fungovat.

    > [!NOTE]
    > Když je v zařízeních se systémem iOS přidružený profil certifikátu SCEP k dalšímu profilu, jako je například profil sítě Wi-Fi nebo VPN, zařízení obdrží certifikát pro každý z těchto dalších profilů. Výsledkem je, že zařízení s iOS má víc certifikátů dodaných žádostí o certifikát SCEP.  

- Pokud používáte spolusprávu pro Intune a Configuration Manager, v Configuration Manager s[nastavte posuvník úlohy](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) pro *zásady přístupu k prostředkům* na Intune nebo **pilotní Intune**. Toto nastavení umožňuje klientům Windows 10 zahájit proces vyžádání certifikátu.  

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
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Certifikát ověřování klienta Symantec se v místním úložišti certifikátů nenašel. Další informace najdete v článku [Nastavení Intune Certificate Connectoru pro platformu DIGICERT PKI](https://docs.microsoft.com/intune/certificates-digicert-configure#troubleshooting) .  |
| 0x00000402 | RevokeCert_AccessDenied  | Zadaný účet nemá oprávnění k odvolání certifikátu z certifikační autority. V podrobnostech zprávy o události vyhledejte pole Název certifikační autority, abyste zjistili vydávající certifikační autoritu.  |
| 0x00000403 | CertThumbprint_NotFound  | Certifikát odpovídající vašemu vstupu se nepodařilo najít. Zaregistrujte si Certificate Connector a zkuste to znovu. |
| 0x00000404 | Certificate_NotFound  | Certifikát odpovídající zadanému vstupu se nepodařilo najít. Zaregistrujte si znovu Certificate Connector a zkuste to znovu. |
| 0x00000405 | Certificate_Expired  | Platnost certifikátu vypršela. Zaregistrujte si znovu Certificate Connector, aby se certifikát obnovil, a zkuste to znovu. |
| 0x00000408 | CRPSCEPCert_NotFound  | Certifikát šifrování CRP se nepodařilo najít. Ověřte správné nastavení NDES a konektoru Intune. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Podpisový certifikát se nepodařilo načíst. Ověřte, že je služba konektoru Intune správně nakonfigurovaná a že je spuštěná. Ověřte také, že se úspěšně dokončily události stažení certifikátu. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Žádost ověřovacího testu SCEP se nepodařilo deserializovat. Ověřte správné nastavení NDES a konektoru Intune. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Žádost se zamítla kvůli vypršení platnosti ověřovacího testu certifikátu. Po načtení nového ověřovacího testu ze serveru pro správu může klientské zařízení pokus opakovat. |
| 0x0FFFFFFFF | Unknown_Error  | Vaši žádost nemůžeme dokončit, protože došlo k chybě na straně serveru. Zkuste to prosím znovu. |

## <a name="next-steps"></a>Další postup

- [Použití certifikátů PKCS](certficates-pfx-configure.md)nebo [vydávání certifikátů PKCS z webové služby správce infrastruktury veřejných klíčů Symantec](certificates-symantec-configure.md)
- [Přidání CA třetí strany pro použití SCEP s Intune](certificate-authority-add-scep-overview.md)
- Další pomoc získáte pomocí následujících průvodců:
  - [Řešení potíží s nasazením profilu certifikátu SCEP v Microsoft Intune](https://support.microsoft.com/help/4457481)
  - [Řešení potíží s konfigurací NDES pro použití s Microsoft Intune profily certifikátů](https://support.microsoft.com/help/4459540)
