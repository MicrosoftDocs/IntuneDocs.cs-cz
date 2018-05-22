---
title: Začínáme s aplikacemi v Microsoft Intune
titlesuffix: ''
description: Najděte a přidejte aplikace do zařízení, aby mohli vaši pracovníci plnit úkoly.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d99812c57596e10d0cdfa2c0f4504f8a6ac583c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Začínáme s přidáváním aplikací v Microsoft Intune

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. Intune podporuje několik různých typů aplikací. Dostupné možnosti se pro jednotlivé typy aplikací liší.

Intune umožňuje přidat a přiřadit k firemním zařízením tyto typy aplikací:
- **Aplikace ze Storu:** U aplikací dostupných v App Storu potřebujete použít další správu mobilních aplikací.
- **Interně napsané aplikace (obchodní):** Nahrajete soubor, který se stáhne do zařízení uživatelů.
- **Integrované aplikace:** K zařízením s iOSem a Androidem přiřadíte kurátorované spravované aplikace, jako jsou třeba aplikace Office 365.
- **Aplikace na webu:** Intune vytvoří zástupce webové aplikace na domovské obrazovce zařízení.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak přiřadím aplikaci z veřejného obchodu?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Vyberte **Mobilní aplikace** a pak vyberte **Aplikace**.
4. Vyberte **Přidat** a potom jako **Typ aplikace** zvolte **iOS**.
5. Zvolte **Vybrat aplikaci**, aby se zobrazilo podokno **Hledat v App Storu**.
6. V textovém poli najděte aplikaci, kterou chcete zařízení přiřadit. Zvolte aplikaci a klikněte na **Vybrat**.
7. V podokně **Přidat aplikaci** vyberte **Informace o aplikaci** a vyplňte všechny informace o aplikaci. Můžete přidat i další podrobnosti užitečné pro zařazení aplikace, jako je **Vlastník**, **Poznámky**, **Vývojář** a **Adresa URL informací o ochraně osobních údajů** pro zásady ochrany osobních údajů používané vaší společností.
8. Nezapomeňte vybrat **Ano** u možnosti **Zobrazit na Portálu společnosti jako vybranou aplikaci** a pak vyberte **OK**.
9. V podokně **Přidat aplikaci** vyberte **Přidat**, abyste mohli přidat aplikaci. Dostanete se do **přehledu** aplikace. Zvolte **Přiřazení**, klikněte na **Přidat skupinu** a přiřaďte aplikaci testovací skupině. Dejte aplikaci **k dispozici** ke stažení. Pak by se aplikace na testovacím zařízení měla zobrazit jako **doporučená aplikace**.


- [Postup přiřazení aplikací do skupin](apps-deploy.md)

## <a name="learn-more"></a>Další informace

* [Co je správa aplikací pomocí Intune?](app-management.md)
* [Přehled životního cyklu aplikace](app-lifecycle.md)
* [Co jsou zásady ochrany aplikací?](app-protection-policy.md)
