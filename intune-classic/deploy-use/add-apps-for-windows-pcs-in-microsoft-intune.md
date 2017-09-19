---
title: "Přidání aplikací pro počítače s Windows, na kterých běží softwarový klient Intune"
description: "V tomto tématu se dozvíte, jak přidat do Intune aplikace pro počítače s Windows před tím, než je nasadíte."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4f198026e5ea7a8c2cadd894e49292ace4eeac06
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Přidání aplikací pro počítače s Windows, na kterých běží softwarový klient Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V tomto tématu se dozvíte, jak přidat do Intune aplikace před tím, než je nasadíte.

> [!IMPORTANT]
> Informace v tomto tématu vám pomůžou přidat aplikace pro počítače s Windows, které spravujete pomocí softwarového klienta Intune. Pokud chcete aplikace přidávat do zaregistrovaných počítačů s Windows nebo do jiných mobilních zařízení, přečtěte si téma [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

Abyste mohli aplikace do počítačů instalovat, musí podporovat bezobslužnou instalaci – bez zásahu uživatele. Pokud tomu tak není, instalace se nezdaří.


## <a name="add-the-app"></a>Přidání aplikace
Pomocí Vydavatele softwaru Microsoft Intune nakonfigurujete vlastnosti aplikace a odešlete ji do svého cloudového úložiště. K tomu slouží tento postup:

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Aplikace** &gt; **Přidat aplikace**. Spustí se Vydavatel softwaru Intune.

    > [!TIP]
    > Před spuštěním vydavatele softwaru možná budete muset zadat svoje uživatelské jméno a heslo k Intune.

2.  Na stránce **Instalace softwaru** vydavatele v části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení** zvolte **Instalační program softwaru** a pak určete jednu z těchto možností:

    - **Vyberte typ souboru instalačního programu softwaru**. Označuje typ softwaru, který chcete nasadit. U počítačů s Windows zvolte **Instalační služba systému Windows**.
    - **Zadejte umístění instalačních souborů softwaru**. Zadejte umístění instalačních souborů, nebo zvolte **Procházet** a vyberte umístění ze seznamu.
    - **Zahrnout další soubory a podsložky ze stejné složky**. Software, který používá Instalační službu systému Windows, někdy potřebuje podpůrné soubory. Ty musí být umístěné ve stejné složce jako instalační soubor. Tuto možnost vyberte, když chcete nasadit i podpůrné soubory.

    Pokud třeba chcete publikovat aplikaci s názvem Application.msi do Intune, stránka bude vypadat takto: ![Stránka instalace softwaru vydavatele](./media/publisher-for-pc.png)

   U tohoto typu instalace se využívá část prostoru cloudového úložiště.

3.  Na stránce **Popis softwaru** nakonfigurujte následující nastavení.

    > [!NOTE]
    > Některé hodnoty můžou být vyplněné automaticky nebo se nemusí zobrazit. Záleží na používaném instalačním souboru.

    - **Vydavatel**. Zadejte název vydavatele aplikace.
    - **Název**. Zadejte název aplikace, který se zobrazí na portálu společnosti.<br />Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis**. Zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
    - **Adresa URL informací o softwaru** (volitelné). Můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL zásad ochrany osobních údajů** (volitelné). Můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Kategorie** (volitelné). Vyberte jednu z předdefinovaných kategorií aplikací. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Ikona** (volitelné). Nahrajte ikonu, která bude k aplikaci přidružená. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.

4.  Na stránce **Požadavky** vyberte požadavky, které je potřeba splnit, aby bylo možné aplikaci nainstalovat. Vybírejte z těchto možností:

    - **Architektura**. Vyberte, do jakých systémů je možné aplikaci instalovat: 32bitové, 64bitové nebo obojí.
    - **Operační systém**. Vyberte minimální verzi operačního systému, který umožňuje aplikaci nainstalovat.

5.  Na stránce **Pravidla detekce** můžete nakonfigurovat pravidla, která zjistí, jestli už je konfigurovaná aplikace na počítači nainstalovaná. Nebo můžete použít výchozí pravidla detekce k automatickému přepsání dříve nainstalovaných verzí aplikace. Tato možnost se týká Instalační služby systému Windows (jenom soubory .exe).

    Jaká pravidla můžete konfigurovat:
    - **Soubor existuje**. Zadejte cestu k souboru, který chcete zjistit. Můžete hledat ve složce **%ProgramFiles%** (prohledá složku **Program Files**\&lt;cesta&gt; a **Program Files (x86)**\&lt;cesta&gt;) na počítači nebo ve složce **%SystemDrive%** (prohledá kořenovou jednotku počítače, většinou je to jednotka C:).
    - **Kód produktu MSI existuje**. Pokud chcete vybrat soubor Instalační služby systému Windows (.msi), který chcete detekovat, vyberte **Procházet**.
    - **Klíč registru existuje**. Zadejte klíč registru, který začíná **HKEY_LOCAL_MACHINE\**. Prohledají se 32bitové i 64bitové cesty registru. Pokud zadaný klíč v některém umístění existuje, pravidlo detekce je splněné.

    Pokud aplikace odpovídá některému z nakonfigurovaných pravidel, nebude se instalovat.

6.  Platí jen pro typ souboru **Instalační služba systému Windows** (.msi a .exe): Na stránce **Argumenty příkazového řádku** můžete vybrat, jestli chcete instalačnímu programu poskytnout volitelné argumenty příkazového řádku.
    Intune automaticky přidá tyto parametry:
    - Pro soubory .exe se přidá parametr **/install**.
    - Pro soubory .msi se přidá parametr **/quiet**.
    Pamatujte na to, že tyto možnosti budou fungovat jenom v případě, že to povolil tvůrce balíčku aplikace.

7.  Platí jen pro typ souboru **Instalační služba systému Windows** (jenom .exe): Na stránce **Návratové kódy** můžete přidat nové chybové kódy, které Intune dokáže interpretovat při instalaci aplikace na spravovaný počítač s Windows.

    Ve výchozím nastavení Intune používá standardní návratové kódy, kterými oznamuje úspěch nebo selhání instalace balíčku aplikace: **0** (úspěch) nebo **3010** (úspěch s restartem). Do seznamu taky můžete přidat vlastní návratové kódy. Pokud zadáte seznam návratových kódů a instalace aplikace vrátí kód, který v seznamu není, interpretuje se to jako selhání instalace.

8.  Na stránce **Shrnutí** zkontrolujte zadané informace. Až budete připravení, zvolte **Odeslat**.

9. Postup dokončíte výběrem možnosti **Zavřít**.

Aplikace se zobrazí v uzlu **Aplikace** v pracovním prostoru **Aplikace**.

## <a name="next-steps"></a>Další kroky

Dalším krokem po vytvoření aplikace je její nasazení. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps.md).

Různé tipy a triky pro nasazení softwaru na počítače s Windows najdete v blogovém příspěvku [Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/) (Tip pro podporu: Osvědčené postupy distribuce softwaru na počítače pomocí Intune).
