---
title: "Postup resetování hesla z webu Portál společnosti | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1d9321838cdf7721410a1ba204dd02bd868dcd72
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Resetování hesla zařízení z webu Portál společnosti

Pokud ztratíte kód PIN nebo heslo zařízení, které jste zaregistrovali v Intune, můžete použít [web Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog) k jeho resetování. Web Portál společnosti se používá ke správě počítačů a zařízení, které jste zaregistrovali v Intune, a k plnění většinou stejných úkolů jako v aplikaci Portál společnosti.

> [!NOTE]
> Je možné, že na webu Portál společnosti neuvidíte tlačítko Resetovat heslo, pokud používáte zařízení zaregistrované společností. Pokud ho nevidíte, budete muset kontaktovat svou firemní podporu, aby heslo resetovala za vás.

Resetování hesla:

1.  Na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog) klepněte na tlačítko __nabídky__ ![Malý obrázek tlačítka nabídky, tři vodorovné pruhy nad sebou](/intune/media/CP_hamburger_menu.png) a potom vyberte __Moje zařízení__.

2. Na stránce __Moje zařízení__ vyberte název zařízení, jehož heslo chcete resetovat.

  ![Snímek obrazovky se stránkou Moje zařízení s několika neidentifikovanými zařízeními zobrazenými nad výzvou k registraci zařízení, která nejsou v seznamu, nebo k identifikaci neidentifikovaných zařízení](./media/macOS_enroll_002_tap_here_banner.png)

3.  Zařízení se otevře v místním okně. Vyberte tlačítko **Resetovat heslo**.

    ![Všechny možnosti pro vybrané zařízení na webu Portál společnosti, včetně možnosti Přejmenovat, Odebrat, Resetovat zařízení, Resetovat heslo a Vzdálené uzamčení ](./media/iwp-screen-with-all-options.png)

4.  Zobrazí se informační zpráva s výzvou, abyste potvrdili, že chcete resetovat heslo, a s informacemi o tom, že po resetování hesla budete ze svého zařízení odhlášeni. Potom budete muset 5 minut počkat, než se budete moct znovu přihlásit.

  ![Informační zpráva s upozorněním týkajícím se resetování hesla zařízení a odhlášení uživatele Tlačítka pro vstup uživatele jsou Odhlásit se a Zrušit.](./media/iwp-reset-passcode-popup.png)

5.  Vyberte možnost **Odhlásit se** a zobrazí se závěrečná zpráva s informacemi o odebrání hesla ze zařízení. Pokud zařízení nemáte s sebou, neodebírejte heslo, protože by se mohlo stát, že kdokoli by měl k zařízení fyzický přístup, měl by přístup k většině osobních i firemních informací, které jsou v něm uložené. 

  ![Druhá informační zpráva s upozorněním týkajícím se resetování hesla zařízení a odebrání hesla ze zařízení. Obsahuje také informace o tom, jak nastavit nové heslo prostřednictvím nastavení zařízení.](./media/iwp-reset-passcode-2nd-popup.png)

  Různá zařízení mají různé typy hesel.

  **Android**: Odebere existující heslo a vytvoří dočasné heslo obsahující písmena i číslice. 
  
  > [!NOTE]
  > U hesel pro zařízení s Androidem 7.0 nebo novějším hesla resetovat nemůžete. Pokud heslo zapomenete, musíte na zařízení obnovit tovární nastavení.

  **iOS**: Odebere existující heslo a nevytvoří dočasné heslo. Pokud pro otevírání zařízení nebo nákupy používáte snímač otisku prstu Touch ID, budete si ho muset nastavit znovu.

  **Windows 10 Mobile**: Odebere existující heslo a vytvoří dočasné heslo obsahující písmena i číslice. Pokud k přihlášení používáte rozpoznávání obličeje Windows Hello, bude tato technologie i nadále podporovaná.
    
  **Windows Phone 8.1**: Odebere existující heslo a vytvoří dočasné heslo obsahující číslice.

  U zařízení s Androidem nebo s Windows se v části **Detaily o zařízení** zobrazí dočasné heslo. 

6.  Odemkněte zařízení a nastavte nové heslo, nebo změňte dočasné heslo pomocí nabídky **Nastavení** v zařízení.

Pokud chcete zobrazit potvrzení, že bylo heslo úspěšně resetované, klikněte na příznak oznámení v pravé horní části webu Portál společnosti.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
