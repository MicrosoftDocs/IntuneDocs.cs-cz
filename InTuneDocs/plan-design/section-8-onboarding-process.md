---
title: "Proces zavedení Intune | Dokumentace Microsoftu"
description: "V tomto článku najdete všechny podrobnosti, které je potřeba vzít v úvahu při zavádění cloudového řešení do vašeho prostředí."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fa33bd3833f7f7198eed3f4f486c27bae3ba47d7
ms.openlocfilehash: 87832ec7f295c08678052d19164af9a8db051f9f


---

# <a name="intune-implementation"></a>Implementace Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

V zaváděcí fázi budete Intune implementovat do svého produkčního prostředí. Proces implementace spočívá v nastavení a konfiguraci Intune a externích závislostí (pokud jsou potřeba) na základě [požadavků na použití](section-3-determine-use-case-requirements.md), které jste sestavili v předchozích částech tohoto průvodce.

Následující část nabízí přehledný popis procesu implementace Intune, včetně požadavků a nejdůležitějších úkolů.

>[!TIP]
> Další informace o procesu implementace Intune najdete v části [Další materiály a zdroje informací](additional-resources.md).

## <a name="intune-requirements"></a>Požadavky Intune

Tady jsou požadavky samotné služby Intune:

-   Předplatné EMS/Intune

-   Předplatné Office 365 (pro aplikace Office a aplikace spravované zásadou MAM)

-   Certifikát Apple APNs (pro správu platformy zařízení iOS)

-   Azure AD Connect (pro synchronizaci adresáře)

-   Místní konektor Intune pro Exchange (pro CA pro místní Exchange, pokud je potřeba)

-   Konektor certifikátu Intune (pro nasazení certifikátu SCEP, pokud je potřeba)

>[!TIP]
> Další informace o požadavcích samotné služby Intune najdete [zde](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune).

## <a name="intune-implementation-process"></a>Proces implementace Intune

### <a name="overview-of-implementation-tasks"></a>Přehled implementačních úkolů

Tady je přehled všech úkolů při implementaci Intune.

#### <a name="task-1-add-intune-subscription"></a>1. úkol: Přidání předplatného Intune

V předchozí části věnované požadavkům jsme uvedli, že je potřeba předplatné EMS nebo Intune. Pokud organizace nemá předplatné EMS nebo Intune, obraťte se na Microsoft nebo na tým, které se stará o účty Microsoft, a informujte je, že se zajímáte o nákup řešení Enterprise Mobility + Security (EMS) nebo Intune.

