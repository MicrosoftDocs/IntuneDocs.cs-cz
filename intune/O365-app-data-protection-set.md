---
title: "Nastavení základní správy dat v aplikacích Office 365 – Intune Azure Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Podpůrná dokumentace pro průvodce Správa aplikací Office 365"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 639d045e036ecdc6ff40d6ae335d2c5109d9e420
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---


# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps"></a>Jak vaši uživatelé budou moct používat základní ochranu ve spravovaných aplikacích Office 365

Průvodce **Správa aplikací Office 365** vytvoří zásady ochrany aplikací pro jednotlivé platformy zařízení.

Průvodce zapne tyto zásady:

**iOS**
* Zašifrovat data aplikací

**Android**
* Zašifrovat data aplikací
* Požadovat jednoduchý kód PIN pro přístup

Tyto zásady umožňují spravovat aplikace Office 365, takže v případě potřeby můžete z aplikací Office vymazat pracovní data. Pro případy, že vám někdo zařízení odcizí nebo ho ztratíte, navíc zajišťují základní ochranu šifrováním pracovních dat. K zobrazení dat v aplikacích Office 365 je nutné zadat PIN kód.


Jako příklad tento článek používá OneDrive pro firmy, pomocí kterého ukazuje možnosti uživatele v aplikaci spravované přes Intune.


>[!NOTE]
>Na osobním zařízení by běžně stahoval aplikaci koncový uživatel. Když se zařízení spravuje pomocí řešení správy mobilních zařízení (MDM), můžete aplikaci nasadit do zařízení.

## <a name="user-experience-on-an-ios-device"></a>Možnosti uživatele na zařízení s iOSem

1. Spuštěním aplikace OneDrive pro firmy otevřete přihlašovací stránku.  <br/> ![Snímek přihlašovací obrazovky OneDrivu pro iOS](./media/onedrive-ios-sign-in.png)
2. Zadejte uživatelské jméno pracovního účtu. Budete přesměrováni na ověřovací stránku Office 365, kde zadáte pracovní přihlašovací údaje. <br/> ![Snímek přihlašovací stránky Office 365](./media/o365-sign-in-ios.png)
3. Po úspěšném ověření přihlašovacích údajů službou Azure Active Directory se použijí zásady správy mobilních aplikací (MAM) a zobrazí se vám výzva restartovat aplikaci OneDrive pro firmy.  <br/>![Snímek výzvy na restartování pro iOS](./media/ios-restart-prompt.png)
>[!NOTE]
>Zpráva s informacemi o vyžadovaném restartování se zobrazí pouze na zařízeních, která nejsou zaregistrovaná v Intune.


4. Znovu spusťte aplikaci OneDrive pro firmy. Aplikace se spustí se zapnutými zásadami MAM a zobrazí se vám výzva k zadání PIN kódu pro zařízení (pokud na něm ještě PIN kód nastavený nemáte). <br/> ![Snímek výzvy k vytvoření PIN kódu](./media/pin-prompt-ios.png)

>[!NOTE]
>Většině vašich uživatelů se tato výzva nezobrazí. Uživatelům, kteří na svém zařízení s iOSem nemají nastavený PIN kód, se tato výzva zobrazí.


5. Jakmile PIN kód nastavíte a potvrdíte, vraťte se do aplikace OneDrive pro firmy. Zobrazí se vám jednorázová zpráva, že váš správce IT teď chrání pracovní data ve OneDrivu. <br/> ![Snímek jednorázového oznámení vašeho správce IT](./media/one-time-notice.png)
6. Abyste mohli přistupovat k souborům ve OneDrivu pro firmy, klikněte někam mimo toto oznámení. <br/> ![Snímek souborů OneDrivu na zařízení s iOSem](./media/onedrive-files-ios.png) <br/>

>[!NOTE]
>Při změně nasazených zásad se změny použijí při příštím otevření aplikace.


## <a name="user-experience-on-an-android-device"></a>Možnosti uživatele na zařízení s Androidem

1. Spuštěním aplikace OneDrive pro firmy otevřete přihlašovací stránku.  <br/> ![Snímek uvítací obrazovky aplikace OneDrive](./media/onedrive-android-welcome.png)
2. Zadejte uživatelské jméno pracovního účtu. Budete přesměrováni na ověřovací stránku Office 365, kde zadáte pracovní přihlašovací údaje. <br/> ![Snímek přihlášení O365 v Androidu](./media/o365-sign-in-android.png)
3. Pokud na zařízení ještě není nainstalovaná aplikace Portál společnosti, po úspěšném ověření přihlašovacích údajů službou Azure Active Directory se vám zobrazí zpráva s pokyny k její instalaci. Pokračujte klepnutím na **Přejít do obchodu**. <br/> ![Snímek zprávy o získání aplikace Portál společnosti](./media/get-company-portal-android.png) <br/>Pokud máte na svém telefonu aplikaci Portál společnosti nainstalovanou, aplikace OneDrive pro firmy se automaticky spustí a můžete přeskočit na poslední poznámku.
>[!IMPORTANT]
>Po nastavení aplikací Office tak, aby se spravovaly přes zásady MAM, **musí** uživatel zařízení s Androidem nainstalovat aplikaci Portál společnosti, aby mohl přistupovat k pracovním e-mailům a dokumentům, i když koncový uživatel pro samotné čtení e-mailů a dokumentů nemusí aplikaci otevírat a přihlašovat se k ní.

