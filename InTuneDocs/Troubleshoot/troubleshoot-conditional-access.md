---
title: "Řešení potíží s podmíněným přístupem | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f79d2890c450a803bfb84ffa3c12b0de58a158c
ms.openlocfilehash: 373b9bf9794840f999d5e5b21fc411ff621a23e1


---

# Řešení potíží s podmíněným přístupem

Toto téma popisuje, co dělat, pokud se vašim uživatelům nedaří získat přístup k prostředkům prostřednictvím podmíněného přístupu Intune. 

### Základní informace potřebné pro úspěšné využívání podmíněného přístupu

Aby bylo možné využívat podmíněný přístup, je třeba splnit následující podmínky:

-   Zařízení musí být spravováno pomocí Intune.
-   Uživatel musí být zaregistrován v Azure Active Directory (AAD).
-   Zařízení musí vyhovovat zásadám dodržování předpisů, které jste nakonfigurovali v Intune. 
-   V zařízení musí být aktivováno EAS, pokud uživatel načítá e-mail prostřednictvím nativního poštovního klienta, a nikoli prostřednictvím aplikace Outlook.

Tyto podmínky lze zobrazit pro každé zařízení v portálu pro správu Azure a v sestavě inventáře zařízení.





Obvykle se uživatel pokusí o přístup k e-mailu nebo ke službě SharePoint a obdrží výzvu k registraci. Prostřednictvím této výzvy přejde uživatele na portál společnosti. Zde jsou možná vysvětlení tohoto chování spolu s navrhovanými řešeními:

## Scénáře s moderním ověřováním

### Problémy s registrací

 -  Zařízení není zaregistrované, takže registrace tento problém odstraní.
 -  Uživatel zařízení zaregistroval, ale připojení k pracovišti se nezdařilo. Uživatel by měl aktualizovat registraci z portálu společnosti. 
 
### Problémy se shodou

 -  Zařízení nevyhovuje zásadám Intune. K běžným problémům patří požadavky na šifrování a heslo. Uživatel bude přesměrován na portál společnosti, kde může nakonfigurovat zařízení tak, aby vyhovovalo požadavkům.
 -  Pro zařízení s iOS bude existující e-mailový profil vytvořený uživatelem blokovat nasazení vyhovujícího profilu (vytvořeného správcem Intune) z Intune. Tento problém je běžný, protože uživatelé s iOS obvykle vytvoří e-mailový profil a potom se zaregistrují. Portál společnosti bude uživatele informovat o tom, že požadavky nejsou splněny kvůli ručně nakonfigurovanému e-mailovému profilu a vyzve uživatele k odebrání příslušného profilu. Uživatel by měl svůj e-mailový profil odebrat, aby bylo možné nasadit profil Intune. Chcete-li problémům zabránit, požádejte své uživatele, aby se zaregistrovali bez instalace e-mailového profilu a aby Intune povolili nasazení profilu.  
 -  Registrace informací o shodě pro zařízení může trvat nějakou dobu. Počkejte několik minut a zkuste akci zopakovat.

### problémy se zásadami;

Když vytvoříte zásady dodržování předpisů a propojíte je se zásadami e-mailů, musí být obojí zásady nasazeny pro téhož uživatele. Buďte proto opatrní při plánování, které zásady skupiny budou nasazeny pro které skupiny. Uživatelé s jedinou použitou zásadou pravděpodobně zjistí, že jejich zařízení nevyhovují.


## Situace s protokolem Exchange ActiveSync


- Zařízení s Androidem, které je zaregistrované a vyhovující, může i přesto obdržet oznámení o karanténě při pokusu o přístup k podnikovým prostředkům. Před zvolením odkazu s textem **Začít** by uživatel měl ověřit, že při pokusu o přístup k prostředkům nebyl portál společnosti otevřený. Uživatelé by měli zavřít portál společnosti, znovu se pokusit o přístup k prostředkům a pak zvolit odkaz **Začít**.

- Vyřazené zařízení může mít stále přístup i několik hodin po vyřazení. Důvodem je skutečnost, že Exchange ukládá přístupová práva do mezipaměti na 6 hodin. Zvažte možnost použití jiných způsobů ochrany dat na vyřazených zařízení v tomto scénáři.
- Možný problém: Nelze opravit EASID podle AAD. Obvyklou příčinou tohoto problému je omezování, proto počkejte několik minut a zkuste akci zopakovat. 

## Shromažďování protokolů poštovní schránky aplikace OWA

Pokud vaše potíže s připojením k Exchangi trvají po odstranění problémů s nasazením, shromážděte protokoly poštovní schránky aplikace OWA, než se obrátíte na podporu společnosti Microsoft podle popisu v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

1. Přihlaste se prostřednictvím aplikace OWA a zvolte symbol nastavení (ozubené kolečko) vedle vašeho jména v pravém horním rohu. 
2. Zvolte **Možnosti**
3. Ve sloupci na levé straně zvolte **Telefon** (může být uvedeno **Mobilní zařízení**).
4. V hlavní nabídce zvolte **Mobilní zařízení**. 
5. V seznamu zvolte příslušné zařízení a pak zvolte **Spustit protokolování**. 
6. Po zobrazení výzvy zvolte v místním dialogovém okně **Ano**. 
7. Proveďte akci, která způsobila problém, abyste ho znovu vyvolali. 
8. Počkejte 1–2 minuty, pak se vraťte k telefonnímu seznamu v aplikaci OWA (ověřte, že váš telefon v seznamu vybrán) a z hlavní nabídky zvolte **Načíst protokol**. 
9. Nyní byste měli od sebe sama obdržet e-mail s přílohou. Při otevření lístku podpory předejte obsah e-mailu podpoře společnosti Microsoft.


### Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Jun16_HO4-->


