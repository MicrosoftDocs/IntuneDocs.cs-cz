---
title: "Nastavení zásad dodržování předpisů pro Android"
description: "Toto téma popisuje nastavení zásad dodržování předpisů pro zařízení s Androidem."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f781c5498a569a067f0f2aa6f780a6cc37c9985c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Nastavení zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nastavení zásad popsané v tomto tématu se týká zařízení se systémem Android 4.0 a novějším nebo Samsung KNOX 4.0 a novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOSem](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení
### <a name="password"></a>Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

- **Kvalita hesla:** Toto nastavení rozpozná, jestli jsou na zařízení nastavené požadavky na heslo, které jste zadali. Toto nastavení povolte, pokud uživatelé musí pro zařízení s Androidem splnit určité požadavky na heslo. Vybírejte z těchto možností:

  -   **Biometrika s nízkým zabezpečením**
  -   **Požadováno**
  -   **Aspoň číslice**
  -   **Aspoň abecední znaky**
  -   **Aspoň alfanumerické znaky**
  -   **Alfanumerické znaky se symboly**

- **Počet minut nečinnosti před vyžádáním hesla:** Určete dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Zadejte počet předchozích hesel, která se nesmí znovu použít (pokud je zvolená možnost **Pamatovat si historii hesel**).

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení použijte v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Při přístupu k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se uživatelům zobrazí výzva k zadání hesla.

### <a name="encryption"></a>Šifrování
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby přístup k prostředkům měla jenom šifrovaná zařízení. Zařízení se šifrují, pokud nakonfigurujete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.

## <a name="device-health-and-security-settings"></a>Stav zařízení a nastavení zabezpečení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující.
- **Požadovat, aby zařízení bránila instalaci aplikací z neznámých zdrojů (Android 4.0 nebo novější):** Pokud chcete blokovat zařízení, která mají povolenou možnost **Zabezpečení > Neznámé zdroje**, povolte toto nastavení a nastavte ho na **Ano**.  

>[!IMPORTANT]
>Zkušební načtení aplikací vyžaduje, aby bylo nastavení **Neznámé zdroje** povolené. Tuto zásadu dodržování předpisů vynuťte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Požadovat, aby ladění USB bylo zakázané (Android 4.2 nebo novější):** Určete, jestli se má zjišťovat, zda je na zařízení povolená možnost ladění USB.
- **Požadovat, aby zařízení měla povolené nastavení Vyhledat v zařízení bezpečnostní hrozby (Android 4.2–4.4):** Určete, že na zařízení má být povolená funkce **Ověřovat aplikace**.
- **Minimální úroveň oprav zabezpečení Androidu (Android 6.0 nebo novější):** Určete minimální úroveň oprav Androidu.  Zařízení, která nejsou alespoň na této úrovni oprav, budou nevyhovující. Datum je nutné zadat v tomto formátu: RRRR-MM-DD.
- **Vyžadovat, aby byla povolena Ochrana zařízení před internetovými útoky**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte jednu z následujících úrovní hrozeb jako maximální povolenou:

  - **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň. Znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud se v zařízení zjistí nějaké hrozby, vyhodnotí se jako nevyhovující.
  - **Nízká:** Zařízení se vyhodnotí jako vyhovující, pokud se v něm nachází jen hrozby nízké úrovně. Jakákoliv vyšší úroveň zařadí zařízení do nevyhovujícího stavu.
  - **Střední:** Zařízení se vyhodnotí jako vyhovující, pokud se v něm nachází hrozby střední nebo nízké úrovně. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.
  - **Vysoká:** Jedná se o nejméně bezpečnou možnost. V podstatě povoluje všechny úrovně hrozeb. Toto řešení může být užitečné prakticky jen pro účely nahlašování.

  Další podrobnosti najdete v článku [Vytváření zásad dodržování předpisů zařízení pro Lookout ve službě Intune](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nevyhovující.
  Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se neprovede změna pravidla, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.
