---
title: Známé problémy v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si o známých problémech v Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 421eea460ee7c00b79a63a014291a8abb88ddaea
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347793"
---
# <a name="known-issues-in-microsoft-intune"></a>Známé problémy v Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V tomto článku se dozvíte více o známých problémech v Microsoft Intune.

Pokud chcete nahlásit chybu, která tu není uvedená, [otevřete žádost o podporu](get-support.md).

Pokud chcete zažádat o novou funkci pro Intune, můžete nám zaslat zprávu prostřednictvím webu [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migrace

### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal"></a>Export zásad dodržování předpisů z portálu Azure Classic pro jejich opětovné vytvoření na portálu Intune Azure

Zásady dodržování předpisů vytvořené na portálu Azure Classic se přestanou používat. Existující zásady si můžete prohlédnout a odstranit je, nelze je ale aktualizovat. Pokud potřebujete jakékoli zásady dodržování předpisů z aktuálního portálu Intune Azure migrovat, můžete je vyexportovat do souboru hodnot oddělených čárkami (.csv). Podrobnosti ze souboru potom můžete využít k opětovnému vytvoření těchto zásad v Intune na portálu Azure Portal.

> [!IMPORTANT]
> Po vyřazení portálu Azure Classic už k zásadám nebudete mít přístup, ani si je nebudete moci prohlížet. Proto zásady nezapomeňte exportovat a znovu vytvořit na webu Azure Portal dříve, než bude provoz portálu Azure Classic ukončen.

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Funkce starší verze klienta Intune v osobním počítači jsou dostupné jenom v konzole Silverlight

Funkce správy Windows 10 v Intune na portálu Azure Portal je k dispozici prostřednictvím registrace Windows MDM. Další informace najdete v tématu [Konzola Intune v Azure a starší verze klienta Intune v osobním počítači](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Skupiny vytvořené pomocí Intune během migrace můžou ovlivnit funkčnost jiných produktů Microsoftu

Při migraci z Intune na Azure Portal se může zobrazit nová skupina s názvem **Všichni uživatelé – b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Tato skupina obsahuje všechny uživatele ve vašem Azure Active Directory, ne jenom uživatele s licencí Intune. Toto použití může způsobit problémy s jinými produkty Microsoftu, pokud očekáváte, že někteří existující nebo noví uživatelé nebudou členem žádné skupiny.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Okna stavu pro migrované zásady nefungují

Nejde zobrazit informace o stavu pro zásady, které se migrovaly z klasického portálu na portál Azure Portal. Můžete ale dál zobrazovat sestavy pro tyto zásady na portálu Classic. Pokud chcete zobrazit informace o stavu migrovaných konfiguračních zásad, na portálu Azure Portal je znovu vytvořte.

## <a name="apps"></a>Aplikace


### <a name="multiple-app-install-prompts-for-certain-vpp-apps"></a>Zobrazování několika výzev k instalaci aplikací u určitých aplikací VPP
U některých aplikací VPP, které jsou už nainstalované na zařízeních koncových uživatelů, se můžete setkat s několika výzvami k instalaci aplikací. K tomuto problému dochází, pokud máte možnost **Automatické aktualizace aplikací** nastavenou na **Zapnuto** u tokenu VPP, který jste nahráli na portál Intune Azure Portal.    

Tento problém vyřešíte tak, že u tokenu VPP zakážete **Automatické aktualizace aplikací**. Uděláte to tak, že na portálu Azure Portal otevřete Microsoft Intune. V Intune vyberete **Klientské aplikace** > **Tokeny VPP pro iOS**. Dále vyberete token VPP, který nasadil ovlivněnou aplikaci, a vyberete **Upravit** > **Automatické aktualizace aplikací** > **Vypnuto** > **Uložit**. Můžete také ukončit nasazení ovlivněné aplikace jako aplikace VPP, čímž zastavíte zobrazování výzev.    

Toto je známý problém v aktuální verzi. Připravujeme opravu, která tento problém vyřeší. Po implementaci této opravy se už uživatelům nebude zobrazovat více výzev k instalaci aplikací.

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Hromadně zakoupené aplikace pro iOS jsou k dispozici pouze ve výchozím jazyce tenanta Intune
Hromadně zakoupené aplikaci pro iOS se zobrazují a jde je přiřadit pouze ke stejnému kódu země, jaký má účet Intune. Intune synchronizuje jenom aplikace ze stejného národního prostředí iTunes, jako je kód země účtu tenanta Intune. Pokud třeba koupíte aplikaci dostupnou jenom pro USA, ale váš účet Intune je český, Intune tuto aplikaci nezobrazí.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Nahrálo se více kopií jednoho hromadně zakoupeného programu pro iOS
Neklikejte u jednoho tokenu VPP na tlačítko **Nahrát** vícekrát. Pokud to uděláte, nahrají se duplicitní tokeny VPP a aplikace se u stejného tokenu VPP budou synchronizovat vícekrát.

### <a name="some-managed-browser-traffic-not-routed-through-azure-app-proxy----2463492---"></a>Část provozu Managed Browseru se nesměruje prostřednictvím Proxy aplikací Azure <!-- 2463492 -->
Existuje známý problém s integrací Managed Browseru a Proxy aplikací, kdy se určitý terciární provoz (například volání jazyka JavaScript nebo AJAX) nesměruje prostřednictvím Proxy aplikací Azure. Toto je známý problém v aktuální verzi.  

<!-- ## Groups -->

## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Nejde uložit zásadu Windows Information Protection pro některá zařízení

Pro zařízení, která nejsou zaregistrovaná v Intune, můžete do pole **Podniková identita** v nastavení pro zásadu Windows Information Protection zadat jenom primární doménu.
Pokud přidáte další domény (pomocí možnosti **Upřesnit nastavení** > **Hranice sítě** > **Přidat chráněnou doménu**), zásadu nejde uložit. Zobrazená chybová zpráva se brzy změní, aby byla přesnější.

### <a name="cisco-anyconnect-and-cisco-legacy-anyconnect-vpn-client-support---ios"></a>Podpora klientů VPN Cisco AnyConnect a Cisco Legacy AnyConnect – iOS

Na zařízeních s iOSem nefunguje integrace NAC s novým klientem Cisco AnyConnect. Pracujeme se společností Cisco, abychom zajistili integraci NAC.

[Vytvoření profilů sítě VPN v Intune](vpn-settings-ios.md) poskytuje další podrobnosti týkající se klientů Cisco AnyConnect a Cisco Legacy AnyConnect.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Použití číselného typu hesla pro zařízení s macOS Sierra

Když v současnosti v profilu omezení zařízení pro zařízení s macOS Sierra vyberete jako **Požadovaný typ hesla** možnost **Číselné**, vynutí se **Alfanumerické**. Pokud s těmito zařízeními chcete použít číselné heslo, toho nastavení nekonfigurujte.
Tento problém se možná vyřeší v budoucí verzi macOS.

Další informace o těchto nastaveních najdete v tématu [Nastavení omezení pro zařízení s macOS v Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Dodržování předpisů

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Zásady dodržování předpisů z Intune se v nové konzole nezobrazí

Zásady dodržování předpisů, které jste vytvořili v klasickém portálu, se migrují, ale na portálu Azure Portal se nezobrazí kvůli změnám v návrhu na portálu Azure Portal. Zásady dodržování předpisů, které jste vytvořili na klasickém portálu Intune, se stále uplatňují, ale musíte je prohlížet a upravovat na klasickém portálu.

Nové zásady dodržování předpisů, které vytvoříte na Azure Portalu, navíc nejsou na klasickém portálu vidět.

Další informace najdete v článku [Co je dodržování předpisů zařízením](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Ochrana dat

### <a name="ios-app-protection-policies"></a>Zásady ochrany aplikací pro iOS

Můžete definovat [zásady ochrany aplikací pro iOS](app-protection-policy-settings-ios.md), které jsou k dispozici pro uživatele na zařízeních spravovaných prostřednictvím správy mobilních zařízení (MAM) bez registrace. Kvůli dočasné chybě můžete tyto zásady definovat pouze pro verze iOS s jedním desetinným místem (ne více). Namísto nastavení minimální verze iOS 10.3.1 nastavíte iOS 10.3. Tento problém se vyřeší v chystané aktualizaci iOS SDK.


## <a name="administration-and-accounts"></a>Správa a účty

Globální správci (také označovaní jako správci tenanta) můžou dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí službu používat, třeba zaregistrovat si vlastní nebo firemní zařízení nebo používat Portál společnosti Intune, potřebují licenci Intune nebo EMS.

<!-- ## Additional items -->
