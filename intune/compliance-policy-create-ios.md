---
title: nastavení dodržování předpisů zařízení s Iosem v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s Iosem v Microsoft Intune. Vyžadovat e-mailu, zkontrolujte zařízení s jailbreakem nebo rootem, nastavení povolený minimální a maximální operačního systému, nastavte žádné omezení pro heslo včetně heslo délku a doby nečinnosti zařízení, omezení aplikací a dalších.
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
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec071622a2e0d49068864f8bfb47954f54c8ba4
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900277"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>nastavení pro iOS se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které můžete nakonfigurovat na zařízeních s Iosem v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení vyžadují e-mailu, začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy, nastavte úroveň, nastavte hesla vyprší povolené hrozeb a další.

Tato funkce platí pro:

- iOS

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **iOS**.

## <a name="email"></a>Email

- **Vyžaduje mobilní zařízení měla spravovaný e-mailový profil**: Pokud je nastavena na **vyžadují**, zařízení, která nemají e-mailový profil spravovaná pomocí Intune je považováno za nevyhovující předpisům. Zařízení nemůže mít spravovaný e-mailový profil, když není správně zacílené nebo pokud uživatel ručně nastavil e-mailového účtu na zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Zařízení se považuje za nedodržující předpisy v následujících situacích:

  - E-mailového profilu je přiřazena ke skupině jiný uživatel, než je skupina uživatelů cílená zásadou dodržování předpisů.
  - Uživatel už nastavil e-mailového účtu na zařízení, která odpovídá e-mailový profil Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem nakonfigurované profil a Intune ho nemůže ani spravovat. Aby vyhovovalo předpisům, musí koncový uživatel odstranit existující nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.

- **Vyberte e-mailový profil, který se musí spravovat přes Intune**: Pokud **e-mailový účet se musí spravovat přes Intune** je vybráno nastavení, zvolte **vyberte** k zadání e-mailový profil Intune. E-mailový profil musí existovat v zařízení.

Podrobnosti o e-mailových profilech najdete v tématu [konfigurace přístupu k organizaci e-mailu pomocí e-mailové profily v Intune](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Zařízení s Jailbreakem**: Zvolte **bloku** se začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na nebo za úrovně hrozby pro zařízení** (iOS 8.0 a novější): Toto nastavení použijte k vyhodnocování rizik jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečené**: Tato možnost je nejbezpečnější a znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud se zjistí, že zařízení s libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud, které se nacházejí v zařízení hrozby střední nebo nízké úrovni. Pokud se zařízení zjistí hrozby vysoké úrovně, má vyhodnotí jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém** (iOS 8.0 a novější): Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel může zvolit upgrade svého zařízení. Po tomto jejich přístup k prostředkům organizace.
- **Maximální povolená verze operačního systému** (iOS 8.0 a novější): Pokud zařízení používá verzi operačního systému novější než verze v pravidle, přístup k prostředkům organizace, blokovaný. Koncovému uživateli se zobrazí výzva, chcete-li kontaktovat správce IT. Zařízení nemá přístup k prostředkům organizace, dokud pravidla se změní na verzi operačního systému povolí.
- **Minimální operační systém sestavení verze** (iOS 8.0 a novější): Jakmile Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, nikoli na verzi operačního systému. Pomocí této funkce lze zadat číslo minimální povolenou sestavení na zařízení.
- **Maximální verze operačního systému sestavení verze** (iOS 8.0 a novější): Jakmile Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, nikoli na verzi operačního systému. Pomocí této funkce lze zadat maximální povolené sestavení číslo na zařízení.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

> [!NOTE]
> Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k nastavení hesla. Uživatelům se výzva bude zobrazovat tak dlouho, dokud heslo nenastaví.

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.
- **Jednoduchá hesla**: Nastavte na **bloku** , uživatelé nemůžou vytvářet jednoduchá hesla, jako například **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaků, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
- **Počet nealfanumerických znaků v hesle**: Zadejte minimální počet speciálních znaků, jako například `&`, `#`, `%`, `!`, a tak dále, který musí být v hesle.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dříve použitých hesel, která nelze použít.

### <a name="device-security"></a>Zabezpečení zařízení

- **Omezených aplikací**: Aplikace můžete omezit přidáním jejich ID sady prostředků do zásady. Pokud má zařízení nainstalovanou aplikaci, je zařízení označeno jako nedodržující předpisy.

  - **Název aplikace**: Zadejte popisný název, abyste mohli snáze zjistit ID sady prostředků.
  - **ID sady prostředků aplikace**: Zadejte jedinečnou sadu identifikátor přiřazený poskytovatelem aplikace. ID sady prostředků najdete v tématu [jak najít ID sady prostředků aplikace pro iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (otevře jiný web společnosti Microsoft).  

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro macOS](compliance-policy-create-mac-os.md) zařízení.
