---
title: "Podmíněný přístup k O365 na základě aplikací"
description: "Udělejte si představu o tom, jak vám podmíněný přístup MAM pomůže určit, které aplikace mají přístup ke službám O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 78b5d58df44252d1f3916c1d2a2ea02fcb1a10e2
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Povolení jenom mobilních aplikací, které podporují zásady ochrany aplikací Intune pro přístup ke službám Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Zásady ochrany aplikací Intune](protect-apps-and-data-with-microsoft-intune.md) pomáhají chránit vaše firemní data na zařízeních, která jsou zaregistrovaná ke správě v Intune. Zásady ochrany aplikací můžete použít také u **zařízení vlastněných zaměstnanci, která nejsou zaregistrovaná ke správě v Intune**.  V takovém případě potřebujete mít pořád jistotu, že jsou vaše firemní data a prostředky chráněné, i když tato zařízení nespravujete. Pomocí podmíněného přístupu s MAM na základě aplikace můžete vytvořit zásadu, která umožňuje přístup ke službám O365 (jako je Exchange Online) jenom mobilním aplikacím, které podporují zásady ochrany aplikací Intune.

Když například povolíte přístup k Exchangi Online jenom **aplikaci Microsoft Outlook**, můžete **integrovaným poštovním aplikacím v iOSu a Androidu**, jejichž data nejsou chráněná zásadami Intune MAM, zablokovat příjem e-mailů z **Exchange Online**. Nebo můžete mobilním aplikacím, které nemají podporu Intune MAM, zablokovat přístup k **SharePointu Online**.

Následující diagram znázorňuje tok používaný zásadami podmíněného přístupu na základě aplikace k určení toho, kdy povolit nebo blokovat přístup: ![Diagram, který zobrazuje různá kritéria k určení, jestli se má povolit nebo blokovat přístup ](../media/mam-ca-decision-flow_simple.png).

Popis zkratek použitých v diagramech:
* **CP**: Aplikace Portál společnosti
* **AA**: Aplikace Azure Authenticator
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Požadavky
**Před tím**, než budete moct vytvořit zásadu podmíněného přístupu založenou na aplikaci, musíte mít **Enterprise Mobility + Security nebo předplatné Azure Active Directory Premium**, přičemž uživatelé musí mít licence na EMS nebo Azure AD. Další informace najdete na [stránce s cenami služby Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) nebo na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Podporované aplikace
**Exchange Online**:
* **Microsoft Outlook** pro Android a iOS.

**SharePoint Online**
* Microsoft Word pro iOS a Android
* Microsoft Excel pro iOS a Android
* Microsoft PowerPoint pro iOS a Android
* Microsoft OneDrive pro firmy pro iOS a Android
* Microsoft OneNote pro iOS

>[!IMPORTANT]
>U zařízení s Androidem se musí počáteční registrace zařízení provést přihlášením k aplikaci OneDrive nebo Outlook. Aplikace OneNote pro Android zatím MAM bez registrace nepodporuje.

Další informace týkající se uživatelského prostředí aplikace, která používá zásady podmíněného přístupu založené na aplikaci, najdete v tématu [Co očekávat při používání aplikace s podmíněným přístupem MAM](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Další kroky
[Vytvoření zásad Exchange Online pro aplikace MAM](mam-ca-for-exchange-online.md)

[Vytvoření zásad SharePointu Online pro aplikace MAM](mam-ca-for-sharepoint-online.md)

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad ochrany aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
