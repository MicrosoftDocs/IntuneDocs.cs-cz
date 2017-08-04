---
title: "Začínáme s registrací zařízení"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7f52c9d44a91ed6547aadd712db42ea68cfd01dc
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-enrolling-devices"></a>Začínáme s registrací zařízení

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune umožňuje vybavit vaše pracovníky mobilními zařízeními a zároveň mít chráněná firemní data. Vzhledem k tomu, že koncoví uživatelé budou s Intune pracovat na svých zařízeních, a nikoli na konzole pro správce, nezapomeňte se důkladně seznámit s registračním prostředím. To vám umožní spojit důkladně připravené zásady dodržování předpisů s vaším prostředím, abyste mohli uživatelům projevit potřebnou dávku empatie. Je to zvlášť důležité, protože uživatelé přesně vědí, jaké informace jako správce vidíte:

## <a name="what-it-cannot-see"></a>Co správci IT neuvidí
* Historie volání a procházení webu
* Umístění
* Osobní e-mail
* Textové zprávy
* Kontakty
* Hesla k osobním účtům
* Události kalendáře
* Obrázky, včetně těch, které jsou ve fotografických aplikacích nebo mezi obrázky z fotoaparátu

## <a name="what-it-can-see"></a>Co správci IT uvidí
* Model
* Sériové číslo
* Verze operačního systému
* Názvy aplikací
* Vlastník
* Název zařízení
* Výrobce (pro zařízení, která nejsou vyrobená společností Apple)
* Telefonní číslo (pro pracovní zařízení celé číslo, pro osobní zařízení jenom poslední čtyři číslice)

## <a name="how-do-i-enroll-a-device"></a>Jak zaregistruji zařízení?

Registrace zařízení je pro mnoho koncových uživatelů první zkušeností s přístupem k prostředkům společnosti. [Pochopením této zkušenosti](end-user-educate.md) dokážete potenciálně nepříjemnou záležitost změnit tak, aby byla pro uživatele lepší.

1. Otevřete **App Store** a vyhledejte **Portál společnosti Intune**.
2. Stáhněte si aplikaci **Portál společnosti Microsoft Intune**.
3. Otevřete aplikaci **Portál společnosti**, zadejte svou e-mailovou adresu testovacího uživatele a heslo a klepněte na **Přihlásit se**.
4. Nahraďte dočasné heslo novým heslem.
5. Na stránce **Nastavení firemního přístupu** klepněte na **Registrace zařízení**.
6. Na stránce **Kdy zaregistrovat zařízení?** si přečtěte, co registrace uživateli zařízení umožní, a pak klepněte na **Pokračovat**.
7. Přečtěte si seznam přístupů, které uživatel registrací získá, a klepněte na **Pokračovat**.
8. Přečtěte si, co správce IT může a nemůže na zařízení dělat, a klepněte na **Pokračovat**.
9. Na stránce **Co dál?** si přečtěte, co se děje při registraci, a klepněte na **Zaregistrovat**.
10. Na stránce **Nainstalovat profil** klepněte na **Nainstalovat**. Pokud se zobrazí výzva, zadejte heslo zařízení.
11. Klepněte na **Instalovat**.
12. Dalším klepnutím na **Nainstalovat** potvrďte, že jste si přečetli upozornění.
13. V místní nabídce **Upozornění** klepněte na **Důvěřovat**.
14. Po změně obrazovky, která signalizuje dokončení instalace profilu, klepněte na **Hotovo**.
15. Na obrazovce se zobrazí zpráva o registraci zařízení a potom se zobrazí zpráva o tom, že zařízení bylo úspěšně zaregistrováno. Zobrazí se místní nabídka s dotazem, jestli chcete otevřít stránku na Portálu společnosti. Klepněte na **Otevřít**.
16. Vrátíte se na obrazovku **Nastavení přístupu k firmě**. Pokud jste nenastavili testovací zásady, mělo by se zařízení zobrazit jako vyhovující. Pokud jste je nastavili, po klepnutí na **Dodržování předpisů zařízením** se zobrazí, co je potřeba udělat, aby bylo zařízení bezpečné.
