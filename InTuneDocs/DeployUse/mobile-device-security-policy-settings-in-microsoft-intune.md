---
title: "Nastavení zásad zabezpečení mobilního zařízení | Microsoft Intune"
description: "Intune můžete použít ke konfiguraci široké škály nastavení, která se dají nasadit na spravovaných zařízeních v organizaci."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 388426657c5fa96289f5e14a85e8c299e4b50037
ms.openlocfilehash: ac19128499f078b4fe7d16713f18c78b248d38db



---

# Nastavení zásad zabezpečení mobilního zařízení v Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune teď nabízí oddělené zásady konfigurace pro každou platformu zařízení. Tyto zásady obsahují nejaktuálnější nastavení, která můžete použít. Můžete dál používat zásady zabezpečení mobilních zařízení a všechna existující nasazení budou i nadále fungovat. Měli byste si ale v nejbližší době naplánovat migraci na nové zásady konfigurace, protože zásady zabezpečení mobilních zařízení budou v budoucnu odebrány.

Zásady zabezpečení mobilních zařízení Intune můžete použít ke konfiguraci široké škály nastavení, která se dají nasadit na spravovaných zařízeních v organizaci. Tato nastavení se dají použít k řízení funkcí a zabezpečení vašich zařízení.

Zásady zabezpečení mobilních zařízení můžete vytvořit a nasadit u následujících typů zařízení:

-   Windows RT 8.1 a zaregistrovaná zařízení se systémem Windows 8.1

-   Windows RT

-   Windows Phone 8 a Windows Phone 8.1

-   iOS

-   Android a Samsung KNOX

> [!NOTE]
> Některá nastavení se u některých zařízení nedají použít. Úplný seznam nastavení, která můžete nakonfigurovat, najdete v následujících tabulkách.

## Nastavení zabezpečení

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Ne|Ne|Ano|Ano|Ano|
|**Vyžadovaný typ hesla**<br /><br />Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|Ano|Ano|Ano|Ano|Ne|
|**Vyžadovaný typ hesla – Minimální počet znakových sad**<br /><br />Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Toto nastavení určuje, kolik různých znakových sad musí být v hesle zahrnutých. Pro zařízení s iOS ale určuje počet symbolových znaků, které musí heslo obsahovat.|Ano|Ano|Ano|Ano|Ne|
|**Minimální délka hesla**|Ano|Ano|Ano|Ano|Ano|
|**Povolit jednoduchá hesla**<br /><br />Příklady jednoduchých hesel: 0000 a 1234.|Ne|Ne|Ano|Ano|Ne|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Ano|Ano|Ano|Ano|Ano|
|**Počet minut nečinnosti před vypnutím displeje**<sup>1</sup>|Ano|Ano|Ano|Ano|Ano|
|**Vypršení platnosti hesla (dny)**|Ano|Ano|Ano|Ano|Ano|
|**Pamatovat si historii hesel**|Ano|Ano|Ano|Ano|Ano|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Ano|Ano|Ano|Ano|Ano|
|**Kvalita hesla**|Ne|Ne|Ne|Ne|Ano|
|**Povolit obrázkové heslo a PIN**|Ano|Ano|Ne|Ne|Ne|
|**Počet minut nečinnosti před vyžadováním hesla**|Ne|Ne|Ne|Ano|Ne|
|**Povolit odemknutí otiskem prstu**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
<sup>1</sup>Pokud pro zařízení s iOS nakonfigurujete nastavení **Počet minut nečinnosti před vypnutím displeje** a **Počet minut nečinnosti před vyžadováním hesla**, tato nastavení se použijí v uvedeném pořadí. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

Když nasadíte zásadu délky hesel na zařízení se systémem Windows RT, budou uživatelé přinucení změnit heslo, i když jejich aktuální heslo odpovídá požadavkům zásady.

## Nastavení šifrování

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Vyžadovat šifrování u mobilního zařízení**<sup>1</sup><br /><br />Pro zařízení s Windows Phone 8 je potřeba nastavit hodnotu **Ano**.<br /><br />Pokud chcete povolit šifrování na zařízeních iOS, povolte nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.|Ano|Ne|Ano|Ne|Ano|
|**Vyžadovat šifrování u paměťových karet**<br /><br />Platí i pro zařízení, která spravuje Exchange ActiveSync.|není k dispozici|není k dispozici|není k dispozici <br />Aplikace a související data se šifrují automaticky.|není k dispozici|Ano|
<sup>1</sup>Další informace pro zařízení s Windows 8.1:

-   K vynucení šifrování na zařízeních s Windows 8.1 je potřeba na každé zařízení nainstalovat [aktualizaci MDM klienta pro Windows z prosince 2014](http://support.microsoft.com/kb/3013816) .

-   Pokud toto nastavení povolíte pro zařízení s Windows 8.1, všichni uživatelé zařízení musí mít účet Microsoft.

-   Šifrování funguje, jenom když zařízení splňuje hardwarové požadavky certifikace Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) .

-   Pokud vynutíte šifrování na zařízení, je obnovovací klíč přístupný jenom uživatelům s účtem Microsoft, ke kterému přistupují z účtu na Onedrivu. Tento klíč se nedá obnovit jménem uživatele.

## Nastavení ochrany proti malwaru

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Vyžadovat síťovou bránu firewall**|Ano|Ne|Ne|Ne|Ne|
|**Povolit SmartScreen**|Ano|Ne|Ne|Ne|Ne|

## Nastavení systému

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Vyžadovat automatické aktualizace**|Ano|Ne|Ne|Ne|Ne|
|**Vyžadovat automatické aktualizace – automatická instalace minimální klasifikace aktualizací**<br /><br />Vyberte klasifikace aktualizací, které se instalují automaticky:<br /><br />- **Důležité**. Nainstaluje všechny aktualizace klasifikované jako důležité.<br /><br />- **Doporučené**. Nainstaluje všechny aktualizace klasifikované jako důležité nebo doporučené.|Ano|Ne|Ne|Ne|Ne|
|**Povolit snímek obrazovky**|Ne|Ne|Jenom Windows Phone 8.1|Ano|Ano (jenom Samsung KNOX)|
|**Povolit řídicí centrum na zamykací obrazovce**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
|**Povolit zobrazení oznámení na zamykací obrazovce**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
|**Povolit zobrazení informací o dnešku na zamykací obrazovce**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
|**Řízení uživatelských účtů**|Ano|Ne|Ne|Ne|Ne|
|**Povolit odeslání diagnostických dat**|Ano|Ne|Jenom Windows Phone 8.1|Ano|Ano (jenom Samsung KNOX)|
|**Povolit nedůvěryhodné certifikáty TLS**|Ne|Ne|Ne|Ano|Ne|
|**Povolit software osobní Peněženka při uzamčení**|Ne|Ne|Ne|Ano|Ne|
|**Povolit obnovení továrního nastavení**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|


## Nastavení cloudu – dokumenty a data

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit zálohování na iCloud**|Ne|Ne|Ne|Ano|Ne|
|**Povolit synchronizaci dokumentů s iCloudem**|Ne|Ne|Ne|Ano|Ne|
|**Povolit synchronizaci datového proudu fotografií s iCloudem**|Ne|Ne|Ne|Ano|Ne|
|**Vyžadovat šifrované zálohování**|Ne|Ne|Ne|Ano|Ne|
|**Adresa URL pracovních složek**<br /><br />Nastaví adresu URL pracovní složky, aby bylo možné synchronizovat dokumenty na všech zařízeních.|Ano|Ne|Ne|Ne|Ne|
|**Povolit zálohování Google**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|

## Nastavení cloudu – účty a synchronizace

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit účet Microsoft**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ne|
|**Povolit automatickou synchronizaci účtu Google**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|

## Nastavení e-mailu

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit uživatelům stahovat přílohy e-mailů**<sup>1</sup>|není k dispozici|není k dispozici|není k dispozici|není k dispozici|není k dispozici|
|**Interval synchronizace e-mailu** <br /><br />Platí i pro zařízení, která spravuje Exchange ActiveSync.|není k dispozici|není k dispozici|není k dispozici|není k dispozici|není k dispozici|
|**Povolí mobilní zařízení, která tato nastavení pro synchronizaci se serverem Exchange (Exchange ActiveSync) plně nepodporují.** <br /><br />Platí i pro zařízení, která spravuje Exchange ActiveSync.|není k dispozici|není k dispozici|není k dispozici|není k dispozici|není k dispozici|
|**Nastavit účet Microsoft jako volitelný v aplikaci Windows Pošta**|Ano|Ne|Ne|Ne|Ne|
|**Povolit vlastní e-mailové účty**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ne|

