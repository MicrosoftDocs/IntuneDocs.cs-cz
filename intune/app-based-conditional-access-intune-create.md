---
title: Nastavení zásad podmíněného přístupu na základě aplikace v Intune
description: Zjistěte, jak vytvořit zásadu podmíněného přístupu na základě aplikace.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7e3654021935495189b62da5257793383586137
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Nastavení zásad podmíněného přístupu na základě aplikace v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jak pro aplikace, které jsou na seznamu schválených aplikací, nastavit zásady podmíněného přístupu na základě aplikace. Na seznamu schválených aplikací jsou aplikace, které testoval Microsoft.

> [!IMPORTANT]
> Tento článek vás provede jednotlivými kroky přidání zásady podmíněného přístupu na základě aplikace s použitím Exchange Online, ale stejný postup můžete použít při přidání dalších aplikací, jako je SharePoint Online, Microsoft Teams, a dalších aplikací ze seznamu schválených aplikací.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace
1.  Přejděte na [portál Azure Portal](https://portal.azure.com) a přihlaste se.

2.  Zvolte **Všechny služby** a zadejte: Intune.

3.  Zvolte **Ochrana aplikací Intune**.

4.  V podokně **Intune App Protection** v části **Podmíněný přístup** zvolte **Exchange Online**.

    ![Snímek obrazovky s podoknem nastavení, ve kterém se zobrazuje sekce podmíněného přístupu se zvýrazněnou možností Exchange Online](./media/MAM-conditional-access-1.png)

6. V podokně **Povolené aplikace** zvolte možnost **Povolit aplikace, které podporují zásady aplikací Intune**. Tím umožníte, aby přístup k Exchangi Online měly jenom aplikace podporované zásadami ochrany aplikací Intune. Při výběru této možnosti se zobrazí seznam podporovaných aplikací.

    > [!NOTE]
    > Všichni poštovní klienti Exchange Active Sync, včetně integrovaných poštovních klientů v iOSu a Androidu, kteří se připojují k Exchangi Online, mají zakázané odesílání a příjem e-mailů. Místo toho uživatelé dostanou e-mail, který je informuje o tom, že musí použít poštovní aplikaci Outlook.

7. Pokud chcete tuto zásadu uplatnit na uživatele, otevřete podokno **Omezené skupiny uživatelů** a zvolte **Přidat skupinu uživatelů**. Vyberte skupiny uživatelů, které by tuto zásadu měly obdržet.

    ![Snímek obrazovky s podoknem s omezenou skupinou uživatelů a zvýrazněnou možností Přidat skupinu uživatelů](./media/mam-ca-add-user-group.png)

8. Můžete chtít, aby pro některé uživatele ve skupině uživatelů, kterou jste vybrali v předchozím kroku, tato zásada neplatila. V takovém případě přidejte skupinu uživatelů do seznamu vyloučených skupin uživatelů. V podokně **Exchange Online** zvolte **Vyloučené skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** otevřete seznam skupin uživatelů. Vyberte skupiny, které chcete z této zásady vyloučit.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Úprava nebo odstranění skupin uživatelů z existujících zásad podmíněného přístupu na základě aplikace

1. Otevřete podokno **Omezené skupiny uživatelů** a pak zvýrazněte skupinu uživatelů, kterou chcete odstranit.
2. Kliknutím na tři tečky zobrazíte možnosti odstranění.
3. Volbou možnosti **Odstranit** odeberte tuto skupinu uživatelů ze seznamu.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Vytvoření zásad podmíněného přístupu na základě aplikace v úloze Azure AD

Počínaje verzí Intune 1708 můžou správci IT vytvářet zásady podmíněného přístupu na základě aplikace v úloze Azure AD. Má to tu výhodu, že není potřeba přepínat mezi úlohami Azure a Intune.

> [!IMPORTANT]
> Abyste mohli vytvořit zásady podmíněného přístupu Azure AD na portálu Intune Azure Portal, musíte mít licenci Azure AD Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace

> [!IMPORTANT]
> Než začnete využívat zásady podmíněného přístupu na základě aplikace, je potřeba použít pro vaše aplikace [zásady ochrany aplikací Intune](app-protection-policies.md).

1. Na **řídicím panelu Intune** zvolte **Podmíněný přístup**.

2. V podokně **Zásady** vytvořte novou zásadu podmíněného přístupu na základě aplikace výběrem možnosti **Nová zásada**.

4. Zadejte název zásady a nakonfigurujte nastavení dostupná v části **Přiřazení** a potom v části **Ovládací prvky přístupu** zvolte **Přiřazení**.

5. Zvolte **Vyžadovat klientem schválenou aplikaci**, klikněte na **Vybrat** a potom novou zásadu uložte kliknutím na **Vytvořit**.

## <a name="next-steps"></a>Další kroky
[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)

### <a name="see-also"></a>Viz taky

[Ochrana dat aplikací pomocí zásad ochrany aplikací](app-protection-policies.md)
[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
