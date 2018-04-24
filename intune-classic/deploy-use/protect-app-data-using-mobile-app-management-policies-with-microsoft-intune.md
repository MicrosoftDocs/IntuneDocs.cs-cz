---
title: Ochrana dat aplikací pomocí zásad MAM
description: Toto téma vysvětluje, jak zásady správy mobilních aplikací můžou pomoct chránit podniková data, bránit úniku informací a oddělovat osobní a pracovní informace.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dcdee874e42aa9511c09fda43a8cc662afaea38a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a>Ochrana dat aplikací pomocí zásad ochrany aplikací v Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Způsob ochrany dat aplikací
Vaši zaměstnanci používají mobilní zařízení pro osobní a pracovní úkoly. Chcete, aby vaši zaměstnanci byli produktivní, ale také chcete zabránit případným záměrným či neúmyslným únikům informací.  Kromě toho chcete mít možnost chránit podniková data, ke kterým zaměstnanci přistupují ze zařízení, která nespravujete.

K ochraně firemních dat můžete použít zásady ochrany aplikací Intune. Protože se zásady ochrany aplikací Intune dají používat **nezávisle na řešení správy mobilních zařízení (MDM)**, můžete správu mobilních aplikací (MAM) použít k ochraně firemních dat i bez registrace zařízení do nějakého řešení správy zařízení. Implementací **zásad na úrovni aplikace** můžete omezit přístup k prostředkům společnosti a ponechat data v kompetenci IT oddělení.

Zásady ochrany aplikací můžete konfigurovat pro aplikace běžící na zařízeních, která jsou:

-   **Zaregistrovaná v Microsoft Intune:** Do této kategorie obvykle spadají zařízení vlastněná společností.

-   **Zaregistrovaná v řešení MDM třetí strany:** Do této kategorie obvykle spadají zařízení vlastněná společností.

    > [!NOTE]
    > Zásady ochrany aplikací nedoporučujeme používat s řešeními pro správu mobilních aplikací třetích stran nebo s řešeními zabezpečeného kontejneru.

-   **Nezaregistrovaná v žádném řešení MDM:** Do této kategorie obvykle spadají zařízení vlastněná zaměstnanci, která nejsou spravovaná ani zaregistrovaná v Intune nebo jiných řešeních MDM.

> [!IMPORTANT]
> Můžete vytvářet zásady ochrany aplikací pro mobilní aplikace Office, které se připojují ke službám Office 365. Zásady ochrany aplikací nejsou podporované pro aplikace, které se připojují k místním službám Exchange, Skype pro firmy nebo SharePoint.

## <a name="benefits-of-using-app-protection-policies"></a>Výhody použití zásad ochrany aplikací

-   **Chrání podniková data na úrovni aplikace.** Protože správa mobilních aplikací nevyžaduje správu zařízení, můžete podniková data chránit na spravovaných i nespravovaných zařízeních. Správa je zaměřená na identitu uživatele, odpadá tedy požadavek na správu zařízení.

-   **Produktivita uživatele není ovlivněná a při použití aplikace pro osobní účely se zásady neaplikují.** Zásady se použijí jenom v pracovním kontextu, což umožňuje chránit podniková data bez zásahu do osobních dat.

Použití MDM se zásadami ochrany aplikací přináší i další výhody. Společnosti můžou zásady MAM současně používat jak se správou MDM, tak i bez ní. Zaměstnanci můžou například používat podnikový telefon i vlastní tablet. V takovém případě je podnikový telefon zaregistrovaný ve správě mobilních zařízení a chráněný zásadami ochrany aplikací, zatímco vlastní zařízení je chráněné jen zásadami ochrany aplikací.

- **MDM zajišťuje ochranu zařízení.** Můžete například přístup do zařízení zabezpečit kódem PIN nebo do zařízení nasadit spravované aplikace. Do zařízení můžete aplikace nasadit také pomocí řešení MDM, čímž získáte větší kontrolu nad správou aplikací.

- **Zásady ochrany aplikací zajišťují použití ochrany na úrovni aplikací.** Můžete například vytvořit zásadu, která bude při otevření aplikace v pracovním kontextu vyžadovat kód PIN, zabrání sdílení dat mezi aplikacemi nebo zabrání ukládání podnikových dat do osobního úložiště.

