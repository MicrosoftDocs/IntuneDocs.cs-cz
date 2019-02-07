---
title: Kontrola úspěchu nebo neúspěchu standardních hodnot zabezpečení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zkontrolujte stav chyby, ke konfliktu a úspěchu, při nasazení standardních hodnot zabezpečení pro uživatele a zařízení v Microsoft Intune MDM. Naleznete v části řešení potíží pomocí protokolů klienta a funkcí sestavy v Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: db748f7c39cb133c5c7025dbb299f3fd1411ba17
ms.sourcegitcommit: 5b4a6c17bdba2f87e6ae81a3ac0cb88438a0fa27
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55807745"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>Monitorování standardních hodnot zabezpečení a profilu v Microsoft Intune

Existují různé možnosti monitorování, při použití standardních hodnot zabezpečení. Můžete monitorovat na profil standardních hodnot zabezpečení, která se použije pro uživatele a zařízení. Můžete také monitorovat skutečné směrného plánu a všechna zařízení, které odpovídají (nebo se neshodují.) doporučené hodnoty.

Tento článek vás provede obou možností monitorování.

[Základní nastavení zabezpečení v Intune](security-baselines.md) poskytuje podrobnější informace o funkci směrné plány zabezpečení v Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorování zařízení a snímek směrného plánu

Když monitorujete směrný plán, získejte přehled o stavu zabezpečení vašich zařízení, na základě doporučení služby od Microsoftu.

> [!NOTE]
> Po prvním přiřazení směrného plánu, sestavy může trvat až 24 hodin k aktualizaci. Potom se může trvat až 6 hodin k aktualizaci.

1. V [webu Azure portal](https://portal.azure.com/)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **směrné plány zabezpečení (preview)** > vyberte směrný plán.
3. V **přehled**, graf ukazuje, kolik zařízení je postiženo zvolíte a snímek směrného plánu různé stavy:

    ![Kontrola stavu zařízení](./media/security-baselines-monitor/overview.png)

    K dispozici jsou následující stavy:

    - **Standardní hodnoty shody**: Všechna nastavení ve směrném plánu shodovat s doporučeným nastavením.
    - **Neodpovídá směrného plánu**: Alespoň jedno nastavení ve směrném plánu neodpovídá doporučené nastavení.
    - **Chybně nakonfigurovaný**: Alespoň jedno nastavení není správně nakonfigurována. Tento stav znamená, že toto nastavení je v konfliktu, chyby nebo stavu čekající na vyřízení.
    - **Není k dispozici**: Alespoň jedno nastavení nelze použít a nebude použita.

4. Vyberte jednu z stavy, které se mají zařízení. Vyberte například **Misconfigured** stav.

5. Seznam všech zařízení s tímto stavem se zobrazí. Vyberte konkrétní zařízení, abyste získali více podrobností. 

    V následujícím příkladu, vyberte **konfigurace zařízení** > vyberte profil s chybový stav:

    ![Kontrola stavu zařízení](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Vyberte profil, chyba. Seznam všech nastavení v profilu a jejich stav se zobrazí. Teď se můžete posouvat nastavení příčinou chyby:

    ![Podívejte se na nastavení, který způsobil chybu](./media/security-baselines-monitor/profile-with-error-status.png)

Pomocí těchto sestav můžete zobrazit všechna nastavení v profilu, které jsou příčinou problému. Také Získejte podrobnosti o zásady a profily nasadit do zařízení.

> [!NOTE]
> Pokud je vlastnost nastavena na **Nenakonfigurováno** ve standardních hodnotách, nastavení je ignorováno a žádná omezení se vynucují. Vlastnost se nezobrazí v jakékoli generování sestav.

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
