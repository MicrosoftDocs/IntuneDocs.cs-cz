---
title: Možnosti správy zařízení v Microsoft Intune
description: Přečtěte si toto téma a zjistěte, jak vám může Intune pomoct spravovat zaregistrovaná zařízení.
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
ms.openlocfilehash: 2c2c50909b701ee5418ea69d73e67518de1c5bce
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045734"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Možnosti správy zaregistrovaných zařízení v Microsoft Intune

Microsoft Intune umožňuje spravovat řadu zařízení tím, že je *zaregistruje*. Některé typy zařízení můžete zaregistrovat sami, nebo je můžou zaregistrovat uživatelé pomocí aplikace *Portál společnosti*. Registrace umožní je procházet a instalovat aplikace, ujistěte se, že jsou jejich zařízení vyhovuje zásadám společnosti a obraťte se na jejich podporu IT.

Tento článek obsahuje úplný seznam možností, získáte po registraci zařízení.

Správy, inventáře, nasazování aplikací, zřizování a vyřazování z provozu probíhají prostřednictvím Intune na portálu Azure portal.

Uživatelé získají přístup k portálu společnosti, odkud můžou instalovat aplikace a registrovat a odebírat zařízení a odkud můžou snadno kontaktovat IT oddělení nebo technickou podporu.



## <a name="device-security-and-configuration"></a>Konfigurace a zabezpečení zařízení

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Zásady konfigurace<br><br>Vlastní zásady| Umožňují spravovat množství nastavení a funkcí na mobilních zařízeních ve vaší organizaci. Můžete třeba vyžadovat heslo, omezit počet neúspěšných pokusů o přihlášení, určit dobu, po které se uzamkne obrazovka zařízení, nastavit dobu platnosti hesla a zabránit nastavení už použitých hesel. Můžete také řídit použití funkcí hardwaru a softwaru, jako je třeba fotoaparát zařízení nebo webový prohlížeč.<br><br>Použití vlastních zásad, když zásady Konfigurace neobsahují nastavení, která požadujete. Pro zařízení s iOSem můžete importovat nastavení, které jste vyexportovali z nástroje Apple Configurator. Pro další zařízení můžete pomocí nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) nakonfigurovat nastavení a funkce v zařízení.|[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](device-compliance-get-started.md)|
|Vzdálené vymazání, Vzdálené uzamčení a Resetování hesla|V případě ztráty nebo odcizení zařízení je možné vymazat citlivá data. Zařízení můžete třeba vzdáleně uzamknout, obnovit do továrního nastavení nebo vymazat jenom firemní data.<br><br>Můžete resetovat hesla, když uživatelé ztratí přístup ke svým zařízením, uzamknout ztracená nebo odcizená zařízení nebo z takových zařízení dokonce vymazat data.|Chraňte svá zařízení s [vzdálené uzamčení](device-remote-lock.md) a [resetování hesla](device-passcode-reset.md)|
|Celoobrazovkový režim|Umožňuje uzamknout určité funkce mobilních zařízení, třeba snímek obrazovky a vypínač. Umožňuje taky omezit zařízení tak, aby v nich mohla běžet jenom jedna vámi určená aplikace. |[Nastavení zásad konfigurace pro iOS v Microsoft Intune](device-restrictions-ios.md)|

