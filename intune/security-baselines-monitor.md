---
title: Kontrola úspěchu nebo neúspěchu standardních hodnot zabezpečení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zkontrolujte stav chyby a úspěchu konflikt při nasazení standardních hodnot zabezpečení pro uživatele a zařízení v Microsoft Intune MDM. Naleznete v části řešení potíží pomocí protokolů klienta a funkcí sestavy v Intune.
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
ms.openlocfilehash: e3bf59f75d41d50cfd9280251e20964a35a149a8
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403580"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Monitorování standardních hodnot zabezpečení a profilů v Microsoft Intune  

Intune poskytuje celou řadu možností pro monitorování vaší základní nastavení zabezpečení. Můžete monitorovat na profil standardních hodnot zabezpečení, která se použije pro uživatele a zařízení. Můžete také monitorovat skutečné směrného plánu a všechna zařízení, které odpovídají (nebo se neshodují.) doporučené hodnoty.

Tento článek vás provede obou možností monitorování.

[Základní nastavení zabezpečení v Intune](security-baselines.md) poskytuje podrobnější informace o funkci směrné plány zabezpečení v Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorování zařízení a snímek směrného plánu  

Když monitorujete směrný plán, získejte přehled o stavu zabezpečení vašich zařízení, na základě doporučení služby od Microsoftu. Tyto informace z podokna přehledu standardních hodnot zabezpečení můžete zobrazit v konzole Intune.  Trvá až 24 hodin se zobrazí po prvním přiřazení směrného plánu data. Novější změny trvat až 6 hodin se zobrazí.  

