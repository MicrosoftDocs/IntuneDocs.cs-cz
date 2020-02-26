---
title: Řešení potíží se zařízeními s Androidem Enterprise v Microsoft Intune
description: Návrhy pro řešení některých nejběžnějších problémů při registraci zařízení s Androidem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/25/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 312f8ee3acb6b8be767d6349b29932ab65ae75d8
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77611028"
---
# <a name="troubleshoot-android-device-enrollment-problems-in-microsoft-intune"></a>Řešení potíží s registrací zařízení s Androidem v Microsoft Intune

Tento článek pomáhá správcům Intune pochopit a řešit problémy při registraci zařízení s Androidem v Intune.

## <a name="apps-on-android-devices"></a>Aplikace na zařízeních s Androidem

### <a name="managed-google-play-apps-that-arent-deployed-through-intune-are-displayed-in-the-work-profile"></a>Spravované Google Play aplikace, které nejsou nasazené prostřednictvím Intune, se zobrazují v pracovním profilu.
Systémové aplikace můžete v pracovním profilu povolit výrobcem OEM zařízení v době, kdy se pracovní profil vytvoří. Toto neřídí poskytovatel MDM.

K řešení potíží použijte následující postup:

  1. Shromáždí protokoly Portál společnosti.
  2. Všimněte si neočekávaných aplikací, které se zobrazují v pracovním profilu.
  3. Zruší registraci zařízení v Intune a odinstalace Portál společnosti.
  4. Nainstalujte aplikaci [test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) , která umožňuje vytvořit pracovní profil bez modulu EMM pro testování.
  5. Podle pokynů v části [test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) vytvořte pracovní profil na zařízení.
  6. Zkontrolujte aplikace, které se zobrazují v pracovním profilu. 
  7. Pokud se stejné aplikace zobrazují v aplikaci test DPC, aplikace je pro toto zařízení očekávána výrobcem OEM.

### <a name="unapproved-google-play-for-work-store-apps-arent-being-removed-from-the-mobile-apps-page-in-intune"></a>Neschválená Google Play pro aplikace z obchodu s pracovními aplikacemi se neodstraňují ze stránky Mobile Apps v Intune.
Toto chování je očekávané.

### <a name="managed-google-play-apps-arent-being-reported-under-the-discovered-apps-blade-in-the-intune-portal"></a>Spravované Google Play aplikace nejsou hlášeny v okně zjištěné aplikace na portálu Intune.
Toto chování je očekávané.

### <a name="are-web-applications-supported-for-work-profile-enrolled-devices"></a>Jsou webové aplikace podporované pro zařízení zaregistrovaná v pracovním profilu?
Momentálně ne.

## <a name="device-management"></a>Správa zařízení

### <a name="file-path-internal-storageandroiddatacommicrosoftwindowsintunecompanyportalfiles-missing-on-work-profile-enrolled-devices"></a>Cesta k souboru interní úložiště/Android/data. com. Microsoft. WindowsIntune. CompanyPortal/soubory chybějící v zaregistrovaných zařízeních pracovního profilu

  **Odpověď**: Toto chování je očekávané. Tato cesta je vytvořená jenom pro scénář Správce zařízení (starší verze registrace Androidu).

  Pokud chcete shromažďovat protokoly Portál společnosti, postupujte takto:

  1. V aplikaci Portál společnosti s označením klepněte na **nabídku** > **pomoc** > **e-mailová podpora**a potom klepněte na **Odeslat e-mail & Odeslat protokoly**. 
  2. Až se vám zobrazí výzva k **odeslání žádosti o podporu**, vyberte jednu z e-mailových aplikací.
  3. Správci IT se vygeneruje e-mail s ID incidentu, které je možné poskytnout podpoře produktů Microsoftu.

### <a name="managed-google-play-last-sync-time--hasnt-been-updated-in-days"></a>Čas poslední synchronizace spravovaného Google Play se neaktualizoval ve dnech.
Toto chování je očekávané. Synchronizace se spustí, jenom když to uděláte ručně.

### <a name="is-system-center-configuration-manager-hybrid-supported"></a>Je System Center Configuration Manager podporován hybridní?
Podporuje se s Configuration Manager 1702 a novějšími verzemi pro správu profilů práce. Vyhrazená zařízení (COSU) nejsou v hybridním scénáři podporovaná.

### <a name="encryption-is-required-when-a-device-is-enrolled-can-it-be-turned-off"></a>Když je zařízení zaregistrované, vyžaduje se šifrování. Může být vypnutá?
Ne, z Google pro pracovní profil se vyžaduje šifrování. 

### <a name="samsung-devices-are-blocking-the-use-of-third-party-keyboards-like-swiftkey"></a>Zařízení Samsung blokují použití klávesnic třetích stran, jako je SwiftKey.
Společnost Samsung začala toto omezení na zařízeních s Androidem 8.0 a novějším vynucovat. Společnost Microsoft v současnosti pracuje s Samsung na tomto problému a bude publikovat nové informace, jakmile bude k dispozici.

## <a name="remote-actions"></a>Vzdálené akce

### <a name="wipe-factory-reset-option-isnt-available-for-work-profile-enrolled-device"></a>Možnost vymazání (obnovení továrního nastavení) není k dispozici pro zařízení zaregistrovaná v pracovním profilu.
Toto chování je očekávané. Ve scénáři pracovního profilu nemá poskytovatel MDM úplnou kontrolu nad zařízením. Jediná dostupná možnost je vyřadit z provozu (odebrat firemní data), která odebere celý pracovní profil a veškerý jeho obsah.

### <a name="is-device-passcode-reset-supported"></a>Podporuje se resetování hesla zařízení?
U zaregistrovaných zařízení pracovního profilu můžete resetovat jenom heslo pracovního profilu na zařízeních s Androidem 8,0 a novějším, když:
- heslo k pracovnímu profilu je spravované.
- koncový uživatel ho může resetovat.

Pro vyhrazená zařízení (COSU) se podporuje resetování hesla zařízení.


## <a name="next-steps"></a>Další kroky

- [Řešení potíží s registrací zařízení v Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Zeptejte se fóra služby Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Podívejte se na blog týmu podpory Microsoft Intune.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Podívejte se na blog Microsoft Enterprise mobility and Security.](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)