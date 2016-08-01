---
title: "Přidání uživatelů do 30denního testování Intune | Microsoft Intune"
description: "Postup přidání uživatelů, jednotlivě nebo hromadně, při registraci bezplatné 30denní zkušební verze Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: fb9c1cde3288b090961b46f0b47b32bfb67b6828


---

# Přidání uživatelů do 30denního testování Microsoft Intune
Teď, když jste nastavili svůj účet, použijte buď **Průvodce pro nové uživatele** pro přidání jednotlivých uživatelských účtů do Intune, nebo **Průvodce hromadným přidáním uživatelů** pro přidání uživatelů hromadně (viz pokyny v této části).  Než s tím začnete, je důležité, abyste rozuměli tomu, jak Intune zachází s účty správců.

Správce tenanta používá k přidání uživatele do **Skupiny uživatelů** Microsoft Intune centrum pro správu Office 365. Přidání uživatelů do  **Skupiny uživatelů** přiřadí uživatelům licence předplatného Intune a zároveň se tak tito uživatelé objeví v konzole pro správu Microsoft Intune.

Účty správce služby Intune se na rozdíl od běžných uživatelských účtů nevytváří v centru pro správu Office 365. Místo toho můžete uživatelům pomocí konzoly pro správu v pracovním prostoru **Správa** v rámci **Řízení správy** přiřadit oprávnění správce s přístupem jen pro čtení nebo s plným přístupem. Správci služeb, kteří mají přiřazená oprávnění jen pro čtení, nemůžou měnit nastavení Intune, ale můžou zobrazovat data a spouštět sestavy. Správci služeb s úplným přístupem mají k dispozici všechna práva správce.

Pomocí konzoly pro správu služby Intune je možné zobrazit informace správce klienta, ale není tady možné správce klientů vytvořit. Ve výchozím nastavení se vlastník předplatného stává správcem tenanta pro daný účet služby Microsoft Intune a má úplný přístup k centru pro správu Office 365 a konzole pro správu služby Intune. Doporučujeme, abyste prostřednictvím centra pro správu Office 365 vytvořili nejmíň jeden další účet správce tenanta, který vám pomůže delegovat úkoly a zároveň zaručí, že nezůstanete bez přístupu k účtu správce služby Intune, kdybyste zapomněli heslo.

## Přidání jednotlivých uživatelských účtů
Pomocí následujících kroků můžete ve zkušební verzi tenanta vytvořit další uživatelské účty. Pamatujte si, že každý přidaný uživatelský účet se počítá jako jedna ze 100 licencí, které jste získali v rámci bezplatné zkušební verze Intune.

1.  V [centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkID=787455) zvolte **Přidat uživatele** &gt; **Nový** &gt; **Uživatel** a spusťte průvodce **Noví uživatelé**.

2.  Na stránce **Podrobnosti** vyplňte požadovaná pole.

3.  Na stránce **Nastavení** nastavte **umístění** pro uživatele.

4.  Na stránce **Skupina** zvolte **Další**. Tím přijmete výchozí hodnoty a přiřadíte k uživatelskému účtu licenci pro Intune.

5.  Na stránce **E-mail** můžete zadat až pět e-mailových adres, na které přijde upozornění na uživatelské jméno a dočasné heslo k účtu. Jednotlivé e-mailové adresy oddělte středníkem (;). Až to uděláte, přidejte uživatele k předplatnému tím, že zvolíte **Vytvořit**.

6.  Na stránce **Výsledky** se zobrazí název nového účtu a jeho dočasné heslo. Intune automaticky vytvoří dočasné heslo.

7.  Až se nový uživatel zobrazí v centru pro správu Office 365, ověřte, že byl nový uživatel úspěšně vytvořený:

    1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Správa** &gt; **Portál společnosti** a posuňte se k dolnímu okraji obrazovky. Zkopírujte adresu URL v části **Portál společnosti Intune**.

    2.  Otevřete nové okno prohlížeče v režimu ochrany osobních údajů (v Internet Exploreru zvolte **Nástroje** &gt; **Procházení se službou InPrivate**) nebo otevřete nové okno prohlížeče na jiném zařízení a potom přejděte na adresu URL, kterou jste zkopírovali v předchozím kroku. Pokud se uživatel přihlašuje poprvé, musí zadat nové heslo účtu.

## Hromadné přidání uživatelů
Pro hromadné přidání uživatelů do Intune použijte **Průvodce hromadným přidáním uživatelů**, kde můžete nahrát textový soubor s oddělovači (CSV) obsahující uživatelská data. Odkazy v průvodci umožňují stáhnout prázdnou šablonu a ukázkový soubor CSV. První řádek souboru CSV musí ve správném pořadí obsahovat popisky jednotlivých sloupců dat uživatele. Pak musíte pro každého uživatele v souboru .csv uvést **uživatelské jméno** (třeba **jan@contoso.com**) a **zobrazované jméno** (třeba **Macek Jan**).

1.  V [centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkID=787455) zvolte **Uživatelé**&gt;**Nový**.

2.  Volbou **Hromadné přidání** spustíte Průvodce hromadným přidáním uživatelů.

3.  Na stránce **Vybrat soubor** zvolte **Procházet** a najděte a nahrajte existující soubor CSV z vašeho počítače. Můžete si taky stáhnout ukázkový soubor .csv nebo prázdný soubor šablony pomocí odkazů v průvodci .

4.  Na stránce **Ověření** si zkontrolujte výsledky a potom zobrazte další podrobnosti výběrem **Zobrazit**.

5.  Na stránce **Nastavení** zkontrolujte, že stav přihlášení je **Povoleno**, a nastavte **umístění**. Tato nastavení se vztahují na všechny uživatelské účty přidané prostřednictvím souboru .csv.

6.  Na stránce **Skupina** zvolte **Další**. Tím přijmete výchozí hodnoty a všem uživatelským účtům, které jste přidali pomocí souboru CSV, přiřadíte licenci pro Intune. Ve výchozím nastavení je zaškrtnuté políčko, kterým se ke všem uživatelským účtům přiřadí licence pro Intune.

7.  Na stránce **E-mail** můžete zadat až pět e-mailových adres, na které přijde upozornění na uživatelská jména a dočasná hesla, která Intune pro jednotlivé účty vytvoří. Jednotlivé e-mailové adresy oddělte středníkem (;). Zvolte **Vytvořit** a uživatelské účty se přidají k předplatnému.

8.  Na stránce **Výsledky** se zobrazí názvy uživatelských účtů a jejich dočasná hesla.

Všechny uživatelské účty, které jste přidali metodou importování, se teď zobrazují v uzlu **Uživatelé** centra pro správu Office 365. Noví uživatelé musí při prvním přihlášení zadat nové heslo ke svému uživatelskému účtu.

### Další kroky
Gratulujeme! Právě jste dokončili krok 2 příručky pro *testování Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Registrace k vyhodnocení**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Vytvoření skupin** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO4-->


