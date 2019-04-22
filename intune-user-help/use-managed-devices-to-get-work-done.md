---
title: Práce pomocí spravovaných zařízení | Dokumentace Microsoftu
description: Seznámíte se s principy registrace zařízení za účelem správy v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54bdef2252467de9cd06e5b5f0a7c38acc38ba88
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898374"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>Registrace zařízení pro přístup k pracovním nebo školním prostředkům
Registrace zařízení a získat přístup k e-mailu a aplikacím, budete muset nainstalovat aplikaci portál společnosti Intune nebo aplikace pro Microsoft Intune. Při registraci, základní správu zásad, které vaše organizace má nakonfigurovanou, jako jsou hesla, PIN kód a šifrování, se použijí k zařízení. Po nastavení zařízení splňovat všechny požadavky vaší organizace, budete mít bezpečný přístup pracovním informacím prakticky odkudkoli.  

Aplikace portál společnosti a Microsoft Intune zabezpečit zaregistrovaných zařízení tím, že zajišťuje, že nastavení zařízení odpovídat zásadám vaší organizace. 

Aplikace portál společnosti také:  
* Udržuje odděleně váš osobní i pracovní informace.  
* Umožňuje snadno najít a nainstalovat relevantní pracovní a školní aplikace.   

## <a name="get-the-apps"></a>Získat aplikace
Pokud chcete získat portál společnosti:

- Nainstalujte aplikaci portál společnosti z obchodu s aplikacemi pro konkrétní platformu. V některých případech může vaše organizace nainstaluje aplikaci portál společnosti pro vás.  
- Přejděte [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980) přístup k aplikaci v prohlížeči.  

V případě potřeby k používání aplikace Microsoft Intune vaší organizaci ho nainstaluje.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Jaké informace Moje společnost uvidí, když si zaregistruji?
Po registraci vašeho zařízení, uživatelé vaší organizace podpory uvidí jenom informace, které jsou relevantní pro práci. Neuvidí vaše osobní údaje. Pokud registrujete svoje osobní zařízení pro použití v práci, [další přesně co uvidí nebo nemůže být zobrazena](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Jaký je rozdíl mezi aplikací a webem?
Aplikace portál společnosti je k dispozici pro Windows 10, iOS, macOS a androidem. Bez problémů integruje s příslušné platformy zařízení. Webová verze je přístupný z jakéhokoli zařízení a umožňuje využít možnosti stejné a univerzálního bez ohledu na to, jaké zařízení používáte. 

Aplikace pro Microsoft Intune je pro zařízení s Androidem vlastněných společností.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Jaký druh zařízení můžete zaregistrovat pomocí portálu společnosti?
-   Zařízení Apple používající iOS (například iPhone a iPad) a macOS (například MacBook a iMac)
-   Zařízení se systémem Android
-   Zařízení s Windows
    -   Windows 10 Mobile
    -   Windows 10 Desktop
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Jaký druh zařízení můžete zapsat pomocí aplikace pro Microsoft Intune?  
Můžete registraci firemních zařízení s Androidem, které vaše organizace má nastavení pro použití s aplikací. Aplikace podporuje Android 6.0 nebo novější. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Můžete z Portálu společnosti odebrat počítač nebo zařízení?
Počítač nebo zařízení můžete z Portálu společnosti odebrat nebo obnovit. Mezi **odebráním** a **obnovením** je rozdíl.

Když odeberete počítač nebo zařízení z portálu společnosti, zrušíte tím registraci zařízení v Intune. Při zrušení registrace se už z tohoto zařízení nedostanete na Portál společnosti a můžou se z něho odebrat některá firemní data. Informace o odebrání zařízení z portálu společnosti, najdete na následujících odkazech:  

- [Zrušení registrace zařízení s Androidem](unenroll-your-device-from-intune-android.md)
- [Zrušení registrace zařízení s iOSem](unenroll-your-device-from-intune-ios.md)
- [Zrušení registrace zařízení s macOS](unenroll-your-device-from-intune-macos.md)
- [Zrušení registrace zařízení s Windows](unenroll-your-device-from-intune-windows.md)

Když počítač nebo zařízení resetujete, portál společnosti se pokusí obnovit svůj počítač nebo zařízení výchozí nastavení od výrobce. Při obnovení odebere všechna firemní i osobní data ze zařízení. Pokud jste ztratili svoje zařízení, můžete také v něm obnovit vzdáleně z webu portál společnosti.  

Zjistěte, jak resetuji svoje zařízení, najdete v článku [resetování zařízení z webu portál společnosti](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Můžete odebrat počítač nebo zařízení z aplikace pro Microsoft Intune?
Ne, není žádný způsob, jak odebrat zařízení vlastněných společností z aplikace pro Microsoft Intune.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>Co dělat, pokud nevidím svoje zařízení v aplikaci portál společnosti nebo Microsoft Intune?
Abyste zařízení viděli, musíte ho na Portál společnosti napřed přidat. Přejděte na Portál společnosti, který vám doporučil správce, a postupujte podle pokynů pro vaše zařízení. Neuvidíte taky zařízení vlastněná a spravovaná vaší společností.

Pokud používáte aplikace pro Microsoft Intune, uvidíte jenom zařízení, které aktuálně používáte. Jiných zaregistrovaných zařízení se vám nezobrazí v aplikaci.  

## <a name="where-else-can-i-go-for-help"></a>Kde jinde ještě můžu požádat o pomoc?  
Pokud chcete vyřešit běžné problémy a otázky, přečtěte si tyto specifické pro platformu dokumentace:  

- [Řešení běžných problémů se zařízením s Androidem](check-compliance-on-your-device-android.md)  
- [Řešení běžných problémů se zařízením s iOSem](troubleshoot-your-device-ios.md)
- [Řešení běžných problémů se zařízením s macOS](troubleshoot-your-device-macos.md)
- [Řešení běžných problémů se zařízením s Windows](troubleshoot-your-device-windows.md)

Můžete také kontaktovat pro pracovníka podpory. Aplikace portál společnosti a aplikace pro Microsoft Intune nabízí pomoc a podporu stránky, které uvádějí kontaktní informace a způsoby, jak ohlásit problém. Kontaktní informace je také dostupný ve vaší organizaci [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="next-steps"></a>Další postup  

Získejte pomoc při zahájení práce s registrací, který je specifický pro platformu vašeho zařízení:  

- [Použití zařízení s Androidem](using-your-android-device-with-intune.md)
- [Používání zařízení s iOSem](using-your-ios-device-with-intune.md)
- [Používání zařízení s macOS](using-your-macos-device-with-intune.md)
- [Použití zařízení s Windows](using-your-windows-device-with-intune.md)
- [Použití webu Portál společnosti](using-the-intune-company-portal-website.md)


