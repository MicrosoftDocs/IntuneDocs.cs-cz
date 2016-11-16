---
title: "Nastavení zásad dodržování předpisů pro zařízení s Androidem | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad dodržování předpisů pro zařízení s Androidem."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 30fae0cc2e9b3b08f9195c2622b0daec639e0d62
ms.openlocfilehash: 20f61b9dec289252797650e7ef40ff4c5b7c0fbc


---


# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Nastavení zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení se systémem Android 4.0 a novějším nebo Samsung KNOX Standard 4.0 a novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOSem](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

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

- **Zakázat opakované použití předchozích hesel:** Pokud jste zvolili možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení použijte v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se uživatelům zobrazí výzva k zadání hesla.

### <a name="encryption"></a>Šifrování
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby musela být zařízení vyžadující přístup k prostředkům šifrovaná. Zařízení se šifrují, pokud vyberete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.

## <a name="device-health-and-security-settings"></a>Stav zařízení a nastavení zabezpečení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.
- **Požadovat, aby zařízení bránila instalaci aplikací z neznámých zdrojů (Android 4.0 nebo novější):** Pokud chcete blokovat zařízení, která mají povolenou možnost **Zabezpečení** > **Neznámé zdroje**, toto nastavení povolte a nastavte ho na **Ano**.  
>[!IMPORTANT]
>Aplikace instalované bokem vyžadují, aby bylo nastavení **Neznámé zdroje** povolené. Tuto zásadu dodržování předpisů vynuťte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Požadovat, aby ladění USB bylo zakázané (Android 4.2 nebo novější):** Toto nastavení určuje, jestli se má zjišťovat, zda je na zařízení povolená možnost ladění USB.
- **Požadovat, aby zařízení měla povolené nastavení Vyhledat v zařízení bezpečnostní hrozby (Android 4.2-4.4):** Toto nastavení určuje, že je v zařízení povolená funkce **Ověřovat aplikace**.
- **Minimální úroveň oprav zabezpečení Androidu (Android 6.0 nebo novější):** Toto nastavení použijte k určení minimální úrovně oprav Androidu. Zařízení, která nejsou alespoň na této úrovni oprav, budou kompatibilní. Datum musí být zadané ve formátu RRRR-MM-DD.
- **Vyžadovat, aby byla povolena Ochrana zařízení před internetovými útoky**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte jednu z následujících úrovní hrozeb jako maximální povolenou:

  - **Žádná (zabezpečeno)**: Toto je nejbezpečnější úroveň. Znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud se v zařízení zjistí libovolná úroveň hrozeb, bude vyhodnoceno jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká**: Jedná se o nejméně bezpečnou možnost. V podstatě umožňuje všechny úrovně hrozeb. Může se hodit, pokud toto řešení používáte jenom ke generování sestav.

  Další podrobnosti najdete v tématu [Povolení pravidla ochrany zařízení před hrozbami v zásadách dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
  Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidlech, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.



<!--HONumber=Nov16_HO1-->


