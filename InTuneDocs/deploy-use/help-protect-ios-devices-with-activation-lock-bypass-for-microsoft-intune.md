---
title: "Správa zámku aktivace iOS na zařízeních | Dokumentace Microsoftu"
description: "Microsoft Intune vám může pomoci spravovat zámek aktivace v iOSu – funkci aplikace Najít iPhone pro zařízení s iOSem 7.1 a novějším."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 742fac9c401c24bfc0f2500a238c41fa00c47fd3
ms.lasthandoff: 04/24/2017


---

# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>Pomoc při ochraně zařízení s iOSem pomocí funkce Vynechat zámek aktivace pro Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune vám může pomoci spravovat zámek aktivace v iOSu – funkci aplikace Najít iPhone pro zařízení s iOSem 8.0 a novějším. Zámek aktivace je automaticky zapnutý, když uživatel na zařízení otevře aplikaci Najít iPhone. Když je tato funkce povolená, musí se zadat Apple ID a heslo uživatele, aby bylo možné: 

-   Vypnout aplikaci Můj iPhone

-   Vymazat zařízení

-   Znovu aktivovat zařízení

## <a name="how-activation-lock-affects-you"></a>Jaký vliv má funkce Zámek aktivace na práci se zařízením
Funkce Zámek aktivace sice pomáhá zabezpečit zařízení se systémem iOS a zvyšuje šance na obnovení zařízení v případě, že dojde k jeho ztrátě nebo odcizení, ale pro vás, jakožto správce IT, může představovat určité problémy. Například:

-   Uživatel si na zařízení nastaví zámek aktivace. Tento uživatel pak společnost opustí a zařízení vrátí. Bez Apple ID a hesla uživatele neexistuje způsob, jak zařízení znovu aktivovat.

-   Potřebujete sestavu všech zařízení, která mají povolený zámek aktivace.

-   Při obnovování zařízení v organizaci chcete některá zařízení přiřadit jinému oddělení. Můžete to provést jedině se zařízeními, ve kterých není zámek aktivace povolený.

Aby bylo možné tyto problémy vyřešit, společnost Apple vydala v iOSu 7.1 funkci vyřazení zámku aktivace. To vám umožní odebrat zámek aktivace z dozorovaných zařízeních i bez Apple ID a hesla uživatele. Dozorovaná zařízení mohou generovat kód pro vyřazení zámku aktivace, který je uložený na aktivačním serveru společnosti Apple.

> [!TIP]
> Režim Pod dohledem pro zařízení s iOSem vám umožňuje pomocí Apple Configuratoru zařízení zamknout a omezit tak jeho funkčnost jenom na konkrétní firemní účely. Dozorový režim je obecně určený výhradně pro zařízení v majetku podniků.

Další informace o zámku aktivace najdete [zde](https://support.apple.com/en-us/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak Intune pomáhá se správou zámku aktivace
Intune může požádat o stav zámku aktivace u dozorovaných zařízení, na kterých běží iOS 8.0 a novější. Pouze pro dozorovaná zařízení může služba Intune získat kód pro vyřazení zámku aktivace a přímo ho předat zařízení. Pokud bylo zařízení vymazáno, můžete k němu získat přístup přímo tak, že uživatelské jméno necháte prázdné a jako heslo zadáte tento kód.

**Pro firmy to má tyto výhody**:

-   Uživatel získá výhody zabezpečení aplikace Najít iPhone.

-   Dokážete zajistit, aby uživatel mohl zařízení používat ke své práci, a zároveň budete vědět, že když bude nutné zařízení použít k jinému účelu, budete ho moct vyřadit nebo odemknout.

## <a name="before-you-start"></a>Než začnete

Než budete moct zámek aktivace na zařízeních vyřadit, musíte ho nejdřív povolit. Provedete to následujícím způsobem:

1. Podle pokynů v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) vytvořte [zásady konfigurace zařízení](/intune/deploy-use/ios-policy-settings-in-microsoft-intune) pro iOS.
2. Na stránce nastavení v části **Registrace** nakonfigurujte nastavení **Povolit zámek aktivace, když je zařízení v režimu pod dohledem** na **Ano**.
3. Zásady uložte a nasaďte je na zařízení, na kterých chcete spravovat vyřazení zámku aktivace.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Jak používat vyřazení zámku aktivace z konzoly pro správu služby Intune
> [!IMPORTANT]
> Po vyřazení zámku aktivace na zařízení se při otevření aplikace Najít iPhone automaticky použije nový zámek aktivace. Z tohoto důvodu **byste měli mít před provedením tohoto postupu zařízení fyzicky u sebe**.

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) vyberte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy**.

2.  Vyberte zařízení, jehož zámek aktivace chcete vyřadit. Vyberte volbu **Vynechat zámek aktivace**.

3.  Přečtěte si upozornění. Jestli chcete pokračovat, vyberte volbu **Ano**.

Stav požadavku na odemčení můžete zkontrolovat na stránce podrobností pro dané zařízení.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Jak zjistit, která zařízení zámek aktivace používají
To, která zařízení zámek aktivace používají, můžete zjistit dvěma způsoby:

-   Spustíte **sestavy inventáře mobilních zařízení**. Tato sestava obsahuje sloupce **Stav zámku aktivace** a **Pod dohledem**, ve kterých je možné zjistit stav zařízení. Hodnoty pro sloupec **Pod dohledem** jsou **Ano** nebo **Ne**a hodnoty pro sloupec **Stav zámku aktivace** jsou:

    -   Povolené s kódem alternativní metody komunikace

    -   Povolené bez kódu alternativní metody komunikace (zařízení není pod dohledem)

    -   Povolené bez kódu alternativní metody komunikace (zařízení je nedostupné)

    -   Nepovolené

    U zařízení, která nepoužívají iOS 8.0 nebo novější, je pole **Stav zámku aktivace** prázdné.

-   V zobrazení skupin vyberte zařízení. Stav aktivace zámku uvidíte v podokně podrobností o zařízení.

    Pokud vyberete zařízení v uzlu **Všechna zařízení ve vlastnictví firmy** a zámek aktivace je pro zařízení povolený, uvidíte také kód pro vyřazení zámku. Pomocí tohoto kódu je možné ručně vyřadit zámek aktivace.

    > [!IMPORTANT]
    >Intune přebírá inventář ze zařízení kvůli zámku aktivace každých sedm dní. Z tohoto důvodu se zařízení nemusí v konzole Intune okamžitě zobrazit s jejich stavem zámku aktivace stav.


### <a name="see-also"></a>Související témata
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md)
[Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

