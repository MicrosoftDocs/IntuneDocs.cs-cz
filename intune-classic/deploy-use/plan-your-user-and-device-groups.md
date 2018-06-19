---
title: Plánování skupin uživatelů a zařízení
description: Naplánujte skupiny tak, aby to vyhovovalo potřebám vaší organizace.
keywords: ''
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 679399f306f3837a010cc01799c7567c1e5b5b39
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025310"
---
# <a name="plan-your-user-and-device-groups"></a>Plánování skupin uživatelů a zařízení

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Skupiny v Intune poskytují při správě zařízení a uživatelů velkou flexibilitu. Můžete nastavit skupin tak, aby odpovídaly potřebám vaší organizace podle těchto kritérií:

- Geografické umístění
- Oddělení
- Vlastnosti hardwaru
- Operační systém
- To, jestli je zařízení ve vlastnictví uživatele, nebo společnosti


## <a name="how-intune-groups-work"></a>Jak fungují skupiny Intune


Toto je výchozí zobrazení uzlu **Skupiny** v konzole pro správu Intune:

![Snímek obrazovky s výchozím zobrazením uzlu Skupiny v konzole pro správu Intune](../media/Intune_Planning_Groups_Default_small.png)

Zásady se nasazují do skupin, takže hierarchie skupin představuje jedno z klíčových rozhodnutí při návrhu. Je důležité pamatovat na to, že po vytvoření skupiny už nebude možné změnit její nadřazenou skupinu. Způsob návrhu skupin má zásadní význam od první chvíle, kdy začnete používat službu Intune. Toto téma obsahuje popis některých doporučených postupů při návrhu hierarchie skupin na základě potřeb organizace.

## <a name="group-membership-rules"></a>Pravidla členství ve skupinách

- Skupina může obsahovat uživatele nebo zařízení, nemůže obsahovat oboje.

    * **Skupiny zařízení**. Sem patří počítače a mobilní zařízení. Před přidáním počítače do skupiny je potřeba ho zapsat. Než budete moct přidat mobilní zařízení do skupiny, musíte nakonfigurovat prostředí tak, aby podporovalo mobilní zařízení. Zařízení musí navíc být zapsaná nebo zjištěná protokolem Exchange ActiveSync.

    * **Skupiny uživatelů**. Skupina může mít uživatele ze skupin zabezpečení. Skupiny zabezpečení se synchronizují se službou Active Directory. Pokud synchronizaci Active Directory nepoužíváte, můžete tyto skupiny vytvořit ručně.

- Zařízení nebo uživatel může patřit do víc než jedné skupiny.

- Skupina může zahrnout a vyloučit členy na základě následujících pravidel členství:

    * **Členství na základě kritérií**. Jedná se o dynamická pravidla, která Intune používá pro zahrnutí nebo vyloučení členů. Tato kritéria používají skupiny zabezpečení a další informace synchronizované z vaší místní služby Active Directory. Pokud se změní skupina zabezpečení nebo data, při synchronizaci se službou Active Directory se změní i členství ve skupině.

    * **Přímé členství**. Jedná se o statická pravidla, která členy explicitně přidávají nebo vylučují. Seznam členství je statický.

-   K vytvoření skupin uživatelů nebo skupin zařízení obsahujících uživatele nebo počítače se služba Active Directory Domain Services (AD DS) nevyžaduje. Pokud ale mají skupiny zařízení obsahovat mobilní zařízení, musí být prostředí nakonfigurované pro podporu mobilních zařízení.

    Zařízení navíc musí být zjištěná a přidaná do Intune.

## <a name="group-relationship-rules"></a>Pravidla vztahů skupiny

- Každá vytvořená skupina musí mít nadřazenou skupinu. Po vytvoření skupiny už nebude možné změnit její nadřazenou skupinu.

- Přidávání uživatelů nebo zařízení do podřízené skupiny:

    * Podřízená skupina je vždy podskupinou nadřazené skupiny.

    * Noví členové přidaní do podřízené skupiny se automaticky přidají do příslušné nadřazené skupiny.

    * Pokud je člen vyloučený z nadřazené skupiny, nemůžete ho přidat do podřízené skupiny.

- Členství v nadřazené skupině definuje dostupné členy pro podřízenou skupinu.

- Pokud odstraníte nadřazenou skupinu, odstraní se všechny podřízené skupiny.

- Obsah a zásady můžete nasadit na nadřazenou skupinu a současně vyloučit nasazení na její podřízené skupiny.

- Konkrétního uživatele nebo zařízení můžete přidat do podřízené skupiny, pokud už není členem nadřazené skupiny. V takovém případě se nový člen skupiny přidá do nadřazené skupiny.

    Člena ale nemůžete přidat do podřízené skupiny, pokud je vyloučený z nadřazené skupiny.

