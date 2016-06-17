---
# required metadata

title: Nastavení zásad dodržování předpisů pro zařízení s Androidem | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Nastavení zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení se systémem Android 4.0 a novějším nebo Samsung KNOX 4.0 a novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Nastavení zabezpečení systému
### Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli
  získat přístup ke svému zařízení.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

- **Kvalita hesla:** Toto nastavení zapněte, pokud chcete konfigurovat požadavky na heslo pro zařízení s Androidem. Vybírejte z těchto možností:
  -   **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  -   **Aspoň číselné**
  -   **Aspoň abecední**
  -   **Aspoň alfanumerické**
  -   **Alfanumerické se symboly**

- **Počet minut nečinnosti, než se požaduje heslo:** Určuje dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší
  a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Toto nastavení použijte spolu s nastavením **Zakázat opakované použití předchozích hesel**,
  pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív.

- **Zakázat opakované použití předchozích hesel:** Pokud jste vybrali možnost **Pamatovat si historii hesel**, zadejte
  počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:**
  Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení
  **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

### Encryption
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby musela být zařízení
  před připojením k prostředkům šifrovaná. Zařízení
  se šifrují, pokud nakonfigurujete nastavení **Vyžadovat heslo k
  odemknutí mobilních zařízení**..

## Nastavení stavu zařízení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení,
  zařízení s jailbreakem budou vyhodnocena jako nedodržující předpisy.

## Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému,
  nahlásí se jako nevyhovující.
  Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá
  verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.


<!--HONumber=May16_HO1-->


