---
title: Použijte základní nastavení zabezpečení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidat nebo nakonfigurovat nastavení doporučené skupiny zabezpečení k ochraně uživatelů a dat na zařízeních pomocí Microsoft Intune pro správu mobilních zařízení. Povolit nástroj bitlocker, konfigurace rozšířené ochrany před internetovými útoky programu Windows Defender, řídit aplikaci Internet Explorer, použijte SmartScreen, nastavení místní zásady zabezpečení, vyžadovat heslo, blokovat soubory stažené z Internetu a další.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b2a5e2bbd6d06cc4ec0cf71ee815229b01040a8
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394819"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Vytvoření standardních hodnot zabezpečení Windows 10 v Intune

Základní nastavení zabezpečení je funkce ve verzi preview, která je k dispozici pro zařízení s Windows 10 a novější. Tato funkce zahrnuje mnoho nastavení podporovaných službou Intune, můžete použít k zabezpečení a ochrany uživatelů a zařízení. Tato nastavení také automaticky nastaví na hodnoty doporučení zabezpečení týmy. Například Směrný plán automaticky povoluje nástroj BitLocker, automaticky vyžaduje heslo k odemknutí zařízení, automaticky zakáže základní ověřování a další.

Tato funkce platí pro:

- Windows 10 verze 1809 a novější

> [!NOTE]
> Směrné plány zabezpečení je ve verzi preview a nepodporuje Microsoft doporučujeme použití profilů v produkčním prostředí, jako směrných plánů může změnit v průběhu verze preview. Pokud jsou obecně dostupné základní nastavení zabezpečení, nebude stávající profily převést na nejnovější podporované profily.

Cílem pomocí standardních hodnot zabezpečení je poskytnout začátku do konce zabezpečené pracovní postupy při práci s Microsoft 365. Mezi výhody patří:

- Směrný plán zabezpečení obsahuje osvědčené postupy a doporučení týkající se nastavení, které mají vliv na zabezpečení. Intune spolupracuje s týmem stejné zabezpečení Windows, který vytváří základní nastavení zabezpečení zásad skupiny. Tato doporučení jsou založená na pokyny a rozsáhlých zkušeností.
- Pokud jste úplně nová do Intune a nejste si jisti, kde začít, směrné plány zabezpečení vám nabídne výhodu. Můžete rychle vytvořit a nasadit profil zabezpečení vědomím, že vám pomáhají chránit prostředky a data vaší organizace.
- Pokud aktuálně používáte zásady skupiny, migrace do Intune pro správu je mnohem snazší díky tyto standardní hodnoty. Tyto standardní hodnoty jsou nativně integrované do Intune a zahrnují moderní správu prostředí.

Základní nastavení zabezpečení v Intune vytvořit profil"configuration". Tento profil obsahuje všechna nastavení ve směrném plánu. Použití nebo přiřadit tento profil pro uživatele, skupiny a zařízení.

Po přiřazení profilu, můžete sledovat profil a monitorování standardních hodnot. Můžete například zobrazit zařízení, která odpovídají směrný plán nebo směrného plánu se neshodují.

V tomto článku se dozvíte, jak používat směrné plány zabezpečení k vytvoření profilu, profil přiřadit a monitorovat profil.

[Základní nastavení zabezpečení Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) je skvělý prostředek pro další informace o této funkci. [Správa mobilních zařízení](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) je skvělým zdrojem o MDM a co můžete dělat na zařízeních s Windows.

