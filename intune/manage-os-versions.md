---
title: Správa verzí operačního systému pomocí Microsoft Intune
description: Zjistěte, jak pomocí Microsoft Intune spravovat verze operačního systému napříč platformami.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 361ef17b-1ee0-4879-b7b1-d678b0787f5a
ms.openlocfilehash: 1e5b902053290c314aa53b8f17f11ff92247d37e
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
ms.locfileid: "29720302"
---
# <a name="manage-operating-system-versions-with-intune"></a>Správa verzí operačního systému pomocí Intune
Na moderních mobilních a počítačových platformách jsou velké aktualizace, opravy a nové verze vydávány rychlým tempem. Ve Windows máte nad úplnou správou aktualizací a oprav kontrolu, ale jiné platformy jako iOS a Android vyžadují, aby se procesu účastnili koncoví uživatelé.  Microsoft Intune má možnosti, které vám pomůžou se strukturováním správy verzí operačního systému napříč různými platformami.

Intune vám může pomoct vyřešit tyto běžné scénáře: 
- Určit, jaké verze operačního systému jsou na zařízeních koncových uživatelů
- Řídit přístup k datům organizace na zařízeních při ověřování nové vydané verze operačního systému
- Doporučit koncovým uživatelům nebo po nich vyžadovat, aby upgradovali na nejnovější verzi operačního systému, kterou schválila vaše organizace
- Spravovat uvedení nové verze operačního systému v celé organizaci
  
## <a name="operating-system-version-control-using-intune-mobile-device-management-mdm-enrollment-restrictions"></a>Správa verzí operačního systému pomocí omezení registrace ve správě mobilních zařízení (MDM) Intune
Omezení registrace v MDM Intune umožňují definovat požadavky na klientské zařízení, než registraci zařízení povolíte. Cílem je vyžadovat, aby vaši koncoví uživatelé před získáním přístupu k prostředkům organizace registrovali jenom zařízení splňující požadavky. Požadavky na zařízení zahrnují minimální i maximální povolenou verzi operačního systému pro podporované platformy.
 
![Okno konfigurace omezení platformy](./media/os-version-platform-configurations.png) 
 
### <a name="in-practice"></a>V praxi
Organizace využívají omezení typu zařízení k řízení přístupu k prostředkům organizace pomocí následujících nastavení: 
1. Pomocí minimální verze operačního systému dosáhnete toho, aby koncoví uživatelé ve vaší organizaci stále používali aktuální a podporované platformy. 
2. Ponechte maximální verzi operačního systému nezadanou (bez omezení) nebo ji nastavte na poslední ověřenou verzi ve vaší organizaci, abyste získali čas na interní testování nových verzí operačního systému.

Podrobnosti najdete v sekci [Nastavení omezení typu zařízení](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions).
 
## <a name="operating-system-version-reporting-and-compliance-with-intune-mdm-device-compliance-policies"></a>Vytváření sestav o verzích operačního systému a soulad se zásadami dodržování předpisů zařízením v MDM Intune
Zásady dodržování předpisů zařízením v MDM Intune poskytují tyto nástroje: 
- Určení pravidel dodržování předpisů
- Zobrazení stavu dodržování předpisů pomocí sestav
- Reakce na nedodržování předpisů prostřednictvím umístění zařízení do karantény a podmíněného přístupu

Stejně jako omezení registrace i zásady dodržování předpisů zařízením zahrnují minimální i maximální verzi operačního systému. Zásady používají také časový plán dodržování předpisů, který uživatelům poskytne období odkladu, během kterého můžou dodržování předpisů napravit. Zásady dodržování předpisů zařízením udržují zaregistrovaná zařízení koncových uživatelů v souladu se zásadami organizace.

![Dodržování předpisů zařízením – akce pro zařízení nesplňující požadavky](./media/os-version-actions-noncompliance.png) 

### <a name="in-practice"></a>V praxi
Organizace využívají zásady dodržování předpisů zařízením pro stejné scénáře jako omezení registrace. Díky těmto zásadám používají uživatelé ve vaší organizaci aktuální ověřené verze operačního systému. Když zařízení koncových uživatelů přestanou předpisy dodržovat, může být přístup k prostředkům organizace zablokován prostřednictvím podmíněného přístupu, dokud nebudou koncoví uživatelé používat operační systém z podporovaného rozsahu pro vaši organizaci. Koncoví uživatelé jsou informováni, že jejich zařízení nedodržují předpisy, a dostanou k dispozici kroky, jak přístup znovu získat.   

