---
title: "Co jsou zásady ochrany aplikací"
titleSuffix: Intune on Azure
description: "V tomto tématu se seznámíte s ochranou firemních dat pomocí zásad ochrany aplikací Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13b3199108c34a61d117e4d89d118bdd05d7d20f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="what-are-app-protection-policies"></a>Co jsou zásady ochrany aplikací?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady ochrany aplikací Microsoft Intune pomáhají chránit firemní data a bránit únikům informací.

## <a name="how-you-can-protect-app-data"></a>Způsob ochrany dat aplikací
Vaši zaměstnanci používají mobilní zařízení pro osobní a pracovní úkoly.  Chcete, aby vaši zaměstnanci byli produktivní, ale také chcete zabránit případným záměrným či neúmyslným ztrátám dat.  Kromě toho chcete mít možnost chránit firemní data při přístupu pomocí zařízení i v případě, že tato zařízení nespravujete.

K ochraně firemních dat můžete použít zásady ochrany aplikací Intune. Protože se zásady ochrany aplikací Intune dají používat **nezávisle na řešení správy mobilních zařízení (MDM)**, můžete je použít k ochraně firemních dat i bez registrace zařízení do nějakého řešení správy zařízení. Implementací **zásad na úrovni aplikace** můžete omezit přístup k prostředkům společnosti a ponechat data v kompetenci IT oddělení.

Zásady ochrany aplikací lze konfigurovat pro aplikace běžící na zařízeních, která jsou:

- **Zaregistrovaná v Microsoft Intune:** Do této kategorie obvykle spadají zařízení vlastněná společností.

-   **Zaregistrovaná v rámci řešení pro správu mobilních zařízení (MDM) třetích stran:** Do této kategorie obvykle spadají zařízení vlastněná společností.

  > [!NOTE]
  > Zásady správy mobilních aplikací není vhodné používat s řešeními pro správu mobilních aplikací třetích stran nebo zabezpečeného kontejneru.

-   **Neregistrovaná v žádném řešení pro správu mobilních zařízení:** Do této kategorie obvykle spadají zařízení vlastněná zaměstnanci, která nejsou spravovaná ani zaregistrovaná v Intune nebo jiných řešeních MDM.

> [!IMPORTANT]
> Můžete vytvářet zásady správy mobilních aplikací pro mobilní aplikace Office, které se připojují ke službám Office 365. Zásady ochrany aplikací se nepodporují pro aplikace, které se připojují k místním službám Exchange, Skype pro firmy nebo SharePoint.

**Důležité výhody při použití zásad ochrany aplikací:**

-   Ochrana podnikových dat na úrovni aplikace.  Protože správa mobilních aplikací nevyžaduje správu zařízení, můžete firemní data chránit na spravovaných i nespravovaných zařízeních. Správa je zaměřená na identitu uživatele, odpadá tedy požadavek na správu zařízení.

-   Produktivita koncového uživatele není ovlivněná a při použití aplikace pro osobní účely se zásady neaplikují.  Zásady se použijí jenom v pracovním kontextu, což umožňuje chránit firemní data bez zásahu do osobních dat.

Použití správy mobilních zařízení se zásadami ochrany aplikací přináší další výhody, přičemž firmy mohou zásady ochrany aplikací využívat se správou mobilních zařízení i bez. Zaměstnanci mohou například používat podnikový telefon i vlastní tablet.  V takovém případě je podnikový telefon zaregistrovaný ve správě mobilních zařízení a chráněný zásadami ochrany aplikací, zatímco vlastní zařízení je chráněné jen zásadami ochrany aplikací.

- **Řešení MDM zajišťuje ochranu zařízení**.  Můžete například přístup do zařízení zabezpečit kódem PIN nebo do zařízení nasadit spravované aplikace. Do zařízení můžete aplikace nasadit také pomocí řešení MDM, čímž získáte větší kontrolu nad správou aplikací.

- **Zásady ochrany aplikací zajišťují, že se používá ochrana aplikační vrstvy**. Otevírání aplikací v pracovním kontextu, sdílení dat mezi dvěma aplikacemi nebo ukládání firemních dat na soukromá úložiště můžete například zabezpečit pomocí kódu PIN.


### <a name="supported-platforms-for-app-protection-polices"></a>Podporované platformy pro zásady ochrany aplikací
-   iOS 8.1 nebo novější

