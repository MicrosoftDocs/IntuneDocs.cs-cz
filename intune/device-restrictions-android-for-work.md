---
title: Omezení zařízení pro Android for Work v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s Androidem for Work můžete omezit některá nastavení v zařízení, včetně kopírování a vložení, zobrazování oznámení, oprávnění aplikací, sdílení dat, délky hesla, neúspěšných přihlášení, odemykání pomocí otisku prstu, opakovaného použití předchozích hesel a povolení sdílení pracovních kontaktů pomocí Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5715cca4a2f3deff925c5ba2575771c548261e53
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="work-device-restriction-settings-in-intune"></a>Nastavení omezení pracovních zařízení v Intune

Tento článek uvádí nastavení omezení zařízení v Microsoft Intune, která můžete nakonfigurovat pro zařízení s Androidem for Work.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Nastavení pracovního profilu

### <a name="general-settings"></a>Obecná nastavení

- **Kopírování a vkládání mezi pracovními a osobními profily**: ovládá kopírování a vkládání mezi pracovními a osobními aplikacemi. Zvolením možnosti **Blokovat** zapnete blokování. Zvolením možnosti **Nenakonfigurováno** blokování vypnete.
- **Sdílení dat mezi pracovním a osobním profilem**: určuje, jestli aplikace v pracovním profilu můžou používat sdílení s aplikacemi v osobním profilu. Toto nastavení řídí akce sdílení v rámci aplikací (například možnost **Sdílet** v prohlížeči Chrome), nevztahuje se na chování schránky při kopírování a vkládání. Na rozdíl od [nastavení zásad ochrany aplikací](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) se nastavení omezení pro zařízení spravují na portálu Intune a k izolování spravovaných aplikací používají oddíl pracovního profilu Androidu for Work. Vybírejte z těchto možností:
  - **Výchozí omezení sdílení**: jedná se o výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neposkytuje způsob, jak blokovat sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: povoluje integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Povolit sdílení přes hranice**: umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení používejte opatrně, protože povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení.

- **Oznámení z pracovního profilu, když je zařízení zamknuté**: řídí, jestli aplikace v pracovním profilu můžou zobrazovat data v oznámeních, když je zařízení zamknuté.
- **Výchozí oprávnění aplikace**: umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Pomocí této zásady můžete určit, jestli se všechna oprávnění mají automaticky udělit bez výzvy, automaticky odepřít bez výzvy nebo jestli má rozhodnout uživatel. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Zeptat se**
  - **Automaticky udělit**
  - **Automaticky odepřít**

    Stav udělení oprávnění pro konkrétní aplikace je možné dále definovat pomocí zásad konfigurace pro jednotlivé aplikace (v části **Mobilní aplikace** > **Zásady konfigurace aplikací**).

- **Přidat nebo odebrat účty**

   Zabrání koncovým uživatelům ručně přidávat nebo odebírat účty v pracovním profilu.

   Když třeba nasadíte aplikaci Gmail do profilu Androidu for Work, můžete zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v tomto pracovním profilu.

- **Sdílení kontaktů přes Bluetooth**: Povoluje přístup k pracovním kontaktům z jiného zařízení, například ze zařízení v autě, které je spárováno pomocí Bluetooth. Ve výchozím nastavení toto nastavení není nakonfigurováno a pracovní kontakty se nezobrazují. Vyberte **Povolit** a sdílení povolte, aby se zobrazily kontakty pracovního profilu. Toto nastavení platí pro zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších. Když tuto zásadu povolíte, budou určitá zařízení Bluetooth ukládat pracovní kontakty do mezipaměti při prvním připojení. V případě jejího zakázání po počátečním zpárování/synchronizaci se pracovní kontakty ze zařízení Bluetooth nemusí odstranit.

### <a name="work-profile-password"></a>Heslo pracovního profilu

- **Vyžadovat heslo pracovního profilu**: platí pro Android 7.0 a vyšší s aktivovaným pracovním profilem. Umožňuje definovat zásady hesla, které platí jenom pro aplikace v pracovním profilu. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich.
- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat (**4** -**16**).
- **Maximální doba neaktivity v minutách, než se pracovní profil zamkne**: umožňuje vybrat dobu, po které se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se pracovní profil ze zařízení vymaže.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: blokuje koncovému uživateli možnost používat skener otisků prstů zařízení k odemknutí zařízení.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti**: umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo pracovního profilu, pokud se zařízení nachází v důvěryhodném umístění. Například když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="device-password"></a>Heslo zařízení

- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat (**4**-**14**).
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: umožňuje vybrat dobu, po které neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se ze zařízení vymažou veškerá data.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: blokuje koncovému uživateli možnost používat skener otisků prstů zařízení k odemknutí zařízení.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti**: umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Například když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="system-security"></a>Zabezpečení systému

- **Kontrola ohrožení aplikací**: vynutí zapnutí nastavení **Ověřovat aplikace** pro pracovní a osobní profily.

   > [!Note]
   > Toto nastavení funguje jenom u zařízení s Androidem O a vyšším.

## <a name="next-step"></a>Další krok

Informace o uložení a přiřazení profilu uživatelům najdete v článku [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md).
