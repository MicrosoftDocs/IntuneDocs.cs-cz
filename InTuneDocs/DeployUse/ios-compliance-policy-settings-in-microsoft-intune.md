---
title: "Nastavení zásad dodržování předpisů pro zařízení s iOS | Microsoft Intune"
description: "Toto téma popisuje pravidla a nastavení, která můžete použít v zásadách dodržování předpisů pro zařízení s iOS."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8cde3ffb3be8656d5f256e16eb71ed4aaa7ceb5b
ms.openlocfilehash: 37f8d9a2d3057df4f7e8d105e48d75edd6d77dc4


---


# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení zásad dodržování předpisů pro zařízení s iOS v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení s iOSem 8.0 nebo novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s Androidem](android-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro Android for Work](afw-compliance-policy-settings-in-microsoft-intune)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení
### <a name="password"></a>Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, bude uživatel muset zadat heslo, aby mohli získat přístup ke svému zařízení. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.

- **Povolit jednoduchá hesla**: Pokud tuto možnost nastavíte na **Ano**, umožníte uživateli vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

- **Vyžadovaný typ hesla:** Určuje, jestli musí uživatel vytvořit **Alfanumerické** nebo **Číselné** heslo.

- **Minimální počet znakových sad:** Pokud nastavíte **Požadovaný typ hesla** na možnost **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo mít. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla

  Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

  Pro zařízení s iOS toto nastavení znamená počet speciálních znaků (třeba **!**, **#**, **&amp;**), které musí heslo obsahovat.

- **Počet minut nečinnosti před vyžádáním hesla**: Určete dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel**: Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud jste zvolili možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo**: Toto nastavení použijte v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se uživatelům zobrazí výzva k zadání hesla.

### <a name="email-profile"></a>e-mailový profil
- **E-mailový účet se musí spravovat přes Intune**: Pokud je tato možnost nastavená na hodnotu **Ano**, zařízení musí používat e-mailový profil nasazený na zařízení. Zařízení je považováno za nedodržující předpisy v následujících situacích:
  - E-mailový profil je nasazený do jiné skupiny uživatelů, než je ta, která cílí na zásady dodržování předpisů.
  - Uživatel na zařízení už nastavil e-mailový účet, který se shoduje s e-mailovým profilem služby Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem zřízený profil, a proto ho nemůže ani spravovat. Aby zařízení dodržovalo předpisy, musí uživatel odebrat stávající nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.

- **Vyberte e-mailový profil, který se musí spravovat přes Intune**: Pokud je vybraná možnost **E-mailový účet se musí spravovat přes Intune**, zvolte **Vybrat** a nastavte e-mailový profil Intune. Tento e-mailový profil musí být na zařízení.

     Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="device-health-settings"></a>Nastavení stavu zařízení

- **Zařízení nesmí mít jailbreak ani root**: Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.

##  <a name="device-properties"></a>Vlastnosti zařízení
- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel může zvolit upgrade svého zařízení. Pak může přistupovat k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.



<!--HONumber=Nov16_HO2-->