## <a name="devices-that-support-mam"></a>Zařízení podporující MAM
Podpora platforem pro zásady ochrany aplikací Intune je spojená s podporou platforem pro aplikace Office. Podrobnosti najdete v tématu [Požadavky na systém pro Office](https://products.office.com/en-US/office-system-requirements).

>[!NOTE]
>Zařízení s Windows nejsou ve scénáři MAM bez registrace podporované. Pokud zařízení s Windows 10 zaregistrujete do Intune, můžete použít sadu Windows Information Protection, která nabízí podobné funkce. Podrobnosti najdete v tématu věnovanému [ochraně podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


##  <a name="how-app-protection-policies-protect-app-data"></a>Jak zásady ochrany aplikací chrání data aplikací

###  <a name="apps-without-app-protection-policies"></a>Aplikace bez zásad ochrany aplikací

![Obrázek, který znázorňuje, že pokud se nepoužívají zásady ochrany aplikací, můžou se data volně přesouvat mezi aplikacemi](../media/Apps_without_MAM_policies.png)

Pokud aplikace používáte bez omezení, můžou se osobní a podniková data prolínat. Podniková data můžou být uložena do osobního úložiště nebo přenesena do aplikací mimo váš dosah, čímž může dojít k úniku informací. Šipky v diagramu znázorňují neomezený přesun dat mezi aplikacemi (podnikovými a osobními) a úložišti.

### <a name="data-protection-with-app-protection-policies"></a>Ochrana dat pomocí zásad ochrany aplikací

![Obrázek, který znázorňuje způsob ochrany firemních dat při použití zásad ochrany aplikací](../media/Apps_with_mobile_app_policies.png)

Pomocí zásad ochrany aplikací můžete zabránit ukládání firemních dat do místního úložiště na zařízení a omezit přesun dat do jiných aplikací, které nejsou chráněné zásadami ochrany aplikací. Mezi nastavení zásad ochrany aplikací patří:
- Zásady pro přemísťování dat, jako jsou **Zakázat možnost Uložit jako** a **Omezit vyjmutí, zkopírování a vložení**.
- Nastavení zásad přístupu, jako jsou **Vyžadovat pro přístup jednoduchý PIN kód** a **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**.

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a>Ochrana dat pomocí zásad ochrany aplikací na zařízeních spravovaných řešením MDM

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na vlastních zařízeních uživatelů](../media/MAM_BYOD_November.png)

**Zařízení zaregistrovaná v řešení MDM:** Předchozí diagram znázorňuje vrstvy ochrany, které MDM a zásady ochrany aplikací společně nabízejí.

Řešení MDM:

-   Zaregistruje zařízení.

-   Na zařízení nasadí aplikace.

-   Zajišťuje neustálé dodržování předpisů a správu zařízení.

**Zásady ochrany aplikací přidávají hodnotu tím, že:**

-   Chrání před únikem podnikových informací v uživatelských aplikacích a službách.

-   Aplikují omezení (použití příkazu Uložit jako, schránky, kódu PIN atd.) pro mobilní aplikace.

-   Vymažou podniková data z aplikací bez nutnosti tyto aplikace ze zařízení odebrat.


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Ochrana dat pomocí zásad ochrany aplikací na neregistrovaných zařízeních

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na spravovaných zařízeních](../media/MAM_ManagedDevices_November.png)

Předchozí diagram znázorňuje, jak fungují zásady ochrany dat na úrovni aplikace bez správy mobilních zařízení MDM.

U vlastních zařízení uživatelů nezaregistrovaných do řešení MDM můžou zásady ochrany aplikací pomoci chránit firemní data na úrovni aplikace.

Je ale potřeba mít na paměti některá omezení:

-   Aplikace nejde do zařízení nasadit. Uživatel musí aplikace sám získat a nainstalovat.

-   V těchto zařízeních nejde zřídit profily certifikátů.

-   V těchto zařízeních nejde nastavit podnikovou síť Wi-Fi a síť VPN.


## <a name="multi-identity"></a>Víc identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když jsou aplikace použité v pracovním kontextu.  

Pokud třeba uživatel spustí aplikaci OneDrive pomocí svého pracovního účtu, nemůže přesunout soubory do svého osobního úložiště. Pokud ale uživatel použije OneDrive se svým osobním účtem, může kopírovat a přesouvat data ze svého osobního OneDrivu bez omezení.  

- Přečtěte si další informace o aplikacích, které podporují [MAM a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

##  <a name="next-steps"></a>Další kroky
- [Příprava ke konfiguraci zásad ochrany aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