- Členství ve skupině je rekurzivní. Příklad:

    * **Jan** je členem jenom jedné skupiny, skupiny zabezpečení **Uživatelé přenosných počítačů** .

    * Skupina **Uživatelé přenosných počítačů** je členem skupiny zabezpečení **Schválení uživatelé** .

    * Vytvoříte v Intune skupinu, která používá dynamický dotaz na členství obsahující členy skupiny **Schválení uživatelé**. Výsledkem je, že vaše skupina uživatelů Intune zahrnuje uživatele **Jan**.

> [!TIP]
> Při vytváření skupin vezměte v úvahu, jak budete zásady používat. Například můžete mít zásady specifické pro operační systémy zařízení nebo pro různé role či organizační jednotky, které už máte definované ve službě Active Directory. Někteří správci považují za užitečné vytvářet skupiny zařízení pro iOS, Android a Windows. Samozřejmě jako doplněk skupin uživatelů pro každou organizační roli.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Předdefinované skupiny
Intune poskytuje devět předdefinovaných skupin, které se nedají upravit ani odstranit: <!--maybe a screen shot would be best?-->

-   **Všichni uživatelé**
    -   Neseskupení uživatelé
-   **Všechna zařízení**
    -   Všechny počítače
    -   Všechna mobilní zařízení
        -   Všechna přímo spravovaná zařízení
        -   Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync
    -   Všechna zařízení vlastněná společností
    -   Neseskupená zařízení

> [!NOTE]
> Vaším mottem by měla být *jednoduchost*. Pokud vaše organizace nemá žádné specifické potřeby podobné těm, které jsou popsané v dalších částech, pro jednoduchost použijte výchozí strukturu skupin a zásad. To zajistí z dlouhodobého hlediska udržitelnější správu služby. Správa bude jednodušší, pokud budete moci s uživateli pracovat jednotně. S menším rozlišováním podle skupin budete mít k udržování méně zásad.


### <a name="all-users-and-devices-in-your-organization"></a>Všichni uživatelé a zařízení ve vaší organizaci
Definujte nadřazenou skupinu všech uživatelů a zařízení ve vaší organizaci. Pravděpodobně budete mít některé zásady, které se budou vztahovat na všechny. K tomuto účelu můžete v Intune použít výchozí skupiny **Všichni uživatelé** a **Všechna zařízení**. Podřízenými položkami nadřazených skupin **Všichni uživatelé** a **Všechna zařízení** můžou být podskupiny, které umožňují uspořádat zařízení podle konkrétních kritérií, třeba skupina zařízení využívajících model Přineste si vlastní zařízení (BYOD) a skupina zařízení ve vlastnictví společnosti.

## <a name="customize-groups-for-your-organization"></a>Přizpůsobení skupin vaší organizaci

### <a name="byod-and-corporate-owned-devices"></a>Vlastní zařízení a zařízení ve vlastnictví firmy
Pokud vaše organizace umožňuje zaměstnancům používat v práci jejich vlastní zařízení, poskytuje jim zařízení ve vlastnictví společnosti nebo používá kombinaci těchto přístupů, doporučujeme uplatňovat zásady na základě těchto kategorií zařízení odděleně.

V případě modelu BYOD nebo kombinace zařízení zásady pečlivě naplánujte tak, aby neporušovaly místní předpisy na ochranu osobních údajů. Vytvořte nadřazenou skupinu pro všechny uživatele, kteří budou používat svoje vlastní zařízení. Tuto skupinu pak můžete použít k uplatnění zásad, které platí pro všechny uživatele v této kategorii.

![Vytvoření nadřazené skupiny BYOD](../media/Intune_Planning_Groups_BYOD_small.png)

Podobně můžete vytvořit skupinu pro uživatele se zařízeními ve vlastnictví společnosti:

