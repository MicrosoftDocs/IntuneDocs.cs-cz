---
title: "Nastavení zásad pro Windows | Microsoft Intune"
description: "Ke konfiguraci nastavení pro registrovaná zařízení s Windows 8.1 a Windows 8 použijte obecné zásady konfigurace Windows (Windows 8.1 a novější) Intune."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: a70b81e490a5c55d9ce11bd8dbdfc42ab364273c


---

# Nastavení zásad pro Windows v Microsoft Intune
Ke konfiguraci následujících nastavení pro registrovaná zařízení s Windows 8 a Windows 8.1 použijte **obecné zásady konfigurace Windows (Windows 8.1 a novější)** Microsoft Intune:

## Nastavení použitelnosti

|Název nastavení|Podrobnosti|
|----------------|----------------------------------|
|**Použít všechny konfigurace ve Windows 10**|Umožňuje použít nastavení v těchto zásadách kromě zařízení s Windows 8 a Windows 8.1 také pro zařízení s Windows 10.|

## Nastavení zabezpečení

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vyžadovaný typ hesla**|Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|Ano|Ano|
|**Vyžadovaný typ hesla – Minimální počet znakových sad**|Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Toto nastavení určuje, kolik různých znakových sad musí být v hesle zahrnutých. Pro zařízení s iOS ale určuje počet znaků symbolu, které musí být v hesle.|Ano|Ano|
|**Minimální délka hesla**<sup>1</sup>|Konfiguruje minimální vyžadovanou délku hesla (ve znacích) pro zařízení.|Ano|Ano|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Vymaže zařízení, pokud tento počet pokusů o přihlášení selže.|Ano|Ano|
|**Počet minut nečinnosti před vypnutím displeje**|Vyberte počet minut, po které musí být zařízení nečinné, než bude vyžadované heslo pro odemčení.| Ano|Ano|
|**Omezená platnost hesla (ve dnech)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|Ano|Ano|
|**Pamatovat si historii hesel**|Určuje, jestli uživatel může konfigurovat dříve použitá hesla.|Ano|Ano|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.|Ano|Ano|
|**Povolit obrázkové heslo a PIN**|Povolí použití obrázkového hesla a kódu PIN v zařízení. Obrázkové heslo umožňuje uživateli přihlášení pomocí gesta na obrázku. Kód PIN umožňuje uživatelům rychlé přihlášení pomocí 4ciferného kódu.|Ano|Ano|
<sup>1</sup> Když nasadíte zásadu délky hesel na zařízení se systémem Windows RT, budou uživatelé přinucení změnit heslo, i když jejich aktuální heslo odpovídá požadavkům zásady.

## Nastavení šifrování

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vyžadovat šifrování u mobilního zařízení**<sup>1</sup>|Vyžaduje, aby soubory v zařízení byly šifrované.<br>Pro zařízení s Windows Phone 8 je potřeba nastavit hodnotu **Ano**.|Ano|Ne|
<sup>1</sup> Další informace pro zařízení s Windows 8.1

-   K vynucení šifrování na zařízeních s Windows 8.1 je potřeba na každé zařízení nainstalovat [aktualizaci MDM klienta pro Windows z prosince 2014](http://support.microsoft.com/kb/3013816) .

-   Pokud toto nastavení povolíte pro zařízení s Windows 8.1, všichni uživatelé zařízení musí mít účet Microsoft.

-   Šifrování funguje, jenom když zařízení splňuje hardwarové požadavky certifikace Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) .

-   Pokud vynutíte šifrování na zařízení, je obnovovací klíč přístupný jenom uživatelům s účtem Microsoft, ke kterému přistupují z účtu na Onedrivu. Tento klíč se nedá obnovit jménem uživatele.

## Nastavení ochrany proti malwaru

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vyžadovat síťovou bránu firewall**|Vyžaduje zapnutí brány Windows Firewall.|Ano|Ne|
|**Povolit SmartScreen**|Vyžaduje použití filtru Windows SmartScreen v zařízeních.|Ano|Ne|