-   Další informace o [nákupu Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>2. úkol: Přidání předplatného Office 365

Tento krok je nepovinný. V předchozí části věnované požadavkům jsme uvedli, že pokud plánujete používat Exchange Online a chcete spravovat mobilní aplikace Office pomocí zásad MAM, potřebujete předplatné Office 365. Pokud organizace nemá předplatné Office 365, obraťte se na Microsoft nebo na tým, které se stará o účty Microsoft, a informujte je, že se zajímáte o nákup Office 365.

-   Další informace o [nákupu Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>3. úkol: Přidání skupin uživatelů do Azure AD

Na základě scénáře použití a požadavků na nasazení Intune možná bude potřeba přidat do služby AD nebo AAD uživatele nebo skupiny zabezpečení. Zkontrolujte současné uživatele a skupiny zabezpečení ve službě Active Directory nebo Azure Active Directory a zjistěte, jestli plně odpovídají vašim potřebám. Noví uživatelé a skupiny zabezpečení se nejčastěji přidávají v Active Directory a synchronizují se s Azure Active Directory prostřednictvím služby Azure AD Directory Connect.

-   Další informace o [přidání uživatelů nebo skupin v Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>4. úkol: Přiřazení uživatelských licencí Intune a Office 365

Všichni uživatelé, u kterých budete zavádět EMS/Intune a Office 365, musí mít přiřazenou licenci. Licence k EMS/Intune a Office 365 můžete přiřadit na portálu Centra pro správu Office 365.

-   Další informace o [přiřazení licencí Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>5. úkol: Nastavení autority pro správu mobilních zařízení v Intune

Než začnete v Intune nastavovat, konfigurovat, spravovat a registrovat zařízení, musíte nastavit autoritu pro správu mobilních zařízení v Intune. Autoritu pro správu mobilních zařízení nastavíte na portálu pro správu Intune v pracovním prostoru správce.

-   Další informace o [nastavení autority pro správu mobilních zařízení](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>6. úkol: Povolení platforem zařízení

Ve výchozím nastavení je v konzole pro správu Intune povolena většina platforem zařízení. Výjimkou jsou zařízení Apple (iOS a Mac). Předtím, než budete v Intune registrovat a spravovat zařízení s iOS, musíte tuto platformu zařízení povolit. Povolení platformy pro zařízení s iOSem se skládá ze tří kroků: vytvoření certifikátu APNs, jeho stažení a nahrání tohoto certifikátu do Intune.

-   Další informace o tom, [jak funguje nastavení správy zařízení iOS a Mac](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>7. úkol: Přidání a nasazení zásad pro podmínky a ujednání

Microsoft Intune podporuje přidání a nasazení zásad pro podmínky a ujednání. Zásady pro podmínky a ujednání můžete přidat na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby přidejte zásady pro podmínky a ujednání a nasaďte je u cílových skupin na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [přidání a nasazení zásad pro podmínky a ujednání](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>8. úkol: Přidání a nasazení zásad konfigurace

Microsoft Intune podporuje přidání a nasazení dvou typů zásad konfigurace: obecných a vlastních. Zásady konfigurace můžete přidat na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby přidejte zásady konfigurace a nasaďte je u cílových skupin na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [přidání a nasazení zásad konfigurace](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>9. úkol: Přidání a nasazení profilů prostředků

Microsoft Intune podporuje profily e-mailu, Wi-Fi a VPN. Přidání a nasazení profilů se provádí na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby přidejte profily e-mailu, Wi-Fi a VPN a nasaďte je u cílových skupin na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [povolení přístupu k firemním prostředkům v Intune](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>10. úkol: Přidání a nasazení aplikací

Microsoft Intune podporuje nasazení webových aplikací, obchodních aplikací a aplikací z veřejného Storu. Služba také podporuje správu aplikací integrovaných do sady Intune SDK jejich přidružením k zásadám MAM. Aplikace můžete přidat a nasadit na portálu pro správu Intune v pracovním prostoru Aplikace. Zásady MAM můžete přidat na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby přidejte aplikace a nasaďte je u cílových skupin na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [přidání a nasazení aplikací](https://docs.microsoft.com/en-us/intune/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>11. úkol: Přidání a nasazení zásad dodržování předpisů

Microsoft Intune podporuje zásady dodržování předpisů. Zásady dodržování předpisů můžete přidat a nasadit na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby přidejte zásady dodržování předpisů a nasaďte je u cílových skupin na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [zásadách dodržování předpisů](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>12. úkol: Povolení zásad podmíněného přístupu

Microsoft Intune podporuje podmíněný přístup pro Exchange Online i pro místní Exchange, dále pro SharePoint Online, Online Skype pro firmy a Dynamics CRM Online. Zásady podmíněného přístupu povolíte na portálu pro správu Intune v pracovním prostoru Zásady. Podle potřeby povolte a nakonfigurujte podmíněný přístup na základě [způsobu použití nasazené služby Intune a požadavků](section-3-determine-use-case-requirements.md).

-   Další informace o [podmíněném přístupu](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>13. úkol: Registrace zařízení

Intune podporuje tyto platformy zařízení: iOS, Mac OS, Android, Windows pro stolní počítače a Windows Mobile. Podle potřeby zaregistrujte požadované platformy mobilních zařízení na základě způsobu použití nasazené služby Intune a požadavků.

-   Další informace o [registraci zařízení](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Další informace o procesu implementace Intune najdete v tomto [modulu relací Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676).

## <a name="next-section"></a>Další část

Další část obsahuje pokyny k [testování a ověřování nasazeného řešení Intune](section-9-test-and-validation.md).



<!--HONumber=Dec16_HO5-->


