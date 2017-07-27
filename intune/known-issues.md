---
title: "Známé problémy v Microsoft Intune na Azure"
titleSuffix: Intune on Azure
description: "Informace o známých problémech v Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b08a097e785f85d8b9260cdaa60e720ed88cb4a1
ms.sourcegitcommit: 21a9db380956a50031dbea360b4c76664cbc2768
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2017
---
# <a name="known-issues-in-microsoft-intune"></a>Známé problémy v Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Toto téma vám pomůže dozvědět se více o známých problémech v Microsoft Intune.

Pokud chcete nahlásit chybu, která tu není uvedená, [otevřete žádost o podporu](get-support.md).

Pokud chcete zažádat o novou funkci pro Intune, zvažte zaslání zprávy na webu [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migrace

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Skupiny vytvořené pomocí Intune během migrace můžou ovlivnit funkčnost jiných produktů Microsoftu

Při migraci z klasického portálu Intune na Azure se může zobrazit nová skupina s názvem **Všichni uživatelé – b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Tato skupina obsahuje všechny uživatele ve vašem Azure Active Directory, ne jenom uživatele s licencí Intune. Toto použití může způsobit problémy s jinými produkty Microsoftu, pokud očekáváte, že někteří existující nebo noví uživatelé nebudou členem žádné skupiny.

### <a name="secondary-migration-required-for-select-capabilities"></a>Pro vybrané možnosti se vyžaduje sekundární migrace

Účty Intune vytvořené před lednem 2017 je nutné před použitím těchto schopností na portálu Azure Portal migrovat:

- Profily registrace podnikových zařízení
- Program Apple Device Enrollment Program
- Firemní předregistrovaná zařízení podle skupiny sériových čísel iOSu
- Správci registrace zařízení
- Apple Volume Purchase Program

Protože tyto schopnosti nejde spravovat z klasické konzoly Silverlight i konzoly Azure, migrace:
- Zakáže schopnosti v klasické konzole.
- Povolí schopnosti v konzole Azure.  

Pokud teď tyto schopnosti Intune spravujete na portálu Azure Portal, mějte na paměti tyto body:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Odebrání výchozích profilů registrace podnikových zařízení v programu Apple DEP
Azure Portal nepodporuje výchozí profil registrace podnikového zařízení pro zařízení programu Apple DEP (Device Enrollment Program). Tato funkce, která je dostupná v klasické konzole Silverlight Intune, se vyřazuje, aby nedocházelo k neúmyslnému přiřazení profilů. Když se na portálu Azure Portal synchronizují sériová čísla DEP, nepřiřadí se žádný profil registrace podnikového zařízení. Před použitím zařízení musí být registrační profil přiřazený.

#### <a name="apple-dep-token-restored-with-migration"></a>Obnovení tokenu Apple DEP při migraci

Pokud v klasickém (Silverlight) portálu Intune odstraníte token Apple Device Enrollment Programu a neodešlete nový token na portálu Azure Portal, původní token se při migraci na novém portálu Azure Portal obnoví. Pokud chcete tento token odebrat a zabránit registraci v programu DEP, odstraňte token z portálu Azure Portal.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Okna stavu pro migrované zásady nefungují

Nejde zobrazit informace o stavu pro zásady, které se migrovaly z klasického portálu na portál Azure Portal. Můžete ale dál zobrazovat sestavy pro tyto zásady na portálu Classic.
Pokud chcete zobrazit informace o stavu migrovaných konfiguračních zásad, na portálu Azure Portal je znovu vytvořte.

## <a name="apps"></a>Aplikace

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Hromadně zakoupené aplikace pro iOS jsou k dispozici pouze ve výchozím jazyce tenanta Intune
Hromadně zakoupené aplikaci pro iOS se zobrazují a jde je přiřadit pouze ke stejnému kódu země, jaký má účet Intune. Intune synchronizuje pouze aplikace ze stejného národního prostředí iTunes, jako je kód země účtu tenanta Intune. Pokud tedy například koupíte aplikaci, která je k dispozici pouze pro USA, ale váš účet Intune je německý, Intune tuto aplikaci nezobrazí.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Nahrálo se více kopií jednoho hromadně zakoupeného programu pro iOS
Neklikejte u jednoho tokenu VPP na tlačítko **Nahrát** vícekrát. Pokud to uděláte, nahrají se duplicitní tokeny VPP a aplikace se u stejného tokenu VPP budou synchronizovat vícekrát. 

<!-- ## Groups -->

## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Nejde uložit zásadu Windows Information Protection pro některá zařízení

Pro zařízení, která nejsou zaregistrovaná v Intune, můžete do pole **Podniková identita** v nastavení pro zásadu Windows Information Protection zadat jenom primární doménu.
Pokud přidáte další domény (pomocí možnosti **Upřesnit nastavení** > **Hranice sítě** > **Přidat chráněnou doménu**), zásadu nejde uložit. Zobrazená chybová zpráva se brzy změní, aby byla přesnější.

### <a name="cisco-anyconnect-vpn-client-support"></a>Podpora klientů VPN Cisco AnyConnect
 
Nejnovější vydaná verze klienta VPN Cisco AnyConnect (4.0.07072) v současnosti není kompatibilní s Intune. Budoucí aktualizace Intune umožní kompatibilitu s touto verzí klienta VPN. Do té doby doporučujeme klienta VPN Cisco AnyConnect neaktualizovat a dál používat stávající verzi.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Použití číselného typu hesla pro zařízení s macOS Sierra

Když v současnosti v profilu omezení zařízení pro zařízení s macOS Sierra vyberete jako **Požadovaný typ hesla** možnost **Číselné**, vynutí se **Alfanumerické**. Pokud s těmito zařízeními chcete použít číselné heslo, toho nastavení nekonfigurujte.
Tento problém se možná vyřeší v budoucí verzi macOS.

Další informace o těchto nastaveních najdete v tématu [Nastavení omezení pro zařízení s macOS v Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Dodržování předpisů

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Zásady dodržování předpisů z Intune se v nové konzole nezobrazí

Zásady dodržování předpisů, které jste vytvořili v klasickém portálu, se migrují, ale na portálu Azure Portal se nezobrazí kvůli změnám v návrhu na portálu Azure Portal. Zásady dodržování předpisů, které jste vytvořili v klasickém portálu Intune, se stále vynucují, ale musíte je prohlížet a upravovat na klasické portálu Intune.
A nové zásady dodržování předpisů, které vytvoříte na portálu Azure Portal, se nezobrazí v klasickém portálu Intune.

Další informace najdete v článku [Co je dodržování předpisů zařízením](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Ochrana dat

### <a name="ios-app-protection-policies"></a>Zásady ochrany aplikací pro iOS

Můžete definovat [zásady ochrany aplikací pro iOS](app-protection-policy-settings-ios.md), které jsou k dispozici pro uživatele na zařízeních spravovaných prostřednictvím správy MAM bez registrace. Kvůli dočasné chybě můžete tyto zásady definovat pouze pro verze iOS s jedním desetinným místem (ne více). Namísto nastavení minimální verze iOS 10.3.1 nastavíte iOS 10.3. Tento problém se vyřeší v chystané aktualizaci iOS SDK.


## <a name="administration-and-accounts"></a>Správa a účty

Globální správci (také označovaní jako správci tenanta) můžou dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí službu používat, třeba zaregistrovat si vlastní nebo firemní zařízení nebo používat Portál společnosti Intune, potřebují licenci Intune nebo EMS.

<!-- ## Additional items -->












 
