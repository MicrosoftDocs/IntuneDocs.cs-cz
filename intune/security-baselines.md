---
title: Použijte základní nastavení zabezpečení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidat nebo konfigurovat doporučené nastavení zabezpečení k ochraně uživatelů a dat na zařízeních pomocí Microsoft Intune pro správu mobilních zařízení. Povolit nástroj BitLocker, konfigurace rozšířené ochrany před internetovými útoky Defender Microsoft, řídit aplikaci Internet Explorer, použijte SmartScreen, nastavení místní zásady zabezpečení, vyžadovat heslo, blokovat soubory stažené z Internetu a další.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93e470175829008b72b5b8991188f3c92e38a567
ms.sourcegitcommit: 690e680e854b7d707421c5e06f134e493f4f4194
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2019
ms.locfileid: "67416848"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Konfigurace zařízení s Windows 10 v Intune pomocí standardních hodnot zabezpečení

Použijte základní nastavení zabezpečení v Intune při zabezpečení a ochrana vašich uživatelů a zařízení. Základní nastavení zabezpečení jsou předem nakonfigurované skupiny nastavení, které vám pomůžou se týká známá skupina nastavení a výchozí hodnoty, které se doporučují týmy relevantní zabezpečení Windows. Když v Intune vytvoříte profil standardních hodnot zabezpečení, kterou vytváříte *konfigurace zařízení* profilu.

Tato funkce platí pro:

- Windows 10 verze 1809 a novější

Nasazení standardních hodnot zabezpečení pro skupiny uživatelů nebo zařízení v Intune a nastavení platí pro zařízení se systémem Windows 10 nebo novější. Například *směrný plán zabezpečení MDM* automaticky povoluje nástroj BitLocker pro vyměnitelné jednotky, automaticky vyžaduje heslo k odemknutí zařízení, automaticky zakáže základní ověřování a další. Pokud výchozí hodnota nebude fungovat pro vaše prostředí, přizpůsobte směrný plán použít nastavení, které potřebujete.  

Samostatné základní typy mohou zahrnovat stejné nastavení, ale použít různé výchozí hodnoty pro tato nastavení. Je důležité pochopit, výchozí hodnoty v směrné plány, které chcete použít, a potom upravte každý směrný plán, aby vaše organizace potřebuje.  

> [!NOTE]
> Microsoft nebude doporučujeme používat verze preview standardních hodnot zabezpečení v produkčním prostředí. V průběhu verze preview může změnit nastavení v základní verzi preview. 

Cílem využít je směrné plány zabezpečení je, aby začátku do konce zabezpečené pracovní postupy při práci s Microsoft 365. Mezi výhody patří:

- Směrný plán zabezpečení obsahuje osvědčené postupy a doporučení týkající se nastavení, které mají vliv na zabezpečení. Intune spolupracuje s týmem stejné zabezpečení Windows, který vytváří základní nastavení zabezpečení zásad skupiny. Tato doporučení jsou založená na pokyny a rozsáhlých zkušeností.
- Pokud jste nový do Intune a nejste si jisti, kde začít, směrné plány zabezpečení vám nabídne výhodu. Můžete rychle vytvořit a nasadit profil zabezpečení vědomím, že vám pomáhají chránit prostředky a data vaší organizace.
- Pokud aktuálně používáte zásady skupiny, migrace do Intune pro správu je mnohem snazší díky tyto standardní hodnoty. Tyto standardní hodnoty jsou nativně integrované do Intune a zahrnují moderní správu prostředí.



[Základní nastavení zabezpečení Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) je skvělý prostředek pro další informace o této funkci. [Správa mobilních zařízení](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) je skvělým zdrojem o MDM a co můžete dělat na zařízeních s Windows.

## <a name="security-baseline-versions-and-instances"></a>Zabezpečení základní verze a instance
Čas od času budou k dispozici nové aktualizace pro směrný plán. Každá nová verze instance směrného plánu lze přidat nebo odebrat nastavení nebo zavést další změny. Například jako zpřístupní nové nastavení Windows 10 s novou verzí Windows 10, Směrný plán zabezpečení MDM se může zobrazit nové instance verze zahrnuje nejnovější nastavení.  

