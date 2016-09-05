---
title: "Nastavení zásad dodržování předpisů pro zařízení s Androidem | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad dodržování předpisů pro zařízení s Androidem."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: f99158924b83254efedb8663b9d6175a6b6775b1


---


# Nastavení zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení se systémem Android 4.0 a novějším nebo Samsung KNOX 4.0 a novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systémové nastavení zabezpečení
### Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

- **Kvalita hesla:** Toto nastavení zapněte, pokud chcete konfigurovat požadavky na heslo pro zařízení s Androidem. Vybírejte z těchto možností:
  -   **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  -   **Aspoň číselné**
  -   **Aspoň abecední**
  -   **Aspoň alfanumerické**
  -   **Alfanumerické se symboly**

- **Počet minut nečinnosti, než se požaduje heslo:** Určuje dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

### Šifrování
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby musela být zařízení vyžadující přístup k prostředkům šifrovaná. Zařízení se šifrují, pokud nakonfigurujete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.

## Stav zařízení a nastavení zabezpečení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.
- **Požadovat, aby zařízení bránila instalaci aplikací z neznámých zdrojů (Android 4.0 nebo novější):** Pokud chcete blokovat zařízení, která mají povolenou možnost **Zabezpečení > Neznámé zdroje**, toto nastavení povolte a nastavte ho na **Ano**.  
>[!IMPORTANT]
>Zkušební načtení aplikací vyžaduje, aby bylo nastavení **Neznámé zdroje** povolené.  Tuto zásadu dodržování předpisů byste měl vynucovat, jenom když na zařízeních neprovádíte zkušební načtení aplikací pro Android.

- **Požadovat, aby ladění USB bylo zakázané (Android 4.2 nebo novější):** Toto nastavení určuje, jestli se má zjišťovat, zda je na zařízení povolená možnost ladění USB.
- **Požadovat, aby zařízení měla povolené nastavení Vyhledat v zařízení bezpečnostní hrozby (Android 4.2-4.4):** Toto nastavení určuje, že je v zařízení povolená funkce **Ověřovat aplikace**.
- **Minimální úroveň oprav zabezpečení Androidu (Android 6.0 nebo novější):** Toto nastavení použijte k určení minimální úrovně oprav Androidu.  Zařízení, která nejsou alespoň na této úrovni oprav, budou kompatibilní. Datum musí být zadáno ve formátu RRRR-MM-DD.


## Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
  Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.



<!--HONumber=Jul16_HO5-->


