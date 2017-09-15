---
title: "Nastavení omezení pro zařízení v Intune pro Android for Work"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7e7f74f516a4b60b6a727d6c51ec54dab96aa88e
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Nastavení pracovního profilu
- **Sdílení dat mezi pracovním a osobním profilem** – toto nastavení použijte pro určení, jestli aplikace v pracovním profilu můžou používat sdílení s aplikacemi v osobním profilu. Toto nastavení řídí akce sdílení v rámci aplikací (například možnost **Sdílet** v prohlížeči Chrome), nevztahuje se na chování schránky při kopírování a vkládání. Na rozdíl od [nastavení zásad ochrany aplikací](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) se nastavení omezení pro zařízení spravují na Azure Portalu a k izolování spravovaných aplikací se používá oddíl pracovního profilu Androidu for Work. Vybírejte z těchto možností:
    - **Výchozí omezení sdílení** – toto nastavení je výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu používané v zařízení. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neposkytuje způsob, jak blokovat sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.   
    - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu** – tuto možnost použijte, pokud chcete povolit integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
    - **Povolit sdílení přes hranice** – umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení používejte obezřetně, protože povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení.

-   **Oznámení z pracovního profilu, když je zařízení zamknuté** – řídí, jestli aplikace v pracovním profilu můžou zobrazovat data v oznámeních, když je zařízení zamknuté.
-   **Výchozí oprávnění aplikace** – umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Pomocí této zásady můžete určit, jestli se všechna oprávnění mají automaticky udělit bez výzvy, automaticky odepřít bez výzvy, nebo jestli má rozhodnout uživatel. Vybírejte z těchto možností:
    -   **Výchozí ze zařízení**
    -   **Zeptat se**
    -   **Automaticky udělit**
    -   **Automaticky odepřít**

    Stav udělení oprávnění pro konkrétní aplikace je možné dále definovat pomocí zásad konfigurace pro jednotlivé aplikace (v části **Mobilní aplikace** > **Zásady konfigurace aplikací**).

### <a name="work-profile-password"></a>Heslo pracovního profilu
- **Vyžadovat heslo pracovního profilu** (Android 7.0 a vyšší s povoleným pracovním profilem) – definujte zásady hesla, které se budou vztahovat jenom na aplikace v pracovním profilu. Ve výchozím nastavení má koncový uživatel možnost použít dva samostatně definované PIN kódy, nebo se může rozhodnout je zkombinovat do silnějšího z nich.
- **Minimální délka hesla** – zadejte minimální počet znaků, které uživatelské heslo musí obsahovat (**4** až **16**).
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – umožňuje vybrat dobu, která má uplynout před tím, než se zamkne pracovní profil. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – zadejte, kolikrát může uživatel zadat nesprávné heslo před tím, než se pracovní profil ze zařízení smaže.
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
- **Smart Lock a jiní agenti pro určování důvěryhodnosti** – umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo pracovního profilu, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko štítku NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="device-password"></a>Heslo zařízení

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
- **Smart Lock a jiní agenti pro určování důvěryhodnosti** – umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko štítku NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="next-steps"></a>Další kroky

S použitím informací v tématu [Jak nakonfigurovat nastavení omezení zařízení](device-restrictions-configure.md) uložte a přiřaďte profil uživatelům a zařízením.
