---
title: "Microsoft Intune App SDK pro Android – Příručka pro vývojáře | Microsoft Intune"
description: 
keywords: Sada SDK
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: edbc701effb3817c2f9a160f05e7b5bc8ad0070e
ms.openlocfilehash: ee3a668a5415d14eb82e64e6bb16d9621bb13b57


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Microsoft Intune App SDK pro Android – Příručka pro vývojáře

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Přehled sady Intune App SDK](intune-app-sdk.md), který vysvětluje aktuální funkce sady SDK a popisuje postup přípravy integrace na jednotlivých podporovaných platformách. 

Microsoft Intune App SDK pro Android umožňuje začlenit správu mobilních aplikací (MAM) Intune do vaší aplikace pro Android. Aplikace s podporou MAM je integrovaná se sadou Intune App SDK a umožňuje správcům IT nasadit zásady do mobilní aplikace, která je aktivně spravovaná službou Intune.

# <a name="whats-in-the-sdk"></a>Co je v sadě SDK 

Intune App SDK pro Android je standardní knihovna pro Android, která nemá žádné externí závislosti. Sadu SDK tvoří:  

* **Microsoft.Intune.MAM.SDK.jar**: Rozhraní nutná pro povolení MAM a interoperabilita s Portálem společnosti Microsoft Intune. Aplikace je musí uvádět jako odkazy na knihovnu pro Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Rozhraní nutná pro povolení MAM v aplikacích, které využívají knihovnu podpory Android v4.  Aplikace, které vyžadují tuto podporu, musí na soubor jar odkazovat přímo. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Rozhraní nutná pro povolení MAM v aplikacích, které využívají knihovnu podpory Android v7. Aplikace, které vyžadují tuto podporu, musí na soubor jar odkazovat přímo.

* **Adresář prostředků**: Prostředky (jako jsou třeba řetězce), na které SDK spoléhá. 

* **Microsoft.Intune.MAM.SDK.aar**: Komponenty SDK kromě souborů jar Support.V4 a Support.V7. Tento soubor jde použít místo individuálních komponent, pokud systém sestavení podporuje soubory AAR.

* **AndroidManifest.xml**: Další vstupní body a požadavky knihoven. 

* **THIRDPARTYNOTICES.TXT**: Označení autorství, které uznává kód OSS nebo kód třetí strany, který se zkompiluje do vaší aplikace. 

# <a name="requirements"></a>požadavky 

Intune App SDK je zkompilovaný projekt pro Android. Vzhledem k tomu je do značné míry lhostejné, kterou verzi Androidu aplikace využívá jako minimální nebo cílové verze API. SDK podporuje Android API 14 (Android 4.0+) až Android API 24. 

Intune App SDK pro Android se při povolení zásad MAM spoléhá na přítomnost [Portálu společnosti](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) v zařízení. U MAM bez registrace zařízení **nemusí** uživatel registrovat zařízení přes Portál společnosti.


# <a name="how-the-intune-app-sdk-works"></a>Jak Intune App SDK funguje 

##<a name="entry-points"></a>Vstupní body

Sada Intune App SDK vyžaduje pro povolení zásad správy aplikací Intune změny ve zdrojovém kódu aplikace. Udělají se tak, že se základní třídy Androidu nahradí ekvivalentními základními třídami Intune, jejichž názvy mají předponu **MAM**. Třídy SDK se pohybují mezi základní třídou Androidu a vlastní odvozenou verzí této třídy v aplikaci.  Když jako příklad použijeme aktivitu, výsledná hierarchie dědičnosti bude vypadat takto: Aktivita ->MAMActivity->AppSpecificActivity.

Když třeba **AppSpecificActivity** komunikuje s nadřazenou třídou (například volání `super.onCreate()`), bude **MAMActivity** super třída. 

