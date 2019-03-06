---
title: Windows 10 nastavení sdíleného zařízení – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidat a používat Windows 10 pro konfiguraci zařízení, které jsou sdílená nebo použít víc uživatelů v Microsoft Intune. Zobrazit seznam všech nastavení a co dělají na zařízeních, včetně Microsoft Surface. Řídit účty hostů, Správa účtů a odstranit neaktivní účty, povolit nebo zakázat ukládání do místního úložiště, nastavení napájení a režimu spánku možnosti, vyberte při aktualizace jsou nainstalovány a používat zařízení v prostředí education v profilu konfigurace zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 31248225205608c6f8809c52b98ed1141395aec1
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389294"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Nastavení Windows 10 a novější spravovat sdílená zařízení pomocí Intune

Windows 10 a novější zařízení, jako je například Microsoft Surface, je možné mnoha uživateli. Zařízení, která mají více uživatelů se nazývají sdílené zařízení a jsou součástí správy mobilních zařízení (MDM) řešení.

Pomocí Microsoft Intune, koncovým uživatelům můžete přihlásit do těchto sdílených zařízení pomocí účtu guest. Během používání zařízení, dostanou jenom přístup k funkcím, které povolíte. Jako správce Intune nakonfigurovat přístup, zvolte při odstranění účtů, nastavení řízení spotřeby ovládacího prvku a další možnosti pro sdílená zařízení s Windows 10.

Tento článek uvádí a popisuje, jaká nastavení použít v profilu konfigurace Windows 10 (nebo novějším). Profil se vytvoří v Intune, nasazení nebo přiřaďte profil ke skupinám zařízení ve vaší organizaci. Můžete také přiřadit tento profil ke skupinám zařízení s typy smíšené zařízení a verze operačního systému.

Další informace o této funkci v Intune najdete v tématu [ovládat přístup, účty a funkce power sdílené počítače nebo zařízení více uživatelů](shared-user-device-settings.md). Další informace o Windows CSP najdete v tématu [SharedPC CSP](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>Před vaše begin

[Vytvoření profilu](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Nastavení sdíleného zařízení s více uživateli

- **Režim sdíleného počítače**: Zvolte **povolit** zapnout režim sdíleného počítače. V tomto režimu se jenom jeden uživatel přihlásí k zařízení současně. Jiný uživatel nemůže přihlásit, dokud odhlášení prvního uživatele. **Není nakonfigurováno** (výchozí) opustí, tato nastavení nespravovaných přes Intune a nebude push všechny zásady pro řízení tohoto nastavení na zařízení.
- **Účet Guest**: Zvolte možnost hostovaného na obrazovce přihlášení. Účty hostů nevyžadují žádné přihlašovací údaje uživatele nebo ověřování. Toto nastavení se vytvoří nový místní účet pokaždé, když se používá. Možnosti:
  - **Host**: Vytvoří účet guest místně na zařízení.
  - **Domény**: Vytvoří účet hostovaný v Azure Active Directory (AD).
  - **Host a domény**: Vytvoří účet guest místně na zařízení a v Azure Active Directory (AD).
- **Správa účtů**: Nastavte na **povolit** automaticky odstranit místní účty vytvořené Hosté a účtů v AD a Azure AD. Když se uživatel odhlásí vypnutí zařízení nebo když údržbu systému, jsou tyto účty odstranit. Pokud je povolená, taky nastavte:
  - **Odstranění účtu**: Zvolte, pokud dojde k odstranění účtu: **Na prahové hodnoty pro prostor úložiště**, **prahová hodnota pro prostor úložiště a neaktivní prahová hodnota**, nebo **ihned po odhlášení**. Dále zadejte:
    - **Spuštění odstranění threshold(%)**: Zadejte hodnotu v procentech (0 – 100) místa na disku. Pokud celkový disk nebo prostor úložiště se sníží pod hodnota, kterou zadáte, se odstraní účty v mezipaměti. Trvale odstraní účty pro uvolnění místa na disku. Účty, které jsou neaktivní nejdéle jsou jako první smazány.
    - **Zastavit odstraňování threshold(%)**: Zadejte hodnotu v procentech (0 – 100) místa na disku. Pokud celkový disk nebo prostor úložiště splňuje hodnota, kterou zadáte, odstraňuje se zastaví.

  Nastavte na **zakázat** zachovat místní AD a účty Azure AD, které jsou vytvořené hosté.

- **Místní úložiště**: Zvolte **povoleno** lze zabránit uživatelům v ukládání a zobrazení souborů na pevný disk zařízení. Zvolte **zakázané** umožňuje uživatelům zobrazit a uložit soubory místně pomocí Průzkumníka souborů. **Není nakonfigurováno** (výchozí) opustí, tato nastavení nespravovaných přes Intune a nebude push všechny zásady pro řízení tohoto nastavení na zařízení.
- **Zásady napájení**: Pokud je nastavena na **povoleno**, uživatelé nebudou moci zapnout vypnout do režimu hibernace, nelze přepsat všechny akce v režimu spánku (například zavření víka) a nelze změnit nastavení napájení používané tehdy. Pokud je nastavena na **zakázané**, uživatelé můžete zařízení do režimu hibernace, můžete zavření krytu do režimu spánku, zařízení a měnit nastavení napájení používané tehdy. **Není nakonfigurováno** (výchozí) opustí, tato nastavení nespravovaných přes Intune a nebude push všechny zásady pro řízení tohoto nastavení na zařízení.
- **Přejít do režimu spánku vypršení časového limitu (v sekundách)**: Zadejte počet sekund neaktivní (0 – 100) předtím, než zařízení přejde do režimu spánku. Pokud nemají nastavený čas, zařízení přejde do režimu spánku po 60 minutách.
- **Přihlášení po probuzení počítače**: Nastavte na **povoleno** budou muset uživatelé přihlásit pomocí hesla, pokud zařízení vzejde z režimu spánku. Zvolte **zakázané** aby uživatelé nemuseli k zadání uživatelského jména a hesla. **Není nakonfigurováno** (výchozí) opustí, tato nastavení nespravovaných přes Intune a nebude push všechny zásady pro řízení tohoto nastavení na zařízení.
- **Údržba počáteční čas (v minutách od půlnoci)**: Zadejte dobu v minutách (0 – 1440) při spuštění úlohy automatické údržby, jako je například Windows Update. Výchozí počáteční čas je půlnoc nebo nula (`0`) minut. Počáteční čas změníte tak, že zadáte počáteční čas v minutách od půlnoci. Například pokud chcete údržby má začít ve 2: 00, zadejte `120`. Pokud chcete údržby má začít ve 20: 00, zadejte `1200`.
- **Zásady vzdělávání**: Zvolte **povoleno** použít doporučená nastavení pro zařízení používaná v školy, které jsou více omezující. Zvolte **zakázané** tak výchozí a doporučený vzdělávání zásady nepoužijí. **Není nakonfigurováno** (výchozí) opustí, tato nastavení nespravovaných přes Intune a nebude push všechny zásady pro řízení tohoto nastavení na zařízení.

  Další informace o čem vzdělávání zásady, najdete v části [doporučené konfigurace Windows 10 pro education zákazníky](https://docs.microsoft.com/education/windows/configure-windows-for-education).

## <a name="next-steps"></a>Další postup

- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
- Podívejte se na nastavení pro [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
