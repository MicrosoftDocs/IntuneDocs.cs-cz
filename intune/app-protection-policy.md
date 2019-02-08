---
title: Co jsou zásady ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak zásady ochrany aplikací Microsoft Intune pomáhají chránit firemní data a bránit únikům informací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dbb6a8f159aebe837fabf671a84dd96223298227
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836349"
---
# <a name="what-are-app-protection-policies"></a>Co jsou zásady ochrany aplikací?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady ochrany aplikací Microsoft Intune pomáhají chránit firemní data a bránit únikům informací.

## <a name="how-you-can-protect-app-data"></a>Způsob ochrany dat aplikací
Vaši zaměstnanci používají mobilní zařízení pro osobní a pracovní úkoly. Chcete, aby vaši zaměstnanci byli produktivní, ale chcete zabránit případným záměrným či neúmyslným ztrátám dat. Budete také chtít chránit firemní data, s kterými se pracuje ze zařízení, která nespravujete.

Můžete použít zásady ochrany aplikací Intune **nezávisle na řešení správy mobilních zařízení (MDM)**. Tato nezávislost vám pomůže s ochranou dat vaší společnosti, ať už budou zařízení registrovaná v řešení pro správu zařízení nebo ne. Implementací **zásad na úrovni aplikace** můžete omezit přístup k prostředkům společnosti a ponechat data v kompetenci IT oddělení.

Zásady ochrany aplikací lze konfigurovat pro aplikace běžící na zařízeních, která jsou:

- **Zaregistrovaná v Microsoft Intune:** Obvykle jsou tato zařízení ve vlastnictví.

- **Zaregistrovaná v řešení správy mobilních zařízení třetích stran:** Obvykle jsou tato zařízení ve vlastnictví.

  > [!NOTE]
  > Zásady správy mobilních aplikací není vhodné používat s řešeními pro správu mobilních aplikací třetích stran nebo zabezpečeného kontejneru.

- **Nejsou zaregistrovaná v žádném řešení pro správu mobilních zařízení:** Zařízení jsou obvykle zařízení zaměstnanců, která nejsou spravovaná ani zaregistrovaná v Intune nebo jiných řešeních MDM.

