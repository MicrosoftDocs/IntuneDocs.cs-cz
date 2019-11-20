---
title: Konfigurace aplikace Portál společnosti
titleSuffix: Microsoft Intune
description: Learn how you can apply company-specific branding to the Intune Company Portal app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b750c09207b1950aa27a5f2cae1267503537b6e7
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199201"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Konfigurace aplikace Portál společnosti služby Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Portál společnosti v Microsoft Intune je místo, odkud mají uživatelé přístup k firemním datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu. Additionally, the company portal app allows user to securely access company resources. The company portal app provides several different pages, such as Home, Apps, App details, Devices, and Device details. To quickly find apps within the Company Portal, you can filter the apps on the Apps page.

> [!IMPORTANT]
> To support Google’s Firebase Cloud Messaging (FCM), you must update your Android Company Portal app to the latest version.  

> [!Tip]
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti. Note that users must have an Intune license assigned to access the Company Portal website.

By customizing the Company Portal, you will help provide a familiar and helpful experience for your end users. To do this, in the Intune portal, select **Client apps** > **Branding and customization**, and then configure the required settings.

When a user is installing an iOS application from the Company Portal they will receive a prompt. This occurs when the iOS app is linked to the app store, linked to a volume-purchase program (VPP), or linked to a line-of-business (LOB) app. The prompt allows the users to accept the action or allow management of the app. The prompt will display your company name, or when your company name is unavailable, **Company Portal** will be displayed. 

> [!Note]
> Pokud používáte Azure Government, nabízí se protokoly aplikace koncovým uživatelům, aby se rozhodli o způsobu sdílení po inicializaci procesu získání pomoci s problémem. Pokud ale Azure Government nepoužíváte, Portál společnosti pro Windows 10 bude odesílat protokoly aplikace přímo Microsoftu, když uživatel iniciuje proces pro získání pomoci s problémem. Odesílání protokolů aplikace do Microsoftu usnadní řešení problémů. 

## <a name="company-information-and-privacy-statement"></a>Informace o společnosti a prohlášení o zásadách ochrany osobních údajů
Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.

| Název pole | Maximální délka | Další informace |
|---|---|---|
|**Název společnosti**| 40 | Tento název se zobrazí v záhlaví okna Portálu společnosti a bude se zobrazovat jako text během činnosti koncového uživatele Intune. |
| **Adresa URL prohlášení o zásadách ochrany osobních údajů** |     79     | Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Musíte zadat platnou adresu URL ve formátu `<https://www.contoso.com>`. |

> [!NOTE]
> Consistent with Microsoft and Apple policy, we do not sell any data collected by our service to any third parties for any reason.

## <a name="support-information"></a>Informace o podpoře
Enter your company's support information to provide your employee with a contact for Intune-related questions.

|Název pole|Maximální délka|Další informace|
|---|---|---|
|**Jméno kontaktu** | 40 | This name is displayed on the **Help and Support** page. |
|**Telefonní číslo** | 20 | This contact number is displayed on the **Help and Support** page to enable employees to contact you for support. |
|**E-mailová adresa**| 40 | This contact address is displayed on the **Help and Support** page. Je potřeba zadat platnou e-mailovou adresu ve formátu `alias@domainname.com`. |
|**Název webu**| 40 | Toto je popisný název, který se zobrazí pro adresu URL webu podpory. If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Help and Support** page in the Company Portal. |
|**Adresa URL webu**| 150 | Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu `https://www.contoso.com`. If you don't specify a URL, nothing is displayed for the support website on the **Help and Support** page in the Company Portal. |
| **Další informace**| 120 | Displayed on the **Help and Support** page. |


## <a name="company-identity-branding-customization"></a>Přizpůsobení brandingu firemní identity
Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.

### <a name="theme-color-and-logo-in-the-company-portal"></a>Barva motivu a logo na Portálu společnosti
Přiřaďte barvu motivu pro Portál společnosti. Vyberte standardní barvu nebo zadejte šestimístný šestnáctkový kód pro vlastní barvu.

|Název pole|Další informace|
|---|---|
|**Vyberte standardní barvu, nebo zadejte šestičíselný šestnáctkový kód**| Choose **Standard** to visually select a color. Zvolte **Vlastní**, pokud chcete vybrat konkrétní barvu podle hodnoty šestnáctkového kódu.|
|**Zvolit barvu motivu**| Vyberte barvu motivu, kterou chcete použít pro Portál společnosti. Můžete ji vybrat ze standardní barvy nebo zadat konkrétní šestnáctkový kód. |
|**Zobrazení**| Vyberte, zda chcete zobrazit **Logo a název firmy**, **Jen logo firmy** nebo **Jen název firmy**. |
|**Nahrát firemní logo**|Tato možnost vám umožní nahrát vlastní firemní logo, které se bude zobrazovat na Portálu společnosti. Všimněte si, že barva textu se automaticky zvolí tak, aby byl zajištěn nejvyšší kontrast. Pokud chcete dosáhnout nejlepšího vzhledu, nahrajte logo s transparentním pozadím.<p><ul><li>Maximální velikost obrázku: 400 px × 400 px</li><li>Maximální velikost souboru: 750 kB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

