---
title: Android Enterprise device settings in Microsoft Intune - Azure | Microsoft Docs
description: On Android Enterprise or Android for Work devices, restrict settings on the device, including copy and paste, show notifications, app permissions, data sharing, password length, sign in failures, use fingerprint to unlock, reuse passwords, and enable bluetooth sharing of work contacts. Configure devices as a dedicated device kiosk to run one app, or multiple apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b38ab611ecf6a33c8cc48fa120751af8548a7f95
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390929"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Android Enterprise device settings to allow or restrict features using Intune

This article lists and describes the different settings you can control on Android Enterprise devices. As part of your mobile device management (MDM) solution, use these settings to allow or disable features, run apps on dedicated devices, control security, and more.

## <a name="before-you-begin"></a>Před zahájením

[Create a device configuration profile](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Device owner only

### <a name="general-settings"></a>Obecná nastavení

- **Screen capture**: Choose **Block** to prevent screenshots or screen captures on the device. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Not configured** lets the user capture the screen contents as an image.
- **Camera**: Choose **Block** to prevent access to the camera on the device. **Not required** allows access to the device's camera.
- **Výchozí zásady oprávnění**: Toto nastavení definuje výchozí zásady oprávnění pro žádosti o oprávnění za běhu. Mezi možné hodnoty patří:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Zeptat se**: Uživateli se zobrazí výzva ke schválení oprávnění.
  - **Automaticky udělit**: Oprávnění jsou udělena automaticky.
  - **Automaticky odepřít**: Oprávnění jsou odepřena automaticky.
- **Date and Time changes**: Choose **Block** to prevent users from manually setting the date and time. **Not configured** allows users to the set date and time on the device.
- **Volume changes**: **Block** prevents users from changing the device's volume, and also mutes the master volume. **Not configured** allows using the volume settings on the device.
- **Factory reset**: Choose **Block** to prevent users from using the factory reset option in the device's settings. **Not configured** allows users to use this setting on the device.
- **Bezpečné spuštění**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v restartování zařízení do nouzového režimu. **Not configured** allows users to reboot the device in safe mode.
- **Status bar**: Choose **Block** to prevent access to the status bar, including notifications and quick settings. **Not configured** allows users access to the status bar.
- **Roaming data services**: Choose **Block** to prevent data roaming over the cellular network. **Not configured** allows data roaming when the device is on a cellular network.
- **Wi-Fi setting changes**: Choose **Block** to prevent users from changing Wi-Fi settings created by the device owner. Users can create their own Wi-Fi configurations. **Not configured** allows users to change the Wi-Fi settings on the device.
- **Wi-Fi access point configuration**: Choose **Block** to prevent users from creating or changing any Wi-Fi configurations. **Not configured** allows users to change the Wi-Fi settings on the device.
- **Bluetooth configuration**: Choose **Block** to prevent users from configuring Bluetooth on the device. **Not configured** allows using Bluetooth on the device.
- **Tethering and access to hotspots**: Choose **Block** to prevent tethering and access to portable hotspots. **Not configured** allows tethering and access to portable hotspots.
- **USB storage**: Choose **Allow** to access USB storage on the device. **Not configured** prevents access to USB storage.
- **USB file transfer**: Choose **Block** to prevent transferring files over USB. **Not configured** allows transferring files.
- **External media**: Choose **Block** to prevent using or connecting any external media on the device. **Not configured** allows external media on the device.
- **Beam data using NFC**: Choose **Block** to prevent using the Near Field Communication (NFC) technology to beam data from apps. **Not configured** allows using NFC to share data between devices.
- **Debugging features**: Choose **Allow** to let users use debugging features on the device. **Not configured** prevents users from using the debugging features on the device.
- **Microphone adjustment**: Choose **Block** to prevent users from unmuting the microphone and adjusting the microphone volume. **Not configured** allows the user to use and adjust the volume of the microphone on the device.
- **Factory reset protection emails**: Choose **Google account email addresses**. Enter the email addresses of device administrators that can unlock the device after it's wiped. Be sure to separate the email addresses with a semi-colon, such as `admin1@gmail.com;admin2@gmail.com`. If an email isn't entered, anyone can unlock the device after it's restored to the factory settings. These emails only apply when a non-user factory reset is ran, such as running a factory reset using the recovery menu.
- **Network escape hatch**: Choose **Enable** to allow users to turn on the network escape hatch feature. If a network connection isn't made when the device boots, then the escape hatch asks to temporarily connect to a network and refresh the device policy. Po uplatnění zásad se tato dočasná síť zapomene a zařízení pokračuje ve spouštění. This feature connects devices to a network if:
  - There isn't a suitable network in the last policy.
  - The device boots into an app in lock task mode.
  - The user is unable to reach the device settings.

  **Not configured** prevents users from turning on the network escape hatch feature on the device.

- **System update**: Choose an option to define how the device handles over-the-air updates:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Automaticky**: Aktualizace se instalují automaticky bez zásahu uživatele. Po nastavení této zásady se hned nainstalují všechny čekající aktualizace.
  - **Odloženo**: Aktualizace se odloží o 30 dní. At the end of the 30 days, Android prompts the user to install the update. Výrobci zařízení nebo mobilní operátoři mohou zakázat (vyloučit) odklad důležitých aktualizací zabezpečení. Vynechaná aktualizace zobrazí uživateli zařízení zprávu systému.
  - **Časové období údržby**: Aktualizace se instalují automaticky během časového období údržby, které nastavíte v Intune. Installation tries daily for 30 days, and can fail if there's insufficient space or battery levels. After 30 days, Android prompts the user to install. Toto okno se také používá k instalaci aktualizací aplikací Play. Use this option for dedicated devices, such as kiosks, as single-app dedicated device foreground apps can be updated.

- **Notification windows**: When set to **Disable**, window notifications, including toasts, incoming calls, outgoing calls, system alerts, and system errors aren't shown on the device. When set to **Not configured**, the operating system default is used, which may be to show notifications.
- **Skip first use hints**: **Enable** hides or skips suggestions from apps that step through tutorials, or hints when the app starts. When set to **Not configured**, the operating system default is used, which may show these suggestions when the app starts.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

- **Threat scan on apps**: **Require** (default) enables Google Play Protect to scan apps before and after they’re installed. If it detects a threat, it may warn the user to remove the app from the device. **Not configured** doesn't enable or run Google Play Protect to scan apps.

### <a name="dedicated-device-settings"></a>Dedicated device settings

Use these settings to configure a kiosk-style experience on your dedicated devices. You can configure a device to run one app, or run many apps. When a device is set with kiosk mode, only the apps you add are available. These settings apply to Android Enterprise dedicated devices. They don't apply to Android Enterprise fully managed devices.

**Kiosk mode**: Choose if the device runs one app or runs multiple apps.

- **Single app**: Users can only access a single app on the device. When the device starts, only the specific app starts. Uživatelé nemůžou otevírat nové aplikace ani měnit spuštěnou aplikaci.

  - **Select a managed app**: Select the managed Google Play app from the list.

    If you don't have any apps listed, then [add some Android apps](../apps/apps-add-android-for-work.md) to the device. Be sure to [assign the app to the device group created for your dedicated devices](../apps/apps-deploy.md).

  > [!IMPORTANT]
  > When using single-app kiosk mode, dialer/phone apps may not function properly. 
  
- **Multi-app**: Users can access a limited set of apps on the device. When the device starts, only the apps you add start. You can also add some web links that users can open. When the policy is applied, users see icons for the allowed apps on the home screen.

  > [!IMPORTANT]
  > For multi-app dedicated devices, the [Managed Home Screen app](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) from Google Play **must be**:
  >   - [Added as a client app](../apps/apps-add-android-for-work.md) in Intune
  >   - [Assigned to the device group](../apps/apps-deploy.md) created for your dedicated devices
  >
  > The **Managed Home Screen** app isn't required to be in the configuration profile, but it is required to be added as a client app. When the **Managed Home Screen** app is added as a client app, any other apps you add in the configuration profile are shown as icons on the **Managed Home Screen** app.
  >
  > When using multi-app kiosk mode, dialer/phone apps may not function properly. 

  - **Add**: Select your apps from the list.

    If the **Managed Home Screen** app isn't listed, then [add it from Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Be sure to [assign the app](../apps/apps-deploy.md) to the device group created for your dedicated devices.

    You can also add other [Android apps](../apps/apps-add-android-for-work.md) and [web apps](../apps/web-app.md) created by your organization to the device. Be sure to [assign the app to the device group created for your dedicated devices](../apps/apps-deploy.md).

  - **Virtual home button**: A soft-key button that returns users to the Managed Home Screen so users can switch between apps. Možnosti:

    - **Not configured** (default): A home button isn't shown. Users must use the back button to switch between apps.
    - **Swipe up**: A home button shows when a user swipes up on the device.
    - **Floating**: Shows a persistent, floating home button on the device.

  - **Leave kiosk mode**: Choose **Enable** to allow Administrators to temporarily pause kiosk mode to update the device. To use this feature, the administrator:
  
    1. Continues to select the back button until the **Exit kiosk** button is shown. 
    2. Selects the **Exit kiosk** button, and enters the **Leave kiosk mode code** PIN.
    3. When finished, select the **Managed Home Screen** app. This step relocks the device into multi-app kiosk mode.

      When set to **Not configured**, administrators can't pause kiosk mode. If the administrator continues to select the back button, and selects the **Exit kiosk** button, then a message states that a passcode is required.

    - **Leave kiosk mode code**: Enter a 4-6 digit numeric PIN. The administrator uses this PIN to temporarily pause kiosk mode.

  - **Set custom URL background**: Enter a URL to customize the background screen on the dedicated device.

    > [!NOTE]
    > For most cases, we recommend starting with images of at least the following sizes:
    >
    > - Phone: 1080x1920 px
    > - Tablet: 1920x1080 px
    >
    > For the best experience and crisp details, it’s suggested that per device image assets be created to the display specifications.
    >
    > Modern displays have higher pixel densities and can display equivalent 2K/4K definition images.

  - **Wi-Fi configuration**: **Enable** shows the Wi-Fi control on the Managed Home Screen, and allows end users to connect the device to different WiFi networks. Enabling this feature also turns on device location. **Not configured** (default) doesn't show the Wi-Fi control on the Managed Home Screen. It prevents users from connecting to Wi-Fi networks while using the Managed Home Screen.

  - **Bluetooth configuration**: **Enable** shows the Bluetooth control on the Managed Home Screen, and allows end users to pair devices over Bluetooth. Enabling this feature also turns on device location. **Not configured** (default) doesn't show the Bluetooth control on the Managed Home Screen. It prevents users from configuring Bluetooth and pairing devices while using the Managed Home Screen.

  - **Flashlight access**: **Enable** shows the flashlight control on the Managed Home Screen, and allows end users to turn the flashlight on or off. **Not configured** (default) doesn't show the flashlight control on Managed Home Screen. It prevents users from using the flashlight while using the Managed Home Screen.

  - **Media volume control**: **Enable** shows the media volume control on the Managed Home Screen, and allows end users to adjust the device's media volume using a slider. **Not configured** (default) doesn't show the media volume control on Managed Home Screen. It prevents users from adjusting the device's media volume while using the Managed Home Screen, unless their hardware buttons support it. 

  - **Screen saver mode**: **Enable** shows a screensaver on the Managed Home Screen when the device is locked or times out. **Not configured** (default) doesn't show a screensaver on the Managed Home Screen.

    When enabled, also configure:

    - **Set custom screen saver image**: Enter the URL to a custom PNG, JPG, JPEG, GIF, BMP, WebP, or ICOimage. For example, enter:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.webp`

      If you don't enter a URL, then the device's default image is used, if there is a default image.
      
      > [!TIP]
      > Any file resource URL that can be turned into a bitmap is supported.

    - **Number of seconds the device shows screen saver before turning off screen**: Choose how long the device shows the screensaver. Enter a value between 0-9999999 seconds. Default is `0` seconds. When left blank, or set to zero (`0`), the screen saver is active until a user interacts with the device.
    - **Number of seconds the device is inactive before showing screen saver**: Choose how long the device is idle before showing the screensaver. Enter a value between 1-9999999 seconds. Default is `30` seconds. You must enter a number greater than zero (`0`).
    - **Detect media before starting screen saver**: **Enable** (default) doesn't show the screen saver if audio or video is playing on the device. **Not configured** shows the screen saver, even if audio or video is playing.

### <a name="device-password-settings"></a>Nastavení hesla zařízení

- **Disable lock screen**: Choose **Disable** to prevent users from using Keyguard lock screen feature on the device. **Not configured** allows the user to use the Keyguard features.
- **Disabled lock screen features**: When keyguard is enabled on the device, choose which features to disable. For example, when **Secure camera** is checked, the camera feature is disabled on the device. Any features not checked are enabled on the device.

  These features are available to users when the device is locked. Users won't see or access features that are checked.

- **Požadovaný typ hesla**: Definujte typ hesla požadovaného pro zařízení. Možnosti:
  - **Výchozí ze zařízení**
  - **Password required, no restrictions**
  - **Weak biometric**: [Strong vs. weak biometrics](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (opens Android's web site)
  - **Numeric**: Password must only be numbers, such as `123456789`. Enter the **minimum password length** a user must enter, between 4 and 16 characters.
  - **Numeric complex**: Repeated or consecutive numbers, such as "1111" or "1234", aren't allowed. Enter the **minimum password length** a user must enter, between 4 and 16 characters.
  - **Alphabetic**: Letters in the alphabet are required. Numbers and symbols aren't required. Enter the **minimum password length** a user must enter, between 4 and 16 characters.
  - **Alphanumeric**: Includes uppercase letters, lowercase letters, and numeric characters. Enter the **minimum password length** a user must enter, between 4 and 16 characters.
  - **Alphanumeric with symbols**: Includes uppercase letters, lowercase letters, numeric characters, punctuation marks, and symbols. Dále zadejte:

    - **Minimum password length**: Enter the minimum length the password must have, between 4 and 16 characters.
    - **Number of characters required**: Enter the number of characters the password must have, between 0 and 16 characters.
    - **Number of lowercase characters required**: Enter the number of lowercase characters the password must have, between 0 and 16 characters.
    - **Number of uppercase characters required**: Enter the number of uppercase characters the password must have, between 0 and 16 characters.
    - **Number of non-letter characters required**: Enter the number of non-letters (anything other than letters in the alphabet) the password must have, between 0 and 16 characters.
    - **Number of numeric characters required**: Enter the number of numeric characters (`1`, `2`, `3`, and so on) the password must have, between 0 and 16 characters.
    - **Number of symbol characters required**: Enter the number of symbol characters (`&`, `#`, `%`, and so on) the password must have, between 0 and 16 characters.

- **Number of days until password expires**: Enter the number of days, between 1-365, until the device password must be changed. For example, to change the password after 60 days, enter `60`. When the password expires, users are prompted to create a new password.
- **Number of passwords required before user can resuse a password**: Enter the number of recent passwords that can't be reused, between 1-24. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.
- **Number of sign-in failures before wiping device**: Enter the number, between 4-11, of failed sign-ins to allow before the device is wiped.

### <a name="power-settings"></a>Nastavení napájení

- **Time to lock screen**: Enter the maximum time a user can set until the device locks. For example, if you set this setting to **10 minutes**, then users can set the time from 15 seconds up to 10 minutes. When set to **Not configured** (default), Intune doesn't change or control this setting.

- **Zapnutá obrazovka, když se zařízení napájí ze sítě**: Zvolte zdroje napájení, při jejichž použití zůstane obrazovka zařízení zapnutá.

### <a name="users-and-accounts-settings"></a>Nastavení uživatelů a účtů

- **Přidat nové uživatele**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v přidávání nových uživatelů. Each user has a personal space on the device for custom Home screens, accounts, apps, and settings. **Not configured** (default) allows users to add other users to the device.
- **Odebírání uživatelů**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v odebírání uživatelů. **Not configured** (default) allows users to remove other users from the device.
- **Account changes** (dedicated devices only): Choose **Block** to prevent users from modifying accounts. **Not configured** (default) allows users to update user accounts on the device.

  > [!NOTE]
  > This setting isn't honored on device owner (fully managed) devices. If you configure this setting, then the setting is ignored, and has no impact.

- **Personal Google Accounts**: **Block** prevents users from adding their personal Google account to the device. **Not configured** (default) allows users to add their personal Google account.

### <a name="applications"></a>Aplikací

- **Allow installation from unknown sources**: Choose **Allow** so users can turn on **Unknown sources**. This setting allows apps to install from unknown sources, including sources other than the Google Play Store. **Not configured** prevents users from turning on **Unknown sources**.
- **Allow access to all apps in Google Play store**: When set to **Allow**, users get access to all apps in Google Play store. They don't get access to the apps the administrator blocks in [Client Apps](../apps/apps-add-android-for-work.md). **Not configured** forces users to only access the apps the administrator makes available Google Play store, or apps required in [Client Apps](../apps/apps-add-android-for-work.md).
- **App auto-updates**: Choose when automatic updates are installed. Možnosti:
  - **Není nakonfigurováno**
  - **User choice**
  - **Never**
  - **Wi-Fi only**
  - **Always**

### <a name="connectivity"></a>Connectivity

- **Neustále aktivní připojení VPN**: výběrem možnosti **Povolit** nastavte klienta VPN tak, aby se automaticky připojoval a znovu připojoval k VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: vyberte klienta VPN, který podporuje neustále aktivní připojení VPN. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: zadejte ID balíčku aplikace v obchodu Google Play. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - There may be known issues when using per-app VPN with F5 Access for Android 3.0.4. See [F5's release notes for F5 Access for Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) for more information.

- **Lockdown mode**: Choose **Enable** to force all network traffic to use the VPN tunnel. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

- **Recommended global proxy**: Choose **Enable** to add a global proxy to the devices. When enabled, HTTP and HTTPS traffic, including some apps on the device, use the proxy you enter. This proxy is only a recommendation. It's possible some apps won't use the proxy. **Not configured** (default) doesn't add a recommended global proxy.

  For more information on this feature, see [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (opens an Android site).

  When enabled, also enter the **Type** of proxy. Možnosti:

  - **Direct**: Choose this option to manually enter the proxy server details, including:
    - **Host**: Enter the hostname or IP address of your proxy server. Zadejte například `proxy.contoso.com` nebo `127.0.0.1`.
    - **Port number**: Enter the TCP port number used by the proxy server. Zadejte například `8080`.
    - **Excluded hosts**: Enter a list of host names or IP addresses that won't use the proxy. This list can include an asterisk (`*`) wildcard and multiple hosts separated by semicolons (`;`) with no spaces. Zadejte například `127.0.0.1;web.contoso.com;*.microsoft.com`.

  - **Proxy Auto-Config**: Enter the **PAC URL** to a proxy autoconfiguration script. Zadejte například `https://proxy.contoso.com/proxy.pac`.

    For more information on PAC files, see [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).

## <a name="work-profile-only"></a>Pouze pracovní profil

### <a name="work-profile-settings"></a>Nastavení pracovního profilu

#### <a name="general"></a>Obecné

- **Copy and paste between work and personal profiles**: Choose **Block** to prevent copy-and-paste between work and personal apps. **Not configured** allows users to share data using copy-and-paste with apps in the personal profile 
- **Data sharing between work and personal profiles**: Choose if apps in the work profile can share with apps in the personal profile. For example, you can control sharing actions within applications, such as the **Share…** v aplikaci prohlížeče Chrome. Toto nastavení se nevztahuje na chování schránky při kopírování/vkládání. Your sharing options:
  - **Device default**: The default sharing behavior of the device, which varies depending on the Android version. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neblokuje sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: povoluje integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Prevent any sharing across boundaries**: Prevents sharing between work and personal profiles.
  - **No restrictions on sharing**: Enables sharing across the work profile boundary in both directions. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení. Proto ho používejte opatrně.

- **Work profile notifications while device locked**: Controls whether apps in the work profile can show data in notifications when the device is locked. **Block** doesn't show the data. **Not configured** shows the data.
- **Výchozí oprávnění aplikace**: umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Tyto zásady používejte k automatickému udělování oprávnění bez výzvy, automatickému odepření oprávnění bez výzvy nebo ponechání rozhodnutí na koncovém uživateli. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Zeptat se**
  - **Automaticky udělit**
  - **Automaticky odepřít**

  Zásady konfigurace aplikace můžete použít také k udělení oprávnění pro jednotlivé aplikace (**Klientské aplikace** > **Zásady konfigurace aplikací**).

- **Add and remove accounts**: Choose **Block** to prevent end users from manually adding or removing accounts in the work profile. Když do pracovního profilu Androidu nasadíte například aplikaci Gmail, můžete zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v tomto pracovním profilu. **Not configured** allows adding accounts in the work profile.  

- **Sdílení kontaktů přes Bluetooth**: Povoluje přístup k pracovním kontaktům z jiného zařízení, například ze zařízení v autě, které je spárováno pomocí Bluetooth. Ve výchozím nastavení toto nastavení není nakonfigurováno a pracovní kontakty se nezobrazují. Vyberte **Povolit** a sdílení povolte, aby se zobrazily kontakty pracovního profilu. Toto nastavení platí pro zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších. Když toto nastavení povolíte, budou určitá zařízení Bluetooth ukládat pracovní kontakty do mezipaměti při prvním připojení. V případě jejího zakázání po počátečním zpárování/synchronizaci se pracovní kontakty ze zařízení Bluetooth nemusí odstranit.

- **Screen capture**: Choose **Block** to prevent screenshots or screen captures on the device in the work profile. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Not configured** allows getting screenshots.

- **Display work contact caller-id in personal profile**: When enabled (**Not configured**), the work contact caller details are displayed in the personal profile. When set to **Block**, the work contact caller number isn't displayed in the personal profile. Platí pro operační systém Android 6.0 a novější verze.

- **Search work contacts from personal profile**: Choose **Block** to prevent users from searching for work contacts in apps in the personal profile. **Not required** allows searching for work contacts in the personal profile.

- **Camera**: Choose **Block** to prevent access to the camera on the device in the work profile. Nastavení nemá vliv na kameru v osobním profilu. **Not required** allows access to the camera in the work profile.

- **Allow widgets from work profile apps**: **Enable** allows end users to put widgets exposed by apps on the home screen. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.

  For example, Outlook is installed on your users' work profiles. When set to **Enable**, users can put the agenda widget on the device home screen.

#### <a name="work-profile-password"></a>Work Profile Password

- **Vyžadovat heslo pracovního profilu**: platí pro Android 7.0 a vyšší s aktivovaným pracovním profilem. Choose **Require** to enter a passcode policy that applies only to the apps in the work profile. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich. **Not configured** allows the user to use work apps, without entering a password.
- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**16**.
- **Maximální doba neaktivity v minutách, než se pracovní profil zamkne**: umožňuje vybrat dobu, po které se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se pracovní profil ze zařízení vymaže.
- **Konec platnosti hesla (dny)** : zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Fingerprint unlock**: Choose **Block** to prevent end users from using the device fingerprint scanner to unlock the device. **Not configured** allows users to unlock devices with a fingerprint in the work profile.
- **Smart Lock and other trust agents**: Choose **Block** to prevent Smart Lock or other trust agents from adjusting lock screen settings on compatible devices. This feature, also known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="device-password"></a>Heslo zařízení

These password settings apply to personal profiles on devices that use a work profile.

- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**14**.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: umožňuje vybrat dobu, po které neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se ze zařízení vymažou veškerá data.
- **Konec platnosti hesla (dny)** : zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Fingerprint unlock**: Choose **Block** to prevent end user from using the device fingerprint scanner to unlock the device. **Not configured** allows the user to unlock the device using a fingerprint.
- **Smart Lock and other trust agents**: Choose **Block** to prevent Smart Lock or other trust agents from adjusting lock screen settings on compatible devices. This feature, also known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="system-security"></a>System security

- **Threat scan on apps**: **Require** enforces that the **Verify Apps** setting is enabled for work and personal profiles.

   > [!Note]
   > This setting only works for devices that are Android 8 (Oreo) and above.

- **Prevent app installations from unknown sources in the personal profile**: By design, Android Enterprise work profile devices can't install apps from sources other than the Play Store. By nature, work profile devices are intended to be dual-profile:

  - A work profile managed using MDM.
  - A personal profile that's isolated from MDM management.

  This setting allows administrators more control of app installations from unknown sources. **Not configured** (default) allows app installations from unknown sources in the personal profile. **Block** prevents app installations from sources other than the Play Store in the personal profile.

### <a name="connectivity"></a>Connectivity

- **Neustále aktivní připojení VPN**: výběrem možnosti **Povolit** nastavte klienta VPN tak, aby se automaticky připojoval a znovu připojoval k VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: vyberte klienta VPN, který podporuje neustále aktivní připojení VPN. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: zadejte ID balíčku aplikace v obchodu Google Play. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - There may be known issues when using per-app VPN with F5 Access for Android 3.0.4. See [F5's release notes for F5 Access for Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) for more information.

- **Lockdown mode**: Choose **Enable** to force all network traffic to use the VPN tunnel. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

You can also create dedicated device kiosk profiles for [Android](device-restrictions-android.md#kiosk) and [Windows 10](kiosk-settings.md) devices.

## <a name="see-also"></a>Související témata

[Configuring and troubleshooting Android enterprise devices in Microsoft Intune](https://support.microsoft.com/help/4476974)
