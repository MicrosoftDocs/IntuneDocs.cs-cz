---
title: Podmíněný přístup na základě aplikace s Intune
titlesuffix: Microsoft Intune
description: Přečtěte si, jak s Intune funguje podmíněný přístup založený na aplikacích.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00cef3e1eb28ef1fc4a54369182982d958c20e6a
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389165"
---
# <a name="app-based-conditional-access-with-intune"></a>Podmíněný přístup na základě aplikace s Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Zásady ochrany aplikací Intune](app-protection-policy.md) pomáhají chránit vaše firemní data na zařízeních, která jsou zaregistrovaná v Intune. Zásady ochrany aplikací můžete použít také u zařízení vlastněných zaměstnanci, která nejsou zaregistrovaná ke správě v Intune. V takovém případě potřebujete mít pořád jistotu, že jsou vaše firemní data a prostředky chráněné, i když tato zařízení vaše společnost nespravuje.

Podmíněný přístup založený na aplikaci a správa klientských aplikací přidávají další vrstvu zabezpečení. Zajišťují, aby přístup k Exchangi Online a dalším službám Office 365 měly jenom klientské aplikace, které podporují řešení Intune s jeho zásadami ochrany aplikací.

> [!NOTE]
> Spravovaná aplikace je taková aplikace, která využívá zásady ochrany aplikací a která lze spravovat pomocí Intune.

Blokovat integrované e-mailové aplikace na zařízeních s iOSem a Androidem můžete jen tehdy, pokud aplikaci Microsoft Outlook povolíte přístup k Exchangi Online. Kromě toho můžete u aplikací, které nepoužívají zásady ochrany aplikací Intune, blokovat přístup k SharePointu Online.

## <a name="prerequisites"></a>Požadavky
Před vytvořením zásady podmíněného přístupu na základě aplikace je potřeba mít:

- **Řešení Enterprise Mobility + Security (EMS)** nebo **předplatné Azure Active Directory (AD) Premium**
- Uživatelé musí mít licenci pro EMS nebo Azure AD.

Další informace najdete na stránce s [cenami Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) nebo [cenami Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

## <a name="supported-apps"></a>Podporované aplikace

Seznam aplikací, které podporují podmíněný přístup na základě aplikace, najdete v [technické referenční dokumentaci k podmíněnému přístupu Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

Podmíněný přístup na základě aplikace [podporuje také obchodní aplikace](app-modern-authentication-block.md). Ty ale musí využívat [moderní ověřování Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a). 

## <a name="how-app-based-conditional-access-works"></a>Jak podmíněný přístup na základě aplikace funguje

V tomto příkladu použil správce zásady ochrany aplikací u aplikace Outlook a následné pravidlo podmíněného přístupu. To přidá Outlook na seznam schválených aplikací, které lze využít k přístupu k firemnímu e-mailu.

> [!NOTE]
> Vývojový diagram vyobrazený níže lze použít i pro další spravované aplikace.

![Podmíněný přístup založený na aplikacích znázorněný ve vývojovém diagramu](./media/ca-intune-common-ways-3.png)

1. Uživatel se pokusí ověřit ve službě Azure AD z aplikace Outlook.

2. Při prvním pokusu o ověření je uživatel přesměrován do obchodu s aplikacemi, odkud si má nainstalovat zprostředkující aplikaci. Zprostředkující aplikací může být buď Microsoft Authenticator pro zařízení s iOSem, nebo Portál společnosti Microsoft pro zařízení s Androidem.

   Pokud se uživatelé pokusí použít nativní e-mailovou aplikaci, budou přesměrováni do obchodu s aplikacemi, aby si nainstalovali Outlook.

3. Zprostředkující aplikace se nainstaluje na zařízení.

4. Zprostředkující aplikace zahájí proces registrace Azure AD, která vytvoří záznam zařízení ve službě Azure AD. To není stejné jako proces zápisu mobilního zařízení management (MDM), ale tento záznam je nezbytné, aby zásady podmíněného přístupu je možné vynucovat na zařízení.

5. Zprostředkující aplikace ověří identitu aplikace. Takže zprostředkující aplikaci ověřit, zda má aplikace oprávnění pro použití tímto uživatelem je vrstva zabezpečení.

6. Zprostředkující aplikace odešle v rámci ověřování uživatele ID klienta aplikace do Azure AD, aby zkontrolovala, že je v seznamu schválených zásad.

7. Azure AD umožní ověření uživatele a použití aplikace na základě seznamu schválených zásad. Pokud aplikace v seznamu není, Azure AD uživateli zakáže přístup k aplikaci.

8. Aplikace Outlook komunikuje s cloudovou službou Outlooku a iniciuje tak komunikaci s Exchangem Online.

9. Cloudová služba Outlooku komunikuje s Azure AD, aby pro uživatele načetla přístupový token služby Exchange Online.

10. Aplikace Outlook komunikuje s Exchangem Online, aby načetla firemní e-mail uživatele.

11. Firemní e-mail se doručí do uživatelovy poštovní schránky.

## <a name="next-steps"></a>Další postup
[Vytvoření zásady podmíněného přístupu na základě aplikace](app-based-conditional-access-intune-create.md)

[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)
