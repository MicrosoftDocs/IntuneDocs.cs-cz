---
title: "Nastavení zásad Exchange ActiveSync | Microsoft Intune"
description: "Pomocí zásady Intune pro Exchange ActiveSync můžete nakonfigurovat nastavení, které vám umožní ovládat funkce v zařízeních spravovaných protokolem Exchange ActiveSync."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 7cdb34c469d2932deb10deec592a899b9848226a


---

# Nastavení zásad Exchange ActiveSync v Microsoft Intune
Pomocí zásady pro Microsoft Intune **Exchange ActiveSync** můžete nakonfigurovat nastavení, které vám umožní ovládat řadu funkcí v zařízení spravovaných protokolem Exchange ActiveSync.


## Nastavení hesla

|Název nastavení|Podrobnosti
|----------------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Určuje, jestli zařízení musí být zamčená s použitím hesla.<br>(nevztahuje se na zařízení s Windows RT)|
|**Vyžadovaný typ hesla**|Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|
|**Minimální délka hesla**|Určuje minimální počet znaků, které musí heslo zařízení obsahovat.|
|**Povolit jednoduchá hesla**|Příklady jednoduchých hesel: 0000 a 1234.|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Povolí toto množství pokusů na zadání správného hesla před vymazáním zařízení.|
|**Omezená platnost hesla (ve dnech)**|Určuje počet dní, po jejichž uplynutí bude nutné změnit heslo zařízení.
|**Pamatovat si historii hesel**|Určuje, jestli má být povolené použití dříve použitých hesel.|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, které nejde znovu použít.|
|**Počet minut nečinnosti před vyžadováním hesla**|Určuje dobu, po kterou musí být zařízení v nečinnosti, než se uzamkne jeho obrazovka.

## Nastavení šifrování

|Název nastavení|Podrobnosti|
|----------------|
|**Vyžadovat šifrování u mobilního zařízení**<sup>1</sup>|Je-li to podporováno, vyžaduje se šifrování dat v zařízení.<br>Pro zařízení s Windows Phone 8 je potřeba nastavit hodnotu **Ano**.<br /><br />Pokud chcete povolit šifrování na zařízeních iOS, povolte nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.|
|**Vyžadovat šifrování u paměťových karet**|Vyžaduje šifrování dat uložených v externích úložištích, jako je karta SD (u podporovaných zařízení).
<sup>1</sup> Další informace pro zařízení s Windows 8.1

-   K vynucení šifrování na zařízeních s Windows 8.1 je potřeba na každé zařízení nainstalovat [aktualizaci MDM klienta pro Windows z prosince 2014](http://support.microsoft.com/kb/3013816) .

-   Pokud toto nastavení povolíte pro zařízení s Windows 8.1, všichni uživatelé zařízení musí mít účet Microsoft.

-   Šifrování funguje, jenom když zařízení splňuje hardwarové požadavky certifikace Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) .

-   Pokud vynutíte šifrování na zařízení, je obnovovací klíč přístupný jenom uživatelům s účtem Microsoft, ke kterému přistupují z účtu na Onedrivu. Tento klíč se nedá obnovit jménem uživatele.

## Nastavení e-mailu

|Název nastavení|Podrobnosti
|----------------|
|**Povolit uživatelům stahovat přílohy e-mailů**|Určuje, jestli lze do zařízení stahovat přílohy e-mailu.|
|**Interval synchronizace e-mailu**|Vyberte počet dnů přijatých e-mailů, které budou synchronizované v zařízení.
|**Povolit mobilním zařízením, která plně nepodporují nastavení Exchange ActiveSync, synchronizaci se serverem Exchange**|Určuje, jestli má mít Exchange povolený přístup k zařízením, která nepodporují jedno nebo více nastavení Exchange ActiveSync.

## Nastavení prohlížeče

|Název nastavení|Podrobnosti
|----------------|-
|**Povolit webový prohlížeč**|Určuje, jestli je možné použít webový prohlížeč v zařízení.<br>(není dostupné pro Windows RT nebo Windows Phone)

## Nastavení hardwaru

|Název nastavení|Podrobnosti
|----------------|
|**Povolit fotoaparát**|Určuje, jestli je možné použít fotoaparát v zařízení.<br>(není dostupné pro Windows RT nebo Windows Phone)



### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


