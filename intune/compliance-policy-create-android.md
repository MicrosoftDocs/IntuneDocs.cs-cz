---
title: Nastavení dodržování předpisů pro zařízení s androidem v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s Androidem v Microsoft Intune. Nastavit pravidla pro hesla, zvolte verzi minimální nebo maximální operačního systému, omezit určité aplikace, zabránění opětovné použití hesla a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7670af46657fed048bfe10b8659eae6d45db7620
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897975"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení pro Android se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které lze konfigurovat v zařízeních s Androidem v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy, nastavení povolené úrovně hrozby, povolit Google Play Protect a další.

Tato funkce platí pro:

- Android

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **Android**.

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Zvolte **bloku** se začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na nebo za úrovně hrozby pro zařízení**: Toto nastavení použijte k vyhodnocování rizika z řešení Lookout MTP jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečené**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo zabezpečení. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud se existující hrozby v zařízení se střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

### <a name="google-play-protect"></a>Ochrana služby Google Play

- **Služby Google Play je nakonfigurovaná**: **Vyžadovat** , že služby Google Play aplikace je nainstalován a povolen. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení**: **Vyžadovat** , aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Kontrola ohrožení aplikací**: **Vyžadovat** , která Android **ověřovat aplikace** funkce je povolená. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  > [!NOTE]
  > Na starších verzích platformy Android tato funkce představuje nastavení dodržování předpisů. Intune může jenom zkontrolovat, jestli je toto nastavení povolené na úrovni zařízení.

- **V rámci ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html) , který musí být splněny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

> [!NOTE]
> Nakonfigurování nastavení Google Play Protect pomocí zásad ochrany aplikací najdete v tématu [nastavení zásad ochrany aplikací Intune](app-protection-policy-settings-android.md#conditional-launch) v Androidu.

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze operačního systému**: Když zařízení používá verzi operačního systému novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se nezmění pravidlo, aby tuto verzi operačního systému povolovalo, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla**: Zvolte, pokud heslo by měl obsahovat pouze číselné znaky, nebo kombinací číslic a dalších znaků. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní**: Opakované nebo po sobě jdoucí čísla, jako například `1111` nebo `1234`, nejsou povoleny.
  - **Aspoň abecední znaky** 
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové heslo.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení** (Android 4.0 a vyšší nebo KNOX 4.0 a novější): Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních. Zařízení se šifrují, pokud vyberete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: Zvolit **bloku** zařízení s "Zabezpečení > neznámé zdroje" povolené zdroje (podporuje se ve Android 4.0 – Android 7.x; není podporované nepodporováno na Androidu 8.0 a novější). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Integrita modulu runtime aplikace portál společnosti**: Zvolte **vyžadují** potvrďte portálu společnosti aplikaci splňuje následující požadavky:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB** (Android 4.2 nebo novější): Zvolte **bloku** chcete zabránit používání funkce ladění USB zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální úroveň oprav zabezpečení** (Android 6.0 nebo novější): Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu `YYYY-MM-DD`.
- **Omezených aplikací**: Zadejte **název aplikace** a **ID sady prostředků aplikace** pro aplikace, které by měla být omezena. Zvolte **přidat**. Pokud je na zařízení nainstalovaná aspoň jedna zakázaná aplikace, označí se zařízení jako nevyhovující.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="locations"></a>Umístění

V zásadách můžete vynutit dodržování předpisů podle polohy zařízení. Vyberte si ze stávající umístění. Žádné umístění ještě nemáte? [Použijte umístění (ohraničení sítě)](use-network-locations.md) v Intune najdete pokyny k.

1. Zvolte **umístění** > **vybrat umístění**.
2. Ze seznamu, zkontrolujte vaši polohu > **vyberte**.
3. **Uložte** zásady.

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro Android Enterprise](compliance-policy-create-android-for-work.md) zařízení.
