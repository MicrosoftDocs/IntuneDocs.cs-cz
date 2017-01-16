---
title: "Ochrana aplikačních dat pomocí zásad MAM | Dokumentace Microsoftu"
description: "Toto téma vysvětluje, jak zásady správy mobilních aplikací můžou pomoct chránit podniková data, bránit úniku informací a oddělovat osobní a pracovní informace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e208608d50c9b5f7fe66743de0d3c7e741dbfbd
ms.openlocfilehash: c2293306e847148ff7413be3e9eeafb8349e33fe


---

# <a name="protect-app-data-using-mobile-application-management-policies-with-microsoft-intune"></a>Ochrana dat aplikací pomocí zásad správy mobilních aplikací v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Způsob ochrany dat aplikací
Vaši zaměstnanci používají mobilní zařízení pro osobní a pracovní úkoly. Chcete, aby vaši zaměstnanci byli produktivní, ale také chcete zabránit případným záměrným či neúmyslným únikům informací.  Kromě toho chcete mít možnost chránit podniková data, ke kterým zaměstnanci přistupují ze zařízení, která nespravujete.

Zásady správy mobilních aplikací (MAM) služby Intune vám pomohou podniková data ochránit. Protože se zásady MAM služby Intune dají používat **nezávisle na řešení správy mobilních zařízení (MDM)**, můžete MAM použít k ochraně podnikových dat i bez registrace zařízení do řešení správy zařízení. Implementací **zásad na úrovni aplikace** můžete omezit přístup k prostředkům společnosti a ponechat data v kompetenci IT oddělení.

Zásady MAM můžete konfigurovat pro aplikace běžící na zařízeních, která jsou:

-   **Zaregistrovaná v Microsoft Intune:** Do této kategorie obvykle spadají zařízení vlastněná společností.

-   **Zaregistrovaná v řešení MDM třetí strany:** Do této kategorie obvykle spadají zařízení vlastněná společností.

  > [!NOTE]
  > Zásady MAM nedoporučujeme používat s řešeními pro správu mobilních aplikací třetích stran nebo s řešeními zabezpečeného kontejneru.

-   **Nezaregistrovaná v žádném řešení MDM:** Do této kategorie obvykle spadají zařízení vlastněná zaměstnanci, která nejsou spravovaná ani zaregistrovaná v Intune nebo jiných řešeních MDM.

> [!IMPORTANT]
> Můžete vytvářet zásady správy mobilních aplikací pro mobilní aplikace Office, které se připojují ke službám Office 365. Zásady MAM se nepodporují pro aplikace, které se připojují k místním službám Exchange, Skype pro firmy nebo SharePoint.

## <a name="benefits-of-using-mam-policies"></a>Výhody použití zásad MAM

-   **Chrání podniková data na úrovni aplikace.** Protože správa mobilních aplikací nevyžaduje správu zařízení, můžete podniková data chránit na spravovaných i nespravovaných zařízeních. Správa je zaměřená na identitu uživatele, odpadá tedy požadavek na správu zařízení.

-   **Produktivita uživatele není ovlivněná a při použití aplikace pro osobní účely se zásady neaplikují.** Zásady se použijí jenom v pracovním kontextu, což umožňuje chránit podniková data bez zásahu do osobních dat.

Použití MDM se zásadami MAM přináší i další výhody. Společnosti můžou zásady MAM současně používat jak se správou MDM, tak i bez ní. Zaměstnanci můžou například používat podnikový telefon i vlastní tablet. V takovém případě je podnikový telefon zaregistrovaný do řešení MDM a chráněný zásadami MAM, zatímco vlastní zařízení zaměstnance je jenom chráněné zásadami MAM.

- **MDM zajišťuje ochranu zařízení.** Můžete například přístup do zařízení zabezpečit kódem PIN nebo do zařízení nasadit spravované aplikace. Do zařízení můžete aplikace nasadit také pomocí řešení MDM, čímž získáte větší kontrolu nad správou aplikací.

- **Zásady MAM zajišťují použití ochrany na úrovni aplikací.** Můžete například vytvořit zásadu, která bude při otevření aplikace v pracovním kontextu vyžadovat kód PIN, zabrání sdílení dat mezi aplikacemi nebo zabrání ukládání podnikových dat do osobního úložiště.

