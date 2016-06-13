---
# required metadata

title: Microsoft Intune App SDK pro Android – Příručka pro vývojáře | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune App SDK pro Android – Příručka pro vývojáře

> [!NOTE] Možná si budete chtít nejdřív přečíst [přehled sady Intune App SDK](intune-app-sdk.md), který vysvětluje aktuální funkce sady SDK a přípravu integrace na jednotlivých podporovaných platformách. 

# Co je v sadě SDK 

Intune App SDK pro Android je standardní knihovna pro Android, která nemá žádné externí závislosti. 
Sadu SDK tvoří:  

* **`Microsoft.Intune MAM.SDK.jar`**: Rozhraní nutná pro povolení MAM v aplikaci. Povolují taky interoperabilitu s aplikací Portál společnosti Microsoft Intune. Aplikace je musí uvádět jako odkazy na knihovnu pro Android.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: Rozhraní nutná pro povolení MAM v aplikacích, které využívají knihovnu podpory Android v4.  Aplikace, které vyžadují tuto podporu, musí na soubor jar odkazovat přímo. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: Rozhraní nutná pro povolení MAM v aplikacích, které využívají knihovnu podpory Android v7.   Aplikace, které vyžadují tuto podporu, musí na soubor jar odkazovat přímo.

* **Adresář prostředků**: Prostředky (jako jsou třeba řetězce), na které SDK spoléhá. 

* **`Microsoft.Intune.MAM.SDK.aar`**: Komponenty SDK kromě souborů jar Support.V4 a Support.V7. Tento soubor jde použít místo individuálních komponent, pokud systém sestavení podporuje soubory AAR.

* **`AndroidManifest.xml`**: Další vstupní body a požadavky knihoven. 

* **`THIRDPARTYNOTICES.TXT`**: Označení autorství, které uznává kód OSS nebo kód třetí strany, který se zkompiluje do vší aplikace. 

# Požadavky 

Intune App SDK je zkompilovaný projekt pro Android. Vzhledem k tomu je do značné míry lhostejné, kterou verzi Androidu aplikace využívá jako minimální nebo cílové verze API. SDK podporuje Android API 14 (Android 4.0+) až Android 24. 

# Jak Intune App SDK funguje 

Intune App SDK vyžaduje pro povolení zásad správy aplikací změny ve zdrojovém kódu aplikace. Udělají se tak, že se základní třídy Androidu nahradí ekvivalentními spravovanými třídami, které jsou v dokumentu označené předponou `MAM`. Třídy SDK se pohybují mezi základní třídou Androidu a vlastní odvozenou verzí této třídy v aplikaci.  Když jako příklad použijeme aktivitu, výsledná hierarchie dědičnosti bude vypadat takto: `Activity ->MAMActivity->AppSpecificActivity`.

Když chce `AppSpecificActivity` interagovat se svou nadřazenou třídou, třeba `super.onCreate())`, je supertřídou `MAMActivity`, i když je v hierarchii dědičnosti a nahrazuje několik metod. Aplikace pro Android mají jediný režim a mají přístup k celému systému prostřednictvím objektu Context.  Aplikace, které začlenily Intune App SDK, mají oproti tomu dva režimy. Aplikace i dál přistupuje k systému prostřednictvím objektu Context, ale v závislosti na použité základní aktivitě bude objekt Context poskytovaný Androidem nebo bude inteligentně multiplexovaný mezi omezeným zobrazením systému a objektem Context, který poskytuje Android.

Intune App SDK pro Android se při povolení zásad MAM spoléhá na přítomnost aplikace Portál společnosti v zařízení. Když aplikace Portál společnosti není dostupná, chování aplikace s podporou MAM se nezmění a bude fungovat stejně jako kterákoli jiná mobilní aplikace. Pokud je aplikace Portál společnosti nainstalovaná a má zásadu pro uživatele, vstupní body SDK se inicializují asynchronně. Inicializace se vyžaduje, jenom když je proces původně vytvořený Androidem. Při inicializaci se naváže připojení k aplikaci Portál společnosti a stáhnou se zásady omezení pro aplikaci.  

# Postup při integraci s Intune App SDK
 
