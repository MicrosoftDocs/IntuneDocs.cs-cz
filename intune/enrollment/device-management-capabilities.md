---
title: Možnosti správy zařízení v Microsoft Intune
description: Přečtěte si toto téma a zjistěte, jak vám může Intune pomáhat při správě zaregistrovaných zařízení.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: bf862e59e135a875f5f18af731c581f3e5ea89d5
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306614"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Možnosti správy zaregistrovaných zařízení Microsoft Intune

Microsoft Intune umožňuje spravovat řadu zařízení tím, že je *zaregistruje* do služby. Některé typy zařízení si můžete zaregistrovat sami nebo se uživatelé můžou zaregistrovat pomocí aplikace *portál společnosti* . Registrace umožňuje procházet a instalovat aplikace, zajistěte, aby jejich zařízení vyhovovala podnikovým zásadám a kontaktovalo IT oddělení IT.

Tento článek obsahuje úplný seznam funkcí, které získáte po registraci zařízení.

Správa, inventarizace, nasazování aplikací, zřizování a vyřazení z provozu se procházejí prostřednictvím Intune v Azure Portal.

Uživatelé získají přístup k portálu společnosti, který jim umožní instalovat aplikace, registrovat a odebírat zařízení a kontaktovat IT oddělení nebo helpdesk.



## <a name="device-security-and-configuration"></a>Zabezpečení a konfigurace zařízení

