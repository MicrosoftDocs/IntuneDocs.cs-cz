---
title: Microsoft Intune App SDK pro testování Příručka vývojáře pro Android
description: Microsoft Intune App SDK pro Android – příručka testování umožňuje testovat svou aplikaci s Androidem spravovaná pomocí Intune.
keywords: Sada SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4203f424c395399cb0ed1e7472b006602aa0b210
ms.sourcegitcommit: db7a6b8fc9e82dae4f2111ca0b2d3c14e33658f9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58073242"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Microsoft Intune App SDK pro testování průvodce vývojáři pro Android

Microsoft Intune App SDK pro Android – příručka testování je určená vám pomůže otestovat aplikaci s Androidem spravovaná pomocí Intune.  

## <a name="prerequisite-test-accounts"></a>Požadovaný test účty
Nové účty lze vytvořit a nemusíte předem generovaná data. Chcete-li vytvořit nový účet:
1. Přejděte [Microsoft Demos](https://demos.microsoft.com/environments/create/tenant) lokality. 
2. [Nastavení Intune](https://docs.microsoft.com/intune/setup-steps) povolit správu mobilních zařízení (MDM).
3. [Vytvoření uživatelů](https://docs.microsoft.com/intune/users-add).
4. [Vytvoření skupin](https://docs.microsoft.com/intune/groups-add).
5. [Přiřazení licencí](https://docs.microsoft.com/intune/licenses-assign) odpovídajícím způsobem pro testování.


## <a name="azure-portal-policy-configuration"></a>Konfigurace zásad Azure portal
[Vytvoření a přiřazení zásad ochrany aplikací](https://docs.microsoft.com/intune/app-protection-policies) v [okno v Intune Azure portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Vaše [zásady Konfigurace aplikací](https://docs.microsoft.com/intune/app-configuration-policies-overview) lze také vytvořit a přiřadit v okně Intune.

> [!NOTE]
> Pokud vaše aplikace není uvedená na webu Azure Portal, můžete zacílíte ho pomocí zásad tak, že vyberete **více aplikací** možnost a poskytnutí názvu balíčku v textovém poli.

> [!IMPORTANT]
> Pro zásady Konfigurace aplikací použít, musí být cílem registraci uživatele [zásady ochrany aplikací Intune](https://docs.microsoft.com/intune/app-protection-policy).

## <a name="test-cases"></a>Testovací případy

Následující testovací případy popisuje kroky konfigurace a potvrzení hesla. Použijte tyto pokyny při řešení problémů s Androidem aplikací spravovaných v Intune.

### <a name="required-pin-and-corporate-credentials"></a>Vyžadovat kód PIN a podnikové přihlašovací údaje

Může vyžadovat kód pin pro přístup k firemním prostředkům. Můžete také vynutit podnikové ověřování předtím, než se uživatelé můžou používat spravované aplikace. Chcete-li nastavit tyto požadavky, postupujte následovně:

1. Konfigurace **požadovat kód PIN pro přístup k** a **vyžadovat pro přístup podnikové přihlašovací údaje** k **Ano**. Další informace najdete v tématu [nastavení zásad ochrany aplikací pro Android v Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Zkontrolujte následující podmínky:
    - Spuštění aplikace by se měl prokázat výzvu pro PIN kód. input/nastavení a/nebo produkční uživatele použité během registrace na portálu společnosti.
    - Selhání předložit platný výzvě přihlášení může být způsobeno není správně nakonfigurován. android manifest, konkrétně hodnoty pro integraci knihovny ADAL (SkipBroker ClientID a autorita).
    - Selhání prezentovat libovolného řádku může být z důvodu nesprávně integrované `MAMActivity` hodnotu. Další informace o `MAMActivity`, naleznete v tématu [Microsoft Intune App SDK pro Android developer průvodce](app-sdk-android.md).

> [!NOTE] 
> Pokud výše uvedené testů nefunguje, následující testy se pravděpodobně také nezdaří. Kontrola [SDK](app-sdk-android.md##sdk-integration) a [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) integrace.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Omezit přenos a přijímání dat s jinými aplikacemi
Můžete ovládat přenosy dat mezi podnikovým spravované aplikace následujícím způsobem:

1. Nastavte **povolit aplikaci posílat data do jiných aplikací** k **aplikacemi spravovanými podle zásad**.
2. Nastavte **povolit aplikaci přijímat data z jiných aplikací** k **všechny aplikace**. Tyto zásady ovlivní pomocí tříd Intent a poskytovatelů obsahu.
3. Zkontrolujte následující podmínky:
    - Otevření z nespravovaných aplikací do vaší aplikace funkcí správně.
    - Je povolené sdílení obsahu mezi spravovanými aplikacemi.
    - Sdílení ze spravovaných aplikací do nespravované aplikace (například Chrome) je blokován.

### <a name="restrict-cut-copy-and-paste"></a>Omezit vyjmutí, zkopírování a vložení
Můžete omezit schránky systému ke spravovaným aplikacím následujícím způsobem:

1. Nastavte **omezit vyjmutí, kopírování a vkládání v ostatních aplikacích** k **s vložením spravované podle zásad**.
2. Zkontrolujte následující podmínky:
    - Zkopírování textu z vaší aplikace do spravované nespravované aplikace (například zpráv) je blokován.

### <a name="prevent-save-as"></a>Zabránit **uložit jako**
Můžete řídit **uložit jako** funkce následujícím způsobem:

1. Pokud vaše aplikace vyžaduje [integrované ovládací prvky "Uložit jako"](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), nastavte **zabránit uložit jako** k **Ano**.
2. Zkontrolujte následující podmínky:
    - Uložte je omezen na příslušné spravované umístění.

### <a name="file-encryption"></a>Šifrování souborů
Data na zařízení můžete zašifrovat následujícím způsobem:

1. Nastavte **šifrovat data aplikace** k **Ano**.
2. Zkontrolujte následující podmínky:
    - Chování normální aplikace nemá žádný vliv.

### <a name="prevent-android-backups"></a>Zabránit zálohám Androidu
Zálohování aplikace můžete řídit následujícím způsobem:

1. Pokud jste nastavili [integrované zálohování omezení](app-sdk-android.md#protecting-backup-data), nakonfigurujte **zálohám Androidu zabránit** k **Ano**.
2. Zkontrolujte následující podmínky:
    - Zálohy jsou omezeny.

### <a name="unenrollment"></a>Zrušení registrace
Spravované aplikace z firemního e-mailu a dokumentům a obsahuje můžou vzdáleně vymazat a osobní data se dešifrují, když je již spravován následujícím způsobem:

1. Na webu Azure Portal [vydat vymazání](https://docs.microsoft.com/intune/apps-selective-wipe).
2. Pokud vaše aplikace nezaregistruje pro všechny rutiny vymazání potvrďte následující podmínky:
    - Vyvolá se v úplné vymazání aplikace.
3. Pokud vaše aplikace je zaregistrovaná pro `WIPE_USER_DATA` nebo `WIPE_USER_AUXILARY_DATA`, zkontrolujte následující podmínky:
    - Spravovaný obsah se odebere z aplikace. Další informace najdete v tématu [sady Intune App SDK pro Android developer Průvodce – selektivní vymazání](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Více identit
Integrace [podpora více identit](app-sdk-android.md#multi-identity-optional) je vysoce rizikových změnu, kterou je potřeba důkladně otestovat. Nejčastější problémy budou kvůli nesprávné nastavení identity (objektu context vs. úroveň hrozby) a také soubory sledování (`MAMFileProtectionManager`).

Minimálně musí ověřit následující scénáře pro více identit:

- **Uložit jako** zásady pro spravované identity pracuje správně.
- Kopírování a vkládání, který vynutí se omezení správně z spravovat tak, aby osobní.
- Pouze data, patří do identity spravované zašifrují a osobní soubory nezmění.
- Selektivní vymazání při zrušení registrace pouze odebere data spravovaná identita.
- Koncový uživatel vyzván k podmíněnému spuštění při změně z nespravovaného do spravovaného účtu (jenom prvním).

### <a name="app-configuration-optional"></a>Konfigurace aplikací (volitelné)
Chování spravovaných aplikací můžete nakonfigurovat následujícím způsobem:

1. Pokud vaše aplikace používá jakékoli nastavení konfigurace aplikace, měli byste otestovat, že vaše aplikace správně zpracovává všechny hodnoty, které (jako správce) můžete nastavit. [Zásady Konfigurace aplikací](https://docs.microsoft.com/intune/app-configuration-policies-overview) lze vytvořit a přiřadit pomocí Intune.

## <a name="next-steps"></a>Další postup

- [Přidání – obchodní aplikace pro Android do Microsoft Intune](lob-apps-android.md).
