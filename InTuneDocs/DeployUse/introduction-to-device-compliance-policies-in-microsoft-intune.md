---
# required metadata

title: Zásady dodržování předpisů pro zařízení | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zásady dodržování předpisů pro zařízení v Microsoft Intune
## Co je zásada dodržování předpisů?
Chcete-li chránit data společnosti, ujistěte se, že zařízení používaná k přístupu k firemním aplikacím a datům dodržují určitá pravidla, jako jsou použití kódu PIN pro přístup k zařízení a šifrování dat uložených v zařízení. Sada těchto pravidel je označovaná jako zásada dodržování předpisů.

## Jak mám použít zásady dodržování předpisů?
Zásady dodržování předpisů spolu se zásadami podmíněného přístupu slouží k omezení přístupu k zařízením, která jsou v souladu s pravidly zásad dodržování předpisů. Pro pochopení jak používat obě zásady společně si přečtěte článek [Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Zásady dodržování předpisů mohou být použité nezávisle na podmíněném přístupu. Při nezávislém použití jsou cílová zařízení vyhodnocená a nahlášená společně se stavem dodržování předpisů. Například můžete chtít zjistit, kolik zařízení není šifrovaných nebo která zařízení jsou s jailbreakem nebo rootem. Pokud jsou však použity nezávisle, nefunguje omezení přístupu k prostředkům společnosti.

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

### Související témata
[Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->

