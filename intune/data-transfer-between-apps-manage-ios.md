---
title: Správa přenosu dat mezi aplikacemi pro iOS
titleSuffix: Microsoft Intune
description: Přečtěte si, jak používat zásady správy mobilních aplikací v Microsoft Intune ke správě přenosů dat mezi aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a1e370b65d8bfd7e61562347323bf1455dfe55b
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354294"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune

Aby bylo možné chránit podniková data, omezte přenos souborů jenom na aplikace, které spravujete. Aplikace pro iOS můžete spravovat těmito způsoby:

- Nakonfigurujte zásady ochrany aplikací pro aplikace, které zavolají aplikace **spravované zásadami** , a zabránit tak ztrátě firemních dat. Přečtěte si téma s informacemi o [všech aplikacích spravovaných přes Intune, které je možné spravovat pomocí zásad ochrany aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

- Nasaďte a spravujte aplikace přes **kanál MDM**, který vyžaduje, aby se zařízení zaregistrovala v řešení správy mobilních zařízení (MDM). Aplikace, které nasazujete, můžou být aplikace **spravované podle zásad** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. V nastavení konfigurace nastavte možnost *otevřít v* omezeních správy a pak je nasaďte pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, uplatní se vámi nastavená omezení.

## <a name="use-app-protection-with-ios-apps"></a>Použití ochrany aplikací s aplikacemi pro iOS
Pomocí zásad ochrany aplikací se službou iOS **Open in Management** můžete chránit firemní data následujícími způsoby:

- **Zařízení vlastněná zaměstnanci nejsou spravovaná žádným řešením MDM:** Nastavení zásad ochrany aplikací můžete nastavit tak, aby **aplikace mohla přenášet data do aplikací spravovaných zásadou**. Chování při *otevření* v aplikaci spravované zásadou prezentuje jenom jiné aplikace spravované zásadou jako možnosti pro sdílení. Pokud se uživatel pokusí odeslat soubor chráněný zásadou jako přílohu z OneDrivu v nativní e-mailové aplikaci, tento soubor je nečitelný.

- **Zařízení spravovaná řešeními MDM**: U zařízení zaregistrovaných v rámci služby Intune nebo řešení pro správu mobilních zařízení třetích stran je sdílení dat mezi aplikacemi se zásadami ochrany aplikací a dalšími spravovanými aplikacemi pro iOS nasazenými prostřednictvím MDM řízeno zásadami aplikací Intune a funkcí **pro iOS Open in** . Aby se zajistilo, že aplikace nasazené pomocí řešení MDM jsou taky přidružené k zásadám ochrany aplikací Intune, nakonfigurujte nastavení hlavního názvu uživatele (UPN), jak je popsáno v následující části [Konfigurace nastavení hlavního názvu uživatele (UPN)](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Chcete-li určit, jak chcete povolit přenos dat do jiných aplikací, povolte možnost **Odeslat organizační data do jiných aplikací** a pak zvolte upřednostňovanou úroveň sdílení. Pokud chcete určit, jak chcete aplikaci povolit, aby přijímala data z jiných aplikací, povolte **příjem dat z jiných aplikací** a pak zvolte upřednostňovanou úroveň přijímání dat. Další informace o přijímání a sdílení dat aplikací najdete v tématu [Nastavení přemístění dat](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro Microsoft Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce
Konfigurace nastavení hlavního názvu uživatele (UPN) je **povinná** pro zařízení spravovaná pomocí Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce. Konfigurace hlavního názvu uživatele (UPN) spolupracuje se zásadami ochrany aplikací, které nasazujete z Intune. Následující postup představuje obecné informace o tom, jak nakonfigurovat nastavení hlavního názvu uživatele (UPN) a výsledné prostředí uživatele:

1. Na portálu [Azure Portal](https://portal.azure.com) [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace iOS, které by tyto zásady měly používat.

2. Nasaďte aplikace a e-mailový profil, který chcete spravovat prostřednictvím Intune nebo řešení MDM jiného výrobce, pomocí následujících obecných kroků. Na toto prostředí se vztahuje také *Příklad 1*.

3. Nasaďte aplikaci s následujícím nastavením konfigurace aplikace na spravované zařízení:

      **Key** = IntuneMAMUPN; **hodnota** = <username@company.com>

      Příklad: [‘IntuneMAMUPN’, ‘janellecraig@contoso.com’]
      
     > [!NOTE]
     > V Intune musí být typ registrace zásady konfigurace aplikace nastavený na **spravovaná zařízení**.
     > Kromě toho musí být aplikace nainstalovaná z Portál společnosti Intune (Pokud je nastavená jako dostupná) nebo vložená jako požadovaná pro zařízení. 

4. Nasaďte **zásadu správy Open in** prostřednictvím Intune nebo jiného poskytovatele řešení MDM do zaregistrovaných zařízení.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Příklad 1: Prostředí pro správu v Intune nebo konzole MDM třetí strany

1. Přejděte do konzoly pro správu Intune nebo poskytovatele řešení MDM jiného výrobce. Přejděte do části konzoly, ve které nasadíte nastavení konfigurace aplikace do zaregistrovaných zařízení s iOSem.

2. V části Konfigurace aplikace zadejte tato nastavení:

   **Key** = IntuneMAMUPN; **hodnota** = <username@company.com>

   Skutečná syntaxe dvojice klíč/hodnota se může lišit podle toho, jakého máte jiného poskytovatele řešení MDM. V následující tabulce jsou uvedeny příklady poskytovatelů MDM třetích stran a přesné hodnoty, které byste měli zadat pro dvojici klíč/hodnota.

   |Jiný poskytovatel řešení MDM| Konfigurační klíč | Typ hodnoty | Konfigurační hodnota|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Řetězec | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Řetězec | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Řetězec | ${userUPN} **nebo** ${userEmailAddress} |
   |Správa koncových bodů Citrix | IntuneMAMUPN | Řetězec | $ {User. userPrincipalName} |
   |Správce mobilních zařízení ManageEngine | IntuneMAMUPN | Řetězec | %upn% |

> [!NOTE]  
> V případě aplikace Outlook v systému iOS když nasadíte zásadu konfigurace aplikace s možností "použití nástroje Configuration Designer", konfigurace konfiguračního klíče IntuneMAMUPN se automaticky nakonfiguruje na pozadí zásady. Další podrobnosti najdete v části Nejčastější dotazy z [nové aplikace Outlook pro zásady konfigurace aplikací pro iOS a Android – konfigurace obecné aplikace](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481). 


### <a name="example-2-end-user-experience"></a>Příklad 2: Činnost koncového uživatele

1. Uživatel nainstaluje aplikaci Microsoft Word do zařízení.

2. Uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup k e-mailu.

3. Uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4. Po spuštění aplikace Word se uživateli zobrazí výzva, abyste se přihlásili pomocí svého pracovního účtu. Účet, který uživatel zadá, musí odpovídat účtu, který jste zadali v nastavení konfigurace aplikace pro aplikaci Microsoft Word.

    > [!NOTE]
    > Uživatel může pomocí aplikace Word přidat a používat své osobní účty. Zásady ochrany aplikací se nepoužijí, pokud uživatel používá slovo mimo pracovní kontext. 

5. Po přihlášení se nastavení zásad ochrany aplikací aplikují na aplikaci Word.

6. Přenos dat bude tentokrát úspěšný a dokument se v aplikaci označí firemní identitou.  Data jsou zpracována v pracovním kontextu a nastavení zásad platí. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Ověření nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce

Po nakonfigurování nastavení hlavního názvu uživatele (UPN) ověřte schopnost aplikace pro iOS přijímat a dodržovat zásady ochrany aplikací Intune.

Například nastavení zásad **vyžadovat kód PIN aplikace** se snadno otestuje. Pokud se nastavení zásad rovná **Ano**, uživateli se zobrazí výzva k nastavení nebo zadání kódu PIN, než bude moci získat přístup k firemním datům.

Nejdřív pro aplikaci pro iOS [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md). Další informace o tom, jak testovat zásady ochrany aplikací, najdete v tématu [ověření zásad ochrany aplikací](app-protection-policies-validate.md).


## <a name="see-also"></a>Viz také:
[Co jsou zásady ochrany aplikací Intune](app-protection-policy.md)
