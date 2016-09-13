---
title: "Nastavení zásad dodržování předpisů pro zařízení s iOS | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b6a5e2435a3cdffeaf27b0045dee9b8263cdc7a
ms.openlocfilehash: 1e2dc1e94870bb53143bee62ccc9696a28285987


---


# Nastavení zásad dodržování předpisů pro zařízení s iOS v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení s iOS 6 nebo novějším.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s Androidem](android-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systémové nastavení zabezpečení
### Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení. Zařízení s iOS, která používají heslo, jsou zašifrovaná.

- **Povolit jednoduchá hesla:** Pokud tuto možnost nastavíte na **Ano**, umožníte uživatelům vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla:** Určuje, jestli musí uživatelé vytvořit heslo typu **Alfanumerický**, nebo **Číslo**.

- **Minimální počet znakových sad:** Pokud nastavíte **Požadovaný typ hesla** na možnost **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla

  Pokud se v tomto nastavení nastaví větší číslo, uživatelé budou muset vytvářet složitější hesla.

  Pro zařízení s iOS toto nastavení znamená počet speciálních znaků (třeba **!**, **#**, **&amp;**), které musí heslo obsahovat.
- **Počet minut nečinnosti před vyžádáním hesla:** Určete dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

### E-mailový profil
- **E-mailový účet se musí spravovat přes Intune:** Pokud je tato možnost nastavená na hodnotu **Ano**, zařízení musí používat e-mail nedodržující předpisy nasazený do zařízení. Zařízení je považováno za nedodržující předpisy v následujících situacích:
  - E-mailový profil musí být také nasazený na stejnou skupinu uživatelů, jako je skupina uživatelů, která je cílem zásady dodržování předpisů, jinak budou zařízení uživatelů považována za nedodržující předpisy.
  - Zařízení se hlásí jako nedodržující předpisy, pokud uživatel na zařízení už nastavil e-mailový účet, který se shoduje s e-mailovým profilem Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem zřízený profil, a proto ho nemůže ani spravovat. Aby zařízení dodržovalo předpisy, uživatel musí odstranit existující nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.


- **Vyberte e-mailový profil, který se musí spravovat přes Intune:**
   Pokud je vybraná možnost **E-mailový účet se musí spravovat přes Intune**, klikněte na **Vybrat** a zvolte e-mailový profil Intune. Tento e-mailový profil musí být na zařízení.

     Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Nastavení stavu zařízení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.

##  Vlastnosti zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom by měl mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.



<!--HONumber=Aug16_HO5-->