Po nahrání loga se v oblasti náhledu zobrazí logo s barvou motivu. Pokud jste si zvolili zobrazení názvu firmy, zobrazí se název na Portálu společnosti v černé nebo bílé barvě. Barva se zvolí automaticky tak, aby byl zajištěn nejvyšší kontrast s ohledem na barvu motivu. V oblasti náhledu na obrazovce se název vaší firmy nezobrazí. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logo, které se použije na bílých nebo světlých pozadích
Zvolte logo, které bude nejlépe vypadat na bílých nebo světlých pozadích.

|Název pole|Další informace|
|---|---|
|**Nahrát logo**| Tato možnost je dostupná, pokud jste zvolili zobrazení loga společnosti. Pokud chcete dosáhnout nejlepšího vzhledu, nahrajte logo s transparentním pozadím.<p><ul><li>Maximální velikost obrázku: 400 px × 400 px</li><li>Maximální velikost souboru: 750 kB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Firemní logo pro Portál společnosti

Zobrazte si firemní logo, které odráží značku vaší společnosti. Po uložení změn můžete v horní části okna zvolit možnost **Podívejte se na náhled nastavení** na webovém portálu Intune, abyste viděli, jak budou konfigurace vypadat. Všimněte si, že náhled firemního loga uvidíte jenom na zařízení s iOSem, ale ne na webovém portálu Intune. 

|Název pole|Další informace|
|---|---|
|**Nahrát firemní logo**| This option allows you to display a brand image. On the iOS Company Portal, it shows as a background image on the user's profile page.<p><ul><li>Recommended image width: Greater than 1125px (required to be at least 650 px)</li><li>Maximální velikost obrázku: 1,3 MB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

Správné firemní logo může zvýšit důvěru uživatelů v aplikaci Portál společnosti tím, že prezentuje silný smysl pro vaši firemní značku. Nabízíme vám několik tipů, nad kterými byste se mohli zamyslet při pořizování, výběru a optimalizaci loga pro Portál společnosti. 

- Obraťte se na marketingové nebo kreativní oddělení. They may already have an approved set of brand images. Mohli by vám také pomoci při optimalizaci obrázků. 

- Zvažte kompozici v orientaci jak na šířku, tak i na výšku. Ústřední bod obrázku by mělo obklopovat dostatečně velké pozadí. The image may be cropped differently based on device size, orientation, and platform. 

- Nepoužívejte obecné obrázky převzaté z fotobanky. Obrázek by měl odrážet vaši firemní značku a měl by být pro uživatele srozumitelný. Pokud žádný obrázek nemáte, je lepší nepoužívat žádný, než použít obecný, který pro uživatele nemá žádný význam. 

- Odeberte nepotřebná metadata. Soubor obrázku může obsahovat metadata, jako jsou profil fotoaparátu, zeměpisná poloha, název, popisek a další. Pomocí nástroje pro optimalizaci obrázků tyto informace odstraňte, abyste zachovali kvalitu, ale vešli se do velikostního limitu souboru. 

After a brand image is added or changed in Intune, the end user may not see the change on iOS devices until the Company Portal has recognized the change on start up, and then has been restarted to display the brand image. 

### <a name="brand-image-examples"></a>Brand image examples

The following image shows an example iPad branding image:

![Screenshot of example iPhone branding image](./media/company-portal-app/company-portal-app-03.png)

The following image shows an example iPhone branding image:

![Screenshot of example iPad branding image](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Privacy statement customization

You can customize the privacy statement that appears for your organization on managed iOS devices. This message lists the items that your organization can't see or do on managed iOS devices.

Under **Company Portal customization** > **Device management and privacy message**, you can:

- Accept the **Default** to use the list as shown, or
- Choose **Custom** to customize the the list of items that your organization can’t see or do on managed iOS devices. You can use [markdown](https://daringfireball.net/projects/markdown/) to add bullets, bolding, italics, and links.

## <a name="company-portal-derived-credentials-for-ios-devices"></a>Company Portal derived credentials for iOS devices
Intune supports Personal Identity Verification (PIV) and Common Access Card (CAC) Derived Credentials in partnership with credential providers DISA Purebred, Entrust Datacard, and Intercede. End users will go through additional steps post-enrollment of their iOS device to verify their identity in the Company Portal application. Derived Credentials will be enabled for users by first setting up a credential provider for your tenant, then targeting a profile that uses Derived Credentials to users or devices.

> [!NOTE]
> The user will see instructions about derived credentials based on the link that you have specified via Intune.

For more information about derived credentials for iOS devices, see [Use derived credentials in Microsoft Intune](~/protect/derived-credentials.md).

## <a name="dark-mode-for-ios-company-portal"></a>Dark Mode for iOS Company Portal

Dark Mode is available for the iOS Company Portal. Users can download company apps, manage their devices, and get IT support in the color scheme of their choice based on device settings. The iOS Company Portal will automatically match the end user's device settings for dark or light mode. 

## <a name="windows-company-portal-keyboard-shortcuts"></a>Klávesové zkratky v Portálu společnosti pro Windows

End users can trigger navigation, app, and device actions in the Windows Company Portal using keyboard shortcuts (accelerators).

V aplikaci Portál společnosti pro Windows jsou k dispozici následující klávesové zkratky.

| Oblast | Description | Keyboard shortcut |
|:------------------:|:--------------:|:-----------------:|
| Navigační nabídka | Navigation | Alt+M |
|  | Domů | Alt+H |
|  | Všechny aplikace | Alt+A |
|  | Nainstalované aplikace | Alt+I |
|  | Váš názor | Alt+F |
|  | Můj profil | Alt+U |
|  | Nastavení | Alt+T |
| Úvodní stránka – dlaždice Zařízení | Přejmenovat | F2 |
|  | Odebrat | Ctrl+D nebo Delete |
|  | Zkontrolovat přístup | Ctrl+M nebo F9 |
| Podrobnosti o zařízení | Přejmenovat | F2 |
|  | Odebrat | Ctrl+D nebo Delete |
|  | Zkontrolovat přístup | Ctrl+M nebo F9 |
| Podrobnosti aplikace | Install | Ctrl+I |
| Zařízení | K dispozici | Ctrl+D |

End users will also be able to see the available shortcuts in the Windows Company Portal app.

![Screenshot of the available shortcuts in the Windows Company Portal](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>User self-service device actions from the Company Portal

Users can perform actions on their local or remote devices via the Company Portal app or Website. The actions that a user can perform varies based on device platform and configuration. In all cases, the remote device actions can only be performed by device’s Primary User.
- **Retire** – Removes the device from Intune Management. In the company portal app and website, this shows as **Remove**.
- **Wipe** – This action initiates a device reset. In the company portal website this is shown as **Reset**, or **Factory Reset** in the iOS Company Portal App.
- **Rename** – This action changes the device name that the user can see in the Company Portal. It does not change the local device name, only the listing in the Company Portal.
- **Sync** – This action initiates a device check-in with the Intune service. This shows as **Check Status** in the Company Portal.
- **Remote Lock** – This locks the device, requiring a PIN to unlock it.
- **Reset Passcode** – This action is used to reset device passcode. On iOS devices the passcode will be removed and the end user will be required to enter a new code in settings. On supported Android devices, a new passcode is generated by Intune and temporarily displayed in the Company Portal.
- **Key Recovery** – This action is used to recover a personal recovery key for encrypted macOS devices from the Company Portal website. 

### <a name="self-service-actions"></a>Self Service Actions

Some platforms and configurations do not allow self-service device actions. This table below provides further details about self service actions:

|  | Windows 10<sup>(3)</sup> | iOS/iPadOS<sup>(3)</sup> | MacOS<sup>(3)</sup> | Android<sup>(3)</sup> |
|----------------------|--------------------------|-------------------|-----------------------------------|-------------------------|
| Vyřazení | Available<sup>(1)</sup> | K dispozici | K dispozici | Available<sup>(7)</sup> |
| Vymazání | K dispozici | Available<sup>(5)</sup> | NA | Available<sup>(7)</sup> |
| Rename<sup>(4)</sup> | K dispozici | K dispozici | K dispozici | K dispozici |
| Sync | K dispozici | K dispozici | K dispozici | K dispozici |
| Vzdálené uzamčení | Windows Phone only | K dispozici | K dispozici | K dispozici |
| Reset Passcode | Windows Phone only | Available<sup>(8)</sup> | NA | Available<sup>(6)</sup> |
| Key Recovery | NA | NA | Available<sup>(2)</sup> | NA |

<sup>(1)</sup> **Retire** is always blocked on Azure AD Joined Windows devices.<br>
<sup>(2)</sup> **Key Recovery** for MacOS is only available via the Web Portal.<br>
<sup>(3)</sup> All remote actions are disabled if using a Device Enrollment Manager enrollment.<br>
<sup>(4)</sup> **Rename** only changes the device name in the Company Portal app or Web Portal, not on the device.<br>
<sup>(5)</sup> **Wipe** is not available on User Enrolled iOS devices.<br>
<sup>(6)</sup> **Reset Passcode** is not supported on some Android and Android Enterprise configurations. For more information, see [Reset or remove a device passcode in Intune](../remote-actions/device-passcode-reset.md).<br>
<sup>(7)</sup> **Retire** and **Wipe** are not available on Android Enterprise Device Owner scenarios (COPE, COBO, COSU).<br> 
<sup>(8)</sup> **Reset Passcode** is not supported on User Enrolled iOS devices.

## <a name="next-steps"></a>Další kroky

- [Ruční přidání aplikace Portál společnosti pro Windows 10 pomocí Microsoft Intune](company-portal-app.md)