> [!IMPORTANT]
> Můžete vytvářet zásady správy mobilních aplikací pro mobilní aplikace Office, které se připojují ke službám Office 365. Přístup k místním poštovním schránkám Exchange můžete chránit také tak, že vytvoříte zásady ochrany aplikací Intune pro Outlook pro iOS a Android s hybridním moderním ověřováním. Ještě než začnete tuto funkci využívat, zkontrolujte, že splňujete [požadavky na Outlook pro iOS a Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Zásady ochrany aplikací se nepodporují pro jiné aplikace, které se připojují k místním službám Exchange nebo SharePoint.

**Důležité výhody při použití zásad ochrany aplikací:**

-   Ochrana podnikových dat na úrovni aplikace. Protože správa mobilních aplikací nevyžaduje správu zařízení, můžete podniková data chránit na spravovaných i nespravovaných zařízeních. Správa je zaměřená na identitu uživatele, odpadá tedy požadavek na správu zařízení.

-   Produktivita koncového uživatele není ovlivněná a při použití aplikace pro osobní účely se neaplikují zásady. Zásady se použijí jenom v pracovním kontextu, což umožňuje chránit podniková data bez zásahu do osobních dat.

Použití správy mobilních zařízení se zásadami ochrany aplikací přináší další výhody, přičemž firmy můžou zásady ochrany aplikací využívat najednou se správou mobilních zařízení i bez. Představte si třeba zaměstnance, který používá firemní telefon i vlastní tablet. Firemní telefon je zaregistrovaný ve správě mobilních zařízení a chráněný zásadami ochrany aplikací, zatímco vlastní zařízení je chráněné jen zásadami ochrany aplikací.

- **Řešení MDM zajišťuje ochranu zařízení**. Můžete například přístup do zařízení zabezpečit kódem PIN nebo do zařízení nasadit spravované aplikace. Do zařízení můžete aplikace nasadit také pomocí řešení MDM, čímž získáte větší kontrolu nad správou aplikací.

- **Zásady ochrany aplikací zajišťují, že se používá ochrana aplikační vrstvy**. Například můžete:
  - Vyžadovat PIN k otevření aplikace v pracovním kontextu 
  - Řídit sdílení dat mezi aplikacemi 
  - Zabránit ukládání dat firemních aplikací do osobního úložiště


### <a name="supported-platforms-for-app-protection-policies"></a>Podporované platformy pro zásady ochrany aplikací
Podpora platforem pro zásady Intune app protection v souladu s podporou platforem pro mobilní aplikace Office pro zařízení s Androidem a iOS. Podrobnosti najdete v části **Mobilní aplikace** článku [Požadavky na systém pro Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

V současné době není dostupná podpora zařízení s Windows. Můžete ale použít Windows Information Protection, která nabízí podobné funkce. Podrobnosti najdete v tématu věnovanému [ochraně podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


## <a name="how-app-protection-policies-protect-app-data"></a>Jak zásady ochrany aplikací chrání data aplikací

#### <a name="apps-without-app-protection-policies"></a>Aplikace bez zásad ochrany aplikací

![Koncepčního obrázku pro přesun dat mezi aplikacemi se žádné zásady na místě](./media/apps-without-protection-policies.png)

Pokud se aplikace používají bez omezení, můžou se osobní a firemní data prolínat. Firemní data můžou být uložená v osobním úložišti nebo přenesená do aplikací mimo váš dosah, a může tím dojít ke ztrátě dat. Šipky v předchozím diagramu znázorňují neomezený přesun dat mezi firemními i osobními aplikacemi a do úložišť.


### <a name="data-protection-with-app-protection-policies"></a>Ochrana dat pomocí zásad ochrany aplikací

![Koncepčního obrázku, který zobrazuje firemní data chráněná zásadami](./media/apps-with-protection-policies.png)


Pomocí zásad ochrany aplikací můžete zabránit ukládání firemních dat do místního úložiště na zařízení. Můžete také zamezit přesunu dat do jiných aplikací, které nejsou chráněné zásadami ochrany aplikací. Mezi nastavení zásad ochrany aplikací patří:
- Zásady pro přemísťování dat, jako jsou **Zakázat možnost Uložit jako** a **Omezit vyjmutí, zkopírování a vložení**.
- Nastavení zásad přístupu, jako jsou **Vyžadovat pro přístup jednoduchý PIN kód** a **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Ochrana dat pomocí zásad ochrany aplikací na zařízeních spravovaných řešením Správa mobilních zařízení

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na vlastních zařízeních uživatelů (BYOD)](./media/app-protection-policies-with-mdm.png)

**Zařízení zaregistrovaná v řešení MDM**-

Předchozí obrázek znázorňuje vrstvy ochrany, které řešení MDM a zásady ochrany aplikací nabízejí společně.

Řešení MDM:

-   Zaregistruje zařízení.

-   Na zařízení nasadí aplikace.

-   Zajišťuje neustálé dodržování předpisů a správu zařízení.

**Zásady ochrany aplikací přidávají hodnotu tím, že dokážou:**

-   Chránit před únikem firemních dat v uživatelských aplikacích a službách

-   Používat v klientských aplikacích omezení jako *Uložit jako*, *schránka* nebo *PIN*

-   Vymazat firemní data z aplikací bez nutnosti tyto aplikace ze zařízení odebrat


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Ochrana dat pomocí zásad ochrany aplikací na neregistrovaných zařízeních

![Obrázek, který znázorňuje, jak zásady ochrany aplikací fungují na spravovaných zařízeních](./media/app-protection-policies-without-mdm.png)

Předchozí diagram znázorňuje, jak fungují zásady ochrany dat na úrovni aplikace bez správy mobilních zařízení MDM.

U vlastních zařízení uživatelů nezaregistrovaných do řešení MDM můžou zásady ochrany aplikací pomoci chránit firemní data na úrovni aplikace.
Je ale potřeba mít na paměti některá omezení, jako například:

-   Aplikace nejde do zařízení nasadit. Koncový uživatel musí aplikace sám nainstalovat.

-   V těchto zařízeních nejde zřídit profily certifikátů.

-   V těchto zařízeních nejde zřídit firemní Wi-Fi a nastavit VPN.

## <a name="app-protection-global-policy"></a>Globální zásada ochrany aplikací

Když správce OneDrivu přejde na web **admin.office.com** a vybere **Zařízení**, může nastavit ovládací prvky **správy mobilních aplikací** pro klientské aplikace OneDrivu a SharePointu. 

V tomto nastavení, které je přístupné na konzole pro správu OneDrivu, může nakonfigurovat speciální **globální** zásadu ochrany aplikací v Intune. Tato globální zásada se dá použít pro všechny uživatele v tenantovi, ale nedovoluje řídit adresování zásad. 

Jakmile ji zapnete, jsou aplikace OneDrivu a SharePointu pro iOS a Android automaticky chráněné vybraným nastavením. Odborník na IT může tuto zásadu upravit v konzole Intune, kde může přidat další cílové aplikace a změnit její nastavení. 

Implicitně smí existovat jenom jedna **globální** zásada pro tenanta. K vytvoření dalších globálních zásad pro tenanta je však možné použít [rozhraní Graph API v Intune](intune-graph-apis.md). Tento postup se ale nedoporučuje. Vytvoření dalších globálních zásad se nedoporučuje kvůli možným komplikacím při řešení potíží s implementací této zásady.

**Globální** zásada sice platí pro všechny uživatele v tenantovi, ale každá standardní zásada ochrany aplikací v Intune toto nastavení přepíše.


## <a name="multi-identity"></a>Víc identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když se aplikace použijí v pracovním kontextu.

Pro příklad osobní kontext, vezměte v úvahu uživatel, který spustí nový dokument ve Wordu, to je považovány za osobní kontext tak nepoužívají zásady ochrany aplikací Intune. Jakmile je uložený na firemním Onedrivu účtu pak bude za firemním a zásady ochrany aplikací Intune se použijí.

Příklad práci vezměte v úvahu uživatel spustí aplikaci OneDrive pomocí svého pracovního účtu. V pracovním kontextu nemůže přesunout soubory do svého osobního úložiště. Pokud ale později uživatel použije OneDrive se svým osobním účtem, může kopírovat a přesouvat data ze svého osobního OneDrivu bez omezení.

- Přečtěte si další informace o aplikacích, které podporují [MAM a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

## <a name="next-steps"></a>Další postup

[Jak vytvořit a nasadit zásady ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)

## <a name="see-also"></a>Viz také:
Aplikace jiných firem, například mobilní aplikace Salesforce, fungují s Intune specifickým způsobem, aby chránily podniková data. Další informace o tom, jak konkrétně aplikace Salesforce funguje s Intune (včetně nastavení konfigurace aplikace MDM), najdete v článku [Aplikace Salesforce a Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
