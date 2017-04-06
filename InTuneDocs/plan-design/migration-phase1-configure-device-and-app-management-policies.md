---
title: "Konfigurace zásad dodržování předpisů zařízením a správy aplikací během migrace Intune | Dokumentace Microsoft"
description: "Tento článek popisuje kroky potřebné ke konfiguraci zásad dodržování předpisů zařízením a správy aplikací během migrace Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 5904b117ccab9046d2afde4a761b4724431a6302
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Fáze 1: Konfigurace zásad dodržování předpisů zařízením a správy aplikací

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

[Klasický portál Intune](https://manage.microsoft.com/) umožňuje vytvářet skupiny zařízení, které využijete, pokud chcete provádět různé úlohy správy podle identity zařízení, ne podle identity uživatelů.

Skupiny zařízení jsou užitečné ke správě zařízení bez vyhrazených uživatelů, jako jsou například zařízení v celoobrazovkovém režimu nebo zařízení sdílená pracovníky ve směnném provozu nebo přiřazená určitému umístění.

Když nakonfigurujete skupiny zařízení ještě před registrací zařízení, můžete využít kategorie zařízení k tomu, aby se zařazení při registraci automaticky seskupovala, a automaticky tak přijímala zásady zařízení příslušné skupiny.

-   Zjistěte, [jak přidat skupiny zařízení](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5).

-   Zjistěte, [jak konfigurovat kategorie zařízení](https://docs.microsoft.com/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Krok 2: Použití profilů přístupu k prostředkům (sítím Wi-Fi, VPN a e-mailovým certifikátům)

Profily přístupu k prostředkům zřídí pro registrovaná zařízení certifikáty a nastaví konfiguraci přístupu.

Jak bylo uvedeno výše v části Vyhodnocení požadavků na MDM, musíte mít [zavedenou infrastrukturu PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles), abyste mohli nasazovat sítě VPN a Wi-Fi a e-mailové certifikáty, pokud používáte ověřování pomocí certifikátů.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Přímý import profilů přístupu k prostředkům (volitelné)

Pokud je v existujícím řešení MDM mechanismus pro export profilů e-mailu, Wi-Fi a VPN do formátu XML, stačí, když soubor XML zkusíte naimportovat do Intune pomocí OMA-URI a vytvoříte tak vlastní profily pro zařízení s iOSem, Androidem a Windows.

-   Zjistěte, jak přidat vlastní zásady pro zařízení s [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune), [Androidem](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune) a [Windows](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Krok 3: Vytvoření a nasazení profilů konfigurace zařízení

Je potřeba vytvořit profil konfigurace zařízení k vynucení nastavení na úrovni zařízení, například: zakázání fotoaparátu nebo obchodu s aplikacemi, konfigurace režimu jedné aplikace, nastavení domovské obrazovky apod.

- Informace o [profilech konfigurace zařízení](https://docs.microsoft.com/intune-azure/configure-devices/how-to-create-device-profiles).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Přímý import profilů konfigurace iOSu (volitelné)

-   **Profily Apple Configuratoru pro iOS (7.1 a novější):** Pokud vaše existující řešení MDM používá profily Apple Configuratoru (soubory .mobileconfig), Intune je může přímo importovat jako vlastní zásady konfigurace.

-   **Zásady konfigurace mobilních aplikací pro iOS:** Pokud vaše existující řešení MDM používá zásady konfigurace mobilních aplikací pro iOS, Intune je může přímo importovat za předpokladu, že odpovídají formátu XML, který Apple používá pro seznamy vlastností.

- Zjistěte, jak přidat vlastní zásady pro [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Krok 4: Vytvoření a nasazení zásad dodržování předpisů pro zařízení (volitelné)

Zásady dodržování předpisů pro zařízení vyhodnocují nastavení týkající se zabezpečení a vytvářejí sestavy, které ukazují, jestli jsou zařízení v souladu s firemními standardy. Zásady dodržování předpisů pro zařízení vyhodnocují faktory zabezpečení, jako jsou:

-   Délka PIN kódu

-   Stav jailbreaku

-   Verze operačního systému

Podívejte se na další materiály k nastavení kompatibility zařízení:

-   Informace o [zásadách dodržování předpisů pro zařízení](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Zjistěte, [jak vytvořit zásady dodržování předpisů pro zařízení](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Krok 5: Publikování a nasazení aplikací

Pokud používáte správu mobilních zařízení (MDM) v Intune, můžete zřídit aplikace – buď vyžádat jejich automatickou instalaci, nebo je zpřístupnit v aplikaci Portál společnosti.

-   Přečtěte si, [jak přidávat aplikace](https://docs.microsoft.com/intune/deploy-use/add-apps).

-   Přečtěte si, [jak nasazovat aplikace](https://docs.microsoft.com/intune/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Krok 6: Povolení registrace zařízení

Při registraci se na zařízení zřídí ovládací prvky pro správu.

-   Zjistěte, [jak se připravit na registraci firemních zařízení a osobních zařízení uživatelů](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

-   Přečtěte si, [jak zaregistrovat firemní zařízení](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices).

Pokud potřebujete zaregistrovat sdílená zařízení nebo zařízení bez uživatelů, můžete použít [účet správce registrace zařízení (DEM)](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>Další kroky 

[Fáze 1: Konfigurace zásad ochrany aplikací (volitelné)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

