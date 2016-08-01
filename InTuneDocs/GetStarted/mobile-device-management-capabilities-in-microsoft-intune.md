---
title: "Možnosti správy mobilních zařízení | Microsoft Intune"
description: "Přečtěte si toto téma a zjistěte, jak vám může Intune pomoct spravovat mobilní zařízení registrovaná ve službě."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 23054b2f02d11ca19cd0902ebc1e6fdcf499d1f1
ms.openlocfilehash: 8f44256fe249c60df8e910858516a25463c8e875


---
# Možnosti správy mobilních zařízení v Microsoft Intune

Microsoft Intune umožňuje spravovat řadu zařízení tím, že je *zaregistruje*. Uživatelé pak můžou použít *portál společnosti* k provedení řady operací, jako je třeba registrace zařízení, procházení a instalace aplikací, zajištění kompatibility zařízení se zásadami společnosti a kontaktování podpory IT.
Toto téma poskytuje úplný seznam možností, které se vám po registraci zařízení nabízí.

Operace správy, inventáře, nasazování aplikací, zřizování a vyřazování z provozu probíhají prostřednictvím konzoly pro správu Intune. Uživatelé získají přístup k portálu společnosti, odkud můžou instalovat aplikace a registrovat a odebírat zařízení a odkud můžou snadno kontaktovat IT oddělení nebo technickou podporu.



## Konfigurace a zabezpečení zařízení

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Zásady konfigurace<br><br>Vlastní zásady|Zásady konfigurace mobilního zařízení umožňují spravovat množství nastavení a funkcí na mobilních zařízeních ve vaší organizaci. Můžete třeba vyžadovat heslo, omezit počet neúspěšných pokusů o přihlášení, omezit dobu, po které se uzamkne obrazovka zařízení, nastavit dobu platnosti hesla a zabránit nastavení už použitých hesel. Může také řídit použití funkcí hardwaru a softwaru, jako je třeba fotoaparát zařízení nebo webový prohlížeč.<br><br>Vlastní zásady použijte při konfiguraci zásad, které neobsahují nastavení, které vyžadujete. Pro zařízení s iOS můžete importovat nastavení, které jste vyexportovali z nástroje Apple Configurator. Pro další zařízení můžete pomocí nastavení OMA-URI nakonfigurovat nastavení a funkce v zařízení.|[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Vzdálené vymazání, Vzdálené uzamčení a Resetování hesla|Pokud dojde ke ztrátě nebo odcizení zařízení, vymažou se citlivá data. Zařízení můžete třeba vzdáleně uzamknout, obnovit do továrního nastavení nebo vymazat jenom firemní data.<br>Můžete resetovat hesla, když uživatelé ztratí přístup ke svým zařízením, uzamknout ztracená nebo odcizená zařízení nebo z takových zařízení dokonce vymazat data.|[Lepší ochrana zařízení pomocí vzdáleného uzamčení a resetování hesla](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) a [Vyřazení zařízení ze správy Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Celoobrazovkový režim|Umožňuje uzamknout určité funkce mobilních zařízení, třeba snímek obrazovky a vypínač. Umožňuje taky omezit zařízení tak, aby v nich mohla běžet jenom jedna vámi určená aplikace.|[Nastavení zásad konfigurace pro iOS v Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Správa aplikací

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Správa a nasazení aplikací|Poskytuje řadu nástrojů, které vám pomůžou spravovat mobilní aplikace v průběhu jejich životního cyklu, včetně nasazení aplikací z instalačních souborů a obchodů s aplikacemi, podrobného sledování stavu aplikací a jejich odebrání.|[Nasazení aplikací v Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Kompatibilní a nekompatibilní aplikace|Umožňuje určit seznam kompatibilních aplikací (které uživatelé můžou nainstalovat) a nekompatibilních aplikací (které uživatelé nesmí nainstalovat).|[Nastavení zásad pro iOS v Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Správa mobilních aplikací|Nakonfigurujte omezení pro aplikace pomocí správy mobilních aplikací jak pro zařízení, která spravujete v Intune, tak pro zařízení, která Intune nespravuje. Umožňuje zvýšit zabezpečení firemních dat omezením operací, jako jsou třeba kopírování a vkládání, externí zálohování dat a přenos dat mezi aplikacemi.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Příprava aplikací pro iOS na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Příprava aplikací pro Android na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Konfigurace mobilních aplikací pro iOS|Zásady konfigurace mobilních aplikací slouží k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci pro iOS. Aplikace může například vyžadovat, aby uživatel zadal číslo portu pro přihlašovací informace. To může usnadnit konfiguraci aplikace a omezit počet volání služby helpdesk.|[Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Profily zřizování mobilních aplikací pro iOS|Intune poskytuje nástroje k proaktivnímu nasazování zřizovacích profilů pro aplikace iOS, u kterých se blíží vypršení platnosti.|[Pomocí mobilních zásad zřizovacích profilů pro iOS zabráníte vypršení platnosti aplikací.](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|Spravovaný prohlížeč|Po nasazení spravovaného prohlížeče pro uživatele můžete nakonfigurovat zásadu spravovaného prohlížeče pro řízení webů, které můžou uživatelé navštěvovat. Pro spravovaný prohlížeč můžete taky použít zásady správy mobilních aplikací.|[Správa přístupu k internetu pomocí zásad spravované prohlížeče v Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Intune umožňuje integraci se službou Microsoft Passport for Work. Tato alternativní metoda pro přihlašování do Windows 10 pomocí účtu služby Active Directory nebo Azure Active Directory může nahradit hesla, čipové karty a virtuální čipové karty.|[Kontrola nastavení Microsoft Passportu v zařízeních s Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Přístup k prostředkům společnosti

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Profily certifikátů|Vytvořte a nasaďte profily důvěryhodných certifikátů a certifikáty protokolu SCEP (Simple Certificate Enrollment Protocol), které se dají použít k zabezpečení a ověření profilů Wi-Fi, VPN a e-mailu.|[Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Profily sítě Wi-Fi|Nasaďte uživatelům nastavení bezdrátové sítě. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné k připojení k firemní síti.|[Připojení Wi-Fi v Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-mailové profily|Vytvořte a nasaďte nastavení e-mailu pro zařízení. Díky tomu mají uživatelé na svých osobních zařízeních přístup k podnikovému e-mailu, bez nutnosti něco nastavovat.|[Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|Profily sítě VPN|Nasaďte nastavení sítě VPN pro uživatele a zařízení ve vaší organizaci. Nasazením těchto nastavení zjednodušíte koncovým uživatelům připojování k prostředkům v síti společnosti.|[Připojení VPN v Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Zásady podmíněného přístupu|Spravujte přístup k e-mailu Microsoft Exchange a službám SharePoint Online ze zařízení, která nespravuje Intune.|[Omezení přístupu k e-mailu a SharePointu pomocí Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventář a vytváření sestav

|Funkce|Podrobnosti|Další informace|
|--------------|-----------|--------------------|
|Inventář a vytváření sestav|Vyhledejte informace o vámi spravovaných zařízeních a softwaru, který používají.|[Seznámení se zařízeními s inventářem v Microsoft Intune](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Související témata
[Možnosti správy počítačů s Windows v Microsoft Intune](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