Jak je uvedené výš, Intune App SDK vyžaduje pro povolení zásad správy aplikací změny ve zdrojovém kódu aplikace. Tady jsou kroky nutné k povolení MAM v aplikaci: 

## Náhrada tříd, metod a aktivit odpovídajícím ekvivalentem MAM (povinné) 

* Základní třídy Android se musí nahradit odpovídajícími ekvivalenty MAM. Uděláte to tak že vyhledáte všechny instance tříd uvedených v následující tabulce a nahradíte je ekvivalenty ze sady Intune App SDK.  

    | Třída Androidu | Náhrada ze sady Intune App SDK |
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
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *Náhrada třídy Binder třídou MAMBinder je nutná, jenom když se Binder negeneruje z rozhraní AIDL.

    **Microsoft.Intune.MAM.SDK.Suppnebot.v4.jar**:

    | Intune MAM třídy Androidu | Náhrada ze sady SDK |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppnebot.v7.jar**:

    |Třída Androidu | Náhrada ze sady Intune MAM SDK |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* Při použití vstupního bodu Androidu, který se přepsal ekvivalentem MAM, se musí použít alternativní verze životního cyklu vstupního bodu (kromě třídy `MAMApplication`).

    Třeba při odvozování od třídy `MAMActivity`musí aktivita místo přepsání `onCreate` a volání `super.onCreate`přepsat `onMAMCreate` a volat`uper.onMAMCreate`. To mimo jiné umožňuje v určitých případech omezení spuštění aktivity. 

# Povolení funkcí, které vyžadují účast aplikace 

Některé zásady nemůže sada SDK implementovat sama o sobě. K tomu, aby aplikace mohla kontrolovat své chování pro tyto funkce,  zveřejňujeme několik rozhraní API, které najdete v rozhraní `AppPolicy` uvedeném níž.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

## Povolení kontroly správce IT nad chováním při ukládání aplikace

Spousta aplikací implementuje funkce, které koncovému uživateli umožňují uložit soubory místně nebo do jiné služby. Intune App SDK umožňuje správcům IT nastavit ochranu před úniky dat tak, že použijí omezení zásad, která jsou vhodná pro jejich organizaci.  Jedna ze zásad, kterou správce může kontrolovat, je, jestli koncový uživatel může ukládat do osobního úložiště dat. To zahrnuje ukládání do místního umístění, na kartu SD nebo do služeb zálohování. K povolení této funkce je nutné zapojení aplikací. Pokud aplikace povoluje přímé ukládání do osobních nebo cloudových umístění, musíte implementací této funkce zajistit, aby správce IT měl kontrolu nad tím, jestli ukládání do umístění je nebo není povolené. Rozhraní API níž dá aplikaci vědět, jestli je na základě aktuálních zásad správce povolené ukládání do osobního úložiště. Aplikace pak může tyto zásady vynutit, protože si je vědoma, že jejím prostřednictvím jsou koncovým uživatelům dostupná osobní úložiště dat.  

K určení, jestli je tato zásada vynucená, aplikace použije toto volání: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Poznámka**: MAMComponents.get(AppPolicy.class) vždycky vrátí nenulovou zásadu aplikace, i když zařízení nebo aplikace nejsou spravované. 

## Povolení detekce, jestli se vyžaduje zásada PIN
 
 Existují další zásady, kdy si aplikace může přát zakázat některé ze svých funkcí, aby neduplikovala funkce Intune App SDK. Pokud aplikace třeba využívá vlastní PIN, můžete ho chtít zakázat, pokud je sada SDK nakonfigurovaná tak, aby od koncového uživatele vyžadovala zadání PIN. 

K určení, jestli je zásada PIN nakonfigurovaná tak, aby vyžadovala pravidelné zadání PIN, může aplikace využít toto volání: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## Registrace oznámení od SDK  

