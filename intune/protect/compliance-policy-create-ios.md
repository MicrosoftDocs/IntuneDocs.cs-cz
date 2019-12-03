---
title: nastavení dodržování předpisů pro zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení s iOS v Microsoft Intune. Vyžadovat e-mail, podívejte se na zařízení s jailbreakem nebo rootem, nastavte povolený minimální a maximální operační systém, nastavte jakákoli omezení hesla, včetně délky hesla a nečinnosti zařízení, omezit aplikace a další.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3b83b764af415349b287df2a09f9b4c355734c28
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810232"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>nastavení iOS k označení zařízení jako kompatibilních nebo nekompatibilních s Intune

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních s iOS v Intune. Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení pro vyžadování e-mailu, označení rootem (jailbreak) zařízení jako nevyhovující předpisům, nastavení povolené úrovně hrozby, nastavení hesel pro vypršení platnosti a další.

Tato funkce platí pro:

- iOS
- iPadOS

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). V případě **platformy**vyberte **iOS/iPadOS**.

## <a name="email"></a>E-mailu

- **Vyžadovat, aby mobilní zařízení měla spravovaný e-mailový profil**:  
  - **Nenakonfigurováno** (*výchozí*) – Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.
  - **Vyžadovat** – zařízení, která nemají e-mailový profil spravovaná přes Intune, se považují za nevyhovující předpisům. Zařízení nemůže mít spravovaný e-mailový profil, pokud není správně cíleno nebo pokud uživatel ručně nastavil e-mailový účet na zařízení.

  Zařízení je považováno za nedodržující předpisy v následujících situacích:  
  - E-mailový profil se přiřadí jiné skupině uživatelů, než je skupina uživatelů, na kterou cílí zásady dodržování předpisů.
  - Uživatel už na zařízení nastavil e-mailový účet, který se shoduje s e-mailovým profilem Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem nakonfigurovaný profil a Intune ho nemůže spravovat. Aby bylo možné nastavit dodržování předpisů, musí koncový uživatel odebrat existující nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.  

Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k e-mailu organizace pomocí e-mailových profilů s Intune](../configuration/email-settings-configure.md)

## <a name="device-health"></a>Stav zařízení

- **Zařízení s jailbreakem**:  
  - **Nenakonfigurováno** (*výchozí*) – Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.
  - Zařízení s označením root (jailbreak) jako nevyhovující předpisům.  

- **Vyžadovat, aby zařízení bylo na úrovni hrozby pro zařízení nebo pod** ní *(iOS 8,0 a novější)* :  
  Toto nastavení použijte, pokud chcete vyhodnotit hodnocení rizik jako podmínku pro dodržování předpisů. Vyberte povolenou úroveň hrozby:  
  - **Nenakonfigurováno** (*výchozí*) – Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.
  - **Zabezpečené** – Tato možnost je nejbezpečnější a to znamená, že zařízení nemůže mít žádné hrozby. Pokud se zjistí, že zařízení má žádnou úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká** – zařízení se vyhodnotí jako vyhovující, pokud jsou přítomny jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední** – zařízení se vyhodnotí jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení bude mít hrozby vysoké úrovně, je zjištěno, že nedodržuje předpisy.
  - **Vysoká** – Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

## <a name="device-properties"></a>Vlastnosti zařízení

### <a name="operating-system-version"></a>Verze operačního systému  

- **Minimální požadovaný operační systém** *(iOS 8,0 a novější)* :  
  Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nevyhovující. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může upgradovat svoje zařízení. Pak mají přístup k prostředkům organizace.

- **Maximální povolená verze operačního systému** *(iOS 8,0 a novější)* :  
  Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které povoluje verzi operačního systému.

- **Minimální verze buildu operačního systému** *(iOS 8,0 a novější)* :  
  Když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat minimální povolené číslo sestavení v zařízení.

- **Maximální verze buildu operačního systému** *(iOS 8,0 a novější)* :  
  Když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat maximální povolené číslo sestavení v zařízení.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

> [!NOTE]
> Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k nastavení hesla. Uživatelům se výzva bude zobrazovat tak dlouho, dokud heslo nenastaví. Když je pro zařízení se systémem iOS nastavené heslo, automaticky se spustí proces šifrování. Zařízení zůstane zašifrované, dokud heslo nebude zakázané.

- **Vyžadovat heslo k odemknutí mobilních zařízení**:  
  - **Nenakonfigurováno** (*výchozí*) – Toto nastavení není vyhodnoceno pro dodržování předpisů nebo nedodržování předpisů.  
  - **Vyžadovat** – uživatelé musí zadat heslo, aby mohli získat přístup ke svému zařízení. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.

- **Jednoduchá hesla**:  
  - **Nenakonfigurováno** (*výchozí*) – uživatelé můžou vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.
  - **Blok** – uživatelé nemůžou vytvářet jednoduchá hesla, třeba **1234** nebo **1111**. 

- **Minimální délka hesla**:  
  Zadejte minimální počet číslic nebo znaků, které musí heslo obsahovat.  

- **Požadovaný typ hesla**:  
  Vyberte, jestli má heslo obsahovat jenom **číselné** znaky, nebo jestli má být kombinace čísel a dalších znaků (**alfanumerické**).

- **Počet nealfanumerických znaků v hesle**:  
  Zadejte minimální počet speciálních znaků, například `&`, `#`, `%`, `!`a tak dále, které musí být v hesle. 

  Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut po uzamčení obrazovky před vyžadováním hesla** *(iOS 8,0 a novější)* :  
  Zadejte, jak brzy bude obrazovka uzamčena, než uživatel musí zadat heslo pro přístup k zařízení. Mezi možnosti patří výchozí hodnota *není nakonfigurované*, *okamžitě*a *1 minuta* až *4 hodiny*.

- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**:  
  Zadejte dobu nečinnosti, než zařízení zamkne obrazovku. Mezi možnosti patří výchozí nastavení *není nakonfigurováno*, *okamžitě*a od *1 minuty* do *15 minut*.

- **Vypršení platnosti hesla (dny)** :  
  Vyberte počet dní, po jejichž uplynutí vyprší platnost hesla, a musí vytvořit nové. 

- **Počet předchozích hesel pro zabránění opakovanému použití** *(iOS 8,0 a novější)* :   
  Zadejte počet dříve použitých hesel, která se nedají použít.

### <a name="device-security"></a>Zabezpečení zařízení

- **Aplikace s omezeným přístupem**:  
  Aplikace můžete omezit přidáním jejich ID sady prostředků do zásady. Pokud je aplikace v zařízení nainstalovaná, zařízení se označí jako nevyhovující.

  - **Název aplikace** – zadejte uživatelsky přívětivý název, který vám usnadní identifikaci ID sady prostředků.
  - **ID sady prostředků aplikace** – zadejte jedinečný identifikátor sady přiřazený poskytovatelem aplikace. ID sady najdete v tématu [Jak najít ID sady prostředků pro aplikaci pro iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (otevře se další web Microsoftu).  

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení MacOS](compliance-policy-create-mac-os.md) .