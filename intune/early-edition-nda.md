---
title: Časná edice – Microsoft Intune
titlesuffix: ''
description: Časná edice Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 94125ced318f304e5b2bdc8f09472280fc05b08a
ms.sourcegitcommit: 662afec5e87639a7f541bb89700cc0fec5037bb0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/07/2019
ms.locfileid: "54069349"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>Časná edice Microsoft Intune – leden 2019

> [!Note]
> Smlouvu NDA pro oznámení: Následující změny v Intune jsou ve vývoji. Tyto informace jsou sdíleny ve velmi omezeném rozsahu a platí pro ně dohoda o mlčenlivosti (NDA). Nepublikujte žádné z těchto informací na sociálních sítích nebo veřejných webech, jako jsou Twitter, UserVoice, Reddit apod. 

**Časná edice** poskytuje seznam funkcí, sdílený na základě dohody o mlčenlivosti (NDA), které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Tyto informace netweetujte, nepublikujte na webu UserVoice ani jinak nesdílejte mimo vaši společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Aplikace Android Enterprise <!-- 1352553  -->
Budete moct odstranit spravované aplikace Google Play v Microsoft Intune. Pokud chcete odstranit spravovanou aplikaci služby Google Play, se otevře Microsoft Intune v Azure portal a vyberte **klientské aplikace** > **aplikace**. Ze seznamu aplikací vyberte symbol tří teček (...) napravo od spravované aplikace Google Play a potom vyberte **odstranit** ze zobrazeného seznamu. Když odstraníte spravované aplikace Google Play ze seznamu aplikací, je automaticky neschválených spravované aplikace Google Play.

### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikace Google Play spravované <!-- 1352580 -->
**Spravované Google Play** typ aplikace vám umožní konkrétně přidat [spravované aplikace Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do Intune. Jako správce Intune budou teď procházet, Hledat, schválit, synchronizovat a přiřazení aplikací v Intune schválené spravovaného obchodu Google Play. Je potřeba už spravovanou konzolu Google Play vyhledejte samostatně a už máte donutit k. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**. V **typ aplikace** seznamu vyberte **spravovaný obchod Google Play** jako typ aplikace.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Ve verzi Preview podpory pro vlastněných společností, plně spravovaná zařízení s Androidem <!-- 1574342  -->
Intune bude podporovat plně spravovaná zařízení s Androidem vlastnictví "vlastník zařízení" scénář, ve kterém zařízení úzce spravuje IT a jste spojeni jednotlivým uživatelům. To umožňuje správcům spravovat celé zařízení, vynucovat ochranu před rozsahem rozšířené ovládací prvky zásad, není k dispozici pro pracovní profily a instalaci aplikací ze spravovaného obchodu Google Play pouze omezení pro uživatele. K nastavení plně spravovaná zařízení s Androidem, budou moct **registrace zařízení** > **registrace zařízení s Androidem** > **uživatele vlastněné společností, plně spravovaná zařízení** . Mějte prosím na paměti, že tato funkce je ve verzi preview. Některé funkce Intune, jako jsou certifikáty, dodržování předpisů a podmíněného přístupu nejsou aktuálně k dispozici pro Android je plně spravovaná zařízení uživatelů.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660----"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 16726660  -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Konfigurace profilu tak, aby se v Průvodci nastavením přeskočily některé obrazovky <!-- 2276470  -->
Když vytvoříte profil registrace s macOS, bude možné a nakonfigurujte ho na některý z následujících obrazovky přeskočit, když uživatel prochází Pomocníka pro instalaci:
- Migrace zařízení s Androidem
- Tón zobrazení
- Ochrana osobních údajů
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Přiřazení profilů Autopilotu virtuální skupině Všechna zařízení <!--2715522  -->
Profily Autopilotu budete moct přiřadit virtuální skupině Všechna zařízení. Uděláte to tak, že vyberete **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil > **Přiřazení** > v části **Přiřadit k** vyberte **Všechna zařízení**. Další informace o profilech Autopilotu najdete v článku [Registrace zařízení s Windows pomocí Windows Autopilotu](enrollment-autopilot.md).

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Přizpůsobení tapeta na zařízeních s Iosem pod dohledem pomocí konfiguračního profilu zařízení <!-- 2809324  -->
Když vytvoříte profil konfigurace zařízení pro zařízení s Iosem, budete moct povolit a omezit některá nastavení v **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **iOS** pro platformu > **omezení zařízení** pro typy profilů. Tato aktualizace zahrnuje nové **tapeta** nastavení, které umožňují správcům se použije jako tapeta, PNG, JPG nebo JPEG image ve verzi preview na obrázku a zablokovat uživatelům možnost měnit tapetu. Tapeta nastavení platí pouze pro zařízení pod dohledem. Seznam nastavení najdete v tématu [nastavení omezení zařízení s Iosem](device-restrictions-ios.md).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Informační zprávy pro aplikace Win32 <!-- 3136566   -->
Budete moct potlačit oznámení informační zpráva zobrazující koncový uživatel jednotlivé přiřazení aplikace. V Intune, vyberte **klientské aplikace** > **aplikace** > vyberte aplikaci > **Assignemnts** > **zahrnout skupiny**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Sdílení kontaktů přes Bluetooth se už v omezení zařízení > vlastník zařízení pro Android Enterprise <!-- 3598396 -->
Když vytvoříte profil omezení zařízení pro zařízení s Androidem Enterprise, je **sdílení kontaktů přes Bluetooth** nastavení. V této aktualizaci **sdílení kontaktů přes Bluetooth** bude třeba odebrat nastavení (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu Enterprise** pro platformu > **omezení zařízení > vlastník zařízení** pro typy profilů >  **Obecné**). 

**Sdílení kontaktů přes Bluetooth** nastavení není podporováno pro vlastníka zařízení s Androidem Enterprise management. Takže při odebrání tohoto nastavení neovlivní žádné zařízení ani tenantů, i když toto nastavení je povolena a konfigurována ve vašem prostředí.

Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md).