V konzole Intune můžete zobrazit, které směrné plány zabezpečení jsou k dispozici a informace o nich. K dispozici informace zahrnují, kolik profilů, máte, které používají toto zadejte, kolik samostatné instance typu směrného plánu jsou k dispozici a kdy byl proveden poslední instance nejnovější k dispozici nebo publikované.  Následující příklad ukazuje na dlaždici pro běžně používané směrný plán zabezpečení MDM:  

![Základní dlaždice](./media/security-baselines/baseline-tile.png)

Chcete-li zobrazit informace o základní verze používat, vyberte směrný plán a pak vyberte **verze**. Intune zobrazí podrobnosti o verzích používá podle vašich profilů. V podokně s verzí můžete vybrat jednu verzi zobrazíte podrobnější informace o profilech, které používají tuto verzi. Můžete také vybrat dvě různé verze a klikněte na tlačítko **porovnání směrné plány** ke stažení souboru CSV s podrobnostmi o těchto rozdílů.  

![Porovnat standardní hodnoty](./media/security-baselines/compare-baselines.png)

Když vytváříte směrný plán zabezpečení *profilu*, profil použije automaticky nedávno vydané instance standardních hodnot zabezpečení.  Můžete nadále používat a upravit profily, které jste dříve vytvořili, které používají starší verzi instance směrného plánu včetně směrné plány vytvořené ve verzi Preview. 

