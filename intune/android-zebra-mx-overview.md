---
title: Zebra Mobility rozšíření použít na zařízeních s Androidem v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Pomocí Microsoft Intune spravovat a využívat Zebra zařízení s Androidem s Zebra Mobility rozšíření (MX). Zobrazíte všechny kroky, včetně nainstalovat aplikaci portál společnosti, zkušebně načtené aplikace, přiřazení role Správce zařízení, vytvořte profil StageNow a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2734247569245794bce7fe1de68c8b20c6091f
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490600"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Použití a správa zařízení Zebra s příponami Zebra nastavení mobilních zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune obsahuje bohatou sadu funkcí, včetně správy aplikací a konfigurace nastavení zařízení. Tyto integrované funkce a nastavení se používají ke správě zařízení s Androidem, které pocházejí od Zebra technologií, označované také jako "Zebra zařízení".

Pokud chcete upravit nebo přidat další nastavení specifická pro Zebra, můžete použít také Zebra **Mobility rozšíření (MX)** na těchto zařízeních. 

Tato funkce platí pro:

- Android

Vaše společnost může pomocí Zebra zařízení pro maloobchodní prodej ve výrobním závodě a další. Například jste prodejce a vaše prostředí zahrnuje tisíce Zebra mobilních zařízení používaných prodejcům. Intune může pomoct spravovat tato zařízení jako součást řešení správy mobilních zařízení.

Pomocí Intune, můžou zapsat zařízení Zebra nasazení z obchodních aplikací do zařízení. "Konfigurace zařízení" profily vám umožňují vytvořit profily MX a spravovat Zebra konkrétní nastavení.

Tento článek ukazuje, jak použít rozšíření Mobility Zebra (MX) na Zebra zařízení v Microsoft Intune.

## <a name="before-you-begin"></a>Před zahájením