Platí pro: Vlastník zařízení s androidem Enterprise

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Aplikace pro Android Enterprise-jsme nasazení aplikace <!-- 1171203 -->
Pro zařízení s Androidem v neregistrovaných ochrany zásady bez registrace aplikace (APP-jsme) scénář nasazení, které budete moct pomocí spravovaného obchodu Google Play můžete nasadit aplikace pro store a obchodní aplikace pro uživatele. Konkrétně může oddělení IT koncovým uživatelům poskytnout aplikaci katalogu a instalace prostředí, které už vyžaduje, aby koncoví uživatelé zmírnit stav zabezpečení svých zařízeních tím, že instalace z neznámých zdrojů. Kromě toho tento scénář nasazení bude poskytovat Vylepšené uživatelské prostředí.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nové možnosti, které automaticky připojit a zachovat pravidla při použití nastavení DNS na Windows 10 a novější zařízení <!-- 1333665, 2999078 -->
V systému Windows 10 a novější zařízení budete moct vytvořit konfigurační profil sítě VPN, který obsahuje seznam serverů DNS přeložit domén, třeba contoso.com. To bude obsahovat nové nastavení pro překlad adres (**konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit  **Windows 10 a novější** pro platformu > zvolit **VPN** pro typy profilů > **nastavení DNS** >**přidat**): 

- **Automaticky se připojovat**: Když **povoleno**, zařízení se automaticky připojí k síti VPN, když zařízení kontaktuje domény můžete zadat, třeba contoso.com.
- **Trvalé**: Ve výchozím nastavení všechna pravidla tabulky (IP adres NRPT) název zásady překladu IP adres jsou aktivní, tak dlouho, dokud se zařízení připojí pomocí tohoto profilu sítě VPN. Pokud je toto nastavení **povoleno** u pravidla tabulky NRPT, zůstane aktivní na zařízení, pravidla, dokonce i při odpojení sítě VPN. Pravidlo zůstane, dokud se odebere profil sítě VPN nebo dokud je ručně odebrat pravidlo, které lze provést pomocí Powershellu.

[Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md) popisuje aktuální seznam nastavení. 

### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user----1333642-eeready---"></a>Použít S/MIME k šifrování a podepisování více zařízení pro uživatele <!-- 1333642 eeready -->
Šifrování S/MIME e-mailu pomocí nového profilu importovaný certifikát se bude podporovat (**konfigurace zařízení** > **profily** > **vytvořit profil** > Vyberte platformy > **importovaný certifikát PKCS** typ profilu). V Intune můžete importovat certifikáty ve formátu PFX. Intune pak může doručit stejné certifikáty do více zařízení zaregistrovaných jedním uživatelem. To také zahrnuje:

- Nativní e-mailový profil v iOS podporuje povolení šifrování S/MIME pomocí importovaných certifikátů ve formátu PFX.
- Nativní poštovní aplikace na zařízeních se systémem Windows Phone 10 automaticky použije certifikát S/MIME.
- Privátní certifikáty je možné doručit na různé platformy. Některé e-mailové aplikace ale S/MIME nepodporují.
- Na jiných platformách může být nutné ručně nakonfigurovat e-mailovou aplikaci a povolit S/MIME.  
- E-mailové aplikace, které podporují šifrování S/MIME, můžou zpracovávat načítání certifikátů pro šifrování S/MIME e-mailů způsobem, který MDM nepodporuje (například ho načítají z úložiště certifikátů svého vydavatele).

Podporované platformy: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Nápověda a podpora stránky v aplikaci portál společnosti pro Windows <!-- 1488939 -->
Nová stránka se přidají do aplikace portál společnosti Windows. Na stránce Nápověda a podpora poskytne kontaktní údaje helpdesku. Koncoví uživatelé budou také moct posílat protokoly portálu společnosti v případě, že jsou problémy s. Na stránce také poskytuje části Nejčastější dotazy k pomoci koncovým uživatelům.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Detekce důvěryhodných sítí pomocí profilů sítě VPN na zařízeních s Windows 10 <!-- 1500165 -->
Při použití detekce důvěryhodných sítí, budete moct zabránit profily sítě VPN automaticky vytvoří připojení k síti VPN, pokud je uživatel v důvěryhodné síti. Budete moct přidat přípony DNS pro povolení detekce důvěryhodných sítí na zařízeních s Windows 10 a novější (**konfigurace zařízení** > **profily**  >   **Vytvoření profilu** > **Windows 10 a novější** pro platformu > **VPN** pro typ profilu).
[Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md) uvádí aktuální nastavení sítě VPN.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune App SDK bude podporovat 256bitových šifrovacích klíčů <!-- 1832174 -->
Sady Intune App SDK pro Android bude používat 256bitových šifrovacích klíčů, když je povoleno šifrování pomocí zásad ochrany aplikací. Sady SDK bude dále poskytovat podpora 128bitových klíčů z důvodu kompatibility s obsahem a aplikace, které používají starší verze sady SDK.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917-1063203---"></a>Povolené nastavení sdíleného počítače v Intune profil <!-- 1907917, 1063203 -->
V současné době můžete nakonfigurovat nastavení sdílené počítače na desktopových zařízeních s Windows 10 pomocí vlastního nastavení OMA-URI. Přidá nový profil konfigurace nastavení sdílené počítače (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** > **sdílený více uživateli zařízení**).

