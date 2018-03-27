---
title: Vytvoření zásad podmíněného přístupu na základě aplikace pro SharePoint Online
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 05/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 5848fc18e0c288f8806f1fc93427d96c48317d64
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Nastavení zásad podmíněného přístupu (CA) na základě aplikace pro SharePoint Online

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Toto téma obsahuje pokyny pro nastavení zásad podmíněného přístupu na základě aplikace pro SharePoint Online. Podmíněný přístup na základě aplikace umožňuje správcům povolit pouze mobilní aplikace, které používají zásady ochrany aplikací Intune.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Vytvoření zásad podmíněného přístupu na základě aplikace pro SharePoint Online

1. Přejděte na [portál Azure Portal](https://portal.azure.com) a přihlaste se.

    > [!NOTE]
    > Pokud Azure Portal ještě neznáte, přečtěte si téma [Azure Portal pro zásady ochrany aplikací](azure-portal-for-microsoft-intune-mam-policies.md).

2. V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune App Protection** > **Správa mobilních aplikací Intune** > **Veškerá nastavení**.

4. V okně správy mobilních aplikací Intune vyberte dlaždici SharePoint Online.

5. V okně **Povolené aplikace** zvolte možnost **Povolit aplikace, které podporují zásady aplikací Intune**, čímž povolíte pouze aplikace podporované zásadami ochrany aplikací Intune.

    > [!NOTE] 
    > Když vyberete tuto možnost a povolíte přístup jenom aplikacím podporovaným zásadami ochrany aplikací Intune, zobrazí se seznam obsahující **pouze** podporované aplikace.

    ![Snímek obrazovky s oknem povolených aplikací, na které je zobrazen seznam aplikací](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Přiřazení zásad podmíněného přístupu na základě aplikace uživatelům

1. Otevřete okno **Omezené skupiny uživatelů** a pak vyberte **Přidat skupinu uživatelů**.

2. Vyberte skupiny uživatelů, které by tuto zásadu měly obdržet.

    ![Snímek obrazovky okna s omezenou skupinou uživatelů a zvýrazněnou možností Přidat skupinu uživatelů](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Můžete chtít, aby pro některé uživatele ve skupině uživatelů, kterou jste vybrali v předchozím kroku, tato zásada neplatila. V takovém případě přidejte skupinu uživatelů do seznamu vyloučených skupin uživatelů. 

3. V okně **SharePoint Online** vyberte **Vyloučené skupiny uživatelů**, pak vyberte **Přidat skupinu uživatelů** a otevřete seznam skupin uživatelů.

4. Vyberte skupiny, které chcete z této zásady vyloučit.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Úprava nebo odstranění skupin uživatelů z existujících zásad podmíněného přístupu na základě aplikace

1. Otevřete okno **Omezené skupiny uživatelů**, pak zvýrazněte skupinu uživatelů, kterou chcete odstranit.
2. Kliknutím na tři tečky zobrazíte možnosti odstranění.
3. Volbou možnosti **Odstranit** odeberte tuto skupinu uživatelů ze seznamu.

> [!NOTE] 
> Stejným postupem můžete odebrat skupinu uživatelů ze seznamu **Vyloučené skupiny uživatelů**.

## <a name="next-steps"></a>Další kroky

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Viz taky

[Ochrana dat aplikací pomocí zásad ochrany aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Konfigurace podmíněného přístupu na základě aplikace pro Exchange Online](mam-ca-for-exchange-online.md)
