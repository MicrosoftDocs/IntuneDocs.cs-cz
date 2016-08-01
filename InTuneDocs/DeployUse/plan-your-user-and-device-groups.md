---
title: "Plánování skupin uživatelů a zařízení | Microsoft Intune"
description: "Naplánujte skupiny, tak aby to vyhovovalo organizačním potřebám."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: bb3e96ad4276819ad46ab2a5e1a8deb931bd421a


---

# Plánování skupin uživatelů a zařízení
Skupiny v Intune poskytují velmi flexibilní správu zařízení a uživatelů. Můžete nastavit skupin tak, aby odpovídaly potřebám vaší organizace podle těchto kritérií:

- Geografické umístění
- Oddělení
- Vlastnosti hardwaru
- Operační systém
- To, jestli je zařízení ve vlastnictví uživatele, nebo společnosti


## Jak fungují skupiny Intune


Výchozí zobrazení uzlu Skupiny v konzole pro správu Intune je následující:

![Snímek obrazovky s výchozím zobrazením uzlu Skupiny v konzole pro správu Intune](/intune/media/Intune_Planning_Groups_Default_small.png)

Do skupin se nasazují zásady, takže hierarchie skupin představuje jedno z klíčových rozhodnutí při návrhu. Je také důležité vědět, že po vytvoření skupiny se už nedá změnit její nadřazená skupina, takže návrh skupin má zásadní význam od první chvíle, kdy začnete používat službu Intune. Toto téma obsahuje popis některých doporučených postupů při návrhu hierarchie skupin na základě potřeb organizace.

## Pravidla členství ve skupinách

1. Skupina může obsahovat uživatele nebo zařízení, nemůže obsahovat oboje.

    * **Skupiny zařízení:** Sem patří počítače a mobilní zařízení. Před přidáním počítače do skupiny je potřeba ho zapsat. Než budete moct přidat mobilní zařízení do skupiny, musíte nakonfigurovat prostředí tak, aby podporovalo mobilní zařízení. Zařízení musí navíc být zapsaná nebo zjištěná protokolem Exchange ActiveSync.

    * **Skupiny uživatelů:** Skupina může obsahovat uživatele ze skupin zabezpečení. To jsou skupiny, které se synchronizují ze služby Active Directory. Pokud synchronizaci Active Directory nepoužíváte, můžete tyto skupiny vytvořit ručně.

2. Zařízení nebo uživatel může patřit do víc než jedné skupiny.

3. Skupina může zahrnout a vyloučit členy na základě následujících pravidel členství:

    * **Členství na základě kritérií:** Jedná se o dynamická pravidla, která Intune používá pro zahrnutí nebo vyloučení členů. Tato kritéria používají **skupiny zabezpečení** a další informace synchronizované z vaší místní služby Active Directory. Pokud se změní skupina zabezpečení nebo data, při synchronizaci se službou AD se změní i členství ve skupině.

    * **Přímé členství:** Jedná se o statická pravidla, která členy explicitně přidávají nebo vylučují. Seznam členství je statický.

4. K vytvoření skupin uživatelů nebo skupin zařízení obsahujících uživatele nebo počítače se služba Active Directory Domain Services (AD DS) nevyžaduje. Pokud ale mají skupiny zařízení obsahovat mobilní zařízení, musí být prostředí nakonfigurované pro podporu mobilních zařízení.

    Zařízení navíc musí být zjištěná a přidaná do Intune.

## Pravidla vztahů skupiny

1. Každá vytvořená skupina musí mít nadřazenou skupinu. Po vytvoření skupiny už nemůžete její nadřazenou skupinu změnit.

2. Přidávání uživatelů nebo zařízení do podřízené skupiny:

    * Podřízené skupiny jsou vždycky podskupinami nadřazené skupiny.

    * Noví členové přidaní do podřízené skupiny se automaticky přidají do příslušné nadřazené skupiny.

    * Pokud je člen vyloučený z nadřazené skupiny, nemůžete ho přidat do podřízené skupiny.

3. Členství v nadřazené skupině definuje dostupné členy pro podřízenou skupinu.

4. Pokud odstraníte nadřazenou skupinu, odstraní se všechny podřízené skupiny.

5. Obsah a zásady můžete nasadit na nadřazenou skupinu, i když je nasazení na podřízené skupiny vyloučené.

6. Do podřízené skupiny, která není členem nadřazené skupiny, můžete přidat konkrétního uživatele nebo zařízení. V takovém případě se nový člen skupiny přidá do nadřazené skupiny.

    Člena ale nemůžete přidat do podřízené skupiny, která je z nadřazené skupiny vyloučená.

