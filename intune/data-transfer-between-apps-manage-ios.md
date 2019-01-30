---
title: Správa přenosu dat mezi aplikacemi pro iOS | Microsoft Intune
description: Přečtěte si, jak používat zásady správy mobilních aplikací v Microsoft Intune ke správě přenosů dat mezi aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8e223301b15a408c5f5a444a1904fca9826929ac
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2019
ms.locfileid: "55229895"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune

K ochraně firemních dat, omezte přenosy souborů jenom na aplikace, které spravujete. Aplikace pro iOS můžete spravovat těmito způsoby:

-   Zabraňují úniku dat společnosti tím, že nakonfigurujete zásady ochrany aplikací pro aplikace, které označujeme jako **spravované podle zásad** aplikace. Přečtěte si téma s informacemi o [všech aplikacích spravovaných přes Intune, které je možné spravovat pomocí zásad ochrany aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

-   Nasazení a správě aplikací prostřednictvím **kanálu MDM.**, která vyžaduje zařízení k registraci v řešení správy mobilních zařízení (MDM). Je možné aplikace nasadíte **spravované podle zásad** aplikací nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. Nastavte *Správa Open in* omezení v nastavení konfigurace a potom ji nasadíte pomocí řešení pro správu.  Když uživatel nainstaluje nasazenou aplikaci, použijí se omezení, která jste nastavili.

##  <a name="use-app-protection-with-ios-apps"></a>Ochrana aplikací pomocí aplikace pro iOS
Použití zásad ochrany aplikací v IOS **Správa Open in** funkce k ochraně firemních dat těmito způsoby:

-   **Zařízení patřící zaměstnancům, nejsou spravována žádným řešením MDM:** Můžete nastavit ochranu aplikace nastavení zásad **povolit aplikaci přenos dat jenom aplikace spravované podle zásad**. *Open In* chování v aplikaci spravované zásadami prezentuje jako možnosti pro sdílení jenom další aplikace spravované zásadami. Pokud se uživatel pokusí odeslat soubor chráněný zásadami jako přílohu z Onedrivu v nativním e-mailové aplikace, je tento soubor nejde přečíst.

-   **Zařízení spravovaná pomocí Intune:** Pro zařízení zaregistrovaná v Intune přenos dat mezi aplikacemi se zásadami ochrany aplikací a další spravované aplikace pro iOS nasazenými prostřednictvím Intune automaticky povolené. Chcete-li určit, jak chcete povolit přenos dat do jiných aplikací, povolit **povolit aplikaci posílat data do jiných aplikací** a pak vyberte požadovanou úroveň sdílení. Chcete-li určit, jak chcete povolit aplikaci přijímat data z jiných aplikací, povolit **povolit aplikaci přijímat data z jiných aplikací** a pak vyberte požadovanou úroveň pro příjem dat. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune. Další informace o přijímání a sdílení dat aplikací najdete v tématu [Nastavení přemístění dat](app-protection-policy-settings-ios.md#data-protection).   

-   **Zařízení spravovaná řešením MDM třetí strany:** Můžete omezit přenosy dat jenom do spravovaných aplikací s použitím iOS **Správa Open in** funkce.
Pokud chcete mít jistotu, že aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k pomocí zásad ochrany aplikací Intune, konfigurace nastavení hlavního názvu uživatele (UPN), jak je popsáno v následující části [konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Při nasazení aplikace pomocí nastavení hlavního názvu uživatele (UPN), použít zásady ochrany aplikací pro aplikaci, jakmile se uživatel přihlásí pomocí svého pracovního účtu.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Konfigurace nastavení hlavního názvu uživatele (UPN) pro Microsoft Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce
Konfigurace nastavení hlavního názvu uživatele (UPN) je **povinná** pro zařízení spravovaná pomocí Intune nebo řešení EMM (Enterprise Mobility Management) jiného výrobce. Konfigurace hlavního názvu uživatele funguje se zásadami ochrany aplikací, které můžete nasadit z Intune. Následující postup představuje obecné kroky pro konfiguraci nastavení (UPN) a výsledného prostředí uživatele:

1.  Na portálu [Azure Portal](https://portal.azure.com) [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace iOS, které by tyto zásady měly používat.

2.  Nasaďte aplikace a e-mailový profil, který chcete spravovat prostřednictvím Intune nebo řešení MDM jiného výrobce pomocí následujících obecných kroků. Toto prostředí je také popsaná v *Příklad 1*.

3.  Nasazení aplikace s následujícím nastavením konfigurace aplikací:

      **klíč** = IntuneMAMUPN, **hodnota** = <username@company.com>

      Příklad: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Nasaďte **zásadu správy Open in** prostřednictvím Intune nebo jiného poskytovatele řešení MDM do zaregistrovaných zařízení.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Příklad 1: Prostředí pro správu v Intune nebo konzole řešení MDM třetí strany

1. Přejděte do konzoly pro správu Intune nebo poskytovatele řešení MDM jiného výrobce. Přejděte do části konzoly, ve které nasadíte nastavení konfigurace aplikace do zaregistrovaných zařízení s iOSem.

2. V části Konfigurace aplikace zadejte tato nastavení:

   **klíč** = IntuneMAMUPN, **hodnota** = <username@company.com>

   Skutečná syntaxe dvojice klíč/hodnota se může lišit podle toho, jakého máte jiného poskytovatele řešení MDM. V následující tabulce jsou uvedeny příklady jiných poskytovatelů MDM a přesných hodnot, které je potřeba zadat dvojice klíč/hodnota.

   |Jiný poskytovatel řešení MDM| Konfigurační klíč | Typ hodnoty | Konfigurační hodnota|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Řetězec | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Řetězec | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Řetězec | ${userUPN} **nebo** ${userEmailAddress} |
   |Správce mobilních zařízení ManageEngine | IntuneMAMUPN | Řetězec | %upn% |


### <a name="example-2-end-user-experience"></a>Příklad 2: Činnost koncového uživatele

1.  Uživatel nainstaluje na zařízení aplikaci Microsoft Word.

2.  Uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup k e-mailu.

3.  Uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4.  Při spuštění aplikace Word, bude uživatel vyzván k přihlášení pomocí svého pracovního účtu. Účet, který uživatel zadá musí odpovídat účtu, který jste zadali v nastavení konfigurace aplikace pro aplikaci Microsoft Word.

    > [!NOTE]
    > Uživatele můžete přidat a používat jejich osobní účty s aplikací Word. Zásady ochrany aplikací nemůžete použít, pokud uživatel použije aplikaci Word mimo pracovní kontext. 

5.  Po přihlášení platí nastavení zásad ochrany aplikací pro aplikace Word.

6.  Přenos dat bude tentokrát úspěšný a dokument se v aplikaci označí firemní identitou.  Data zpracovávají v pracovním kontextu a nastavení zásad platí. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Ověření nastavení hlavního názvu uživatele (UPN) pro řešení MDM jiného výrobce

Po dokončení konfigurace nastavení hlavního názvu uživatele (UPN), ověření aplikace pro iOS umožňuje přijímat a dodržovat zásady ochrany aplikací Intune.

Například **požadování PINU v aplikaci** je snadné k otestování nastavení zásad. Při nastavení zásad rovná **Ano**, uživatel by měl zobrazit výzva k nastavení nebo zadání PIN kódu před přístupem k firemním datům.

Nejdřív pro aplikaci pro iOS [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md). Další informace o testování zásad ochrany aplikací najdete v tématu [ověření zásad ochrany aplikací](app-protection-policies-validate.md).


### <a name="see-also"></a>Viz také:
[Co jsou zásady ochrany aplikací Intune](app-protection-policy.md)