---
title: "Možnosti správy zaregistrovaných zařízení"
description: "Přečtěte si toto téma a zjistěte, jak vám může Intune pomoct spravovat zaregistrovaná zařízení."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 59bbc6d9a4170b504e3a5bb3dfe688332a0063f2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Možnosti správy zaregistrovaných zařízení v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune umožňuje spravovat řadu zařízení tím, že je *zaregistruje*. Některé typy zařízení můžete zaregistrovat sami, nebo je můžou zaregistrovat uživatelé pomocí aplikace *Portál společnosti*. Ta jim taky umožní řadu dalších činností, jako je procházení a instalace aplikací, kontrola kompatibility zařízení se zásadami společnosti a kontaktování podpory IT.

Toto téma poskytuje úplný seznam možností, které po registraci zařízení získáte.

Operace správy, inventáře, nasazování aplikací, zřizování a vyřazování z provozu probíhají prostřednictvím konzoly pro správu Intune. Uživatelé získají přístup k portálu společnosti, odkud můžou instalovat aplikace a registrovat a odebírat zařízení a odkud můžou snadno kontaktovat IT oddělení nebo technickou podporu.



## <a name="device-security-and-configuration"></a>Konfigurace a zabezpečení zařízení

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Zásady konfigurace<br><br>Vlastní zásady| Umožňují spravovat množství nastavení a funkcí na mobilních zařízeních ve vaší organizaci. Můžete třeba vyžadovat heslo, omezit počet neúspěšných pokusů o přihlášení, určit dobu, po které se uzamkne obrazovka zařízení, nastavit dobu platnosti hesla a zabránit nastavení už použitých hesel. Můžete také řídit použití funkcí hardwaru a softwaru, jako je třeba fotoaparát zařízení nebo webový prohlížeč.<br><br>Vlastní zásady použijte při konfiguraci zásad, které neobsahují nastavení, které vyžadujete. Pro zařízení s iOSem můžete importovat nastavení, které jste vyexportovali z nástroje Apple Configurator. Pro další zařízení můžete pomocí nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) nakonfigurovat nastavení a funkce v zařízení.|[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Vzdálené vymazání, Vzdálené uzamčení a Resetování hesla|V případě ztráty nebo odcizení zařízení je možné vymazat citlivá data. Zařízení můžete třeba vzdáleně uzamknout, obnovit do továrního nastavení nebo vymazat jenom firemní data.<br><br>Můžete resetovat hesla, když uživatelé ztratí přístup ke svým zařízením, uzamknout ztracená nebo odcizená zařízení nebo z takových zařízení dokonce vymazat data.|[Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Celoobrazovkový režim|Umožňuje uzamknout určité funkce mobilních zařízení, třeba snímek obrazovky a vypínač. Umožňuje taky omezit zařízení tak, aby v nich mohla běžet jenom jedna vámi určená aplikace.|[Nastavení zásad konfigurace pro iOS v Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Správa aplikací

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Správa a nasazení aplikací|Poskytuje řadu nástrojů, které vám pomůžou spravovat mobilní aplikace v průběhu jejich životního cyklu, včetně nasazení aplikací z instalačních souborů a obchodů s aplikacemi, podrobného sledování stavu aplikací a jejich odebrání.|[Nasazení aplikací v Microsoft Intune](/intune-classic/deploy-use/deploy-apps)|
|Kompatibilní a nekompatibilní aplikace|Umožňuje určit seznam kompatibilních aplikací (které uživatelé můžou nainstalovat) a nekompatibilních aplikací (které uživatelé nainstalovat nesmí).|[Nastavení zásad pro iOS v Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|správa mobilních aplikací|Konfiguruje omezení pro aplikace pomocí správy mobilních aplikací jak pro zařízení, která spravujete v Intune, tak pro zařízení, která Intune nespravuje. Umožňuje zvýšit zabezpečení firemních dat omezením operací, jako jsou třeba kopírování a vkládání, externí zálohování dat a přenos dat mezi aplikacemi.|[Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](/intune/app-wrapper-prepare-android)|
|Konfigurace mobilních aplikací pro iOS|Využívá zásady konfigurace mobilních aplikací k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci pro iOS. Aplikace může například vyžadovat, aby uživatel zadal číslo portu nebo přihlašovací informace. To může usnadnit konfiguraci aplikace a omezit počet volání služby helpdesk.|[Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Profily zřizování mobilních aplikací pro iOS|Pomáhá při nasazování zřizovacích profilů pro aplikace iOS, u kterých se blíží vypršení platnosti. |[Použití zásad pro mobilní zřizovací profil pro iOS k zabránění vypršení platnosti aplikací](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Spravovaný prohlížeč|Konfiguruje zásady spravovaného prohlížeče pro kontrolu nad weby, které uživatelé můžou navštěvovat. Pro spravovaný prohlížeč můžete taky použít zásady správy mobilních aplikací.|[Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello pro firmy|Umožňuje integraci se službou Microsoft Hello pro firmy. Tato alternativní metoda pro přihlašování do Windows 10 pomocí místní služby Active Directory nebo Azure Active Directory může nahradit hesla, čipové karty a virtuální čipové karty.|[Řízení nastavení Windows Hello pro firmy na zařízeních pomocí Microsoft Intune](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Hromadně zakoupené aplikace|Pomůže spravovat aplikace, které jste koupili prostřednictvím programu hromadného nákupu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili, a zabráněním instalace více aplikací, než na kolik máte licence.|[Správa hromadně koupených aplikací v Microsoft Intune](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Přístup k prostředkům společnosti

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Profily certifikátů|Vytvoří a nasadí profily důvěryhodných certifikátů a certifikáty protokolu SCEP (Simple Certificate Enrollment Protocol), které se dají použít k zabezpečení a ověření profilů sítí Wi-Fi, VPN a e-mailu.|[Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Profily sítě Wi-Fi|Nasadí uživatelům nastavení bezdrátových sítí. Nasazením těchto nastavení minimalizujete úsilí uživatelů potřebné k připojení k firemní síti.|[Připojení Wi-Fi v Microsoft Intune](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-mailové profily|Vytvoří a nasadí nastavení e-mailu do zařízení. Díky tomu mají uživatelé na svých osobních zařízeních přístup k podnikovému e-mailu, bez nutnosti něco nastavovat.|[Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Profily sítě VPN|Nasadí nastavení sítě VPN pro uživatele a zařízení ve vaší organizaci. Nasazením těchto nastavení zjednodušíte uživatelům připojování k prostředkům v síti společnosti.|[Připojení VPN v Microsoft Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Zásady podmíněného přístupu|Spravuje přístup k e-mailu Microsoft Exchange a službám SharePoint Online ze zařízení, která nespravuje Intune.|[Omezení přístupu k e-mailu a SharePointu pomocí Microsoft Intune](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Inventář a vytváření sestav

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Inventář a vytváření sestav|Vyhledá informace o vámi spravovaných zařízeních a softwaru, který používají.|[Seznámení se zařízeními s inventářem v Microsoft Intune](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|