Směrný plán zabezpečení profilů podpory [změnit verze](#change-the-baseline-instance-for-a-profile) směrného plánu, který je používán. To znamená, když se dodává se nová verze, není nutné vytvořit nový profil směrného plánu jej využít. Místo toho až budete připraveni, můžete vybrat profil standardních hodnot a pak pomocí integrované možnosti změnit verzi instance pro tento profil.  

## <a name="available-security-baselines"></a>Směrné plány zabezpečení k dispozici 

Následující instance standardních hodnot zabezpečení jsou k dispozici pro použití s Intune. Chcete-li zobrazit nastavení pro aktuální instanci každý směrný plán pomocí odkazů. 

- **Směrný plán zabezpečení MDM**
  - [Směrný plán zabezpečení MDM pro Spring 2019 (19 hod. 1)](security-baseline-settings-mdm.md)
  - [Ve verzi Preview: Směrný plán zabezpečení MDM pro října 2018](security-baseline-settings-mdm-archive.md)

- **Směrný plán ochrany ATP v programu Windows Defender**  
  *(Chcete-li použít tyto standardní hodnoty musí vaše prostředí splňovat požadavky pro použití [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites))* .
  - [Ve verzi Preview: Směrný plán ochrany ATP v programu Windows Defender](security-baseline-settings-defender-atp.md)  

Můžete nadále používat a upravit profily, které jste dříve vytvořili založen na šabloně ve verzi preview, i v případě, že tato šablona ve verzi preview již není k dispozici pro vytváření nových profilů. 

## <a name="prerequisites"></a>Požadavky
- Ke správě směrných plánů v Intune, musí mít váš účet [správce zásad a profilů](role-based-access-control.md#built-in-roles) předdefinovaná role.

- Použití některými směrnými plány může být nutné mít aktivní předplatné k dalším službám, jako je ochrana ATP v programu Defender Microsoft.  

## <a name="co-managed-devices"></a>Spoluspravovaná zařízení

Základní nastavení zabezpečení na zařízeních spravovaných Intune se podobají spoluspravovaná zařízení s Configuration Managerem. Spoluspravovaná zařízení pomocí System Center Configuration Manager a Microsoft Intune můžete spravovat zařízení s Windows 10 současně. Umožňuje připojení nástroje Configuration Manager stávajícího prostředí k výhodám Intune cloudu. [Přehled spolusprávy](https://docs.microsoft.com/sccm/comanage/overview) je skvělý prostředek, pokud používáte nástroj Configuration Manager a také vhodné výhod cloudu.

Při použití spoluspravovaná zařízení, je nutné přepnout **konfigurace zařízení** pracovního vytížení (nastavení) do Intune. [Úlohy konfigurace zařízení](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) poskytuje další informace.

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a pak vyberte **zabezpečení zařízení** > **směrné plány zabezpečení** zobrazíte seznam dostupných standardních hodnot.


    ![Vyberte směrný plán zabezpečení ke konfiguraci](./media/security-baselines/available-baselines.png)

2. Vyberte směrný plán, který chcete použít a potom vyberte **vytvořit profil**.  

3. Na **Základy** kartu, zadejte následující vlastnosti:

    - **Název**: Zadejte název pro svůj profil standardních hodnot zabezpečení. Zadejte například *standardní profil ochrany ATP v programu Defender*.

    - **Popis**: Zadejte nějaký text, který popisuje, co dělá tyto standardní hodnoty. Popis je můžete zadat libovolný text, který chcete. Je volitelný, ale doporučujeme.  

   Vyberte **Další** přejdete na další kartě. Poté, co můžete upřesnit na novou kartu, můžete vybrat název karty se vraťte na dříve zobrazenou kartu.  

4. Na kartě nastavení konfigurace zobrazit skupiny **nastavení** , které jsou dostupné ve standardních hodnotách, které jste vybrali. Můžete rozbalit skupinu a zobrazit nastavení v této skupině a výchozí hodnoty pro tato nastavení ve směrném plánu. Vyhledání konkrétní nastavení:
   - Vyberte skupinu rozbalte a zkontrolujte nastavení k dispozici.  
   - Použití *hledání* řádku a zadejte klíčová slova, která filtrovat zobrazení a zobrazit pouze skupiny, které obsahují kritériím hledání.  
 
   Každé nastavení ve standardních hodnotách má výchozí konfigurace pro tuto základní verzi. Překonfigurujte výchozí nastavení, aby vyhovovala vašim obchodním potřebám. Jiné standardní hodnoty mohou obsahovat stejné nastavení a použít různé výchozí hodnoty pro nastavení, v závislosti na záměru směrného plánu. 

    ![Rozbalením skupiny lze zobrazit nastavení pro tuto skupinu](./media/security-baselines/sample-list-of-settings.png)

5. Na **značky oboru** kartu, vyberte možnost **vyberte značky oboru** otevřít *vyberte tagy, které* podoknem přiřadit značky oboru profilu. 

6. Na **přiřazení** kartu, vyberte možnost **vybrat skupiny, které chcete zahrnout** a pak mu přiřaďte standardních hodnot do jedné nebo více skupin. Použití **výběr skupin k vyloučení** a systém doladit přiřazení.  

   ![Přiřazení profilu](./media/security-baselines/assignments.png)
  
7. Až budete připravení nasadit standardní hodnoty, pokračujte **zkontrolujte + vytvořit** kartu zkontrolujte také podrobnosti pro požadovaný směrný plán. Vyberte **vytvořit** uložte a nasaďte profil.  

   Jakmile vytvoříte profil, se vloží do přiřazené skupině a může ihned.

   > [!TIP]  
   > Pokud uložíte profil bez první přiřazení do skupin, můžete později upravit profil, který chcete provést.  

   ![Revize směrného plánu](./media/security-baselines/review.png) 

  
8. Až profil vytvoříte, upravit ji tak, že přejdete do **zabezpečení zařízení** > **směrné plány zabezpečení**, vyberte typ směrný plán, který jste nakonfigurovali a pak vyberte **profily**.  Ze seznamu dostupných profilů vyberte profil a pak vyberte **vlastnosti**. Můžete upravit nastavení z všechny dostupné konfigurace karty a vybrat **revize + Uložit** potvrďte provedené změny.  

## <a name="change-the-baseline-instance-for-a-profile"></a>Změna instance směrný plán pro profil
Profily směrného plánu podpory změnu instance směrného plánu, který bude profil používat. Můžete vybrat instance starší nebo častěji novější instance stejného základu.  Mezi dva různé směrné plány, jako je například změna profilu pomocí směrný plán pro ochrany ATP v programu Defender pomocí standardních hodnot zabezpečení MDM nelze změnit. 

Při změně verze standardních hodnot konfigurace, budete mít možnost Stáhnout soubor CSV, který obsahuje seznam změn mezi zahrnuté dva základní verze. Budete také nabízí možnost zachovat všechny úpravy v původní základní verzi a aplikovat na novou verzi nebo implementovat všechny výchozí hodnoty nalezené v nové základní verze, kterou jste vybrali. 

Po uložení, po dokončení převodu směrného plánu je ihned znovu nasadit do přiřazených skupin.  

**Při převodu**:
- Nová nastavení, která nejsou v původní verzi, kterou jste používali jsou přidány a nastaveno pro použití výchozí hodnoty.  

- Nastavení, které nejsou v nové základní verze, kterou vyberete, se odeberou a už nebudou vynucené tento profil standardních hodnot zabezpečení.  

  Při nastavení už není spravované v rámci směrného plánu profilu, toto nastavení není obnovit v zařízení. Místo toho nastavení na zařízení zůstane sada k jeho poslední konfigurace až do nějaký jiný proces slouží ke správě nastavení změnit. Procesy, které můžete změnit nastavení, poté, co zastavíte jeho správu příkladem profil různých standardních hodnot, nastavení zásad skupiny nebo ruční konfigurace, která je vytvořena na zařízení. 

### <a name="to-change-the-instance-for-a-baseline"></a>Chcete-li změnit instanci pro směrný plán  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a pak vyberte **zabezpečení zařízení** > **směrné plány zabezpečení**a pak vyberte dlaždici pro základní typ, který má profil, který chcete, aby Chcete-li změnit.  

2. V dalším kroku vyberte **profily**a potom zaškrtněte políčko pro profil, který chcete upravit a pak vyberte **změnit verzi**.  

   ![Vyberte směrný plán](./media/security-baselines/select-baseline.png)  

3. Na **změnit verzi** podokně, použijte **vyberte směrný plán zabezpečení k aktualizaci** rozevíracího seznamu a vyberte verzi instanci, kterou chcete použít.  

   ![Vyberte verzi](./media/security-baselines/select-instance.png)  
 
4. Vyberte **aktualizace** stáhnout soubor CSV, který zobrazuje rozdíl mezi profily aktuální instance verzi a nová verze, které jste vybrali. Zkontrolováním tohoto souboru tak, že rozumíte nastavení, které jsou přidány, odebrány, a jaké výchozí hodnoty pro tato nastavení jsou v aktualizovaný profil.  

   Až to budete mít, pokračujte k dalšímu kroku.  

5. Zvolte jednu ze dvou možností pro **vyberte metodu se aktualizovat profil**: 
   - **Přijmout změny základní, ale ponechat Moje stávající nastavení přizpůsobení** – tuto možnost udržuje vlastní nastavení provedené profil standardních hodnot a aplikuje je na novou verzi jsme se rozhodli použít.
   - **Přijmout změny směrný plán a zahodit stávající nastavení přizpůsobení** – tato možnost přepíše váš původním profil úplně. Aktualizovaný profil použije výchozí hodnoty pro všechna nastavení.  

6. Vyberte **odeslat**. Aktualizace profilu na vybrané základní verzi a po dokončení převodu směrný plán ihned znovu nasadí do přiřazených skupin.

## <a name="remove-a-security-baseline-assignment"></a>Odebrání přiřazení směrného plánu zabezpečení
Při nastavení standardních hodnot zabezpečení už platí pro zařízení, nebo ve standardních hodnotách nastavení *Nenakonfigurováno*, tato nastavení na zařízení nechcete obnovit předem spravované konfigurace. Místo toho dříve spravovaných nastavení na zařízení zachovat jejich poslední konfigurace přijetí ze standardních hodnot, dokud se tato nastavení na zařízení aktualizuje nějaký jiný proces.  

Další procesy, které může být později změnit nastavení na zařízení zahrnují směrný plán zabezpečení různých nebo nové, konfigurační profil zařízení, konfigurace zásad skupiny nebo ruční úpravy nastavení na zařízení.  





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

- Migrace z místní zásady skupiny služby Active Directory na čistě cloudové řešení pomocí Azure Active Directory (AD) pomocí Microsoft Intune se na cestu. Abychom pomohli, jsou součástí šablony zásad skupiny [Toolkit dodržování předpisů zabezpečení](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10) , který může pomoct spravovat hybridní AD a Azure zařízení připojených k doméně AD. Tato zařízení můžete získat nastavení MDM z cloudu (Intune) a nastavení zásad skupiny z řadičů domény s místními podle potřeby.

## <a name="next-steps"></a>Další postup
- Zobrazte nastavení v nejnovějších verzích dostupné standardní hodnoty:  
  - [Směrný plán zabezpečení MDM](security-baseline-settings-mdm.md)  
  - [Směrný plán ochrany ATP v programu Windows Defender](security-baseline-settings-defender-atp.md)  

- Zkontrolujte stav a monitorování [směrného plánu a profil](security-baselines-monitor.md).