Chcete-li zobrazit data monitorování standardních hodnot a zařízení, přihlaste se k [portál Intune](https://go.microsoft.com/fwlink/?linkid=2090973). V dalším kroku vyberte **zabezpečení zařízení** > **směrné plány zabezpečení**vyberte směrný plán a zobrazení **přehled** podokně.

**Přehled** podokně nabízí dvě metody k monitorování stavu:
- **Zobrazení zařízení** – souhrn kolik zařízení je v každé kategorii stav směrného plánu.  
- **Podle kategorie** – zobrazení, která zobrazuje každou kategorii ve směrném plánu a procento zařízení pro každou skupinu stav pro každou kategorii směrný plán obsahuje. 

Každé zařízení je reprezentované pomocí jedné z následujících stavů, které se používají v obou *zařízení* zobrazení a *podle kategorie* zobrazení:  
- **Standardní hodnoty shody** – všechna nastavení ve směrném plánu shodovat s doporučeným nastavením.
- **Neodpovídá směrného plánu** – alespoň jedno nastavení ve směrném plánu neodpovídá doporučené nastavení.
- **Chybně nakonfigurovaný** – alespoň jedno nastavení není správně nakonfigurována. Tento stav znamená, že toto nastavení je v konfliktu, chyby nebo stavu čekající na vyřízení.
- **Není k dispozici** – alespoň jedno nastavení nelze použít a nebude použita.


### <a name="device-view"></a>Zobrazení zařízení
Podokno s přehledem zobrazí shrnutí graf na základě počtu zařízení mají konkrétní stav směrného plánu; **Stav standardních hodnot zabezpečení pro zařízení s Windows 10 přiřazené**.  

![Kontrola stavu zařízení](./media/security-baselines-monitor/overview.png)

Pokud má zařízení jiný stav z různých kategorií podle směrného plánu, zařízení je reprezentován jeden stav. Stav, který představuje zařízení je převzata z následujícího pořadí priorit: **Chybně nakonfigurovaný**, **neodpovídá směrného plánu**, **není k dispozici**, **směrného plánu odpovídá**.  

Například, pokud zařízení obsahuje nastavení jsou klasifikovány jako *nesprávně nakonfigurované* a jedno nebo více nastavení, které jsou klasifikovány jako *neodpovídá směrného plánu*, zařízení je klasifikován tak *správněnakonfigurovaný*.  

Můžete kliknout na graf na Procházet a zobrazit seznam zařízení s různými stavy. Jednotlivá zařízení pak můžete vybrat ze seznamu zobrazíte podrobnosti o jednotlivých zařízeních. Příklad:
- Vyberte **konfigurace zařízení** > vyberte profil s chybový stav:

  ![Kontrola stavu zařízení](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Vyberte profil, chyba. Seznam všech nastavení v profilu a jejich stav se zobrazí. Teď se můžete posouvat nastavení příčinou chyby:

  ![Podívejte se na nastavení, který způsobil chybu](./media/security-baselines-monitor/profile-with-error-status.png)

Pomocí těchto sestav můžete zobrazit všechna nastavení v profilu, které jsou příčinou problému. Také Získejte podrobnosti o zásady a profily nasadit do zařízení.

> [!NOTE]
> Pokud je vlastnost nastavena na **Nenakonfigurováno** ve standardních hodnotách, nastavení je ignorováno a žádná omezení se vynucují. Vlastnost se nezobrazí v jakékoli generování sestav.

### <a name="per-category-view"></a>Na zobrazení kategorií
Podokno s přehledem zobrazuje graf podle kategorií pro požadovaný směrný plán; **Stav standardních hodnot zabezpečení podle kategorie**.  Toto zobrazení zobrazuje každou kategorii ze standardních hodnot a určuje procento zařízení, které spadají do klasifikace stav pro každou z těchto kategorií. 
 
![Stav zobrazení podle kategorií](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Stav **směrného plánu odpovídá** nezobrazí, dokud se 100 % zařízení nahlásit stav pro kategorii.   

Zobrazení podle kategorií můžete řadit jednotlivé sloupce tak, že vyberete ikonu šipky nahoru dolů v horní části sloupce.  


## <a name="monitor-the-profile"></a>Monitorování profilu

Sledování profil, který poskytuje přehled o stavu nasazení z vašich zařízení, ale ne stav zabezpečení podle základní doporučení.

1. V Intune, vyberte **směrné plány zabezpečení** > vyberte směrný plán > **profily vytvořené**.

2. Vyberte profil. V **přehled**, obrázek ukazuje, kolik zařízení a uživatelé budou používat tento profil přiřadit:

    ![Zobrazit, kolik zařízení a uživatelů se přiřadí k profilu standardních hodnot zabezpečení](./media/security-baselines-monitor/existing-profile-overview.png)

3. V části **spravovat** > **vlastnosti**, seznam všech nastavení ve směrném plánu jsou uvedeny. Můžete také změnit některé z těchto nastavení:

    ![Zobrazit a aktualizovat nastavení v profilu standardních hodnot zabezpečení](./media/security-baselines-monitor/manage-settings.png)

4. V **monitorování**, zobrazí se stav nasazení profilu na jednotlivá zařízení, stav pro každého uživatele a stav pro každé nastavení podle směrného plánu:

    ![Zobrazí se možnosti různých sledování profil standardních hodnot zabezpečení](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Řešení potíží pomocí stav podle nastavení

Nasazení standardních hodnot zabezpečení, ale ukazuje chybu, stav nasazení. Následující kroky vám poskytnou několik doprovodné materiály k řešení potíží s chybou.

1. V Intune, vyberte **směrné plány zabezpečení** > vyberte směrný plán > **profily vytvořené**.
2. Vyberte profil > v části **monitorování** > **stav podle nastavení**.
3. V tabulce jsou uvedeny všechna nastavení a stavu každého nastavení. Vyberte **chyba** sloupec nebo **konflikt** sloupec, který chcete zobrazit nastavení příčinou chyby.

### <a name="mdm-diagnostic-information"></a>Diagnostické informace MDM

Nyní je, že nastavení problematické. Dalším krokem je zjistit, proč je toto nastavení způsobí chybu nebo konflikt. 

Na zařízení s Windows 10 je integrované sestavy MDM diagnostické informace. Tato sestava obsahuje výchozí hodnoty, aktuální hodnoty, uvádí zásadu, zobrazí, pokud je nasazený do zařízení nebo uživatele a další. Tato sestava slouží k určení toho, proč nastavení způsobuje konflikt nebo chybu.

1. Na zařízení, přejděte na **nastavení** > **účty** > **přístup do práce nebo do školy**.
2. Vyberte účet > **informace** > **Advanced diagnostickou sestavu** > **vytvoření sestavy**.
3. Zvolte **exportovat**a otevřete vygenerovaný soubor.
4. V sestavě vyhledejte chyba nebo konflikt nastavení v jiné části sestavy.

  Například, podívejte se **zaregistrované zdroje konfigurace a cílové prostředky** části nebo **nespravované zásady** části. Může získat představu, proč je příčinou chyby nebo konflikt.

[Diagnostikování selhání MDM ve Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) poskytuje další informace o tomto předdefinované sestavy.

> [!TIP]
> - Některá nastavení seznamu také identifikátor GUID. Můžete vyhledat tento identifikátor GUID v místním registru (regedit) pro všechny hodnoty.
> - Protokoly Prohlížeče událostí může také obsahovat některé informace o chybě na problematický nastavení (**Prohlížeč událostí** > **protokoly aplikací a služeb**  >   **Microsoft** > **Windows** > **DeviceManagement Enterprise Diagnostika zprostředkovatele** > **správce** ).

## <a name="next-steps"></a>Další postup

[Sledování profilů zařízení](device-profile-monitor.md) a [naleznete v tématu některé běžné problémy a řešení](device-profile-troubleshoot.md).
