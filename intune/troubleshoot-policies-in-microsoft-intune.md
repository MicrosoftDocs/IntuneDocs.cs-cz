---
title: Řešení potíží se zásadami v Microsoft Intune – Azure | Microsoft Docs
description: Zjistěte, jak použít funkci integrované řešení potíží a přečtěte si informace o běžných problémů nebo problémy a jejich řešení při použití zásad dodržování předpisů a konfiguračních profilů v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9314617640d0bfd7f3a7b0cd0ba572e99ede53f9
ms.sourcegitcommit: cd451ac487c7ace18ac9722a28b9facfba41f6d3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2019
ms.locfileid: "67298401"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Řešení potíží s zásady a profily a v Intune

Microsoft Intune obsahuje některé integrované funkce řešení potíží. Tyto funkce využijete k řešení potíží se zásadami dodržování předpisů a profily konfigurace ve vašem prostředí.

Tento článek uvádí některé běžné postupy řešení potíží a popisuje některé problémy, se kterými se můžete setkat.

## <a name="check-tenant-status"></a>Zkontrolujte stav tenanta.
Zkontrolujte, [stav Tenanta](tenant-status.md) a potvrďte je předplatné aktivní. Můžete také zobrazit podrobnosti pro informační zpravodaje, které může mít vliv na vaše nasazení zásady nebo profil a aktivními incidenty.

## <a name="use-built-in-troubleshooting"></a>Použít integrované řešení potíží

1. V [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)vyberte **Poradce při potížích**:

    ![V Intune přejděte na Nápověda a odborná pomoc a vyberte Poradce při potížích](./media/help-and-support-troubleshoot.png)

2. Zvolte **vybrat uživatele** > vyberte uživatele, se vyskytl problém > **vyberte**.
3. Ujistěte se, že **licence Intune** a **stav účtu** obě tyto sestavy ukazují zelené kontroly:

    ![V Intune vyberte uživatele a potvrďte, že stav účtu a licence pro Intune zobrazit značky zelené kontroly stavu](./media/account-status-intune-license-show-green.png)

    **Užitečné odkazy**:

    - [Přiřazení licencí, aby uživatelé mohli registrovat zařízení](licenses-assign.md)
    - [Přidání uživatelů do Intune](users-add.md)