## <a name="devices-that-support-mam"></a>Zařízení podporující MAM
Zásady MAM se aktuálně podporují v těchto systémech:
-   iOS 8.1 nebo novější
-   Android 4 nebo novější

V současné době není dostupná podpora zařízení s Windows.
##  <a name="how-mam-policies-protect-app-data"></a>Jak zásady MAM chrání data aplikací

###  <a name="apps-without-mam-policies"></a>Aplikace bez zásad MAM

![Obrázek znázorňující, jak se můžou data volně přesouvat mezi aplikacemi, pokud nejsou nastavené zásady MAM](../media/Apps_without_MAM_policies.png)

Pokud aplikace používáte bez omezení, můžou se osobní a podniková data prolínat. Podniková data můžou být uložena do osobního úložiště nebo přenesena do aplikací mimo váš dosah, čímž může dojít k úniku informací. Šipky v diagramu znázorňují neomezený přesun dat mezi aplikacemi (podnikovými a osobními) a úložišti.

### <a name="data-protection-with-mam-policies"></a>Ochrana dat pomocí zásad MAM

![Obrázek znázorňující způsob ochrany podnikových dat při použití zásad MAM](../media/Apps_with_mobile_app_policies.png)

Pomocí zásad MAM můžete zabránit uložení podnikových dat do místního úložiště na zařízení a omezit přesun dat do jiných aplikací, které nejsou chráněné zásadami MAM. Nastavení zásad MAM zahrnuje tyto položky:
- Zásady pro přemísťování dat, jako jsou **Zakázat možnost Uložit jako** a **Omezit vyjmutí, zkopírování a vložení**.
- Nastavení zásad přístupu, jako jsou **Vyžadovat pro přístup jednoduchý PIN kód** a **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**.

### <a name="data-protection-with-mam-policies-on-devices-that-are-managed-by-a-mdm-solution"></a>Ochrana dat pomocí zásad MAM na zařízeních spravovaných řešením MDM

![Obrázek znázorňující, jak zásady MAM fungují na vlastních zařízeních uživatelů (BYOD)](../media/MAM_BYOD_November.png)

**Zařízení zaregistrovaná v řešení MDM**: Předchozí diagram znázorňuje vrstvy ochrany, které MDM a zásady MAM společně nabízejí.

Řešení MDM:

-   Zaregistruje zařízení.

-   Na zařízení nasadí aplikace.

-   Zajišťuje neustálé dodržování předpisů a správu zařízení.

**Zásady MAM navíc pomáhají z následujících důvodů:**

-   Chrání před únikem podnikových informací v uživatelských aplikacích a službách.

-   Aplikují omezení (použití příkazu Uložit jako, schránky, kódu PIN atd.) pro mobilní aplikace.

-   Vymažou podniková data z aplikací bez nutnosti tyto aplikace ze zařízení odebrat.


### <a name="data-protection-with-mam-policies-for-devices-without-enrollment"></a>Ochrana dat pro zařízení bez registrace pomocí zásad MAM

![Obrázek, který ukazuje, jak fungují zásady MAM na spravovaných zařízeních](../media/MAM_ManagedDevices_November.png)

Předchozí diagram znázorňuje, jak fungují zásady ochrany dat na úrovni aplikace bez správy mobilních zařízení MDM.

U vlastních zařízení uživatelů nezaregistrovaných do řešení MDM můžou zásady MAM pomoct chránit podniková data na úrovni aplikace.

Je ale potřeba mít na paměti některá omezení:

-   Aplikace nejde do zařízení nasadit. Uživatel musí aplikace sám získat a nainstalovat.

-   V těchto zařízeních nejde zřídit profily certifikátů.

-   V těchto zařízeních nejde nastavit podnikovou síť Wi-Fi a síť VPN.


## <a name="multi-identity"></a>Víc identit

Aplikace, které podporují víc identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady MAM se použijí, jen když jsou aplikace použité v pracovním kontextu.  

Pokud třeba uživatel spustí aplikaci OneDrive pomocí svého pracovního účtu, nemůže přesunout soubory do svého osobního úložiště. Pokud ale uživatel použije OneDrive se svým osobním účtem, může kopírovat a přesouvat data ze svého osobního OneDrivu bez omezení.  

Všechny mobilní aplikace Office podporují přístup pomocí více identit.

##  <a name="next-steps"></a>Další kroky
- [Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


