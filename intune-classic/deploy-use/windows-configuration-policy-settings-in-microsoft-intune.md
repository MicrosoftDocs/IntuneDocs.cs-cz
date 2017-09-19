---
title: "Nastavení zásad pro Windows"
description: "Ke konfiguraci nastavení pro registrovaná zařízení s Windows 8.1 a Windows 8 použijte obecné zásady konfigurace Windows (Windows 8.1 a novější) Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57ec28e843e6c90e81824cabff51c3e5bc85dae1
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a>Nastavení zásad pro Windows v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ke konfiguraci následujících nastavení pro zaregistrovaná zařízení s Windows 8, Windows 8.1 a Windows RT 8.1 použijte **obecné zásady konfigurace Windows (Windows 8.1 a novější)** Microsoft Intune:

## <a name="applicability-settings"></a>Nastavení použitelnosti

|Název nastavení|Podrobnosti|
|----------------|----------------------------------|
|**Použít všechny konfigurace ve Windows 10**|Umožňuje použít nastavení v těchto zásadách kromě zařízení s Windows 8 a Windows 8.1 také pro zařízení s Windows 10.|

## <a name="security-settings"></a>Nastavení zabezpečení

|Název nastavení|Podrobnosti|
|----------------|------|
|**Vyžadovaný typ hesla**|Určuje vyžadované vlastnosti hesla, například jenom číslice nebo alfanumerické znaky.|
|**Vyžadovaný typ hesla – Minimální počet znakových sad**|Určuje, kolik různých znakových sad musí být v hesle zahrnutých. Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Pro zařízení s iOSem ale toto nastavení určuje počet symbolů, které musí heslo obsahovat.|
|**Minimální délka hesla**|Konfiguruje minimální vyžadovanou délku hesla (ve znacích).|
|**Počet povolených opakovaných neúspěšných přihlášení, než se zařízení vymaže**|Vymaže zařízení po zadaném počtu neúspěšných pokusů o přihlášení.|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje počet minut, po které musí být zařízení nečinné, než bude vyžadované heslo pro odemčení.|
|**Vypršení platnosti hesla (dny)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|
|**Pamatovat si historii hesel**|Určuje, jestli uživatel může konfigurovat dříve použitá hesla.|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.|
|**Povolit obrázkové heslo a PIN**|Povolí použití obrázkového hesla a kódu PIN. Obrázkové heslo umožňuje uživateli přihlášení pomocí gesta na obrázku. Kód PIN umožňuje uživatelům rychlé přihlášení pomocí čtyřmístného kódu.|

## <a name="encryption-settings"></a>Nastavení šifrování

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Vyžadovat šifrování u mobilního zařízení**<sup>1</sup>|Vyžaduje, aby soubory v zařízení byly šifrované.|
<sup>1</sup> Další informace pro zařízení s Windows 8.1

-   K vynucení šifrování na zařízeních s Windows 8.1 je potřeba na každé zařízení nainstalovat [aktualizaci MDM klienta pro Windows z prosince 2014](http://support.microsoft.com/kb/3013816).

-   Pokud toto nastavení povolíte pro zařízení s Windows 8.1, všichni uživatelé zařízení musí mít účet Microsoft.

-   Šifrování funguje, jenom když zařízení splňuje hardwarové požadavky certifikace Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) .

-   Pokud vynutíte šifrování na zařízení, je obnovovací klíč přístupný jenom uživatelům s účtem Microsoft, ke kterému přistupují z účtu na Onedrivu. Tento klíč se nedá obnovit jménem uživatele.

## <a name="malware-settings"></a>Nastavení ochrany proti malwaru

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Vyžadovat síťovou bránu firewall**|Vyžaduje zapnutí brány Windows Firewall.|
|**Povolit filtr SmartScreen**|Vyžaduje použití filtru Windows SmartScreen.|

## <a name="system-settings"></a>Nastavení systému

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Vyžadovat automatické aktualizace**|Zapne v zařízeních nastavení automatických aktualizací.|
|**Vyžadovat automatické aktualizace – Minimální klasifikace aktualizací, které se mají instalovat automaticky**|Umožňuje vybrat klasifikaci aktualizací, které se budou instalovat automaticky:<br /><br />-   **Důležité** – Nainstaluje všechny aktualizace klasifikované jako důležité.<br />-   **Doporučené** – Nainstaluje všechny aktualizace klasifikované jako důležité nebo doporučené.|
|**Řízení uživatelských účtů**|Vyžaduje použití řízení uživatelských účtů (UAC) v zařízeních.|
|**Povolit odeslání diagnostických dat**|Povolí zařízení odesílat diagnostické informace Microsoftu.|


## <a name="cloud-settings--documents-and-data"></a>Nastavení cloudu – dokumenty a data

|Název nastavení|Podrobnosti|
|----------------|------|
|**Adresa URL pracovních složek**|Nastaví adresu URL pracovní složky, aby bylo možné synchronizovat dokumenty na všech zařízeních.|

## <a name="email-settings"></a>Nastavení e-mailu

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Nastavit účet Microsoft v aplikaci Windows Mail jako volitelný**|Povolí přístup k aplikaci Windows Mail bez účtu Microsoft.|

## <a name="application-settings---browser"></a>Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit automatické vyplňování**|Povolí uživatelům změnit nastavení automatického dokončování v prohlížeči.|
|**Povolit blokování automaticky otevíraných oken**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.|
|**Povolit moduly plug-in**|Umožní uživatelům přidávat do Internet Exploreru moduly plug-in.|
|**Povolit aktivní skriptování**|Povolí prohlížeči spouštění skriptů, jako třeba skriptů Active X.|
|**Povolit upozornění na podvod**|Povolí nebo zakáže upozornění na potenciální podvodné weby.|
|**Povolit intranetový server po zadání jednoslovné položky**|Umožňuje použití jednoho slova pro přesměrování Internet Exploreru na web, jako třeba Bing.|
|**Povolit automatické zjišťování intranetové sítě**|Pomáhá konfigurovat zabezpečení intranetových serverů v Internet Exploreru.|
|**Úroveň zabezpečení internetu**|Nastaví úroveň zabezpečení internetových serverů v Internet Exploreru.|
|**Úroveň zabezpečení intranetu**|Nastaví úroveň zabezpečení intranetových serverů v Internet Exploreru.|
|**Úroveň zabezpečení důvěryhodných serverů**|Nakonfiguruje úroveň zabezpečení pro zónu důvěryhodných lokalit.|
|**Úroveň zabezpečení serverů s omezeným přístupem**|Nakonfiguruje úroveň zabezpečení pro zónu lokalit s omezeným přístupem.|
|**Odesílat hlavičku Nesledovat**|Odesílá v Internet Exploreru hlavičku DNT (do not track) navštíveným webům.|
|**Povolit přístup do nabídky Režim rozlehlé sítě**|Umožňuje uživatelům přistupovat k možnostem nabídky podnikového režimu z Internet Exploreru.<br>Když zapnete toto nastavení můžete také určit **Umístění sestavy protokolování**, které obsahuje adresu URL sestavy, která zobrazuje weby, pro které uživatelé zapnuli přístup v podnikovém režimu.|
|**Umístění webů podnikového režimu**|Určuje umístění seznamu webů, které budou používat podnikový režim, pokud bude aktivní.|

## <a name="device-capabilities-settings---cellular"></a>Nastavení možností zařízení – mobilní

|Název nastavení|Podrobnosti|
|----------------|----|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|



### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