4. V části **zařízení**, najděte příslušné zařízení se vyskytl problém. Projděte si různé sloupce:

    - **Spravované**: Pro zařízení mohlo přijmout zásady dodržování předpisů nebo konfigurace, musíte tuto vlastnost zobrazit **MDM** nebo **EAS/MDM**.

      - Pokud **spravované** není nastavená na **MDM** nebo **EAS/MDM**, pak zařízení není zaregistrované. Zásady dodržování předpisů nebo konfigurace neobdrží nebude registrováno.

      - Zásady ochrany aplikací (Správa mobilních aplikací) nevyžadují zařízení byla zaregistrovaná. Další informace najdete v tématu [vytvořte a přiřaďte zásady ochrany aplikací](app-protection-policies.md).

    - **Typ připojení ke službě Azure AD**: By mělo být nastavené **pracoviště** nebo **AzureAD**.
 
      - Pokud je tento sloupec **Neregistrovaný**, může být problém s registrací. Zrušení registrace a zapsalo obvykle řeší tento stav.

    - **Vyhovuje Intune**: By měl být **Ano**. Pokud **ne** zobrazeno, může být problém se zásadami dodržování předpisů nebo zařízení se připojuje ke službě Intune. Například zařízení může být vypnuté nebo nemusí mít připojení k síti. Nakonec je označeno jako zařízení nevyhovující předpisům, případně po 30 dnech.

      Další informace najdete v tématu [Začínáme se zásadami dodržování předpisů zařízení](device-compliance-get-started.md).

    - **Vyhovuje Azure AD**: By měl být **Ano**. Pokud **ne** zobrazeno, může být problém se zásadami dodržování předpisů nebo zařízení se připojuje ke službě Intune. Například zařízení může být vypnuté nebo nemusí mít připojení k síti. Nakonec je označeno jako zařízení nevyhovující předpisům, případně po 30 dnech.

      Další informace najdete v tématu [Začínáme se zásadami dodržování předpisů zařízení](device-compliance-get-started.md).

    - **Poslední vrátit se změnami**: By měla být datum a čas poslední. Ve výchozím nastavení kontrolují zařízení v Intune každých 8 hodin.

      - Pokud **poslední vrátit se změnami** je více než 24 hodin, může být problém se zařízením. Zařízení, které nelze vrátit se změnami nemohou přijímat zásady Intune.

      - Chcete-li vynutit vrácení se změnami:
        - Na zařízení s Androidem, otevřete aplikaci portál společnosti > **zařízení** > vyberte zařízení, ze seznamu > **zkontrolovat nastavení zařízení**.
        - Na zařízení s iOS otevřete aplikaci portál společnosti > **zařízení** > vyberte zařízení, ze seznamu > **zkontrolovat nastavení**. 
        - Na zařízení s Windows otevřete **nastavení** > **účty** > **přístup do práce nebo do školy** > vyberte účet nebo registrace MDM >  **Informace o** > **synchronizace**.

    - Vyberte zařízení, pokud chcete zobrazit informace specifické pro zásady.

      **Dodržování předpisů zařízením** zobrazuje stav zásad dodržování předpisů přiřazených k zařízení.

      **Konfigurace zařízení** zobrazuje stav zásad konfigurace se týkají daného zařízení.

      Pokud se nezobrazují očekávané zásady v rámci **dodržování předpisů zařízením** nebo **konfigurace zařízení**, pak nejsou správně zacílené zásady. Otevřete zásadu a přiřaďte zásady pro tohoto uživatele nebo zařízení.

      **Stavy zásad**:

      - **Není k dispozici**: Tato zásada není na této platformě podporována. Například zásady pro iOS nefungují v Androidu. Samsung KNOX zásady nefungují na zařízeních s Windows.
      - **Konflikt**: Existuje stávající nastavení v zařízení, Intune nemůže přepsat. Nebo jste nasadili dvě zásady s stejné nastavení s použitím různých hodnot.
      - **Čekající**: Zařízení nebylo změnami do Intune a získání zásady. Nebo zařízení přijaty zásady ale neohlásil stav do Intune.
      - **Chyby**: Vyhledat chyby a jejich možná řešení na [řešení problémů pro přístup k prostředkům společnosti](troubleshoot-company-resource-access-problems.md).

      **Užitečné odkazy**: 

      - [Způsoby, jak nasadit zásady dodržování předpisů zařízením](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
      - [Monitorování zásad dodržování předpisů zařízením](compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Jste si jisti, jestli je správně použít profil

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **zařízení** > **všechna zařízení** > vyberte zařízení > **konfigurace zařízení**. 

    Každé zařízení obsahuje své profily. Každý profil obsahuje **stav**. Stav použije, když jsou společně zvažovány všechny přiřazené Profily hardwaru a operačního systému omezení a požadavky, včetně. Možné stavy patří:

    - **Odpovídá**: Zařízení přijetí profil a sestavy do služby Intune, že vyhovuje danému nastavení.

    - **Není k dispozici**: Nastavení profilu nelze použít. Nastavení e-mailu pro zařízení s Iosem například nevztahují na zařízení s Androidem.

    - **Čekající**: Profil se neodesílají do zařízení, ale ještě neohlásilo stav do Intune. Na vyřízení může čekat třeba šifrování v systému Android, které vyžaduje, aby šifrování povolil uživatel.

**Užitečný odkaz**: [Monitorování profilů konfigurace zařízení](device-profile-monitor.md)

> [!NOTE]
> Když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, uplatní se víc omezující zásada.

## <a name="policy-troubleshooting-resources"></a>Materiály pro řešení problémů zásad

- [Řešení potíží s iOS nebo Android zásady není nevztahují na zařízení](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (otevře jiný web společnosti Microsoft)
- [Řešení potíží se selháním zásad Windows 10 Intune](http://configmgrdogsarchive.com/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (otevře blogu)
- [Řešení potíží s vlastních nastavení zprostředkovatele kryptografických služeb pro Windows 10](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (otevře jiný web společnosti Microsoft)
- [Zásady skupiny systému Windows 10 vs Intune MDM zásad](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (otevře jiný web společnosti Microsoft)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Upozornění: Uložení pravidel přístupu do systému Exchange se nezdařilo

**Problém**: Obdržíte výstrahu **uložení pravidel přístupu do systému Exchange se nezdařilo** v konzole pro správu.

Je-li vytvořit zásady v pracovním prostoru zásady pro Exchange On-Premises (konzoly pro správu), ale používáte Office 365, nakonfigurované nastavení zásad vynucovat přes Intune. Ve výstraze poznamenejte si zdroj zásad. V pracovním prostoru zásady pro místní Exchange odstraňte zastaralá pravidla. Zastaralá pravidla jsou globální pravidla Exchange v Intune pro místní Exchange a nejsou relevantní pro Office 365. Vytvořte novou zásadu pro Office 365.

[Řešení potíží s místní Exchange connector Intune](troubleshoot-exchange-connector.md) může být dobrým zdrojem informací je.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Nelze změnit zásady zabezpečení pro zaregistrovaná zařízení

Zařízení Windows Phone neumožňují zmírnění zásad zabezpečení nastavených s použitím MDM nebo EAS, jakmile je nastavíte snížení zabezpečení. Například můžete nastavit **minimální počet znaků hesla** 8 a pak pokusíte snížit na 4. Víc omezující zásada platí pro zařízení.

Zařízení s Windows 10 nemusí odstranit zásady zabezpečení při zrušení přiřazení zásad (Zastavit nasazení). Budete muset nechat přiřazené zásady a poté změňte nastavení zabezpečení zpět na výchozí hodnoty.

V závislosti na platformě zařízení, pokud chcete zásadu změnit na méně zabezpečenou hodnotu, vám může být potřeba resetovat zásady zabezpečení.

Například ve Windows 8.1, na ploše prstem zprava a otevřete **ovládací tlačítka** panelu. Zvolte **nastavení** > **ovládací panely** > **uživatelské účty**. Na levé straně vyberte odkaz **Resetovat zásady zabezpečení** a zvolte **Resetovat zásady**.

Jiné platformy, jako je například Android, iOS a Windows Phone 8.1, možná muset být vyřadit a znovu zaregistrovat použít méně omezující zásadu.

[Řešení potíží s registrací](troubleshoot-device-enrollment-in-intune.md) může být dobrým zdrojem informací je.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Počítače s pomocí softwarového klienta Intune - classic portal

> [!NOTE]
> Tato část se týká na klasickém portálu. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Chyby související se zásadami Microsoft Intune v souboru policyplatform.log

Pro počítače s Windows spravované pomocí softwarového klienta Intune, chyby zásad v `policyplatform.log` soubor může být z jiného než výchozího nastavení v Windows řízení uživatelských účtů (UAC) v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

#### <a name="resolve-uac-issues"></a>Řešení potíží s UAC

1. Vyřaďte počítač. Zobrazte si [Odebrání zařízení](devices-wipe.md).

2. Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat z nabídky Programy a funkce.

3. V nabídce start zadejte **nástroje Řízení uživatelských účtů** otevřete nastavení řízení uživatelských účtů.

4. Nastavte posuvník oznámení na výchozí nastavení.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>CHYBA: Nelze získat hodnotu z počítače, 0x80041013

K této chybě může dojít, pokud se místní systém nesynchronizuje více než pět minut. Pokud je čas v místním počítači synchronizovaný, zabezpečené transakce se nezdaří, protože časová razítka nejsou platné.

Chcete-li vyřešit tento problém, nastavte místního systémového času co nejblíže k internetovým časem. Nebo ji nastavte na čas na řadičích domény v síti.


## <a name="next-steps"></a>Další postup

[Běžné problémy a řešení s e-mailových profilů](troubleshoot-email-profiles-in-microsoft-intune.md)

Získat [podpory Microsoftu](get-support.md), nebo použijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
