---
title: "Konfigurace zásad dodržování předpisů a správy aplikací pro zařízení během migrace do Intune"
description: "Tento článek popisuje kroky potřebné ke konfiguraci zásad dodržování předpisů zařízením a správy aplikací během migrace Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e848dda6643a28141a8f5f1d0bdc01f2bd9d390
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a>Konfigurace zásad dodržování předpisů a správy aplikací

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Hlavním cílem při migraci do Intune je zajistit registraci všech zařízení a jejich dodržování zásad. Zásady pro zařízení pomáhají spravovat nejen zařízení vlastněná společností, která mají jednoho uživatele, ale také osobní zařízení uživatelů (BYOD), sdílená zařízení, jako jsou veřejné terminály, počítače v prodejnách nebo tablety sdílené více studenty ve třídě, a zařízení bez uživatelů (jenom iOS).

Každé zařízení využívá jinou platformu s jinými nastaveními. Zásady zařízení Intune ale fungují na všech těchto platformách, pro které poskytují následující možnosti správy mobilních zařízení:

-   Určení počtu zařízení, která si jednotliví uživatelé můžou zaregistrovat

-   Správa nastavení zařízení (například šifrování na úrovni zařízení, délka hesla nebo používání kamery)

-   Dodávání aplikací, e-mailových profilů, profilů VPN apod.

-   Vyhodnocení kritérií pro zásady dodržování předpisů zabezpečení na úrovni zařízení

> [!IMPORTANT]
> Zásady správy zařízení se nepřiřazují přímo jednotlivým zařízením nebo uživatelům, ale skupinám uživatelů. Zásady je možné použít přímo pro skupinu uživatelů a tím současně pro zařízení uživatelů, nebo je možné je použít pro skupinu zařízení a tím současně pro členy skupiny.

## <a name="task-list-for-device-compliance-policies"></a>Seznam kroků zavedení zásad dodržování předpisů pro zařízení

### <a name="task-1-add-device-groups-optional"></a>Krok 1: Přidání skupin zařízení (volitelné)

Skupiny zařízení můžete vytvořit, když potřebujete provádět různé úlohy správy, které jsou založené na identitě zařízení (místo na identitě uživatele).

Skupiny zařízení jsou užitečné ke správě zařízení bez vyhrazených uživatelů, jako jsou například zařízení v celoobrazovkovém režimu nebo zařízení sdílená pracovníky ve směnném provozu nebo přiřazená určitému umístění.

Když nakonfigurujete skupiny zařízení ještě před registrací zařízení, můžete využít kategorie zařízení k tomu, aby se zařazení při registraci automaticky seskupovala, a automaticky tak přijímala zásady zařízení příslušné skupiny. Další informace najdete v článku [Začínáme se skupinami](/intune/groups-get-started).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Krok 2: Použití profilů přístupu k prostředkům (sítím Wi-Fi, VPN a e-mailovým certifikátům)

Profily přístupu k prostředkům zřídí pro registrovaná zařízení certifikáty a nastaví konfiguraci přístupu.

Jak jsme uvedli v části o vyhodnocení požadavků na správu mobilních zařízení (MDM), pokud k ověřování používáte certifikáty, [nakonfigurujte je](/intune/certificates-configure).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Krok 3: Vytvoření a nasazení profilů konfigurace zařízení

Je potřeba vytvořit profil konfigurace zařízení k vynucení nastavení na úrovni zařízení, například: zakázání fotoaparátu nebo obchodu s aplikacemi, konfigurace režimu jedné aplikace, nastavení domovské obrazovky apod.

- Přečtěte si další informace o [profilech zařízení](/intune/device-profiles).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Přímý import profilů konfigurace iOSu (volitelné)

-   **Profily Apple Configuratoru pro iOS (7.1 a novější):** Pokud vaše existující řešení MDM používá profily Apple Configuratoru (soubory .mobileconfig), Intune je může přímo importovat jako vlastní zásady konfigurace.

-   **Zásady konfigurace mobilních aplikací pro iOS:** Pokud vaše existující řešení MDM používá zásady konfigurace mobilních aplikací pro iOS, Intune je může přímo importovat za předpokladu, že odpovídají formátu XML, který Apple používá pro seznamy vlastností.

- Zjistěte, jak přidat vlastní zásady pro [iOS](/intune/custom-settings-ios).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Krok 4: Vytvoření a nasazení zásad dodržování předpisů pro zařízení (volitelné)

Zásady dodržování předpisů pro zařízení vyhodnocují nastavení týkající se zabezpečení a vytvářejí sestavy, které ukazují, jestli jsou zařízení v souladu s firemními standardy. Zásady dodržování předpisů pro zařízení vyhodnocují faktory zabezpečení, jako jsou:

-   Délka PIN kódu

-   Stav jailbreaku

-   Verze operačního systému

Podívejte se na další materiály k nastavení kompatibility zařízení:

-   Informace o [zásadách dodržování předpisů pro zařízení](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Zjistěte, [jak vytvořit zásady dodržování předpisů pro zařízení](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Krok 5: Publikování a nasazení aplikací

Pokud používáte správu mobilních zařízení (MDM) v Intune, můžete zřídit aplikace – buď vyžádat jejich automatickou instalaci, nebo je zpřístupnit v aplikaci Portál společnosti.

-   Přečtěte si, [jak přidávat aplikace](/intune-classic/deploy-use/add-apps).

-   Přečtěte si, [jak nasazovat aplikace](/intune-classic/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Krok 6: Povolení registrace zařízení

Při registraci se na zařízení zřídí ovládací prvky pro správu. Zjistěte, [jak se připravit na registraci firemních zařízení a osobních zařízení uživatelů](/intune/device-enrollment).

## <a name="next-steps"></a>Další kroky 

[Konfigurace zásad ochrany aplikací (volitelné)](migration-guide-app-protection-policies.md)
