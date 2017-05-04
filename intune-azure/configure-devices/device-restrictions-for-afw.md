---
title: "Nastavení omezení pro zařízení v Intune pro Android for Work"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: b1df2e0c6b2494386193e24c2f6265db35e58dd5
ms.lasthandoff: 04/19/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Nastavení pracovního profilu
-     **Sdílení dat mezi pracovním a osobním profilem** – toto nastavení použijte pro řízení, zda aplikace v pracovním profilu mohou sdílet data s aplikacemi v osobním profilu. Vybírejte z těchto možností: 
    - **Výchozí omezení sdílení** – jedná se o výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu používané v zařízení. Ve výchozím nastavení je povoleno sdílení z osobního do pracovního profilu. Ve výchozím nastavení je také blokováno sdílení mezi pracovním a osobním profilem. To zabraňuje úniku dat z pracovního do soukromého profilu. Google neposkytuje způsob, jak blokovat data přenášená z osobního do pracovního profilu na zařízeních, která používají verze starší než 6.0.  
    - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu** – tuto možnost použijte, pokud chcete povolit integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolena, žádost o sdílení iniciovaná aplikací v osobním profilu bude moci sdílet data s aplikacemi v pracovním profilu. Toto je výchozí chování zařízení s Androidem, které používají verze novější než 6.0.
    - **Aplikace v osobním profilu můžou zpracovat žádost o sdílení z pracovního profilu** – povolí u pracovního profilu sdílení v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s nespravovanými aplikacemi v osobním profilu.  Toto nastavení používejte obezřetně, protože umožňuje přenos spravovaných dat v pracovním profilu do nespravované oblasti zařízení.


-     **Oznámení z pracovního profilu, když je zařízení zamknuté** – řídí, zda aplikace v pracovním profilu můžou zobrazovat oznámení na obrazovce, když je zařízení zamknuté.
-     **Výchozí oprávnění aplikace** – umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se výzvy k povolení některých oprávnění vyžadovaných aplikacemi zobrazují koncovému uživateli při jejich používání. Nastavení této zásady vám umožňuje určit, jak nebo jestli se uživatelům zobrazí výzvy k udělení oprávnění aplikacím v pracovním profilu. Můžete například nainstalovat do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Normálně by tato aplikace zobrazila uživateli dialog s otázkou, jestli chce této aplikaci udělit přístup k poloze, a uživatel by ji schválil nebo zamítl. Pomocí této zásady můžete určit, jestli se všechna oprávnění mají automaticky udělit bez výzvy, automaticky odepřít bez výzvy, nebo jestli to má rozhodnout uživatel. Vybírejte z těchto možností:
    -     **Výchozí ze zařízení**
    -     **Zeptat se**
    -     **Automaticky udělit**
    -     **Automaticky odepřít**

## <a name="password"></a>Heslo

- **Minimální délka hesla** – zadejte minimální počet znaků, které uživatelské heslo musí obsahovat (**4** až **14**).
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – umožňuje vybrat délku doby, která má uplynout před tím, než se neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – zadejte počet, kolikrát může uživatel zadat nesprávné heslo před tím, než se ze zařízení smažou veškerá data.
- **Konec platnosti hesla (dny)** – zadejte počet dnů, které mají uplynout, než uživatel bude muset změnit heslo (**1** až **255**).
- **Požadovaný typ hesla** – vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
    - **Výchozí ze zařízení**
    - **Biometrika s nízkým zabezpečením**
    - **Požadováno**
    - **Aspoň číslice**
    - **Číselné komplexní** – opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
    - **Aspoň abecední znaky**
    - **Aspoň alfanumerické znaky**
    - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel** – zadejte počet nových hesel, které je třeba použít před tím, než uživatel bude moci znovu použít staré heslo (**1** až **24**).
- **Odemknutí pomocí otisků prstů** – blokuje koncovému uživateli možnost používat skener otisků prstů zařízení k odemknutí zařízení.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti** – umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.


