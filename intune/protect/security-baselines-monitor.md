---
title: Ověření úspěšného nebo neúspěšného směrného plánu zabezpečení v Microsoft Intune – Azure | Microsoft Docs
description: Při nasazení standardních hodnot zabezpečení pro uživatele a zařízení v Microsoft Intune MDM se podívejte na stav Chyba, konflikt a úspěch. Podívejte se, jak řešit potíže s používáním klientských protokolů a funkce sestav v Intune.
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
ms.openlocfilehash: b16b4ee95647b3bb182af075bbe7f7aad71351f0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731946"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Sledování standardních hodnot zabezpečení a profilů v Microsoft Intune  

Intune nabízí několik možností monitorování standardních hodnot zabezpečení. Můžete monitorovat profil standardních hodnot zabezpečení, který platí pro uživatele a zařízení. Můžete také monitorovat skutečné standardní hodnoty a všechna zařízení, která se shodují (nebo se neshodují) s doporučenými hodnotami.

Tento článek vás provede jednotlivými možnostmi monitorování.

[Směrné plány zabezpečení v Intune](../security-baselines.md) poskytují další podrobnosti o funkci směrného plánu zabezpečení v Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorování standardních hodnot a zařízení  

Při sledování směrného plánu získáte přehled o stavu zabezpečení vašich zařízení na základě doporučení Microsoftu. Tyto přehledy si můžete prohlédnout v podokně Přehled směrného plánu zabezpečení v konzole Intune.  Po prvním přiřazení směrného plánu trvá zobrazení dat až 24 hodin. Pozdější změny se projeví až po šesti hodinách.  

