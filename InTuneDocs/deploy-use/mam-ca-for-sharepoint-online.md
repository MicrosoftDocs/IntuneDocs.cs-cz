---
title: "Konfigurace přístupu aplikací pro SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Povolení přístupu jenom aplikacím s podporou MAM vytvořením zásad podmíněného přístupu pro SharePoint Online
Toto téma obsahuje podrobný postup, jak nastavením podmíněného přístupu pro Exchange Online povolíte jenom mobilní aplikace, které podporují zásady správy mobilních aplikací (MAM) v Intune.

## <a name="configure-a-sharepoint-online-policy"></a>Konfigurace zásad SharePointu Online
**Krok 1:** Přihlaste se k [portálu Azure](https://portal.azure.com), který zahrnuje funkci přístupu aplikací. Pokud Azure Portal ještě neznáte, přečtěte si téma [Azure Portal pro zásady MAM](azure-portal-for-microsoft-intune-mam-policies.md).

**Krok 2:** Přejděte na **Procházet > Intune > okno Správa mobilních aplikací Intune > Nastavení** a v části **Podmíněný přístup** zvolte **SharePoint Online**.

![Snímek obrazovky s oknem nastavení, na kterém je zobrazena část věnovaná podmíněnému přístupu a otevřené okno SharePointu Online](../media/mam-ca-settings-spo.png)

**Krok 3:** V okně **Povolené aplikace** zvolte možnost **Povolit aplikace, které podporují zásady aplikací Intune**. Tím umožníte, aby přístup k SharePointu Online měly jenom aplikace podporované zásadami MAM Intune. Když vyberete tuto možnost a povolíte přístup jenom aplikacím podporovaným zásadami MAM Intune, zobrazí se seznam podporovaných aplikací.

![Snímek obrazovky s oknem povolených aplikací, na které je zobrazen seznam aplikací](../media/mam-ca-spo-allowed-apps.png)

**Krok 4:** Pokud tuto zásadu chcete uplatnit na uživatele, otevřete okno **Omezené skupiny uživatelů** a zvolte **Přidat skupinu uživatelů**. Vyberte skupiny uživatelů, které by tuto zásadu měly obdržet.

![Snímek obrazovky okna s omezenou skupinou uživatelů a zvýrazněnou možností Přidat skupinu uživatelů](../media/mam-ca-spo-restricted-groups.png)


**Krok 5:** Můžete chtít, aby pro některé uživatele ve skupině uživatelů, kterou jste vybrali v předchozím kroku, tato zásada neplatila. V takovém případě přidejte skupinu uživatelů do seznamu vyloučených skupin uživatelů. V okně **SharePoint Online** zvolte **Vyloučené skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** otevřete seznam skupin uživatelů. Vyberte skupiny, které chcete z této zásady vyloučit.  

## <a name="modifying-an-existing-policy"></a>Změna existující zásady
### <a name="adding-or-deleting-user-groups"></a>Přidání nebo odstranění skupin
Pokud chcete **odstranit skupinu uživatelů** ze seznamu **omezených skupin uživatelů**, otevřete okno Omezené skupiny uživatelů, zvýrazněte skupinu uživatelů, kterou chcete odstranit, a kliknutím na tři tečky (…) zobrazte možnost odstranění. Volbou možnosti **Odstranit** odeberte tuto skupinu uživatelů ze seznamu. Stejným postupem můžete odebrat skupinu uživatelů ze seznamu **vyloučených skupin uživatelů**.


## <a name="next-steps"></a>Další kroky
[Konfigurace přístupu aplikací pro Exchange Online](mam-ca-for-exchange-online.md)

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