Běžné aplikace pro Android mají jeden režim a můžou přistupovat do systému přes svůj objekt [Context](https://developer.android.com/reference/android/content/Context.html).  Aplikace, které začlenily Intune App SDK, mají oproti tomu dva režimy. Aplikace i nadále přistupují k systému přes objekt Context, ale podle základní použité aktivity bude tento objekt poskytovat Android nebo bude inteligentně multiplexovaný mezi omezeným zobrazením systému a objektu Context, který poskytuje Android.

Při použití [vstupního bodu](https://developer.android.com/guide/components/fundamentals.html) Androidu, který se přepsal ekvivalentem MAM, se musí použít verze MAM životního cyklu vstupního bodu (kromě třídy **MAMApplication**).

Třeba při odvozování z třídy **MAMActivity** musí aktivita místo přepsání `onCreate` a volání `super.onCreate` přepsat `onMAMCreate` a volat `super.onMAMCreate`. Intune tak mimo jiné může v určitých případech omezit spuštění aktivity. 


##<a name="sdk-permissions"></a>Oprávnění sady SDK

Intune App SDK vyžaduje tři [oprávnění pro systém Android](https://developer.android.com/guide/topics/security/permissions.html) u aplikací, které ji integrují:

* `android.permission.GET_ACCOUNTS`  [v případě potřeby se požaduje za běhu]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

Tato oprávnění vyžaduje Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) k zprostředkovanému ověřování. Pokud nejsou tato oprávnění udělená aplikaci nebo je uživatel odvolá, zakážou se toky ověřování, které vyžadují zprostředkovatele (aplikace Portál společnosti).


##<a name="company-portal"></a>Portál společnosti

Proč se vyžaduje aplikace Portál společnosti. Pokud je Portál společnosti nainstalovaný na zařízení a načetl zásady omezení pro aplikací pro uživatele ze služby Intune, inicializují se vstupní body SDK asynchronně. Inicializace se vyžaduje, jenom když je proces původně vytvořený Androidem. Při inicializaci se naváže spojení s aplikací Portál společnosti a z aplikace se načtou zásady.  

> [!NOTE]
> Pokud není aplikace Portál společnosti dostupná, chování aplikace s podporou Intune se nezmění a bude se chovat stejně jako normální aplikace.


# <a name="how-to-integrate-with-the-intune-app-sdk"></a>Postup při integraci s Intune App SDK
 
Jak se uvádí výše, Intune App SDK vyžaduje pro povolení zásad správy aplikací změny ve zdrojovém kódu aplikace. Tady jsou kroky nutné k povolení MAM v aplikaci: 

## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Náhrada tříd, metod a aktivit odpovídajícím ekvivalentem MAM (povinné) 

Základní třídy Android se musí nahradit odpovídajícími ekvivalenty MAM. Uděláte to tak že vyhledáte všechny instance tříd uvedených v následující tabulce a nahradíte je ekvivalenty ze sady Intune App SDK. 

| Základní třída Android | Náhrada ze sady Intune App SDK |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | **MAMPendingIntent** * |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | **MAMBinder** (nutné jenom v případě, že se třída Binder negeneruje z rozhraní AIDL (Android Interface Definition Language)) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppnebot.v4.jar**:

| Intune MAM třídy Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
    
**Microsoft.Intune.MAM.SDK.Suppnebot.v7.jar**:

|Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Při použití [vstupního bodu](https://developer.android.com/guide/components/fundamentals.html) Androidu, který se přepsal ekvivalentem MAM, se musí použít verze MAM životního cyklu vstupního bodu (kromě třídy **MAMApplication**).
>
>Třeba při odvozování z třídy **MAMActivity** musí aktivita místo přepsání `onCreate` a volání `super.onCreate` přepsat `onMAMCreate` a volat `super.onMAMCreate`. Intune tak mimo jiné může v určitých případech omezit spuštění aktivity. 

### <a name="pendingintents-and-renamed-methods"></a>Třídy PendingIntents a přejmenované metody 

Po odvození některého ze vstupních bodů MAM je bezpečné používat objekt Context jako obvykle, třeba k běžnému spouštění aktivit, používání **Správce balíčků** atd.  

Výjimkou z tohoto pravidla jsou třídy **PendingIntents**. Při volání těchto tříd je nutné změnit název třídy. Třeba místo `PendingIntent.get*` se musí použít metoda `MAMPendingIntents.get*`. Pak se dají výsledné třídy **PendingIntents** používat jako obvykle.

V některých případech je metoda dostupná ve třídě Androidu označená v náhradní třídě MAM jako finální. Náhradní třída MAM pak poskytuje metodu s podobným názvem (obecně s příponou MAM), která by se měla přepsat místo toho. Třeba místo `ContentProvider.query`by se mělo přepsat `MAMContentProvider.queryMAM`. Kompilátor Javy by měl vynutit finální omezení, která zabrání náhodnému přepsání původní metody místo jejího ekvivalentu MAM. 

##<a name="enable-features-that-require-app-participation"></a>Povolení funkcí, které vyžadují účast aplikace 

Některé zásady nemůže sada SDK implementovat sama o sobě. Aplikace může kontrolovat své chování a dosáhnout těchto funkcí přes několik rozhraní API, která najdete v níže uvedeném rozhraní **AppPolicy**.  

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 * 
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 * 
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 * 
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

## <a name="enable-it-control-over-app-saving-behavior"></a>Povolení kontroly IT nad chováním při ukládání aplikace

Spousta aplikací implementuje funkce, které koncovému uživateli umožňují uložit soubory místně nebo do služby cloudového úložiště. Intune App SDK umožňuje správcům IT nastavit ochranu před úniky dat tak, že použijí omezení zásad, která jsou vhodná pro jejich organizaci.  Jedno ze zásad, kterou IT může kontrolovat, je to, jestli koncový uživatel může ukládat do osobního nespravovaného úložiště dat. To zahrnuje ukládání do místního umístění, na kartu SD nebo do služeb zálohování třetích stran. 

**K povolení této funkce je nutné zapojení aplikací.** Pokud aplikace umožňuje přímé ukládání do osobních nebo cloudových umístění, musíte implementací této funkce zajistit, aby správce IT měl kontrolu nad tím, jestli je ukládání do umístění povolené. Rozhraní API níže dá aplikaci vědět, jestli je na základě aktuálních zásad správce Intune povolené ukládání do osobního úložiště. Aplikace pak může tyto zásady vynutit, protože si je vědoma, že jejím prostřednictvím jsou koncovým uživatelům dostupná osobní úložiště dat.  

K určení, jestli je tato zásada vynucená, aplikace použije toto volání: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Poznámka**: `MAMComponents.get(AppPolicy.class)` vždycky vrátí nenulovou zásadu aplikace, i když zařízení nebo aplikace nepodléhají zásadám správy Intune. 

## <a name="allow-app-to-detect-if-pin-policy-is-required"></a>Povolení detekce, jestli se vyžaduje zásada PIN
 
U některých omezení aplikací Intune je možné, že budete chtít, aby vaše aplikace zakázala některé ze svých funkcí, aby se funkce neduplikovala v Intune App SDK. Pokud aplikace třeba využívá vlastní kód PIN, bude ho chtít zřejmě zakázat, pokud je sada SDK nakonfigurovaná tak, aby od koncového uživatele vyžadovala zadání kódu PIN. 

Aby mohla aplikace určit, jestli je zásada pro PIN nakonfigurovaná tak, aby vyžadovala při spuštění kód PIN, může využít toto volání: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## <a name="registering-for-notifications-from-the-sdk"></a>Registrace oznámení od SDK  

Intune App SDK umožňuje aplikaci, aby měla kontrolu nad chováním určitých zásad, jako je třeba selektivní vymazání, pokud je správce IT nasadil. Jakmile správce IT tuto zásadu nasadí, služba Intune odešle sadě SDK oznámení.

Vaše aplikace musí registrovat oznámení ze sady SDK vytvořením třídy **MAMNotificationReceiver**, kterou pak zaregistruje pomocí **MAMNotificationReceiverRegistry**. V `App.onCreate` se uvede příjemce a typ požadovaného oznámení, jak ukazuje tento příklad:

``` 
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

**MAMNotificationReceiver** bude jednoduše dostávat oznámení ze služby Intune. Některá oznámení zpracovává přímo sada SDK, jiná vyžadují zapojení aplikace. 

Aplikace **musí** z oznámení vrátit hodnotu true nebo false. 

True musí vracet vždycky, pokud neselže některá z akcí, kterou se v důsledku oznámení pokusí provést. 

* Toto selhání může být nahlášené službě Intune. Příkladem scénáře nahlášení je situace, kdy správce IT iniciuje vymazání dat uživatele a aplikaci se pak nepodaří data vymazat. 

Blokování v `MAMNotificationReceiver.onReceive` je bezpečné, protože zpětné volání neběží na vlákně uživatelského rozhraní. 

Níže je uvedené rozhraní **MAMNotificationReceiver** tak, jak je definované v sadě SDK: 

```
/**
 * The SDK is signaling that a WG event has occurred. 
 * 
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     * 
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in 
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

##<a name="types-of-notifications"></a>Typy oznámení
Následující oznámení se odesílají do aplikace a některá z nich můžou vyžadovat zapojení aplikace: 

* **`WIPE_USER_DATA`**: Toto oznámení se posílá ve třídě **MAMUserNotification**. Po přijetí tohoto oznámení by aplikace měla odstranit všechna data přidružená k podnikové identitě předané přes **MAMUserNotification**. Toto oznámení se momentálně odesílá při rušení registrace služby Intune. Během procesu registrace se obvykle zadává primární uživatelské jméno. Když si zaregistrujete toto oznámení, aplikace musí zajistit odstranění všech dat uživatele. Pokud si ho nezaregistrujete, použije se výchozí selektivní mazání.

* **`WIPE_USER_AUXILIARY_DATA`**: Aplikace si můžou zaregistrovat toto oznámení, pokud má sada Intune App SDK provést výchozí selektivní vymazání a mají se přitom odebrat ještě některá pomocná data.  

* **`REFRESH_POLICY`**: Toto oznámení se posílá ve třídě **MAMUserNotification**. Po přijetí tohoto oznámení se musí zrušit platnost všech zásad Intune uložených v mezipaměti a zásady se musí aktualizovat. To má běžně na starosti sada SDK, ale pokud se zásada používá trvale, měla by ji zpracovat aplikace. 



## <a name="protecting-backup-data"></a>Ochrana dat zálohy 

Od verze Android Marshmallow (API 23) má Android dvě možnosti, jak může aplikace zálohovat svá data. Obě možnosti se dají použít pro vaši aplikaci a k tomu, aby se zajistila správná implementace ochrany dat Intune, je potřeba udělat různé kroky. Přehled akcí požadovaných pro zajištění správné ochrany dat najdete v tabulce níže.  Další informace o metodách zálohování najdete v [průvodci rozhraním Android API](http://developer.android.com/guide/topics/data/backup.html). 

### <a name="auto-backup-for-apps"></a>Automatické zálohování pro aplikace

Na zařízeních s Androidem Marshmallow začal Android nabízet aplikacím [automatické úplné zálohování](https://developer.android.com/guide/topics/data/autobackup.html) bez ohledu na cílové rozhraní API aplikace. Pokud v souboru AndroidManifest.xml, explicitně nastavíte `android:allowBackup` na hodnotu **false**, Android nikdy nezařadí vaši aplikaci do fronty pro zálohy a podniková data zůstanou v aplikaci. V takovém případě není potřeba žádná další akce.

Ve výchozím nastavení je ale atribut `android:allowBackup` nastavený na hodnotu true, i když v souboru manifestu není specifikovaný parametr `android:allowBackup`. To znamená, že všechna data aplikace se automaticky zálohují do účtu Disku Google uživatele. Je to výchozí chování, které představuje určité **riziko úniku dat**. Proto sada SDK vyžaduje níže uvedené změny, které zajistí použití ochrany dat.  Pokud chcete svoji aplikaci spouštět na zařízeních s Androidem Marshmallow, měli byste postupovat podle níže uvedených pokynů k zajištění řádné ochrany zákaznických dat.  

*  Pokud jste nenapsali agenta pro zálohování svojí aplikace přes **MAMBackupAgent** nebo **MAMBackupAgentHelper**, musíte zvážit a určit, jak bude automatické zálohování nahrávat data aplikace. Intune vám umožňuje využívat všechny [funkce automatického zálohování](https://developer.android.com/guide/topics/data/autobackup.html), které nabízí Android, včetně možnosti definovat vlastní pravidla v XML, musíte ale zabezpečit svoje data podle tohoto postupu:

    1. Díky výchozí třídě MAMBackupAgent můžete povolit automatické úplné zálohy, které splňují zásady Intune. Do manifestu aplikace vložte `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"`. 
    2. Až se rozhodnete, jaký typ plné zálohy by měla vaše aplikace obdržet (nefiltrovaný, filtrovaný nebo žádný), budete muset v aplikaci nastavit atribut `android:fullBackupContent` na hodnotu true, false nebo prostředek XML. Všechno, co vložíte do `android:fullBackupContent`, zkopírujte prosím do značky metadat s názvem `com.microsoft.intune.mam.FullBackupContent`.

    **Příklady**: Pokud chcete, aby měla vaše aplikace úplné zálohy podle vašich vlastních pravidel v souboru XML, uveďte prosím v manifestu prostředek pod značkou metadat `com.microsoft.intune.mam.FullBackupContent`, například: 
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



### <a name="keyvalue-backup"></a>Zálohy páru klíč-hodnota

Tato možnost je dostupná pro všechna rozhraní API a používá `BackupAgent` a `BackupAgentHelper`. 

#### <a name="using-backupagenthelper"></a>Použití třídy BackupAgentHelper

`BackupAgentHelper` je mnohem jednodušší než implementace třídy `BackupAgent` , jak z hlediska nativních funkcí Androidu, tak z hlediska integrace MAM. `BackupAgentHelper` umožňuje vývojáři registrovat celé soubory a sdílet předvolby s třídou `FileBackupHelper` nebo `SharedPreferencesBackupHelper`, které se pak při vytvoření přidají do třídy `BackupAgentHelper` . 

#### <a name="using-backupagent"></a>Použití třídy BackupAgent

`BackupAgent` umožňuje explicitnější určení zálohovaných dat. Tahle možnost ale znamená, že nebudete moct využít architekturu zálohování Androidu.  Protože za implementaci do velké míry zodpovídáte, vyžaduje se pro zajištění odpovídající ochrany dat z MAM víc kroků. Většina práce bude na vás jako na vývojáři a integrace MAM se tak zapojí o něco víc. 

##### <a name="app-does-not-have-a-backup-agent"></a>Aplikace nemá agenta zálohování
  
Při nastavení `android:allowBackup =true`:

###### <a name="full-back-up-according-to-a-configuration-file"></a>Úplné zálohování podle konfiguračního souboru 

Do značky metadat `com.microsoft.intune.mam.FullBackupContent` v manifestu zadejte prostředek, třeba:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Do značky `<application>` přidejte následující atribut: `android:fullBackupContent="@xml/my_scheme"`, kde `my_scheme` je prostředek XML ve vaší aplikaci. 

###### <a name="full-back-dup-without-exclusions"></a>Úplné zálohování bez vyloučení 

Do manifestu zadejte značku jako třeba `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Do značky `<application>` přidejte následující atribut: `android:fullBackupContent="true"`.

##### <a name="app-has-a-backup-agent"></a>Aplikace má agenta zálohování

Postupujte podle doporučení v částech `BackupAgent` a `BackupAgentHelper` , jak je uvedeno výš. 

Zvažte možnost použití našeho agenta `MAMDefaultFullBackupAgent`, který poskytuje v systému Android M snadné zálohování. 

#### <a name="before-your-backup"></a>Před zálohováním

Před zahájením zálohování je nutné zkontrolovat, že soubory nebo datové vyrovnávací paměti, které plánujete zálohovat, mají skutečně povolené zálohování. Aby to bylo možné určit, nabízíme vám funkci `isBackupAllowed` v `MAMFileProtectionManager` a `MAMDataProtectionManager` . Pokud soubor nebo datová vyrovnávací paměť nemá povolené zálohování, pak byste neměli pokračovat v jejich použití v rámci zálohování.

Když v určitém okamžiku během zálohování chcete zálohovat identity pro soubory zkontrolované v kroku 1, musí volat `backupMAMFileIdentity(BackupDataOutput data, File … files)` se soubory, ze kterých plánujete extrahovat data. Tato akce automaticky vytvoří nové entity zálohování a zapíše je za vás do `BackupDataOutput` . Při obnovení se tyto entity automaticky využijí. 

### <a name="configure-azure-directory-authentication-library-adal"></a>Konfigurace knihovny ADAL (Azure Directory Authentication Library)  

Sada SDK spoléhá na knihovnu ADAL s jejími scénáři ověření a podmíněného spuštění, což vyžaduje, aby aplikace obsahovaly určitou část konfigurace Azure Active Directory. Hodnoty konfigurace se předávají SDK prostřednictvím metadat `AndroidManifest` . Když chcete konfigurovat svoji aplikaci a povolit správné ověření, přidejte do uzlu aplikace v `AndroidManifest`. Některé z těchto konfigurací jsou potřeba, jen když vaše aplikace používá ADAL pro ověřování obecně; v takovém případě budete potřebovat konkrétní hodnoty, které vaše aplikace používá k registraci v AAD. To slouží k zajištění, že koncovému uživateli se nezobrazí výzva k ověření dvakrát kvůli tomu, že AAD rozpozná hodnoty dvou samostatných registrací: jedné z aplikace a jedné ze sady SDK. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

Neočekává se, že by identifikátory GUID měly na začátku nebo na konci složené závorky.

#### <a name="common-adal-configurations"></a>Obvyklé konfigurace ADAL 

Dál jsou uvedené obvyklé konfigurace pro hodnoty vysvětlené dřív. 

##### <a name="app-does-not-integrate-adal"></a>Aplikace neintegruje ADAL.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* SkipBroker musí být nastavené na hodnotu true.

##### <a name="app-integrates-adal"></a>Aplikace integruje ADAL.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* ID klienta musí být nastavené na ID klienta aplikace.

* `NonBrokerRedirectURI` by mělo být nastavené na platný identifikátor URI přesměrování pro aplikaci.
    * Or `urn:ietf:wg:oauth:2.0:oob` nastavené jako platný identifikátor URI přesměrování AAD.

* SkipBroker musí být nastavené na hodnotu false (nebo chybět).

* AAD musí být nakonfigurovaná tak, aby přijímala identifikátor URI přesměrování zprostředkovatele.

##### <a name="app-integrates-adal-but-does-not-support-the-aad-authenticator-app"></a>Aplikace integruje ADAL, ale nepodporuje aplikaci AAD Authenticator.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* ID klienta musí být nastavené na ID klienta aplikace.

* `NonBrokerRedirectURI` musí být nastavené na platný identifikátor URI přesměrování pro aplikaci.

    * Or `urn:ietf:wg:oauth:2.0:oob` nastavené jako platný identifikátor URI přesměrování AAD.

### <a name="how-to-enable-logging-in-the-sdk"></a>Povolení protokolování v sadě SDK 

Protokolování se provádí pomocí architektury `java.util.logging` . Když chcete přijímat protokoly, nastavte globální protokolování, jak je popsané v [Technické příručce Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). V závislosti na aplikaci je obvykle `App.onCreate` nejlepší místo k zahájení protokolování. Všimněte si, že zprávy protokolu jsou klíčovány pomocí názvu třídy, což může být matoucí.

##<a name="multiidentity"></a>Více identit
###<a name="overview"></a>Přehled
Intune App SDK ve výchozím nastavení uplatní zásady na aplikaci jako celek. Možnost používat více identit je funkce MAM, kterou můžete zapnout, pokud chcete zásady uplatňovat na úrovni jednotlivých identit.  K tomu je od aplikace potřeba mnohem větší účast než u ostatních funkcí MAM. Pokud chce aplikace změnit aktivní identitu, musí to oznámit sadě App SDK a sada SDK zase oznámí aplikaci, kdy je změna identity nutná. V současné době je podporována jen jedna spravovaná identita. Jakmile uživatel zařízení nebo aplikaci zaregistruje, SDK tuto identitu použije a bude ji považovat za primární spravovanou. Ostatní uživatelé v aplikaci budou považováni za nespravované s nastavením zásad bez omezení. 

Pamatujte si, že identita je definována jednoduše jako řetězec. Identity rozlišují malá a velká písmena, ale žádosti odeslané sadě SDK je nemusí vrátit se stejnou velikostí písmen, s jakou byly nastaveny.

###<a name="enabling-multiidentity"></a>Povolení více identit
Ve výchozím nastavení se všechny aplikace považují za aplikace s jedinou identitou. Aplikace deklaruje, že dokáže rozpoznat více identit tím, že do manifestu Androidu umístí následující metadata.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###<a name="setting-the-identity"></a>Nastavení Identity

Vývojáři můžou identitu aplikace nastavit na těchto úrovních: 
1. Úroveň procesu 
2. Úroveň objektu Context (obecně aktivita) 
3. Úroveň vlákna 

Identita nastavená na úrovni vlákna nahrazuje identitu nastavenou na úrovni objektu Context, která nahrazuje identitu nastavenou na úrovni procesu. Identita nastavená u objektu Context se používá jenom v případě potřeby. Operace V/V souborů třeba nemají přidružený objekt Context. Následující metody u třídy MAMPolicyManager se dají použít k nastavení identity a načtení dříve nastavených hodnot identity.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Identitu aplikace můžete taky vymazat tím, že ji nastavíte na hodnotu null. Prázdný řetězec může sloužit jako identita, která nebude mít nikdy žádná omezení. Všechny metody nastavení identity vrátí zpět výsledné hodnoty přes ``` MAMIdentitySwitchResult```. Vrátit se můžou čtyři hodnoty:

1.**SUCCEEDED**: změna identity byla úspěšná 2.**NOT_ALLOWED**: změna identity není povolená. To se stane při pokusu o přepnutí na jiného podnikového uživatele ze stejné společnosti jako zaregistrovaný uživatel. Tato hodnota se vrátí taky při pokusu o nastavení identity (objektu Context) uživatelského rozhraní, když je v aktuálním vláknu nastavená jiná identita.
3.**CANCELLED**: uživatel zrušil změnu identity stisknutím tlačítka Zpět po zobrazení výzvy k zadání kódu PIN / ověřování.
4.**FAILED**: změna identity se z neznámého důvodu nezdařila.

V případě nastavení identity objektu Context je výsledek nahlášený asynchronně. Pokud je objektem Context aktivita, bude jasné, jestli byla změna identity úspěšná až po podmíněném spuštění, které může vyžadovat, aby uživatel zadal kód PIN nebo úplné podnikové přihlašovací údaje. Aby se dosáhlo tohoto výsledku, měla by aplikace implementovat ```MAMSetUIIdentityCallback```, i když je možné pro tento parametr předat hodnotu null.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

Namísto volání ``` MAMPolicyManager.setUIPolicyIdentity``` můžete identitu aktivity taky nastavit přímo díky metodě na MAMActivity. To můžete udělat touto metodou:

 ```public final void switchMAMIdentity(final String newIdentity);```

Aplikace můžou taky přepsat metodu na MAMActivity, aby mohly být informované o výsledku pokusů změnit identitu této aktivity 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Poznámka:** Přepnutí identity může vyžadovat nové vytvoření aktivity. Nové instanci aktivity se pak doručí zpětné volání ```onSwitchMAMIdentityComplete```.

###<a name="implicit-identity-changes"></a>Implicitní změny identity

Kromě schopnosti aplikace nastavit identitu se může změnit vlákno nebo identita objektu Context podle příchozího přenosu dat z jiné aplikace s podporou MAM. Pokud se třeba aktivita spustí ze záměru odeslaného jinou aplikací MAM, nastaví se identita aktivity podle účinné identity v jiné aplikaci v místě odeslání záměru.
U služeb se identita vlákna nastaví podobně po dobu volání onStart nebo onBind. Volání do třídy Binder vrácená z onBind taky dočasně nastaví identitu vlákna.
Volání do ```ContentProvider``` podobně nastaví identitu vlákna po dobu jejich trvání.
Kromě toho interakce uživatele s aktivitou může způsobit přepnutí implicitní identity.
Pokud třeba uživatel zruší výzvu k autorizaci během ```Resume```, dojde k implicitnímu přepnutí na prázdnou identitu.
Aplikace bude moct tyto změny rozpoznat a v určitých případech je může podle potřeby zakázat. Třídy ```MAMService``` a ```MAMContentProvider``` zveřejňují následující metodu, kterou můžou podtřídy přepsat:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
V případě ```MAMActivity``` je v metodě k dispozici další parametr: 
```
public void onMAMIdentitySwitchRequired(final String identity, 
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
```AppIdentitySwitchReason``` zachycuje zdroj implicitního přepnutí a může přijmout hodnoty ```CREATE```, ```RESUME_CANCELLED``` a ```NEW_INTENT```.  Důvod oznámení ```RESUME_CANCELLED``` se použije, když obnovení aktivity způsobí zobrazení uživatelského rozhraní pro zadání kódu PIN, ověřování nebo jiné dodržování předpisů a uživatel se pokusí toto uživatelské prostředí zrušit, obvykle použitím tlačítka Zpět.
```AppIdentitySwitchResultCallback``` vypadá takto:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
Kde ```AppIdentitySwitchResult``` je ```SUCCESS``` nebo ```FAILURE```. 

Metoda ```onMAMIdentitySwitchRequired``` se volá u všech implicitních změn identity s výjimkou změn provedených třídou Binder, která se vrátila z ```MAMService.onMAMBind```. Výchozí implementace ```onMAMIdentitySwitchRequired``` okamžitě volá ```reportIdentitySwitchResult(FAILURE)```, pokud je důvodem oznámení ```RESUME_CANCELLED```. Ve všech ostatních případech volá ```reportIdentitySwitchResult(SUCCESS)```. 

Neočekává se, že většina aplikací bude chtít blokovat nebo zpozdit přepnutí identity jinak. Pokud to ale aplikace chce udělat, musíte vzít v úvahu tyto body: *Když je zablokované přepnutí identity, bude výsledek stejný, jako kdyby nastavení sdílení ```Receive``` zakázalo příchozí přenos dat. *Pokud služba běží na hlavním vlákně, **musí** se ```reportIdentitySwitchResult``` volat synchronně, jinak přestane vlákno uživatelského rozhraní reagovat. 
*Při vytváření ```Activity``` se bude ```onMAMIdentitySwitchRequired``` volat před ```onMAMCreate```. Pokud musí aplikace zobrazit uživatelské rozhraní, aby určila, jestli se má povolit přepnutí identity, musí se toto uživatelské rozhraní zobrazit díky jiné aktivitě. *Pokud je potřeba přepnout na prázdnou identitu s odůvodněním, které odpovídá ```RESUME_CANCELLED```, musí aplikace upravit obnovenou aktivitu tak, aby zobrazovala data, která jsou konzistentní s tímto přepnutím identity.  Pokud to není možné, aplikace by měla přepnutí odmítnout a uživatel se znovu vyzve k dodržování zásad pro obnovení identity (třeba zobrazením obrazovky pro zadání kódu PIN). 

**Poznámka:** Aplikace s více identitami bude vždycky přijímat příchozí data z spravovaných i nespravovaných aplikací. Aplikace musí zacházet s daty ze spravovaných identit řízeně. Pokud požadovanou identitu spravuje ```(MAMPolicyManager.getIsIdentityManaged)```, ale aplikace nemůže tento účet používat (třeba kvůli tomu, že se v aplikaci musí nejdřív nastavit účty, například e-mailové účty), mělo by se přepnutí identity odmítnout.

##<a name="file-protection"></a>Ochrana souborů
Každý soubor bude mít identitu, která je s ním spojena v době vytvoření podle identity vláken a procesů. Tato identita se používá pro šifrování souborů i selektivní vymazání. Šifrovat se budou jenom soubory, jejichž identita má zásady vyžadující šifrování. Výchozí selektivní vymazání sadou SDK vymaže jenom soubory spojené s identitou, u které se požaduje vymazání. Aplikace může zadat dotaz na identitu souboru nebo ji změnit pomocí ```MAMFileProtectionManager```.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     * 
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     * 
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

**Poznámka:** označení identity souboru je citlivé na offline režim. Je potřeba vzít v úvahu tyto body.
* Pokud není nainstalovaný portál společnosti, soubory nemůžou mít označenou identitu. 
* Pokud je Portál společnosti nainstalovaný, ale aplikace nemá zásady, nedá se u souborů spolehlivě označit identita.
* Jakmile je označování identity souborů k dispozici, považují se všechny dříve vytvořené soubory za osobní (patří do identity s prázdným řetězcem), pokud nebyla aplikace dřív nainstalovaná jako spravovaná aplikace s jedinou identitou. V takovém případě se má zato, že soubory patří zaregistrovanému uživateli.

###<a name="data-protection"></a>Data Protection
Soubor se nedá označit jako soubor, který má více identit. Aplikace, které musí ukládat data různých uživatelů ve stejném souboru, to můžou provádět ručně díky funkcím, které poskytuje ```MAMDataProtectionManager```. Aplikace tak můžou šifrovat data a spojit je s určitým uživatelem. Šifrovaná data se hodí k ukládání na disk v souboru. Na data, která souvisejí s identitou, můžete zadávat dotazy a později je dešifrovat. 

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected 
 * input.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function 
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The 
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original 
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method. 
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the 
 * unprotected input.
     * 
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     * 
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input stream to get information on. Either this input 
 *            stream must have been returned by a previous call to 
     *            protect OR input.markSupported() must return true. 
 *            Otherwise it will be impossible to get protection info 
 *            without advancing the stream position. The stream must be 
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input bytes to get information on. These must be bytes 
 *            returned by a previous call to protect() or a copy of 
 *            such bytes.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
##<a name="content-providers"></a>Poskytovatelé obsahu
Pokud aplikace potenciálně nabízí jiná podniková data než ```ParcelFileDescriptor``` přes ```ContentProvider```, musí volat metodu ```MAMContentProvider``` ```isProvideContentAllowed(String)```, která předá obsahu hlavní název vlastníka (```UPN```) . Pokud tato funkce vrací hodnotu false, nemusí se obsah vrátit zpět volajícímu. Popisovače souborů, které se vrátí přes poskytovatele obsahu, se automaticky zpracují podle identity souboru.

##<a name="selective-wipe"></a>Selektivní vymazání
Pokud aplikace zaregistruje oznámení ```WIPE_USER_DATA```, nezíská výhodu sady SDK výchozího chování sady SDK při selektivním vymazání. U aplikací, které pracují s více identitami, to může být mnohem závažnější, protože výchozí selektivní vymazání MAM vymaže jenom soubory odpovídající identitě, kterou chcete vymazat. Pokud vytváříte aplikaci, která pracuje s více identitami, můžete si zaregistrovat oznámení ```WIPE_USER_AUXILIARY_DATA```, abyste mohli využívat výhody výchozího chování sady SDK při vymazání. Toto oznámení se odešle těsně předtím, než sada SDK zahájí výchozí selektivní vymazání. Aplikace by nikdy neměla zaregistrovat ```WIPE_USER_DATA``` i ```WIPE_USER_AUXILIARY_DATA```.

## <a name="known-platform-limitations"></a>Známá omezení platformy 

### <a name="file-size-limitations"></a>Omezení velikosti souborů 

V systému Android se může stát omezení formátu spustitelných souborů Dalvik problémem u rozsáhlých základů kódu, které běží bez ProGuard. Konkrétně může dojít k následujícím omezením: 

* Limit 65 kB pro pole

* Limit 65 kB pro metody

Při zahrnutí mnoha projektů každý balíček android:package získá kopii R, což značně zvýší počet polí při přidání knihoven. Následující doporučení mohou toto omezení zmírnit:
 
* Všechny projekty knihovny by měly sdílet stejný balíček android:package, kde je to možné. Protože je to čistě problém v době sestavení, nedojde k selhání v poli.   Kromě toho novější verze sady SDK pro Android předem zpracují soubory DEX, aby odstranily některé redundance. To snižuje vzdálenost od polí ještě víc.

* Použijte nejnovější dostupné nástroje sestavení sady SDK pro Android.

* Odeberte všechny nepotřebné a nepoužívané knihovny (například `android.support.v4`).

### <a name="policy-enforcement-limitations"></a>Omezení vynucení zásad

**Snímek obrazovky**: Sada SDK není schopná vynutit novou hodnotu nastavení snímku obrazovky v aktivitách, které již šly voláním Activity.onCreate. To může vést k časovému úseku, kdy aplikace je nakonfigurovaná tak, aby byly zakázané snímky obrazovky, ale snímky obrazovky jde pořád pořizovat.

**Použití překladačů obsahu*: Zásady přenosu nebo příjmu můžou blokovat nebo částečně blokovat použití překladače obsahu při přístupu k poskytovateli obsahu v jiné aplikaci. To způsobí, že metody ContentResolver vrátí hodnotu null nebo generují hodnotu selhání (například `openOutputStream` vyvolá při blokování výjimku `FileNotFoundException` ). Aplikace může určit, jestli selhání při zápisu dat pomocí překladače obsahu způsobila zásada (nebo by způsobila zásada), a to voláním:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exportované služby**: Soubor `AndroidManifest.xml` zahrnutý v sadě Intune App SDK obsahuje službu `MAMNotificationReceiverService`, která musí být exportovanou službou, aby umožňovala portálu společnosti odesílat oznámení do vylepšené aplikace. Služba zkontroluje volajícího, aby zajistila, že odesílat oznámení může jenom portál společnosti. 

## <a name="recommended-android-best-practices"></a>Doporučené osvědčené postupy pro Android 

Intune SDK udržuje kontrakt poskytovaný rozhraním Android API, i když podmínky selhání mohou být vyvolány častěji v důsledku vynucení zásad. Tyto doporučené postupy pro Android sníží pravděpodobnost selhání: 

* Funkce sady Android SDK, které můžou vrátit hodnotu null, mají nyní vyšší pravděpodobnost vrácení hodnoty null.  Chcete-li minimalizovat problémy, zajistěte, aby byly na správných místech kontroly hodnoty null.

* Vlastnosti, které jde zkontrolovat, musí být kontrolované pomocí příslušných rozhraní API sady SDK.

* Všechny odvozené funkce se musí provolat ke svým verzím v nadřazené třídě.

* Vyhněte se použití jakéhokoli rozhraní API nejednoznačný způsobem. Například `Activity.startActivityForResult/onActivityResult` bez kontroly requestCode způsobí neobvyklé chování.






<!--HONumber=Oct16_HO5-->


