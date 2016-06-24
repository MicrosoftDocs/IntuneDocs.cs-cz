---
# required metadata

title: Konfigurace infrastruktury certifikátu | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurace infrastruktury certifikátu
Toto téma popisuje, co potřebujete k vytvoření a nasazení profilů certifikátů.

Pokud chcete v rámci své organizace používat ověření na základě certifikátů, potřebujete certifikační autoritu organizace.

Pokud chcete používat profily certifikátů SCEP, kromě certifikační autority organizace budete potřebovat ještě tyto položky:

-   Server, na kterém běží služba zápisu síťových zařízení

-   Intune Certificate Connector, který se instaluje na Windows Server 2012 R2, na kterém běží NDES

Pokud chcete používat profily certifikátů .PFX, kromě certifikační autority organizace budete potřebovat ještě tyto položky:

-  Počítač, který může komunikovat s certifikační autoritou, nebo použijte přímo počítač certifikační autority.

-  Intune Certificate Connector běžící na počítači, který může komunikovat se službou certifikační autority

## Místní infrastruktura


-    **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

-  **Certifikační autorita** (CA): Označuje se jako vydávající certifikační autorita. Musíte mít certifikační autoritu organizace, která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novějšího. Samostatná certifikační autorita není podporovaná. Návod, jak nastavit certifikační autoritu, najdete v tématu [Instalace certifikační autority](http://technet.microsoft.com/library/jj125375.aspx).
    Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Server NDES** (jenom SCEP): Na serveru, na kterém běží Windows Server 2012 R2 nebo novější, musíte nastavit službu zápisu síťových zařízení (NDES). Intune nepodporuje používání služby zápisu síťových zařízení, pokud běží na serveru, na kterém běží taky certifikační autorita organizace. Pokyny k tomu, jak konfigurovat Windows Server 2012 R2 k hostování služby zápisu síťových zařízení, najdete v tématu [Příručka ke Službě zápisu síťových zařízení](http://technet.microsoft.com/library/hh831498.aspx).
-  **Počítač, který může komunikovat s certifikační autoritou** (jenom .PFX): Můžete taky použít přímo počítač certifikační autority.
-  **Microsoft Intune Certificate Connector**: Prostřednictvím konzoly pro správu Intune můžete stáhnout instalační program konektoru **Certificate Connector** (**ndesconnectorssetup.exe**). Pak můžete soubor **ndesconnectorssetup.exe** spustit na počítači, kde chcete konektor Certificate Connector nainstalovat. V případě profilů certifikátů .PFX nainstalujte Certificate Connector v počítači, který komunikuje s certifikační autoritou.
-  **Proxy server webových aplikací** (volitelné): Jako proxy server služby Proxy webových aplikací (WAP) můžete použít server se systémem Windows Server 2012 R2 nebo novějším. Tato konfigurace:
    -  Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
    -  Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.

> [!NOTE]           
> -    Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení. Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](http://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Server hostující službu WAP musí mít také certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.
Informace o certifikátech pro službu WAP najdete v části **Plánování certifikátů** tématu [Plánování publikování aplikací pomocí serveru proxy webových aplikací](https://technet.microsoft.com/library/dn383650.aspx). Obecné informace o serverech WAP najdete v tématu [Práce se serverem proxy webových aplikací](http://technet.microsoft.com/library/dn584113.aspx).|


### Certifikáty a šablony

|Objekt|Podrobnosti|
|----------|-----------|
|**Šablona certifikátu**|Tuto šablonu konfigurujete na své vydávající certifikační autoritě.|
|**Certifikát pro ověřování klientů**|Tento certifikát vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte na server NDES.|
|**Ověřovací certifikát serverů**|Tento certifikát SSL vyžádaný z vaší vydávající certifikační autority nebo veřejné certifikační autority nainstalujte a připojte ve službě IIS na serveru NDES.|
|**Certifikát důvěryhodné kořenové certifikační autority**|Ten exportujete jako soubor **.cer** z vydávající certifikační autority nebo jakéhokoli zařízení, které důvěřuje vydávající certifikační autoritě, a nasadíte ho do zařízení pomocí profilu certifikátu důvěryhodné certifikační autority.<br /><br />Použijete jeden certifikát důvěryhodné kořenové certifikační autority na každou platformu operačního systému a přidružíte ho ke každému profilu důvěryhodného kořenového certifikátu, který vytvoříte.<br /><br />Pokud potřebujete, můžete vytvořit další certifikáty důvěryhodné kořenové certifikační autority. Můžete to třeba udělat, abyste vytvořili vztah důvěryhodnosti k certifikační autoritě, která podepisuje ověřovací certifikáty serverů pro vaše přístupové body Wi-Fi.|

### Účty

|Název|Podrobnosti|
|--------|-----------|
|**Účet služby NDES**|Zadáte účet uživatele domény, který chcete použít jako účet služby NDES.|

## Konfigurace infrastruktury
Před konfigurací profilů certifikátů musíte provést následující úlohy, které vyžadují znalosti systému Windows Server 2012 R2 a služby AD CD (Active Directory Certificate Services):

**Úloha 1** – konfigurace šablon certifikátů v certifikační autoritě

**Úloha 2**, jenom pro profil SCEP – konfigurace požadavků na serveru NDES

**Úloha 3**, jenom pro profil SCEP – konfigurace NDES pro použití s Intune

**Úloha 4** – povolení, instalace a konfigurace konektoru Intune Certificate Connector

## Úloha 1 – konfigurace šablon certifikátů v certifikační autoritě
V této úloze:

-   Vytvoříte účet služby NDES

    > [!NOTE] K odvolání certifikátů vyžaduje účet služby NDES oprávnění *Vydávat a spravovat certifikáty* ke každé šabloně certifikátu používané profilem certifikátu.

-   Konfigurujete šablonu certifikátu pro NDES

-   Publikujete šablonu certifikátu pro NDES

##### Konfigurace certifikační autority

1.  Vytvořte účet uživatele domény, který chcete použít jako účet služby NDES. Tento účet zadáte při konfiguraci šablon ve vydávající certifikační autoritě před instalací a konfigurací NDES.

2.  Ve vydávající certifikační autoritě použijte modul snap-in Šablony certifikátů k vytvoření nové vlastní šablony nebo zkopírování existující šablony a následnému upravení existující šablony (jako je šablona Uživatel) pro použití s NDES.

    Šablona musí obsahovat následující konfigurace:

    -   Zadejte popisný **zobrazovaný název šablony** .

    -   Na kartě **Název subjektu** vyberte možnost **Dodán v žádosti**. (Zabezpečení je vynucené modulem zásad Intune pro NDES).

    -   Na kartě **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

        > [!IMPORTANT] V případě šablon certifikátů pro iOS a Mac OS X na kartě **Rozšíření** upravte **Použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu**.

    -   Na kartě **Zabezpečení** přidejte účet služby NDES a poskytněte šabloně oprávnění k **zápisu**.

3.  Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Máte ale možnost konfigurovat, aby certifikační autorita žadateli umožňovala určit jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

    > [!IMPORTANT] Platformy iOS a Mac OS X vždycky používají hodnotu nastavenou v šabloně bez ohledu na ostatní konfigurace, které provedete.

    Pokud chcete certifikační autoritu konfigurovat, aby žadateli umožňovala určit dobu platnosti, spusťte v certifikační autoritě následující příkazy:

    1.  **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Ve vydávající certifikační autoritě použijte modul snap-in Certifikační autorita k publikování šablony certifikátu.

    1.  Vyberte uzel **Šablony certifikátů**, klikněte na **Akce**-&gt;**Nové**&gt;**Vystavovaná šablona certifikátu** a potom vyberte šablonu, kterou jste vytvořili v kroku 2.

    2.  Ověřte, že je šablona publikovaná, jejím zobrazením ve složce **Šablony certifikátů** .

5.  Pro profily .PFX: Na počítači certifikační autority (CA) zkontrolujte, že má počítač, který je hostitelem Certificate Connectoru, oprávnění k registraci, aby měl přístup k šabloně použité při vytváření profilu .PFX. Nastavte tato oprávnění na kartě **Zabezpečení** vlastností počítače certifikační autority.

## Úloha 2 (jenom profil SCEP) – Konfigurace požadavků na serveru NDES
V této úloze:

-   Přidáte NDES do Windows Serveru a konfigurujete službu IIS pro podporu NDES

-   Přidáte účet služby NDES do skupiny IIS_IUSR

-   Nastavíte hlavní název služby (SPN) pro účet služby NDES

##### Konfigurace požadavků pro server NDES

1.  Na serveru, který bude hostitelem NDES, se musíte přihlásit jako **Správce podnikové sítě**a potom pomocí [Průvodce přidáním rolí a funkcí](https://technet.microsoft.com/library/hh831809.aspx) instalovat NDES:

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

3.  Spusťte následující příkaz pro nastavení hlavního názvu služby (SPN) účtu služby NDES:

    -   **setspn -s http/&lt;název DNS serveru NDES&gt; &lt;název domény&gt;\&lt;název účtu služby NDES&gt;**

    Například pokud je název serveru NDES **Server01**, vaše doména je **Contoso.com**a účet služby je **NDESService**, použijte:

    -   **setspn – s http/Server01.contoso.com contoso\NDESService**

## Úloha 3 (jenom profil SCEP) – konfigurace NDES pro použití s Microsoft Intune 
V této úloze:

-   Nakonfigurujete NDES pro použití s vydávající certifikační autoritou

-   Vytvoříte vazbu certifikátu serveru ověřování (SSL) ve službě IIS

-   Konfigurujete filtrování požadavků ve službě IIS

##### Konfigurace NDES pro použití se službou Intune

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

3.  Po úpravě registru spusťte na serveru **iisreset** , abyste server přinutili načíst nedávné změny konfigurace.

##### Instalace a vytvoření vazby certifikátů na serveru NDES

1.  Na serveru NDES vyžádejte a nainstalujte **ověřovací certifikát serveru** z vaší interní nebo veřejné certifikační autority. Pro tento certifikát SSL pak vytvoříte vazbu ve službě IIS.

    > [!TIP]
    > Po vytvoření vazby certifikátu SSL ve službě IIS nainstalujete taky certifikát pro ověřování klientů. Tento certifikát může být vydaný certifikační autoritou, která je důvěryhodná pro server NDES. I když se nejedná o osvědčený postup, můžete použít stejný certifikát pro ověřování serverů i klientů, pokud má obě rozšířená použití klíče (EKU). Informace o těchto ověřovacích certifikátech najdete v následujících krocích.

    1.  Po obdržení ověřovacího certifikátu serverů otevřete **Správce služby IIS**, vyberte **Výchozí webový server** v podokně **Připojení** a pak klikněte na **Vazby** v podokně **Akce** .

    2.  Klikněte na **Přidat**, nastavte **Typ** na **https**a pak se ujistěte, že port je **443**. (Pro samostatnou službu Intune je podporovaný jenom port 443).

    3.  Jako **Certifikát SSL**zadejte ověřovací certifikát serverů.

        > [!NOTE] Pokud server NDES používá externí i interní název pro jednu síťovou adresu, musí mít ověřovací certifikát serverů nastavený **Název subjektu** s názvem externího veřejného serveru a **Alternativní název subjektu**, který obsahuje název interního serveru.

2.  Na serveru NDES vyžádejte a nainstalujte certifikát pro **ověřování klientů** z vaší interní certifikační autority nebo z veřejné certifikační autority. Může to být stejný certifikát jako ověřovací certifikát serverů, pokud má tento certifikát obě schopnosti.

    Certifikát pro ověřování klientů musí mít následující vlastnosti:

    **Rozšířené použití klíče** – musí zahrnovat **Ověření klienta**.

    **Název subjektu** – musí být stejný jako název DNS serveru, na který instalujete certifikát (server NDES).

##### Konfigurace filtrování požadavků služby IIS

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

## Úloha 4 – Povolení, instalace a konfigurace Intune Certificate Connectoru – pro certifikáty SCEP a .PFX
V této úloze:

Povolíte podporu NDES ve službě Intune

Stáhnete, nainstalujete a nakonfigurujete konektor Certificate Connector na serveru NDES.

##### Povolení podpory pro Certificate Connector

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a klikněte na **Správce** &gt; **Certificate Connector**.

2.  Klikněte na **Konfigurace místního Certificate Connectoru**.

3.  Vyberte **Zapnout Certificate Connector**a potom klikněte na **OK**.

##### Stažení, instalace a konfigurace konektoru Certificate Connector

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a potom klikněte na **Správce** &gt; **Správa mobilních zařízení** &gt; **Certificate Connector** &gt; **Stáhnout Certificate Connector**.

2.  Po dokončení stahování spusťte stažený instalační program (**ndesconnectorssetup.exe**):

    -   Pro certifikáty .PFX spusťte instalační program na počítači, který se bude moct připojit k certifikační autoritě. Zvolte distribuci .PFX a klikněte na Nainstalovat. Po dokončení instalace pokračujte vytvořením profilu certifikátu podle popisu v části [Konfigurace profilů certifikátů](configure-intune-certificate-profiles.md).

    -   Pro certifikáty SCEP spusťte instalační program na Windows Serveru 2012 R2.

    Pro možnost SCEP instalační program nainstaluje také modul zásad pro NDES a webovou službu CRP. (Webová služba CRP, CertificateRegistrationSvc, běží ve službě ve službě IIS jako aplikace).

    > [!NOTE]
    > Při instalaci NDES pro samostatnou službu Intune se s konektorem Certificate Connector automaticky nainstaluje služba CRP. Při použití služby Intune se Správcem konfigurace nainstalujete bod registrace certifikátu (CRP) jako samostatnou roli serveru.

3.  Pokud budete vyzváni k zadání klientského certifikátu pro konektor Certificate Connector, klikněte na **Vybrat**a vyberte certifikát pro **ověřování klientů** , který jste nainstalovali na server NDES v úloze 3.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, kliknutím na **Další** zobrazte vlastnosti certifikátu. Pak klikněte na **Další**a pak klikněte na **Nainstalovat**.

4.  Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP] Pokud průvodce zavřete před spuštěním uživatelského rozhraní Certificate Connectoru, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > **&lt;cesta_k_instalaci&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  V uživatelském rozhraní **Certificate Connectoru** :

    Klikněte na **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu.

    Pokud vaše organizace používá proxy server a ten je vyžadovaný pro přístup serveru NDES k internetu, klikněte na **Použít proxy server** a potom zadejte název proxy serveru, port a přihlašovací údaje účtu pro připojení.

    Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **Vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě, a pak klikněte na **Použít**.

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

6.  Otevřete příkazový řádek, zadejte **services.msc** a potom stiskněte **Enter**, klikněte pravým tlačítkem na **Intune Certificate Connector** a nakonec klikněte na **Restartovat**.

Pokud chcete ověřit, jestli je služba spuštěná, spusťte prohlížeč a zadejte následující adresu URL, která by měla vrátit chybu **403** :

**http:// &lt;Název_FQDN_serveru_NDES&gt;/certsrv/mscep/mscep.dll**

### Další kroky
Teď jste připravení konfigurovat profily certifikátů podle návodu v tématu [Konfigurace profilů certifikátů](configure-intune-certificate-profiles.md).


<!--HONumber=Jun16_HO1-->


