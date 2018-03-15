---
title: "Přidání aplikací do Microsoft Intune"
titlesuffix: 
description: "Zjistěte, jak přidat aplikace do Microsoft Intune, aby je bylo možné přiřadit uživatelům a zařízením. Intune podporuje širokou škálu různých typů aplikací."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91762eafbba5f96ce04f3ffd4d83f63434a3ac74
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Přidání aplikací do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. Intune podporuje širokou škálu různých typů aplikací. Dostupné možnosti se pro jednotlivé typy aplikací liší.

Intune umožňuje přidat a přiřadit tyto typy aplikací:
| Typ aplikace                                  | Instalace                                                                  | Updates                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Aplikace na webu                           | Intune vytvoří zástupce webové aplikace na domovské obrazovce zařízení.          | Aktualizace aplikací jsou automatické.     |
| Interně napsané aplikace (obchodní)  | Intune nainstaluje aplikaci na zařízení (vy dodáte instalační soubor).    | Aplikaci musíte aktualizovat sami.       |
| Aplikace ze Storu                       | Intune nainstaluje aplikaci na zařízení.                                       | Aktualizace aplikací jsou automatické.     |
| Aplikace, které jsou integrované                        | Intune nainstaluje aplikaci na zařízení.                                       | Aktualizace aplikací jsou automatické.     |


Kromě webových aplikací Intune podporuje následující konkrétní platformy pro aplikace ze Storu a obchodní aplikace:
- Aplikace ze Storu
    - Aplikace pro Android Store
    - Aplikace pro iOS Store
    - Aplikace pro Windows Phone 8.1 Store
    - Aplikace pro Windows Store
    - Aplikace pro Android for Work
    - Aplikace Office 365 pro Windows
    - Aplikace Office 365 pro macOS
- Vytvoření vlastní aplikace – obchodní aplikace (LOB)
    - Obchodní aplikace (LOB) pro Android
    - Obchodní aplikace (LOB) pro iOS
    - Obchodní aplikace (LOB) pro Windows Phone (soubory .xap)
    - Obchodní aplikace (LOB) pro Windows (pouze soubory .msi)
- Integrované aplikace    

>[!TIP]
> Obchodní aplikace (LOB) je aplikace, kterou přidáte z instalačního souboru aplikace. Když například chcete nainstalovat obchodní aplikaci iOS, přidáte aplikaci tak, že jako **Typ aplikace** v okně **Přidat aplikaci** vyberete **Obchodní aplikace**. Potom vyberte soubor balíčku aplikace (má příponu .ipa). Tyto typy aplikací obvykle vznikají interně.

## <a name="assess-application-requirements"></a>Vyhodnocení požadavků na aplikace 
Jako správce IT musíte nejen určit, které aplikace vaše skupina musí používat, ale musíte také určit potřeby jednotlivých skupin a podskupin. U každé aplikace musíte určit vhodnou platformu, skupiny uživatelů, které aplikaci potřebují, zásady konfigurace, které se mají použít u těchto skupin uživatelů, a zásady ochrany, které se mají použít.  

Dále musíte určit, zda je třeba zaměřit na správu mobilních zařízení (MDM) nebo zda bude dostačující správa mobilních aplikací (MAM). Správa zařízení (správa mobilních zařízení) přes Intune je užitečná v těchto případech:
- Uživatelé potřebují Wi-Fi nebo firemní připojení k síti VPN, aby mohli vykonávat svoji práci.
- Uživatelé potřebují sadu aplikací, které se na jejich zařízení budou doručovat bez vyžádání.
- Vaše organizace musí dodržovat zákonné nebo jiné zásady, které vyžadují konkrétní řídicí mechanismy správy mobilních zařízení (MDM), jako je zabezpečení nebo šifrování.

