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
ms.openlocfilehash: 2f698f03ed3c7523ef1d768d2a1361d6d1a55008
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883874"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>Registrace zařízení pro přístup k pracovním nebo školním prostředkům
Pokud chcete své zařízení zaregistrovat a získat přístup k e-mailu a aplikacím, musíte nainstalovat aplikaci Portál společnosti Intune nebo aplikaci Microsoft Intune. Když se zaregistrujete, na vaše zařízení se aplikují základní zásady správy, které vaše organizace nakonfigurovala, jako je třeba heslo, PIN a šifrování. Jakmile nastavení zařízení vyhoví všem požadavkům vaší organizace, můžete k pracovním informacím bezpečně přistupovat prakticky odkudkoli.  

Aplikace Portál společnosti a Microsoft Intune zajišťují zabezpečení zaregistrovaných zařízení tím, že zajistí, že nastavení zařízení odpovídají zásadám vaší organizace. 

Aplikace Portál společnosti taky:  
* Zachovává vaše osobní a pracovní informace oddělené.  
* Umožňuje snadno najít a nainstalovat relevantní pracovní a školní aplikace.   

## <a name="get-the-apps"></a>Získat aplikace
Postup získání Portál společnosti:

- Nainstalujte aplikaci Portál společnosti z obchodu s aplikacemi pro konkrétní platformu. V některých případech vám vaše organizace nainstaluje Portál společnosti aplikaci.  
- Přejděte na [web portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980) , abyste měli přístup k aplikaci z prohlížeče.  

Pokud potřebujete použít aplikaci Microsoft Intune, vaše organizace je nainstaluje za vás.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Jaké informace může moje společnost vidět při registraci?
Po registraci zařízení uvidí pracovníci podpory vaší organizace jenom informace, které jsou relevantní pro práci. Nevidí vaše osobní údaje. Pokud zaregistrujete osobní zařízení pro použití v práci, Seznamte se [přesně s tím, co se může a nedá zobrazit](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Jaký je rozdíl mezi aplikacemi a webem?
Aplikace Portál společnosti je dostupná pro zařízení s Windows 10, iOS, macOS a Androidem. Bez problémů se integruje s příslušnou platformou vašeho zařízení. Verze webu je přístupná z libovolného zařízení a nabízí stejné, univerzální prostředí bez ohledu na to, jaké zařízení používáte. 

Aplikace Microsoft Intune je určena pro zařízení s Androidem vlastněná společností.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Jaký druh zařízení je možné zaregistrovat v Portál společnosti?
- Zařízení Apple používající iOS (například iPhone a iPad) a macOS (například MacBook a iMac)
- Zařízení se systémem Android
- Zařízení s Windows
  - Windows 10 Mobile
  - Windows 10 Desktop
  - Windows Phone 8.1
  - Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Jaký druh zařízení je možné zaregistrovat v aplikaci Microsoft Intune?  
Můžete zaregistrovat zařízení s Androidem vlastněná společností, která vaše organizace nastavila pro použití s aplikací. Aplikace podporuje Android 6,0 a novější. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Můžete z Portálu společnosti odebrat počítač nebo zařízení?
Počítač nebo zařízení můžete z Portálu společnosti odebrat nebo obnovit. Mezi **odebráním** a **obnovením** je rozdíl.

Když počítač nebo zařízení odeberete z Portál společnosti, zrušíte tím registraci zařízení v Intune. Při zrušení registrace se už z tohoto zařízení nedostanete na Portál společnosti a můžou se z něho odebrat některá firemní data. Informace o tom, jak odebrat zařízení z Portál společnosti, najdete na následujících odkazech:  

- [Zrušení registrace zařízení s Androidem](unenroll-your-device-from-intune-android.md)
- [Zrušení registrace zařízení s iOSem](unenroll-your-device-from-intune-ios.md)
- [Zrušení registrace zařízení s macOS](unenroll-your-device-from-intune-macos.md)
- [Zrušení registrace zařízení s Windows](unenroll-your-device-from-intune-windows.md)

Když počítač nebo zařízení resetujete, Portál společnosti se pokusí resetovat počítač nebo zařízení zpátky na výchozí nastavení výrobce. Po resetování zařízení se ze zařízení odeberou všechna firemní a osobní data. Pokud jste ztratili svoje zařízení, můžete ho také vzdáleně obnovit z Portál společnosti webu.  

Informace o tom, jak resetovat zařízení, najdete v tématu [resetování zařízení na webu portál společnosti](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Můžete počítač nebo zařízení odebrat z aplikace Microsoft Intune?
Ne, k dispozici není žádný způsob, jak odebrat zařízení vlastněná společností z aplikace Microsoft Intune.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>Co když mi moje zařízení nevidím v Portál společnosti nebo v aplikaci Microsoft Intune?
Abyste zařízení viděli, musíte ho na Portál společnosti napřed přidat. Přejděte na Portál společnosti, který vám doporučil správce, a postupujte podle pokynů pro vaše zařízení. Neuvidíte taky zařízení vlastněná a spravovaná vaší společností.

Pokud používáte aplikaci Microsoft Intune, zobrazí se jenom zařízení, které právě používáte. Jiná zaregistrovaná zařízení se v aplikaci nezobrazí.  

## <a name="where-else-can-i-go-for-help"></a>Kde jinde ještě můžu požádat o pomoc?  
Pokud chcete řešit běžné problémy a otázky, podívejte se na tyto dokumentace pro konkrétní platformu:  

- [Řešení běžných problémů se zařízením s Androidem](check-compliance-on-your-device-android.md)  
- [Řešení běžných problémů se zařízením s iOSem](troubleshoot-your-device-ios.md)
- [Řešení běžných problémů se zařízením s macOS](troubleshoot-your-device-macos.md)
- [Řešení běžných problémů se zařízením s Windows](troubleshoot-your-device-windows.md)

Můžete se také obrátit na pracovníka podpory. Aplikace Portál společnosti a Microsoft Intune nabízejí stránky pro nápovědu a podporu, které uvádějí kontaktní informace a způsoby, jak ohlásit problém. Kontaktní informace jsou také k dispozici na [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)vaší organizace.  

## <a name="next-steps"></a>Další postup  

Získejte nápovědu od registrace, která je specifická pro platformu vašeho zařízení:  

- [Použití zařízení s Androidem](using-your-android-device-with-intune.md)
- [Používání zařízení s iOSem](using-your-ios-device-with-intune.md)
- [Používání zařízení s macOS](using-your-macos-device-with-intune.md)
- [Použití zařízení s Windows](using-your-windows-device-with-intune.md)
- [Použití webu Portál společnosti](using-the-intune-company-portal-website.md)