## <a name="prerequisites"></a>Požadavky
Ke správě směrných plánů v Intune, musí mít váš účet [správce zásad a profilů](role-based-access-control.md#built-in-roles) předdefinovaná role.


## <a name="co-managed-devices"></a>Spoluspravovaná zařízení

Základní nastavení zabezpečení na zařízeních spravovaných Intune se podobají spoluspravovaná zařízení s Configuration Managerem. Spoluspravovaná zařízení pomocí System Center Configuration Manager a Microsoft Intune můžete spravovat zařízení s Windows 10 současně. Umožňuje připojení nástroje Configuration Manager stávajícího prostředí k výhodám Intune cloudu. [Přehled spolusprávy](https://docs.microsoft.com/sccm/comanage/overview) je skvělý prostředek, pokud používáte nástroj Configuration Manager a také vhodné výhod cloudu.

Při použití spoluspravovaná zařízení, je nutné přepnout **konfigurace zařízení** pracovního vytížení (nastavení) do Intune. [Úlohy konfigurace zařízení](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) poskytuje další informace.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com/)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **směrné plány zabezpečení (preview)**. Seznam dostupných standardních hodnot je k dispozici. Při přidání více směrných plánů, zobrazí se tady:

    ![Podívejte se do seznamu standardních hodnot zabezpečení aktuálně k dispozici v Intune](./media/security-baselines/available-baselines.png)

3. Vyberte směrný plán by chtěl používat > **vytvořit profil**.
4. V **Základy**, zadejte následující vlastnosti:

    - **Název**: Zadejte název pro svůj profil standardních hodnot zabezpečení. Zadejte například `pilot Windows 10 MDM baseline - Oct 2018`.
    - **Popis**: Zadejte nějaký text, který popisuje, co dělá tyto standardní hodnoty. Popis je můžete zadat libovolný text, který chcete. Je volitelný, ale jednoznačně doporučujeme.

5. Rozbalte **nastavení**. V seznamu uvidíte všechna nastavení v těchto standardních hodnot zabezpečení a co je automaticky nastavení. Nastavení a jejich hodnoty se doporučuje a může být změněno vámi.

    ![Rozbalte nastavení, pokud chcete zobrazit všechna nastavení v těchto standardních hodnot zabezpečení v Intune](./media/security-baselines/sample-list-of-settings.png)

    Rozbalte některá nastavení ke kontrole jejich hodnot. Rozbalte například položku **programu Windows Defender**. Všimněte si, že některé z nastavení, a co je nastavena:

    ![Jaké některé z programu Windows Defender automaticky nastavení v Intune](./media/security-baselines/expand-windows-defender.png)

6. **Vytvoření** profilu. 
7. Vyberte **profily**. Váš profil je vytvořen a uvedené v seznamu. Ale to není teď zrovna nic nedělá ještě. Dále přiřaďte profil.

## <a name="assign-the-profile"></a>Přiřadit profil

Po vytvoření profilu je připraven k přiřazení na uživatele, zařízení a skupiny. Po přiřazení, profil a nastavení se použijí na uživatele, zařízení a skupiny, kterou zvolíte.

1. V Intune, vyberte **směrné plány zabezpečení** > vyberte směrný plán > **profily**.
2. Vyberte požadovaný profil > **přiřazení**.

    ![Zvolte profil standardních hodnot zabezpečení v Intune a klikněte na přiřazení nasazení profilu](./media/security-baselines/assignments.png)

3. V **zahrnout** kartu, přidat skupiny uživatelů nebo zařízení, které chcete tuto zásadu použít.

    > [!TIP]
    > Všimněte si, že je také možné **vyloučit** skupiny. Pokud pomocí zásad zasílejte **všichni uživatelé**, zvažte možnost vyloučit skupiny správců. V případě, že se stane něco, vám a vašim správcům nechcete uzamčeni.

4. **Uložte** provedené změny.

Po uložení, profil, který se vloží do zařízení, při vracení se pomocí Intune. Ano k tomu může dojít okamžitě.

## <a name="available-security-baselines"></a>Směrné plány zabezpečení k dispozici  

Následující standardní hodnoty zabezpečení jsou páskových pro použití s Intune.
- **Ve verzi Preview: Směrný plán zabezpečení MDM**
  - Verze: [. Října 2018](security-baseline-settings-windows.md)

## <a name="q--a"></a>Dotazy a odpovědi

#### <a name="why-these-settings"></a>Proč tato nastavení?

Bezpečnostní tým Microsoftu se po několika letech zkušeností pracovat přímo s vývojáři Windows a bezpečnostní komunitě, chcete-li vytvořit těchto doporučení. Nastavení v těchto standardních hodnot, jsou považovány za relevantní možnosti konfigurace související se zabezpečením. Tým v každé nové sestavení Windows upraví jeho doporučení v závislosti na nově vydané funkce.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Je nějaký rozdíl v doporučení pro směrné plány zabezpečení Windows pro vs zásad skupiny. Intune?

Stejné bezpečnostní tým Microsoftu zvolili a uspořádané nastavení pro každé standardní hodnoty. Intune obsahuje všechny relevantní nastavení v Intune standardních hodnot zabezpečení. Existují některá nastavení ve standardních hodnotách zásad skupiny, které jsou specifické pro řadič domény v místním prostředí. Tato nastavení jsou vyloučeny z doporučení v Intune. Všechna nastavení jsou stejné.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Jsou v Intune směrné plány zabezpečení CIS nebo institutu NSIT kompatibilní?

Přísně vzato není. Bezpečnostní tým Microsoftu consults organizacím, jako je například položek konfigurace, chcete-li zkompilovat svá doporučení. Ale není k dispozici mapování 1: 1 mezi "CIS CLS" a směrné plány společnosti Microsoft.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Jaké certifikace má směrné plány zabezpečení od Microsoftu? 

- Microsoft nadále publikovat základní nastavení zabezpečení pro zásady skupiny (GPO) a [Toolkit dodržování předpisů zabezpečení](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), protože má mnoho let. Řada organizací používá tyto standardní hodnoty. Doporučení v těchto standardních hodnot způsobují engagement bezpečnostní tým Microsoftu s podnikovými zákazníky a externími entitami, včetně ministerstva obrany (DoD) Národního institutu standardů a technologie (NIST) a více. Naše doporučení a směrných plánů sdílíme s těmito organizacemi. Tyto organizace také mít své vlastní doporučení, která úzce zrcadlí doporučení společnosti Microsoft. Správa mobilních zařízení (MDM) se stále rozrůstá do cloudu, společnost Microsoft vytvořila ekvivalentní MDM doporučení tyto standardní hodnoty zásad skupiny. Tato další standardní hodnoty jsou integrované v Microsoft Intune a zahrnují sestavy dodržování předpisů na uživatele, skupiny nebo zařízení, která postupujte (nebo neodpovídají) směrného plánu.

- Mnoho zákazníků používáte Intune základní doporučení jako výchozí bod a potom přizpůsobte tak, aby vyhovovala IT a požadavky na zabezpečení. Společnosti Microsoft Windows 10 RS5 **směrný plán zabezpečení MDM** je první základ k uvolnění. Tyto standardní hodnoty je vytvořena jako obecná infrastrukturu, která umožňuje zákazníkům nakonec importovat další základní nastavení zabezpečení na základě CIS, NIST a dalších standardů. V současné době je dostupná pro Windows a nakonec bude obsahovat zařízení s iOS a Android.

- Migrace z místní zásady skupiny služby Active Directory na čistě cloudové řešení pomocí Azure Active Directory (AD) pomocí Microsoft Intune se na cestu. Abychom pomohli, jsou doprovodné publikování objekty zásad skupiny pro hybridní AD a Azure zařízení připojených k doméně AD. Tato zařízení můžete získat nastavení MDM z cloudu (Intune) a nastavení zásad skupiny z řadičů domény s místními podle potřeby.

## <a name="next-steps"></a>Další postup
- Zobrazení [nastavení standardních hodnot zabezpečení Windows](security-baseline-settings-windows.md) podporovaných službou Intune.  
- Zkontrolujte stav a monitorování [směrného plánu a profil](security-baselines-monitor.md).