-   Android 4 nebo novější

V současné době není dostupná podpora zařízení s Windows. Pokud zařízení s Windows 10 zaregistrujete do Intune, můžete použít sadu Windows Information Protection, která nabízí podobné funkce. Podrobnosti najdete v tématu věnovanému [ochraně podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
##  <a name="how-app-protection-policies-protect-app-data"></a>Jak zásady ochrany aplikací chrání data aplikací

####  <a name="apps-without-app-protection-policies"></a>Aplikace bez zásad ochrany aplikací

![Obrázek, který znázorňuje, že pokud se nepoužívají zásady ochrany aplikací, můžou se data volně přesouvat mezi aplikacemi](./media/apps-without-protection-policies.png)

Pokud se aplikace používají bez omezení, můžou se osobní a firemní data prolínat.  Firemní data můžou být uložená v osobním úložišti nebo přenesená do aplikací mimo váš dosah, a může tím dojít ke ztrátě dat. Šipky v diagramu znázorňují neomezený přesun dat mezi aplikacemi (podnikovými a osobními) a úložišti.

### <a name="data-protection-with-app-protection-policies"></a>Ochrana dat pomocí zásad ochrany aplikací

![Obrázek, který znázorňuje způsob ochrany firemních dat při použití zásad ochrany aplikací ](./media/apps-with-protection-policies.png)


Pomocí zásad ochrany aplikací můžete zabránit ukládání firemních dat do místního úložiště na zařízení a omezit přesun dat do jiných aplikací, které nejsou chráněné zásadami ochrany aplikací. Mezi nastavení zásad ochrany aplikací patří:
- Zásady přemístění dat, jako je **Zakázat možnost Uložit jako**, **Omezit vyjmutí, zkopírování a vložení**.
- Nastavení zásad přístupu, jako je **Vyžadovat pro přístup jednoduchý PIN kód**, **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Ochrana dat pomocí zásad ochrany aplikací na zařízeních spravovaných řešením MDM

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na vlastních zařízeních uživatelů (BYOD)](./media/app-protection-policies-with-mdm.png)

**Zařízení zaregistrovaná v řešení MDM**-

Předchozí obrázek znázorňuje vrstvy ochrany, které řešení MDM a zásady ochrany aplikací nabízejí společně.

Řešení MDM:

-   Zaregistruje zařízení.

-   Na zařízení nasadí aplikace.

-   Zajišťuje neustálé dodržování předpisů a správu zařízení.

**Zásady ochrany aplikací přidávají hodnotu tím, že dokážou:**

-   Chránit před únikem firemních dat v uživatelských aplikacích a službách

-   Aplikovat omezení (Uložit jako, schránka, kód PIN atd.) pro mobilní aplikace

-   Vymazat firemní data z aplikací bez nutnosti tyto aplikace ze zařízení odebrat


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Ochrana dat pomocí zásad ochrany aplikací na neregistrovaných zařízeních

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na spravovaných zařízeních](./media/app-protection-policies-without-mdm.png)

Diagram výš ukazuje, jak fungují zásady ochrany dat na úrovni aplikace bez správy mobilních zařízení.

U vlastních zařízení uživatelů nezaregistrovaných do řešení MDM můžou zásady ochrany aplikací pomoci chránit firemní data na úrovni aplikace.
Je ale potřeba mít na paměti některá omezení, jako například:

-   Aplikace nejde do zařízení nasadit.  Koncový uživatel musí aplikace sám nainstalovat.

-   V těchto zařízeních nejde zřídit profily certifikátů.

-   V těchto zařízeních nejde zřídit firemní sítě Wi-Fi a nastavit síť VPN.


## <a name="multi-identity"></a>Víc identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když jsou aplikace použité v pracovním kontextu.

Pokud třeba uživatel spustí aplikaci OneDrive pomocí svého pracovního účtu, nemůže přesunout soubory do svého osobního úložiště. Pokud ale uživatel použije OneDrive se svým osobním účtem, může kopírovat a přesouvat data ze svého osobního OneDrivu bez omezení.

- Přečtěte si další informace o aplikacích, které podporují [MAM a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

##  <a name="next-steps"></a>Další kroky

[Jak vytvořit a nasadit zásady ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)
