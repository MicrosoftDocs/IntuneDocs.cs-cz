---
title: Přehled životního cyklu Microsoft Intune MDM
description: Zjistěte, jak vám pomůže Intune spravovat zařízení prostřednictvím jejich životního cyklu od registrace přes konfiguraci až po závěrečné vyřazení.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: b78f7414e4ba383e934abd467a9f4c7c67c6bac5
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182597"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Přehled životního cyklu správy mobilních zařízení (MDM) v Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Všechna zařízení, která spravujete, mají *životní cyklus*. Intune vám může pomoci při správě tohoto životního cyklu od registrace přes konfiguraci a ochranu až po vyřazení zařízení, když už nebude potřeba.

![Životní cyklus zařízení](./media/device-lifecycle.png "Životní cyklus zařízení Intune")

## <a name="enroll"></a>registrace
Dnešní strategie správy mobilních zařízení (MDM) zahrnují využívání různých druhů telefonů, tabletů a počítačů (se systémy iOS, Android, Windows a Mac OS X). Pokud potřebujete mít možnost spravovat zařízení, což se často stává třeba u zařízení vlastněných společností, prvním krokem je [nastavení registrace zařízení](device-enrollment.md) ([portál Classic](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)). Počítače s Windows můžete také spravovat buď tak, že je zaregistrujete v Intune (MDM), nebo do nich [nainstalujete klientský software Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune).

## <a name="configure"></a>Konfigurace
Registrace zařízení je jenom první krok. Pokud chcete využívat všechno, co Intune nabízí, a zajistit u zařízení zabezpečení a dodržování standardů společnosti, můžete si vybrat z široké nabídky zásad. Ty vám umožní nastavit skoro každý aspekt fungování spravovaných zařízení. Mají třeba uživatelé na zařízeních, která obsahují firemní data, používat heslo? Můžete to vyžadovat. Máte podnikovou síť Wi-Fi? Můžete ji automaticky nakonfigurovat. Tady je přehled typů dostupných možností konfigurace:

- [**Konfigurace zařízení**](device-profiles.md) ([portál Classic](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)) Tyto zásady umožňují nastavit způsob fungování funkcí a možností zařízení, která spravujete. Můžete třeba vyžadovat použití hesla na zařízeních Windows Phone nebo zakázat použití fotoaparátu na zařízeních iPhone.
- [**Přístup k prostředkům společnosti**](device-profiles.md) ([portál Classic](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)) Pokud umožníte uživatelům přistupovat k pracovním dokumentům z osobních zařízení, může to znamenat určité výzvy. Jak třeba zajistíte, aby byla všechna zařízení, která potřebují přístup k firemním e-mailům, správně nakonfigurovaná? Jak zajistíte, aby mohli uživatelé získat přístup do podnikové sítě pomocí připojení VPN, aniž by museli znát složitá nastavení? Intune vám může pomoct tyto překážky překonat díky automatické konfiguraci, která spravovaným zařízením umožní přístup k běžným prostředkům společnosti.
- [**Zásady správy počítačů s Windows (s klientským softwarem Intune)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) I když vám nejvíc možností správy zařízení přinese registrace počítačů s Windows do Intune, Intune dál podporuje správu počítačů s Windows pomocí klientského softwaru Intune. Pokud potřebujete informace o některých úlohách, které můžete s počítači provádět, začněte tady.

## <a name="protect"></a>Ochrana
V moderním světě informačních technologií představuje ochrana zařízení proti neoprávněnému přístupu jeden z vašich nejdůležitějších úkolů. Kromě položek v kroku **Konfigurace** životního cyklu zařízení Intune poskytuje tyto možnosti, které pomáhají chránit spravovaná zařízení proti neoprávněnému přístupu nebo nebezpečným útokům:
- [**Víceúrovňové ověřování**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune). Přidáním další úrovně ověřování k přihlašování uživatelů můžete přispět k ještě lepšímu zabezpečení zařízení. Mnoho zařízení podporuje vícefaktorové ověřování, které před povolením přístupu uživatelů vyžaduje druhou úroveň ověření, například prostřednictvím telefonního hovoru nebo textové zprávy.
- [**Nastavení Windows Hello pro firmy**](windows-hello.md) ([portál Classic](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)) Nastavení Windows Hello pro firmy je alternativní metoda přihlašování, která umožňuje uživatelům používat k přihlášení *gesto*, třeba otisk prstu nebo Windows Hello, takže nemusí zadávat heslo.
- [**Zásady ochrany počítačů se systémem Windows (s klientským softwarem Intune)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune). Pokud spravujete počítače s Windows pomocí klientského softwaru Intune, jsou dostupné zásady, které vám umožňují řídit na spravovaných počítačích s Windows nastavení služby Endpoint Protection, aktualizací softwaru a brány Windows Firewall.

## <a name="retire"></a>Vyřazení
Když dojde ke ztrátě nebo odcizení zařízení, když je potřeba zařízení vyměnit nebo když se uživatelé přesunou na jinou pracovní pozici, je většinou vhodné zařízení [vyřadit nebo vymazat](device-management.md) ([portál Classic](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)). To můžete udělat několika způsoby, třeba zařízení resetovat, odebrat ho ze zprávy nebo z něj vymazat firemní data.
