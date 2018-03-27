---
title: Řešení potíží se zásadami
description: Řešení potíží s konfigurací zásad
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7f9632a8b769fae5c3ae0fdf7041b968a9707d24
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="troubleshoot-policies-in-microsoft-intune"></a>Řešení potíží se zásadami v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud máte potíže s nasazením a správou zásad v Intune, začněte tady. Toto téma popisuje některé běžné problémy, na které můžete narazit, a jejich řešení.

## <a name="general-issues"></a>Běžné problémy

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Použili jste na zařízení nasazené zásady?
**Problém:** Nejste si jisti, jestli jste správně použili zásady.

V konzole pro správu služby Intune má každé zařízení v části **Vlastnosti zařízení**vlastní kartu zásad. U každé zásady je **Zamýšlená hodnota** a **Stav**. Určená hodnota označuje to, čeho chcete dosáhnout při přiřazování zásady. Stav označuje to, co se skutečně použije, když jsou společně zpracovány všechny zásady platné pro zařízení a všechna omezení a požadavky na hardware a operační systém. Možné stavy:

-   **Vyhovuje**: Zařízení přijalo zásady a hlásí službě, že vyhovuje danému nastavení.

-   **Nepoužívá se**: Nastavení zásad se nedá použít. Například nastavení e-mailu pro zařízení se systémem iOS se nedají použít pro zařízení se systémem Android.

-   **Čeká na vyřízení**: Došlo k odeslání zásady do zařízení a to ještě nenahlásilo službě svůj stav. Na vyřízení může čekat třeba šifrování v systému Android, které vyžaduje, aby šifrování povolil uživatel.

Na tomto snímku obrazovky vidíte dva jasné příklady:

-   Možnost **Povolit jednoduchá hesla** je nastavená na **Ano**, jak ukazuje sloupec **Určená hodnota**, ale její **Stav** je **Nepoužívá se**. Důvodem je, že se na zařízeních s Androidem nepodporují jednoduchá hesla.

-   Podobně pak u tohoto zařízení není použitá rozšířená položka zásad **Nastavení e-mailu pro zařízení iOS**, protože to je zařízení s Androidem.

![Zásady zařízení Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Mějte na paměti, že když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, v praxi se uplatní víc omezující zásada.


## <a name="issues-with-enrolled-devices"></a>Problémy s registrovanými zařízení

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Výstraha: Uložení pravidel přístupu do systému Exchange se nezdařilo
**Problém**: V konzole pro správu se objeví výstraha **Uložení pravidel přístupu do systému Exchange se nezdařilo**  .

Pokud jste vytvořili zásady v pracovním prostoru Zásady pro místní Exchange v konzole pro správu, ale používáte služby O365, služba Intune nebude nakonfigurované nastavení zásad vynucovat. Poznamenejte si zdroj zásad uvedený ve výstraze.  V pracovním prostoru Zásady pro místní Exchange odstraňte zastaralá pravidla, protože se jedná o globální pravidla Exchange v rámci Intune pro místní Exchange a nevztahují se na služby O365. Pak vytvořte nové zásady pro služby O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Nejde změnit zásady zabezpečení pro různá zaregistrovaná zařízení
Zařízení s Windows Phone neumožňují zmírnění zásad zabezpečení nastavených přes MDM nebo EAS potom, co je nastavíte. Nastavíte třeba **Minimální počet znaků hesla** na hodnotu 8 a tu se pak pokusíte snížit na 4. V zařízení se už ale používá více omezující zásada.

Pokud chcete zásadu změnit na méně zabezpečenou hodnotu, v závislosti na platformě zařízení může být potřeba resetovat zásady zabezpečení.
Například ve Windows otevřete potáhnutím prstu z pravého okraje plochy panel **ovládacích tlačítek** a zvolte **Nastavení** &gt; **Ovládací panely**.  Vyberte aplet **Uživatelské účty** .
V navigační nabídce vlevo najdete dole odkaz **Resetovat zásady zabezpečení** . Zvolte jej a potom zvolte tlačítko **Resetovat zásady** .
Jiná zařízení MDM, třeba zařízení se systémy Android, Windows Phone 8.1 (a novějšími) a iOS, může být potřeba vyřadit a znovu zaregistrovat do služby, abyste mohli aplikovat méně omezující zásadu.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problémy s počítači, které používají klientský software Intune

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Chyby související se zásadami Microsoft Intune v souboru policyplatform.log
U počítačů s Windows spravovaných pomocí klientského softwaru Intune můžou být chyby zásad v souboru policyplatform.log výsledkem jiného než výchozího nastavení nástroje Řízení uživatelských účtů v systému Windows (UAC) v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

#### <a name="to-resolve-uac-issues"></a>Řešení potíží s UAC

1.  Vyřaďte počítač, jak je popsané v tématu [Vyřazení zařízení ze správy službou Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat pomocí panelu Programy a funkce.

3.  V nabídce Start zadejte **UAC**. Otevře se nastavení nástroje Řízení uživatelských účtů.

4.  Nastavte posuvník oznámení na výchozí nastavení.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>CHYBA: Nelze získat hodnotu z počítače, 0x80041013
K této chybě může dojít, pokud se místní systém nesynchronizuje delší dobu než pět minut. Pokud není čas v místním počítači synchronizovaný, zabezpečené transakce se nepodaří, protože budou mít neplatná časová razítka.

Pokud chcete tento problém vyřešit, nastavte místní čas počítače co nejblíž internetovému času nebo času nastavenému na řadičích domény v síti.








### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
