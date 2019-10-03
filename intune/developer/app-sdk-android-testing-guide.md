---
title: Příručka pro vývojové testování v sadě Microsoft Intune App SDK pro Android
description: Průvodce testováním sady Microsoft Intune App SDK pro Android vám pomůže otestovat aplikaci pro Android spravovanou v Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1484567721283ddb91f3ecebbc448e7356ceaf5a
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830538"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Průvodce testováním sady Microsoft Intune App SDK pro vývojáře v Androidu

Průvodce testováním sady Microsoft Intune App SDK pro Android je navržený tak, aby vám pomohla při testování aplikace pro Android spravované v Intune.  

## <a name="prerequisite-test-accounts"></a>Požadované zkušební účty
Je možné vytvořit nové účty s předem generovanými daty a bez nich. Vytvoření nového účtu:
1. Přejděte na web [ukázek ukázek společnosti Microsoft](https://demos.microsoft.com/environments/create/tenant) . 
2. [Nastavte Intune](../fundamentals/setup-steps.md) pro povolení správy mobilních zařízení (MDM).
3. [Vytvořte uživatele](../fundamentals/users-add.md).
4. [Vytvořte skupiny](../fundamentals/groups-add.md).
5. [Přiřaďte licence](../fundamentals/licenses-assign.md) podle potřeby pro vaše testování.


## <a name="azure-portal-policy-configuration"></a>Konfigurace zásad Azure Portal
[Vytvořte a přiřaďte zásady ochrany aplikací](../apps/app-protection-policies.md) v okně [Intune Azure Portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). [Zásady konfigurace aplikací](../apps/app-configuration-policies-overview.md) se taky dají vytvořit a přiřadit v okně Intune.

> [!NOTE]
> Pokud vaše aplikace není uvedená v Azure Portal, můžete na ni cílit pomocí zásady výběrem možnosti **Další aplikace** a zadáním názvu balíčku do textového pole.

## <a name="test-cases"></a>Testovací případy

Následující testovací případy poskytují kroky konfigurace a potvrzení. Tyto pokyny vám pomůžou při řešení problémů s aplikacemi pro Android spravovanými přes Intune.

### <a name="required-pin-and-corporate-credentials"></a>Požadované PIN a firemní přihlašovací údaje

Pro přístup k firemním prostředkům můžete vyžadovat PIN kód. Můžete taky vymáhat podnikové ověřování, aby mohli uživatelé používat spravované aplikace. Pro nastavení těchto požadavků použijte následující postup:

1. Nakonfigurujte **pro přístup vyžadování PIN kódu** a pro přístup k **Ano** **vyžadovat podnikové přihlašovací údaje** . Další informace najdete v tématu [nastavení zásad ochrany aplikací pro Android v Microsoft Intune](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Potvrďte následující podmínky:
    - Při spuštění aplikace by se měla zobrazit výzva k zadání kódu PIN pro vstup/nastavení nebo k výrobnímu uživateli, který se použil při registraci s Portál společnosti.
    - Nepovedlo se vytvořit platnou výzvu k přihlášení kvůli nesprávně nakonfigurovanému manifestu Androidu, konkrétně hodnoty pro integraci ADAL (SkipBroker, ClientID a Authority).
    - K chybě může dojít z důvodu nesprávné integrované @no__t hodnoty 0. Další informace o `MAMActivity` najdete v tématu [Microsoft Intune App SDK pro Android – příručka pro vývojáře](app-sdk-android.md).

> [!NOTE] 
> Pokud výše uvedený test nefunguje, testy níže budou pravděpodobně také neúspěšné. Projděte si integraci [sady SDK](app-sdk-android.md##sdk-integration) a [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) .

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Omezení přenosu a příjem dat s jinými aplikacemi
Přenos dat mezi podnikovými spravovanými aplikacemi můžete řídit následujícím způsobem:

1. Nastavte možnost **povoluje aplikaci přenášet data do jiných aplikací** do **aplikací spravovaných podle zásad**.
2. Nastavte **možnost dovolit aplikaci, aby přijímala data z jiných aplikací** do **všech aplikací**. Používání záměrů a poskytovatelů obsahu bude mít vliv na tyto zásady.
3. Potvrďte následující podmínky:
    - Správné otevření z nespravované aplikace do funkce aplikace.
    - Sdílení obsahu mezi spravovanými aplikacemi je povolené.
    - Sdílení ze spravovaných aplikací do nespravovaných aplikací (například Chrome) je zablokované.

### <a name="restrict-cut-copy-and-paste"></a>Omezit vyjmutí, kopírování a vložení
Systémovou schránku můžete omezit na spravované aplikace následujícím způsobem:

1. Nastavte **Omezit vyjmutí, kopírování a vložení s jinými aplikacemi** do **zásad spravovaných pomocí vložit**.
2. Potvrďte následující podmínky:
    - Kopírování textu z aplikace do spravované nespravované aplikace (například zprávy) je zablokované.

### <a name="prevent-save-as"></a>Zabránit **uložení jako**
Funkci **Uložit jako** můžete řídit následujícím způsobem:

1. Pokud vaše aplikace vyžaduje [Integrované ovládací prvky Uložit jako](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), nastavte možnost **zakázat možnost Uložit jako** na **Ano**.
2. Potvrďte následující podmínky:
    - Uložení je omezené jenom na vhodná spravovaná umístění.

### <a name="file-encryption"></a>Šifrování souborů
Data v zařízení můžete šifrovat následujícím způsobem:

1. Nastavte **šifrovat data aplikací** na **Ano**.
2. Potvrďte následující podmínky:
    - Normální chování aplikace není ovlivněno.

### <a name="prevent-android-backups"></a>Zabránit zálohování Androidu
Zálohování aplikací můžete řídit následujícím způsobem:

1. Pokud jste nastavili [integrovaná omezení zálohování](app-sdk-android.md#protecting-backup-data), nakonfigurujte **zabránit zálohování Androidu** na **Ano**.
2. Potvrďte následující podmínky:
    - Zálohy jsou omezené.

### <a name="unenrollment"></a>Zrušení registrace
Spravované aplikace můžete vzdáleně vymazat z obsahujícího podnikového e-mailu a dokumentů a osobní údaje se dešifrují, když je už nespravujete takto:

1. Z Azure Portal [vydejte vymazání](../apps/apps-selective-wipe.md).
2. Pokud se vaše aplikace neregistruje pro jakékoli obslužné rutiny vymazání, potvrďte následující podmínky:
    - Dojde k úplnému vymazání aplikace.
3. Pokud je vaše aplikace zaregistrovaná pro `WIPE_USER_DATA` nebo `WIPE_USER_AUXILARY_DATA`, potvrďte následující podmínky:
    - Spravovaný obsah se z aplikace odebere. Další informace najdete v tématu [sada Intune App SDK pro Android Developer Guide – selektivní vymazání](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Více identit
Integrace [podpory více identit](app-sdk-android.md#multi-identity-optional) je vysoce riziková změna, kterou je třeba důkladně otestovat. Nejběžnější problémy budou kvůli nesprávnému nastavení identity (kontext vs. úroveň ohrožení) a také sledování souborů (`MAMFileProtectionManager`).

U více identit je potřeba znovu ověřit následující scénáře:

- Zásada **Uložit jako** pro spravované identity funguje správně.
- Omezení kopírování pro vložení se správně vynutila ze spravovaných na osobní.
- Šifrovaná jsou jenom data patřící do spravované identity a osobní soubory se nemění.
- Selektivní vymazání během Odregistrace odebírá jenom spravovaná data identity.
- Koncový uživatel se při změně z nespravovaného na spravovaný účet vyzve k zadání podmíněného spuštění.

### <a name="app-configuration-optional"></a>Konfigurace aplikace (volitelné)
Chování spravovaných aplikací můžete nakonfigurovat následujícím způsobem:

1. Pokud vaše aplikace spotřebovává nastavení konfigurace aplikace, měli byste otestovat, jestli vaše aplikace správně zpracovává všechny hodnoty, které jste (jako správce) mohli nastavit. [Zásady konfigurace aplikací](../apps/app-configuration-policies-overview.md) se dají vytvářet a přiřazovat pomocí Intune.

## <a name="next-steps"></a>Další kroky

- [Přidejte obchodní aplikaci pro Android do Microsoft Intune](../apps/lob-apps-android.md).