- Ujistěte se, že máte nejnovější verzi aplikace klasické pracovní plochy StageNow z Zebra technologie.
- Nezapomeňte se podívat [Zebra na úplný přehled funkcí MX](http://techdocs.zebra.com/mx/compatibility) (otevře web společnosti Zebra) pro potvrzení, můžete vytvořit profily jsou kompatibilní s MX verzi, verze operačního systému a model zařízení.
- Určitá zařízení, jako jsou 25. ledna TC20, nepodporují všechny dostupné funkce MX v StageNow. Nezapomeňte se podívat [přehled funkcí pro Zebra](http://techdocs.zebra.com/mx/tc2x/) (otevře web společnosti Zebra) pro podporu aktualizované informace.

## <a name="step-1-install-the-latest-company-portal-app"></a>Krok 1: Nainstalujte nejnovější aplikaci portál společnosti

Na zařízení přejděte do obchodu Google Play a stáhnout a nainstalovat aplikaci portál společnosti Intune od Microsoftu. Při instalaci z Google Play, získá aktualizace aplikace portál společnosti a automaticky opraví.

Pokud není k dispozici Google Play, stáhnout [portál společnosti Microsoft Intune pro Android](https://www.microsoft.com/download/details.aspx?id=49140) (otevře jiný web společnosti Microsoft), a [zkušebně načíst ji](#sideload-the-company-portal-app) (v tomto článku). Při instalaci tímto způsobem, aplikace nebude dostávat aktualizace nebo opravy automaticky. By měl pravidelně aktualizovat a opravovat aplikaci ručně.

### <a name="sideload-the-company-portal-app"></a>Zkušebně načtené aplikace portál společnosti

"Zkušební načtení před prodejem" je, když nepoužíváte k instalaci aplikace Google Play. Pokud chcete zkušebně načtené aplikace portál společnosti použijte StageNow. 

Následující kroky obsahují základní informace o. Konkrétní podrobnosti najdete v dokumentaci společnosti Zebra. [Registrace v MDM pomocí StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (otevře web společnosti Zebra) může být dobrým zdrojem informací je.

1. V StageNow, vytvořte profil **registrace v MDM**.
2. V **nasazení**, vyberte a stáhněte soubor agenta MDM.
3. Nastavte **podporu aplikace** a **stáhnout konfiguraci** kroky **ne**.
4. V **stáhnout MDM**vyberte **přenos nebo kopírování souboru**. Přidáte zdroj a cíl balíček Android portál společnosti (APK).
5. V **spuštění MDM**, ponechte výchozí hodnoty jako-je. Přidejte následující podrobnosti:

    - **Název balíčku**: `com.microsoft.windowsintune.companyportal`
    - **Název třídy**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Dál profil publikování a využívání s StageNow aplikací na zařízení. Aplikace portál společnosti je nainstalované a otevře v zařízení.

> [!TIP]
> Další informace o StageNow a co to dělá, naleznete v tématu [přípravy zařízení s Androidem StageNow](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (otevře web společnosti Zebra).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Krok 2: Potvrďte, že aplikace portál společnosti s rolí Správce zařízení

Aplikace portál společnosti vyžaduje Správce zařízení ke správě zařízení s Androidem. Aktivovat roli Správce zařízení, některá zařízení Zebra zahrnují uživatelské rozhraní (UI) v zařízení. Pokud zařízení obsahuje uživatelské rozhraní, aplikace portál společnosti vyzve koncový uživatel musí udělit Správce zařízení během [registrace](#step-3-enroll-the-device-in-to-intune) (v tomto článku).

Pokud není k dispozici uživatelské rozhraní, použijte **DevAdmin správce** v StageNow k vytvoření profilu, který uděluje ručně Správce zařízení na aplikaci portál společnosti.

Následující kroky obsahují základní informace o. Konkrétní podrobnosti najdete v dokumentaci společnosti Zebra. 
[Nastavit režim prohození baterie jako správce zařízení](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (otevře se web společnosti Zebra) může být dobrým zdrojem informací je.

1. V StageNow, vytvořte profil a vyberte **Xpert režimu**.
2. Přidat **DevAdmin správce** k profilu.
3. Nastavte **akce správy zařízení** k **zapnout jako správce zařízení**.
4. Nastavte **název balíčku Správce zařízení** k `com.microsoft.windowsintune.companyportal`.
5. Nastavte **název třídy Správce zařízení** k `com.microsoft.omadm.client.PolicyManagerReceiver`.

Dál profil publikování a využívání s StageNow aplikací na zařízení. Aplikace portál společnosti je udělena role Správce zařízení.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Krok 3: Registrace zařízení v Intune

Po dokončení první dva kroky, je nainstalovaná aplikace portál společnosti na zařízení. Zařízení je připravené byla zaregistrovaná v Intune.

[Registrace zařízení s Androidem](android-enroll.md) jsou uvedené kroky. Pokud máte mnoho Zebra zařízení, můžete použít [účet správce registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Krok 4: Vytvoření profilu správy zařízení v StageNow

StageNow použijte k vytvoření profilu, který konfiguruje nastavení, které chcete spravovat zařízení. Konkrétní podrobnosti najdete v dokumentaci společnosti Zebra. [Profily](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (otevře se web společnosti Zebra) může být dobrým zdrojem informací je.

Když vytvoříte profil v StageNow, v posledním kroku, vyberte **exportovat do MDM**. Tím se vytvoří soubor XML. Soubor uložte. Budete potřebovat v pozdějším kroku.

> [!TIP]
> Doporučuje se test profil předtím, než ho nasadíte do zařízení ve vaší organizaci. K otestování v posledním kroku při vytváření profilů s StageNow v počítači, použijte **testování** možnosti. Potom využívání souboru generované StageNow s StageNow aplikací na zařízení. 
> 
> StageNow aplikace na zařízení zobrazí protokoly generované při testování profilu. [Použití StageNow přihlášení Zebra zařízení s Androidem v Intune](android-zebra-mx-logs-troubleshoot.md) obsahuje informace o použití StageNow protokoly o chybách.

> [!NOTE]
> Je-li odkazovat na aplikace, balíčky aktualizací nebo aktualizovat ostatní soubory ve vašem profilu StageNow chcete zařízení a získat tyto aktualizace. Můžou získat aktualizace, musí zařízení připojit k serveru StageNow nasazení, když se profil použije. 
> 
> Nebo můžete použít integrované funkce v Intune k získání těchto změn, včetně: 
> - Funkce správy aplikací k [přidat](apps-add.md), [nasazení](apps-deploy.md), aktualizovat, a [monitorování](apps-monitor.md) aplikace.
> - Správa [aktualizace systému a aplikací](device-restrictions-android-for-work.md#device-owner-only) na zařízeních s Androidem Enterprise

Po otestování soubor, dalším krokem je nasazení profilu na zařízení pomocí Intune.

> [!NOTE]
> Jeden profil nasaďte do každé zařízení. Pokud existuje více StageNow profily, které chcete nasadit na zařízení, exportovat StageNow profily a nastavení do jednoho souboru XML zkombinovat předtím, než ho přidáte do Intune. 
> 
> Nechcete, aby dvě nastavení konfigurace stejná vlastnost ve stejném souboru XML. Cílem je zabránit konfliktům mezi nastavení v zařízení.

## <a name="step-5-create-a-profile-in-intune"></a>Krok 5: V Intune vytvořit profil

V Intune vytvořte profil konfigurace zařízení:

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte **Android**.
    - **Typ profilu**: Vyberte **MX profil (jenom Zebra)**.

4. V **MX profilu ve formátu .xml**, přidejte soubor XML profilu [jste exportovali z StageNow](#step-4-create-a-device-management-profile-in-stagenow) (v tomto článku).
5. Vyberte **OK** > **Vytvořit** a změny uložte. Zásada se vytvoří a zobrazí v seznamu.

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

Při příštím zařízení kontroluje aktualizace konfigurace MX profil je nasazený do zařízení. Při registraci zařízení se zařízení synchronizovat s Intune a pak přibližně každých 8 hodin. Můžete také [vynucení synchronizace v Intune](device-sync.md). Nebo na zařízení, otevřete **aplikaci portál společnosti** > **nastavení** > **synchronizace**. 

> [!TIP]
> - Z bezpečnostních důvodů se nezobrazí XML text profilu po uložení. Text je šifrovaný a zobrazí jenom hvězdičky (`****`). Pro srovnání si se doporučuje ukládat kopie profily MX předtím, než je přidáte do Intune.
> 
> - Po přiřazení k zařízením Zebra aktualizovat profil, vytvořte aktualizovaný soubor StageNow XML upravit stávající profil Intune a přidejte nový soubor StageNow XML. Tento nový soubor přepíše předchozí zásady StageNow v profilu.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

[Řešení potíží s Zebra zařízení pomocí protokolů StageNow](android-zebra-mx-logs-troubleshoot.md).
