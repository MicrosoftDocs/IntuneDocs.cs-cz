---
title: "Zásady podmíněného přístupu k aplikacím v Intune"
description: "Toto téma popisuje, jak v Intune nakonfigurovat zásadu podmíněného přístupu k aplikacím."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Nastavení zásad podmíněného přístupu k aplikacím

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V tomto tématu najdete pokyny k nastavení zásad podmíněného přístupu k aplikacím, které jsou na seznamu schválených aplikací. Na seznamu schválených aplikací jsou aplikace, které testoval Microsoft.

> [!IMPORTANT]
> Toto téma vás provede jednotlivými kroky přidání zásady podmíněného přístupu k aplikaci pomocí Exchange Online, ale stejný postup můžete použít k přidání dalších aplikací, jako je SharePoint Online, Microsoft Teams a další ze seznamu schválených aplikací.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace
1.  Přejděte na [portál Azure Portal](https://portal.azure.com) a přihlaste se.

2.  Zvolte **Další služby** a zadejte „Intune“.

3.  Zvolte **Ochrana aplikací Intune**.

4.  V okně **Správa mobilních aplikací Intune** zvolte **Všechna nastavení**.

5.  V části **Podmíněný přístup** zvolte **Exchange Online**.

    ![Snímek obrazovky s oknem nastavení, ve kterém se zobrazuje sekce podmíněného přístupu se zvýrazněnou možností Exchange Online](./media/MAM-conditional-access-1.png)

6. V okně **Povolené aplikace** zvolte možnost **Povolit aplikace, které podporují zásady aplikací Intune**. Tím umožníte, aby přístup k Exchangi Online měly jenom aplikace podporované zásadami ochrany aplikací Intune. Při výběru této možnosti se zobrazí seznam podporovaných aplikací.

    > [!NOTE]
    > Všem poštovním klientům Exchange Active Sync, včetně integrovaných poštovních klientů v iOSu a Androidu, kteří se připojují k Exchangi Online, se zakáže odesílání a příjem e-mailů. Místo toho uživatelé dostanou e-mail, který je informuje o tom, že musí použít poštovní aplikaci Outlook.

7. Pokud tuto zásadu chcete uplatnit na uživatele, otevřete okno **Omezené skupiny uživatelů** a zvolte **Přidat skupinu uživatelů**. Vyberte skupiny uživatelů, které by tuto zásadu měly obdržet.

    ![Snímek obrazovky okna s omezenou skupinou uživatelů a zvýrazněnou možností Přidat skupinu uživatelů](./media/mam-ca-add-user-group.png)

8. Můžete chtít, aby pro některé uživatele ve skupině uživatelů, kterou jste vybrali v předchozím kroku, tato zásada neplatila. V takovém případě přidejte skupinu uživatelů do seznamu vyloučených skupin uživatelů. V okně **Exchange Online** zvolte **Vyloučené skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** otevřete seznam skupin uživatelů. Vyberte skupiny, které chcete z této zásady vyloučit.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Úprava nebo odstranění skupin uživatelů z existujících zásad podmíněného přístupu na základě aplikace

1. Otevřete okno **Omezené skupiny uživatelů**, pak zvýrazněte skupinu uživatelů, kterou chcete odstranit.
2. Kliknutím na tři tečky zobrazíte možnosti odstranění.
3. Volbou možnosti **Odstranit** odeberte tuto skupinu uživatelů ze seznamu.

## <a name="next-steps"></a>Další kroky
[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)

### <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad ochrany aplikací](app-protection-policies.md)
