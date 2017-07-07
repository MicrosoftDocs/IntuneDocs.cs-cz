---
title: "Nastavení omezení pro zařízení s Androidem v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44d80e1c72b58eccd4e69b1d561c7d651f39b3c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení zařízení používajících Android a Samsung KNOX Standard v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tato nastavení spolu se zásadami omezení pro zařízení s Androidem se používají ke konfiguraci zařízení v organizaci.

## <a name="general"></a>Obecné

|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Fotoaparát**|Umožňuje použití fotoaparátu v zařízení.|Ano|Ano|
|**Kopírování a vložení**|Povolí v zařízení funkce kopírování a vkládání.|Ne|Ano|
|**Sdílení přes schránku mezi aplikacemi**|Povolí používání schránky pro kopírování a vkládání mezi jednotlivými aplikacemi.|Ne|Ano|
|**Odeslání diagnostických dat**|Zabrání uživateli v odesílání diagnostických dat ze zařízení.|Ne|Ano|
|**Obnovení továrního nastavení**|Umožňuje uživateli obnovit v zařízení výrobní nastavení.|Ne|Ano|
|**Zeměpisná poloha**|Povolí zařízení využívat informace o poloze (jenom Samsung KNOX Standard).|Ne|Ano|
|**Vypnutí**|Povolí uživateli vypnout zařízení.<br>Pokud je tato možnost zakázaná, nepůjde nastavit ani možnost **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**.|Ne|Ano|
|**Snímek obrazovky**|Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.|Ne|Ano|
|**Hlasový asistent**|Povolí použití softwaru hlasového asistenta v zařízení.|Ne|Ano|
|**YouTube**|Povoluje v zařízení použití aplikace YouTube.|Ne|Ano|
|**Sdílená zařízení**|Nakonfigurujte spravované zařízení Samsung KNOX Standard jako sdílené. V tomto režimu se koncoví uživatelé můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení zůstává spravované bez ohledu na to, jestli se používá.<br>Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.|Ne|Ano|

## <a name="password"></a>Heslo

|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Heslo**|Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.|Ano|Ano|
|**Minimální délka hesla**|Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi 4 a 16 znaky).|Ano|Ano|
|**Maximální počet minut nečinnosti, po které se zamkne obrazovka**|Určuje počet minut nečinnosti, než se zařízení automaticky zamkne.|Ano|Ano|
|**Počet neúspěšných přihlášení před vymazáním obsahu zařízení**|Určuje počet povolených neúspěšných přihlášení, než bude zařízení vymazáno.|Ano|Ano|
|**Konec platnosti hesla (dny)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|Ano|Ano|
|**Vyžadovaný typ hesla**|Určuje požadovanou úroveň složitosti hesla a to, jestli se můžou používat biometrická zařízení. Vybírejte z těchto možností:<br><br>    -     **Výchozí ze zařízení**<br>-     **Biometrika s nízkým zabezpečením**<br>    -     **Aspoň číselné**<br>    -     **Číselné komplexní** (opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena)<sup>1</sup><br>    -     **Aspoň abecední**<br>    -     **Aspoň alfanumerické**<br>    -     **Aspoň alfanumerické se symboly**|Ano|Ano|
|**Znemožnit opakované použití předchozích hesel**|Zakáže koncovému uživateli nastavit dříve používané heslo.|Ano|Ano|
|**Odemknutí pomocí otisků prstů**|Povolí na zařízeních, která to podporují, odemknutí pomocí otisku prstu.|Ne|Ano|
|**Smart Lock a jiní agenti pro určování důvěryhodnosti**|Umožňuje řídit funkci Smart Lock na kompatibilních zařízeních s Androidem (Samsung KNOX Standard 5.0 a novějším). Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné ji například použít, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.|Ano (5.0 nebo novější)|Ano|
|**Šifrování**|Vyžaduje, aby soubory v zařízení byly šifrované.|Ano|Ano|

<sup>1</sup> Před přiřazením tohoto nastavení k zařízením zkontrolujte, jestli je aplikace Portál společnosti v daných zařízeních aktualizovaná na nejnovější verzi.