Správa aplikací (správa mobilních aplikací) přes Intune bez správy zařízení je užitečná v těchto případech:
- Uživatelům chcete povolit používání vlastních zařízení (BYOD).
- Místo průběžných upozornění na zařízení chcete uživatelům jednorázově zobrazit automatické sdělení, že jste zavedli ochranu MAM.
- Chcete zajistit soulad se zásadami, které vyžadují méně funkcí pro správu na osobních zařízeních. Chcete například spravovat firemní data u aplikací, ale nechcete je spravovat na celém zařízení.

Další informace najdete v tématu [Porovnání správy mobilních zařízení (MDM) a správy mobilních aplikací (MAM)](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Určení, kdo bude používat aplikaci
Po přidání aplikace do Intune přiřadíte skupinu uživatelů, která bude danou aplikaci používat. Nejprve na základě citlivosti dat obsažených v aplikaci musíte určit příslušnou skupinu, která bude mít k aplikaci přístup. Je možné, že budete muset zahrnout nebo vyloučit určité typy rolí v rámci organizace. Pro vaši prodejní skupinu se například můžou vyžadovat jenom některé obchodní aplikace, ale lidé z technického, finančního, personálního nebo právního oddělení obchodní aplikaci používat nemusí. Dále vaše prodejní skupina může na svých mobilních zařízeních potřebovat další ochranu dat a přístup k interním firemním službám. Musíte určit, jak se tato skupina bude přes aplikaci připojovat k prostředkům. Budou se data, ke kterým má aplikace přístup, uchovávat v cloudu, nebo místně? Musíte také promyslet, jak se uživatelé budou přes aplikaci připojovat k prostředkům. Intune podporuje také povolení přístupu k mobilním aplikacím, které vyžadují zabezpečený přístup k místním datům, třeba serverům obchodních aplikací. Tento typ přístupu se obvykle zajišťuje pomocí [certifikátů spravovaných službou Intune](certificates-configure.md) pro řízení přístupu v kombinaci se standardní bránou sítě VPN nebo proxy serverem v hraniční síti, například Microsoft Azure Active Directory Application Proxy. [Nástroj App Wrapping Tool a sada App SDK](apps-prepare-mobile-application-management.md) v Intune můžou pomoct zajistit, aby šlo firemní data využívat jenom v rámci dané podnikové aplikace a nešlo je předat zákaznickým aplikacím nebo službám.

S určením, jak máte identifikovat organizační skupiny pro jednotlivé scénáře použití a dílčí použití, vám pomůže [Průvodce plánováním nasazení, návrhem a implementací Intune](planning-guide.md). Podrobnosti o přiřazení aplikací ke skupinám najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md). 

### <a name="determine-the-type-of-app-for-your-solution"></a>Určení typu aplikace pro konkrétní řešení
Můžete si vybrat mezi následujícími typy aplikací:
- **Aplikace na webu** – webová aplikace představuje aplikaci klient-server. Server poskytuje webovou aplikaci, která zahrnuje uživatelské rozhraní, obsah a funkce. Moderní webové hostingové platformy dále běžně nabízejí zabezpečení, vyrovnávání zatížení a další výhody. Tento typ aplikace se samostatně udržuje na webu. Na tento typ aplikace se odkazuje pomocí Intune. Můžete také určit, které skupiny uživatelů mají k této aplikaci přístup. Všimněte si, že Android webové aplikace nepodporuje.
- **Interně napsané aplikace (obchodní)** – aplikace vytvořené interně se nazývají obchodní aplikace (LOB). Funkce tohoto typu aplikace se vytvářejí pro některou z platforem podporovaných Intune, například pro Windows, iOS nebo Android. Vaše organizace vytvoří a poskytuje aktualizace jako samostatný soubor. Aktualizace aplikace poskytujete uživatelům tak, že přidáte a nasadíte aktualizace přes Intune. 
- **Aplikace ze Storu** – aplikace pro Store je aplikace, která je nahraná ve Windows Storu, obchodu pro iOS nebo Android. Poskytovatel aplikace pro Store udržuje a poskytuje aktualizace aplikace. Aplikaci si vyberete v seznamu ve Storu a přidáte ji pomocí Intune jako aplikaci dostupnou pro vaše uživatele.