## Nastavení aplikace – prohlížeč

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit webový prohlížeč**|Ne|Ne|Jenom Windows Phone 8.1|Ano|Ano (jenom Samsung KNOX)|
|**Povolit automatické vyplňování**|Ano|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit blokování automaticky otevíraných oken**|Ano|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit soubory cookie**|Ne|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit moduly plug-in**|Ano|Ne|Ne|Ne|Ne|
|**Povolit aktivní skriptování**|Ano|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit upozornění na podvod**|Ano|Ne|Ne|Ano|Ne|
|**Povolit intranetovému serveru zadání jednoslovné položky**<br /><br />Umožňuje použití jednoho slova pro přesměrování Internet Exploreru na web, jako třeba Bing.|Ano|Ne|Ne|Ne|Ne|
|**Povolit automatické zjišťování sítě intranet**|Ano|Ne|Ne|Ne|Ne|
|**Úroveň zabezpečení pro internet**|Ano|Ne|Ne|Ne|Ne|
|**Úroveň zabezpečení pro intranet**|Ano|Ne|Ne|Ne|Ne|
|**Úroveň zabezpečení pro důvěryhodné lokality**|Ano|Ne|Ne|Ne|Ne|
|**Úroveň zabezpečení pro lokality s omezeným přístupem**|Ano|Ne|Ne|Ne|Ne|
|**Odesílat hlavičku DNT (Do Not Track)**|Ano|Ne|Ne|Ne|Ne|
|**Povolit přístup nabídky podnikového režimu**|Ano|Ne|Ne|Ne|Ne|
|**Umístění webů podnikového režimu**|Ano|Ne|Ne|Ne|Ne|

## Nastavení aplikace – aplikace

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit obchod s aplikacemi**|Ne|Ne|Jenom Windows Phone 8.1|Ano|Ano (jenom Samsung KNOX)|
|**Vyžadovat heslo pro přístup do obchodu s aplikacemi**|Ne|Ne|Ne|Ano|Ne|
|**Povolit nákupy v aplikaci**|Ne|Ne|Ne|Ano|Ne|
|**Povolit spravované dokumenty v jiných nespravovaných aplikacích**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
|**Povolit nespravované dokumenty v jiných spravovaných aplikacích**|Ne|Ne|Ne|iOS 7 nebo novější|Ne|
|**Povolit videokonference**|Ne|Ne|Ne|Ano|Ne|
|**Povolit obsah pro dospělé v obchodě s mediálním obsahem**|Ne|Ne|Ne|Ano|Ne|
|**Povolit instalace aplikací**|Ne|Ne|Ne|iOS 6 nebo novější|Ne|

## Nastavení aplikace – hry

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit přátele z herního centra**|Ne|Ne|Ne|Ano|Ne|
|**Povolit hru s více hráči**|Ne|Ne|Ne|Ano|Ne|

## Nastavení možností zařízení – hardware

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit fotoaparát**|Ne|Ne|Jenom Windows Phone 8.1|Ano|Ano|
|**Povolit vyměnitelné úložiště**|Ne|Ne|Ano|Ne|Ano (jenom Samsung KNOX)|
|**Povolit Wi-Fi**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit sdílení internetového připojení přes Wi-Fi**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit automatické připojení k bezplatným Wi-Fi hotspotům**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ne|
|**Povolit oznamování Wi-Fi hotspotů**<br /><br />Umožní odesílání informací o připojeních Wi-Fi, aby uživatel mohl nacházet možnosti připojení v okolí.|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ne|
|**Povolit zeměpisnou polohu**<br /><br />Umožňuje zařízení využívat informace o poloze.|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit komunikaci NFC**<br /><br />Umožní operace, které používají bezkontaktní komunikaci.|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit Bluetooth**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit vypnutí napájení**<br>Pokud je toto nastavení zakázané, nastavení **Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno** pro zařízení Samsung KNOX není funkční.|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|

## Nastavení možností zařízení – mobilní

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit hlasový roaming**|Ne|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit datový roaming**|Ano|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit automatickou synchronizaci při roamingu**|Ne|Ne|Ne|Ano|Ne|
|**Povolit SMS a MMS zprávy**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|

## Nastavení možností zařízení – funkce

|Název nastavení|Windows 8.1 a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|iOS|Android a Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Povolit hlasového asistenta**|Ne|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit hlasového asistenta při uzamknutém zařízení**|Ne|Ne|Ne|Ano|Ne|
|**Povolit hlasové vytáčení**|Ne|Ne|Ne|Ano|Ano (jenom Samsung KNOX)|
|**Povolit kopírování a vkládání**|Ne|Ne|Jenom Windows Phone 8.1|Ne|Ano (jenom Samsung KNOX)|
|**Povolit sdílení schránky mezi aplikacemi**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|
|**Povolit YouTube**|Ne|Ne|Ne|Ne|Ano (jenom Samsung KNOX)|

### Viz taky
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


