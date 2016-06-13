---
# required metadata

title: Pomoc při ochraně zařízení s iOS pomocí funkce Vynechat zámek aktivace | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Pomoc při ochraně zařízení s iOS pomocí funkce Vynechat zámek aktivace pro Microsoft Intune
Microsoft Intune vám může pomoci spravovat zámek aktivace v iOS – funkci aplikace Najít iPhone pro zařízení s iOS 7.1 a novějším. Zámek aktivace se povolí automaticky, když se na zařízení používá aplikace Najít iPhone. Když je tato funkce povolená, musí se zadat Apple ID a heslo uživatele, aby bylo možné:

-   Vypnout aplikaci Můj iPhone

-   Vymazat zařízení

-   Znovu aktivovat zařízení

## Jaký vliv má funkce Zámek aktivace na práci se zařízením
Funkce Zámek aktivace sice pomáhá zabezpečit zařízení se systémem iOS a zvyšuje šance na obnovení zařízení v případě, že dojde k jeho ztrátě nebo odcizení, ale pro vás, jakožto správce IT, může představovat určité problémy. Například:

-   Jeden z vašich uživatelů si na zařízení nastaví zámek aktivace. Tento uživatel pak společnost opustí a zařízení vrátí. Bez Apple ID a hesla uživatele neexistuje způsob, jak zařízení znovu aktivovat.

-   Potřebujete sestavu všech zařízení, která mají povolený zámek aktivace.

-   V rámci obnovování zařízení v organizaci chcete přiřadit některá zařízení jinému oddělení. Můžete to provést jedině se zařízeními, ve kterých není zámek aktivace povolený.

Aby bylo možné tyto problémy vyřešit, společnost Apple vydala v iOS 7.1 funkci vyřazení zámku aktivace. To vám umožní odebrat zámek aktivace z dozorovaných zařízeních i bez Apple ID a hesla uživatele. Dozorovaná zařízení mohou generovat kód pro vyřazení zámku aktivace, který je uložený na aktivačním serveru společnosti Apple.

> [!TIP]
> Dozorový režim pro zařízení s iOS vám umožňuje pomocí nástroje Apple Configurator zařízení zamknout a omezit tak jeho funkčnost jenom na konkrétní firemní účely. Dozorový režim je obecně určený výhradně pro zařízení v majetku podniků.

## Jak Intune pomáhá se správou zámku aktivace
Intune může požádat o stav zámku aktivace jak u dozorovaných, tak i u nedozorovaných zařízení, na kterých běží iOS 7.1 a novější. Pouze pro dozorovaná zařízení může služba Intune získat kód pro vyřazení zámku aktivace a přímo ho předat zařízení. Pokud bylo zařízení vymazáno, můžete k zařízení získat přístup tak, že jako uživatelské jméno zadáte tento kód a heslo necháte prázdné).

**Pro firmy to má tyto výhody**:

-   Uživatel získá výhody zabezpečení aplikace Najít iPhone.

-   Dokážete zajistit, aby uživatel mohl zařízení používat ke své práci, a zároveň budete vědět, že když bude nutné zařízení použít k jinému účelu, budete ho moct vyřadit nebo odemknout.

## Jak používat vyřazení zámku aktivace z konzoly pro správu služby Intune
> [!IMPORTANT]
> Po vyřazení zámku aktivace na zařízení se při otevření aplikace Najít iPhone automaticky použije nový zámek aktivace. Z tohoto důvodu **byste měli mít před provedením tohoto postupu zařízení fyzicky u sebe**.

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) vyberte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy**.

2.  Vyberte zařízení, jehož zámek aktivace chcete vyřadit. Vyberte volbu **Vynechat zámek aktivace**.

3.  Přečtěte si upozornění. Jestli chcete pokračovat, vyberte volbu **Ano**.

Stav požadavku na odemčení můžete zkontrolovat na stránce podrobností pro dané zařízení.

## Jak zjistit, která zařízení zámek aktivace používají
To, která zařízení zámek aktivace používají, můžete zjistit dvěma způsoby:

-   Spustíte **sestavy inventáře mobilních zařízení**. Tato sestava obsahuje sloupec **Stav zámku aktivace** a **Pod dohledem** , ze kterých je možné zjistit stav zařízení. Hodnoty pro sloupec **Pod dohledem** jsou **Ano** nebo **Ne**a hodnoty pro sloupec **Stav zámku aktivace** jsou:

    -   Povolené s kódem alternativní metody komunikace

    -   Povolené bez kódu alternativní metody komunikace (zařízení není pod dohledem)

    -   Povolené bez kódu alternativní metody komunikace (zařízení je nedostupné)

    -   Nepovolené

    U zařízení, na kterých neběží iOS 7.1 nebo novější, je pole **Stav zámku aktivace** prázdné.

-   V zobrazení skupin vyberte zařízení. Stav aktivace zámku uvidíte v podokně podrobností o zařízení.

    Pokud vyberete zařízení v uzlu **Všechna zařízení ve vlastnictví firmy** a zámek aktivace je pro zařízení povolený, uvidíte také kód pro vyřazení zámku. Pomocí tohoto kódu je možné ručně vyřadit zámek aktivace.

### Související témata
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md)
[Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)


<!--HONumber=May16_HO3-->


