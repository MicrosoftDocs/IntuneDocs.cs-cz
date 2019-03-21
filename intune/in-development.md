---
title: Při vývoji – Microsoft Intune
titlesuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2310f9720c64301a3ea25631e1e8688d88a001e4
ms.sourcegitcommit: 768430b5296573c6e007ae4e13d57aeda4be4b7e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58306817"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>Při vývoji pro Microsoft Intune – březen 2019

Pomáhat při vaší připravenosti a plánování, tato stránka seznamy uživatelské rozhraní Intune aktualizuje a funkce, které jsou ve vývoji, ale ještě není. Navíc platí:

- Pokud předpokládáme, že budete muset udělat před změnu, budeme publikovat praktického příspěvek Centru zpráv Office.
- Když funkce se spustí v produkčním prostředí, buď ve verzi preview nebo obecně k dispozici, popis funkce se přesune mimo tuto stránku a na [stránce s novinkami](whats-new.md).
- Na této stránce a [stránce s novinkami](whats-new.md) jsou pravidelně aktualizovány. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Odkazovat [M365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) pro strategické dodávky a časovými osami.

> [!Note]
> Tyto položky odrážejí aktuální očekávání společnosti Microsoft o možnostech Intune v budoucí verzi. Data a jednotlivé funkce mohou změnit. Ne všechny položky ve vývoji mají popis funkce na této stránce.

**Informační kanál RSS**: Nechte se informovat Tato stránka se aktualizuje zkopírováním a vložením do informačního kanálu čtečky na následující adrese URL: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal


<!-- 1903 start-->

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Značky oboru pro zásady Konfigurace aplikací <!--2371891 -->
Budete moct přidat značku oboru pro zásady Konfigurace aplikací tak, aby pouze uživatelé s rolí také přiřadit značky oboru přístupu pro zásady Konfigurace aplikací. Zásady Konfigurace aplikací můžete pouze cílené na nebo přidružené aplikace přiřazené stejné značka oboru.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Přiřazení profilů Autopilot na všechny virtuální skupiny zařízení <!--2715522 -->
Profily Autopilotu budete moct přiřadit virtuální skupině Všechna zařízení. Uděláte to tak, že vyberete **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil > **Přiřazení** > v části **Přiřadit k** vyberte **Všechna zařízení**. Další informace o profilech Autopilotu najdete v článku [Registrace zařízení s Windows pomocí Windows Autopilotu](enrollment-autopilot.md).

### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523----"></a>Instalovat dostupné aplikace pomocí aplikace portál společnosti po Windows hromadný zápis <!-- 2751523  -->
Zařízení Windows, která zaregistrovaná v Intune pomocí [Windows hromadnou registraci](windows-bulk-enroll.md) (zřizovacích balíčků) budete moct používat aplikaci portál společnosti instalovat aplikace k dispozici. Další informace o aplikaci portál společnosti, naleznete v tématu [ručně přidat portál společnosti pro Windows 10](store-apps-company-portal-app.md) a [konfigurace aplikace portál společnosti Microsoft Intune](company-portal-app.md).

### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430---"></a>Značky oboru pro zřizovací profily aplikací pro iOS <!--2934430 -->
Budete moct přidat značku oboru do zřizovacího profilu aplikace iOS tak, aby pouze uživatelé s rolí také přiřadit značky oboru mít přístup k zřizovací profil aplikace pro iOS. 

### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477----"></a>Nástroj pro nasazení Office (ODT) XML pro nasazení Office ProPlus <!-- 3192477  -->
Budete moct poskytovat nástroj pro nasazení Office (ODT) XML při vytváření instance Office Pro Plus v konzole správce Intune. To vám umožní větší přizpůsobitelnost, pokud existující možnosti uživatelského rozhraní Intune nevyhovují vašim potřebám. 

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Zablokovat uživatelům hledání aktualizací Windows    <!-- 3316758    -->
Přidáváme nové Windows aktualizační kanál nastavení, které můžete použít, který se zablokuje uživatelům možnost skenování pro aktualizace Windows. Toto nastavení nebude k dispozici v rámci portálu, ale dá se s použitím rozhraní Intune Graph API.

### <a name="windows-update-notifications-----3316782---"></a>Oznámení o aktualizaci Windows  <!-- 3316782 -->
Konfigurace aktualizačního kanálu Windows Update Doplňujeme podporu, takže budete moci konfigurovat oznámení o aktualizaci Windows, které se uživatelům zobrazí. Toto nastavení nebude k dispozici v rámci portálu, ale dá se s použitím rozhraní Intune Graph API.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Změny registrace pomocí portálu společnosti pro uživatele zařízení s Iosem 12 <!--3448635 -->  
Portál společnosti pro iOS budou aktualizace obrazovek registrace aplikace a postupy, které bylo v souladu s MDM změny registrace v Apple iOS 12.2. Aktualizovaný pracovní postup bude nyní vyzvat uživatele, aby:

- Povolit Safari otevřít na webu portál společnosti (přes Safari) a stáhněte profil správy před návratem do aplikace portál společnosti. 
- Otevřete aplikaci nastavení na instalaci profilu správy na svém zařízení.
- Vraťte se do aplikace portál společnosti, aby prošel registrací.  

Další informace o tom, jak můžete připravit pro tyto změny najdete v tématu [technické komunitě Microsoftu příspěvek](https://aka.ms/CP_changes_iOS12). Do té doby pro podporu nové registrace iOS v aplikaci portál společnosti, jsme aktualizovali kroky v [zaregistrovat zařízení s Iosem v Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Po vydání iOS verze 12.2 Apple, budou tyto změny dokumentu za provozu. 

### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202-------"></a>Podpora pro další konektory na stránce Stav Tenanta. <!-- 3617202     -->
Na stránce Stav Tenanta se zobrazí informace o dalších konektorů, včetně stavu *rozšířené ochrany před internetovými útoky programu Windows Defender* (ATP) a dalším konektorům Mobile Threat Defense.

### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917---"></a>Udělení Intune přístup pro čtení jenom k několik rolí Azure Active Directory <!-- 3637917 -->
Jsme budete udělení, že Intune přístup pro čtení jenom k následující role Azure AD. Oprávnění udělená role Azure AD mají přednost před oprávněním s Intune řízení přístupu na základě role (RBAC).

Číst pouze přístup k datům auditování Intune:

- Správce dodržování předpisů
- Správce dat dodržování předpisů

Přístup jen ke čtení ke všem datům Intune:

- Správce zabezpečení
- Operátor zabezpečení
- Čtenář zabezpečení
- Globální čtečky

### <a name="easier-access-to-diagnostic-settings------3804627-----"></a>Jednodušší přístup k nastavení diagnostiky   <!-- 3804627   -->
Přidáváme novou možnost, jak **protokoly auditu** okno v každé v každé úloze protokolu auditu v konzole Intune, který vám umožní otevřít přímo *nastavení diagnostiky* stránky.

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Vytváření a používání profilů konfigurace zařízení na zařízeních s Androidem Zebra v Intune <!-- 3895244  -->
Intune bude podporovat konfiguraci zařízení s Androidem Zebra. Konkrétně budete moci: 

- Vytvořit profil konfigurace zařízení a použijte nastavení na zařízení s Androidem Zebra pomocí profilů rozšíření Mobility (MX) generovaných StageNow (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Android** pro platformu).

Platí pro:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 1672660  -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
