---
title: "Správa přenosu dat mezi aplikacemi pro iOS | Intune Azure Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Toto téma vám pomůže pochopit, jak můžete použít funkci systému iOS Otevřít v a zásady správy mobilních aplikací ke správě přenosů dat mezi aplikacemi."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 44747236ba1bda84ccb01f613e1702c536720a2c
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Správa přenosu dat mezi aplikacemi pro iOS
## <a name="manage-ios-apps"></a>Správa aplikací pro iOS
V rámci ochrany vašich firemních dat je potřeba zajistit, aby přenosy souborů mohly probíhat jenom v aplikacích, které spravujete.  Aplikace pro iOS můžete spravovat těmito způsoby:

-   Firemní data můžete chránit před ztrátou tím, že pro aplikace nakonfigurujete zásady ochrany aplikací. Takovým aplikacím říkáme aplikace **spravované zásadami**. Viz téma s informacemi o [všech aplikacích s nativní podporou Intune, které je možné spravovat pomocí zásad ochrany aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Aplikace také můžete nasazovat a spravovat prostřednictvím **kanálu správy mobilních zařízení (MDM)**.  K tomu je potřeba, aby byla zařízení zaregistrovaná v nějakém řešení správy mobilních zařízení. Může se jednat o aplikace **spravované zásadami** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. Omezení správy Open In se nastavují v nastavení konfigurace a nasazují pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, použijí se nastavená omezení.
##  <a name="using-app-protection-with-ios-apps"></a>Používání ochrany aplikací u aplikací pro iOS
Zásady ochrany aplikací se dají používat společně s funkcí **Správa Open In** k ochraně firemních dat těmito způsoby:

-   **Zařízení patřící zaměstnancům, která nejsou spravovaná řešením MDM:** Zásady ochrany aplikací můžete nastavit na **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Koncový uživatel nebude moci otevřít chráněný soubor v aplikaci, která není spravována zásadami.

-   **Zařízení spravovaná v Intune:** Pro zařízení zaregistrovaná v Intune jsou přenosy dat mezi aplikacemi se zásadami ochrany aplikací a ostatními spravovanými aplikacemi pro iOS nasazenými prostřednictvím Intune automaticky povolené. Pokud chcete povolit přenos mezi aplikacemi se zásadami ochrany aplikací, povolte nastavení **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune.   

-   **Zařízení spravovaná řešením MDM jiného výrobce:** Pomocí funkce **Správa Open In** můžete omezit přenosy dat jenom do spravovaných aplikací.
Pokud chcete zajistit, aby aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k zásadám ochrany aplikací, které jste nakonfigurovali v Intune, musíte nakonfigurovat nastavení hlavního názvu uživatele (UPN) podle postupu popsaného v části [Konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting-for-third-party-emm).  Když je aplikace nasazená s nastavením hlavního názvu uživatele (UPN), použijí se pro ni zásady ochrany aplikací, jakmile se koncový uživatel přihlásí pomocí svého pracovního účtu.

> [!IMPORTANT]
> Nastavení hlavního názvu uživatele (UPN) se vyžaduje jenom pro aplikace nasazené na zařízení spravovaná řešením MDM jiného výrobce.  U zařízení spravovaných pomocí Intune se toto nastavení nevyžaduje.


## <a name="configure-user-upn-setting-for-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce
Konfigurace nastavení hlavního názvu uživatele (UPN) je **nutná** pro zařízení spravovaná pomocí řešení MDM jiného výrobce. Níže popsaný postup představuje obecné kroky pro konfiguraci nastavení hlavního názvu uživatele (UPN) a výsledného prostředí koncového uživatele:


1.  Na portálu [Azure Portal](https://portal.azure.com) [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace iOS, které by tyto zásady měly používat.

2.  Nasaďte aplikace a e-mailový profil, které chcete spravovat **prostřednictvím řešení MDM jiného výrobce**, pomocí níže uvedených obecných kroků. Tato činnost je také popsaná v Příkladu 1.

  1.  Nasaďte aplikaci s tímto nastavením konfigurace:

      **key** = IntuneMAMUPN, **value** = <username@company.com>

      Příklad: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Nasaďte zásadu správy Open in prostřednictvím jiného poskytovatele řešení MDM do zaregistrovaných zařízení.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Příklad 1: Činnost správce v konzole MDM jiného výrobce

1. Přejděte do konzoly pro správu od jiného poskytovatele řešení MDM. Přejděte do části konzoly, ve které nasadíte nastavení konfigurace aplikace do zaregistrovaných zařízení s iOSem.

2. V části Konfigurace aplikace zadejte tato nastavení:

  **key** = IntuneMAMUPN, **value** = <username@company.com>

  Skutečná syntaxe dvojice klíč/hodnota se může lišit podle toho, jakého máte jiného poskytovatele řešení MDM. Níže uvedená tabulka obsahuje příklady jiných poskytovatelů řešení MDM a přesných hodnot, které je potřeba zadat ve dvojici klíč/hodnota.

|Jiný poskytovatel řešení MDM| Konfigurační klíč | Typ hodnoty | Konfigurační hodnota|
| ------- | ---- | ---- | ---- |
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

