---
title: Nastavení dodržování předpisů s androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s Androidem Enterprise v Microsoft Intune. Nastavit pravidla pro hesla, zvolte verzi minimální nebo maximální operačního systému, omezit určité aplikace, zabránění opětovné použití hesla a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423556"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení androidu Enterprise se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které můžete konfigurovat v zařízeních s Androidem Enterprise v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy, nastavení povolené úrovně hrozby, povolit Google Play Protect a další.

Tato funkce platí pro:

- Android Enterprise

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). Pro **platformy**vyberte **Androidu Enterprise**.

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Zvolte **bloku** se začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na nebo za úrovně hrozby pro zařízení**: Toto nastavení použijte k vyhodnocování rizika z řešení Lookout MTP jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečené**: Tato možnost je nejbezpečnější a znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud, které se nacházejí v zařízení hrozby střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

### <a name="google-play-protect"></a>Ochrana služby Google Play

- **Služby Google Play je nakonfigurovaná**: **Vyžadovat** , že služby Google Play aplikace je nainstalován a povolen. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení**: **Vyžadovat** , aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **V rámci ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html) , který musí být splněny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

> [!NOTE]
> Na zařízeních s Androidem Enterprise **kontrola ohrožení aplikací** je zásad konfigurace zařízení. Pomocí zásad konfigurace, můžou správci povolit nastavení na zařízení. Další informace viz [Nastavení omezení pro zařízení s Androidem](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Nastavení vlastností zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.
- **Maximální verze operačního systému**: Pokud zařízení používá verzi operačního systému novější než verze v pravidle, přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se nezmění pravidlo, aby tuto verzi operačního systému povolovalo, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Toto nastavení se použije na úrovni zařízení. Pokud potřebujete jenom se vyžaduje heslo na úrovni pracovního profilu, použijte zásadu konfigurace. Zobrazit [nastavení konfigurace zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla**: Zvolte, pokud heslo by měl obsahovat pouze číselné znaky, nebo kombinací číslic a dalších znaků. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní**
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení**: Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. 

  Není nutné konfigurovat toto nastavení, protože zařízení s Androidem Enterprise vynutit šifrování.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: Zvolit **bloku** zařízení s "Zabezpečení > neznámé zdroje" povolené zdroje (podporuje se ve Android 4.0 – Android 7.x; není podporované nepodporováno na Androidu 8.0 a novější). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

  Není nutné ke konfiguraci tohoto nastavení jako zařízení s Androidem Enterprise vždy omezit instalaci z neznámých zdrojů.

- **Integrita modulu runtime aplikace portál společnosti**: Zvolte **vyžadují** potvrďte portálu společnosti aplikaci splňuje následující požadavky:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB**: Zvolte **bloku** chcete zabránit používání funkce ladění USB zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Není nutné konfigurovat toto nastavení, protože ladění USB bylo zakázané už na zařízení s Androidem Enterprise.

- **Minimální úroveň oprav zabezpečení**: Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu *RRRR-MM-DD*.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro Android](compliance-policy-create-android.md) zařízení.