|Schopnost|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Zásady konfigurace<br><br>Vlastní zásady| Umožňuje spravovat spoustu nastavení a funkcí na mobilních zařízeních ve vaší organizaci. Můžete třeba vyžadovat heslo, omezit počet neúspěšných pokusů o přihlášení, omezit dobu, po které se uzamkne obrazovka, nastavit vypršení platnosti hesla a zabránit používání hesel dřív. Můžete také řídit použití hardwarových a softwarových funkcí, jako je třeba fotoaparát zařízení nebo webový prohlížeč.<br><br>Vlastní zásady použijte v případě, že zásady konfigurace neobsahují nastavení, které požadujete. U zařízení se systémem iOS můžete importovat nastavení, která jste exportovali z nástroje Apple Configuratoru. Pro další zařízení můžete pomocí nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) nakonfigurovat nastavení a funkce v zařízení.|[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](../protect/device-compliance-get-started.md)|
|Vzdálené vymazání, vzdálené uzamčení a resetování hesla|Smaže citlivá data, když dojde ke ztrátě nebo odcizení zařízení. Můžete třeba zařízení vzdáleně uzamknout, obnovit do továrního nastavení nebo vymazat jenom firemní data.<br><br>Můžete resetovat hesla, když uživatelé ztratí přístup ke svým zařízením, zamkne chybějící nebo odcizená zařízení nebo dokonce vymažou data z chybějících nebo odcizených zařízení.|Chraňte svá zařízení pomocí [vzdáleného zámku](../remote-actions/device-remote-lock.md) a [resetování hesla](../remote-actions/device-passcode-reset.md) .|
|Celoobrazovkový režim|Umožňuje uzamknout určité funkce mobilních zařízení, jako jsou například snímky obrazovky a vypínače napájení. Umožňuje taky omezit zařízení tak, aby spouštěla jednu aplikaci, kterou zadáte. |[nastavení zásad konfigurace pro iOS v Microsoft Intune](../configuration/device-restrictions-ios.md)|
|Resetování autopilotu|Odešle úlohu na zařízení, aby se proces resetování spouštěl vzdáleně, aby nemuseli pracovníci IT nebo jiní správci navštěvovat jednotlivé počítače, aby mohli tento proces spustit. Když se na zařízení používá resetování autopilotního projektu, primární uživatel zařízení se odebere. Další uživatel, který se přihlásí po obnovení, se nastaví jako primární uživatel.|[Resetování vzdáleného Windows autopilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset#reset-devices-with-remote-windows-autopilot-reset)|

## <a name="app-management"></a>Správa aplikací

|Schopnost|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Nasazení a Správa aplikací|Poskytuje celou řadu nástrojů, které vám pomůžou se správou mobilních aplikací prostřednictvím jejich životního cyklu, včetně nasazení aplikací z instalačních souborů a obchodů s aplikacemi, podrobného sledování stavu aplikace a odebrání aplikací.|[Nasazení aplikací v Microsoft Intune](../apps/apps-deploy.md)|
|Kompatibilní a nekompatibilní aplikace|Umožňuje určit seznam kompatibilních aplikací (které uživatelé můžou instalovat) a nekompatibilních aplikací (které uživatelé nemůžou instalovat).|[nastavení zásad pro iOS v Microsoft Intune](../configuration/device-restrictions-ios.md)|
|Správa mobilních aplikací|Konfiguruje omezení pro aplikace pomocí správy mobilních aplikací pro všechna zařízení spravovaná pomocí Intune a nespravovaná pomocí Intune. Můžete zvýšit zabezpečení firemních dat omezením operací, jako je kopírování a vkládání, externí zálohování dat a přenos dat mezi aplikacemi.|[Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](../developer/app-wrapper-prepare-android.md)|
|konfigurace mobilních aplikací pro iOS|Pomocí zásad konfigurace mobilních aplikací poskytuje nastavení pro aplikace pro iOS, které se můžou požadovat, když uživatel spustí aplikaci. Aplikace může například vyžadovat, aby uživatel určil číslo portu nebo přihlašovací informace. Můžete zjednodušit konfiguraci aplikace a snížit počet volání podpory.|[Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](../apps/app-configuration-policies-use-ios.md)|
|profily zřizování mobilních aplikací pro iOS|Pomáhá nasadit zřizovací profily na aplikace pro iOS, které brzy vyprší platnost. |[Použití mobilních zásad zřizovacích profilů pro iOS k zabránění vypršení platnosti vašich aplikací](../apps/app-provisioning-profile-ios.md)|
|Spravovaný prohlížeč|Konfiguruje zásady spravovaného prohlížeče za účelem řízení webů, které můžou uživatelé zařízení navštěvovat. Kromě toho můžete zásady správy mobilních aplikací použít taky pro spravovaný prohlížeč.|[Správa přístupu k Internetu pomocí zásad spravovaného prohlížeče pomocí Microsoft Intune](../apps/app-configuration-managed-browser.md)|
|Windows Hello pro firmy|Umožňuje integraci se službou Windows Hello pro firmy, což je alternativní metoda pro přihlašování do Windows 10, která používá místní službu Active Directory nebo Azure Active Directory k nahrazení hesel, čipových karet a virtuálních čipových karet.|[Řízení nastavení Windows Hello pro firmy na zařízeních s Microsoft Intune](../protect/windows-hello.md)|
|Hromadně zakoupené aplikace|Vám pomůže spravovat aplikace, které jste zakoupili prostřednictvím multilicenčního programu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili, a zabráněním v instalaci více kopií aplikace, než na kolik máte licence.|[Správa hromadně zakoupených aplikací pomocí Microsoft Intune](../apps/vpp-apps.md)|

## <a name="company-resource-access"></a>Přístup k prostředkům společnosti

|Schopnost|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Profily certifikátů|Vytvoří a nasadí důvěryhodné profily certifikátů a certifikáty Simple Certificate Enrollment Protocol (SCEP), které se dají použít k zabezpečení a ověření profilů Wi-Fi, VPN a e-mailu.|[Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](../protect/certificates-configure.md)|
|Profily sítě Wi-Fi|Nasadí nastavení bezdrátové sítě pro vaše uživatele. Nasazením těchto nastavení minimalizujete úsilí uživatelů potřebné k připojení k podnikové síti.|[Připojení Wi-Fi v Microsoft Intune](../configuration/wi-fi-settings-configure.md)|
|E-mailové profily|Vytvoří a nasadí nastavení e-mailu na zařízení, aby uživatelé měli přístup k podnikovému e-mailu na svých osobních zařízeních, aniž by jejich součást musela mít.|[Konfigurace přístupu k firemnímu e-mailu pomocí e-mailových profilů v Microsoft Intune](../configuration/email-settings-configure.md)|
|Profily sítě VPN|Nasadí nastavení sítě VPN pro uživatele a zařízení ve vaší organizaci. Nasazením těchto nastavení minimalizujete úsilí uživatelů potřebné pro připojení k prostředkům v síti společnosti.|[Připojení VPN v Microsoft Intune](../configuration/device-profiles.md#vpn)|
|Zásady podmíněného přístupu|Spravuje přístup k e-mailům Microsoft Exchange a SharePointu Online ze zařízení, která nespravuje Intune.|[Omezení přístupu k e-mailu a SharePointu pomocí Microsoft Intune](../protect/app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Další kroky

[Podívejte se na seznam zařízení, která můžete spravovat](../remote-actions/device-management.md).