Pokud chcete zobrazit data monitorování pro základní hodnoty a zařízení, přihlaste se na [portál Intune](https://go.microsoft.com/fwlink/?linkid=2090973). V dalším kroku vyberte **zabezpečení zařízení** > **standardní hodnoty zabezpečení**, vyberte směrný plán a zobrazte podokno **přehledu** .

V podokně **Přehled** jsou k dispozici dvě metody monitorování stavu:
- **Zobrazení zařízení** – souhrn toho, kolik zařízení je v každé kategorii stavů pro směrný plán.  
- **Podle kategorií** – zobrazení, které zobrazuje jednotlivé kategorie ve standardních hodnotách a zahrnuje procento zařízení pro každou skupinu stavů pro každou kategorii standardních hodnot. 

Každé zařízení je reprezentované jedním z následujících stavů, které se používají v zobrazení *zařízení* , a v *jednotlivých kategoriích* zobrazení:  
- **Odpovídá směrnému plánu** – všechna nastavení v směrném plánu odpovídají doporučeným nastavením.
- Neodpovídá **směrnému plánu** – nejméně jedno nastavení v směrném plánu se neshoduje s doporučeným nastavením.
- **Nesprávně nakonfigurovaná – aspoň** jedno nastavení není správně nakonfigurované. Tento stav znamená, že je nastavení v konfliktu, chyba nebo čeká na vyřízení.
- **Nedá se použít** – aspoň jedno nastavení se nedá použít a není použité.


### <a name="device-view"></a>Zobrazení zařízení
V podokně Přehled se zobrazí souhrn založený na grafu o tom, kolik zařízení má určitý stav pro směrný plán. **Zabezpečení standardních hodnot stav pro přiřazená zařízení s Windows 10**  

![Kontrolovat stav zařízení](./media/security-baselines-monitor/overview.png)

Pokud má zařízení různý stav z různých kategorií na základě směrného plánu, zařízení je reprezentované jediným stavem. Stav, který představuje zařízení, pochází z následujícího pořadí: nesprávně **nakonfigurované**, **neshoduje se se směrným plánem**, **není k dispozici**, **odpovídá směrnému plánu**.  

Pokud má například zařízení nastavení klasifikované jako nesprávně *nakonfigurované* a jedno nebo více nastavení klasifikovaných jako neodpovídá *směrnému plánu*, je zařízení klasifikované jako nesprávně *nakonfigurované*.  

Kliknutím na graf můžete procházet a zobrazit seznam zařízení s různými stavy. Pak můžete vybrat jednotlivá zařízení z tohoto seznamu a zobrazit podrobnosti o jednotlivých zařízeních. Například:
- Vyberte **Konfigurace zařízení** > vyberte profil s chybovým stavem:

  ![Kontrolovat stav zařízení](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Vyberte chybový profil. Zobrazí se seznam všech nastavení v profilu a jejich stav. Nyní se můžete posouvat a najít nastavení způsobující chybu:

  ![Zobrazit nastavení způsobující chybu](./media/security-baselines-monitor/profile-with-error-status.png)

Pomocí tohoto hlášení můžete zobrazit všechna nastavení v profilu, která způsobují problém. Získejte taky další podrobnosti o zásadách a profilech nasazených do zařízení.

> [!NOTE]
> Pokud je vlastnost nastavena na hodnotu **není nakonfigurováno** v směrném plánu, je nastavení ignorováno a nejsou vydodržována žádná omezení. Vlastnost není zobrazená v žádné sestavě.

### <a name="per-category-view"></a>Podle zobrazení kategorií
Podokno přehled zobrazuje pro směrný plán graf podle kategorií; **Základní úroveň zabezpečení stav podle kategorie**.  Toto zobrazení zobrazuje jednotlivé kategorie ze standardních hodnot a určuje procento zařízení, která spadají do klasifikace stavu pro každou z těchto kategorií. 
 
![Zobrazení stavu podle kategorie](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Stav pro **porovnání standardních hodnot** se nezobrazuje, dokud 100% zařízení nehlásí stav pro danou kategorii.   

Zobrazení podle kategorií můžete podle jednotlivých sloupců seřadit tak, že v horní části sloupce vyberete ikonu šipky dolů.  


## <a name="monitor-the-profile"></a>Monitorování profilu

Monitorování profilu vám umožní získat přehled o stavu nasazení vašich zařízení, ale ne stav zabezpečení na základě standardních doporučení.

1. V Intune vyberte **standardní hodnoty zabezpečení** > vyberte směrné > **vytvořené profily**.

2. Vyberte profil. V **přehledu**se na obrázku zobrazuje, kolik zařízení a uživatelů má tento profil přiřazený:

    ![Podívejte se, kolik zařízení a uživatelů má přiřazený profil standardních hodnot zabezpečení.](./media/security-baselines-monitor/existing-profile-overview.png)

3. V části **Spravovat** **vlastnosti** >  se zobrazí seznam všech nastavení ve standardních hodnotách. Můžete také změnit kterékoli z těchto nastavení:

    ![Zobrazit a aktualizovat nastavení v profilu standardních hodnot zabezpečení](./media/security-baselines-monitor/manage-settings.png)

4. V okně **monitor**můžete zobrazit stav nasazení profilu na jednotlivých zařízeních, stav pro každého uživatele a stav každého nastavení ve standardních hodnotách:

    ![Zobrazit různé možnosti monitorování pro profil standardních hodnot zabezpečení](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Řešení potíží s použitím stavu podle nastavení

Nasadili jste základní úroveň zabezpečení, ale stav nasazení zobrazuje chybu. Následující kroky vám poskytnou pokyny k řešení této chyby.

1. V Intune vyberte **standardní hodnoty zabezpečení** > vyberte směrné > **vytvořené profily**.
2. Vyberte profil > pod položkou **monitorovat**stav  > **pro nastavení**.
3. V tabulce jsou uvedena všechna nastavení a stav jednotlivých nastavení. Pokud chcete zobrazit nastavení, které způsobuje chybu, vyberte sloupec **Chyba** nebo sloupec **konfliktů** .

### <a name="mdm-diagnostic-information"></a>Diagnostické informace MDM

Nyní znáte problematické nastavení. V dalším kroku zjistíte, proč toto nastavení způsobuje chybu nebo konflikt. 

Na zařízeních s Windows 10 je k dispozici integrovaná sestava diagnostické informace MDM. Tato sestava obsahuje výchozí hodnoty, aktuální hodnoty, seznam těchto zásad, informace o tom, jestli se nasadí do zařízení nebo uživatele, a další. Tato sestava vám pomůže zjistit, proč nastavení způsobuje konflikt nebo chybu.

1. V zařízení přejděte na **nastavení** > **účty** >  přístup do**práce nebo do školy**.
2. Vyberte účet > **informace** > **Pokročilá diagnostická zpráva**-1  > **vytvořit sestavu**.
3. Vyberte **exportovat**a vygenerovaný soubor otevřete.
4. V sestavě vyhledejte nastavení chyba nebo konflikt v různých částech sestavy.

  Podívejte se například na oddíl **zaregistrované zdrojové konfigurace a cílové prostředky** nebo na oddíl **nespravované zásady** . Můžete získat představu o tom, proč způsobuje chybu nebo konflikt.

[Diagnostika selhání MDM ve Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) poskytuje další informace o této předdefinované sestavě.

> [!TIP]
> - Některá nastavení také uvádějí identifikátor GUID. Tento identifikátor GUID můžete vyhledat v místním registru (Regedit) pro všechny hodnoty sady.
> - Protokoly Prohlížeč událostí mohou také obsahovat informace o problémech s problematickým nastavením (**protokoly aplikací a služeb**v**prohlížeči událostí** >   > **Microsoft** > **Windows** >  **DeviceManagement-Enterprise-Diagnostics-Provider** **admin** > ).

## <a name="next-steps"></a>Další kroky

[Sledujte profily zařízení](../configuration/device-profile-monitor.md) a [Podívejte se na některé běžné problémy a jejich řešení](../configuration/device-profile-troubleshoot.md).
