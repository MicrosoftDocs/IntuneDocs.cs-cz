---
title: "Vyřazení zařízení"
description: "Při odebírání zařízení ze správy Intune podporuje tato služba selektivní i úplné vymazání, přičemž se odeberou příslušné zásady a portál společnosti."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 493b5bfce7ab9b78f5f7c48d0d18524d1b191f1f
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="retire-devices-from-intune-management"></a>Vyřazení zařízení ze správy Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nezáleží na tom, jestli zařízení patří společnosti nebo jednotlivci, nakonec ho bude potřeba odebrat ze správy v Intune.

Zařízení se z Intune nikdy neodeberou bez vašeho zásahu, a to ani v případě, že se daná zařízení po nějakou dobu ke službě Intune nepřipojila.

Vyřazení zařízení může mít různé důvody:

-   Uživatel opustí společnost plánovaným způsobem („spravovaný“ odchod).
-   Uživatel opustí společnost náhle (dostane výpověď, skončí atd.).
-   Dojde ke ztrátě zařízení.
-   Zařízení se začne používat jinak (přesune se k jinému uživateli, začne se používat jiným způsobem atd.).

Spravované mobilní zařízení můžete vymazat buď selektivně, nebo úplně. Můžete ho také zamknout a resetovat jeho heslo. Pokud zařízení vymažete, uvolníte předplatné uživatele, které můžete přidat jinému zařízení. Vyřadit můžete také počítače, které jsou spravované klientským softwarem Intune.

## <a name="wipe-data-and-apps-from-devices"></a>Vymazání dat a aplikací ze zařízení
Při selektivním i úplném vymazání se zařízení odebere ze správy v Intune tím, že se odeberou jeho zásady a portál společnosti. V zařízení tak nebudou přihlašovací údaje potřebné pro přihlášení k prostředkům společnosti, jako je Microsoft SharePoint, e-mail nebo Office 365.

[Selektivní vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) by se mělo upřednostňovat u zaměstnanců, kteří mají v Intune zaregistrované své vlastní zařízení, protože vymazání dat se v tomto případě nedotkne osobních údajů uložených na zařízení. Odeberou se jenom firemní data.

Pro zařízení, která je třeba přiřadit někomu jinému, můžete také použít [úplné vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), které resetuje zařízení do továrního nastavení.

### <a name="removing-user-licenses-and-managed-devices"></a>Odebrání uživatelských licencí a spravovaných zařízení
Když odeberete uživatelskou licenci, zařízení zaregistrovaná tímto uživatelem přestanou být registrovaná. Doporučujeme, abyste před odebráním licence Intune uživateli nejdříve odebrali podniková data ze spravovaných zařízení. Jakmile uživatelskou licenci odeberete, nemůže být zařízení cílem vzdálených akcí.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Odstranění zařízení na portálu služby Azure Active Directory

1.  Přihlaste se přihlašovacími údaji vaší organizace na [http://aka.ms/accessaad](http://aka.ms/accessaad) nebo [https://portal.office.com](https://portal.office.com) a potom zvolte **Centra pro správu** &gt; **Azure AD**.

2.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, nepotřebujete k tomu platební kartu ani platbu. Vyberte odkaz na **registraci bezplatného předplatného Azure Active Directory**.

4.  Zvolte **Active Directory** a vyberte svoji organizaci.

5.  Zvolte kartu **Uživatelé**.

6.  Vyberte uživatele, kterému chcete odstranit zařízení.

7.  Zvolte **Zařízení**.

8.  Vyberte příslušná zařízení a zvolte **Odstranit zařízení**. Zařízení se vymaže při příští synchronizaci se službou Active Directory. To obvykle proběhne do čtyř hodin. Po synchronizaci se zařízení vyřadí ze správy. Tím se také odebere jedno zařízení z limitu počtu zařízení pro daného uživatele.

## <a name="retire-managed-computers"></a>Vyřazení spravovaných počítačů
Počítače spravované v klientském softwaru Intune je možné odebrat ze správy v konzole pro správu Intune. Tím se také z počítače odinstaluje klientský software a odstraní se z něj zásady Intune. Viz informace o [vyřazení počítačů spravovaných pomocí klientského softwaru Intune](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="block-access-a-device"></a>Zablokování přístupu k zařízení
Při ztrátě zařízení nebo když ho musíte vyřadit, protože zaměstnanec opustil společnost, ale hardware vlastněný společností nevrátil zpět, také můžete [resetovat heslo a zařízení vzdáleně zamknout](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Tím se zajistí ochrana informací společnosti před zneužitím, i když může být nutné zařízení odepsat jako ztrátu.

Také můžete chtít odvolat licenci pro uživatelský účet Intune zaměstnance. Tím se licence uvolní a je možné ji přiřadit novému uživatelskému účtu.

## <a name="retire-hardware"></a>Vyřazení zařízení
V některých případech zařízení samotné dosáhne konce své životnosti. V takových případech [obnovením zařízení do továrního nastavení](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) s plným vymazáním odeberete všechna data a také odebere zařízení ze služby Intune. Pak můžete hardware vyřadit v souladu se zásadami společnosti.

### <a name="see-also"></a>Viz taky
[Lepší ochrana dat s využitím úplného nebo selektivního vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)

