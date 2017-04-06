---
title: "Správa přenosu dat mezi aplikacemi pro iOS | Dokumentace Microsoftu"
description: "Toto téma použijte k pochopení, jak můžete použít funkci systému iOS Otevřít v a zásady správy mobilních aplikací ke správě přenosů dat mezi aplikacemi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c66226b7fc31f91669c4f4f0693ccbd7c679189f
ms.openlocfilehash: e71ebacec9d7b890b41e7650c8c50f42952c6326
ms.lasthandoff: 03/29/2017


---

# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>Správa aplikací pro iOS
V rámci ochrany vašich firemních dat je potřeba zajistit, aby přenosy souborů mohly probíhat jenom v aplikacích, které spravujete.  Aplikace pro iOS můžete spravovat těmito způsoby:

-   Firemní data můžete chránit před ztrátou tím, že pro aplikace nakonfigurujete zásady ochrany aplikací. Takovým aplikacím říkáme aplikace **spravované zásadami**.

-   Aplikace také můžete nasazovat a spravovat prostřednictvím **kanálu správy mobilních zařízení (MDM)**.  K tomu je potřeba, aby byla zařízení zaregistrovaná v nějakém řešení správy mobilních zařízení. Může se jednat o aplikace **spravované zásadami** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazené prostřednictvím **kanálu MDM**. Omezení správy Open In se nastavují v nastavení konfigurace a nasazují pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, použijí se nastavená omezení.

##  <a name="manage-data-transfer-between-ios-apps"></a>Správa přenosu dat mezi aplikacemi pro iOS
Zásady ochrany aplikací se dají použít společně s funkcí **Správa Open In** k ochraně firemních dat těmito způsoby:

-   **Zařízení patřící zaměstnancům, která nejsou spravovaná řešením MDM:** Můžete nastavit [nastavení zásad ochrany aplikací](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) na **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Když koncový uživatel otevře chráněný soubor v aplikaci, která není spravovaná zásadami, soubor nejde přečíst.

-   **Zařízení spravovaná v Intune:** Pro zařízení zaregistrovaná v Intune jsou přenosy dat mezi aplikacemi se zásadami ochrany aplikací a ostatními spravovanými aplikacemi pro iOS nasazenými prostřednictvím Intune automaticky povolené. Pokud chcete povolit přenos mezi aplikacemi se zásadami ochrany aplikací, povolte nastavení **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune.   

-   **Zařízení spravovaná řešením MDM jiného výrobce:** Pomocí funkce **Správa Open In** můžete omezit přenosy dat jenom do spravovaných aplikací.
Pokud chcete zajistit, aby aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k zásadám ochrany aplikací, které jste nakonfigurovali v Intune, musíte nakonfigurovat nastavení hlavního názvu uživatele (UPN) podle postupu popsaného v části [Konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting-for-third-party-emm).  Když je aplikace nasazená s nastavením hlavního názvu uživatele (UPN), použijí se pro ni zásady ochrany aplikací, jakmile se koncový uživatel přihlásí pomocí svého pracovního účtu.

> [!IMPORTANT]
> Nastavení hlavního názvu uživatele (UPN) se vyžaduje jenom pro aplikace nasazené na zařízení spravovaná řešením MDM jiného výrobce.  U zařízení spravovaných pomocí Intune se toto nastavení nevyžaduje.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce
Konfigurace nastavení hlavního názvu uživatele (UPN) je **nutná** pro zařízení spravovaná pomocí řešení MDM jiného výrobce. Níže popsaný postup představuje obecné kroky pro konfiguraci nastavení hlavního názvu uživatele (UPN) a výsledného prostředí koncového uživatele:


1.  Na portálu Azure Portal [nakonfigurujte zásady ochrany aplikací](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace, které by tyto zásady měly používat.

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
| VMware AirWatch | IntuneMAMUPN | Řetězec | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Řetězec | $EMAIL$ **nebo** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Řetězec | ${userUPN} **nebo** ${userEmailAddress} |

### <a name="example-2-end-user-experience"></a>Příklad 2: Činnost koncového uživatele

1.  Koncový uživatel nainstaluje na zařízení aplikaci Microsoft Word.

2.  Koncový uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup do svého e-mailu.

3.  Koncový uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4.  Při spuštění aplikace Word se koncovému uživateli zobrazí výzva k přihlášení pomocí pracovního účtu.  Tento pracovní účet by měl odpovídat účtu zadanému v konfiguračním nastavení aplikace Microsoft Word.

    > [!NOTE]
    > Koncový uživatel potom může do Wordu přidat další osobní účty, na které se zásady ochrany aplikací při použití aplikace Word pro soukromé účely nevztahují.

5.  Pokud je přihlášení úspěšné, použije se u aplikace Word nastavení zásad ochrany aplikací.

6.  Přenos souborů byl tentokrát úspěšný a dokument se v aplikaci označí firemní identitou. Kromě toho se soubor zpracovává v pracovním kontextu a nastavení zásad jsou použitá odpovídajícím způsobem.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Ověření nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce

Až nakonfigurujete nastavení hlavního názvu uživatele (UPN), měli byste ověřit schopnost aplikace pro iOS přijmout zásady ochrany aplikací Intune a vyhovět jim.

Na zařízení se například dá snadno vizuálně otestovat nastavení zásad pro **požadování PINu v aplikaci**. Pokud je toto nastavení zásad nastavené na **Ano** a koncový uživatel se pokusí o přístup k firemním datům, měla by se mu zobrazit výzva k nastavení nebo zadání PIN kódu.

Nejdříve pro aplikaci pro iOS [vytvořte a nasaďte zásady ochrany aplikací](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md). Další informace o testování zásad ochrany aplikací najdete v článku [Ověření zásad ochrany aplikací](validate-mobile-application-management.md).



### <a name="see-also"></a>Viz taky
[Ochrana dat aplikací pomocí zásad ochrany aplikací v Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

