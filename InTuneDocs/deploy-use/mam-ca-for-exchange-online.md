---
title: "Přístup k aplikacím pro Exchange Online | Dokumentace Microsoftu"
description: "Toto téma popisuje, jak nakonfigurujete zásadu podmíněného přístupu pro aplikace MAM."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: ab6d1cf6a6b77be6aff6398ff99135674471ba35


---

# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a>Povolení přístupu jenom aplikacím s podporou MAM vytvořením podmíněného přístupu pro Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma obsahuje podrobný postup, jak nastavením podmíněného přístupu pro Exchange Online povolíte jenom mobilní aplikace, které podporují zásady ochrany aplikací Intune.


## <a name="create-an-exchange-online-policy"></a>Vytvoření zásady pro Exchange Online
1.  Přihlaste se na [Azure Portal](https://portal.azure.com), který obsahuje funkci přístupu aplikací. Pokud Azure Portal ještě neznáte, přečtěte si téma [Azure Portal pro zásady ochrany aplikací](azure-portal-for-microsoft-intune-mam-policies.md).

2.  Zvolte **Další služby** a zadejte „Intune“.

3.  Zvolte **Ochrana aplikací Intune**.

4.  V okně **Správa mobilních aplikací Intune** zvolte **Všechna nastavení**.

5.  V části **Podmíněný přístup** zvolte **Exchange Online**.

    ![Snímek obrazovky s oknem nastavení, ve kterém se zobrazuje sekce podmíněného přístupu se zvýrazněnou možností Exchange Online](../media/MAM-conditional-access-1.png)

6. V okně **Povolené aplikace** zvolte možnost **Povolit aplikace, které podporují zásady aplikací Intune**. Tím umožníte, aby přístup k Exchangi Online měly jenom aplikace podporované zásadami ochrany aplikací Intune. Při výběru této možnosti se zobrazí seznam podporovaných aplikací.

    >[!NOTE]
    >Všem poštovním klientům Exchange Active Sync, včetně integrovaných poštovních klientů v iOSu a Androidu, kteří se připojují k Exchangi Online, se zakáže odesílání a příjem e-mailů. Místo toho uživatelé dostanou e-mail, který je informuje o tom, že musí použít poštovní aplikaci Outlook.

7. Pokud tuto zásadu chcete uplatnit na uživatele, otevřete okno **Omezené skupiny uživatelů** a zvolte **Přidat skupinu uživatelů**. Vyberte skupiny uživatelů, které by tuto zásadu měly obdržet.

    ![Snímek obrazovky okna s omezenou skupinou uživatelů a zvýrazněnou možností Přidat skupinu uživatelů](../media/mam-ca-add-user-group.png)

8. Můžete chtít, aby pro některé uživatele ve skupině uživatelů, kterou jste vybrali v předchozím kroku, tato zásada neplatila. V takovém případě přidejte skupinu uživatelů do seznamu vyloučených skupin uživatelů. V okně **Exchange Online** zvolte **Vyloučené skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** otevřete seznam skupin uživatelů. Vyberte skupiny, které chcete z této zásady vyloučit.  

## <a name="modify-an-existing-policy"></a>Úprava existující zásady
### <a name="add-or-delete-user-groups"></a>Přidání nebo odstranění skupin uživatelů

Pokud chcete **odstranit skupinu uživatelů** ze seznamu **omezených skupin uživatelů**, otevřete okno **Omezené skupiny uživatelů**, zvýrazněte skupinu uživatelů, kterou chcete odstranit, a kliknutím na **tři tečky (...)** zobrazte možnost **Odstranit**. Volbou možnosti **Odstranit** odeberte tuto skupinu uživatelů ze seznamu. Stejným postupem můžete odebrat skupinu uživatelů ze seznamu **vyloučených skupin uživatelů**.


## <a name="next-steps"></a>Další kroky
[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a>Související témata
[Ochrana dat aplikací pomocí zásad ochrany aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