Podrobnosti najdete v tématu [Začínáme se zásadami dodržování předpisů zařízeními v Intune](https://docs.microsoft.com/intune/device-compliance-get-started).
 
## <a name="operating-system-version-controls-using-intune-app-protection-policies"></a>Správa verzí operačního systému pomocí zásad ochrany aplikací Intune    
Nastavení přístupu v zásadách ochrany aplikací Intune a správě mobilních aplikací (MAM) umožňují zadat minimální verzi operačního systému ve vrstvě aplikací. Můžete tak koncové uživatele informovat a vybídnout nebo po nich vyžadovat, aby svůj operační systém aktualizovali na zadanou minimální verzi.
 
Máte dvě různé možnosti: 

|Upozornění  |Blokování  |
|---------|---------|
|Upozornění informuje koncového uživatele, pokud spustí aplikaci se zásadami ochrany aplikací nebo nastavením přístupu MAM na zařízení s nižší než zadanou verzí operačního systému, že by měl upgradovat. Přístup k datům aplikace a organizace je povolený.|Blokování informuje koncového uživatele, když spustí aplikaci se zásadami ochrany aplikací nebo nastavením přístupu MAM na zařízení s nižší než zadanou verzí operačního systému, že musí upgradovat. Přístup k datům aplikace a organizace není povolený.|
|![Dialogové okno Androidu s upozorněním na aktualizaci](./media/os-version-update-warning.png)    |![Dialogové okno o blokovaném přístupu k aplikaci](./media/os-version-access-blocked.png)          |

 
### <a name="in-practice"></a>V praxi
Organizace dnes nastavení zásad ochrany aplikací využívají při spuštění nebo obnovení aplikací jako způsob, jak uživatele informovat o potřebě udržovat aplikace aktuální. Příkladem konfigurace je, že koncoví uživatelé s verzí o jednu nižší než aktuální jsou upozorněni a uživatelé s verzí o dvě nižší než aktuální jsou zablokováni.
 
Podrobnosti najdete v tématu [Vytvoření a přiřazení zásad ochrany aplikací](https://docs.microsoft.com/intune/app-protection-policies).

## <a name="managing-a-new-operating-system-version-rollout"></a>Správa zavedení nové verze operačního systému
Možností Intune popsaných v tomto článku můžete využít k přechodu organizace na novou verzi operačního systému v rámci časového plánu, který určíte. Následující kroky popisují ukázkový model nasazení pro přechod vašich uživatelů z operačního systému verze 1 na operační systém verze 2 během sedmi dní.
- **Krok 1**: Pomocí omezení registrace vyžadujte operační systém verze 2 jako minimální verzi k registraci zařízení. To zajistí, aby nová zařízení koncových uživatelů v době registrace dodržovala předpisy.
- **Krok 2a**: Pomocí zásad ochrany aplikací Intune uživatele při spuštění nebo obnovení aplikace upozorněte, že je vyžadován operační systém verze 2.
- **Krok 2b**: Pomocí zásad dodržování předpisů zařízením vyžadujte operační systém verze 2 jako minimální verzi k tomu, aby zařízení dodržovalo předpisy. Pomocí **akcí** při nedodržení předpisů umožněte sedmidenní období odkladu a zašlete koncovým uživatelům oznamovací e-mail s časovým plánem a požadavky.
  -  Tyto zásady budou koncové uživatele informovat, že stávající zařízení se musí aktualizovat, a to prostřednictvím e-mailu, Portálu společnosti Intune a při spuštění aplikace v případě aplikací, pro které jsou aktivní zásady ochrany aplikací.
  - Můžete spustit sestavu dodržování předpisů, abyste identifikovali uživatele, kteří předpisy nedodržují. 
- **Krok 3a**: Pomocí zásad ochrany aplikací Intune uživatele při spuštění nebo obnovení aplikace zablokujte, pokud zařízení nepoužívá operační systém verze 2.
- **Krok 3b**: Pomocí zásad dodržování předpisů zařízením vyžadujte operační systém verze 2 jako minimální verzi k tomu, aby zařízení dodržovalo předpisy.
  - Tyto zásady vyžadují, aby byla zařízení aktualizována, pokud mají mít dál přístup k datům organizace. Chráněné služby jsou zablokované při použití s podmíněným přístupem zařízení. Aplikace, pro které jsou aktivní zásady ochrany aplikací, jsou zablokované při spuštění nebo přístupu k datům organizace.

## <a name="next-steps"></a>Další kroky
Ke správě verzí operačního systému ve vaší organizaci můžete využít tyto prostředky: 

- [Nastavení omezení typů zařízení](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions)
- [Začínáme s dodržováním předpisů zařízeními](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Vytvoření a přiřazení zásad ochrany aplikací](https://docs.microsoft.com/intune/app-protection-policies)
