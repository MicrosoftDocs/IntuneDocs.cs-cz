---
title: "Přehled životního cyklu MDM | Dokumentace Microsoftu"
description: "Zjistěte, jak Intune vám pomůže spravovat zařízení prostřednictvím jejich životního cyklu od registrace přes konfiguraci až po závěrečné vyřazení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 106b24e73a21d7cd8608c44c4dd7ded4c0eebe4f


---

# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>Přehled životního cyklu správy mobilních zařízení (MDM)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Všechna zařízení, která spravujete, mají takzvaný *životní cyklus*. Intune vám může pomoci při správě tohoto životního cyklu od registrace přes konfiguraci a ochranu až po vyřazení zařízení, když už nebude potřebné:

![Životní cyklus zařízení](./media/device-lifecycle.png "Životní cyklus zařízení Intune")

## <a name="enroll"></a>registrace
Dnešní strategie správy mobilních zařízení (MDM) zahrnují využívání různých druhů telefonů, tabletů a počítačů (se systémy iOS, Android, Windows a Mac OS X). Pokud potřebujete mít možnost spravovat zařízení, což se často stává třeba u zařízení vlastněných společností, prvním krokem je [nastavení registrace zařízení](enroll-devices-in-microsoft-intune.md). Počítače s Windows můžete také spravovat buď tak, že je zaregistrujete v Intune (MDM), nebo do nich [nainstalujete klientský software Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Konfigurace
Registrace zařízení je jenom první krok. Pokud chcete využívat všechno, co Intune nabízí, a zajistit u zařízení zabezpečení a dodržování standardů společnosti, můžete si vybrat z široké nabídky zásad. Ty vám umožní nastavit skoro každý aspekt fungování spravovaných zařízení. Mají třeba uživatelé na zařízeních, která obsahují firemní data, používat heslo? Můžete to vyžadovat. Máte podnikovou síť Wi-Fi? Můžete ji automaticky nakonfigurovat. Tady je přehled typů dostupných možností konfigurace:

- [**Zásady konfigurace**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Tyto zásady umožňují nastavit způsob fungování funkcí a možností zařízení, která spravujete. Můžete třeba vyžadovat použití hesla na zařízeních Windows Phone nebo zakázat použití fotoaparátu na zařízeních iPhone.
- [**Zásady přístupu k podnikovým prostředkům**](enable-access-to-company-resources-with-microsoft-intune.md). Pokud umožníte uživatelům přistupovat k pracovním dokumentům z osobních zařízení, může to znamenat určité výzvy. Jak třeba zajistíte, aby byla všechna zařízení, která potřebují přístup k firemním e-mailům, správně nakonfigurovaná? Jak zajistíte, aby mohli uživatelé získat přístup do podnikové sítě pomocí připojení VPN, aniž by museli znát složitá nastavení? Intune vám může pomoct tyto překážky překonat díky automatické konfiguraci, která spravovaným zařízením umožní přístup k běžným prostředkům společnosti.
- [**Zásady správy počítačů s Windows (s klientským softwarem Intune)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) I když vám nejvíc možností správy zařízení přinese registrace počítačů s Windows do Intune, Intune dál podporuje správu počítačů s Windows pomocí klientského softwaru Intune. Pokud potřebujete informace o některých úlohách, které můžete s počítači provádět, začněte tady.

## <a name="protect"></a>Ochrana
V moderním světě informačních technologií představuje ochrana zařízení proti neoprávněnému přístupu jeden z vašich nejdůležitějších úkolů. Kromě položek v kroku **Konfigurace** životního cyklu zařízení Intune poskytuje tyto možnosti, které pomáhají chránit spravovaná zařízení proti neoprávněnému přístupu nebo nebezpečným útokům:
- [**Víceúrovňové ověřování**](protect-windows-devices-with-multi-factor-authentication.md). Přidáním další úrovně ověřování k přihlašování uživatelů můžete přispět k ještě lepšímu zabezpečení zařízení. Zařízení se systémy Windows, Windows Phone a Windows Mobile nabízí víceúrovňové ověřování, které před povolením přístupu uživatelů vyžaduje druhou úroveň ověření, třeba prostřednictvím telefonátu nebo textové zprávy.
- [**Nastavení služby Microsoft Passport**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Microsoft Passport je alternativní metoda přihlašování, která umožňuje uživatelům používat k přihlášení *gesto*, třeba otisk prstu nebo Windows Hello, takže nemusí zadávat heslo.
- [**Zásady ochrany počítačů se systémem Windows (s klientským softwarem Intune)**](policies-to-protect-windows-pcs-in-microsoft-intune.md). Pokud spravujete počítače s Windows pomocí klientského softwaru Intune, jsou dostupné zásady, které vám umožňují řídit na spravovaných počítačích s Windows nastavení služby Endpoint Protection, aktualizací softwaru a brány Windows Firewall.

## <a name="retire"></a>Vyřazení
Když dojde ke ztrátě nebo odcizení zařízení, když je potřeba zařízení vyměnit nebo když se uživatelé přesunou na jinou pracovní pozici, je většinou vhodné zařízení [vyřadit nebo vymazat](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). To můžete udělat několika způsoby, třeba zařízení resetovat, odebrat ho ze zprávy nebo z něj vymazat firemní data.



<!--HONumber=Dec16_HO5-->