Při určování potřebných aplikací pro vaši organizaci zvažte, jak se tyto aplikace integrují s cloudovými službami, k jakým datům mají aplikace přístup, zda jsou aplikace dostupné pro uživatele, kteří používají vlastní zařízení (BYOD), a zda aplikace vyžadují přístup k internetu.

Další informace o určení typu aplikací, které vaše organizace potřebuje, najdete v části **Aplikace** v oddílu **Funkční požadavky** článku [Vytvoření návrhu](planning-guide-design.md#feature-requirements).

### <a name="understanding-app-management-and-protection-policies"></a>Principy zásad ochrany a správy aplikací
Intune vám umožňuje upravit funkce nasazovaných aplikací tak, aby byly v souladu se zásadami dodržování předpisů a zabezpečení vaší společnosti. Tento řídicí mechanismus vám umožňuje určit, jak jsou data vaší společnosti chráněná. Aplikace spravované přes Intune jsou povolené s bohatou sadou zásad ochrany mobilních aplikací, jako jsou:

- Omezení funkcí kopírování a uložení a uložení jako
- Konfigurace webových odkazů pro otevírání v aplikaci Intune Managed Browser
- Povolení použití více identit a podmíněného přístupu na úrovni aplikace

Aplikace spravované přes Intune můžou také povolit ochranu aplikací bez nutnosti registrace, čímž vám umožňují použít zásady ochrany před únikem informací bez správy uživatelských zařízení. Pomocí sady App SDK (App Software Development Kit) a nástroje App Wrapping Tool služby Intune můžete dále do mobilních a obchodních aplikací začlenit i správu firemních mobilních aplikací. Další informace o těchto nástrojích najdete v článku [Přehled sady Intune App SDK](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Princip licencovaných aplikací
Kromě webových aplikací, aplikací pro Store a obchodních aplikací byste měli také něco vědět o cíli aplikací programu Volume Purchase Program a licencovaných aplikací, jako jsou:     
- **Apple Volume Purchasing Program for Business (iOS a MacOS)** – App Store pro iOS umožňuje pro aplikace, které chcete používat ve vaší společnosti, nakoupit více licencí. Zakoupením více kopií můžete efektivně spravovat aplikace ve vaší společnosti. Další informace najdete v článku [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu](vpp-apps-ios.md).
- **Android for Work (Android)** – zařízením s Androidem for Work se aplikace přiřazují jiným způsobem než zařízením se standardním Androidem. Všechny aplikace, které instalujete pro Android for Work, pocházejí z obchodu Google Play for Work. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace a schválíte je. Aplikace se pak objeví v uzlu Licencované aplikace na portálu Azure Portal. Odsud můžete přiřazení aplikace spravovat stejným způsobem, jakým byste přiřadili jakoukoli jinou aplikaci.
- **Windows Store pro firmy (Windows 10)** – Microsoft Store pro firmy je místo, kde můžete najít a zakoupit aplikace pro svou organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete hromadně zakoupené aplikace spravovat z Azure Portalu. Další informace najdete v článku [Správa aplikací zakoupených v Microsoft Storu pro firmy](windows-store-for-business.md). 

## <a name="before-you-start"></a>Než začnete
Než začnete aplikace přidávat a přiřazovat, zvažte následující body.

- Pokud chcete přidat a přiřadit aplikaci z obchodu, musí mít koncoví uživatelé u tohoto obchodu zřízený účet, aby si aplikaci mohli nainstalovat.
- Některé aplikace nebo položky, které přiřadíte, můžou záviset na integrovaných aplikacích pro iOS. Pokud třeba přiřadíte knihu z obchodu pro iOS, musí být v zařízení aplikace iBooks. Pokud jste integrovanou aplikaci iBooks odebrali, nemůžete ji pomocí Intune obnovit.

## <a name="cloud-storage-space"></a>prostor v cloudovém úložišti
Všechny aplikace, které vytváříte pomocí instalace typu Instalační program softwaru (například obchodní aplikace), se zabalí a nahrají do cloudového úložiště Intune. Zkušební předplatné Intune zahrnuje 2 gigabajty (GB) cloudového úložiště, které se používá k ukládání spravovaných aplikací a aktualizací. Úplné předplatné zahrnuje 20 GB úložného prostoru.

Další úložiště pro Intune můžete zakoupit stejným způsobem jako u původního nákupu.  Pokud jste platili fakturou nebo platební kartou, navštivte [portál pro správu předplatných](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Jinak kontaktujte svého partnera nebo prodejního zástupce.

Požadavky na cloudové úložiště jsou následující:

-   Všechny instalační soubory musí být umístěné stejné složce.
-   Maximální velikost kteréhokoli nahraného souboru je 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak vytvořit a upravit kategorie pro aplikace

Když aplikace seřadíte do kategorií, uživatelé je jednodušeji najdou na portálu společnosti. K aplikaci můžete přiřadit jednu kategorii i více, například **Aplikace pro vývojáře** nebo **Aplikace pro komunikaci**.
Když přidáte aplikaci do Intune, budete mít možnost vybrat požadovanou kategorii. Informace k přidání aplikací a přiřazení kategorií získáte v tématech pro jednotlivé platformy. Pokud chcete vytvořit a upravit vlastní kategorie, postupujte podle následujících pokynů:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Kategorie aplikací**.
5. V okně **Kategorie aplikací** se zobrazí seznam aktuálních kategorií. Vyberte jednu z následujících akcí:
    - **Vytvořit kategorii**: Výběrem možnosti **Přidat** zobrazte okno **Vytvořit kategorii** a potom přidejte název nové kategorie. Názvy je možné zadat jenom v jednom jazyce a služba Intune je nepřekládá. Až skončíte, klikněte na **Vytvořit**.
    - **Upravit kategorii**: Pro jakoukoliv kategorii v seznamu, zvolte tlačítko se třemi tečkami (**...**). Tato možnost zobrazí místní nabídku, která vám umožní kategorii **připnout na řídicí panel** nebo **odstranit**.

## <a name="apps-added-automatically-by-intune"></a>Aplikace přidaní automaticky službou Intune

Dříve služba Intune obsahovala řadu integrovaných aplikací, které jste mohli rychle přiřadit. Na základě vaší zpětné vazby jsme tento seznam odebrali a integrované aplikace už neuvidíte.
Pokud jste už ale nějaké integrované aplikace přiřadili, budou se v seznamu aplikací dál zobrazovat. Tyto aplikace můžete dál přiřazovat podle potřeby.
V pozdější verzi plánujeme přidat jednodušší způsob výběru a přiřazování integrovaných aplikací z Azure Portalu.

## <a name="next-steps"></a>Další kroky

Informace o tom, jak do Intune přidat aplikace pro jednotlivé platformy, najdete v příslušných tématech:

- [Aplikace pro Android Store](store-apps-android.md)
- [Obchodní aplikace pro Android](lob-apps-android.md)
- [Aplikace pro iOS Store](store-apps-ios.md)
- [Obchodní aplikace pro iOS](lob-apps-ios.md)
- [Webové aplikace (pro všechny platformy)](web-app.md)
- [Aplikace pro Windows Phone 8.1 Store](store-apps-windows-phone-8-1.md)
- [Obchodní aplikace pro Windows Phone](lob-apps-windows-phone.md)
- [Aplikace pro Windows Store](store-apps-windows.md)
- [Obchodní aplikace pro Windows](lob-apps-windows.md)
- [Aplikace Office 365 pro Windows 10](apps-add-office365.md)
- [Integrované aplikace](apps-add-built-in.md)

