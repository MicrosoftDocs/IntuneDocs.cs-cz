---
title: Konfigurace infrastruktury certifikátů pro PFX
description: Vytvoření a nasazení profilů certifikátů .PFX
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/17/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a19dbd6ad2b65e7d2d090b543f3e2200180c660a
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="configure-certificate-infrastructure"></a>Konfigurace infrastruktury certifikátu

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje, co potřebujete k vytvoření a nasazení profilů certifikátů .PFX.

Pokud chcete v rámci své organizace používat ověření na základě certifikátů, potřebujete certifikační autoritu organizace.

Pokud chcete používat profily certifikátů .PFX, kromě certifikační autority organizace budete potřebovat ještě tyto položky:

-   Počítač, který může komunikovat s certifikační autoritou, nebo použijte přímo počítač certifikační autority.

-  Intune Certificate Connector běžící na počítači, který může komunikovat se službou certifikační autority

## <a name="on-premises-infrastructure-description"></a>Popis místní infrastruktury


-    **Doména služby Active Directory**: Všechny servery uvedené v této části (s výjimkou proxy serveru webové aplikace) musí být připojené k vaší doméně služby Active Directory.

-  **Certifikační autorita**: Certifikační autorita organizace (CA), která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novější. Samostatná certifikační autorita není podporovaná. Návod, jak nastavit certifikační autoritu, najdete v tématu [Instalace certifikační autority](http://technet.microsoft.com/library/jj125375.aspx).
    Pokud certifikační autorita používá Windows Server 2008 R2, musíte [instalovat opravu hotfix z KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Počítač, který může komunikovat s certifikační autoritou**: Můžete taky použít přímo počítač certifikační autority.
-  **Microsoft Intune Certificate Connector**: Prostřednictvím konzoly pro správu Intune můžete stáhnout instalační program konektoru **Certificate Connector** (**ndesconnectorssetup.exe**). Pak můžete soubor **ndesconnectorssetup.exe** spustit na počítači, kde chcete konektor Certificate Connector nainstalovat. V případě profilů certifikátů .PFX nainstalujte Certificate Connector v počítači, který komunikuje s certifikační autoritou.
-  **Proxy server webových aplikací** (volitelné): Jako proxy server služby Proxy webových aplikací (WAP) můžete použít server se systémem Windows Server 2012 R2 nebo novějším. Tato konfigurace:
    -  Umožňuje zařízením získat certifikáty pomocí připojení k internetu.
    -  Je doporučeným zabezpečením v případě, že se zařízení připojují prostřednictvím internetu za účelem příjmu a obnovení certifikátů.

 > [!NOTE]           
> -    Server, který je hostitelem WAP, [musí nainstalovat aktualizaci](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umožňující podporu dlouhých adres URL, které používá služba zápisu síťových zařízení (NDES). Tato aktualizace je součástí [kumulativní aktualizace z prosince 2014](http://support.microsoft.com/kb/3013769)nebo jde instalovat jednotlivě z [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Server hostující službu WAP musí mít také certifikát SSL odpovídající názvu publikovanému do externích klientů a musí důvěřovat certifikátu SSL, který se používá na serveru NDES. Tyto certifikáty umožňují serveru WAP ukončit připojení protokolem SSL od klientů a vytvořit nové připojení SSL k serveru NDES.
    Informace o certifikátech pro službu WAP najdete v části **Plánování certifikátů** tématu [Plánování publikování aplikací pomocí serveru proxy webových aplikací](https://technet.microsoft.com/library/dn383650.aspx). Obecné informace o serverech WAP najdete v tématu [Práce se serverem proxy webových aplikací](http://technet.microsoft.com/library/dn584113.aspx).|


### <a name="certificates-and-templates"></a>Certifikáty a šablony

|Objekt|Podrobnosti|
|----------|-----------|
|**Šablona certifikátu**|Tuto šablonu konfigurujete na své vydávající certifikační autoritě.|
|**Certifikát důvěryhodné kořenové certifikační autority**|Ten exportujete jako soubor **.cer** z vydávající certifikační autority nebo jakéhokoli zařízení, které důvěřuje vydávající certifikační autoritě, a nasadíte ho do zařízení pomocí profilu certifikátu důvěryhodné certifikační autority.<br /><br />Použijete jeden certifikát důvěryhodné kořenové certifikační autority na každou platformu operačního systému a přidružíte ho ke každému profilu důvěryhodného kořenového certifikátu, který vytvoříte.<br /><br />Pokud potřebujete, můžete vytvořit další certifikáty důvěryhodné kořenové certifikační autority. Můžete to třeba udělat, abyste vytvořili vztah důvěryhodnosti k certifikační autoritě, která podepisuje ověřovací certifikáty serverů pro vaše přístupové body Wi-Fi.|


## <a name="configure-your-infrastructure"></a>Konfigurace infrastruktury
Než budete moci konfigurovat profily certifikátů, je třeba provést následující úlohy. Tyto úlohy vyžadují znalost systému Windows Server 2012 R2 a ADCS (Active Directory Certificate Services):

- **Úloha 1**: Konfigurace šablon certifikátů v certifikační autoritě.
- **Úloha 2**ovolení, instalace a konfigurace Certificate Connectoru Intune.

### <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>Úloha 1 – konfigurace šablon certifikátů v certifikační autoritě
V této úloze budete publikovat šablonu certifikátu.

##### <a name="to-configure-the-certification-authority"></a>Konfigurace certifikační autority

1.  Ve vydávající certifikační autoritě vytvořte novou vlastní šablonu pomocí modulu snap-in Šablony certifikátů, nebo zkopírujte a upravte některou z existujících šablon (například šablona Uživatel) pro použití s .PFX.

    Šablona musí obsahovat následující vlastnosti:

    -   Zadejte popisný **zobrazovaný název šablony** .

    -   Na kartě **Název subjektu** vyberte možnost **Dodán v žádosti**. 

    -   Na kartě **Rozšíření** zkontrolujte, jestli **Popis zásad použití** obsahuje **Ověření klienta**.

        > [!IMPORTANT]
        > V případě šablon certifikátů pro iOS a Mac OS X na kartě **Rozšíření** upravte **Použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu** .

2.  Zkontrolujte **Období platnosti** na kartě **Obecné** šablony. Ve výchozím nastavení Intune používá hodnotu nakonfigurovanou v šabloně. Máte ale možnost konfigurovat, aby certifikační autorita žadateli umožňovala určit jinou hodnotu, kterou pak můžete nastavit v konzole pro správu Intune. Pokud chcete vždy používat hodnotu v šabloně, zbývající část tohoto kroku přeskočte.

    > [!IMPORTANT]
    > Platformy iOS a Mac OS X vždycky používají hodnotu nastavenou v šabloně bez ohledu na ostatní konfigurace, které provedete.

    Pokud chcete certifikační autoritu konfigurovat, aby žadateli umožňovala určit dobu platnosti, spusťte v certifikační autoritě následující příkazy:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Ve vydávající certifikační autoritě použijte modul snap-in Certifikační autorita k publikování šablony certifikátu.

    a.  Vyberte uzel **Šablony certifikátů**, klikněte na **Akce**-&gt; **Nové** &gt; **Vystavovaná šablona certifikátu** a potom vyberte šablonu, kterou jste vytvořili v kroku 2.

    b.  Ověřte, že je šablona publikovaná, jejím zobrazením ve složce **Šablony certifikátů** .

4.  Na počítači certifikační autority (CA) zkontrolujte, zda počítač, který je hostitelem Certificate Connectoru Intune, má oprávnění k registraci. Tím bude mít přístup k šabloně použité při vytváření profilu .PFX. Nastavte tato oprávnění na kartě **Zabezpečení** vlastností počítače certifikační autority.

### <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>Úloha 2 – Povolení, instalace a konfigurace Intune Certificate Connectoru
V této úloze:

Stažení, instalace a konfigurace Certificate Connectoru.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Povolení podpory pro Certificate Connector

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a zvolte **Správce** &gt; **Certificate Connector**.

2.  Zvolte možnost **Konfigurace místního Certificate Connectoru**.

3.  Vyberte **Zapnout Certificate Connector**a potom zvolte **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace Certificate Connectoru

1.  Otevřete [konzolu správce Intune](https://manage.microsoft.com) a zvolte **Správce** &gt; **Správa mobilních zařízení** &gt; **Certificate Connector** &gt; **Stáhnout Certificate Connector**.

2.  Po dokončení stahování spusťte stažený instalační program (**ndesconnectorssetup.exe**).

  Spusťte instalační program na počítači, který se bude moct připojit k certifikační autoritě. Zvolte distribuci .PFX a zvolte **Nainstalovat**. Po dokončení instalace pokračujte vytvořením profilu certifikátu podle popisu v části [Konfigurace profilů certifikátů](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  Pokud budete vyzváni k zadání klientského certifikátu pro Certificate Connector, zvolte **Vybrat**a vyberte certifikát pro **ověřování klientů**, který jste nainstalovali v úloze 3.

    Po vybrání certifikátu pro ověřování klientů se vrátíte na plochu **Klientský certifikát pro konektor Certificate Connector služby Microsoft Intune** . I když vybraný certifikát není zobrazený, zvolte **Další**. Zobrazí se vlastnosti certifikátu. Zvolte možnost **Další** a potom **Nainstalovat**.

4.  Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

    > [!TIP]
    > Pokud průvodce zavřete před spuštěním uživatelského rozhraní konektoru Certificate Connector, můžete ho znovu otevřít spuštěním následujícího příkazu:
    >
    > **&lt;cesta_k_instalaci&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  V uživatelském rozhraní **Certificate Connectoru** :

    a. Vyberte možnost **Přihlásit** a zadejte své přihlašovací údaje správce služby Intune nebo přihlašovací údaje správce klienta s oprávněním pro globální správu.

    b. Vyberte kartu **Upřesnit** a pak zadejte přihlašovací údaje pro účet, který má oprávnění **vydávat a spravovat certifikáty** ve vaší vydávající certifikační autoritě.

    c. Zvolte **Použít**.

    Teď můžete zavřít uživatelského rozhraní Certificate Connectoru.

6.  Otevřete příkazový řádek a zadejte **services.msc**. Stiskněte klávesu **Enter**, klikněte pravým tlačítkem myši na **službu konektoru Intune** a zvolte **Restartovat**.


### <a name="next-steps"></a>Další kroky
Teď jste připravení nastavit profily certifikátů podle návodu v tématu [Konfigurace profilů certifikátu](Configure-Intune-certificate-profiles.md).
