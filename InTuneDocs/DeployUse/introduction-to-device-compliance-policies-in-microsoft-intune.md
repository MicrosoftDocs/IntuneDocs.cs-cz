---
title: "Zásady dodržování předpisů pro zařízení | Microsoft Intune"
description: "Toto téma vysvětluje koncepty, které vám pomohou pochopit, co jsou zásady dodržování předpisů zařízení a jak pracují."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: dfa123266222004b6c6e4f7b21446b96be444d0b


---

# Zásady dodržování předpisů pro zařízení v Microsoft Intune
## Co je zásada dodržování předpisů?
Pokud chcete ochránit data společnosti, ujistěte se, že zařízení používaná k přístupu k firemním aplikacím a datům dodržují určitá pravidla, jako jsou použití kódu PIN pro přístup k zařízení a šifrování dat uložených v zařízení. Sada takových pravidel se označuje jako zásada dodržování předpisů.

## Jak mám použít zásady dodržování předpisů?
Zásady dodržování předpisů spolu se zásadami podmíněného přístupu umožňují povolit přístup k e-mailu a dalším službám jenom zařízením, která jsou v souladu s pravidly zásad dodržování předpisů. Přečtěte si článek [Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), abyste pochopili, jak oba druhy zásad používat.

Zásady dodržování předpisů se můžou používat nezávisle na podmíněném přístupu. Při nezávislém použití se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete třeba chtít zjistit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů nasazujete uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů.

Následující tabulka uvádí typy zařízení podporované zásadami dodržování předpisů. Kromě toho je v ní i způsob, jak se spravují nastavení, která předpisy nedodržují, pokud se zásady používají se zásadami podmíněného přístupu.

--------------

|Nastavení zásady| Windows 8.1 a vyšší| Windows Phone 8.1 nebo novější| iOS 6.0 nebo novější|Android 4.0 nebo novější<br/>Zařízení, na kterém běží Samsung KNOX Standard 4.0 nebo novější|
|-----|----|----|----|
|**Konfigurace kódu PIN nebo hesla** |Opravené|Opravené|Opravené|V karanténě|
|**Šifrování zařízení**|Není k dispozici|Opravené|Opravené (nastavením PIN kódu)|V karanténě|
|**Zařízení s jailbreakem nebo rootem**|Není k dispozici|Není k dispozici|V karanténě (není nastavení)|V karanténě (není nastavení)|
|**E-mailový profil**|Není k dispozici|Není k dispozici|V karanténě|Není k dispozici|
|**Minimální verze operačního systému**|V karanténě|V karanténě|V karanténě|V karanténě|
|**Maximální verze operačního systému**|V karanténě| V karanténě| V karanténě| V karanténě|
|**Ověření stavu Windows**|Windows 10 a Windows 10 Mobile jsou v karanténě.<br /><br />Nastavení se nevztahuje na Windows 8.1.|Není k dispozici|Není k dispozici|Není k dispozici|
--------------
**Opravené** = Dodržování předpisů se vynucuje operačním systémem zařízení (třeba tak, že uživatel musí nastavit kód PIN).  To se nikdy nestane, pokud nastavení nedodržuje předpisy.

**V karanténě** = Operační systém zařízení nevynucuje dodržování předpisů (třeba zařízení s Androidem nenutí uživatele šifrovat svoje zařízení). Pokud zařízení nesplňuje předpisy, provedou se následující akce:

-   Zařízení se zablokuje, pokud se na uživatele zaměřuje zásada podmíněného přístupu.

-   Firemní portál oznámí uživateli všechny problémy s dodržováním předpisů.

## Další kroky
[Vytváření zásad dodržování předpisů pro zařízení](create-a-device-compliance-policy-in-microsoft-intune.md)

[Nasazení a monitorování zásady dodržování předpisů pro zařízení](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Viz taky
[Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


