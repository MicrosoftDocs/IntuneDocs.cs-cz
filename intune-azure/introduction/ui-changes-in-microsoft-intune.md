---
title: Kde v Azure najdu svoje funkce Intune?
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Pomáhá najít funkce Intune v konzole Azure."
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 6a6b64465c95a3edd6fc2e2d4ae3da80ba3367ee
ms.openlocfilehash: 92bd41aa4acc02e67e983c68f818bd656b0b9608
ms.lasthandoff: 04/12/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Kde v Azure najdu svoje funkce Intune?
Při přesunu Intune do portálu Azure Portal jsme využili příležitost uspořádat některé úlohy logičtěji. Každé vylepšení ale přichází za cenu toho, že je potřeba se s novým uspořádáním seznámit. Proto jsme vytvořili tento referenční přehled pro ty z vás, kteří dobře znají Intune v klasické konzole a zajímá je, jak v Intune pracovat na platformě Azure. Pokud tento článek nepopisuje funkci, kterou hledáte, uveďte ji v poznámce na konci článku, abychom ho mohli aktualizovat.
## <a name="quick-reference-guide"></a>Stručný referenční přehled
|Funkce |Cesta v klasické konzole|Cesta v Intune na Azure| |------------||---------------|---------------|
|Program registrace zařízení (DEP) |Správce > Správa mobilních zařízení > iOS a Mac OS X > Program registrace zařízení|[Registrace zařízení > Registrace Apple > Token Programu registrace zařízení (DEP)](#where-did-apple-dep-go) |
|Program registrace zařízení (DEP)| Správce > Správa mobilních zařízení > iOS a Mac OS X > Program registrace zařízení |[Registrace zařízení > Registrace Apple > Sériová čísla programu registrace](#where-did-apple-dep-go) |
|Pravidla registrace |Správce > Správa mobilních zařízení > Pravidla registrace|[Registrace zařízení > Omezení registrace](#where-did-enrollment-rules-go) |
|Skupiny podle sériového čísla iOS |Skupiny > Všechna zařízení > Firemní předregistrovaná zařízení > Podle sériového čísla iOS|[Registrace zařízení > Registrace Apple > Sériová čísla programu registrace](#where-did-corporate-pre-enrolled-devices-go) |
|Skupiny podle sériového čísla iOS |Skupiny > Všechna zařízení > Firemní předregistrovaná zařízení > Podle sériového čísla iOS| [Registrace zařízení > Registrace Apple > Sériová čísla AC](#where-did-corporate-pre-enrolled-devices-go)|
|Skupiny podle IMEI (všechny platformy)| Skupiny >Všechna zařízení > Firemní předregistrovaná zařízení > Podle IMEI (všechny platformy) | [Registrace zařízení > Identifikátory podnikových zařízení](#by-imei-all-platforms)|
| Profil Registrace podnikového zařízení | Zásady > Registrace podnikového zařízení | [Registrace zařízení > Registrace Apple > Profily programu registrace](#where-did-corporate-pre-enrolled-devices-go) |
| Profil Registrace podnikového zařízení | Zásady > Registrace podnikového zařízení | [Registrace zařízení > Registrace Apple > Profily AC](#where-did-corporate-pre-enrolled-devices-go) |


## <a name="where-do-i-manage-groups"></a>Kde můžu spravovat skupiny?
Intune na Azure používá ke správě skupin [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

## <a name="where-did-enrollment-rules-go"></a>Kde najdu pravidla registrace?
V klasické konzole jste mohli nastavit pravidla řídící registraci MDM mobilních a moderních zařízení s Windows a macOS:

![Obrázek klasických pravidel registrace mobilních zařízení](./media/ui-changes/01-classic-rules.png)

Tato pravidla platila bez výjimky pro všechny uživatele ve vašem účtu Intune. Na portálu Azure Portal se teď tato pravidla zobrazují ve dvou rozdílných typech zásad: Omezení typů zařízení a Omezení limitů počtů zařízení:

![Obrázek omezení registrace mobilních zařízení v Azure](./media/ui-changes/02-azure-enroll-restrictions.png)

Výchozí Omezení limitů počtů zařízení odpovídá Limitu pro registraci zařízení v klasické konzole:

![Obrázek omezení počtů zařízení v Azure](./media/ui-changes/03-azure-device-limit.png)

Výchozí Omezení typů zařízení odpovídá Omezením platformy v klasické konzole:

![Obrázek omezení typu zařízení v Azure](./media/ui-changes/04-azure-platform-restrictions.png)

Schopnost povolit nebo blokovat zařízení v osobním vlastnictví se teď spravuje v Konfiguracích platformy v rámci Omezení typů zařízení:

![Obrázek nastavení blokování osobních zařízení v Azure](./media/ui-changes/05-azure-personal-block.png)

Nové možnosti omezení budou přidány jenom do portálu Azure Portal.

## <a name="where-did-apple-dep-go"></a>Kde najdu Program registrace zařízení (DEP) Apple?
V klasické konzole jste mohli nastavit integraci Intune s Programem registrace zařízení Apple a ručně vyžádat synchronizaci se službou společnosti Apple:

![Obrázek klasického tokenu DEP](./media/ui-changes/06-classic-dep-token.png)

Na portálu Azure Portal můžete Program registrace zařízení Apple nastavit stejným postupem jako v klasickém Intune:

![Obrázek tokenu DEP v Azure](./media/ui-changes/07-azure-dep-token.png)

Možnost **Synchronizovat** se ale v klasické konzole přesunula do pracovního postupu správy sériových čísel, protože se tam zobrazují výsledky ruční synchronizace:

![Obrázek synchronizace DEP v Azure](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Kde najdu firemní předregistrovaná zařízení?
### <a name="by-ios-serial-number"></a>Podle sériového čísla iOSu
V klasické konzole můžete zařízení s iOSem registrovat prostřednictvím Programu registrace zařízení (DEP) Apple a Apple Configuratoru. Obě metody nabízejí předregistraci zařízení podle sériového čísla a zahrnují přiřazení speciálních profilů Registrace podnikového zařízení. Ještě před registrací můžete přiřazení profilu registrace spravovat prostřednictvím skupiny zařízení **Firemní předregistrované zařízení podle sériového čísla iOS**:

![Obrázek klasických sériových čísel Apple](./media/ui-changes/09-classic-apple-serials.png)

Tam najdete sériová čísla pro registraci pomocí DEP Apple i Apple Configuratoru v jednom seznamu. Abychom omezili neshody při přiřazení profilů (profil DEP přiřazený sériovému číslu AC a naopak), rozdělili jsme sériová čísla na portálu Apple Portal do dvou seznamů:

**Sériová čísla DEP**
![Obrázek sériových čísel DEP v Azure](./media/ui-changes/10-azure-dep-serials.png)

**Sériová čísla Apple Configuratoru**
![Obrázek sériových čísel Apple Configuratoru v Azure](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Podle IMEI (všechny platformy)

V klasické konzole můžete předem zobrazit seznam čísel IMEI zařízení, abyste je při zaregistrování do Intune mohli označit jako firemní:

![Obrázek klasického seznamu čísel IMEI](./media/ui-changes/12-classic-corp-imei.png)

V konzole Azure musíte stejné IMEI nahrát do seznamu identifikátorů podnikových zařízení pomocí souboru hodnot oddělených čárkami (CSV). Nový portál nepodporuje ruční zadání čísel IMEI:

![Obrázek seznamu čísel IMEI v Azure](./media/ui-changes/13-azure-corp-imei.png)

Intune na portálu Azure Portal je připravený na budoucnost díky podpoře jiných typů identifikátorů kromě IMEI, ale aktuálně umožňuje předběžné seznamy jenom čísel IMEI.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Kde najdu profily registrace podnikového zařízení?
Pokud chcete registrovat zařízení s iOSem prostřednictvím Programu registrace zařízení (DEP) Apple nebo pomocí Apple Configuratoru, musíte zadat profil registrace podnikového zařízení, kterému se má zařízení přiřadit. V klasické konzole se tvorba a správa těchto profilů prováděla v jednom seznamu:

![Obrázek klasických profilů registrace zařízení](./media/ui-changes/14-classic-corp-profiles.png)

Tento seznam ukazuje profily povolené pro použití s Programem registrace zařízení (DEP) Apple (**DEP zapnuto**) a profil povolený jenom pro použití s Apple Configuratorem (**DEP vypnuto**).

Abychom omezili možnost záměny obou typů profilů a potenciální nesprávná přiřazení (profil DEP přiřazený zařízením Configuratoru a naopak), oddělili jsme tvorbu a správu profilů programu registrace (podporují Program registrace zařízení Apple i Apple School Manager) a profilů Apple Configuratoru:

**Profily DEP**
![Obrázek profilů DEP v Azure](./media/ui-changes/15-azure-dep-profiles.png)

**Profily Apple Configuratoru**
![Obrázek profilů Apple Configuratoru v Apple](./media/ui-changes/16-azure-ac-profiles.png)

