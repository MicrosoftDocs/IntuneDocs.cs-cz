---
title: "Řešení potíží se zásadami | Microsoft Intune"
description: "Řešení potíží s konfigurací zásad"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: fbc18b12c00a4b61f7419731c6b4306b583638cc


---

# Řešení potíží se zásadami v Microsoft Intune

Pokud máte potíže s nasazením a správou zásad v Intune, začněte zde. Toto téma popisuje některé běžné problémy, na které můžete narazit, a jejich řešení.

## Běžné problémy

### Použili jste na zařízení nasazené zásady?
**Problém:** Nejste si jisti, jestli jste správně použili zásady.

V konzole pro správu služby Intune má každé zařízení v části **Vlastnosti zařízení**vlastní kartu zásad. Každá zásada má **určenou hodnotu** a **Stav**. Určená hodnota označuje to, čeho chcete dosáhnout při přiřazování zásady. Stav označuje to, co se skutečně použije, když jsou společně zpracovány všechny zásady platné pro zařízení a všechna omezení a požadavky na hardware a operační systém. Možné stavy:

-   **Vyhovuje**: Zařízení přijalo zásady a hlásí službě, že vyhovuje danému nastavení.

-   **Nepoužívá se**: Nastavení zásad se nedá použít. Například nastavení e-mailu pro zařízení se systémem iOS se nedají použít pro zařízení se systémem Android.

-   **Čeká na vyřízení**: Došlo k odeslání zásady do zařízení a to ještě nenahlásilo službě svůj stav. Na vyřízení může čekat třeba šifrování v systému Android, které vyžaduje, aby šifrování povolil uživatel.

Na tomto snímku obrazovky vidíte dva jasné příklady:

-   Možnost **Povolit jednoduchá hesla** je nastavená na **Ano**, jak ukazuje sloupec **Určená hodnota**, ale její **Stav** je **Nepoužívá se**. Důvodem je, že se na zařízeních s Androidem nepodporují jednoduchá hesla.

-   Podobně pak u tohoto zařízení není použitá rozšířená položka zásad **Nastavení e-mailu pro zařízení iOS**, protože to je zařízení s Androidem.

![Zásady zařízení Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Mějte na paměti, že když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, v praxi se uplatní víc omezující zásada.


## Problémy s registrovanými zařízení

### Výstraha: Uložení pravidel přístupu do systému Exchange se nezdařilo
**Problém**: V konzole pro správu se objeví výstraha **Uložení pravidel přístupu do systému Exchange se nezdařilo**  .

Pokud jste vytvořili zásady v pracovním prostoru Zásady pro místní Exchange v konzole pro správu, ale používáte služby O365, služba Intune nebude nakonfigurované nastavení zásad vynucovat. Poznamenejte si zdroj zásad uvedený ve výstraze.  V pracovním prostoru Zásady pro místní Exchange odstraňte zastaralá pravidla, protože se jedná o globální pravidla Exchange v rámci Intune pro místní Exchange a nevztahují se na služby O365. Pak vytvořte nové zásady pro služby O365.

### Nejde změnit zásady zabezpečení pro různá zaregistrovaná zařízení
Zařízení s Windows Phone neumožňují zmírnění zásad zabezpečení nastavených přes MDM nebo EAS potom, co je nastavíte. Nastavíte třeba **Minimální počet znaků hesla** na hodnotu 8 a tu se pak pokusíte snížit na 4. V zařízení se už ale používá více omezující zásada.

Pokud chcete zásadu změnit na méně zabezpečenou hodnotu, v závislosti na platformě zařízení může být potřeba resetovat zásady zabezpečení.
Například ve Windows otevřete potáhnutím prstu z pravého okraje plochy panel **ovládacích tlačítek** a zvolte **Nastavení** &gt; **Ovládací panely**.  Vyberte aplet **Uživatelské účty** .
V navigační nabídce vlevo najdete dole odkaz **Resetovat zásady zabezpečení** . Zvolte jej a potom zvolte tlačítko **Resetovat zásady** .
Jiná zařízení MDM, třeba zařízení se systémy Android, Windows Phone 8.1 (a novějšími) a iOS, může být potřeba vyřadit a znovu zaregistrovat do služby, abyste mohli aplikovat méně omezující zásadu.

## Problémy s počítači, které používají klientský software Intune

### Chyby související se zásadami Microsoft Intune v souboru policyplatform.log
U počítačů s Windows spravovaných pomocí klientského softwaru Intune můžou být chyby zásad v souboru policyplatform.log výsledkem jiného než výchozího nastavení nástroje Řízení uživatelských účtů v systému Windows (UAC) v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

#### Řešení potíží s UAC

1.  Vyřaďte počítač, jak je popsané v tématu [Vyřazení zařízení ze správy službou Microsoft Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat pomocí panelu Programy a funkce.

3.  V nabídce Start zadejte **UAC**. Otevře se nastavení nástroje Řízení uživatelských účtů.

4.  Nastavte posuvník oznámení na výchozí nastavení.

### CHYBA: Nelze získat hodnotu z počítače, 0x80041013
K této chybě může dojít, pokud se místní systém nesynchronizuje delší dobu než pět minut. Pokud není čas v místním počítači synchronizovaný, zabezpečené transakce se nepodaří, protože budou mít neplatná časová razítka.

Pokud chcete tento problém vyřešit, nastavte místní čas počítače co nejblíž internetovému času nebo času nastavenému na řadičích domény v síti.








### Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Oct16_HO2-->


