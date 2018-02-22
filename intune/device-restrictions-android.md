---
title: "Nastavení omezení pro zařízení s Androidem v Intune"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Androidem."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c2ebbe451f83dc14a9294c78a21ecfd30e5d155
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení zařízení používajících Android a Samsung Knox Standard v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tato nastavení spolu se zásadami omezení pro zařízení s Androidem se používají ke konfiguraci zařízení v organizaci.

>[!TIP]
>Pokud požadovaná nastavení nejsou k dispozici, možná budete moct zařízení nakonfigurovat pomocí [vlastního profilu](custom-settings-android.md).

## <a name="general"></a>Obecné

- **Kamera** – Povolí použití fotoaparátu v zařízení.
- **Kopírování a vkládání (jenom Samsung Knox)** – povolí v zařízení funkce kopírování a vložení.
- **Sdílení přes schránku mezi aplikacemi (jenom Samsung Knox)** – povolí použití schránky ke kopírování a vložení obsahu mezi aplikacemi.
- **Odeslání diagnostických dat (jenom Samsung Knox)** – znemožní uživateli posílat ze zařízení diagnostická data.
- **Obnovení továrního nastavení (jenom Samsung Knox)** – povolí uživateli obnovit v zařízení tovární nastavení.
- **Zeměpisná poloha (jenom Samsung Knox)** – povolí zařízení využívat informace o poloze.
- **Vypnutí (jenom Samsung Knox)** – Povolí uživateli vypnout zařízení.<br>Pokud je tato možnost zakázaná, nepůjde nastavit ani možnost **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**.
- **Snímek obrazovky (jenom Samsung Knox)** – umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.
- **Hlasový asistent (jenom Samsung Knox)** – povolí v zařízení používat software hlasového asistenta.
- **YouTube (jenom Samsung Knox)** – povolí v zařízení používat aplikaci YouTube.
- **Sdílená zařízení (jenom Samsung Knox)** – umožňuje nakonfigurovat spravované zařízení se zabezpečením Samsung Knox Standard jako sdílené. V tomto režimu se koncoví uživatelé můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení zůstává spravované bez ohledu na to, jestli se používá.<br>Při použití ve spojení s profilem certifikátu SCEP umožňuje tato funkce koncovým uživatelům sdílet zařízení se stejnou skupinou aplikací pro všechny uživatele, ale s vlastním uživatelským certifikátem SCEP.  Po odhlášení uživatelů se všechna data aplikací vymažou.  Tato funkce je omezená jenom na obchodní aplikace.
- **Zablokovat změny data a času (Samsung Knox)** – zakáže uživateli v zařízení měnit nastavení data a času. 

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
- **Odemykání otiskem prstu (jenom Samsung Knox)** – povolí odemykání podporovaných zařízení otiskem prstu.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti** – na kompatibilních zařízeních s Androidem (Samsung Knox Standard 5.0 a novější) umožňuje ovládat funkci Smart Lock. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné ji například použít, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.
- **Šifrování** – Vyžaduje, aby soubory v zařízení byly šifrované.

<sup>1</sup> Před přiřazením tohoto nastavení k zařízením zkontrolujte, jestli je aplikace Portál společnosti v daných zařízeních aktualizovaná na nejnovější verzi.

Pokud nakonfigurujete nastavení **Číselné komplexní** a potom ho přiřadíte k zařízení, které používá verzi Androidu starší než 5.0, bude platit následující chování.
- Pokud má aplikace Portál společnosti verzi starší než 1704, nepoužijí se u zařízení žádné zásady PIN kódu a na portálu Azure Portal se zobrazí chybová zpráva.
- Pokud aplikace Portál společnosti používá verzi 1704 nebo novější, je možné použít jenom jednoduchý PIN kód. Verze Androidu starší než 5.0 toto nastavení nepodporují. Na portálu Azure Portal se nezobrazí žádná chybová zpráva.


## <a name="google-play-store"></a>Obchod Google Play

- **Obchod Google Play (jenom Samsung Knox)** – umožní uživateli zařízení přístup do obchodu Google Play.

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete pro zařízení s Androidem a zabezpečením Samsung Knox Standard nakonfigurovat některý z následujících seznamů:

Seznam **Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných přes Intune), které budou nahlášeny, pokud je uživatelé nainstalují a spustí.
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

