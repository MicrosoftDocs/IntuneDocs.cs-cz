---
title: "Vyřazení zařízení | Microsoft Intune"
description: "Při odebírání zařízení ze správy Intune podporuje tato služba selektivní i úplné vymazání, přičemž se odeberou příslušné zásady a portál společnosti."
keywords: 
author: staciebarker
ms.author: staciebarker
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
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 834f20a0280c2e3c4301e1a0769ed44c82a6bad0


---

# <a name="retire-devices-from-intune-management"></a>Vyřazení zařízení ze správy Intune

Nezáleží na tom, jestli zařízení patří společnosti nebo jednotlivci, nakonec ho bude potřeba odebrat ze správy v Intune. Vyřazení zařízení může mít různé důvody:

-   Uživatel opustí společnost plánovaným způsobem („spravovaný“ odchod).
-   Uživatel opustí společnost náhle (dostane výpověď, skončí atd.).
-   Dojde ke ztrátě zařízení.
-   Zařízení se začne používat jinak (přesune se k jinému uživateli, začne se používat jiným způsobem atd.).

Spravované mobilní zařízení můžete vymazat buď selektivně, nebo úplně. Můžete ho také zamknout a resetovat jeho heslo. Pokud zařízení vymažete, uvolníte předplatné uživatele, které můžete přidat jinému zařízení. Vyřadit můžete také počítače, které jsou spravované klientským softwarem Intune.

## <a name="wipe-data-and-apps-from-devices"></a>Vymazání dat a aplikací ze zařízení
Při selektivním i úplném vymazání se zařízení odebere ze správy v Intune tím, že se odeberou jeho zásady a portál společnosti. V zařízení tak nebudou přihlašovací údaje potřebné pro přihlášení k prostředkům společnosti, jako je Microsoft SharePoint, e-mail nebo Office 365.

[Selektivní vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) by se mělo upřednostňovat u zaměstnanců, kteří mají v Intune zaregistrované své vlastní zařízení, protože vymazání dat se v tomto případě nedotkne osobních údajů uložených na zařízení. Odeberou se jenom firemní data.

Pro zařízení, která je třeba přiřadit někomu jinému, můžete také použít [úplné vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), které resetuje zařízení do továrního nastavení.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Odstranění zařízení na portálu služby Azure Active Directory

1.  Přihlaste se přihlašovacími údaji vaší organizace na [http://aka.ms/accessaad](http://aka.ms/accessaad) nebo [https://portal.office.com](https://portal.office.com) a potom zvolte **Centra pro správu** &gt; **Azure AD**.

2.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, nepotřebujete k tomu platební kartu ani platbu. Vyberte odkaz na **registraci bezplatného předplatného Azure Active Directory**.

4.  Zvolte **Active Directory** a vyberte svoji organizaci.

5.  Zvolte kartu **Uživatelé**.

6.  Vyberte uživatele, kterému chcete odstranit zařízení.

7.  Zvolte **Zařízení**.

8.  Vyberte příslušná zařízení a zvolte **Odstranit zařízení**. Zařízení se vymaže při příští synchronizaci se službou Active Directory. To obvykle proběhne do čtyř hodin. Po synchronizaci se zařízení vyřadí ze správy. Tím se také odebere jedno zařízení z limitu počtu zařízení pro daného uživatele.

## <a name="retire-managed-computers"></a>Vyřazení spravovaných počítačů
Počítače spravované v klientském softwaru Intune je možné odebrat ze správy v konzole pro správu Intune. Tím se také z počítače odinstaluje klientský software a odstraní se z něj zásady Intune. Viz informace o [vyřazení počítačů spravovaných pomocí klientského softwaru Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## <a name="block-access-a-device"></a>Zablokování přístupu k zařízení
Při ztrátě zařízení nebo když ho musíte vyřadit, protože zaměstnanec opustil společnost, ale hardware vlastněný společností nevrátil zpět, také můžete [resetovat heslo a zařízení vzdáleně zamknout](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Tím se zajistí ochrana informací společnosti před zneužitím, i když může být nutné zařízení odepsat jako ztrátu.

Také můžete chtít odvolat licenci pro uživatelský účet Intune zaměstnance. Tím se licence uvolní a je možné ji přiřadit novému uživatelskému účtu.

## <a name="retire-hardware"></a>Vyřazení zařízení
V některých případech zařízení samotné dosáhne konce své životnosti. V takových případech [obnovením zařízení do továrního nastavení](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) s plným vymazáním odeberete všechna data a také odebere zařízení ze služby Intune. Pak můžete hardware vyřadit v souladu se zásadami společnosti.

### <a name="see-also"></a>Viz taky
[Lepší ochrana dat s využitím úplného nebo selektivního vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


