---
title: Správa přenosu dat mezi aplikacemi pro iOS
titleSuffix: Microsoft Intune
description: Naučte se používat zásady správy mobilních aplikací v Microsoft Intune ke správě přenosů dat mezi aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
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
ms.openlocfilehash: b9b93ec96eb6480c04514f1505a787332dd13625
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940008"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Správa přenosu dat mezi aplikacemi pro iOS v Microsoft Intune

Aby bylo možné chránit podniková data, omezte přenos souborů jenom na aplikace, které spravujete. Aplikace pro iOS můžete spravovat následujícími způsoby:

- Chraňte data organizace pro pracovní nebo školní účty tak, že nakonfigurujete zásady ochrany aplikací pro aplikace. které říkáme *aplikacím spravovaným zásadou*.  Zobrazit [všechny aplikace spravované v Intune, které můžete spravovat pomocí zásad ochrany aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

- Nasaďte a spravujte aplikace přes správu zařízení s iOS, která vyžaduje, aby se zařízení zaregistrovala v řešení správy mobilních zařízení (MDM). Aplikace, které nasazujete, můžou být *aplikace spravované zásadou* nebo jinými aplikacemi spravovanými v iOS.

Funkce **správy otevřených v** zaregistrovaných zařízeních s iOS může omezit přenosy souborů mezi aplikacemi spravovanými v iOS. V nastavení konfigurace Nastavte omezení *správy Open in* a pak je nasaďte pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, uplatní se vámi nastavená omezení.

## <a name="use-app-protection-with-ios-apps"></a>Použití ochrany aplikací s aplikacemi pro iOS
Pomocí zásad ochrany aplikací se službou pro **správu** systému iOS můžete chránit data společnosti následujícími způsoby:

- **Zařízení nespravovaná žádným řešením MDM:** Nastavení zásad ochrany aplikací můžete nastavit tak, abyste mohli řídit sdílení dat s jinými aplikacemi prostřednictvím rozšíření *otevřít* nebo *sdílet*.  Uděláte to tak, že nakonfigurujete nastavení **Odeslat organizační data na jiné aplikace** do **aplikací spravovaných podle zásad s hodnotou filtrování otevřít v/sdílet** .  Chování funkce *otevřít v/sdílet* v *aplikaci spravované zásadou* prezentuje jenom jiné *aplikace spravované zásadou* jako možnosti pro sdílení. 

- **Zařízení spravovaná řešeními MDM**: u zařízení zaregistrovaných v řešení MDM pro Intune nebo jiných výrobců se sdílení dat mezi aplikacemi se zásadami ochrany aplikací a dalšími spravovanými aplikacemi pro iOS nasazenými prostřednictvím MDM řídí zásadami aplikací Intune a s **otevřenými iOS. funkce správy** . Aby se zajistilo, že aplikace nasazené pomocí řešení MDM jsou taky přidružené k zásadám ochrany aplikací Intune, nakonfigurujte nastavení hlavního názvu uživatele (UPN), jak je popsáno v následující části [Konfigurace nastavení hlavního názvu uživatele (UPN)](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Chcete-li určit, jak chcete povolit přenos dat do jiných aplikací, povolte možnost **Odeslat organizační data do jiných aplikací** a pak zvolte upřednostňovanou úroveň sdílení. Pokud chcete určit, jak chcete aplikaci povolit, aby přijímala data z jiných aplikací, povolte **příjem dat z jiných aplikací** a pak zvolte upřednostňovanou úroveň přijímání dat. Další informace o přijímání a sdílení dat aplikací najdete v tématu [Nastavení přemístění dat](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro Microsoft Intune nebo modul EMM třetích stran
Konfigurace nastavení hlavního názvu uživatele (UPN) se **vyžaduje** pro zařízení spravovaná pomocí Intune nebo řešení EMM jiného výrobce k identifikaci zaregistrovaného uživatelského účtu. Konfigurace hlavního názvu uživatele (UPN) spolupracuje se zásadami ochrany aplikací, které nasazujete z Intune. Následující postup představuje obecné informace o tom, jak nakonfigurovat nastavení hlavního názvu uživatele (UPN) a výsledné prostředí uživatele:

1. V [Azure Portal](https://portal.azure.com) [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace pro iOS, které by měly mít tuto zásadu.

2. Nasaďte aplikace a e-mailový profil, který chcete spravovat prostřednictvím Intune nebo řešení MDM jiného výrobce, pomocí následujících obecných kroků. Na toto prostředí se vztahuje také *Příklad 1*.

3. Nasaďte aplikaci s následujícím nastavením konfigurace aplikace na spravované zařízení:

      **Key** = IntuneMAMUPN, **Value** =  @ no__t-3

      Příklad: [' IntuneMAMUPN ', ' janellecraig@contoso.com ']
      
     > [!NOTE]
     > V Intune musí být typ registrace zásady konfigurace aplikace nastavený na **spravovaná zařízení**.
     > Kromě toho musí být aplikace nainstalovaná z Portál společnosti Intune (Pokud je nastavená jako dostupná) nebo vložená jako požadovaná pro zařízení. 

4. Nasaďte zásadu **správy Open in** pomocí Intune nebo poskytovatele MDM třetí strany na zaregistrovaná zařízení.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Příklad 1: prostředí pro správu v Intune nebo konzole MDM třetí strany

1. Přejdete do konzoly pro správu Intune nebo vašeho poskytovatele MDM jiného výrobce. V části konzoly, ve které nasadíte nastavení konfigurace aplikace na zaregistrovaná zařízení se systémem iOS.

2. V části Konfigurace aplikace zadejte následující nastavení:

   **Key** = IntuneMAMUPN, **Value** =  @ no__t-3

   Přesná syntaxe dvojice klíč/hodnota se může lišit v závislosti na vašem poskytovateli MDM jiného výrobce. V následující tabulce jsou uvedeny příklady poskytovatelů MDM třetích stran a přesné hodnoty, které byste měli zadat pro dvojici klíč/hodnota.

   |Poskytovatel MDM třetí strany| Konfigurační klíč | Typ hodnoty | Hodnota konfigurace|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | String | {{UserPrincipalName}}|
   |Prostředí VMware pro sledování| IntuneMAMUPN | String | Třídy|
   |MobileIron | IntuneMAMUPN | String | $ {userUPN} **nebo** $ {userEmailAddress} |
   |Správa koncových bodů Citrix | IntuneMAMUPN | String | $ {User. userPrincipalName} |
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | String | názvu |

> [!NOTE]  
> V případě aplikace Outlook v systému iOS když nasadíte zásadu konfigurace aplikace s možností "použití nástroje Configuration Designer", konfigurace konfiguračního klíče IntuneMAMUPN se automaticky nakonfiguruje na pozadí zásady. Další podrobnosti najdete v části Nejčastější dotazy z [nové aplikace Outlook pro zásady konfigurace aplikací pro iOS a Android – konfigurace obecné aplikace](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481). 


### <a name="example-2-end-user-experience"></a>Příklad 2: činnost koncového uživatele

*Sdílení z* aplikace spravované zásadou *do jiných aplikací se sdílením operačního systému*

1. Uživatel otevře aplikaci Microsoft OneDrive na zaregistrovaném zařízení s iOS a přihlásí se ke svému pracovnímu účtu.  Účet, který uživatel zadá, musí odpovídat hlavnímu názvu uživatele (UPN) účtu, který jste zadali v nastavení konfigurace aplikace pro aplikaci Microsoft OneDrive.

2. Po přihlášení se u správce nakonfigurovala nastavení aplikace na uživatelský účet na Microsoft OneDrive.  To zahrnuje konfiguraci nastavení **Odeslat organizační data ostatním aplikacím** do **aplikací spravovaných zásadou s hodnotou sdílení operačního systému** .

3. Uživatel zobrazí pracovní soubor a pokusí se o sdílení prostřednictvím aplikace Open-in se spravovaným systémem iOS.  

4. Přenos dat je úspěšný a data jsou teď chráněná **správou Open in** v aplikaci spravované v iOS.  APLIKACE Intune se nevztahuje na aplikace, které nejsou *aplikacemi spravovanými podle zásad*.

*Sdílení z* aplikace spravované v iOS *do* aplikace spravované zásadou *s příchozími daty organizace*

1. Uživatel otevře nativní E-mail na zaregistrovaném zařízení s iOS pomocí spravovaného e-mailového profilu.  

1. Uživatel otevře přílohu pracovního dokumentu z nativního e-mailu do aplikace Microsoft Word.

1. Při spuštění aplikace Word se objeví jedna ze dvou situací:
   1. Data jsou chráněná aplikací Intune, když:
      - Uživatel je přihlášený ke svému pracovnímu účtu, který odpovídá hlavnímu názvu uživatele (UPN) účtu, který jste zadali v nastavení konfigurace aplikace pro aplikaci Microsoft Word. 
      - Správce nakonfiguroval nastavení aplikace na uživatelský účet v aplikaci Microsoft Word.  To zahrnuje konfiguraci nastavení **přijímat data z jiných aplikací** na **všechny aplikace s hodnotou příchozích dat organizace** .
      - Přenos dat je úspěšný a dokument je označený pracovní identitou v aplikaci.  APLIKACE Intune chrání akce uživatelů pro dokument.
   1. Tato data **nejsou** CHRÁNĚNá aplikací Intune, když:
      - Uživatel **není přihlášený** ke svému pracovnímu účtu.
      - Nastavení nakonfigurovaná správcem se v aplikaci Microsoft Word **nepoužívají,** protože uživatel není přihlášený.
      - Přenos dat je úspěšný a dokument **není označený pracovní** identitou v aplikaci.  APLIKACE Intune **nechrání akce** uživatelů pro dokument, protože není aktivní.

    > [!NOTE]
    > Uživatel může pomocí aplikace Word přidat a používat své osobní účty. Zásady ochrany aplikací se nepoužijí, pokud uživatel používá slovo mimo pracovní kontext. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Ověřit nastavení hlavního názvu uživatele (UPN) pro modul EMM třetích stran

Po nakonfigurování nastavení hlavního názvu uživatele (UPN) ověřte schopnost aplikace pro iOS přijímat a dodržovat zásady ochrany aplikací Intune.

Například nastavení zásad **vyžadovat kód PIN aplikace** se snadno otestuje. Pokud se nastavení zásad rovná **požadavku**, uživateli by se měla zobrazit výzva k nastavení nebo zadání kódu PIN, než bude moci získat přístup k firemním datům.

Nejdřív [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro iOS. Další informace o tom, jak testovat zásady ochrany aplikací, najdete v tématu [ověření zásad ochrany aplikací](app-protection-policies-validate.md).


## <a name="see-also"></a>Viz také:
[Co jsou zásady ochrany aplikací Intune](app-protection-policy.md)
