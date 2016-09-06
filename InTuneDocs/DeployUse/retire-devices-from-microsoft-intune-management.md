---
title: "Vyřazení zařízení | Microsoft Intune"
description: "Při odebírání zařízení ze správy Intune podporuje tato služba selektivní i úplné vymazání, přičemž se odeberou příslušné zásady a portál společnosti."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: 29d13dcbc367c18d64f9522fa9a3b962226feebb


---

# Vyřazení zařízení ze správy Intune

Ať jsou zařízení vlastněná firmou nebo v osobním vlastnictví, nakonec přijde chvíle, kdy musí být spravované zařízení vyřazené ze správy v Intune. Zařízení může být vyřazené z různých důvodů:

-   Uživatel opustí společnost plánovaným způsobem („spravovaný“ odchod).
-   Uživatel opustí společnost náhle (dostane výpověď, skončí atd.).
-   Dojde ke ztrátě zařízení.
-   Zařízení se začne používat jinak (přesune se k jinému uživateli, začne se používat jiným způsobem atd.).

U mobilních zařízení můžete provést buď selektivní vymazání, nebo úplné vymazání. Další možností je zamknout zařízení a resetovat heslo. Pokud zařízení vymažete, uvolníte tak předplatné příslušného uživatele pro jiné zařízení. Pomocí klientského softwaru Intune můžete také vyřadit počítače s Windows.

## Vymazání dat a aplikací ze zařízení
Selektivní vymazání i úplné vymazání odebere zařízení ze správy Intune odebráním zásad a portálu společnosti, což znamená, že zařízení už nemá pověřovací údaje potřebné k přihlášení k firemním prostředkům, jako je Microsoft SharePoint, e-mail nebo Office 365.

[Selektivní vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) by se mělo upřednostňovat u zaměstnanců, kteří mají v Intune zaregistrované své vlastní zařízení, protože vymazání dat se v tomto případě nedotkne osobních údajů uložených na zařízení. Odeberou se jenom firemní data.

Pro zařízení, která je třeba přiřadit někomu jinému, můžete také použít [úplné vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), které resetuje zařízení do továrního nastavení.

## Odstranění zařízení na portálu služby Azure Active Directory

1.  Přihlaste se s přihlašovacími údaji vaší společnosti na adrese [http://aka.ms/accessaad](http://aka.ms/accessaad) nebo [https://portal.office.com](https://portal.office.com) a vyberte možnost **Centra pro správu** &gt; **Azure AD**.

2.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (zvolte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory**).

4.  Vyberte možnost **Active Directory** a potom vyberte svoji organizaci.

5.  Vyberte kartu **Uživatelé** .

6.  Vyberte uživatele, jehož zařízení chcete odstranit.

7.  Zvolte **Zařízení**.

8.  Vyberte požadované zařízení a zvolte **Odstranit zařízení**. Zařízení se vymaže při příští synchronizaci se službou Active Directory. To obvykle proběhne do 4 hodin. Po synchronizaci se zařízení vyřadí ze správy. Tím se také odebere jedno zařízení z limitu počtu zařízení pro daného uživatele.

## Vyřazení spravovaných počítačů
Počítače spravované klientským softwarem Intune je možné odebrat ze správy pomocí konzoly Správce Intune. Tím se také z počítače odinstaluje klientský software a odstraní zásady Intune. Viz informace o [vyřazení počítačů spravovaných pomocí klientského softwaru Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Zablokování přístupu k zařízení
V případě ztráty zařízení nebo když potřebujete vyřadit zařízení v majetku společnosti, které odcházející zaměstnanec nevrátil, můžete také [resetovat heslo a vzdáleně uzamknout](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) zařízení. Tím se zajistí ochrana informací společnosti před zneužitím, i když může být nutné zařízení odepsat jako ztrátu.

Také můžete chtít odvolat licenci pro uživatelský účet Intune zaměstnance. Tím se licence uvolní a bude možné ji přiřadit novému uživatelskému účtu.

## Vyřazení zařízení
V některých případech zařízení samotné dosáhne konce své životnosti. V takových případech [obnovením zařízení do továrního nastavení](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) s plným vymazáním odeberete všechna data a také odebere zařízení ze služby Intune. Pak můžete hardware vyřadit z evidence podle zásad vaší společnosti.

### Viz taky
[Lepší ochrana dat s využitím úplného nebo selektivního vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


