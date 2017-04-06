---
title: "Nastavení omezení pro zařízení s Androidem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f316b332c3f1b80b9d6af488943298fcfea13741
ms.openlocfilehash: 009c6491b8ce457a371f5db31de3f122fa41fb95
ms.lasthandoff: 03/30/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení zařízení používajících Android a Samsung KNOX Standard v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

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
|**Vypnutí**|Povolí uživateli vypnout zařízení.<br>Pokud je toto nastavení zakázané, není nastavení **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** pro zařízení Samsung KNOX Standard funkční.|Ne|Ano|
|**Snímek obrazovky**|Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.|Ne|Ano|
|**Hlasový asistent**|Povolí použití softwaru hlasového asistenta v zařízení.|Ne|Ano|
|**YouTube**|Povoluje v zařízení použití aplikace YouTube.|Ne|Ano|

## <a name="password"></a>Heslo

|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Heslo**|Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.|Ano|Ano|
|**Minimální délka hesla**|Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi 4 a 16 znaky).|Ano|Ano|
|**Maximální počet minut nečinnosti, po které se zamkne obrazovka**|Určuje počet minut nečinnosti, než se zařízení automaticky zamkne.|Ano|Ano|
|**Počet neúspěšných přihlášení před vymazáním obsahu zařízení**|Určuje počet povolených neúspěšných přihlášení, než bude zařízení vymazáno.|Ano|Ano|
|**Konec platnosti hesla (dny)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|Ano|Ano|
|**Požadovaný typ hesla**|Určuje požadovanou úroveň složitosti hesla a to, jestli se můžou používat biometrická zařízení.|Ano|Ano|
|**Znemožnit opakované použití předchozích hesel**|Zakáže koncovému uživateli nastavit dříve používané heslo.|Ano|Ano|
|**Odemknutí pomocí otisků prstů**|Povolí na zařízeních, která to podporují, odemknutí pomocí otisku prstu.|Ne|Ano|
|**Smart Lock a jiní agenti pro určování důvěryhodnosti**|Umožňuje řídit funkci Smart Lock na kompatibilních zařízeních s Androidem (Samsung KNOX Standard 5.0 a novějším). Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.|Ano (5.0 nebo novější)|Ne|
|**Šifrování**|Vyžaduje, aby soubory v zařízení byly šifrované.|Ano|Ano|

## <a name="google-play-store"></a>Obchod Google Play

|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Obchod Google Play**|Povolí uživatelům na zařízení přístup do obchodu Google Play.|Ne|Ano|

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

**Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Aby byla zachovaná kompatibilita, uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.
Profily zařízení, které obsahují nastavení aplikací s omezeným přístupem, se musí nasadit do skupin uživatelů.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací, použijte následující postup:

V [oddílu Aplikace na Google Play](https://play.google.com/store/apps) najděte aplikaci, kterou chcete použít.

Otevřete instalační stránku aplikace a zkopírujte adresu URL do schránky. Tu teď můžete použít jako adresu URL v seznamu kompatibilních nebo nekompatibilních aplikací.

Příklad: Na webu Google Play vyhledejte systém Microsoft Office Mobile. Použijete adresu URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a naplnit seznam ze souboru csv ve formátu <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo kliknout na **Export** a vytvořit si soubor csv obsahující seznam aplikací s omezeným přístupem ve stejném formátu.        

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
|**NFC**|Umožňuje operace, které používají bezkontaktní komunikaci, pokud je zařízení podporuje.|Ne|Ano|
|**Wi-Fi**|Povolí použití možností Wi-Fi zařízení.|Ne|Ano|
|**Wi-Fi tethering**|Povolí použití sdíleného internetového připojení přes Wi-Fi na zařízení.|Ne|Ano|

## <a name="kiosk"></a>Kiosk
|||||
|-|-|-|-|
|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|**Vyberte spravovanou aplikaci**|Vyhledejte a vyberte spravovanou aplikaci, která se může spustit, když je zařízení v celoobrazovkovém režimu (v současné době se nepodporují aplikace v podobě odkazu na obchod). Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět.|Ne|Ano|
|**Tlačítko pro režim spánku obrazovky**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|Ne|Ano|
|**Tlačítka pro hlasitost**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|Ne|Ano|

