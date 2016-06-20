---
# required metadata

title: Reset hesla zařízení z webu portálu společnosti | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Reset hesla zařízení z webu portálu společnosti

Pokud ztratíte kód PIN nebo heslo zařízení, které jste zaregistrovali v Intune, můžete použít [web portálu společnosti](http://portal.manage.microsoft.com) k jeho resetování. Web portálu společnosti je webová stránka, kterou můžete použít ke správě počítačů a zařízení, které jste registrovali v Intune, a k provádění většiny úloh, které můžete provádět pomocí aplikace Portál společnosti.

> [!NOTE] 
> V závislosti na tom, jak váš správce Intune konfiguroval Intune, se na webu portálu společnosti nemusí tlačítko Resetovat heslo zobrazit. Restování hesla není podporované u zařízení s Windows 8.1 a Windows RT.

Resetování hesla:

1.  Otevřete [web portálu společnosti](http://portal.manage.microsoft.com) a klepněte na zařízení, jehož heslo chcete resetovat.

2.  Klepněte na **Resetovat heslo**.

    ![tap-passcode-to-reset](./media/iwp-1-tap-reset-passcode.png)

3.  Klepněte na **Odhlásit se** a potom se znovu přihlaste s pracovními nebo školními přihlašovacími údaji. Musíte se znovu přihlásit do pěti minut.

    ![sign-out-sign-back-in](./media/iwp-2-sign-out.png)

4.  Klepněte na **Resetovat heslo**.

    ![tap-reset-passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    V tabulce najdete, jak resetování hesla funguje ve vašem zařízení.

    |Platforma|Support|
    |------------|-----------|
    |Android|Vytvoří nové dočasné alfanumerické heslo.|
    |iOS|Odebere heslo ze zařízení a nevytvoří nové dočasné heslo. Poku používáte Touch ID, musíte ho v zařízení znovu nainstalovat, protože se při resetování hesla odebere.|
    |Windows 10 (pouze mobilní zařízení)|Vytvoří nové dočasné alfanumerické heslo. Windows Hello je podporované.|
    |Windows Phone 8.1|Vytvoří nové dočasné číselné heslo.|
    Po odemčení zařízení můžete nastavit nové heslo pomocí nabídky **Nastavení** vašeho zařízení.

5.  Odemkněte zařízení a nastavte nové heslo nebo změňte dočasné heslo pomocí nabídky **Nastavení** vašeho zařízení.

    Pokud chcete zobrazit potvrzení, že bylo heslo úspěšně resetované, klikněte na příznak oznámení v pravé horní části webu portálu společnosti.

### Související témata
[Použití webu Portál společnosti Intune](using-the-intune-company-portal-website.md)

<!--HONumber=May16_HO1-->

