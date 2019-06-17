---
title: Nastavení omezení zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení zařízení s Androidem, které můžete v Microsoft Intune ovládat nebo omezit. Tato nastavení můžete použít k ovládání hesla, přístupu ke Google Play, povolení nebo zakázání aplikací, ovládání nastavení prohlížeče, blokování aplikací, zálohování do cloudu Google, ovládání zpráv, hlasového volání, datového roamingu a možností připojení k Wi-Fi nebo prostřednictvím technologie Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f13b78e05b9f0b94d98677004c7059f1acaa80f9
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045722"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Android a Samsung Knox Standard seznamy nastavení omezení zařízení v Intune

Tento článek ukazuje všechna nastavení omezení zařízení v Microsoft Intune, která můžete nakonfigurovat pro zařízení s Androidem.

>[!TIP]
>Pokud požadovaná nastavení nejsou k dispozici, možná budete moct zařízení nakonfigurovat pomocí [vlastního profilu](custom-settings-android.md).

## <a name="general"></a>Obecné

- **Camera**: Zvolte **bloku** zabránit přístupu k fotoaparátu. **Není nakonfigurováno** umožňuje přístup k fotoaparátu zařízení.
- **Kopírování a vkládání (jenom Samsung Knox)**: Zvolte **bloku** zabránit kopírování a vkládání. **Není nakonfigurováno** povolí v zařízení funkce kopírování a vkládání.
- **Sdílení přes schránku mezi aplikacemi (jenom Samsung Knox)**: Zvolte **bloku** k zabránění použití clipboardu pro kopírování a vkládání mezi aplikacemi. **Není nakonfigurováno** umožňuje použití clipboardu pro kopírování a vkládání mezi aplikacemi.
- **Odeslání diagnostických dat (jenom Samsung Knox)**: Zvolte **bloku** zastavit uživateli v odesílání diagnostických dat ze zařízení. **Není nakonfigurováno** umožňuje uživatelům odesílat data.
- **Vymazat (jenom Samsung Knox)**: Umožňuje uživateli spustit [vymazání](devices-wipe.md) akcí na zařízení.
- **Informace o zeměpisné poloze (jenom Samsung Knox)**: Zvolte **bloku** zakázat zařízení používat informace o poloze. **Není nakonfigurováno** umožňuje zařízení využívat informace o poloze.
- **Vypnutí (jenom Samsung Knox)**: Zvolte **bloku** zabránit uživateli ve vypnutí zařízení. Pokud je toto nastavení zakázáno, **počet neúspěšných přihlášení před vymazáním obsahu zařízení** nastavení nelze nastavit a nebude fungovat. **Není nakonfigurováno** povolí uživateli vypnout zařízení.
- **Snímek obrazovky (jenom Samsung Knox)**: Zvolte **bloku** zabránit snímky obrazovky. **Není nakonfigurováno** umožňuje uživateli zachytit obsah obrazovky jako obrázek.
- **Hlasový asistent (jenom Samsung Knox)**: Zvolte **bloku** zakázat službu S hlasu. **Není nakonfigurováno** dovoluje S hlasových služeb a aplikací na zařízení. Toto nastavení neplatí pro Bixby nebo hlasového Pomocníka pro usnadnění přístupu, které předčítá obsahu obrazovky.
- **YouTube (jenom Samsung Knox)**: Zvolte **bloku** uživatelům zabránit v používání aplikace YouTube. **Není nakonfigurováno** umožňuje použití aplikace YouTube na zařízení.
- **Sdílená zařízení (jenom Samsung Knox)**: Nakonfigurujte spravované zařízení Samsung Knox Standard jako sdílené. Pokud je nastavena na **povolit**, koncoví uživatelé můžou přihlásit do zařízení pomocí svých přihlašovacích údajů Azure AD. Zařízení zůstává spravované, ať už používá nebo není.</br>Při použití pomocí profilu certifikátu SCEP, tato funkce umožňuje koncovým uživatelům sdílet zařízení pomocí stejného aplikací pro všechny uživatele. Ale každý uživatel má své vlastní uživatelský certifikát SCEP. Po odhlášení uživatelů se všechna data aplikací vymažou. Tato funkce je omezená jenom na obchodní aplikace. </br>**Není nakonfigurováno** více koncovým uživatelům zabrání v přihlašování k aplikaci portál společnosti na zařízení pomocí svých přihlašovacích údajů Azure AD.
- **Zablokovat změny data a času (Samsung Knox)**: Zvolte **bloku** uživateli zabránit ve změně data a času nastavení na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit datum a čas nastavení.