## <a name="app-management"></a>Správa aplikací

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Správa a nasazení aplikací|Poskytuje řadu nástrojů, které vám pomůžou spravovat mobilní aplikace v průběhu jejich životního cyklu, včetně nasazení aplikací z instalačních souborů a obchodů s aplikacemi, podrobného sledování stavu aplikací a jejich odebrání.|[Nasazení aplikací v Microsoft Intune](apps-deploy.md)|
|Kompatibilní a nekompatibilní aplikace|Umožňuje určit seznam kompatibilních aplikací (které uživatelé můžou nainstalovat) a nekompatibilních aplikací (které uživatelé nainstalovat nesmí).|[Nastavení zásad pro iOS v Microsoft Intune](device-restrictions-ios.md)|
|správa mobilních aplikací|Konfiguruje omezení pro aplikace pomocí správy mobilních aplikací jak pro zařízení, která spravujete v Intune, tak pro zařízení, která Intune nespravuje. Můžete zvýšit zabezpečení firemních dat omezením operací, jako je kopírování a vkládání, externí zálohování dat a přenos dat mezi aplikacemi.|[Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](app-wrapper-prepare-android.md)|
|Konfigurace mobilních aplikací pro iOS|Využívá zásady konfigurace mobilních aplikací k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci pro iOS. Aplikace může například vyžadovat, aby uživatel zadal číslo portu nebo přihlašovací informace. Může usnadnit konfiguraci aplikace a snížení počtu volání podpory.|[Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](app-configuration-policies-use-ios.md)|
|Profily zřizování mobilních aplikací pro iOS|Pomáhá při nasazování zřizovacích profilů pro aplikace iOS, u kterých se blíží vypršení platnosti. |[Použití zásad pro mobilní zřizovací profil pro iOS k zabránění vypršení platnosti aplikací](app-provisioning-profile-ios.md)|
|Spravovaný prohlížeč|Konfiguruje zásady spravovaného prohlížeče pro kontrolu nad weby, které uživatelé můžou navštěvovat. Pro spravovaný prohlížeč můžete taky použít zásady správy mobilních aplikací.|[Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](app-configuration-managed-browser.md)|
|Windows Hello pro firmy|Umožňuje integraci se službou Microsoft Hello pro firmy. Tato alternativní metoda pro přihlašování do Windows 10 pomocí místní služby Active Directory nebo Azure Active Directory může nahradit hesla, čipové karty a virtuální čipové karty.|[Řízení nastavení Windows Hello pro firmy na zařízeních pomocí Microsoft Intune](windows-hello.md)|
|Hromadně zakoupené aplikace|Pomůže spravovat aplikace, které jste koupili prostřednictvím programu hromadného nákupu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili, a zabráněním instalace více aplikací, než na kolik máte licence.|[Správa hromadně koupených aplikací v Microsoft Intune](vpp-apps.md)|

## <a name="company-resource-access"></a>Přístup k prostředkům společnosti

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Profily certifikátů|Vytvoří a nasadí profily důvěryhodných certifikátů a certifikáty protokolu SCEP (Simple Certificate Enrollment Protocol), které se dají použít k zabezpečení a ověření profilů sítí Wi-Fi, VPN a e-mailu.|[Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](certificates-configure.md)|
|Profily sítě Wi-Fi|Nasadí uživatelům nastavení bezdrátových sítí. Nasazením těchto nastavení minimalizujete úsilí uživatelů potřebné k připojení k firemní síti.|[Připojení Wi-Fi v Microsoft Intune](wi-fi-settings-configure.md)|
|E-mailové profily|Vytvoří a nasadí nastavení e-mailu do zařízení tak, aby uživatelé měli přístup k podnikovému e-mailu na jejich osobních zařízení bez nutnosti něco nastavovat jejich část.|[Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](email-settings-configure.md)|
|Profily sítě VPN|Nasadí nastavení sítě VPN pro uživatele a zařízení ve vaší organizaci. Nasazením těchto nastavení zjednodušíte uživatelům připojování k prostředkům v síti společnosti.|[Připojení VPN v Microsoft Intune](device-profiles.md#vpn)|
|Zásady podmíněného přístupu|Spravuje přístup k e-mailu Microsoft Exchange a službám SharePoint Online ze zařízení, která nespravuje Intune.|[Omezení přístupu k e-mailu a SharePointu pomocí Microsoft Intune](app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Další postup

[Podívejte se do seznamu zařízení, která můžete spravovat](device-management.md).
