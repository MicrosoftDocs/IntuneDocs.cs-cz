---
title: "Nastavení omezení pro zařízení s Androidem v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b9e009e94fb4d9bdb99960e0d238d5471d1f4b50
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení zařízení používajících Android a Samsung KNOX Standard v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tato nastavení spolu se zásadami omezení pro zařízení s Androidem se používají ke konfiguraci zařízení v organizaci.

## <a name="general"></a>Obecné

- **Kamera** – Povolí použití fotoaparátu v zařízení.
- **Kopírování a vložení (jenom Samsung KNOX)** – Povolí v zařízení funkce kopírování a vkládání.
- **Sdílení přes schránku mezi aplikacemi (jenom Samsung KNOX)** –Povolí používání schránky ke kopírování a vkládání mezi aplikacemi.
- **Odeslání diagnostických dat (jenom Samsung KNOX)** – Zabrání uživateli v odesílání diagnostických dat ze zařízení.
- **Obnovení továrního nastavení (jenom Samsung KNOX)** – Povolí uživateli obnovit v zařízení tovární nastavení.
- **Zeměpisná poloha (jenom Samsung KNOX)** – Povolí zařízení využívat informace o poloze.
- **Vypnutí (jenom Samsung KNOX)** – Povolí uživateli vypnout zařízení.<br>Pokud je tato možnost zakázaná, nepůjde nastavit ani možnost **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**.
- **Snímek obrazovky (jenom Samsung KNOX)** – Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.
- **Hlasový asistent (jenom Samsung KNOX)** – Povolí používání softwaru hlasového pomocníka na zařízení.
- **YouTube (jenom Samsung KNOX)** – Povolí používání aplikace YouTube na zařízení.
- **Sdílená zařízení** – Nakonfigurujte spravované zařízení Samsung KNOX Standard jako sdílené. V tomto režimu se koncoví uživatelé můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení zůstává spravované bez ohledu na to, jestli se používá.<br>Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

## <a name="password"></a>Heslo

- **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.|Ano|Ano|
- **Minimální délka hesla** – Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi 4 a 16 znaky).
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje počet minut nečinnosti, než se zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Určuje počet povolených neúspěšných přihlášení, než se zařízení vymaže.
- **Konec platnosti hesla (dny)** – Určuje počet dní, než bude nutné změnit heslo zařízení.
-  **Požadovaný typ hesla** – Určuje požadovanou úroveň složitosti hesla a to, jestli se můžou používat biometrická zařízení. Vybírejte z těchto možností:
    - **Výchozí ze zařízení**
    - **Biometrika s nízkým zabezpečením**
    - **Aspoň číslice**
    - **Číselné komplexní** – Opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.<sup>1</sup>
    - **Aspoň abecední znaky**
    - **Aspoň alfanumerické znaky**
    - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel** – Zabrání koncovému uživateli vytvořit dříve používané heslo.
- **Odemknutí pomocí otisků prstů (jenom Samsung KNOX)** – Povolí na zařízeních, která to podporují, odemknutí pomocí otisku prstu.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti** – Umožňuje řídit funkci Smart Lock na kompatibilních zařízeních s Androidem (Samsung KNOX Standard 5.0 a novější). Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné ji například použít, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.
- **Šifrování** – Vyžaduje, aby soubory v zařízení byly šifrované.

<sup>1</sup> Před přiřazením tohoto nastavení k zařízením zkontrolujte, jestli je aplikace Portál společnosti v daných zařízeních aktualizovaná na nejnovější verzi.

Pokud nakonfigurujete nastavení **Číselné komplexní** a potom ho přiřadíte k zařízení, které používá verzi Androidu starší než 5.0, bude platit následující chování.
- Pokud aplikace Portál společnosti používá verzi starší než 1704, nepoužijí se u zařízení žádné zásady PIN kódu a na portálu Intune se zobrazí chyba.
- Pokud aplikace Portál společnosti používá verzi 1704 nebo novější, je možné použít jenom jednoduchý PIN kód. Verze Androidu starší než 5.0 toto nastavení nepodporují. Na portálu Intune se nezobrazí žádná chyba.


## <a name="google-play-store"></a>Obchod Google Play

- **Obchod Google Play (jenom Samsung KNOX)** – Povolí uživateli přístup k obchodu Google Play na zařízení.

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

- **Webový prohlížeč (jenom Samsung KNOX)** – Určuje, jestli je možné používat výchozí webový prohlížeč zařízení.
- **Automatické vyplňování (jenom Samsung KNOX)** – Povolí používání funkce automatického vyplňování webového prohlížeče.
- **Soubory cookie (jenom Samsung KNOX)** – Povolí webovému prohlížeči v zařízení používat soubory cookie.
- **JavaScript (jenom Samsung KNOX)** – Povolí webovému prohlížeči v zařízení spouštět skripty Java.
- **Automaticky otevíraná okna (jenom Samsung KNOX)** – Povolí používání blokování automaticky otevíraných oken ve webovém prohlížeči.

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Zálohovací služba Google (jenom Samsung KNOX)** – Povolí použití zálohování Google.
- **Automatická synchronizace účtu Google (jenom Samsung KNOX)** – Povolí automatickou synchronizaci nastavení účtu Google.
- **Vyměnitelné úložiště (jenom Samsung KNOX)** – Povolí zařízení používat vyměnitelné úložiště, třeba SD kartu.
- **Šifrování na paměťových kartách (jenom Samsung KNOX)** – Určuje, jestli musí být paměťová karta zařízení šifrovaná.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Datový roaming (jenom Samsung KNOX)** – Povolí datový roaming, když je zařízení v mobilní síti.
- **Zprávy SMS a MMS (jenom Samsung KNOX)** – Povolí na zařízení používat zprávy SMS a MMS.
- **Hlasové vytáčení (jenom Samsung KNOX)** – Povolí nebo zakáže funkci hlasového vytáčení na zařízení.
- **Hlasový roaming (jenom Samsung KNOX)** – Povolí hlasový roaming, když je zařízení v mobilní síti.
- **Bluetooth (jenom Samsung KNOX)** – Povolí používání Bluetooth na zařízení.
- **NFC (jenom Samsung KNOX)** – Umožní operace, které na podporovaných zařízeních používají bezkontaktní komunikaci.
- **Wi-F (jenom Samsung KNOX)i** – Povolí použití možností Wi-Fi zařízení.
- **Wi-Fi tethering (jenom Samsung KNOX)** – Povolí sdílení mobilního internetového připojení (tethering) přes Wi-Fi na zařízení.

## <a name="kiosk"></a>Kiosk

Nastavení Kiosku se týká jenom zařízení se Samsung KNOX Standard.

- **Vyberte spravovanou aplikaci** – Pokud chcete přidat jednu nebo více aplikací, které se budou moct spustit, když je zařízení v beznabídkovém režimu, zvolte jednu z následujících možností. Žádné jiné aplikace se na zařízení nebudou moct spustit.
    - **Přidat aplikace pomocí názvu balíčku**
    - **Přidat aplikace pomocí adresy URL**
    - **Přidat spravované aplikace**
- **Tlačítko pro režim spánku obrazovky** – Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.
- **Tlačítka hlasitosti** – Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.