Platí pro: Windows 10 a novější, Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Aktualizovat zásady Intune metodu ověřování a instalace aplikace portál společnosti  <!-- 1927359 -->
Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple Intune nebude podporovat aplikace portál společnosti nainstalovaný ručně koncovými uživateli z app storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator
* Obchodní ředitel společnosti Apple
* Apple School Manager
* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. Tato zařízení bude očekávat, jenom když ho se převede, automaticky, pomocí Intune během registrace použijí portál společnosti. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. Kromě toho **identifikaci vašeho zařízení** obrazovky v aplikaci portál společnosti bude brzo zastaralá.  
Chcete-li nainstalovat portál společnosti na již zaregistrované zařízení DEP, budete muset přejít do Intune > klientských aplikací a poslat ho jako spravovaná aplikace pomocí zásad Konfigurace aplikací. Podrobnosti o tom, jak provést tyto kroky budou uvedené v budoucích dokumentace.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Non-správci mohou povolit nástroj BitLocker na zařízeních s Windows 10 připojená k Azure AD<!-- 2147379 -->
Když povolíte nastavení nástroje BitLocker na zařízeních s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** pro platformu > **Endpoint protection** pro typy profilů > **šifrování Windows**), přidejte nastavení Bitlockeru. Tato aktualizace zahrnuje nové nastavení nástroje BitLocker umožňuje standardní uživatelé (bez oprávnění správce), aby šifrování povolil. Aktuální nastavení najdete v tématu [nastavení služby Endpoint protection pro Windows 10](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-app-pin----2298397---"></a>PIN aplikace Intune <!-- 2298397 -->
Jako správce IT budete moct nakonfigurovat počet dní, po které koncový uživatel počkat, až pro aplikaci Intune, které se musí změnit PIN kód. Nové nastavení bude k dispozici na webu Azure Portal tak, že vyberete **Intune** > **klientské aplikace** > **zásady ochrany aplikací**  >  **Vytvořit zásadu** > **nastavení** > **požadavky na přístup**. Tato funkce bude k dispozici na iOS a androidem. Toto nastavení podporuje kladné celé číslo.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Nové nastavení aktualizace Windows 10 <!-- 2626030 2512994 -->
Pro vaše aktualizační okruhy Windows 10 budete moct:
- obnovit původní nastavení automatických aktualizací na počítač s Windows 10 na počítače, které běží *aktualizace z října 2018*
- aktualizace nastavení, která umožňuje blokovat nebo povolit uživatelům k pozastavení instalace aktualizace z nového softwaru nakonfigurujte *nastavení* jejich počítačů. 



### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>e-mailové profily iOS můžete použít S/MIME podepisování a šifrování <!-- 2662949 -->
Budete moct vytvořit e-mailový profil, který obsahuje jiné nastavení. To zahrnuje nastavení S/MIME, které lze použít pro podepisování a šifrování komunikace e-mailu na zařízeních s Iosem (**konfigurace zařízení** > **profily**  >   **Vytvoření profilu** > zvolit **iOS** pro platformu > **e-mailu** pro typ profilu).

[Konfigurace nastavení e-mailu iOS](email-settings-ios.md) vypíše aktuální nastavení.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>Přeskočit další obrazovky Pomocníka s nastavením nastavení na zařízení s Iosem <!-- 2687509 -->
Kromě obrazovky, které se aktuálně můžete přeskočit budete moct nastavit zařízení s programem DEP, přejděte na následující obrazovce v nastavením když se uživatel zaregistruje zařízení s Iosem: Zobrazení tón, ochrany osobních údajů, Android migrace, tlačítko Domů, iMessage & FaceTime, připojení, sledování migrace, vzhled, čas obrazovky, aktualizace softwaru, SIM instalace.
Zvolte, které obrazovky přeskočte, přejděte na **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token > **Profily** > zvolte profil > **vlastnosti** > **Pomocníka pro nastavení přizpůsobení** > zvolte **skrýt**  pro všechny obrazovky, které chcete nechat Přeskočit > **OK**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Edice Windows 10 Pro podporu některých nastavení Bitlockeru<!-- 2727036 -->
Budete moct vytvořit konfigurační profil, který nastaví nastavení služby endpoint protection na zařízeních s Windows 10, včetně nástroje BitLocker. Tento postup přidá podporu pro Windows 10 Professional edition pro některá nastavení nástroje BitLocker. Nastavení aktuální edice Windows 10 najdete v tématu [nastavení služby Endpoint protection pro Windows 10](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-device-reporting-fields----2748738---"></a>Zařízení v Intune polí pro vytváření sestav <!-- 2748738 -->
Intune bude poskytovat další zařízení polí, včetně s Androidem výrobce, model a verzi opravy zabezpečení, jakož i modelu iOS, který pro vytváření sestav. V Intune najdete tato pole budou dostupná tak, že vyberete **klientské aplikace** > **stav ochrany aplikace** a zvolíte **sestava ochrany aplikací: iOS, Android**. Kromě toho tyto parametry můžete nakonfigurovat **povolit** seznamu pro výrobce zařízení (Android), **povolit** seznam pro model zařízení (Android a iOS) a minimální opravu zabezpečení Androidu nastavení verze. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>Konfigurace sdíleného zařízení bylo přejmenováno na zpráva na zamčené obrazovce pro zařízení s Iosem na webu Azure Portal <!-- 2809362 -->
Při vytváření konfiguračního profilu pro zařízení s Iosem, budete moct přidat **konfigurace sdíleného zařízení** nastavení na zamykací obrazovce zobrazit určitý text. To zahrnuje následující změny: 

- **Konfigurace sdíleného zařízení** nastavení na portálu Azure portal je přejmenován na "Zpráva na zamčené obrazovce (jenom pod dohledem)" (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolit **iOS** pro platformu > zvolit **funkcí na zařízeních** pro typy profilů > **zámku Obrazovky zprávy**).
- Když přidáte zámek obrazovky zprávy, můžete vložit sériové číslo, název zařízení nebo jiné hodnoty konkrétní zařízení jako proměnná v **informace z inventárního štítku**. Například můžete zadat `Device name: {{device name}}` nebo `Serial number is {{serial number}}` pomocí složených závorek. [tokeny pro iOS](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) uvádí dostupné tokeny, které lze použít.

[Nastavení pro zobrazení zpráv na zamykací obrazovce](shared-device-settings-ios.md) vypíše aktuální nastavení.

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Podrobnější zasílání zpráv selhání omezení registrace <!-- 3111564-->
Podrobné chybové zprávy, bude k dispozici, pokud nejsou splněné omezení registrace. Chcete-li zobrazit tyto zprávy, přejděte na **Intune** > **Poradce při potížích** > a zkontrolovat chyby registrace tabulku.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nové oznámení, Rady a keyguard nastavení vlastníka zařízení s Androidem Enterprise <!-- 3201839 3201843 -->
Tato aktualizace zahrnuje několik nových funkcí na zařízeních s Androidem Enterprise, při spuštění jako vlastník zařízení. K používání těchto funkcí, přejděte na **konfigurace zařízení** > **profily** > **vytvořit profil** > v **platformy**, zvolte **Androidu Enterprise** > v **typ profilu**, zvolte **jen vlastník zařízení** > **zařízení Omezení**.
Mezi nové funkce patří: 
- Zakázat oznámení systému ze zobrazení, včetně příchozí volání, systém upozornění, chyby systému a další
- Navrhne přeskočit počáteční kurzy a pomocných parametrů pro aplikace, které jsou otevřené poprvé
- Zakázat rozšířené keyguard, odemkněte nastavení, jako je fotoaparát, oznámení, otisk prstu a další

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení omezení pro zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Vlastník zařízení s androidem enterprise, můžete použít připojení Always On VPN <!-- 3202194 -->
V této aktualizaci použijete k připojení vždy zapnutá síť VPN na zařízeních s Androidem enterprise zařízení vlastníka. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
Můžete povolit vždy zapnutá síť VPN v **konfigurace zařízení** > **profily** > **vytvořit profil**  >   **Android enterprise** pro platformu > **omezení zařízení** jen vlastník zařízení > **připojení** nastavení. Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení omezení pro zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nové nastavení pro procesy ve Správci úloh na zařízení s Windows 10 <!-- 3285177 --> 
Tato aktualizace zahrnuje nové nastavení k ukončení procesů pomocí Správce úloh na zařízení s Windows 10. Pomocí konfiguračního profilu zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > v **platformy** , zvolte **Windows 10** > v **typ profilu**, zvolte **omezení zařízení** > **Obecné** nastavení), budete chtít povolit nebo zakázat toto nastavení.
Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení omezení zařízení s Windows 10](device-restrictions-windows-10.md).
Platí pro: Windows 10 a novější

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi public preview a přesunout do své vlastní konfigurační profil <!-- 3322847 -->
Šablony pro správu v Intune (**konfigurace zařízení** > **šablony pro správu**) jsou aktuálně ve verzi private preview. Od této aktualizace: Šablony pro správu zahrnuje přibližně 300 nastavení, které jde spravovat v Intune. Dříve tato nastavení existuje pouze v editoru zásad skupiny.
Šablony pro správu jsou k dispozici ve verzi public preview pro správu šablon se přesouvají z **konfigurace zařízení** > **šablony pro správu** k **zařízení konfigurace** > **profily** >**vytvořit profil** > v **platformy**, zvolte  **Windows 10 a novější**v **typ profilu**, zvolte **šablony pro správu**.
Je povoleno oznamování platí pro: Windows 10 a novější

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>MacOS tmavě režimu portál společnosti Intune <!-- 3300524 -->
Portál společnosti pro macOS Intune teď podporuje tmavě režim pro macOS. Když zapnete režim tmavé na zařízení s macOS 10.14 +, portál společnosti bude upravit vzhled na barvy zrcadlení tohoto režimu.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Použití Microsoftem doporučených nastavení se standardními hodnotami zabezpečení <!-- 2055484 -->
Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce bude moct vytvářet zásady zabezpečení přímo z těchto standardních hodnot a potom je nasazovat svým uživatelům. Doporučení osvědčených postupů může upravit tak, aby vyhovovala potřebám jeho organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

