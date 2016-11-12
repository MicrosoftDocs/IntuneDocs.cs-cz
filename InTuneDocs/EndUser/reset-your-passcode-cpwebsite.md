---
title: "Resetování hesla zařízení z webu Portál společnosti | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: b3a3b7c2a983776f79ffa8562e130bb11e714e29


---


# <a name="reset-your-device-passcode-from-the-company-portal-website"></a>Resetování hesla zařízení z webu Portál společnosti

Pokud ztratíte kód PIN nebo heslo zařízení, které jste zaregistrovali v Intune, můžete použít [web Portál společnosti](http://portal.manage.microsoft.com) k jeho resetování. Web Portál společnosti se používá ke správě počítačů a zařízení, které jste zaregistrovali v Intune, a k plnění většinou stejných úkolů jako v aplikaci Portál společnosti.

> [!NOTE]
> Tlačítko **Resetovat heslo** se na webu Portál společnosti nemusí zobrazit – záleží na tom, jak správce IT nakonfiguroval Intune. Resetování hesla není podporované na zařízeních s Windows 8.1.

Resetování hesla:

1.  Otevřete [web Portál společnosti](http://portal.manage.microsoft.com) a zvolte zařízení, jehož heslo chcete resetovat.

2.  Zvolte **Resetovat heslo**.

    ![Detaily zařízení s tlačítkem Resetovat heslo](./media/iwp-screen-with-all-options.png)

3.  Zvolte **Odhlásit se** a pak se znovu přihlaste. Použijte přihlašovací údaje pracovního nebo školního účtu. Musíte se znovu přihlásit do pěti minut.

    ![Zpráva o resetování s tlačítkem pro odhlášení](./media/iwp-2-sign-out.png)

4.  Zvolte **Resetovat heslo**.

    ![Zpráva s vysvětlením, co se stane, když resetujete heslo](./media/iwp-3-tap-reset-passcode-after-signin.png)

    V tabulce najdete informace o tom, jak **resetování hesla** funguje na vašem zařízení.

    |Platforma|Support|
    |------------|-----------|
    |Android|Vytvoří dočasné alfanumerické heslo.|
    |iOS|Odebere heslo ze zařízení, ale nevytvoří dočasné heslo. Pokud používáte Touch ID, musíte ho v zařízení znovu nainstalovat, protože se při resetování hesla odebere.|
    |Windows 10 (pouze mobilní zařízení)|Vytvoří dočasné alfanumerické heslo. Windows Hello je podporované.|
    |Windows Phone 8.1|Vytvoří dočasné číselné heslo.|
    Po odemčení zařízení můžete nastavit nové heslo pomocí nabídky **Nastavení** vašeho zařízení.

5.  Odemkněte zařízení a nastavte nové heslo nebo změňte dočasné heslo pomocí nabídky **Nastavení** vašeho zařízení.

    Pokud chcete zobrazit potvrzení, že bylo heslo úspěšně resetované, klikněte na příznak oznámení v pravé horní části webu Portál společnosti.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->


