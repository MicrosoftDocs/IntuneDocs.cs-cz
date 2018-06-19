---
title: Konfigurace zásad dodržování předpisů a správy aplikací pro zařízení během migrace do Intune
titlesuffix: Microsoft Intune
description: Tento článek popisuje kroky potřebné ke konfiguraci zásad dodržování předpisů zařízením a správy aplikací během migrace do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 13a9c0a036eb6ce6ea7e984419c9598194b35b68
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/16/2018
ms.locfileid: "29926350"
---
# <a name="configure-device-compliance-and-app-management-policies-when-migrating-to-microsoft-intune"></a>Konfigurace zásad dodržování předpisů zařízením a správy aplikací během migrace do Microsoft Intune

Hlavním cílem při migraci do Intune je zajistit, aby se všechna zařízení zaregistrovala ve službě Intune a dodržovala její zásady. Zásady pro zařízení pomáhají spravovat nejen zařízení vlastněná společností, která mají jednoho uživatele, ale také osobní zařízení uživatelů (BYOD), sdílená zařízení, jako jsou veřejné terminály, počítače v prodejnách nebo tablety sdílené více studenty ve třídě, a zařízení bez uživatelů (jenom iOS).

Každé zařízení využívá jinou platformu s jinými nastaveními. Zásady zařízení Intune ale fungují na všech těchto platformách, pro které poskytují následující možnosti správy mobilních zařízení:

-   Určení počtu zařízení, která si jednotliví uživatelé můžou zaregistrovat

-   Správa nastavení zařízení (například šifrování na úrovni zařízení, délka hesla nebo používání kamery)

-   Dodávání aplikací, e-mailových profilů, profilů VPN apod.

-   Vyhodnocení kritérií pro zásady dodržování předpisů zabezpečení na úrovni zařízení

> [!IMPORTANT]
> Zásady správy zařízení se nepřiřazují přímo jednotlivým zařízením nebo uživatelům, ale skupinám uživatelů. Zásady je možné použít přímo pro skupinu uživatelů a tím současně pro zařízení uživatelů, nebo je možné je použít pro skupinu zařízení a tím současně pro členy skupiny.

## <a name="task-list-for-device-compliance-policies"></a>Seznam kroků zavedení zásad dodržování předpisů pro zařízení

### <a name="task-1-add-device-groups-optional"></a>Krok 1: Přidání skupin zařízení (volitelné)

Skupiny zařízení můžete vytvořit, když potřebujete provádět úlohy správy, které jsou založené na identitě zařízení (místo na identitě uživatele).

Skupiny zařízení jsou užitečné ke správě zařízení bez vyhrazených uživatelů, jako jsou veřejné terminály nebo zařízení sdílená pracovníky ve směnném provozu nebo přiřazená určitému umístění.

Když nakonfigurujete skupiny zařízení ještě před registrací zařízení, můžete využít kategorie zařízení k tomu, aby se zařízení při registraci automaticky seskupovala. Automaticky pak obdrží zásady zařízení příslušné skupiny. Další informace najdete v článku [Začínáme se skupinami](groups-get-started.md).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Krok 2: Použití profilů přístupu k prostředkům (sítím Wi-Fi, VPN a e-mailovým certifikátům)

Profily přístupu k prostředkům dodají pro registrovaná zařízení certifikáty a nastaví konfiguraci přístupu. Pokud používáte ověřování pomocí certifikátů, [nakonfigurujte certifikáty](certificates-configure.md).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Krok 3: Vytvoření a nasazení profilů konfigurace zařízení

Je potřeba vytvořit profil konfigurace zařízení k vynucení nastavení na úrovni zařízení, například: zakázání fotoaparátu nebo obchodu s aplikacemi, konfigurace režimu jedné aplikace, nastavení domovské obrazovky apod. Přečtěte si další informace o [profilech zařízení](device-profiles.md).

####  <a name="directly-import-ios-configuration-profiles-optional"></a>Přímý import profilů konfigurace iOSu (volitelné)

-   **Profily Apple Configuratoru pro iOS (7.1 a novější):** Pokud vaše existující řešení MDM používá profily Apple Configuratoru (soubory .mobileconfig), Intune je může přímo importovat jako vlastní zásady konfigurace.

-   **Zásady konfigurace mobilních aplikací pro iOS:** Pokud vaše existující řešení MDM používá zásady konfigurace mobilních aplikací pro iOS, Intune je může přímo importovat za předpokladu, že odpovídají formátu XML, který Apple používá pro seznamy vlastností.

- Zjistěte, jak přidat vlastní zásady pro [iOS](custom-settings-ios.md).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Krok 4: Vytvoření a nasazení zásad dodržování předpisů pro zařízení (volitelné)

Zásady dodržování předpisů pro zařízení vyhodnocují nastavení týkající se zabezpečení a vytvářejí sestavy, které ukazují, jestli jsou zařízení v souladu s firemními standardy. Nastavení zahrnují:

-   Délka PIN kódu

-   Stav jailbreaku

-   Verze operačního systému

Podívejte se na další materiály k nastavení kompatibility zařízení:

-   Informace o [zásadách dodržování předpisů pro zařízení](device-compliance.md).

-   Zjistěte, [jak vytvořit zásady dodržování předpisů pro zařízení](device-compliance-get-started.md).

### <a name="task-5-publish-and-deploy-apps"></a>Krok 5: Publikování a nasazení aplikací

Pokud používáte správu mobilních zařízení (MDM) v Intune, můžete dodat aplikace vyžádáním jejich automatické instalace nebo jejich zpřístupněním v Portálu společnosti.

-   [Jak přidat aplikace](apps-add.md)

-   [Jak nasadit aplikace](apps-deploy.md)

### <a name="task-6-enable-device-enrollment"></a>Krok 6: Povolení registrace zařízení

Registrace zařízení je nezbytná k jejich správě. Zjistěte, [jak se připravit na registraci firemních zařízení a osobních zařízení uživatelů](device-enrollment.md).

## <a name="next-steps"></a>Další kroky

[Konfigurace zásad ochrany aplikací (volitelné)](migration-guide-app-protection-policies.md)
