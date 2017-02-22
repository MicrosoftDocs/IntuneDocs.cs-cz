---
title: "Jak konfigurovat certifikáty pomocí Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se pomocí Intune vytvářet a přiřazovat certifikáty, které vám pomůžou zabezpečit Wi-Fi, VPN a další připojení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: a0183f2a170ed458b19c7688b20ee5ba5c2c696e


---

# <a name="how-to-configure-certificates-with-intune-azure-preview"></a>Jak konfigurovat certifikáty pomocí Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Když uživatelům poskytnete přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, můžete tento přístup zabezpečit pomocí certifikátu, který je nainstalovaný na všech uživatelských zařízeních. Pracovní postup je ve stručnosti následující:

1. Zajistěte, abyste měli připravenou správnou infrastrukturu certifikátů. Můžete použít [certifikáty SCEP](configure-certificate-infrastructure-for-scep.md) a [certifikáty PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. K tomuto účelu vytvořte a přiřaďte **profil důvěryhodného certifikátu**. Po přiřazení tohoto profilu budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu budete muset vytvořit samostatný profil. Profily důvěryhodného certifikátu jsou dostupné pro tyto platformy:
    - iOS 8.0 a novější
    - macOS 10.9 a novější
    - Android 4.0 a novější <!--Android for Work --->
    - Windows 8.1 a novější
    - Windows Phone 8.1 a novější
    - Windows 10 a novější
3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu. Pro zařízení s následujícími platformami můžete vytvořit a nasadit profil certifikátu **PKCS** nebo **SCEP**:
    - iOS 8.0 a novější
    - Android 4.0 a novější
    - Android for Work
    - Windows 10 (desktopové a mobilní) a novější

    Pro zařízení s následujícími platformami můžete použít jenom profil certifikátu SCEP:

-   macOS 10.9 a novější
-   Windows Phone 8.1 a novější

Pro každou platformu zařízení musíte vytvořit samostatný profil. Při vytváření profil přidružíte k profilu důvěryhodného kořenového certifikátu, který jste vytvořili dříve.

### <a name="further-considerations"></a>Další pravidla

- Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
- Pokud se na základě platforem zařízení rozhodnete použít profil SCEP (Simplified Certificate Enrollment Protocol), musíte taky nakonfigurovat server Služby zápisu síťových zařízení (NDES).
- Bez ohledu na to, jestli plánujete používat profily SCEP nebo PKCS, si musíte stáhnout a nakonfigurovat Microsoft Intune Certificate Connector.

## <a name="before-you-start"></a>Než začnete


### <a name="if-you-want-to-use-scep-certificates"></a>Pokud chcete používat certifikáty SCEP

Zajistěte splnění nezbytných požadavků pro [infrastrukturu certifikátů pro SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### <a name="if-you-want-to-use-pkcs-certificates"></a>Pokud chcete používat certifikáty PKCS

Zajistěte splnění nezbytných požadavků pro [infrastrukturu certifikátů pro PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Úloha 1: Export certifikátu důvěryhodné kořenové certifikační autority
Exportujte certifikát důvěryhodné kořenové certifikační autority jako soubor **.cer** z vydávající certifikační autority nebo z jakéhokoli zařízení, které vaší vydávající certifikační agentuře důvěřuje. Privátní klíč neexportujte.

Tento certifikát budete importovat při nastavování profilu důvěryhodného certifikátu.

## <a name="task-2-create-trusted-certificate-profiles"></a>Úloha 2: Vytvoření profilů důvěryhodných certifikátů
Před vytvořením profilu certifikátu SCEP nebo PKCS musíte vytvořit profil důvěryhodného certifikátu. Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo PKCS pro každou platformu zařízení.

### <a name="to-create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** profilu důvěryhodného certifikátu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento důvěryhodný certifikát. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Důvěryhodný certifikát**.
7. Procházením vyhledejte certifikát, který jste si uložili v rámci úlohy 1, a pak klikněte na **OK**.
8. Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:
    - **Úložiště počítačových certifikátů – kořenové**
    - **Úložiště počítačových certifikátů – zprostředkující**
    - **Úložiště uživatelských certifikátů – zprostředkující**
8. Až to budete mít, zvolte **OK**, vraťte se do okna **Vytvořit profil** a zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).


> [!Note]
> Na zařízeních s Androidem se zobrazí oznámení o tom, že třetí strana nainstalovala důvěryhodný certifikát.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Úloha 3: Vytvoření profilů certifikátů SCEP nebo PKCS
Po vytvoření profilu důvěryhodného certifikátu vytvořte profily certifikátů SCEP nebo PKCS pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP musíte zadat profil důvěryhodného certifikátu pro stejnou platformu. Tím se oba profily certifikátů propojí, ale přesto musíte každý profil přiřadit samostatně.

### <a name="to-create-an-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1. Na portálu Azure Portal vyberte úlohu **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** profilu certifikátu SCEP.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento certifikát SCEP. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Certifikát SCEP**.
7. V okně **Certifikát SCEP** nakonfigurujte následující nastavení:
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
    - **Alternativní název subjektu** – Určete způsob, jak má Intune automaticky vytvořit hodnoty pro alternativní název subjektu (SAN) v žádosti o certifikát. Pokud jste zvolili třeba uživatelský typ certifikátu, můžete do alternativního názvu subjektu zahrnout hlavní název uživatele (UPN). Pokud bude klientský certifikát sloužit k ověřování na server NPS (Network Policy Server), musíte alternativní název subjektu nastavit na UPN. 
    - **Použití klíče** – Zadejte možnosti použití klíče pro certifikát. Vybírat můžete z těchto možností: 
        - **Šifrování klíče** – Umožňuje výměnu klíče jenom v případě, že je klíč zašifrovaný. 
        - **Digitální podpis** – Umožňuje výměnu klíče jenom v případě, že se k ochraně klíče využívá digitální podpis. 
    - **Velikost klíče (bity)** – Vyberte počet bitů, které bude klíč obsahovat. 
    - **Algoritmus hash** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) – Vyberte jeden z dostupných typů algoritmu hash, který chcete s tímto certifikátem použít. Vyberte nejsilnější úroveň zabezpečení, kterou připojované zařízení podporuje. 
    - **Kořenový certifikát** – Zvolte profil certifikátu kořenové CA, který jste nakonfigurovali a přiřadili pro uživatele nebo zařízení. Tento certifikát certifikační autority musí být kořenovým certifikátem pro certifikační autoritu, která vydává certifikát konfigurovaný v tomto profilu. 
    - **Rozšířené použití klíče** – Zvolte **Přidat** a přidejte hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje **Ověření klienta**, aby se mohl uživatel nebo zařízení ověřit na serveru. Můžete ale přidat jakákoli další použití klíče podle potřeby. 
    - **Nastavení registrace**
        - **Prahová hodnota obnovení (%)** – Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
        - **Serverové adresy URL pro SCEP** – Zadejte jednu nebo více adres URL pro servery NDES, které budou vystavovat certifikáty prostřednictvím SCEP. 
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

Pokud chcete konfigurovat nastavení profilu certifikátu SCEP, postupujte podle pokynů na stránce konfigurace profilu.
>[!Note]
> Jenom pro zařízení s iOSem: V části Formát názvu subjektu můžete vybrat Vlastní a zadat vlastní formát názvu subjektu.
> Dvě proměnné, které jsou aktuálně podporované pro vlastní formát, jsou **Common Name (CN)** a **Email (E)**. Pomocí kombinace těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu jako například tento: **CN={{UserName}},E={{EmailAddress}},OU=Mobilni,O=Finance,L=Brno,C=CZ**. V tomto příkladu jste vytvořili formát názvu subjektu, který kromě proměnných CN a E využívá řetězce pro organizační jednotku, organizaci, umístění a zemi. V [tomto tématu](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) si můžete přečíst další informace o funkci **CertStrToName** a jejích podporovaných řetězcích.


### <a name="to-create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

Na portálu Azure Portal vyberte úlohu **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** vyberte **Spravovat** > **Profily**.
3. V okně s profily zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** profilu certifikátu PKCS.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento certifikát PKCS z těchto možností:
    - **Android**
    - **iOS**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Certifikát PKCS**.
7. V okně **Certifikát PKCS** nakonfigurujte následující nastavení:
    - **Prahová hodnota obnovení (%)** – Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
    - **Období platnosti certifikátu** – Pokud jste na vydávající CA spustili příkaz **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**, který umožňuje nastavit vlastní období platnosti, můžete zadat dobu zbývající do vypršení platnosti certifikátu.<br>Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vydávající CA.
    - **Zprostředkovatel úložiště klíčů (KSP)** (Windows 10)
    - **Certifikační autorita** -
    - **Název certifikační autority** -
    - **Název šablony certifikátu** – Zadejte název šablony certifikátu, kterou má Služba zápisu síťových zařízení používat a která byla přidaná k vydávající CA.
    Dbejte na to, aby název přesně odpovídal některé ze šablon certifikátů obsažených v registru serveru, kde je spuštěná Služba zápisu síťových zařízení. Zadat musíte název šablony certifikátu, a ne její zobrazované jméno. 
    Názvy šablon certifikátů můžete najít v tomto klíči: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Šablony certifikátů se zobrazí jako hodnoty položek **EncryptionTemplate**, **GeneralPurposeTemplate**a **SignatureTemplate**. Výchozí hodnota všech tří šablon certifikátů je IPSECIntermediateOffline a je namapovaná na zobrazovaný název šablony **IPSec (žádost offline)**. 
    - **Formát názvu subjektu** – Ze seznamu vyberte způsob, jak má Intune automaticky vytvořit název subjektu v žádosti o certifikát. Pokud je certifikát určený pro uživatele, můžete do názvu subjektu zahrnout taky e-mailovou adresu uživatele. Vybírejte z těchto možností:
        - **Není nakonfigurováno**
        - **Běžný název**
        - **Běžný název včetně e-mailové adresy**
        - **Běžný název jako e-mail**
    - **Alternativní název subjektu** – Určete způsob, jak má Intune automaticky vytvořit hodnoty pro alternativní název subjektu (SAN) v žádosti o certifikát. Pokud jste zvolili třeba uživatelský typ certifikátu, můžete do alternativního názvu subjektu zahrnout hlavní název uživatele (UPN). Pokud bude klientský certifikát sloužit k ověřování na server NPS (Network Policy Server), musíte alternativní název subjektu nastavit na UPN.
    - **Rozšířené použití klíče** (Android) – Zvolte **Přidat** a přidejte hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje **Ověření klienta** , aby se mohl uživatel nebo zařízení ověřit na serveru. Můžete ale přidat jakákoli další použití klíče podle potřeby. 
    - **Kořenový certifikát** (Android) – Zvolte profil certifikátu kořenové CA, který jste nakonfigurovali a přiřadili pro uživatele nebo zařízení. Tento certifikát certifikační autority musí být kořenovým certifikátem pro certifikační autoritu, která vydává certifikát konfigurovaný v tomto profilu.
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

## <a name="task-4-assign-certificate-profiles"></a>Úloha 4: Přiřazení profilů certifikátů

Před přiřazením profilů certifikátů ke skupinám vezměte v úvahu následující:

- Při přiřazení profilů certifikátů ke skupinám se soubor certifikátu z profilu certifikátu důvěryhodné CA nainstaluje na zařízení. Zařízení profil certifikátu SCEP nebo PKCS použije k vytvoření vlastní žádosti o certifikát.
- Profily certifikátů se nainstalují jenom na zařízení s tou platformou, kterou jste použili při vytváření profilu.
- Profily certifikátů můžete nasadit do kolekce uživatelů nebo do kolekce zařízení.
- Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, nasaďte profil certifikátu do skupinu uživatelů (ne zařízení). Pokud ho nasadíte do skupiny zařízení, budete je muset před obdržením zásad plně zaregistrovat.
- I když se každý profil nasazuje samostatně, je třeba nasadit jak důvěryhodnou kořenovou certifikační autoritu, tak profil SCEP nebo PKCS. Jinak zásady certifikátu SCEP nebo PKCS nebudou fungovat.

## <a name="next-steps"></a>Další kroky
Obecné informace o tom, jak přiřadit profily zařízení, najdete v tématu [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).



<!--HONumber=Feb17_HO1-->