- **Webový prohlížeč (jenom Samsung Know)** – určuje, jestli je možné používat výchozí webový prohlížeč zařízení.
- **Automatické vyplňování (jenom Samsung Knox)** – povolí používání funkce automatického vyplňování ve webovém prohlížeči.
- **Soubory cookie (jenom Samsung Knox)** – povolí webovému prohlížeči v zařízení používat soubory cookie.
- **JavaScript (jenom Samsung Knox)** – povolí webovému prohlížeči v zařízení spouštět skripty Java.
- **Automaticky otevíraná okna (jenom Samsung Knox)** – povolí ve webovém prohlížeči blokování automaticky otevíraných oken.

## <a name="allow-or-block-apps"></a>Povolení nebo blokování aplikací

Tato nastavení můžete použít k určení aplikací instalovatelných nebo spustitelných jenom na zařízeních se spuštěným zabezpečením Samsung Knox Standard.
Navíc můžete také určit nainstalované aplikace, které budou uživateli zařízení skryty. Uživatelé tyto aplikace nemůžou spouštět.

- **Aplikace, které je možné nainstalovat (pouze Samsung Knox Standard)**
- **Aplikace, jejichž spouštění je blokováno (pouze Samsung Knox Standard)**
- **Aplikace, které jsou před uživatelem skryty (pouze Samsung Knox Standard)**

Pro každé nastavení nakonfigurujte pomocí jedné z následujících možností seznam aplikací:

- **Přidat aplikace pomocí názvu balíčku** – primárně slouží pro obchodní aplikace. Zadejte název aplikace a název balíčku aplikace.
- **Přidat aplikace pomocí adresy URL** – zadejte název aplikace a její adresu URL v obchodě Google Play.
- **Přidat spravované aplikace** – v seznamu aplikací spravovaných přes Intune vyberte požadovanou aplikaci.

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Zálohovací služba Google (jenom Samsung Knox)** – povolí použití zálohování Google.
- **Automatická synchronizace účtu Google (jenom Samsung Knox)** – povolí automatickou synchronizaci nastavení účtu Google.
- **Vyměnitelné úložiště (jenom Samsung Knox)** – povolí zařízení používat vyměnitelné úložiště, třeba SD kartu.
- **Šifrování na paměťových kartách (jenom Samsung Knox)** – určuje, jestli má být paměťová karta zařízení šifrovaná.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Datový roaming (jenom Samsung Knox)** – povolí datový roaming, pokud je zařízení v mobilní síti.
- **Zprávy SMS a MMS (jenom Samsung Knox)** – povolí na zařízení používat zprávy SMS a MMS.
- **Hlasové vytáčení (jenom Samsung Knox)** – povolí nebo zakáže v zařízení funkci hlasového vytáčení.
- **Hlasový roaming (jenom Samsung KNOX)** – povolí hlasový roaming, když je zařízení v mobilní síti.
- **Bluetooth (jenom Samsung KNOX)** – povolí zařízení používat Bluetooth.
- **NFC (jenom Samsung Knox)** – umožní operace, které na podporovaných zařízeních používají bezkontaktní komunikaci.
- **Wi-F (jenom Samsung KNOX)i** – povolí na zařízení používat možnosti Wi-Fi.
- **Wi-Fi tethering (jenom Samsung Knox)** – povolí v zařízení používat Wi-Fi tethering (sdílené internetové připojení přes Wi-Fi).

## <a name="kiosk"></a>Kiosk

Nastavení platí jen pro zařízení se zabezpečením Samsung Knox Standard a jen pro aplikace, které spravujete přes Intune.

- **Vyberte spravovanou aplikaci** – Pokud chcete přidat spravované aplikace, které poběží, když je zařízení v režimu Kiosk, zvolte jednu z následujících možností. Žádné jiné aplikace se na zařízení nebudou moct spustit.
    - **Přidat aplikace pomocí názvu balíčku**
    - **Přidat aplikace pomocí adresy URL**
    - **Přidat spravované aplikace**
- **Tlačítko pro režim spánku obrazovky** – Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.
- **Tlačítka hlasitosti** – Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.


## <a name="next-steps"></a>Další kroky

Pokračujte tím, že podle pokynů v části popisující [postup konfigurace nastavení omezení zařízení](device-restrictions-configure.md) vytvoříte a pak přiřadíte profil omezení zařízení.
