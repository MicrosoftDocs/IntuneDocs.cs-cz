---
title: Nastavení dodržování předpisů pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavení dodržování předpisů pro zařízení s Androidem v Microsoft Intune. Nastavte pravidla pro hesla, vyberte minimální nebo maximální verzi operačního systému, omezte konkrétní aplikace, Zabraňte použití hesla a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80ed21c0831eb92a8e18596e7ab5f09848362b3a
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729802"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení pro Android označení zařízení jako kompatibilních nebo nekompatibilních s Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních s Androidem v Intune. V rámci řešení pro správu mobilních zařízení (MDM) použijte Tato nastavení k označení rootem (jailbreak) zařízení jako nevyhovující předpisům, nastavte povolenou úroveň hrozby, povolte Google Play chránit a další.

Tato funkce platí pro:

- Android

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **Android**.

## <a name="device-health"></a>Device health

- **Zařízení s rootem:** Pokud chcete všechna zařízení s rootem (jailbreakem) označit jako nevyhovující, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na úrovni hrozby pro zařízení nebo pod**ní: Toto nastavení použijte, pokud chcete vyhodnotit hodnocení rizik z řešení zabezpečení z mobilního koncového bodu jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení se vyhodnotí jako vyhovující, pokud se existující hrozby pohybují na střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

### <a name="google-play-protect"></a>Google Play chránit

- **Aplikace Služby Google Play je nakonfigurovaná:** **Vyžaduje**, aby aplikace Služby Google Play byla nainstalovaná a povolená. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení:** **Vyžaduje**, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými hrozbami. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Kontrola ohrožení aplikací**: **Vyžaduje**, aby byla povolená funkce Androidu **Ověřovat aplikace**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  > [!NOTE]
  > Na starších verzích platformy Android tato funkce představuje nastavení dodržování předpisů. Intune může jenom zkontrolovat, jestli je toto nastavení povolené na úrovni zařízení.

- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Nenakonfigurováno** (výchozí): U nastavení se nevyhodnocuje, jestli zařízení vyhovuje.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

> [!NOTE]
> Konfigurace nastavení Google Play chránit pomocí zásad ochrany aplikací najdete v tématu [nastavení zásad ochrany aplikací Intune](../apps/app-protection-policy-settings-android.md#conditional-launch) na Androidu.

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze specifikovaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se pravidlo nezmění a nepovolí verzi operačního systému, nebude mít toto zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla:** Zvolte, jestli se má heslo obsahovat jenom číslice nebo kombinaci číslic s jinými znaky. Možnosti:
  - **Výchozí nastavení zařízení**: Pokud chcete vyhodnotit dodržování předpisů heslem, nezapomeňte vybrat jinou sílu hesla než **výchozí zařízení**.
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní:** Nejsou povolená opakující se ani po sobě jdoucí čísla, jako například `1111` nebo `1234`.
  - **Aspoň abecední znaky** 
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který heslo vyprší a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Encryption

- **Šifrování úložiště dat na zařízení** (Android 4.0 a vyšší nebo KNOX 4.0 a vyšší): Vyberte **Vyžadovat** a zašifrujte úložiště dat na vašich zařízeních. Zařízení se šifrují, pokud vyberete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů:** Zvolte, že chcete **blokovat** zařízení s povolenými zdroji Zabezpečení > Neznámé zdroje (podporované v Androidu 4.0 – Android 7.x, nepodporované v Androidu 8.0 a novějších verzích). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Integrita modulu runtime aplikace Portál společnosti:** Pokud chcete potvrdit, že aplikace Portál společnosti splňuje všechny následující požadavky, zvolte **Vyžadovat**:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB** (Android 4.2 nebo novější): Pokud chcete na zařízeních zakázat použití funkce ladění USB, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální úroveň opravy zabezpečení** (Android 6.0 nebo novější): Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu `YYYY-MM-DD`.
- **Omezené aplikace:** Pokud chcete používání některých aplikací zakázat, zadejte **název aplikace** a **ID sady prostředků aplikace**. Zvolte **Přidat**. Pokud je na zařízení nainstalovaná aspoň jedna zakázaná aplikace, označí se zařízení jako nevyhovující.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="locations"></a>Polohy

V zásadách můžete vynutit dodržování předpisů podle umístění zařízení. Vyberte si z existujících umístění. Žádné umístění ještě nemáte? V Intune jsou k dispozici pokyny k [použití umístění (síťová síť)](use-network-locations.md) .

1. Zvolte **umístění** > **Vyberte umístění**.
2. V seznamu ověřte umístění > **Vyberte**.
3. **Uložte** zásady.

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení s Androidem Enterprise](compliance-policy-create-android-for-work.md) .