4. Teď jste v obchodě Google Play, kde si můžete stáhnout a nainstalovat aplikaci Portál společnosti. Tato aplikace vám pomůže uchovávat data v bezpečí. <br/> ![Snímek aplikace v obchodu Google Play](./media/google-play-get-app-android.png)
5. Po dokončení instalace aplikace přijměte podmínky zvolením **Přijmout**. Aplikace OneDrive pro firmy se automaticky spustí.


>[!NOTE]
>Pokud vaše oddělení IT vyžaduje PIN kód, při příštím otevření OneDrivu pro firmy se vám zobrazí výzva ho nastavit. Až PIN kód nastavíte a potvrdíte, budete moct pokračovat do OneDrivu pro firmy.

![Snímek výzvy zadat PIN kód](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a>Jaké zásady tento průvodce nastavuje?
|     |       | |
|----|--------|-|
|**Název**|Správa aplikací Office 365| |
| **Popis**|Vytvořené průvodcem Správa aplikací Office 365| |
| |  | |
| **Název nastavení** |**Hodnota zásad iOSu** | **Hodnota zásad Androidu** |
|Zakázat zálohování dat v iTunes a na iCloudu| Ne | Není k dispozici |
|Zakázat zálohování dat v zařízeních s Androidem |Není k dispozici | Ne|
|Povolit aplikaci přenos dat do ostatních aplikací | Všechny aplikace | Všechny aplikace|
|Povolit aplikaci, aby přijímala data z jiných aplikací| Všechny aplikace | Všechny aplikace|
|Zakázat možnost Uložit jako | Ne | Ne|
|Omezit operace vyjmutí, kopírování a vložení s jinými aplikacemi | Libovolná aplikace | Libovolná aplikace |
|Omezit zobrazování obsahu webu jenom na podnikový spravovaný prohlížeč | Ne| Ne|
|Zašifrovat data aplikací | Když je zařízení blokované | Ano|
|Zakázat synchronizaci kontaktů | Ne| Ne|
|Zakázat tisk | Ne | Ne|
|Vyžadovat pro přístup kód PIN | Ne | Ano|
|Počet pokusů o zadání před obnovení kódu PIN | Není k dispozici |5|
|Povolit jednoduchý PIN | Není k dispozici |Ano|
|Délka PIN kódu | Není k dispozici | 4|
|Povolit otisk prstu místo PIN kódu | Není k dispozici | Ano |
|Vyžadovat podnikové přihlašovací údaje pro přístup | Ne | Ne|
|Blokovat spuštění spravovaných aplikací v zařízení s jailbreakem nebo rootem | Ne | Ne|
|Znovu zkontrolovat požadavky na přístup po (minuty) – časový limit | 30 | 30|
|Znovu zkontrolovat požadavky na přístup po (minuty) – období odkladu pro offline režim | 720 |720|
|Doba v offline režimu (ve dnech) před vymazáním dat | 90 | 90|
|Blokovat snímání obrazovky (jenom zařízení s Androidem) | Není k dispozici | Ne |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a>Proč se zásady PIN kódu aplikace konfigurují jenom pro zařízení s Androidem?
Šifrování v iOSu a Androidu funguje rozdílně.

V iOSu se data aplikací přidružených k zásadám Intune MAM šifrují při nečinnosti pomocí šifrování na úrovni zařízení poskytovaného operačním systémem. Proto, když zapnete zásady šifrování aplikací, automaticky požadujete, aby uživatel měl a zadal pro přístup k pracovním datům PIN kód zařízení. Uživatelům, kteří na zařízení PIN kód nakonfigurovaný nemají, se zobrazí výzva vytvořit PIN kód zařízení.

V Androidu se data aplikací přidružených k zásadám Intune MAM šifrují synchronně během vstupně-výstupních úloh se soubory. Obsah v úložišti zařízení je zašifrovaný vždycky. Na zařízeních, která nejsou spravovaná pomocí MDM, zásady MAM nemůžou vynutit požadavek na PIN kód zařízení. Aby uživatelé museli pro přístup k pracovním datům použít PIN kód, průvodce povolí zásady PIN kódu aplikace.

Vždy můžete tato nastavení zásad upravit tak, aby odpovídala požadavkům vaší organizace.

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a>Jak můžu zobrazit a upravit zásady, které vytvořil průvodce?
Pokud chcete upravit tyto zásady nebo zásady vytvořené v Intune Azure Preview, zvolte na řídicím panelu **Spravovat aplikace** > **Zásady ochrany aplikací**. Vpravo se otevře seznam zásad. Zvolte zásadu, kterou si chcete zobrazit, a zobrazí se vám její nastavení, která můžete upravit. <br/>
![Snímek cesty uživatelského rozhraní pro zobrazení zásad](./media/image-for-faq.png)

## <a name="next-steps"></a>Další kroky
Další informace o [zásadách ochrany aplikací](https://docs.microsoft.comapp-protection-policy.md)

