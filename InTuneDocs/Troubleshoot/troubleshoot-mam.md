---
title:
- "Řešení potíží se správou mobilních aplikací | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Řešení potíží se správou mobilních aplikací

Pokud máte problémy se správou mobilních aplikací, začněte tady. Toto téma popisuje některé běžné problémy, na které můžete narazit, a jejich řešení.


**Problém:** MAM bez zásad registrace z konzoly Azure se nevztahuje na aplikaci Skype pro firmy na zařízeních se systémem iOS a Android.

Řešení: Skype pro firmy je nutné nastavit pro moderní ověřování.  Pokud chcete pro Skype nastavit moderní ověřování, řiďte se pokyny v tématu [Povolení tenanta pro moderní ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

**Problém:** MAM bez zásad registrace se nevztahuje na žádnou z podporovaných aplikací Office [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] pro jakéhokoli uživatele.
 
Řešení: Potvrďte, že uživatel má licenci ke službě Intune.  

**Problém:** Správce IT nemůže na webu Azure Portal nakonfigurovat zásady MAM

Řešení: K webu Azure Portal mají přístup následující role:

- Globální správce, kterého můžete nastavit na [Portálu Office](http://portal.office.com/)
- Vlastník, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).
- Přispěvatel, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).

Nápovědu k nastavení těchto rolí najdete v tématu [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). 

**Problém:** V sestavě aplikací se nezobrazují uživatelé, na které jsme v poslední době zacílili zásady MAM.

Řešení: Než se uživatelé nově zacílení pomocí zásad MAM zobrazí v sestavách jako cíloví uživatelé, může uplynout až 24 hodin. 

**Problém:** Než se změny/aktualizace zásad projeví, může uplynout až 8 hodin.  

Řešení: Koncový uživatel se může z aplikace odhlásit a znovu přihlásit, aby vynutil synchronizaci se službou.  

**Problém:** Zásady MAM se nevztahují na zařízení v programu Apple DEP

Řešení: Zkontrolujte, jestli používáte spřažení uživatelů s Programem registrace zařízení Apple (DEP). Spřažení uživatelů je požadováno u všech aplikací vyžadujících ověření uživatele pod programem DEP.
Další informace o registraci DEP pro iOS najdete v tématu [Registrace zařízení s iOS vlastněných společností do programu registrace zařízení DEP](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### Viz taky
- [Jak ověřit nastavení správy mobilních aplikací](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