Intune App SDK umožňuje aplikaci, aby měla kontrolu nad chováním, když správce IT používá určité zásady, třeba zásadu vzdáleného vymazání. K tomu se musí registrovat oznámení od SDK, a to vytvořením třídy `MAMNotificationReceiver` a její registrací pomocí `MAMNotificationReceiverRegistry`. V  `App.onCreate`se uvede příjemce a typ oznámená, které chce příjemce dostávat, jak ukazuje tento příklad:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` bude jednoduše dostávat oznámení. Některá oznámení zpracovává přímo SDK, jiné vyžadují zapojení aplikace. Aplikace musí z oznámení vrátit true nebo false. True musí vracet vždycky, pokud neselže některá z akcí, kterou se v důsledku oznámení pokusí provést. Toto selhání se může hlásit službě Intune, jako třeba když aplikace udává, že se jí nepovedlo vymazat data. Blokování v `MAMNotificationReceiver.onReceive`je bezpečné. Zpětné volání se totiž nespouští ve vlákně UI. 

Dál je uvedené rozhraní MAMNotificationReceiver tak, jak je definované v SDK: 

    /**
     * The SDK is signaling that a MAM event has occurred. 
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

Následující oznámení se odesílají do aplikace a některá z nich můžou vyžadovat zapojení aplikace: 

* **Oznámení `WIPE_USER_DATA`**: Toto oznámení se posílá ve třídě `MAMUserNotification`. Po přijetí tohoto oznámení by aplikace měla odstranit všechna data přidružená k identitě předané pomocí `MAMUserNotification`. Toto oznámení se momentálně odesílá při rušení registrace služby Intune. Během procesu registrace se obvykle zadává primární uživatelské jméno. Když si zaregistrujete toto oznámení, aplikace musí zajistit, že se odstranila všechna uživatelská data. Pokud si ho nezaregistrujete, použije se výchozí selektivní mazání. 

* **Oznámení `WIPE_USER_AUXILIARY_DATA`**: Aplikace si můžou zaregistrovat toto oznámení, když chtějí, aby sada Intune App SDK provedla výchozí vymazání, ale chtějí při tomto vymazání odebrat ještě některá pomocná data.  

* **Oznámení `REFRESH_POLICY`**: Toto oznámení se odesílá ve třídě MAMNotification bez jakýchkoli dalších informací. Při příjmu tohoto oznámení se všechny zásady v mezipaměti musí přestat považovat za zneplatněné, a proto by se mělo zjistit, o jakou zásadu jde. Tuto operaci obecně provádí SDK, ale pokud se zásada používá jakýmkoli trvalým způsobem, měla by ji zpracovat aplikace. 

## Čekající záměry a metody 

Po odvození některého ze vstupních bodů MAM můžete objekt Context použít ke spuštění aktivit běžným způsobem s využitím `PackageManager`atd.  Výjimkou z tohoto pravidla jsou třídy  `PendingIntents` . Při volání těchto tříd je nutné změnit název třídy. Třeba místo `PendingIntent.get*`, se musí použít `MAMPendingIntents.get*`. 

V některých případech je metoda dostupná ve třídě Androidu označená v náhradní třídě MAM jako finální. Náhradní třída MAM pak poskytuje metodu s podobným názvem (obecně s příponou MAM), která by se měla přepsat místo toho. Třeba místo `ContentProvider.query`by se mělo přepsat `MAMContentProvider.queryMAM`. Kompilátor Javy by měl vynutit finální omezení, která zabrání náhodnému přepsání původní metody místo jejího ekvivalentu MAM. 

# Ochrana dat zálohy 

Od verze Android Marshmallow (API 23) má Android dva způsoby, kterými aplikace můžou zálohovat svá data. Tyto možnosti můžete ve své aplikaci využít, ale vyžadují různé kroky, které zajišťují, aby se ochrana dat MAM použila správně. Stručný přehled akcí požadovaných pro správné chování ochrany dat najdete v tabulce níž.  Další informace o zálohování v Androidu najdete v [příručce zálohování dat pro vývojáře v Androidu](http://developer.android.com/guide/topics/data/backup.html.). 

## Automatické úplné zálohování

V Androidu M začal Android nabízet aplikacím automatické úplné zálohování bez ohledu na cílové rozhraní API při spuštění v zařízení s Androidem M. Pokud atribut `android:allowBackup` nemá hodnotu false, aplikace získá plné nefiltrované zálohy. To ale představuje riziko úniku dat, a proto SDK vyžaduje změny uvedené v tabulce níž, které zajistí použití ochrany dat.  K zajištění ochrany dat zákazníků je důležité dodržovat pokyny uvedené níž.  Pokud nastavíte `android:allowBackup=false` , aplikace nebude nikdy zařazená do fronty pro zálohování operačního systému a pro MAM nejsou žádné další akce, protože nebude žádná záloha.
 
 ## Zálohy „klíč/hodnota“

Tato možnost je dostupná pro všechna rozhraní API a používá `BackupAgent` a `BackupAgentHelper`. 

### Použití třídy BackupAgentHelper

`BackupAgentHelper` je mnohem jednodušší než implementace třídy `BackupAgent`, jak z hlediska nativních funkcí Androidu, tak z hlediska integrace MAM. `BackupAgentHelper` umožňuje vývojáři registrovat celé soubory a sdílet předvolby s třídou `FileBackupHelper` nebo `SharedPreferencesBackupHelper`, které se pak při vytvoření přidají do třídy `BackupAgentHelper`. 

### Použití třídy BackupAgent

`BackupAgent` umožňuje explicitnější určení zálohovaných dat. Tahle možnost ale znamená, že nebudete moct využít architekturu zálohování Androidu.  Protože za implementaci do velké míry zodpovídáte, vyžaduje se pro zajištění odpovídající ochrany dat z MAM víc kroků. Většina práce bude na vás jako na vývojáři a integrace MAM se tak zapojí o něco víc. 

#### Aplikace nemá agenta zálohování
  
Při nastavení `Android:allowbBackup =true`:

##### Úplné zálohování podle konfiguračního souboru 

Do značky metadat `com.microsoft.intune.mam.FullBackupContent` v manifestu zadejte prostředek, třeba
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Do značky `<application>` přidejte následující atribut: `android:fullBackupContent="@xml/my_scheme"`, kde `my_scheme` je prostředek XML ve vaší aplikaci. 

##### Úplné zálohování bez vyloučení 

Do manifestu zadejte značku jako třeba `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Do značky `<application>` přidejte následující atribut: `android:fullBackupContent="true"`.