## <a name="password"></a>Heslo

- **Heslo**: **Vyžadovat** koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** umožňuje uživatelům přístup k zařízení bez zadávání hesla.

    > [!NOTE]
    > Při registraci MDM zařízení Samsung Knox automaticky vyžadují 4místný číselný kód PIN. Nativní zařízení s Androidem můžou automaticky vyžadovat PIN kód kompatibilní s podmíněným přístupem.

- **Minimální délka hesla**: Zadejte minimální délku hesla, které uživatel musí zadat (mezi 4 a 16 znaky).
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Zadejte maximální počet minut nečinnosti, které jsou povoleny v zařízení po kterém se zamkne obrazovka. Koncový uživatel nemůže na zařízení nastavit větší časovou hodnotu, než je nakonfigurovaná v profilu. Může ale nastavit kratší časovou hodnotu. Pokud je v profilu nastaveno třeba 15 minut, může koncový uživatel nastavit 5 minut, ale nemůže nastavit 30 minut. 
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Zadejte počet neúspěšných přihlášení povolit předtím, než se zařízení vymaže.
- **Vypršení platnosti hesla (dny)**: Zadejte počet dní, než se musí změnit heslo zařízení.
- **Vyžadovaný typ hesla**: Zadejte požadovanou úroveň složitosti hesla a to, jestli můžou používat biometrická zařízení. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číslice**
  - **Číselné komplexní**: Opakovat nebo po sobě jdoucí čísla, jako je například "1111" nebo "1234" nejsou povoleny. <sup>1</sup>
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Zakázat opakované použití předchozích hesel**: Zakáže koncovému uživateli ve vytváření hesel, kterou jste použili dříve.
- **Odemknutí pomocí otisků prstů (jenom Samsung Knox)**: Zvolte **bloku** zabránit k odemknutí zařízení otiskem prstu. **Není nakonfigurováno** uživatel k odemknutí zařízení otiskem prstu.
- **Smart Lock a jiné agenty pro určování důvěryhodnosti**: Zvolte **bloku** zabránit Smart Lock a jiné agenty pro určování důvěryhodnosti úpravy nastavení zamykací obrazovky (Standard Samsung KNOX 5.0 +). Tato funkce Telefon, někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Tuto funkci například můžete použít, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.
- **Šifrování**: Zvolte **vyžadují** tak, aby soubory v zařízení byly šifrované. Šifrování nepodporují všechna zařízení. Tato funkce také použití: 
  1. Nastavte **heslo** k **vyžadují**.
  2. Nastavte **požadovaný typ hesla** k **na úrovni aspoň číslice**.
  3. Nastavte **minimální délka hesla** aspoň 4 správně hlásilo pro toto nastavení.

  > [!NOTE]
  > Pokud se vynucují zásady šifrování, zařízení Samsung Knox po uživatelích vyžadují nastavení šestiznakového složitého hesla jako hesla k zařízení.

<sup>1</sup> před přiřazením tohoto nastavení na zařízení, nezapomeňte aktualizovat aplikaci portál společnosti na nejnovější verzi na těchto zařízeních.

Pokud nastavíte **požadovaný typ hesla** k **číselné komplexní**a pak ji přiřaďte zařízení se systémem Android verze starší než 5.0, pak platí následující chování:

- Pokud aplikace portál společnosti používá verzi starší než 1704, je u zařízení žádné zásady PIN kódu a chyba se zobrazí na webu Azure Portal.
- Pokud aplikace Portál společnosti používá verzi 1704 nebo novější, je možné použít jenom jednoduchý PIN kód. Verze Androidu starší než 5.0 nepodporují toto nastavení. Žádná chybová zpráva se zobrazí na webu Azure Portal.

## <a name="google-play-store"></a>Obchod Google Play

- **Obchod Google Play (jenom Samsung Knox)**: Zvolte **bloku** uživatelům zabránit v používání obchodu Google Play. **Není nakonfigurováno** umožňuje uživatelům přístup do obchodu Google Play na zařízení.

## <a name="restricted-apps"></a>Omezené aplikace

Pomocí těchto nastavení můžete povolit nebo zakázat konkrétní aplikace na zařízení. Tato funkce je podporovaná v zařízeních s Androidem a Samsung Knox Standard:

- **Zakázané aplikace**: Seznam aplikací, které nejsou spravované přes Intune, které nechcete, aby na zařízení nainstalovaná. Pokud uživatel aplikaci nainstaluje z tohoto seznamu, budete upozorněni prostřednictvím Intune.
- **Schválené aplikace**: Seznam aplikací, které uživatelé smějí instalovat. Chcete-li i nadále, nesmí uživatelé instalovat jiné aplikace. Aplikace, které spravuje Intune, jsou povolené automaticky.

Chcete-li přidat aplikaci do těchto seznamů, můžete:

- **Přidat** Google Play Store adresu URL aplikaci, kterou chcete. Například pokud chcete přidat aplikaci Microsoft Remote Desktop pro Android, zadejte `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android`. Chcete-li vyhledat adresu URL aplikace, otevřete [obchodu Google Play](https://play.google.com/store/apps)a vyhledejte aplikaci. Například vyhledejte `Microsoft Remote Desktop Play Store` nebo `Microsoft Planner`. Vyberte aplikaci a zkopírujte adresu URL.
- Importujte soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použít <*adresa url aplikace*>, <*název aplikace*>, <*vydavatele aplikace*> formátu. Nebo, **exportovat** existujícího seznamu, který obsahuje seznam aplikací s omezeným přístupem ve stejném formátu.

> [!IMPORTANT]
> Profily zařízení, které používají nastavení aplikace s omezeným přístupem musí přiřadit skupinám uživatelů.

## <a name="browser"></a>Prohlížeč

- **Webový prohlížeč (jenom Samsung Knox)**: Zvolte **bloku** zabránit se na zařízení používat výchozí webový prohlížeč. **Není nakonfigurováno** povolí webovému prohlížeči v zařízení výchozí se použije.
- **Automatické vyplňování (jenom Samsung Knox)**: Zvolte **bloku** zabránit automatické vyplňování textu v prohlížeči. **Není nakonfigurováno** umožňuje používání funkce automatického vyplňování webového prohlížeče, který se má použít.
- **Soubory cookie (jenom Samsung Knox)**: Zvolte, jak chcete zpracovávat soubory cookie z webů na zařízení. Možnosti:
  - Povolit
  - Blokovat všechny soubory cookie
  - Povolit soubory cookie z navštívených webů
  - Povolit soubory cookie z aktuálního webu
- **JavaScript (jenom Samsung Knox)**: Zvolte **bloku** zabránit v prohlížeči spouštění skriptů Java. **Není nakonfigurováno** povolí webovému prohlížeči v zařízení spouštět skripty Java.
- **Automaticky otevíraná okna (jenom Samsung Knox)**: Zvolte **bloku** zabránit automaticky otevíraných oken ve webovém prohlížeči. **Není nakonfigurováno** umožňuje automaticky otevíraných oken ve webovém prohlížeči.

## <a name="allow-or-block-apps"></a>Povolení nebo blokování aplikací

Pomocí těchto nastavení můžete povolit, můžete blokovat nebo skrýt konkrétní aplikace na zařízeních Samsung Knox Standard. Aplikace, které jsou skryté nelze otevřít nebo spuštění uživatelem.

Možnosti:

- **Aplikace, které je možné nainstalovat (pouze Samsung Knox Standard)**
- **Aplikace, jejichž spouštění je blokováno (pouze Samsung Knox Standard)**
- **Aplikace, které jsou před uživatelem skryty (pouze Samsung Knox Standard)**

Ke každému nastavení, přidejte seznamu aplikací. Možnosti:

- **Přidat aplikace pomocí názvu balíčku**: Používá se především pro řádek obchodní aplikace. Zadejte název aplikace a název balíčku aplikace.
- **Přidat aplikace pomocí adresy URL**: Zadejte název aplikace a její adresu URL v obchodu Google Play.
- **Přidat aplikace pro store**: Vyberte aplikaci ze seznamu existujících aplikací, které spravujete v Intune.

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Zálohovací Služba Google (jenom Samsung Knox)**: Zvolte **bloku** zabránit zařízení synchronizují do zálohy na Googlu. **Není nakonfigurováno** povoluje použití zálohování Google.
- **Automatická synchronizace účtu Google (jenom Samsung Knox)**: Zvolte **bloku** aby funkce Google účet automatické synchronizace v zařízení. **Není nakonfigurováno** umožňuje automatickou synchronizaci nastavení účtu Google.
- **Vyměnitelné úložiště (jenom Samsung Knox)**: Zvolte **bloku** zabránit zařízení používat Vyměnitelné úložiště. **Není nakonfigurováno** povolí zařízení používat Vyměnitelné úložiště, třeba SD karty.
- **Šifrování na paměťových kartách (jenom Samsung Knox)**: **Vyžadovat** vynutí, že paměťové karty musí být zašifrován. **Není nakonfigurováno** umožňuje nešifrované paměťové karty, který se má použít. Ne všechna zařízení podporují šifrování paměťové karty. Pokud chcete potvrdit, obraťte se na výrobce zařízení.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Datový roaming (jenom Samsung Knox)**: Zvolte **bloku** zabránit datový roaming přes mobilní síť. **Není nakonfigurováno** povolí datový roaming, když je zařízení v mobilní síti.
- **SMS a MMS zprávy (jenom Samsung Knox)**: Zvolte **bloku** zabránit textové zprávy na zařízení. **Není nakonfigurováno** umožňuje používat zprávy SMS a MMS zprávy na zařízení.
- **Hlasové vytáčení (jenom Samsung Knox)**: Zvolte **bloku** k zabrání uživatelům využívat funkci hlasového vytáčení na zařízení. **Není nakonfigurováno** umožňuje hlasového vytáčení na zařízení.
- **Hlasový roaming (jenom Samsung Knox)**: Zvolte **bloku** zabránit hlasový roaming přes mobilní síť. **Není nakonfigurováno** povolí hlasový roaming, když je zařízení v mobilní síti.
- **Bluetooth (jenom Samsung Knox)**: Zvolte **bloku** zabránit používání Bluetooth na zařízení. **Není nakonfigurováno** povolí používání Bluetooth na zařízení.
- **NFC (jenom Samsung Knox)**: Zvolte **bloku** zastavit technologie téměř Field Communication (NFC). **Není nakonfigurováno** umožní operace, které používají bezkontaktní komunikaci na podporovaných zařízeních.
- **Wi-Fi (jenom Samsung Knox)**: Zvolte **bloku** zabránit pomocí sítě Wi-Fi na zařízení. **Není nakonfigurováno** umožňuje používat funkce sítě Wi-Fi zařízení.
- **Wi-Fi tethering (jenom Samsung Knox)**: Zvolte **bloku** k zabránění použití sdíleného internetového připojení přes Wi-Fi na zařízení. **Není nakonfigurováno** povolí použití sdíleného internetového připojení přes Wi-Fi na zařízení.

## <a name="kiosk"></a>Kiosk

Nastavení platí jen pro zařízení se zabezpečením Samsung Knox Standard a jen pro aplikace, které spravujete přes Intune.

- Přidání aplikací, které chcete spustit, když je zařízení v celoobrazovkovém režimu. V beznabídkovém režimu spouštět pouze aplikace, které přidáte; Při spuštění aplikace nebyla přidána. Předinstalované prohlížeče nespouštět jako aplikace, když je zařízení v celoobrazovkovém režimu. Pokud se vyžaduje prohlížeč, zvažte použití řešení [Managed Browser](app-configuration-managed-browser.md).

  Možnosti aplikace:

  - **Přidat aplikace pomocí názvu balíčku**: Používá se především pro řádek obchodní aplikace. Zadejte název aplikace a název balíčku aplikace.
  - **Přidat aplikace pomocí adresy URL**: Zadejte název aplikace a její adresu URL v obchodu Google Play.
  - **Přidat aplikace pro store**: Vyberte aplikaci ze seznamu existujících aplikací, které spravujete v Intune.

- **Tlačítko režimu spánku obrazovky**: Zvolte **bloku** zakázat nebo skrýt tlačítko Přejít do režimu spánku obrazovky. **Není nakonfigurováno** povolí na zařízení tlačítko probuzení z režimu spánku obrazovky.
- **Tlačítka pro hlasitost**: Zvolte **bloku** uživateli zabránit v nastavení hlasitosti zakázáním tlačítka hlasitosti. **Není nakonfigurováno** umožňuje použití tlačítek hlasitosti na zařízení.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily beznabídkového režimu pro [Androidu Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) a [Windows 10](kiosk-settings.md) zařízení.
