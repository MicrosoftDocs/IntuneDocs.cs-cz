---
title: nastavení dodržování předpisů pro zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení s iOS v Microsoft Intune. Vyžadovat e-mail, podívejte se na zařízení s jailbreakem nebo rootem, nastavte povolený minimální a maximální operační systém, nastavte jakákoli omezení hesla, včetně délky hesla a nečinnosti zařízení, omezit aplikace a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ac2ec4224bead13455752488f6ea34af6e012bc8
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729798"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>nastavení iOS k označení zařízení jako kompatibilních nebo nekompatibilních s Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních s iOS v Intune. Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení pro vyžadování e-mailu, označení rootem (jailbreak) zařízení jako nevyhovující předpisům, nastavení povolené úrovně hrozby, nastavení hesel pro vypršení platnosti a další.

Tato funkce platí pro:

- iOS

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **iOS**.

## <a name="email"></a>E-mailu

- **Vyžadovat, aby mobilní zařízení měla spravovaný e-mailový profil**: Pokud je nastavení **vyžadováno**, zařízení, která nemají e-mailový profil spravovaná přes Intune, se považují za nedodržující předpisy. Zařízení nemůže mít spravovaný e-mailový profil, pokud není správně cíleno nebo pokud uživatel ručně nastavil e-mailový účet na zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Zařízení je považováno za nedodržující předpisy v následujících situacích:

  - E-mailový profil se přiřadí jiné skupině uživatelů, než je skupina uživatelů, na kterou cílí zásady dodržování předpisů.
  - Uživatel už na zařízení nastavil e-mailový účet, který se shoduje s e-mailovým profilem Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem nakonfigurovaný profil a Intune ho nemůže spravovat. Aby bylo možné nastavit dodržování předpisů, musí koncový uživatel odebrat existující nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.

- **Vybrat e-mailový profil, který se musí spravovat přes Intune**: Pokud je vybraná možnost **e-mailový účet musí být spravovaný přes Intune** , zvolte **Vybrat** a zadejte e-mailový profil Intune. E-mailový profil musí existovat na zařízení.

Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k e-mailu organizace pomocí e-mailových profilů s Intune](../configuration/email-settings-configure.md)

## <a name="device-health"></a>Device health

- **Zařízení s jailbreakem**: vyberte **blok** pro označení zařízení s jailbreakem (jailbreak) jako nevyhovující předpisům. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na úrovni hrozby pro zařízení nebo pod** ní (iOS 8,0 a novější): Toto nastavení použijte, pokud chcete vyhodnotit hodnocení rizik jako podmínku pro dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější a znamená, že na zařízení nesmí být žádné hrozby. Pokud se zjistí, že zařízení má žádnou úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení bude mít hrozby vysoké úrovně, je zjištěno, že nedodržuje předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém** (iOS 8,0 a novější): Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může upgradovat svoje zařízení. Pak mají přístup k prostředkům organizace.
- **Maximální povolená verze operačního systému** (iOS 8,0 a novější): Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které povoluje verzi operačního systému.
- **Minimální verze buildu operačního systému** (iOS 8,0 a novější): když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat minimální povolené číslo sestavení v zařízení.
- **Maximální verze buildu operačního systému** (iOS 8,0 a novější): když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat maximální povolené číslo sestavení v zařízení.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

> [!NOTE]
> Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k nastavení hesla. Uživatelům se výzva bude zobrazovat tak dlouho, dokud heslo nenastaví.

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
- **Počet nealfanumerických znaků v hesle**: zadejte minimální počet speciálních znaků (například `&`, `#`, `%`, `!` atd.), které musí být v hesle.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)** : Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nedají použít znovu**: zadejte počet dříve použitých hesel, která se nedají použít.

### <a name="device-security"></a>Zabezpečení zařízení

- **Omezené aplikace**: Aplikace můžete omezit přidáním jejich ID sady prostředků do zásady. Pokud je aplikace v zařízení nainstalovaná, zařízení se označí jako nevyhovující.

  - **Název aplikace**: Zadejte popisný název, který vám pomůže dané ID sady prostředků identifikovat.
  - **ID sady prostředků aplikace**: Zadejte jedinečný identifikátor sady prostředků přidělený poskytovatelem aplikace. ID sady najdete v tématu [Jak najít ID sady prostředků pro aplikaci pro iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (otevře se další web Microsoftu).  

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení MacOS](compliance-policy-create-mac-os.md) .
