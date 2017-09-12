---
title: "Začínáme s registrací zařízení"
titlesuffix: Azure portal
description: "Projděte si celý proces registrace zařízení s iOS a zjistěte, jak registrace probíhá."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cec3db189909238596b42c7a40f5303bb1f1f768
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-enrolling-devices"></a>Začínáme s registrací zařízení

Microsoft Intune umožňuje vybavit vaše pracovníky mobilními zařízeními a zároveň mít chráněná firemní data. Vzhledem k tomu, že koncoví uživatelé budou s Intune pracovat na svých zařízeních, a nikoli na konzole pro správce, nezapomeňte se důkladně seznámit s registračním prostředím. To vám umožní spojit důkladně připravené zásady dodržování předpisů s vaším prostředím, abyste mohli uživatelům projevit potřebnou dávku empatie. Je to zvlášť důležité, protože uživatelé přesně vědí, jaké informace jako správce vidíte:

| Co správci IT neuvidí | Co správci IT uvidí |
|---|---|
| Historie volání a procházení webu | Model |
| Umístění | Sériové číslo |
| Osobní e-mail | Verze operačního systému |
| Textové zprávy | Názvy aplikací |
| Kontakty | Vlastník |
| Hesla k osobním účtům | Název zařízení |
| Události kalendáře | Výrobce (pro zařízení, která nejsou vyrobená společností Apple) |
| Obrázky, včetně těch, které jsou ve fotografických aplikacích nebo mezi obrázky z fotoaparátu | Telefonní číslo (pro pracovní zařízení celé číslo, pro osobní zařízení jenom poslední čtyři číslice) |

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

## <a name="next-steps"></a>Další kroky

[Začínáme s přidáváním aplikací](get-started-apps.md) – najděte a přidejte aplikace do zařízení, aby mohli vaši zaměstnanci plnit úkoly.

## <a name="learn-more"></a>Další informace

* [Možnosti registrace pro Intune](enrollment-options.md)
* [Jak v Intune povolit funkci Přineste si vlastní zařízení](byod-enable.md)
* [Poučení koncových uživatelů o registraci a správě zařízení](end-user-educate.md)
