---
title: Nastavení dodržování předpisů pro Android Enterprise v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení s Androidem Enterprise v Microsoft Intune. Nastavte pravidla pro hesla, vyberte minimální nebo maximální verzi operačního systému, omezte konkrétní aplikace, Zabraňte použití hesla a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7d38d5c71b06587b593eef46eca46f3d32f1349
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729826"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Androidu Enterprise k označení zařízení jako kompatibilních nebo nekompatibilních s Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních s Androidem Enterprise v Intune. V rámci řešení pro správu mobilních zařízení (MDM) použijte Tato nastavení k označení rootem (jailbreak) zařízení jako nevyhovující předpisům, nastavte povolenou úroveň hrozby, povolte Google Play chránit a další.

Tato funkce platí pro:

- Android Enterprise

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

> [!IMPORTANT]
> Zásady dodržování předpisů také používají vyhrazená zařízení s Androidem Enterprise. Pokud je zásada dodržování předpisů přiřazená vyhrazenému zařízení, může se zařízení zobrazovat jako **nevyhovující předpisům**. Podmíněný přístup a vynucování dodržování předpisů není na vyhrazených zařízeních k dispozici. Ujistěte se, že jste dokončili všechny úkoly nebo akce, abyste získali vyhrazená zařízení, která vyhovují vašim přiřazeným zásadám.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). Jako **platformu**vyberte **Android Enterprise**.

## <a name="device-owner"></a>Vlastník zařízení

### <a name="device-health"></a>Stav zařízení

- **Vyžadovat, aby zařízení bylo na úrovni hrozby pro zařízení nebo pod**ní: Vyberte maximální povolenou úroveň hrozby pro zařízení vyhodnocenou [službou ochrany před mobilními hrozbami](mobile-threat-defense.md). Zařízení, která přesahují tuto úroveň hrozby, se označí jako nedodržující předpisy. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:

  - **Nenakonfigurováno** (výchozí): Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.
  - **Zabezpečeno**: Tato možnost je nejbezpečnější a znamená, že na zařízení nesmí být žádné hrozby. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
  
> [!NOTE] 
> Následující poskytovatelé ochrany před mobilními hrozbami (MTD) podporují nasazení vlastníků zařízení s Androidem Enterprise pomocí konfigurace aplikace:
> - Lepší mobilní zařízení 
> - Pradeo
> - Sophos Mobile
> - Zimperium 
>  
>  Projděte si poskytovatele MTD, kde najdete přesnou konfiguraci potřebnou k podpoře platforem pro vlastníka zařízení s Androidem Enterprise v Intune. Tento seznam se aktualizuje, protože MTD součásti podporují scénáře pro vlastníky zařízení s Androidem Enterprise. 

#### <a name="google-play-protect"></a>Google Play chránit

- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Nenakonfigurováno** (výchozí): U nastavení se nevyhodnocuje, jestli zařízení vyhovuje.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

### <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel může upgradovat svoje zařízení a pak získat přístup k prostředkům organizace.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům organizace blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se pravidlo nezmění, aby nedošlo k této verzi operačního systému, nebude mít toto zařízení přístup k prostředkům organizace.