7. Členství ve skupině je rekurzivní. Například:

    * **Jan** je členem jenom jedné skupiny, skupiny zabezpečení **Uživatelé přenosných počítačů** .

    * Skupina **Uživatelé přenosných počítačů** je členem skupiny zabezpečení **Schválení uživatelé** .

    * Vytvoříte v Intune skupinu, která používá dynamický dotaz na členství obsahující členy skupiny **Schválení uživatelé**. Výsledkem je, že vaše skupina uživatelů Intune zahrnuje uživatele **Jan**.

> [!TIP]
> Při vytváření skupin vezměte v úvahu, jak použijete zásady. Můžete mít třeba zásady specifické pro operační systémy zařízení a zásady specifické pro různé role ve vaší organizaci nebo pro organizační jednotky, které jste už v Active Directory definovali. Někdo považuje za užitečné používat skupiny zařízení specifické pro iOS, Android a Windows a skupiny uživatelů pro každou organizační roli.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Předdefinované skupiny
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
> Vaším mottem by měla být *jednoduchost*. Pokud vaše organizace nemá žádné specifické potřeby podobné těm, které jsou tu popsané, pro jednoduchost použijte výchozí strukturu skupin a zásady. To zajistí udržitelnější správu služby z dlouhodobého hlediska. Údržba bude jednodušší, pokud budete moct přistupovat ke všem uživatelům stejně a bez velkých rozdílů mezi skupinami, takže bude potřeba udržovat méně zásad.


### Všichni uživatelé a zařízení ve vaší organizaci
Definujte nadřazenou skupinu pro všechny uživatele a zařízení v organizaci, protože některé zásady budete chtít nejspíš uplatňovat pro všechny. K tomuto účelu můžete použít výchozí skupiny **Všichni uživatelé** a **Všechna zařízení** v Intune. Dílčí skupiny, které umožňují uspořádat zařízení podle konkrétních kritérií, třeba skupina zařízení využívajících model Přineste si vlastní zařízení (BYOD) a skupina zařízení ve vlastnictví společnosti, můžou být podřízenými položkami nadřazených skupin **Všichni uživatelé** a **Všechna zařízení**.

## Přizpůsobení skupin vaší organizaci

### Vlastní zařízení a zařízení ve vlastnictví firmy
Pokud vaše organizace umožňuje zaměstnancům používat v práci jejich vlastní zařízení (Přineste si vlastní zařízení – BYOD), poskytuje jim zařízení ve vlastnictví společnosti nebo používá kombinaci těchto typů zařízení, doporučujeme uplatňovat zásady na základě těchto dvou kategorií zařízení.

V případě modelu BYOD nebo kombinace zařízení zásady pečlivě naplánujte tak, aby neporušovaly místní předpisy na ochranu osobních údajů. Vytvořte nadřazenou skupinu pro všechny uživatele, kteří budou používat svoje vlastní zařízení. Tato skupina se potom dá použít k uplatnění zásad, které platí pro všechny uživatele v této kategorii.

![Snímek obrazovky při vytváření nadřazené skupiny BYOD](/intune/media/Intune_Planning_Groups_BYOD_small.png)

Podobně můžete vytvořit také skupinu pro uživatele zařízení ve vlastnictví společnosti:

