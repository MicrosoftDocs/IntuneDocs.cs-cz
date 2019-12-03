---
title: Řešení potíží se zásadami v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se, jak používat integrovanou funkci řešení potíží, a přečtěte si o běžných problémech nebo problémech a jejich řešeních při používání zásad dodržování předpisů a konfiguračních profilů v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8768022872d32116add0ed4ea4caf1f8fcb800f
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059271"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Řešení potíží se zásadami a profily a v Intune

Microsoft Intune obsahuje některé integrované funkce řešení potíží. Tyto funkce vám pomůžou při odstraňování potíží se zásadami dodržování předpisů a profily konfigurace ve vašem prostředí.

Tento článek uvádí některé běžné techniky řešení potíží a popisuje některé problémy, se kterými se můžete setkat.

## <a name="check-tenant-status"></a>Kontrolovat stav tenanta

Zkontrolujte [stav tenanta](../fundamentals/tenant-status.md) a potvrďte, že je předplatné aktivní. Můžete si také zobrazit podrobnosti o aktivních incidentech a poradcích, které mohou mít vliv na vaše zásady nebo nasazení profilu.

## <a name="use-built-in-troubleshooting"></a>Použití integrovaného řešení potíží

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **řešení potíží + podpora**:

    ![V Intune si přečtěte pomoc a podpora a vyberte řešení potíží.](./media/troubleshoot-policies-in-microsoft-intune/help-and-support-troubleshoot.png)

2. Zvolte **Vybrat uživatele** > vyberte uživatele s problémem > **Vybrat**.
3. Potvrďte, že licence a **stav účtu** **Intune** zobrazují zelenou kontrolu:

    ![V Intune vyberte uživatele a potvrďte stav účtu a licenci Intune zobrazit zeleně kontroler stavu.](./media/troubleshoot-policies-in-microsoft-intune/account-status-intune-license-show-green.png)

    **Užitečné odkazy**:

    - [Přiřazení licencí, aby uživatelé mohli registrovat zařízení](../fundamentals/licenses-assign.md)
    - [Přidání uživatelů do Intune](../fundamentals/users-add.md)