![Skupiny uživatelů na stejné úrovni – zařízení BYOD a zařízení ve vlastnictví společnosti](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Skupiny pro zeměpisné oblasti
Pokud vaše organizace potřebuje různé zásady podle oblastí, můžete vytvořit skupiny založené na geografické oblasti. Můžete pro ně použít oblastních skupiny, které už možná máte vytvořené ve službě Active Directory, a synchronizovat je se službou Azure Active Directory. Oblastní skupiny můžete také vytvořit přímo v Azure Active Directory.

Následující snímky obrazovky ukazují, jak vytvořit skupiny Intune na základě skupin synchronizovaných z místní služby Active Directory. Tento příklad vychází z předpokladu, že máte skupinu zabezpečení služby Active Directory s názvem **US Users Group** (Uživatelé v USA).

Nejdřív zadejte obecné informace.

![Snímek obrazovky s oblastí Upravit skupinu](../media/Intune_Planning_Groups_AD_General_small.png)

V části **Kritéria členství** vyberte skupinu **US Users Group** synchronizovanou ze služby AD jako skupinu zabezpečení, která se má použít v souladu s pravidly členství.

![Snímek obrazovky s dialogovým oknem Upravit skupinu](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Zkontrolujte zadané informace a dokončete vytváření skupiny výběrem možnosti **Dokončit**.

![Snímek obrazovky s dialogovým oknem Upravit skupinu](../media/Intune_Planning_Groups_AD_Summary_small.png)

V našem příkladu jsme také vytvořili skupinu **MEA** pro Střední východ a Asii.

> [!NOTE]
> Pokud se do části členství ve skupině automaticky nezadají informace na základě členství ve skupině zabezpečení, zkontrolujte, jestli jste těmto členům přiřadili licence služby Intune.

### <a name="groups-for-specific-hardware"></a>Skupiny pro konkrétní hardware
Pokud vaše organizace potřebuje zásady, které se budou uplatňovat na konkrétní typy hardwaru, můžete vytvořit skupiny založené na tomto požadavku. Zásady můžete založit na konkrétních skupinách, které už možná máte vytvořené v místní službě Active Directory, a synchronizovat je se službou Azure Active Directory. Skupiny podle oblastí můžete také vytvořit přímo v Azure Active Directory. V tomto příkladu používáme skupinu **US User Group** jako nadřazenou pro skupinu **Laptop Users** (Uživatelé přenosných počítačů).

![Dialog Vybrat skupinu zabezpečení](../media/Intune_Planning_Groups_Laptop_small.png)

Dosud vytvořená hierarchie skupin by měla odpovídat následujícímu snímku obrazovky. Jak vidíte, skupina Intune **Laptop Users** (Uživatelé přenosných počítačů) teď obsahuje členy. Všechny zásady uplatněné na tuto skupinu se použijí na uživatele vlastních přenosných počítačů z oblasti USA.

![Zobrazení skupiny Uživatelé přenosných počítačů](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Skupiny pro konkrétní operační systémy
Pokud vaše organizace potřebuje zásady, které se budou uplatňovat na konkrétní operační systémy, třeba na Android, iOS nebo Windows, můžete vytvořit skupiny založené na tomto požadavku. Jako v předchozích příkladech můžete zásady založit na konkrétních skupinách, které už možná máte vytvořené v místní službě Active Directory, a synchronizovat je se službou Azure Active Directory. Můžete je také vytvořit přímo ve vaší instanci Azure Active Directory.

Použitím stejného postupu jako v předchozích příkladech můžete vytvořit skupiny založené na uživatelích <!--devices?-->, kteří používají konkrétní platformy operačních systémů.

> [!NOTE]
> Pokud máte uživatele, kteří používají různé mobilní platformy nebo operační systémy a nemáte automatizovaný způsob, jak je zařadit do kategorií uživatelů systému Android, iOS nebo Windows, promyslete si, jestli nebude lepší uplatňovat zásady na úrovni zařízení. To vám dá větší flexibilitu při uplatňování zásad pro konkrétní operační systémy.
>
> Dynamické zřizování skupin na základě operačního systému zařízení není možné. Místo toho použijte skupiny zabezpečení Active Directory nebo Azure Active Directory.

![Skupina Laptop Users (Uživatelé přenosných počítačů)](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Po zaplnění všech skupin uživatelů na základě požadavků organizace by vaše hierarchie skupin měla vypadat přibližně takto:

![Zobrazení hierarchie skupin](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Tuto hierarchii můžete použít k uplatňování zásad vaší organizace.

### <a name="device-groups"></a>Skupiny zařízení
Podobné skupiny můžete vytvořit také pro zařízení, jak ukazuje následující příklad. V případě modelu BYOD (Přineste si vlastní zařízení) začněte velkou skupinou zahrnující všechna zařízení ve vlastnictví zaměstnanců.

![Dialog Vytvořit skupinu](../media/Intune_Planning_Groups_Device_General_small.png)

Nezapomeňte vybrat možnost **Všechna zařízení (počítače a mobilní zařízení)**, aby skupina obsahovala všechna vlastní zařízení zaměstnanců:

![Stránka Definovat kritéria členství](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Zkontrolujte zadané informace a dokončete vytváření skupiny výběrem možnosti **Dokončit**.

![Dialog Vytvořit skupinu](../media/Intune_Planning_Groups_Device_Summary_small.png)

Pokračujte ve vytváření skupin zařízení, dokud nebudete mít hierarchii skupin zařízení podobnou hierarchii skupin uživatelů. Uzel skupiny v konzole Intune se bude podobat tomuto příkladu:

![Zobrazení hierarchie skupin v Intune](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Hierarchie skupin a konvence pojmenování
V zájmu snazší správy zásad doporučujeme pojmenovat každou zásadu podle účelu, platformy a rozsahu jejího uplatnění. Použijte systém pojmenování vycházející ze struktury skupin, které jste vytvořili při přípravě zásad.

Třeba zásada pro systém Android, která se uplatňuje na všechna firemní mobilní zařízení s Androidem v oblasti USA, může mít název **CO_US_Mob_Android_General**.

![Vytvoření zásady pro Android](../media/Intune_planning_policy_android_small.png)

Když zásady pojmenujete tímto způsobem, budete je moct snadno identifikovat a zjistit jejich účel a rozsah přímo z uzlu **Zásady** v konzole, například takto:

![Seznam zásad Intune](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Další kroky
[Vytváření skupin](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