#### Aplikace má agenta zálohování

Postupujte podle doporučení v částech `BackupAgent` a `BackupAgentHelper` , jak je uvedeno výš. 

Zvažte možnost použití našeho agenta `MAMDefaultFullBackupAgent`, který poskytuje v systému Android M snadné zálohování. 

### Před zálohováním

Před zahájením zálohování je nutné zkontrolovat, že soubory nebo datové vyrovnávací paměti, které plánujete zálohovat, mají skutečně povolené zálohování. Aby to bylo možné určit, nabízíme vám funkci `isBackupAllowed` v `MAMFileProtectionManager` a `MAMDataProtectionManager` . Pokud soubor nebo datová vyrovnávací paměť nemá povolené zálohování, pak byste neměli pokračovat v jejich použití v rámci zálohování.

Když v určitém okamžiku během zálohování chcete zálohovat identity pro soubory zkontrolované v kroku 1, musí volat `backupMAMFileIdentity(BackupDataOutput data, File … files)` se soubory, ze kterých plánujete extrahovat data. Tato akce automaticky vytvoří nové entity zálohování a zapíše je za vás do `BackupDataOutput` . Při obnovení se tyto entity automaticky využijí. 

## Konfigurace knihovny ADAL (Azure Directory Authentication Library)  

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

### Obvyklé konfigurace ADAL 

Dál jsou uvedené obvyklé konfigurace pro hodnoty vysvětlené dřív. 

#### Aplikace neintegruje ADAL.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* SkipBroker musí být nastavené na hodnotu true.

#### Aplikace integruje ADAL.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* ID klienta musí být nastavené na ID klienta aplikace.

* `NonBrokerRedirectURI` by mělo být nastavené na platný identifikátor URI přesměrování pro aplikaci.
    * Or `urn:ietf:wg:oauth:2.0:oob` nastavené jako platný identifikátor URI přesměrování AAD.

* SkipBroker musí být nastavené na hodnotu false (nebo chybět).

* AAD musí být nakonfigurovaná tak, aby přijímala identifikátor URI přesměrování zprostředkovatele.

#### Aplikace integruje ADAL, ale nepodporuje aplikaci AAD Authenticator.