![Snímek obrazovky skupin uživatelů na stejné úrovni – zařízení BYOD a zařízení ve vlastnictví společnosti](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Skupiny pro zeměpisné oblasti
Pokud vaše organizace potřebuje zásady pro konkrétní oblasti, můžete vytvořit skupiny založené na geografické oblasti. Můžete u nich vycházet z oblastních skupin, které už možná máte vytvořené ve službě AD (Active Directory), a synchronizovat je se službou Azure AD. Můžete je taky vytvořit přímo ve službě Azure AD.

Tyto snímky obrazovky ukazují, jak vytvořit skupiny Intune na základě skupin synchronizovaných z místní služby AD. Tento příklad vychází z předpokladu, že máte skupinu zabezpečení služby AD s názvem **Uživatelé v USA**.

1. Nejdřív zadejte obecné informace.

![Snímek obrazovky s oblastí Upravit skupinu](/intune/media/Intune_Planning_Groups_AD_General_small.png)

V části Kritéria členství vyberte skupinu **Uživatelé v USA** synchronizovanou ze služby AD jako skupinu zabezpečení, která se má použít v souladu s pravidly členství.

![Dialog Upravit skupinu](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Zkontrolujte zadané informace a dokončete vytváření skupiny výběrem možnosti **Dokončit**.

![Dialog Upravit skupinu](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

V našem příkladu jsme také vytvořili skupinu Střední východ a Asie.

> [!NOTE]
> Pokud se do části členství ve skupině automaticky nezadají informace na základě členství ve skupině zabezpečení, zkontrolujte, jestli jste těmto členům přiřadili licence služby Intune.

### Skupiny pro konkrétní hardware
Pokud vaše organizace potřebuje zásady, které se budou uplatňovat na konkrétní typy hardwaru, můžete vytvořit skupiny založené na tomto požadavku. Můžete při tom vycházet z konkrétních skupin, které už máte vytvořené v místní službě AD, a synchronizovat je se službou Azure AD. Můžete je taky vytvořit přímo ve službě Azure AD. V tomto příkladu používáme skupinu **Uživatelé v USA** jako nadřazenou skupinu skupiny **Uživatelé přenosných počítačů**.

![Dialog Vybrat skupinu zabezpečení](/intune/media/Intune_Planning_Groups_Laptop_small.png)

Teď by hierarchie skupin měla vypadat takto. Jak vidíte, skupina Intune **Uživatelé přenosných počítačů** teď obsahuje členy. Všechny zásady uplatněné na tuto skupinu se teď použijí na uživatele vlastních přenosných počítačů z oblasti USA.

![Zobrazení skupiny Uživatelé přenosných počítačů](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Skupiny pro konkrétní operační systémy
Pokud vaše organizace potřebuje zásady, které se budou uplatňovat na konkrétní operační systémy, třeba na Android, iOS nebo Windows, můžete vytvořit skupiny založené na tomto požadavku. Stejně jako v předchozích případech při tom můžete vycházet z konkrétních skupin podle operačních systémů, které už máte vytvořené v místní službě AD, a synchronizovat je se službou Azure AD. Můžete je taky vytvořit přímo ve službě Azure AD.

Pomocí stejného postupu jako v předchozích příkladech můžeme vytvořit skupiny založené na tom, že jejich členové <!--devices?--> používají konkrétní platformy operačních systémů.

> [!NOTE]
> Pokud máte uživatele, kteří používají různé mobilní platformy / operační systémy a nemáte automatizovaný způsob, jak je zařadit do kategorií uživatelů systému Android, iOS nebo Windows, promyslete si, jestli nebude lepší uplatňovat zásady na úrovni zařízení, což vám dá větší flexibilitu při uplatňování zásad pro konkrétní operační systémy.
>
> Dynamické zřizování skupin na základě operačního systému zařízení není možné. Tento krok se provádí pomocí skupin zabezpečení služby AD nebo AAD.

![Zobrazení skupiny Uživatelé přenosných počítačů](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Po zaplnění všech skupin uživatelů na základě požadavků organizace by vaše hierarchie skupin měla vypadat přibližně takto:

![Zobrazení hierarchie skupin](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Tato hierarchie se dá použít k uplatňování příslušných zásad organizace.

### skupiny zařízení.
Podobné skupiny můžete vytvořit také pro zařízení, jak ukazuje následující příklad. V případě modelu BYOD (Přineste si vlastní zařízení) začněte velkou skupinou zahrnující všechna zařízení ve vlastnictví zaměstnanců:

![Dialog Vytvořit skupinu](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Nezapomeňte vybrat možnost **Všechna zařízení (počítače a mobilní zařízení)**, aby skupina obsahovala všechna vlastní zařízení zaměstnanců:

![Stránka Definovat kritéria členství](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Zkontrolujte zadané informace a vytvořte skupinu BYOD výběrem možnosti **Dokončit**.

![Dialog Vytvořit skupinu](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Pokračujte ve vytváření skupin zařízení, dokud nebudete mít hierarchii skupin zařízení podobnou hierarchii skupin uživatelů. Uzel skupin v konzole Intune by se měl podobat tomuto příkladu:

![Zobrazení hierarchie skupin v Intune](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Hierarchie skupin a konvence pojmenování
V zájmu snazší správy zásad doporučujeme pojmenovat každou zásadu podle účelu, platformy a rozsahu jejího uplatnění. Toto standardní pojmenování by mělo vycházet ze struktury skupin, kterou jste vytvořili při přípravě na uplatnění zásad.

Třeba zásada pro systém Android, která se uplatňuje na všechna firemní mobilní zařízení s Androidem v oblasti USA, může mít název **CO_US_Mob_Android_General**.

![Vytvoření zásady pro Android](/intune/media/Intune_planning_policy_android_small.png)

Pokud zásady pojmenujete tímto způsobem, budete je moct snadno identifikovat a zjistit jejich účel a rozsah přímo z uzlu zásad v konzole, jak ukazuje tento příklad:

![Seznam zásad Intune](/intune/media/Intune_planning_policy_view_small.png)

## Další kroky
[Vytváření skupin](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


