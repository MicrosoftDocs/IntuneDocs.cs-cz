---
title: "Nastavení omezení zařízení Intune pro Android | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Nastavení omezení zařízení s Androidem a Samsung KNOX Standard v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Obecné
-   **Kamera** – Povolí použití fotoaparátu v zařízení.
-   **Kopírování a vložení** – Povolí v zařízení funkce kopírování a vkládání.
-   **Sdílení přes schránku mezi aplikacemi** –Povolí používání schránky ke kopírování a vkládání mezi aplikacemi (jenom Samsung KNOX Standard).
-   **Odeslání diagnostických dat** – Zabrání uživateli v odesílání diagnostických dat ze zařízení.    
-   **Obnovení továrního nastavení** – Povolí uživateli obnovit v zařízení tovární nastavení.
-   **Zeměpisná poloha** – Povolí zařízení využívat informace o poloze (jenom Samsung KNOX Standard).
-   **Vypnutí** – Povolí uživateli vypnout zařízení.<br>Pokud je toto nastavení zakázané, není nastavení **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** pro zařízení Samsung KNOX Standard funkční.
-   **Snímek obrazovky** – Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.
-   **Hlasový asistent** – Povolí používání softwaru hlasového pomocníka na zařízení (jenom Samsung KNOX Standard).
-   **YouTube** – Povolí používání aplikace YouTube na zařízení (jenom Samsung KNOX Standard).

## <a name="password"></a>Heslo
-   **Zadání hesla nutné** – Vyžaduje, aby koncový uživatel zadal heslo k přístupu k zařízení.
-   **Minimální délka hesla** – Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi 4 a 16 znaky).
-   **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje počet minut nečinnosti, než se zařízení automaticky zamkne.
-   **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Určuje počet povolených neúspěšných přihlášení, než se zařízení vymaže.
-   **Konec platnosti hesla (dny)** – Určuje počet dní, než bude nutné změnit heslo zařízení.
-   **Požadovaný typ hesla** – Určuje požadovanou úroveň složitosti hesla a to, jestli se můžou používat biometrická zařízení.
-   **Znemožnit opakované použití předchozích hesel** – Zabrání koncovému uživateli vytvořit dříve používané heslo.
-   **Odemknutí pomocí otisků prstů** – Povolí na zařízeních, která to podporují, odemknutí pomocí otisku prstu.
-   **Smart Lock a jiní agenti pro určování důvěryhodnosti** – Umožňuje řídit funkci Smart Lock na kompatibilních zařízeních s Androidem (Samsung KNOX Standard 5.0 a novější). Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.
-   **Šifrování** – Vyžaduje, aby soubory v zařízení byly šifrované.

## <a name="google-play-store"></a>Obchod Google Play

-   **Obchod Google Play** – Povolí uživateli přístup k obchodu Google Play na zařízení (jenom Samsung KNOX Standard).

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
-   **Webový prohlížeč** – Určuje, jestli je možné používat výchozí webový prohlížeč zařízení.
-   **Automatické vyplňování** – Povolí používání funkce automatického vyplňování webového prohlížeče.
-   **Soubory cookie** – Povolí webovému prohlížeči v zařízení používat soubory cookie.
-   **JavaScript** – Povolí webovému prohlížeči v zařízení spouštět skripty Java.
-   **Automaticky otevíraná okna** – Povolí používání blokování automaticky otevíraných oken ve webovém prohlížeči.

## <a name="cloud-and-storage"></a>Cloud a úložiště
-   **Zálohovací služba Google** – Povolí použití zálohování Google.
-   **Automatická synchronizace účtu Google** – Povolí automatickou synchronizaci nastavení účtu Google.
-   **Vyměnitelné úložiště** – Povolí zařízení používat vyměnitelné úložiště, třeba SD kartu (jenom Samsung KNOX Standard).
-   **Šifrování na paměťových kartách** – Určuje, jestli musí být paměťová karta zařízení šifrovaná.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení
-   **Datový roaming** – Povolí datový roaming, když je zařízení v mobilní síti (jenom Samsung KNOX Standard).
-   **Zprávy SMS a MMS** – Povolí na zařízení používat zprávy SMS a MMS (jenom Samsung KNOX Standard).
-   **Hlasové vytáčení** – Povolí nebo zakáže funkci hlasového vytáčení na zařízení (jenom Samsung KNOX Standard).
-   **Hlasový roaming** – Povolí hlasový roaming, když je zařízení v mobilní síti (jenom Samsung KNOX Standard).
-   **Bluetooth** – Povolí používání Bluetooth na zařízení (jenom Samsung KNOX Standard).
-   **Bezkontaktní komunikace (NFC)** – Povolí operace, které používají bezkontaktní komunikaci, pokud je zařízení podporuje (jenom Samsung KNOX Standard).
-   **Wi-Fi** – Povolí použití možností Wi-Fi zařízení (jenom Samsung KNOX Standard).
-   **Wi-Fi tethering** – Povolí sdílení mobilního internetového připojení (tethering) přes Wi-Fi na zařízení (jenom Samsung KNOX Standard).

## <a name="kiosk"></a>Kiosk
-   **Vyberte spravovanou aplikaci** – Vyhledejte a vyberte spravovanou aplikaci, která se může spustit, když je zařízení v celoobrazovkovém režimu (v současné době se nepodporují aplikace v podobě odkazu na obchod). Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět.
-   **Tlačítko pro režim spánku obrazovky** – Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.
-   **Tlačítka hlasitosti** – Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.



<!--HONumber=Feb17_HO1-->


