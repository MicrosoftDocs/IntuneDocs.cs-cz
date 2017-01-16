---
title: "Podmíněný přístup k 0365 na základě aplikací | Dokumentace Microsoftu"
description: "Udělejte si představu o tom, jak vám podmíněný přístup MAM pomůže určit, které aplikace mají přístup ke službám O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2babdeaaf10e9a58716d299cbde0babe45967fb1


---

# <a name="allow-only-mobile-apps-that-support-intune-mam-policies-to-access-office-365-services"></a>Povolení přístupu ke službám Office 365 jenom mobilním aplikacím, které podporují zásady Intune MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Zásady správy mobilních aplikací (MAM) Intune](protect-apps-and-data-with-microsoft-intune.md) pomáhají chránit vaše firemní data na zařízeních, která jsou zaregistrovaná ke správě v Intune. Zásady MAM můžete použít také u **zařízení vlastněných zaměstnanci, která nejsou zaregistrovaná ke správě v Intune**.  V takovém případě potřebujete mít pořád jistotu, že jsou vaše firemní data a prostředky chráněné, i když tato zařízení nespravujete. Pomocí podmíněného přístupu MAM můžete vytvořit zásadu, která umožňuje přístup ke službám O365 (jako je Exchange Online) jenom mobilním aplikacím, které podporují zásady Intune MAM.

Když například povolíte přístup k Exchangi Online jenom **aplikaci Microsoft Outlook**, můžete **integrovaným poštovním aplikacím v iOSu a Androidu**, jejichž data nejsou chráněná zásadami Intune MAM, zablokovat příjem e-mailů z **Exchange Online**.

Následující diagram znázorňuje tok používaný v rámci zásad podmíněného přístupu MAM k určení toho, kdy povolit nebo blokovat přístup: ![Diagram, který zobrazuje různá kritéria k určení, jestli se má povolit nebo blokovat přístup ](../media/mam-ca-decision-flow_simple.png).

Popis zkratek použitých v diagramech:
* **CP**: Aplikace Portál společnosti
* **AA**: Aplikace Azure Authenticator
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Požadavky
**Předtím**, než můžete zásadu podmíněného přístupu MAM nakonfigurovat, musíte mít **Enterprise Mobility + Security nebo předplatné Azure Active Directory Premium**, přičemž uživatelé musí mít licence na EMS nebo Azure AD. Další informace najdete na [stránce s cenami služby Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) nebo na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## <a name="supported-apps"></a>Podporované aplikace
**Exchange Online**: **Microsoft Outlook** pro Android a iOS

Další informace týkající se uživatelského prostředí aplikace, která používá zásady podmíněného přístupu MAM, najdete v části [Co očekávat při používání aplikace s podmíněným přístupem MAM](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Další kroky
[Vytvoření zásad Exchange Online pro aplikace MAM](mam-ca-for-exchange-online.md)

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