### <a name="scope-tags-for-apps---1081941---"></a>Značky oboru pro aplikace <!--1081941 -->
Budete moct vytvářet značky oboru a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).
Pokud chcete vytvořit značku oboru, vyberte **Role Intune** > **Obor (značky)** > **Vytvořit**.
Značku oboru přidáte k přiřazení role tak, že zvolíte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.
Ke konfiguračnímu profilu přidáte značku oboru tak, zvolíte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

### <a name="tenant-health-dashboard----1124854---"></a>Řídicí panel Stav tenanta <!-- 1124854 -->
Stránka Stav tenanta v Intune vám poskytne informace o stavu tenanta na jednom místě. Stránka je rozdělená do 4 částí:  
- **Tenant podrobnosti**: Obsahuje informace, jako je například vaše autorita MDM, celkový počet zaregistrovaných zařízení ve vašem tenantovi a licence se počítá. Tato část také obsahuje aktuální vydanou verzi služby pro vašeho tenanta.
- **Stav konektoru**: Obsahuje informace o konfigurovaných konektorů, jako je například Apple VPP, Windows Store pro firmy a certifikát konektory. Na základě jejich aktuálního stavu jsou konektory označené jako *V pořádku*, *Upozornění* nebo *Není v pořádku*.
- **Stav služby Intune**: Obsahuje aktivní incidenty nebo výpadky pro vašeho tenanta. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).
- **Intune zpráv**: Obsahuje aktivní zprávy pro vašeho tenanta, které patří oznámení, že váš tenant byl přijat nejnovější funkce Intune. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Nasazené zásady WIP bez registrace uživatele <!-- 1434452 -->
Zásady Windows Information Protection (WIP) budou k dispozici pro nasazení, aniž by se vyžadovalo, aby si uživatelé MDM zaregistrovali svá zařízení s Windows 10. Tato konfigurace umožňuje společnostem chránit jejich podnikové dokumenty na základě konfigurace WIP a zároveň umožňuje uživatelům uchovat si správu svých vlastních zařízení s Windows. Jakmile jsou dokumenty chráněny zásadami WIP, mohou být chráněná data selektivně vymazána správcem služby Intune. Výběrem uživatele a zařízení a odesláním žádosti o vymazání se veškerá data chráněná prostřednictvím zásad WIP stanou nepoužitelnými. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Změna v procesu aktualizace pro místní konektory <!-- 2277554 -->
Na základě zpětné vazby od zákazníků se změní způsob, jak se aktualizují místní konektory. Po prvotní instalaci místního konektoru budou aktualizace probíhat automaticky. Tato změna začne s novým konektor certifikátu PFX pro Microsoft Intune a následně bude zavedena u dalších typů místních konektorů. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Kontrola Configuration Manageru z hlediska dodržování předpisů <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení pro dodržování předpisů System Center Configuration Manageru (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. V Intune můžete nastavit požadavek, aby všechny signály Configuration Manageru hlásily vyhovující stav.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.



## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).