## Nastavení systému

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vyžadovat automatické aktualizace**|Zapne nastavení automatických aktualizací v zařízeních.|Ano|Ne|
|**Vyžadovat automatické aktualizace – automatická instalace minimální klasifikace aktualizací**|Vyberte klasifikace aktualizací, které se instalují automaticky:<br /><br />-   **Důležité** – Nainstaluje všechny aktualizace klasifikované jako důležité.<br />-   **Doporučené** – Nainstaluje všechny aktualizace klasifikované jako důležité nebo doporučené.|Ano|Ne|
|**Řízení uživatelských účtů**|Vyžaduje použití řízení uživatelských účtů v zařízeních.|Ano|Ne|
|**Povolit odeslání diagnostických dat**|Povoluje zařízením odesílat diagnostické informace Microsoftu.|Ano|Ne|


## Nastavení cloudu – dokumenty a data

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Adresa URL pracovních složek**|Nastaví adresu URL pracovní složky, aby bylo možné synchronizovat dokumenty na všech zařízeních.|Ano|Ne|

## Nastavení e-mailu

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Nastavit účet Microsoft jako volitelný v aplikaci Windows Pošta**|Povolí přístup k aplikaci Windows Mail bez účtu Microsoft.|Ano|Ne|

## Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Povolit automatické vyplňování**|Uživatel může změnit nastavení automatického dokončování v prohlížeči.|Ano|Ne|
|**Povolit blokování automaticky otevíraných oken**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.|Ano|Ne|
|**Povolit moduly plug-in**|Uživatelé můžou přidávat do Internet Exploreru moduly plug-in.|Ano|Ne|
|**Povolit aktivní skriptování**|Prohlížeč může spouštět skripty, jako třeba skripty Active X.|Ano|Ne|
|**Povolit upozornění na podvod**|Povolí nebo zakáže upozornění na potenciální podvodné weby.|Ano|Ne|
|**Povolit intranetovému serveru zadání jednoslovné položky**|Umožňuje použití jednoho slova pro přesměrování Internet Exploreru na web, jako třeba Bing.|Ano|Ne|
|**Povolit automatické zjišťování sítě intranet**|Pomáhá konfigurovat zabezpečení intranetových serverů v Internet Exploreru.|Ano|Ne|
|**Úroveň zabezpečení pro internet**|Nastaví úroveň zabezpečení internetových serverů v Internet Exploreru.|Ano|Ne|
|**Úroveň zabezpečení pro intranet**|Nastaví úroveň zabezpečení intranetových sítí v Internet Exploreru.|Ano|Ne|
|**Úroveň zabezpečení pro důvěryhodné lokality**|Nakonfiguruje úroveň zabezpečení pro zónu důvěryhodných lokalit.|Ano|Ne|
|**Úroveň zabezpečení pro lokality s omezeným přístupem**|Nakonfiguruje úroveň zabezpečení pro zónu lokalit s omezeným přístupem.|Ano|Ne|
|**Odesílat hlavičku DNT (Do Not Track)**|Odesílá v Internet Exploreru hlavičku DNT (do not track) navštíveným webům.|Ano|Ne|
|**Povolit přístup nabídky podnikového režimu**|Umožňuje uživatelům přistupovat k možnostem nabídky podnikového režimu z Internet Exploreru.<br>Pokud je tato volba vybraná, můžete také určit **Umístění sestavy protokolování**, které obsahuje adresu URL sestavy, která zobrazuje weby, pro které uživatelé zapnuli přístup v podnikovém režimu.|Ano|Ne|
|**Umístění webů podnikového režimu**|Určuje umístění seznamu webů, které budou používat podnikový režim, pokud bude aktivní.|Ano|Ne|

## Nastavení možností zařízení – mobilní

|Název nastavení|Podrobnosti|Windows 8.1 a Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|Ano|Ne|



### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


