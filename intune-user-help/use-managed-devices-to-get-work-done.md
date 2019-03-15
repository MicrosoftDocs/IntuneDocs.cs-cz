---
title: Práce pomocí spravovaných zařízení | Dokumentace Microsoftu
description: Seznámíte se s principy registrace zařízení za účelem správy v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: robstack
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7b67f1484ed74bd538cad53f02babd542b77fff
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838831"
---
# <a name="use-managed-devices-to-access-work-or-school-resources"></a>Pomocí spravovaných zařízení měl přístup k pracovním nebo školním prostředkům
Microsoft Intune je systém správy zařízení, která organizacím umožňuje spravovat přístup k zařízení, aplikacím a e-mailu. Správa zařízení umožní a jiné zaměstnance a studenty, pro přístup k pracovním informacím prakticky odkudkoli na téměř jakémkoli zařízení. I v případě, že pracujete vzdáleně, zůstane zabezpečené jste a informace o vaší organizaci.

Microsoft Intune je software, vaše společnost používá ke konfiguraci jejich zabezpečení a požadavky na zařízení. Až budete připravení nechte si spravovat zařízení, budete používat aplikaci portál společnosti Intune. S touto aplikací vám pomůže zařízení měl přístup k pracovním nebo školním prostředkům. 

## <a name="what-information-can-my-company-see-when-i-get-my-device-managed"></a>Jaké informace Moje společnost uvidí při získat Moje zařízení spravované?
Jakmile máte nastavíte v aplikaci portál společnosti, podpora vaší společnosti uvidí jenom informace, které jsou relevantní pro práci. Neuvidí vaše osobní údaje. To je důležité vědět, když registrujete svoje osobní zařízení, abyste ho používali v práci. Přesně jaké jsou další [uvidí a neuvidí v dalším článku](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

## <a name="how-do-i-get-company-portal"></a>Jak získám portál společnosti?
Portál společnosti Get buď:

- Instalace aplikace portál společnosti na vašem zařízení. Aplikaci Portál společnosti získáte zpravidla v obchodě s aplikacemi pro vaše zařízení, může vám ji ale také nainstalovat firemní podpora.
- Chystáte [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980) , aby nastavila vaše firemní podpora nahoru.

## <a name="whats-the-difference-between-the-app-and-the-website"></a>Jaký je rozdíl mezi aplikací a webem?
Každá aplikace portál společnosti pro Windows 10, iOS, macOS a Android se bez problémů integruje s příslušné platformy zařízení. Na webu je přístupný z jakéhokoli zařízení a umožňuje využít možnosti stejné a univerzálního bez ohledu na to, jaké zařízení používáte. 

Najdete pokyny k portálu společnosti specifické pro platformu vašeho zařízení, počínaje kroky registrace, v části na následujících odkazech:  

- [Použití zařízení s Androidem](using-your-android-device-with-intune.md)
- [Používání zařízení s iOSem](using-your-ios-device-with-intune.md)
- [Používání zařízení s macOS](using-your-macos-device-with-intune.md)
- [Použití zařízení s Windows](using-your-windows-device-with-intune.md)
- [Použití webu Portál společnosti](using-the-intune-company-portal-website.md)

## <a name="what-happens-when-you-add-a-computer-or-device-to-the-company-portal"></a>Co se stane, když přidáte počítač nebo zařízení na Portál společnosti?
Když na Portál společnosti přidáte počítač nebo zařízení, může se nainstalovat určitý software nebo stáhnout aplikace (podle zařízení). Firemní podpoře tím také udělujete oprávnění ke správě vašich zařízení, aby bylo možné lépe chránit firemní informace na daném zařízení.

Pokud vás zajímá, co vaše firemní podpora uvidí nebo naopak neuvidí na vašem zařízení, použijte odkaz, který odpovídá vašemu typu zařízení:

- [Instalace aplikace Portál společnosti pro Android](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-android.md)
- [Instalace aplikace Portál společnosti pro iOS](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)
- [Instalace aplikace Portál společnosti pro macOS](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-macos.md)
- [Instalace aplikace Portál společnosti pro Windows](about-cp-app-for-windows-10.md)

## <a name="what-kind-of-computers-or-devices-can-you-add-to-the-company-portal"></a>Jaký typ počítačů nebo zařízení můžete přidávat na Portál společnosti?
-   Zařízení Apple používající iOS (například iPhone a iPad) a macOS (například MacBook a iMac)
-   Zařízení se systémem Android
-   Zařízení s Windows
    -   Windows 10 Mobile
    -   Windows 10 Desktop
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Můžete z Portálu společnosti odebrat počítač nebo zařízení?
Počítač nebo zařízení můžete z Portálu společnosti odebrat nebo obnovit. Mezi **odebráním** a **obnovením** je rozdíl.

Když počítač nebo zařízení *odeberete* z Portálu společnosti, zrušíte tím registraci zařízení v Intune. Při zrušení registrace se už z tohoto zařízení nedostanete na Portál společnosti a můžou se z něho odebrat některá firemní data. Pokud chcete zjistit, jak zařízení odebrat z Portálu společnosti, zvolte jeden z následujících odkazů:

- [Zrušení registrace zařízení s Androidem](unenroll-your-device-from-intune-android.md)
- [Zrušení registrace zařízení s iOSem](unenroll-your-device-from-intune-ios.md)
- [Zrušení registrace zařízení s macOS](unenroll-your-device-from-intune-macos.md)
- [Zrušení registrace zařízení s Windows](unenroll-your-device-from-intune-windows.md)

Když počítač nebo zařízení *obnovíte*, Portál společnosti se pokusí počítač nebo zařízení obnovit do výchozího továrního nastavení. Při obnovení se ze zařízení odeberou všechna firemní i osobní data. Pokud jste zařízení ztratili, můžete ho také z webu Portál společnosti obnovit vzdáleně.

Postup resetování zařízení najdete tady:

- [Resetování (vymazání) zařízení z webu Portál společnosti](reset-erase-your-device-cpwebsite.md)

## <a name="what-if-i-cant-see-my-device-in-the-company-portal"></a>Co mám dělat, pokud nevidím svoje zařízení na Portálu společnosti?
Abyste zařízení viděli, musíte ho na Portál společnosti napřed přidat. Přejděte na Portál společnosti, který vám doporučil správce, a postupujte podle pokynů pro vaše zařízení. Neuvidíte taky zařízení vlastněná a spravovaná vaší společností.

## <a name="where-else-can-i-go-for-help"></a>Kde jinde ještě můžu požádat o pomoc?
Microsoft doporučuje, abyste se nejprve pokusili vyřešit problém sami. Nabízíme seznam způsobů, jak řešit možné problémy, pro každou z platforem podporovaných v Intune.

- [Řešení běžných problémů se zařízením s Androidem](troubleshoot-your-device-android.md)
- [Řešení běžných problémů se zařízením s iOSem](troubleshoot-your-device-ios.md)
- [Řešení běžných problémů se zařízením s macOS](troubleshoot-your-device-macos.md)
- [Řešení běžných problémů se zařízením s Windows](troubleshoot-your-device-windows.md)

Níže můžete zadat komentář, ve kterém požádáte o pomoc. Každá organizace má ovšem jiné požadavky, proto se může stát, že nebudeme moct na vaše otázky odpovědět. Obraťte se na svou firemní podporu, která vám může nejrychleji pomoct najít relevantní řešení. Příslušné kontaktní informace by měly být k dispozici na [webu Portálu společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
