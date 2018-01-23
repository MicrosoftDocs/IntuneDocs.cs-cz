---
title: "Správa přenosu dat mezi aplikacemi pro iOS"
titlesuffix: Azure portal
description: "Toto téma vám vysvětlí, jak můžete použít funkci systému iOS Open-in a zásady správy mobilních aplikací ke správě přenosů dat mezi aplikacemi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83ef0050380b8b5e3741dc7b8ea57574df6df658
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
---
# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Správa přenosu dat mezi aplikacemi pro iOS
## <a name="manage-ios-apps"></a>Správa aplikací pro iOS
V rámci ochrany vašich firemních dat je potřeba zajistit, aby přenosy souborů mohly probíhat jenom v aplikacích, které spravujete.  Aplikace pro iOS můžete spravovat těmito způsoby:

-   Firemní data můžete chránit před ztrátou tím, že pro aplikace nakonfigurujete zásady ochrany aplikací. Takovým aplikacím říkáme aplikace **spravované zásadami**. Viz téma s informacemi o [všech aplikacích s nativní podporou Intune, které je možné spravovat pomocí zásad ochrany aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Aplikace také můžete nasazovat a spravovat prostřednictvím **kanálu správy mobilních zařízení (MDM)**.  K tomu je potřeba, aby byla zařízení zaregistrovaná v nějakém řešení správy mobilních zařízení. Může se jednat o aplikace **spravované zásadami** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. Omezení správy Open In se nastavují v nastavení konfigurace a nasazují pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, použijí se nastavená omezení.

##  <a name="using-app-protection-with-ios-apps"></a>Používání ochrany aplikací u aplikací pro iOS
Zásady ochrany aplikací se dají používat společně s funkcí **Správa Open In** k ochraně firemních dat těmito způsoby:

-   **Zařízení patřící zaměstnancům, která nejsou spravovaná řešením MDM:** Zásady ochrany aplikací můžete nastavit na **Povolit aplikaci přenos dat jenom do aplikací spravovaných zásadami**. Chování Open in v aplikaci spravované zásadami nabídne jako možnost pro sdílení jenom další aplikace spravované zásadami. Pokud se uživatel pokusí odeslat soubor chráněný zásadami jako přílohu z OneDrivu v nativním e-mailu, bude tento soubor nečitelný.

-   **Zařízení spravovaná v Intune:** Pro zařízení zaregistrovaná v Intune jsou přenosy dat mezi aplikacemi se zásadami ochrany aplikací a ostatními spravovanými aplikacemi pro iOS nasazenými prostřednictvím Intune automaticky povolené. Pokud chcete povolit přenos mezi aplikacemi se zásadami ochrany aplikací, povolte nastavení **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune.   

-   **Zařízení spravovaná řešením MDM jiného výrobce:** Pomocí funkce **Správa Open In** můžete omezit přenosy dat jenom do spravovaných aplikací.
Pokud chcete zajistit, aby aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k zásadám ochrany aplikací, které jste nakonfigurovali v Intune, musíte nakonfigurovat nastavení hlavního názvu uživatele (UPN) podle postupu popsaného v části [Konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting-for-third-party-emm).  Když je aplikace nasazená s nastavením hlavního názvu uživatele (UPN), použijí se pro ni zásady ochrany aplikací, jakmile se koncový uživatel přihlásí pomocí svého pracovního účtu.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro Microsoft Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce
Konfigurace nastavení hlavního názvu uživatele (UPN) je **povinná** pro zařízení spravovaná pomocí Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce. Níže popsaný postup představuje obecné kroky pro konfiguraci nastavení hlavního názvu uživatele (UPN) a výsledného prostředí koncového uživatele:

1.  Na portálu [Azure Portal](https://portal.azure.com) [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace iOS, které by tyto zásady měly používat.

2.  Nasaďte aplikace a e-mailový profil, které chcete spravovat prostřednictvím Intune nebo řešení MDM jiného výrobce, pomocí níže uvedených obecných kroků. Tato činnost je také popsaná v Příkladu 1.

3.  Nasaďte aplikaci s tímto nastavením konfigurace:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Příklad: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Nasaďte **zásadu správy Open in** prostřednictvím Intune nebo jiného poskytovatele řešení MDM do zaregistrovaných zařízení.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Příklad 1: Činnost správce v Intune nebo konzole řešení MDM jiného výrobce

1. Přejděte do konzoly pro správu Intune nebo poskytovatele řešení MDM jiného výrobce. Přejděte do části konzoly, ve které nasadíte nastavení konfigurace aplikace do zaregistrovaných zařízení s iOSem.

2. V části Konfigurace aplikace zadejte tato nastavení:

  **key** = IntuneMAMUPN, **value** = <username@company.com>

  Skutečná syntaxe dvojice klíč/hodnota se může lišit podle toho, jakého máte jiného poskytovatele řešení MDM. Níže uvedená tabulka obsahuje příklady jiných poskytovatelů řešení MDM a přesných hodnot, které je potřeba zadat ve dvojici klíč/hodnota.

|Jiný poskytovatel řešení MDM| Konfigurační klíč | Typ hodnoty | Konfigurační hodnota|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | Řetězec | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | Řetězec | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | Řetězec | ${userUPN} **nebo** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Příklad 2: Činnost koncového uživatele

1.  Koncový uživatel nainstaluje na zařízení aplikaci Microsoft Word.

2.  Koncový uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup do svého e-mailu.

3.  Koncový uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4.  Při spuštění aplikace Word se koncovému uživateli zobrazí výzva k přihlášení pomocí pracovního účtu.  Tento pracovní účet by měl odpovídat účtu zadanému v konfiguračním nastavení aplikace Microsoft Word.

    > [!NOTE]
    > Koncový uživatel potom může do Wordu přidat další osobní účty, na které se zásady ochrany aplikací při použití aplikace Word pro soukromé účely nevztahují.

5.  Pokud je přihlášení úspěšné, použije se u aplikace Word nastavení zásad ochrany aplikací.

6.  Přenos dat bude tentokrát úspěšný a dokument se v aplikaci označí firemní identitou. Kromě toho se data zpracovávají v pracovním kontextu a nastavení zásad jsou použitá odpovídajícím způsobem.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Ověření nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce

Až nakonfigurujete nastavení hlavního názvu uživatele (UPN), měli byste ověřit schopnost aplikace pro iOS přijmout zásady ochrany aplikací Intune a vyhovět jim.

Na zařízení se například dá snadno vizuálně otestovat nastavení zásad pro **požadování PINu v aplikaci**. Pokud je toto nastavení zásad nastavené na **Ano** a koncový uživatel se pokusí o přístup k firemním datům, měla by se mu zobrazit výzva k nastavení nebo zadání PIN kódu.

Nejdřív pro aplikaci pro iOS [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md). Další informace o testování zásad ochrany aplikací najdete v článku [Ověření zásad ochrany aplikací](app-protection-policies-validate.md).


### <a name="see-also"></a>Viz taky
[Co jsou zásady ochrany aplikací Intune](app-protection-policy.md)
