---
title: "Zásady dodržování předpisů pro zařízení"
description: "Toto téma vysvětluje, jaké jsou zásady dodržování předpisů zařízení a jak pracují."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bcdad361dba7ee006bf2e2cffac7f1024c5e6dc6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="device-compliance-policies-in-microsoft-intune"></a>Zásady dodržování předpisů pro zařízení v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>Co je zásada dodržování předpisů?
Pokud chcete chránit firemní data, budete muset zkontrolovat, jestli jsou zařízení určená pro přístup k podnikovým aplikacím a datům v souladu s určitými pravidly. Mezi tyto pravidla může patřit používání kódu PIN pro přístup k zařízením a šifrování dat uložených na zařízeních. Sada těchto pravidel se označuje jako zásady dodržování předpisů.

## <a name="how-should-i-use-compliance-policies"></a>Jak mám použít zásady dodržování předpisů?
Zásady dodržování předpisů spolu se zásadami podmíněného přístupu umožňují povolit přístup k e-mailu a dalším službám jenom zařízením, která jsou v souladu s pravidly zásad dodržování předpisů. Přečtěte si článek [Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), abyste pochopili, jak se dají oba druhy zásad používat.

Zásady dodržování předpisů se můžou používat nezávisle na podmíněném přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete třeba chtít zjistit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů nasazujete uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů.
Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku [Správa nastavení a funkcí na vašich zařízeních](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

Následující tabulka uvádí typy zařízení, které podporují zásady dodržování předpisů. Tabulka taky popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

-----------------------------

|Nastavení zásad| Windows 8.1 a vyšší| Windows Phone 8.1 nebo novější| iOS 8.0 a novější|Android 4.0 nebo novější<br/>Samsung Knox Standard 4.0 a novější|
|-----|----|----|----|----|
|**Konfigurace kódu PIN nebo hesla** |Opravené|Opravené|Opravené|V karanténě|
|**Šifrování zařízení**|Nelze použít|Opravené|Opravené (nastavením PIN kódu)|V karanténě|
|**Zařízení s jailbreakem nebo rootem**|Nelze použít|Nelze použít|V karanténě (není nastavení)|V karanténě (není nastavení)|
|**E-mailový profil**|Nelze použít|Nelze použít|V karanténě|Nelze použít|
|**Minimální verze operačního systému**|V karanténě|V karanténě|V karanténě|V karanténě|
|**Maximální verze operačního systému**|V karanténě|V karanténě|V karanténě|V karanténě|
|**Ověření stavu Windows**|V karanténě: Windows 10 a Windows 10 Mobile<br /><br />Nelze použít: Windows 8.1|Nelze použít|Nelze použít|Nelze použít|

------------------------------

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

-   Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.

-   Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="next-steps"></a>Další kroky
[Vytvoření zásad dodržování předpisů pro zařízení](create-a-device-compliance-policy-in-microsoft-intune.md)

[Nasazení a sledování zásad dodržování předpisů pro zařízení](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Viz taky
[Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