Pokud nakonfigurujete nastavení **Číselné komplexní** a potom ho přiřadíte k zařízení, které používá verzi Androidu starší než 5.0, bude platit následující chování.
- Pokud aplikace Portál společnosti používá verzi starší než 1704, nepoužijí se u zařízení žádné zásady PIN kódu a na portálu Intune se zobrazí chyba.
- Pokud aplikace Portál společnosti používá verzi 1704 nebo novější, je možné použít jenom jednoduchý PIN kód. Verze Androidu starší než 5.0 toto nastavení nepodporují. Na portálu Intune se nezobrazí žádná chyba.


## <a name="google-play-store"></a>Obchod Google Play

|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Obchod Google Play**|Povolí uživatelům na zařízení přístup do obchodu Google Play.|Ne|Ano|

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete pro zařízení se systémy Android a Samsung KNOX Standard nakonfigurovat některý z následujících seznamů:

**Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Kvůli zachování kompatibility nesmí uživatelé instalovat jiné aplikace. Aplikace, které spravuje Intune, jsou povolené automaticky.
Profily zařízení, které obsahují nastavení aplikací s omezeným přístupem, se musí přiřadit skupinám uživatelů.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací, použijte následující postup:

V [oddílu Aplikace na Google Play](https://play.google.com/store/apps) najděte aplikaci, kterou chcete použít.

Otevřete instalační stránku aplikace a zkopírujte adresu URL do schránky. Tuto adresu URL teď můžete použít v seznamu kompatibilních nebo nekompatibilních aplikací.

Příklad: Na webu Google Play vyhledejte systém Microsoft Office Mobile. Použijte adresu URL: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a získat seznam ze souboru csv. Použijte formát <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo klikněte na **Export** v souboru csv obsahujícím seznam omezených aplikací ve stejném formátu.      

## <a name="browser"></a>Prohlížeč
|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Webový prohlížeč**|Určuje, jestli je možné použít výchozí webový prohlížeč zařízení.|Ne|Ano|
|**Automatické vyplňování**|Umožňuje používání funkce automatického vyplňování webového prohlížeče.|Ne|Ano|
|**Soubory cookie**|Povolí webovému prohlížeči v zařízení používat soubory cookie.|Ne|Ano|
|**JavaScript**|Povolí webovému prohlížeči v zařízení spouštět skripty Java.|Ne|Ano|
|**Automaticky otevíraná okna**|Povolí používání blokování automaticky otevíraných oken ve webovém prohlížeči.|Ne|Ano|

## <a name="cloud-and-storage"></a>Cloud a úložiště
|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Zálohovací služba Google**|Povoluje použití zálohování Google.|Ne|Ano|
|**Automatická synchronizace účtu Google**|Povoluje automatickou synchronizaci nastavení účtu Google.|Ne|Ano|
|**Vyměnitelné úložiště**|Povolí použití vyjímatelného úložiště v zařízení, třeba SD karty.|Ne|Ano|
|**Šifrování na paměťových kartách**|Určuje, jestli musí být paměťová karta zařízení šifrovaná.|Ne|Ano|

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení
|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Zprávy SMS a MMS**|Povolí zařízení použití SMS a MMS zpráv.|Ne|Ano|
|**Hlasové vytáčení**|Povolí nebo zakáže použití funkce hlasového vytáčení v zařízení.|Ne|Ano|
|**Hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Bluetooth**|Povolí používání připojení Bluetooth na zařízení.|Ne|Ano|
|**NFC**|Umožní operace, které na podporovaných zařízeních používají bezkontaktní komunikaci.|Ne|Ano|
|**Wi-Fi**|Povolí použití možností Wi-Fi zařízení.|Ne|Ano|
|**Wi-Fi tethering**|Povolí použití sdíleného internetového připojení přes Wi-Fi na zařízení.|Ne|Ano|

## <a name="kiosk"></a>Kiosk
|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Vyberte spravovanou aplikaci**|Pokud chcete přidat jednu nebo více aplikací, které se budou moct spustit, když je zařízení v beznabídkovém režimu, zvolte jednu z následujících možností. Žádné jiné aplikace se na zařízení nebudou moct spustit.<br><br>- **Přidat aplikace pomocí názvu balíčku**<br>- **Přidat aplikace pomocí adresy URL**<br>- **Přidat spravované aplikace**|Ne|Ano|
|**Tlačítko pro režim spánku obrazovky**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|Ne|Ano|
|**Tlačítka pro hlasitost**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|Ne|Ano|