### <a name="system-security"></a>Zabezpečení systému

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Toto nastavení se použije na úrovni zařízení. Pokud potřebujete vyžadovat heslo na úrovni pracovního profilu, použijte zásady konfigurace. Viz [nastavení konfigurace zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).

  - **Požadovaný typ hesla:** Zvolte, jestli se má heslo obsahovat jenom číslice nebo kombinaci číslic s jinými znaky. Možnosti:
    - **Výchozí nastavení zařízení**: Pokud chcete vyhodnotit dodržování předpisů heslem, nezapomeňte vybrat jinou sílu hesla než **výchozí zařízení**.  
    - **Vyžaduje se heslo, žádná omezení.**
    - **Slabý biometrika**: [silný vs. slabý biometrika](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (otevře web v Androidu)
    - **Numeric** (výchozí): heslo musí obsahovat jenom čísla, například `123456789`. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
    - **Číselná složitá**: opakující se nebo po sobě jdoucí čísla, například "1111" nebo "1234", nejsou povolena. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
    - **Abecedy**: jsou vyžadovány písmena v abecedě. Čísla a symboly nejsou požadovány. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
    - **Alfanumerické**znaky: obsahuje velká písmena, malá písmena a číslice. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
    - **Alfanumerické znaky se symboly**: zahrnují velká písmena, malá písmena, číslice, interpunkční znaménka a symboly. Dále zadejte:

      - **Minimální délka hesla**: zadejte minimální délku hesla, která musí být delší než 4 až 16 znaků.
      - **Požadovaný počet znaků**: zadejte počet znaků, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
      - **Počet požadovaných malých**písmen: zadejte počet malých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
      - **Počet požadovaných velkých znaků**: zadejte počet velkých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
      - **Počet požadovaných znaků bez**písmen: zadejte počet jiných než písmen (kromě písmen v abecedě), které musí heslo obsahovat, 0 až 16 znaků.
      - **Požadovaný počet**číslic: zadejte počet číselných znaků (`1`, `2`, `3` atd.) heslo musí mít 0 až 16 znaků.
      - **Požadovaný počet znaků symbolů**: zadejte počet znaků symbolu (`&`, `#`, `%` atd.) heslo musí mít 0 až 16 znaků.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Počet dní do vypršení platnosti hesla**: zadejte počet dnů (v rozmezí 1-365), do kterého se musí heslo zařízení změnit. Pokud například chcete změnit heslo po 60 dnech, zadejte `60`. Po vypršení platnosti hesla se uživatelům zobrazí výzva k vytvoření nového hesla.
- **Počet hesel vyžadovaných před opětovným použitím hesla uživatele**: zadejte počet nedávných hesel, která se nesmí znovu použít, mezi 1-24. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

- **Šifrování datového úložiště na zařízení:** Pokud chcete, aby zařízení měla šifrované datové úložiště, zvolte **Vyžadovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Toto nastavení nemusíte konfigurovat, protože zařízení s Androidem Enterprise vynutila šifrování.

## <a name="work-profile"></a>Pracovní profil

### <a name="device-health"></a>Device health

- **Zařízení s rootem:** Pokud chcete všechna zařízení s rootem (jailbreakem) označit jako nevyhovující, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na úrovni hrozby pro zařízení nebo pod**ní: Vyberte maximální povolenou úroveň hrozby pro zařízení vyhodnocenou [službou ochrany před mobilními hrozbami](mobile-threat-defense.md). Zařízení, která přesahují tuto úroveň hrozby, se označí jako nedodržující předpisy. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:

  - **Nenakonfigurováno** (výchozí): Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.
  - **Zabezpečeno**: Tato možnost je nejbezpečnější a znamená, že na zařízení nesmí být žádné hrozby. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

#### <a name="google-play-protect"></a>Google Play chránit

- **Aplikace Služby Google Play je nakonfigurovaná:** **Vyžaduje**, aby aplikace Služby Google Play byla nainstalovaná a povolená. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení:** **Vyžaduje**, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými hrozbami. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Nenakonfigurováno** (výchozí): U nastavení se nevyhodnocuje, jestli zařízení vyhovuje.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

> [!NOTE]
> V zařízeních s Androidem Enterprise je **Kontrola hrozeb u aplikací** zásada konfigurace zařízení. Pomocí zásad konfigurace můžou správci povolit nastavení na zařízení. Další informace viz [Nastavení omezení pro zařízení s Androidem](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel může upgradovat svoje zařízení a pak získat přístup k prostředkům organizace.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům organizace blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se pravidlo nezmění, aby nedošlo k této verzi operačního systému, nebude mít toto zařízení přístup k prostředkům organizace.

### <a name="system-security"></a>Zabezpečení systému

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Toto nastavení se použije na úrovni zařízení. Pokud potřebujete vyžadovat heslo na úrovni pracovního profilu, použijte zásady konfigurace. Viz [nastavení konfigurace zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).
- **Požadovaný typ hesla:** Zvolte, jestli se má heslo obsahovat jenom číslice nebo kombinaci číslic s jinými znaky. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číslice** (výchozí): zadejte **minimální délku hesla** , kterou musí uživatel zadat, o délce 4 až 16 znaků.
  - **Číselná složitá**: zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Aspoň abecední**: zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Aspoň alfanumerické**: zadejte **minimální délku hesla** , kterou musí uživatel zadat, o délce 4 až 16 znaků.
  - **Aspoň alfanumerické se symboly**: zadejte **minimální délku hesla** , kterou musí uživatel zadat, o délce 4 až 16 znaků.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Počet dní do vypršení platnosti hesla**: Vyberte počet dní do vypršení platnosti hesla a koncový uživatel musí vytvořit nové heslo.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

#### <a name="encryption"></a>Encryption

- **Šifrování datového úložiště na zařízení:** Pokud chcete, aby zařízení měla šifrované datové úložiště, zvolte **Vyžadovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. 

  Toto nastavení nemusíte konfigurovat, protože zařízení s Androidem Enterprise vynutila šifrování.

#### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: vyberte možnost **blokovat** zařízení se **zabezpečením** > **neznámé zdroje** s povoleným zdrojem (podporované v Androidu 4,0 – Android 7. x; nepodporuje Android 8,0 a novější). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili.

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

  Toto nastavení nemusíte konfigurovat, protože zařízení se systémem Android Enterprise vždy omezují instalaci z neznámých zdrojů.

- **Integrita modulu runtime aplikace Portál společnosti:** Pokud chcete potvrdit, že aplikace Portál společnosti splňuje všechny následující požadavky, zvolte **Vyžadovat**:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB:** Pokud chcete zařízením zabránit v použití funkce ladění USB, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Toto nastavení nemusíte konfigurovat, protože ladění USB je už na zařízeních s Androidem Enterprise zakázané.

- **Minimální úroveň opravy zabezpečení**: Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu *RRRR-MM-DD*.

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení s Androidem](compliance-policy-create-android.md) .