4. V části **zařízení**Najděte zařízení, které má problém. Zkontrolujte různé sloupce:

    - **Spravované**: u zařízení, které má přijmout zásady pro dodržování předpisů nebo konfigurace, musí tato vlastnost zobrazovat **MDM** nebo **EAS/MDM**.

        - Pokud se **spravovaný** není nastaven na **MDM** nebo **EAS/MDM**, zařízení se nezaregistruje. Neobdrží zásady dodržování předpisů ani konfigurace, dokud se nezaregistruje.

        - Zásady ochrany aplikací (Správa mobilních aplikací) nevyžadují, aby byla zařízení zaregistrovaná. Další informace najdete v tématu [Vytvoření a přiřazení zásad ochrany aplikací](../apps/app-protection-policies.md).

    - **Typ připojení ke službě Azure AD**: mělo by být nastavené na **pracoviště** nebo **AzureAD**.
 
        - Pokud tento sloupec není **zaregistrován**, může dojít k potížím při registraci. Při odregistraci a opětovné registraci zařízení se tento stav obvykle vyřeší.

    - **Kompatibilní s Intune**: měla by být **Ano**. Pokud se nezobrazí **žádné** , může se jednat o problém se zásadami dodržování předpisů nebo se zařízení nepřipojuje ke službě Intune. Například zařízení může být vypnuté nebo nemusí mít síťové připojení. Zařízení nakonec nebude kompatibilní, možná po 30 dnech.

        Další informace najdete v tématu [Začínáme se zásadami dodržování předpisů pro zařízení](../protect/device-compliance-get-started.md).

    - **Kompatibilní se službou Azure AD**: mělo by to být **Ano**. Pokud se nezobrazí **žádné** , může se jednat o problém se zásadami dodržování předpisů nebo se zařízení nepřipojuje ke službě Intune. Například zařízení může být vypnuté nebo nemusí mít síťové připojení. Zařízení nakonec nebude kompatibilní, možná po 30 dnech.

        Další informace najdete v tématu [Začínáme se zásadami dodržování předpisů pro zařízení](../protect/device-compliance-get-started.md).

    - **Poslední vrácení se změnami**: mělo by se jednat o poslední datum a čas. Ve výchozím nastavení se zařízení Intune zaregistrují každých 8 hodin.

        - Pokud je **Poslední vrácení se změnami** více než 24 hodin, může se jednat o problém se zařízením. Zařízení, které nejde vrátit se změnami, nemůže přijmout vaše zásady z Intune.

        - Chcete-li vynutit vrácení se změnami:
            - Na zařízení s Androidem otevřete Portál společnosti App > **zařízení** > vyberte zařízení ze seznamu > **Ověřte nastavení zařízení**.
            - Na zařízení s iOS otevřete aplikaci Portál společnosti > **zařízení** > v seznamu vyberte zařízení > **kontrolu nastavení**.

        - Na zařízení s Windows otevřete **nastavení** > **účty** > **přístup do práce nebo do školy** > vyberte účet nebo registraci MDM > **informace** > **Sync**.

    - Pokud chcete zobrazit informace specifické pro zásady, vyberte zařízení.

        **Dodržování předpisů zařízením** zobrazuje stavy zásad dodržování předpisů přiřazených k zařízení.

        **Konfigurace zařízení** zobrazuje stavy zásad konfigurace přiřazených k zařízení.

        Pokud se očekávané zásady nezobrazují v části **dodržování předpisů zařízením** nebo **Konfigurace zařízení**, zásady nejsou správně cílené. Otevřete zásadu a přiřaďte tuto zásadu tomuto uživateli nebo zařízení.

        **Stavy zásad**:

        - **Nelze použít**: Tato zásada není na této platformě podporována. Například zásady iOS nefungují na Androidu. Zásady Samsung KNOX nefungují na zařízeních s Windows.
        - **Konflikt**: v zařízení existuje stávající nastavení, které Intune nemůže přepsat. Nebo jste nasadili dvě zásady se stejným nastavením s použitím různých hodnot.
        - **Čeká na vyřízení**: zařízení není zaregistrované v Intune, aby bylo možné tyto zásady získat. Nebo zařízení přijalo zásady, ale neoznámilo stav Intune.
        - **Chyby**: Vyhledání chyb a možných řešení při [řešení problémů s přístupem k prostředkům společnosti](../fundamentals/troubleshoot-company-resource-access-problems.md).

        **Užitečné odkazy**: 

        - [Způsoby nasazení zásad dodržování předpisů pro zařízení](../protect/device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
        - [Monitorování zásad dodržování předpisů zařízením](../protect/compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Nejste si jistí, jestli se profil správně používá

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **všechna zařízení** > vyberte zařízení > **Konfigurace zařízení**. 

    Každé zařízení obsahuje seznam profilů. Každý profil má **stav**. Stav platí, když jsou společně zváženy všechny přiřazené profily, včetně omezení hardwaru a operačního systému a požadavků. Možné stavy zahrnují:

    - **Vyhovuje**: zařízení dostalo profil a sestavy do Intune, které odpovídají danému nastavení.

    - **Nedá se použít**: nastavení profilu se nedá použít. Například nastavení e-mailu pro zařízení s iOS se nevztahují na zařízení s Androidem.

    - **Čeká na vyřízení**: Profil se pošle do zařízení, ale neohlásil stav Intune. Na vyřízení může čekat třeba šifrování v systému Android, které vyžaduje, aby šifrování povolil uživatel.

**Užitečný odkaz**: [monitorování profilů konfigurace zařízení](../configuration/device-profile-monitor.md)

> [!NOTE]
> Když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, uplatní se víc omezující zásada.

## <a name="policy-troubleshooting-resources"></a>Zásady odstraňování potíží s prostředky

- [Řešení potíží se zásadami pro iOS nebo Android, které se nevztahují na zařízení](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (otevírá jiný web Microsoftu)
- [Řešení potíží s chybami zásad Windows 10 v Intune](https://blogs.technet.microsoft.com/configmgrdogs/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (otevření blogu)
- [Řešení potíží s vlastním nastavením CSP pro Windows 10](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (otevře další web Microsoftu)
- Zásady správy mobilních zařízení s [Windows 10 zásady skupiny a Intune](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (otevře se další web Microsoftu)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Výstraha: Uložení pravidel přístupu do systému Exchange se nezdařilo

**Problém**: V konzole pro správu se objeví výstraha **Uložení pravidel přístupu do systému Exchange se nezdařilo**  .

Pokud vytvoříte zásady v pracovním prostoru zásady pro místní Exchange (konzola pro správu), ale používáte Office 365, nakonfigurovaná nastavení zásad se neuplatňují v Intune. Ve výstraze si poznamenejte zdroj zásad. V pracovním prostoru zásady pro místní Exchange odstraňte starší pravidla. Starší pravidla jsou globální pravidla Exchange v rámci Intune pro místní Exchange a nevztahují se na Office 365. Pak vytvořte nové zásady pro Office 365.

[Řešení potíží s místním Exchange Connectorem Intune](../protect/troubleshoot-exchange-connector.md) může být dobrým prostředkem.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Nejde změnit zásady zabezpečení zaregistrovaných zařízení.

Zařízení Windows Phone neumožňují, aby se zásady zabezpečení nastavené pomocí MDM nebo EAS po nastavení snížily v zabezpečení. Například nastavíte **minimální počet znaků hesla** na hodnotu 8 a pak se ho pokusíte snížit na 4. V zařízení se použije více omezující zásada.

Pokud zrušíte přiřazení zásady (zastavit nasazení), zařízení s Windows 10 nemůžou odebrat zásady zabezpečení. Možná budete muset ponechat přiřazenou zásadu a pak změnit nastavení zabezpečení zpátky na výchozí hodnoty.

V závislosti na platformě zařízení může být potřeba resetovat zásady zabezpečení, pokud chcete zásadu změnit na méně bezpečnou hodnotu.

Například v Windows 8.1 na ploše potáhnutím prstem zprava otevřete panel **ovládací tlačítka** . Vyberte **nastavení** > **ovládací Panel** **uživatelské účty** > . Na levé straně vyberte odkaz **Resetovat zásady zabezpečení** a zvolte **Resetovat zásady**.

Jiné platformy, například zařízení se systémem Android, iOS a Windows Phone 8,1, může být potřeba vyřadit a znovu zaregistrovat, aby bylo možné použít méně omezující zásadu.

[Řešení potíží při registraci zařízení](../enrollment/troubleshoot-device-enrollment-in-intune.md) může být dobrým prostředkem.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Počítače používající softwarového klienta Intune – klasický portál

> [!NOTE]
> Tato část se vztahuje na klasický portál. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Chyby související se zásadami Microsoft Intune v souboru policyplatform.log

Pro počítače s Windows spravované pomocí softwarového klienta Intune můžou chyby zásad v souboru `policyplatform.log` být z nevýchozího nastavení v nástroji Řízení uživatelských účtů (UAC) systému Windows v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

#### <a name="resolve-uac-issues"></a>Řešení potíží s UAC

1. Vyřaďte počítač. Zobrazte si [Odebrání zařízení](../remote-actions/devices-wipe.md).

2. Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat z nabídky Programy a funkce.

3. V nabídce Start zadejte **UAC** a otevřete nastavení řízení uživatelských účtů.

4. Přesuňte posuvník oznámení na výchozí nastavení.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>CHYBA: Nelze získat hodnotu z počítače, 0x80041013

K této chybě může dojít, pokud se místní systém nesynchronizuje více než pět minut. Pokud není čas v místním počítači nesynchronizovaný, zabezpečené transakce selžou, protože časová razítka nejsou platná.

Chcete-li tento problém vyřešit, nastavte čas místního systému co nejblíže k času v Internetu. Případně ho nastavte na čas v řadičích domény v síti.

## <a name="next-steps"></a>Další kroky

[Běžné problémy a řešení pomocí e-mailových profilů](../configuration/troubleshoot-email-profiles-in-microsoft-intune.md)

Získejte pomoc [od Microsoftu](../fundamentals/get-support.md)nebo využijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).