* Autorita musí být nastavená na požadované prostředí, kde byly nakonfigurované účty AAD.

* ID klienta musí být nastavené na ID klienta aplikace.

* `NonBrokerRedirectURI` musí být nastavené na platný identifikátor URI přesměrování pro aplikaci.

    * Or `urn:ietf:wg:oauth:2.0:oob` nastavené jako platný identifikátor URI přesměrování AAD.

## Povolení protokolování v sadě SDK 

Protokolování se provádí pomocí architektury `java.util.logging` . Když chcete přijímat protokoly, nastavte globální protokolování, jak je popsané v [Technické příručce Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). V závislosti na aplikaci je obvykle `App.onCreate` nejlepší místo k zahájení protokolování. Všimněte si, že zprávy protokolu jsou klíčovány pomocí názvu třídy, což může být matoucí.

# Známá omezení platformy 

## Omezení velikosti souborů 

V systému Android se může stát omezení formátu spustitelných souborů Dalvik problémem u rozsáhlých základů kódu, které běží bez ProGuard. Konkrétně může dojít k následujícím omezením: 

* Limit 65 kB pro pole

* Limit 65 kB pro metody

Při zahrnutí mnoha projektů každý balíček android:package získá kopii R, což značně zvýší počet polí při přidání knihoven. Následující doporučení mohou toto omezení zmírnit:
 
* Všechny projekty knihovny by měly sdílet stejný balíček android:package, kde je to možné. Protože je to čistě problém v době sestavení, nedojde k selhání v poli.   Kromě toho novější verze sady SDK pro Android předem zpracují soubory DEX, aby odstranily některé redundance. To snižuje vzdálenost od polí ještě víc.

* Použijte nejnovější dostupné nástroje sestavení sady SDK pro Android.

* Odeberte všechny nepotřebné a nepoužívané knihovny (například `android.support.v4`).

## Omezení vynucení zásad

**Snímek obrazovky**: Sada SDK není schopná vynutit novou hodnotu nastavení snímku obrazovky v aktivitách, které již šly voláním Activity.onCreate. To může vést k časovému úseku, kdy aplikace je nakonfigurovaná tak, aby byly zakázané snímky obrazovky, ale snímky obrazovky jde pořád pořizovat.

**Použití překladačů obsahu:* Zásady přenosu nebo příjmu můžou blokovat nebo částečně blokovat použití překladače obsahu při přístupu k poskytovateli obsahu v jiné aplikaci. To způsobí, že metody ContentResolver vrátí hodnotu null nebo generují hodnotu selhání (například `openOutputStream` vyvolá při blokování výjimku `FileNotFoundException` ). Aplikace může určit, jestli selhání při zápisu dat pomocí překladače obsahu způsobila zásada (nebo by způsobila zásada), a to voláním:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exportované služby**: Soubor `AndroidManifest.xml` zahrnutý v sadě Intune App SDK obsahuje službu `MAMNotificationReceiverService`, která musí být exportovanou službou, aby umožňovala portálu společnosti odesílat oznámení do vylepšené aplikace. Služba zkontroluje volajícího, aby zajistila, že odesílat oznámení může jenom portál společnosti. 

# Doporučené osvědčené postupy pro Android 

Intune SDK udržuje kontrakt poskytovaný rozhraním Android API, i když podmínky selhání mohou být vyvolány častěji v důsledku vynucení zásad. Tyto doporučené postupy pro Android sníží pravděpodobnost selhání: 

* Funkce sady Android SDK, které můžou vrátit hodnotu null, mají nyní vyšší pravděpodobnost vrácení hodnoty null.  Chcete-li minimalizovat problémy, zajistěte, aby byly na správných místech kontroly hodnoty null.

* Vlastnosti, které jde zkontrolovat, musí být kontrolované pomocí příslušných rozhraní API sady SDK.

* Všechny odvozené funkce se musí provolat ke svým verzím v nadřazené třídě.

* Vyhněte se použití jakéhokoli rozhraní API nejednoznačný způsobem. Například `Activity.startActivityForResult/onActivityResult` bez kontroly requestCode způsobí neobvyklé chování.


<!--HONumber=May16_HO2-->


