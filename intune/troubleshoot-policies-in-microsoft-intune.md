---
title: Řešení potíží se zásadami v Microsoft Intune – Azure | Microsoft Docs
description: Běžné problémy nebo problémy a řešení při používání zásad v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: bb55ddc283ce4633b5057d5b96ae2ed6973dcf8a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181764"
---
# <a name="troubleshoot-policies-in-intune"></a>Řešení potíží se zásadami v Intune

Pokud máte potíže s nasazením a správou zásad v Intune, začněte tady. Tento článek popisuje některé z běžných problémů, na které můžete narazit, a jejich možná řešení.

## <a name="general-issues"></a>Běžné problémy

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Použili jste na zařízení nasazené zásady?
**Problém:** Nejste si jistí, jestli jste zásady použili správně.

V Intune > **Zařízení** > **Všechna zařízení** > vyberte požadované zařízení > **Konfigurace zařízení**. Každé zařízení uvádí seznam svých zásad. Každá zásada má **Stav**. Stav se použije, když jsou společně zpracovány všechny zásady platné pro zařízení, včetně veškerých omezení a požadavků na hardware a operační systém. Možné stavy:

- **Vyhovuje**: Zařízení přijalo zásady a hlásí službě, že vyhovuje danému nastavení.

- **Nepoužívá se**: Nastavení zásad se nedá použít. Například nastavení e-mailu pro zařízení se systémem iOS se nedají použít pro zařízení se systémem Android.

- **Čeká na vyřízení**: Došlo k odeslání zásady do zařízení a to ještě nenahlásilo službě svůj stav. Na vyřízení může čekat třeba šifrování v systému Android, které vyžaduje, aby šifrování povolil uživatel.

> [!NOTE]
> Když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, uplatní se víc omezující zásada.

## <a name="issues-with-enrolled-devices"></a>Problémy s registrovanými zařízení

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Výstraha: Uložení pravidel přístupu do systému Exchange se nezdařilo
**Problém**: V konzole pro správu se objeví výstraha **Uložení pravidel přístupu do systému Exchange se nezdařilo**  .

Pokud jste vytvořili zásady v pracovním prostoru Zásady místního systému Exchange v konzole pro správu, ale používáte služby O365, pak služba Intune nebude nakonfigurované nastavení zásad vynucovat. Poznamenejte si zdroj zásad uvedený ve výstraze.  V pracovním prostoru Zásady místního systému Exchange odstraňte zastaralá pravidla. Zastaralá pravidla jsou globální pravidla Exchange v rámci Intune pro místní Exchange a nevztahují se na služby O365. Pak vytvořte nové zásady pro služby O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Nejde změnit zásady zabezpečení pro různá zaregistrovaná zařízení
Zařízení s Windows Phone neumožňují zmírnění zásad zabezpečení nastavených přes MDM nebo EAS potom, co je nastavíte. Nastavíte třeba **Minimální počet znaků hesla** na hodnotu 8 a tu se pak pokusíte snížit na 4. V zařízení se už ale používá více omezující zásada.

Pokud chcete zásadu změnit na méně zabezpečenou hodnotu, v závislosti na platformě zařízení může být potřeba resetovat zásady zabezpečení.

Například ve Windows otevřete panel **ovládacích tlačítek** potáhnutím prstu z pravého okraje plochy. Zvolte **Nastavení** > **Ovládací panely** a vyberte **Uživatelské účty**. Na levé straně vyberte odkaz **Resetovat zásady zabezpečení** a zvolte **Resetovat zásady**.

Aby se mohly u jiných zařízení MDM, například zařízení se systémy Android, Windows Phone 8.1 (a novějšími) a iOS, použít méně omezující zásady, může být potřeba je vyřadit a potom je do služby znovu zaregistrovat.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problémy s počítači, které používají klientský software Intune

Platí pro klasický portál.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Chyby související se zásadami Microsoft Intune v souboru policyplatform.log
U počítačů s Windows spravovaných pomocí klientského softwaru Intune můžou být chyby zásad v souboru policyplatform.log výsledkem jiného než výchozího nastavení nástroje Řízení uživatelských účtů v systému Windows (UAC) v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

#### <a name="resolve-uac-issues"></a>Řešení potíží s UAC

1. Vyřaďte počítač. Zobrazte si [Odebrání zařízení](devices-wipe.md).

2. Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat z nabídky Programy a funkce.

3. V nabídce Start zadejte **UAC**. Otevře se nastavení nástroje Řízení uživatelských účtů.

4. Nastavte posuvník oznámení na výchozí nastavení.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>CHYBA: Nelze získat hodnotu z počítače, 0x80041013
K této chybě může dojít, pokud se místní systém nesynchronizuje více než pět minut. Pokud není čas v místním počítači synchronizovaný, zabezpečené transakce se nepodaří, protože budou mít neplatná časová razítka.

Pokud chcete tento problém vyřešit, nastavte místní čas počítače co nejblíž internetovému času nebo času nastavenému na řadičích domény v síti.

### <a name="next-steps"></a>Další postup
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](get-support.md).
