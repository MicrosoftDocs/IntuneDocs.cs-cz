---
title: Microsoft Intune App SDK pro Android – příručka pro vývojáře
description: Sada Microsoft Intune App SDK pro Android umožňuje začlenit správu mobilních aplikací (MAM) Intune do vaší aplikace pro Android.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4316c155645ad8e956cfd89c448da688ac133b3
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314561"
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Microsoft Intune App SDK pro Android – příručka pro vývojáře

> [!NOTE]
> Možná si budete chtít nejdřív přečíst [Přehled sady Intune App SDK](app-sdk.md), který pokrývá aktuální funkce sady SDK, a popisuje, jak připravit integraci na jednotlivých podporovaných platformách.

Sada Microsoft Intune App SDK pro Android umožňuje začlenit do vaší nativní aplikace pro Android zásady ochrany aplikací Intune (označované také jako zásady **App** nebo mam). Aplikace spravovaná v Intune je taková, která je integrovaná se sadou Intune App SDK. Správci Intune můžou zásady ochrany aplikací snadno nasadit do vaší aplikace spravované přes Intune, když Intune tuto aplikaci aktivně spravuje.


## <a name="whats-in-the-sdk"></a>Co je v sadě SDK

Sada Intune App SDK se skládá z následujících souborů:

* **Microsoft. Intune. mam. SDK. AAR**: komponenty sady SDK s výjimkou souborů JAR knihovny podpory.
* **Microsoft. Intune. mam. SDK. support. v4. jar**: třídy potřebné k povolení mam v aplikacích, které využívají knihovnu podpory Android v4.
* **Microsoft. Intune. mam. SDK. support. v7. jar**: třídy, které jsou nezbytné pro povolení mam v aplikacích, které používají knihovnu podpory Android v7.
* **Microsoft. Intune. mam. SDK. support. v17. jar**: třídy, které jsou nezbytné pro povolení mam v aplikacích, které používají knihovnu podpory Android v17. 
* **Microsoft. Intune. mam. SDK. support. text. jar**: třídy, které jsou nezbytné pro povolení mam v aplikacích, které používají třídy knihovny podpory Androidu v balíčku `android.support.text`.
* **Microsoft. Intune. mam. SDK. DownlevelStubs. AAR**: Tento AAR obsahuje zástupné procedury pro systémové třídy Androidu, které jsou k dispozici pouze na novějších zařízeních, ale na které odkazují metody v `MAMActivity`. Novější zařízení budou tyto zástupné třídy ignorovat. Tento AAR je nutný jenom v případě, že vaše aplikace provádí reflexi pro třídy odvozené od `MAMActivity` a většina aplikací je nepotřebuje zahrnout. AAR obsahuje pravidla ProGuard pro vyloučení všech jeho tříd.
* **com. Microsoft. Intune. mam. Build. jar**: modul plug-in Gradle, který [pomáhá při integraci sady SDK](#build-tooling).
* Protokol **změn. txt**: poskytuje záznam změn provedených v každé verzi sady SDK.
* **THIRDPARTYNOTICES. TXT**: označení přizpůsobené, které potvrdí kód třetí strany nebo OSS, který se zkompiluje do vaší aplikace.

## <a name="requirements"></a>Požadavky

### <a name="android-versions"></a>Verze Androidu
Sada SDK podporuje Android API 19 (Android 4.4 +) prostřednictvím rozhraní Android API 28 (Android 9,0).

### <a name="company-portal-app"></a>Aplikace Portál společnosti
Sada Intune App SDK pro Android se spoléhá na přítomnost [portál společnosti](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) aplikace na zařízení, aby se povolily zásady ochrany aplikací. Portál společnosti načte zásady ochrany aplikací ze služby Intune. Po inicializaci aplikace načte zásadu a kód pro vymáhání této zásady z Portál společnosti.

> [!NOTE]
> Když aplikace Portál společnosti není na zařízení, bude se aplikace spravovaná v Intune chovat stejně jako normální aplikace, která nepodporuje zásady ochrany aplikací Intune.

V případě ochrany aplikací bez registrace zařízení _**není nutné,**_ aby uživatel zaregistroval zařízení pomocí aplikace Portál společnosti.

## <a name="sdk-integration"></a>Integrace sady SDK

### <a name="sample-app"></a>Ukázková aplikace
Příklad, jak integrovat se sadou Intune App SDK správně, je k dispozici na [GitHubu](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App). V tomto příkladu se používá [modul plug-in sestavení Gradle](#gradle-build-plugin).

### <a name="referencing-intune-app-libraries"></a>Odkazování na knihovny aplikací Intune

Intune App SDK je standardní knihovna pro Android, která nemá žádné externí závislosti. **Microsoft. Intune. mam. SDK. AAR** obsahuje rozhraní nutná pro povolení zásad ochrany aplikací a kód potřebný pro spolupráci s aplikací Microsoft Intune portál společnosti.

**Microsoft. Intune. mam. SDK. AAR** musí být zadaný jako odkaz na knihovnu pro Android. Provedete to tak, že otevřete projekt aplikace v Android Studio a přejdete na **soubor > nový > nový modul** a vyberete **importovat. JAR/. Balíček AAR** Pak vyberte náš archivní balíček pro Android Microsoft. Intune. MAM. SDK. AAR a vytvořte modul pro. AAR. Klikněte pravým tlačítkem myši na modul nebo moduly, které obsahují kód aplikace, a přejděte na **nastavení modulu** > **karta závislosti** >  **+ ikona**@no__t-**5 > vyberte** modul AAR sady mam SDK, který jste právě vytvořili > **OK**. Tím se zajistí, že se váš modul zkompiluje se sadou MAM SDK při sestavování projektu.

Kromě toho knihovny **Microsoft. Intune. mam. SDK. support. xxx. jar** obsahují varianty odpovídajících knihoven `android.support.XXX` v Intune. Nejsou integrovány do Microsoft. Intune. MAM. SDK. AAR pro případ, že aplikace nemusí záviset na knihovnách podpory.

#### <a name="proguard"></a>ProGuard

Pokud se jako krok sestavení používá [ProGuard](http://proguard.sourceforge.net/) (nebo jakýkoliv jiný mechanizmus zmenšení/dezahrnutí), sada SDK obsahuje další pravidla konfigurace, která musí být zahrnutá. Při zahrnutí. AAR v sestavení jsou naše pravidla automaticky integrována do kroku ProGuard a jsou zachovány potřebné soubory třídy.

Knihovny Azure Active Directory Authentication Library (ADAL) mohou mít vlastní omezení ProGuard. Pokud vaše aplikace integruje ADAL, musíte postupovat podle těchto omezení v dokumentaci k ADAL.

### <a name="policy-enforcement"></a>Vynucování zásad
Intune App SDK je knihovna pro Android, která umožňuje vaší aplikaci podporovat a účastnit se vynucování zásad Intune. 

Většina zásad se vynutila automaticky, ale některé zásady vyžadují, [aby se vaše aplikace vynutila explicitní účastí](#enable-features-that-require-app-participation).
Bez ohledu na to, jestli provedete integraci se zdrojem nebo pomocí nástrojů sestavení pro integraci, se musí pro tyto zásady, které vyžadují explicitní účast, kódovat.

Pro zásady, které se automaticky vynutily, se vyžadují, aby se aplikace nahradily dědění z několika základních tříd Androidu s děděním z ekvivalentů MAM a obdobně nahrazují volání na určité třídy služby systému Android s voláními ekvivalentů MAM. Konkrétní požadované náhrady jsou popsané [níže](#class-and-method-replacements) a je možné je ručně provést pomocí integrace zdrojů nebo provádět automaticky prostřednictvím nástrojů sestavení.

### <a name="build-tooling"></a>Nástroje sestavení
Sada SDK poskytuje nástroje pro sestavení (modul plug-in pro Gradle buildy a nástroj příkazového řádku pro sestavení bez Gradle), které provádějí MAM ekvivalentní náhrady automaticky. Tyto nástroje transformují soubory tříd generované kompilátorem Java a nemění původní zdrojový kód.

Nástroje provádějí pouze [přímé náhrady](#class-and-method-replacements) . Neprovádí žádné složitější integrace sady SDK, jako jsou například [zásady Save-as](#enable-features-that-require-app-participation), [multi-identity](#multi-identity-optional), [Registrace aplikací](#app-protection-policy-without-device-enrollment), [souboru AndroidManifest úpravy](#manifest-replacements) nebo [Konfigurace ADAL](#configure-azure-active-directory-authentication-library-adal) , takže je nutné je dokončit před aplikace je plně Intune zapnutá. Pečlivě si přečtěte část této dokumentace, kde najdete body integrace, které jsou relevantní pro vaši aplikaci.

> [!NOTE]
> Je možné spouštět nástroje proti projektu, který již provedl částečnou nebo úplnou integraci zdrojů sady MAM SDK prostřednictvím ručních nahrazení. Projekt musí dál seznamovat sadu MAM SDK jako závislost.

### <a name="gradle-build-plugin"></a>Modul plug-in sestavení Gradle
Pokud se vaše aplikace sestaví pomocí Gradle, přejděte k [části integrace s nástrojem příkazového řádku](#command-line-build-tool). 

Modul plug-in sady App SDK je distribuován jako součást sady SDK jako **GradlePlugin/com. Microsoft. Intune. mam. Build. jar**. Aby Gradle mohl modul plug-in najít, musí být přidán do třídy classpath buildscript. Modul plug-in závisí na [Javassist](https://jboss-javassist.github.io/javassist/), který musí být také přidán. Pokud je chcete přidat do cesty k cestě, přidejte následující do kořenového `build.gradle`.

```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath "org.javassist:javassist:3.22.0-GA"
        classpath files("$PATH_TO_MAM_SDK/GradlePlugin/com.microsoft.intune.mam.build.jar")
    }
}
```

Pak v souboru `build.gradle` pro projekt APK stačí použít modul plug-in jako
```groovy
apply plugin: 'com.microsoft.intune.mam'
```

Ve výchozím nastavení bude modul plug-in fungovat **jenom** u závislostí `project`.
Kompilace testu neovlivnila. Je možné zadat konfiguraci seznamu.
*  Projekty, které mají být vyloučeny
*  [Externí závislosti, které se mají zahrnout](#usage-of-includeexternallibraries) 
*  Konkrétní třídy, které se mají vyloučit ze zpracování
*  Varianty, které mají být vyloučeny ze zpracování. Ty můžou odkazovat buď na úplný název varianty, nebo na jeden charakter. Například
     * Pokud má vaše aplikace typy sestavení `debug` a `release` s charaktery {`savory`, `sweet`} a {`vanilla`, `chocolate`}, můžete zadat
     * `savory` pro vyloučení všech variant s charakterem Savory nebo `savoryVanillaRelease` pro vyloučení pouze takové přesné varianty.

#### <a name="example-partial-buildgradle"></a>Příklad částečného sestavení. Gradle

```groovy

apply plugin: 'com.microsoft.intune.mam'

dependencies {
    implementation project(':product:FooLib')
    implementation project(':product:foo-project')
    implementation fileTree(dir: "libs", include: ["bar.jar"])
    implementation fileTree(dir: "libs", include: ["zap.jar"])
    implementation "com.contoso.foo:zap-artifact:1.0.0"
    implementation "com.microsoft.bar:baz:1.0.0"
    implementation "com.microsoft.qux:foo:2.0"

    // Include the MAM SDK
    implementation files("$PATH_TO_MAM_SDK/Microsoft.Intune.MAM.SDK.aar")
}
intunemam {
    excludeProjects = [':product:FooLib']
    includeExternalLibraries = ['bar.jar', "com.contoso.foo:zap-artifact", "com.microsoft.*", "!com.microsoft.qux*"]
    excludeClasses = ['com.contoso.SplashActivity']
    excludeVariants=['savory']
}
```

To má následující důsledky:
* `:product:FooLib` se nepřepíše, protože je zahrnutý v `excludeProjects`.
* přepsána `:product:foo-project` s výjimkou `com.contoso.SplashActivity`, která je vynechána, protože je v `excludeClasses`
* přepsána `bar.jar`, protože je obsažena v `includeExternalLibraries`
* `zap.jar` není přepsán, **protože se** nejedná o projekt a není zahrnutý v `includeExternalLibraries`.
* `com.contoso.foo:zap-artifact:1.0.0` se přepíše, protože je zahrnutý v `includeExternalLibraries`.
* přepsána `com.microsoft.bar:baz:1.0.0`, protože je obsažena v `includeExternalLibraries` prostřednictvím zástupného znaku (`com.microsoft.*`).
* `com.microsoft.qux:foo:2.0` není přepsán, přestože odpovídá stejnému zástupnému znaku jako předchozí položka, protože je explicitně vyloučena pomocí vzoru negace.

#### <a name="usage-of-includeexternallibraries"></a>Využití includeExternalLibraries

Vzhledem k tomu, že modul plug-in funguje pouze na závislostech projektu (obvykle poskytované funkcí `project()`), jsou ve výchozím nastavení všechny závislosti zadané `fileTree(...)` nebo získané z Maven nebo jiných zdrojů balíčků (např. "`com.contoso.bar:baz:1.2.0`") musí být poskytnuty vlastnosti `includeExternalLibraries`, pokud MAM zpracování je nutné v závislosti na kritériích, která jsou vysvětlena níže. Jsou podporovány zástupné znaky ("*"). Položka začínající `!` je negace a lze ji použít k vyloučení knihoven, které by jinak zahrnoval zástupný znak.

Když zadáváte externí závislosti se zápisem artefaktů, doporučuje se vynechat součást verze v hodnotě `includeExternalLibraries`. Pokud tuto verzi zahrnete, musí se jednat o přesnou verzi. Specifikace dynamické verze (např. `1.+`) nejsou podporovány.

Obecné pravidlo, které byste měli použít k určení, jestli je potřeba zahrnout knihovny do `includeExternalLibraries` vychází ze dvou otázek:
1. Má knihovna v ní třídy, pro které existují ekvivalenty MAM? Příklady: `Activity`, `Fragment`, `ContentProvider`, `Service` atd.
2. Pokud ano, používá vaše aplikace tyto třídy?

Pokud odpovíte Ano na obě tyto otázky, musíte tuto knihovnu zahrnout do `includeExternalLibraries`. 

| Scénář | Měl by obsahovat? |
|--|--|
| Do své aplikace zahrnete knihovnu prohlížeče PDF a při pokusu uživatele o zobrazení souborů PDF použijete v aplikaci prohlížeč `Activity`. | Ano |
| Do své aplikace zahrnete knihovnu HTTP pro lepší výkon webu. | Ne |
| Zahrnete knihovnu jako reakci nativní, která obsahuje třídy odvozené od `Activity`, `Application` a `Fragment` a použijete nebo dále odvodíte tyto třídy v aplikaci. | Ano |
| Zahrnete knihovnu jako s přístupnou reakce, která obsahuje třídy odvozené od `Activity`, `Application` a `Fragment`, ale používáte pouze statické pomocné pomůcky nebo třídy nástrojů. | Ne |
| Zahrnete knihovnu, která obsahuje třídy zobrazení odvozené od `TextView` a použijete nebo dále odvodíte tyto třídy v aplikaci. | Ano |

#### <a name="reporting"></a>Generování sestav
Modul plug-in sestavení může vygenerovat sestavu HTML změn, které dělá. Chcete-li vyžádat generování této sestavy, zadejte do konfiguračního bloku `intunemam` `report = true`. Při vygenerování bude sestava zapsána do `outputs/logs` v adresáři sestavení.

```groovy
intunemam {
    report = true
}
```

#### <a name="verification"></a>Ověření
Modul plug-in sestavení může spustit dodatečné ověření a vyhledat možné chyby ve zpracování tříd. Pokud to chcete vyžádat, zadejte `verify = true` v konfiguračním bloku `intunemam`. Všimněte si, že tato akce může přidat několik sekund do doby trvání úlohy modulu plug-in.

```groovy
intunemam {
    verify = true
}
```

#### <a name="incremental-builds"></a>Přírůstková sestavení
Pokud chcete povolit podporu pro sestavení přírůstkově, zadejte v konfiguračním bloku `intunemam` `incremental = true`.  Toto je experimentální funkce zaměřená na zvýšení výkonu sestavení tím, že zpracovává pouze vstupní soubory, které se změnily.  Výchozí konfigurace je `false`.

```groovy
intunemam {
    incremental = true
}
```

#### <a name="dependencies"></a>Závislosti

Modul plug-in Gradle má závislost na [Javassist](https://jboss-javassist.github.io/javassist/), která musí být dostupná pro rozlišení závislosti Gradle (jak je popsáno výše). Javassist se používá výhradně v době sestavení při spuštění modulu plug-in. Do vaší aplikace se nepřidá žádný kód Javassist.

> [!NOTE] 
> Musíte používat verzi 3,0 nebo novější modul plug-in Gradle pro Android a Gradle 4,1 nebo novější.

### <a name="command-line-build-tool"></a>Nástroj pro sestavení příkazového řádku
Pokud vaše sestavení používá Gradle, přejděte k [Další části](#class-and-method-replacements).

Nástroj pro sestavení příkazového řádku je k dispozici ve složce `BuildTool` vyřazení sady SDK. Provádí stejnou funkci jako modul plug-in Gradle, který je popsaný výše, ale je možné ho integrovat do vlastních systémů sestavení nebo mimo Gradle. Jak je obecnější, je složitější ji vyvolat, takže modul plug-in Gradle by měl být použit, pokud je to možné.

#### <a name="using-the-command-line-tool"></a>Použití nástroje příkazového řádku

Nástroj příkazového řádku lze vyvolat pomocí dodaných pomocných skriptů umístěných v adresáři `BuildTool\bin`.

Nástroj očekává následující parametry.

| Parametr | Popis |
| -- | -- |
| `--input` | Středníky oddělený seznam souborů JAR a adresářů souborů třídy, které se mají upravit To by mělo zahrnovat všechny jar/adresáře, které máte v úmyslu přepsat. |
| `--output` | Středníkem oddělený seznam souborů a adresářů jar, do kterých se ukládají změněné třídy. Pro každou vstupní položku by měla existovat jedna výstupní položka a měla by být uvedena v pořadí. |
| `--classpath` | Cesta k sestavení Tato třída může obsahovat adresáře jar i třídy. |
| `--excludeClasses`| Seznam oddělený středníky obsahující názvy tříd, které mají být vyloučeny z přepisu. |

Všechny parametry jsou povinné s výjimkou `--excludeClasses`, což je volitelné.

> [!NOTE]
> V případě systémů se systémem UNIX je středníkem příkazu oddělovač příkazů. Aby se prostředí nemohlo rozdělit, ujistěte se, že jste každý středník nahnuli znakem "\'", nebo zabalte úplný parametr v uvozovkách.

#### <a name="example-command-line-tool-invocation"></a>Příklad vyvolání nástroje příkazového řádku

``` batch
> BuildTool\bin\BuildTool.bat --input build\product-foo-project;libs\bar.jar --output mam-build\product-foo-project;mam-build\libs\bar.jar --classpath build\zap.jar;libs\Microsoft.Intune.MAM.SDK\classes.jar;%ANDROID_SDK_ROOT%\platforms\android-27\android.jar --excludeClasses com.contoso.SplashActivity
```

To má následující důsledky:

* `mam-build\product-foo-project` se přepíše adresář `product-foo-project`.
* `bar.jar` se přepíše do `mam-build\libs\bar.jar`.
* `zap.jar` není přepsán, **protože je uvedena** pouze v `--classpath`.
* Třída @no__t- **0 není** přepsána i v případě, že je v `--input`.

> [!NOTE] 
> Nástroj sestavení v současné době nepodporuje soubory AAR. Pokud systém sestavení již neextrahuje `classes.jar` při práci se soubory AAR, budete je muset provést před vyvoláním nástroje pro sestavení.


## <a name="class-and-method-replacements"></a>Nahrazení tříd a metod

Základní třídy Android se musí nahradit odpovídajícími ekvivalenty MAM, aby bylo možné povolit správu Intune. Třídy SDK živé mezi základní třídou Androidu a vlastní odvozenou verzí této třídy v aplikaci. Aktivita aplikace může například končit hierarchií dědičnosti, která vypadá takto: `Activity` @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4. Filtry vrstvy MAM zajišťují volání systémových operací, aby bylo možné bezproblémově poskytovat aplikaci se spravovaným pohledem na světě.

Kromě základních tříd můžou některé třídy, které vaše aplikace používá, bez odvození (například `MediaPlayer`) mít také požadované MAM ekvivalenty a [některá volání metod musí být také nahrazena](#wrapped-system-services). Přesné podrobnosti jsou uvedeny níže.

> [!NOTE] 
> Pokud je vaše aplikace integrována s [nástroji pro sestavení](#build-tooling)sady SDK, provede se automatické nahrazení následující třídy a metody.

| Základní třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. app. Activity | MAMActivity |
| Android. app. Activity | MAMActivityGroup |
| Android. app. AliasActivity | MAMAliasActivity |
| Android. app. Application | MAMApplication |
| Android. app. dialog | MAMDialog |
| Android. app. AlertDialog. Builder | MAMAlertDialogBuilder |
| Android. app. DialogFragment | MAMDialogFragment |
| Android. app. ExpandableListActivity | MAMExpandableListActivity |
| Android. app. fragment | MAMFragment |
| Android. app. IntentService | MAMIntentService |
| Android. app. LauncherActivity | MAMLauncherActivity |
| Android. app. ListActivity | MAMListActivity |
| Android. app. ListFragment | MAMListFragment |
| Android. app. NativeActivity | MAMNativeActivity |
| Android. app. PendingIntent | MAMPendingIntent (viz [nedokončený záměr](#pendingintent)) |
| Android. app. Service | MAMService |
| Android. app. TabActivity | MAMTabActivity |
| Android. app. TaskStackBuilder | MAMTaskStackBuilder |
| Android. app. Backup. třídy backupagent | MAMBackupAgent |
| Android. app. Backup. BackupAgentHelper | MAMBackupAgentHelper |
| Android. app. Backup. FileBackupHelper | MAMFileBackupHelper |
| Android. app. Backup. SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| Android. Content. BroadcastReceiver | MAMBroadcastReceiver |
| Android. Content. Contentprovideru | MAMContentProvider |
| Android. OS. Binder | MAMBinder (nutné jenom v případě, že se pořadač negeneruje z rozhraní AIDL (Android Interface Definition Language)) |
| Android. Media. MediaPlayer | MAMMediaPlayer |
| Android. Media. MediaMetadataRetriever | MAMMediaMetadataRetriever |
| Android. Provider. DocumentsProvider | MAMDocumentsProvider |
| Android. preference. PreferenceActivity | MAMPreferenceActivity |
| Android. support. multidex. MultiDexApplication | MAMMultiDexApplication |
| Android. widget. TextView | MAMTextView |
| Android. widget. AutoCompleteTextView | MAMAutoCompleteTextView |
| Android. widget. CheckedTextView | MAMCheckedTextView |
| Android. widget. EditText | MAMEditText |
| Android. inputmethodservice. ExtractEditText | MAMExtractEditText |
| Android. widget. MultiAutoCompleteTextView | MAMMultiAutoCompleteTextView |

> [!NOTE]
> I v případě, že vaše aplikace nemá potřebnou vlastní odvozenou třídu `Application`, [Přečtěte si téma `MAMApplication` níže](#mamapplication) .

### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft. Intune. MAM. SDK. support. v4. jar:

| Třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. support. v4. app. DialogFragment | MAMDialogFragment
| Android. support. v4. app. FragmentActivity | MAMFragmentActivity
| Android. support. v4. app. fragment | MAMFragment
| Android. support. v4. app. JobIntentService | MAMJobIntentService
| Android. support. v4. app. TaskStackBuilder | MAMTaskStackBuilder
| Android. support. v4. Content. Provider | MAMFileProvider
| Android. support. v4. Content. WakefulBroadcastReceiver | MAMWakefulBroadcastReceiver

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft. Intune. MAM. SDK. support. v7. jar:

|Třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. support. v7. app. AlertDialog. Builder | MAMAlertDialogBuilder |
| Android. support. v7. app. AppCompatActivity | MAMAppCompatActivity |
| Android. support. v7. widget. AppCompatAutoCompleteTextView | MAMAppCompatAutoCompleteTextView |
| Android. support. v7. widget. AppCompatCheckedTextView | MAMAppCompatCheckedTextView |
| Android. support. v7. widget. AppCompatEditText | MAMAppCompatEditText |
| Android. support. v7. widget. AppCompatMultiAutoCompleteTextView | MAMAppCompatMultiAutoCompleteTextView |
| Android. support. v7. widget. AppCompatTextView | MAMAppCompatTextView |

### <a name="microsoftintunemamsdksupportv17jar"></a>Microsoft. Intune. MAM. SDK. support. v17. jar:
|Třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. support. v17. Leanback. widget. SearchEditText | MAMSearchEditText |

### <a name="microsoftintunemamsdksupporttextjar"></a>Microsoft. Intune. MAM. SDK. support. text. jar:
|Třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. support. text. emoji. widget. EmojiAppCompatEditText | MAMEmojiAppCompatEditText |
| Android. support. text. emoji. widget. EmojiAppCompatTextView | MAMEmojiAppCompatTextView |
| Android. support. text. emoji. widget. EmojiEditText | MAMEmojiEditText |
| Android. support. text. emoji. widget. EmojiTextView | MAMEmojiTextView |

### <a name="renamed-methods"></a>Přejmenované metody
V mnoha případech je metoda dostupná ve třídě Androidu označená jako finální ve třídě pro nahrazení MAM. V tomto případě třída nahrazení MAM poskytuje obdobně pojmenovanou metodu (obecně s příponou `MAM`), kterou byste měli přepsat místo toho. Například při odvozování z `MAMActivity` místo přepsání `onCreate()` a volání `super.onCreate()` musí `Activity` přepsat `onMAMCreate()` a volat `super.onMAMCreate()`. Kompilátor Java by měl vyhovět konečným omezením, aby nedocházelo k náhodnému přepsání původní metody místo ekvivalentu MAM.

### <a name="mamapplication"></a>MAMApplication
Pokud vaše aplikace vytvoří podtřídu `android.app.Application`, **musíte** místo toho vytvořit podtřídu `com.microsoft.intune.mam.client.app.MAMApplication`. Pokud vaše aplikace není podtřídou `android.app.Application`, **musíte** nastavit `"com.microsoft.intune.mam.client.app.MAMApplication"` jako atribut `"android:name"` ve značce `<application>` pro souboru AndroidManifest. XML.

### <a name="pendingintent"></a>PendingIntent
Místo `PendingIntent.get*` je nutné použít metodu `MAMPendingIntent.get*`. Pak můžete použít výsledný `PendingIntent` jako obvykle.

### <a name="wrapped-system-services"></a>Zabalené systémové služby
Pro některé třídy systémových služeb je nutné zavolat statickou metodu na obálkovou třídu MAM místo přímého vyvolání požadované metody instance služby. Například volání `getSystemService(ClipboardManager.class).getPrimaryClip()` se musí stát voláním `MAMClipboardManager.getPrimaryClip(getSystemService(ClipboardManager.class)`. Nedoporučuje se tyto náhrady provádět ručně. Místo toho nechte BuildPlugin.

| Třída Androidu | Nahrazení sady Intune App SDK |
|--|--|
| Android. Content. ClipboardManager | MAMClipboard |
| Android. Content. ContentProviderClient | MAMContentProviderClientManagement |
| Android. Content. ContentResolver | MAMContentResolverManagement |
| Android. Content. pm. PackageManager | MAMPackageManagement |
| Android. app. DownloadManager | MAMDownloadManagement |
| Android. Print. PrintManager | MAMPrintManagement |
| Android. support. v4. Print. PrintHelper | MAMPrintHelperManagement |
| Android. View. View | MAMViewManagement |
| Android. View. DragEvent | MAMDragEventManagement |
| Android. app. NotificationManager | MAMNotificationManagement |
| Android. support. v4. app. NotificationManagerCompat | MAMNotificationCompatManagement |

Některé třídy mají většinu zabalení metod, například `ClipboardManager`, `ContentProviderClient`, `ContentResolver` a `PackageManager`, zatímco jiné třídy mají jenom jednu nebo dvě zabalené metody, třeba `DownloadManager`, `PrintManager`, `PrintHelper`, `View`, `DragEvent`, `NotificationManager` a 0. Pokud nepoužíváte BuildPlugin, Projděte si prosím rozhraní API, které jsou vystavené ekvivalentními třídami MAM, pro přesný způsob.

### <a name="manifest-replacements"></a>Náhrady manifestu
Může být nutné provést některé z výše uvedených nahrazení tříd v manifestu i v kódu Java. Speciální Poznámka:
* Odkazy na manifest `android.support.v4.content.FileProvider` musí být nahrazeny řetězcem `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.

## <a name="androidx-libraries"></a>Knihovny AndroidX
V případě Androidu P jsme společnosti Google oznámili novou (přejmenovanou) sadu knihoven podpory nazvanou AndroidX a verze 28 je poslední hlavní verzí stávajících knihoven Android. support.

Na rozdíl od knihovny podpory pro Android neposkytujeme MAM varianty knihoven AndroidX. Místo toho by měla být AndroidX zpracována jako jakákoli jiná externí knihovna a měla by být nakonfigurována tak, aby byla přepsána modulem plug-in nebo nástrojem sestavení. V případě Gradle sestavení to můžete udělat tak, že do pole `includeExternalLibraries` v konfiguraci modulu plug-in nazahrnete `androidx.*`. Volání nástroje příkazového řádku musí vypsat všechny soubory jar explicitně.

### <a name="pre-androidx-architecture-components"></a>Komponenty architektury před AndroidX
Mnoho součástí architektury Androidu, včetně místností, ViewModel a WorkManager, bylo znovu zabalené pro AndroidX. Pokud vaše aplikace používá AndroidX varianty těchto knihoven, zajistěte, aby se přepisy použily, a to zahrnutím `android.arch.*` do pole `includeExternalLibraries` v konfiguraci modulu plug-in. Případně aktualizujte knihovny na jejich ekvivalenty AndroidX.

## <a name="sdk-permissions"></a>Oprávnění sady SDK

Sada Intune App SDK vyžaduje tři [systémová oprávnění pro Android](https://developer.android.com/guide/topics/security/permissions.html) v aplikacích, které ji integrují:

* `android.permission.GET_ACCOUNTS` (požadováno za běhu v případě potřeby)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Knihovna Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) vyžaduje, aby tato oprávnění prováděla zprostředkované ověřování. Pokud tato oprávnění nejsou udělena aplikaci nebo je uživatel odvolá, budou toky ověřování, které vyžadují zprostředkovatele (Portál společnosti aplikace) zakázané.

## <a name="logging"></a>Protokolování

Protokolování by se mělo zpočátku inicializovat, aby se z protokolovaných dat dostala nejvíc hodnot. @no__t – 0 je obvykle nejlepším místem pro inicializaci protokolování.

Pokud chcete přijímat protokoly MAM ve vaší aplikaci, vytvořte [obslužnou rutinu Java](https://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) a přidejte ji do `MAMLogHandlerWrapper`. Tím dojde k vyvolání `publish()` u obslužné rutiny aplikace pro každou zprávu protokolu.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```

## <a name="enable-features-that-require-app-participation"></a>Povolení funkcí, které vyžadují účast aplikace

Existuje několik zásad ochrany aplikací, které sada SDK nemůže implementovat sama o sobě. Aplikace může řídit své chování pro dosažení těchto funkcí pomocí několika rozhraní API, která můžete najít v následujícím rozhraní `AppPolicy`. Chcete-li načíst instanci `AppPolicy`, použijte `MAMPolicyManager.getPolicy`.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
  * This function is now deprecated. Use getIsSaveToLocationAllowed(SaveLocation, String) instead
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Checks whether any activities which could handle the given intent are allowed by policy. Returns false only if all
 * activities which could otherwise handle the intent are blocked. If there are no activities which could handle the intent
 * regardless of policy, returns true. If some activities are allowed and others blocked, returns true. Note that it is not
 * necessary to use this method for policy enforcement. If your app attempts to launch an intent for which there are no
 * allowed activities, MAM will display a dialog explaining the situation to the user.
 *
 * @param intent
 *         intent to check
 *
 * @return whether any activities which could handle this intent are allowed.
*/
boolean areIntentActivitiesAllowed(Intent intent);

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
 * Check if policy allows taking screenshots.
 *
 * @return True if screenshots will be blocked, false otherwise
 */
boolean getIsScreenCaptureAllowed();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Get the notification restriction. If {@link NotificationRestriction#BLOCKED BLOCKED}, the app must not show any notifications
 * for the user associated with this policy. If {@link NotificationRestriction#BLOCK_ORG_DATA BLOCK_ORG_DATA}, the app must show
 * a modified notification that does not contain organization data. If {@link NotificationRestriction#UNRESTRICTED
 * UNRESTRICTED}, all notifications are allowed.
 *
 * @return The notification restriction.
 */
NotificationRestriction getNotificationRestriction();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether file encryption is in use.
 * File encryption is transparent to the app and the app should not need to make any business logic decisions based on this.
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}
```

> [!NOTE]
> `MAMPolicyManager.getPolicy` vždy vrátí zásadu aplikace, která není null, i když zařízení nebo aplikace nejsou v zásadách správy Intune.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Příklad: určení, jestli se pro aplikaci vyžaduje PIN kód

Pokud má aplikace vlastní kód PIN, můžete ji chtít zakázat, pokud správce IT nakonfiguroval sadu SDK tak, aby vyzvat k zadání kódu PIN aplikace. Pokud chcete zjistit, jestli správce IT nasadil do této aplikace zásady pro PIN kód aplikace, zavolejte pro aktuálního koncového uživatele následující metodu:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Příklad: určení primárního uživatele Intune

Kromě rozhraní API zveřejněných v AppPolicy je hlavní název uživatele (**UPN**) zpřístupněn také rozhraním API `getPrimaryUser()` definovaném uvnitř rozhraní `MAMUserInfo`. Chcete-li získat hlavní název uživatele (UPN), zavolejte následující:

```java
MAMComponents.get(MAMUserInfo.class).getPrimaryUser();
```

Úplná definice rozhraní MAMUserInfo je následující:

```java
/**
 * External facing user information.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if neither the device nor app is enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Příklad: určení, jestli je ukládání do zařízení nebo cloudového úložiště povolené

Mnoho aplikací implementuje funkce, které koncovému uživateli umožňují uložit soubory místně nebo do služby cloudového úložiště. Intune App SDK umožňuje správcům IT chránit před únikem dat tím, že aplikuje omezení zásad, která se v jejich organizaci hodí.  Jednou ze zásad, které může řídit, je, zda může koncový uživatel ukládat data do "osobního" nespravovaného úložiště dat. To zahrnuje ukládání do místního umístění, na kartu SD nebo do služeb zálohování třetích stran.

**K povolení této funkce je potřeba účast aplikace.** Pokud vaše aplikace umožňuje ukládání do osobních nebo cloudových umístění přímo z aplikace, musíte tuto funkci implementovat, aby správce IT měl kontrolu nad tím, jestli je ukládání do umístění povolené. Rozhraní API níže umožňuje aplikaci zjistit, jestli je v aktuální zásadě správce Intune povolené ukládání do osobního úložiště. Aplikace pak může tyto zásady vynutila, protože ví o osobním úložišti dat dostupnému koncovému uživateli prostřednictvím aplikace.  

Chcete-li zjistit, zda je zásada vynutila, proveďte následující volání:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

Parametr `service` musí mít jednu z následujících hodnot `SaveLocation`:


- `SaveLocation.ONEDRIVE_FOR_BUSINESS`
- `SaveLocation.SHAREPOINT`
- `SaveLocation.LOCAL`
- `SaveLocation.OTHER`

@No__t-0 by měl být hlavní název uživatele (UPN)/uživatelské jméno/e-mail, který je přidružený ke cloudové službě, na kterou se ukládá (*nemusí* nutně být stejný jako uživatel, který je vlastníkem dokumentu). Pokud mapování mezi hlavním názvem uživatele služby AAD a uživatelským jménem cloudové služby neexistuje nebo není známo uživatelské jméno, použijte hodnotu null. `SaveLocation.LOCAL` není cloudová služba, takže by měla být vždy použita s parametrem uživatelského jména `null`.

Předchozí metoda určení, zda zásada uživatele povoluje ukládání dat do různých umístění, byla `getIsSaveToPersonalAllowed()` v rámci stejné třídy **AppPolicy** . Tato funkce je teď **zastaralá** a neměla by se používat, následující vyvolání je ekvivalentní `getIsSaveToPersonalAllowed()`:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, null);
```

>[!NOTE]
> Použijte `SaveLocation.OTHER`, pokud dané umístění není uvedené ve výčtu **SaveLocation** .

### <a name="example-determine-if-notifications-with-organization-data-need-to-be-restricted"></a>Příklad: určení, jestli je potřeba omezit oznámení s daty organizace

Pokud vaše aplikace zobrazuje oznámení, musíte před zobrazením oznámení ověřit zásadu omezení oznámení pro uživatele přidruženého k oznámení. Chcete-li zjistit, zda je zásada vynutila, proveďte následující volání.

```java
NotificationRestriction notificationRestriction =
    MAMPolicyManager.getPolicyForIdentity(notificationIdentity).getNotificationRestriction();
```

Pokud je omezení `BLOCKED`, aplikace nesmí zobrazit žádná oznámení pro uživatele přidruženého k této zásadě. Pokud `BLOCK_ORG_DATA`, aplikace musí zobrazit upravené oznámení, které neobsahuje data organizace. Pokud je `UNRESTRICTED`, jsou povolena všechna oznámení.

Pokud se nevyvolá `getNotificationRestriction`, sada SDK pro MAM se bude snažit vyhradit automatické omezení oznámení pro aplikace s jedinou identitou. Pokud je povolené Automatické blokování a je nastavená hodnota `BLOCK_ORG_DATA`, nebude se zobrazovat oznámení. V případě podrobnějšího řízení ověřte hodnotu `getNotificationRestriction` a odpovídajícím způsobem upravte oznámení aplikací.

## <a name="register-for-notifications-from-the-sdk"></a>Zaregistrujte se na oznámení ze sady SDK.

### <a name="overview"></a>Přehled
Intune App SDK umožňuje vaší aplikaci řídit chování určitých zásad, jako je selektivní vymazání, pokud je nasadí správce IT. Když správce IT tuto zásadu nasadí, služba Intune odešle sadě SDK oznámení.

Vaše aplikace se musí zaregistrovat pro oznámení ze sady SDK vytvořením `MAMNotificationReceiver` a registrací pomocí `MAMNotificationReceiverRegistry`. To se provádí tím, že poskytne přijímač a typ oznámení požadovaného v `App.onCreate`, jak ukazuje následující příklad:

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

Rozhraní `MAMNotificationReceiver` jednoduše přijímá oznámení ze služby Intune. Některá oznámení jsou zpracovávána přímo v sadě SDK, zatímco jiné vyžadují zapojení aplikace. Aplikace **musí** z oznámení vracet buď true, nebo false. Hodnota true musí vždycky vracet hodnotu true, pokud se nezdařila některá z akcí, kterou se v důsledku oznámení pokusí provést.

* Toto selhání může být oznámeno službě Intune. Příkladem scénáře, který je třeba ohlásit, je, že pokud se aplikaci nepovede vymazat data uživatelů, potom správce IT zahájí vymazání.

>[!NOTE]
> Blokování v `MAMNotificationReceiver.onReceive` je bezpečné, protože jeho zpětné volání není spuštěno ve vlákně uživatelského rozhraní.

Rozhraní `MAMNotificationReceiver` jak je definováno v sadě SDK, je uvedeno níže:

```java
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
```

### <a name="types-of-notifications"></a>Typy oznámení

Následující oznámení se odesílají do aplikace a některé z nich můžou vyžadovat zapojení aplikace:

* **WIPE_USER_DATA**: Toto oznámení se odesílá ve třídě `MAMUserNotification`. Po přijetí tohoto oznámení *musí* aplikace odstranit všechna data přidružená ke spravované identitě (od `MAMUserNotification.getUserIdentity()`). K oznámení může dojít z různých důvodů, včetně toho, kdy vaše aplikace volá `unregisterAccountForMAM`, když správce IT iniciuje vymazání nebo když zásady podmíněného přístupu vyžadované správcem nejsou splněné. Pokud se vaše aplikace pro toto oznámení neregistruje, provede se výchozí chování při vymazání. Výchozí chování odstraní všechny soubory pro aplikaci s jedinou identitou nebo všechny soubory označené spravovanou identitou pro aplikaci s více identitami. Toto oznámení nebude nikdy odesláno ve vlákně uživatelského rozhraní.

* **WIPE_USER_AUXILIARY_DATA**: aplikace se můžou zaregistrovat pro toto oznámení, pokud by chtěli, aby sada Intune App SDK provedla výchozí selektivní vymazání, ale v případě, že se k vymazání dojde, pořád byste chtěli odebrat některá pomocná data. Toto oznámení není k dispozici pro jedinou identitu – aplikace – bude odesláno pouze aplikacím s více identitami. Toto oznámení nebude nikdy odesláno ve vlákně uživatelského rozhraní.

* **REFRESH_POLICY**: Toto oznámení se odesílá v `MAMUserNotification`. Po přijetí tohoto oznámení musí být všechna rozhodnutí o zásadách Intune, která vaše aplikace ukládá do mezipaměti, zrušena a aktualizována. Pokud vaše aplikace neukládá žádné předpoklady zásad, nemusí se pro toto oznámení zaregistrovat. Neudělaly se žádné záruky, jako by to vlákno, na které se toto oznámení pošle.

* **REFRESH_APP_CONFIG**: Toto oznámení se odesílá v `MAMUserNotification`. Po přijetí tohoto oznámení musí být všechna konfigurační data aplikace uložená v mezipaměti zrušena a aktualizována. Neudělaly se žádné záruky, jako by to vlákno, na které se toto oznámení pošle.

* **MANAGEMENT_REMOVED**: Toto oznámení se odesílá v `MAMUserNotification` a informuje aplikaci, že se chystá být nespravované. Po nespravovaném se už nebude moct číst zašifrované soubory, číst data zašifrovaná pomocí MAMDataProtectionManager, pracovat s šifrovanými schránkami nebo jinak účastnit ekosystému spravovaných aplikací. Další podrobnosti najdete níže. Toto oznámení nebude nikdy odesláno ve vlákně uživatelského rozhraní.

* **MAM_ENROLLMENT_RESULT**: Toto oznámení se posílá v `MAMEnrollmentNotification`, aby aplikace informovala o tom, že došlo k pokusu o registraci aplikace, a k poskytnutí stavu tohoto pokusu. Neudělaly se žádné záruky, jako by to vlákno, na které se toto oznámení pošle.

* **COMPLIANCE_STATUS**: Toto oznámení se odesílá v `MAMComplianceNotification`, aby informovalo aplikaci o výsledku pokusu o nápravu v souladu s dodržováním předpisů. Neudělaly se žádné záruky, jako by to vlákno, na které se toto oznámení pošle.

> [!NOTE]
> Aplikace by se nikdy neměla registrovat u oznámení `WIPE_USER_DATA` i `WIPE_USER_AUXILIARY_DATA`.

### <a name="management_removed"></a>MANAGEMENT_REMOVED

Oznámení `MANAGEMENT_REMOVED` značí, že dřív spravovaný uživatel zásad už nebude spravovat zásada MAM Intune. To nevyžaduje vymazání uživatelských dat nebo odhlášení uživatele (pokud bylo vymazání vyžadováno, bude odesláno oznámení `WIPE_USER_DATA`). Mnoho aplikací nemusí toto oznámení zpracovávat vůbec, ale aplikace, které používají `MAMDataProtectionManager`, by si měli [povšimnout tohoto oznámení](#data-protection).

Když MAM volá přijímač `MANAGEMENT_REMOVED` aplikace, bude platit následující:
* MAM už dešifroval dříve šifrované soubory (ale ne chráněné vyrovnávací paměti dat) patřící do aplikace. Soubory ve veřejných umístěních na sdcard, které nepatří přímo do aplikace (např. dokumenty nebo složky pro stahování), se nešifrují.
* Nové soubory nebo chráněné vyrovnávací paměti dat vytvořené metodou přijímače (nebo jakýmkoli jiným kódem spuštěným po spuštění příjemce) nebudou zašifrovány.
* Aplikace má stále přístup k šifrovacím klíčům, takže operace, jako jsou například vyrovnávací paměti dat dešifrování, budou úspěšné.

Jakmile se příjemce vaší aplikace vrátí, už nebude mít přístup k šifrovacím klíčům.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurace knihovny ADAL (Azure Active Directory Authentication Library)

Nejprve si přečtěte pokyny pro integraci ADAL, které najdete v [úložišti ADAL na GitHubu](https://github.com/AzureAD/azure-activedirectory-library-for-android).

Sada SDK spoléhá na knihovnu [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) při svých scénářích [ověřování](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) a podmíněného spuštění, které vyžadují konfiguraci aplikací pomocí [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Hodnoty konfigurace se předávají sadě SDK prostřednictvím metadat souboru AndroidManifest.

Pokud chcete nakonfigurovat aplikaci a povolit správné ověření, přidejte do uzlu aplikace v souboru AndroidManifest. XML následující. Některé z těchto konfigurací se vyžadují jenom v případě, že aplikace používá ADAL k ověřování obecně; v takovém případě budete potřebovat konkrétní hodnoty, které vaše aplikace používá k registraci v AAD. K tomu je potřeba zajistit, aby se koncovým uživatelům nezobrazovala výzva k ověření dvakrát kvůli tomu, že AAD rozpozná dvě samostatné registrační hodnoty: jednu z aplikace a jednu ze sady SDK.

```xml
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
```

### <a name="adal-metadata"></a>Metadata ADAL

* **Autorita** je autorita pro AAD, která se používá. Pokud tato hodnota chybí, použije se veřejné prostředí AAD.
    > [!NOTE]
    > Nenastavte toto pole, pokud je vaše aplikace svrchovaná v cloudu.

* **ClientID** je identifikátor AAD ClientID (označovaný také jako ID aplikace), který se má použít. Pokud je zaregistrované ve službě Azure AD, měli byste použít vlastní ClientID vaší aplikace, nebo můžete použít [výchozí registraci](#default-enrollment-optional) , pokud Neintegruje ADAL.

* **NonBrokerRedirectURI** je identifikátor URI pro přesměrování AAD, který se má použít v případech bez služby Broker. Pokud není zadán, je použita výchozí hodnota `urn:ietf:wg:oauth:2.0:oob`. Tato výchozí hodnota je vhodná pro většinu aplikací.

  * NonBrokerRedirectURI se používá pouze v případě, že SkipBroker je "true".

* **SkipBroker** se používá k přepsání výchozího chování při zapojení jednotného přihlašování do ADAL. SkipBroker by mělo být zadáno pouze pro aplikace, které určují ClientID **a** nepodporují jednotné přihlašování pro jednotné ověřování/pro zařízení. V takovém případě by měl být nastaven na hodnotu "true". Většina aplikací by neměla nastavit parametr SkipBroker.

  * V manifestu **musí** být zadáno ClientID, aby bylo možné zadat hodnotu SkipBroker.

  * Je-li zadán parametr ClientID, je použita výchozí hodnota false (NEPRAVDA).

  * Pokud je SkipBroker "true", bude použit NonBrokerRedirectURI. Aplikace, které neintegrují ADAL (a tudíž nemají žádné ClientID), budou ve výchozím nastavení také "true".

### <a name="common-adal-configurations"></a>Běžné konfigurace ADAL

Níže jsou uvedené běžné způsoby konfigurace aplikace pomocí ADAL. Najděte si konfiguraci vaší aplikace a ujistěte se, že jste nastavili parametry metadat ADAL (popsané výše) na nezbytné hodnoty. Ve všech případech může být autorita zadána, pokud je požadovaná pro jiná než výchozí prostředí. Pokud tento parametr nezadáte, použije se veřejná provozní autorita AAD.

#### <a name="1-app-does-not-integrate-adal"></a>1. aplikace Neintegruje ADAL.
Metadata ADAL **nesmí** být v manifestu přítomna.

#### <a name="2-app-integrates-adal"></a>2. aplikace integruje ADAL.

|Povinný parametr ADAL| Hodnota |
|--|--|
| ClientID | ClientID aplikace (generovaná službou Azure AD při registraci aplikace) |

V případě potřeby může být určena autorita.

Aplikaci musíte zaregistrovat v Azure AD a dát aplikaci přístup ke službě zásady ochrany aplikací:
* Informace o registraci aplikace v Azure AD najdete [tady](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) .
* Zajistěte, aby byla dodržena oprávnění aplikace pro Android ke službě zásady ochrany aplikací (APP). Postupujte podle pokynů v [příručce Začínáme s Intune SDK](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) v části "poskytnutí přístupu aplikace ke službě Intune App Protection (volitelné)". 

Také se podívejte na požadavky pro [podmíněný přístup](#conditional-access) níže.


#### <a name="3-app-integrates-adal-but-does-not-support-brokered-authenticationdevice-wide-sso"></a>3. aplikace integruje ADAL, ale nepodporuje zprostředkované ověřování/jednotné přihlašování pro zařízení.

|Povinný parametr ADAL| Hodnota |
|--|--|
| ClientID | ClientID aplikace (generovaná službou Azure AD při registraci aplikace) |
| SkipBroker | **Podmínka** |

V případě potřeby je možné zadat autoritu a NonBrokerRedirectURI.

### <a name="conditional-access"></a>Podmíněný přístup
Podmíněný přístup (CA) je [funkce](https://docs.microsoft.com/azure/active-directory/develop/active-directory-conditional-access-developer) Azure Active Directory, kterou je možné použít k řízení přístupu k prostředkům AAD. [Správci Intune můžou definovat pravidla certifikační autority](https://docs.microsoft.com/intune/conditional-access) , která povolují přístup k prostředkům jenom ze zařízení nebo aplikací spravovaných pomocí Intune. Aby bylo zajištěno, že aplikace bude mít přístup k prostředkům v případě potřeby, je nutné postupovat podle následujících kroků. Pokud vaše aplikace nezíská přístupové tokeny AAD nebo přistupuje pouze k prostředkům, které nemůžou být chráněné certifikační autoritou, můžete tento postup přeskočit.

1. Postupujte podle [pokynů pro integraci ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-android#how-to-use-this-library). 
   Další informace najdete v tématu Krok 11 pro použití zprostředkovatele.
2. [Zaregistrujte svoji aplikaci pomocí Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-app-registration). 
   Identifikátor URI přesměrování najdete výše v pokynech pro integraci ADAL.
3. Nastavte parametry meta-data manifestu na [Common konfigurace ADAL](#common-adal-configurations), položka 2 výše.
4. Otestujte, jestli je všechno správně nakonfigurované, povolením [certifikační autority založené na zařízeních](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use) z [Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExchangeConnectorMenu/aad/connectorType/2) a potvrzením
    - Toto přihlášení k vaší aplikaci vyzve k instalaci a registraci Portál společnosti Intune
    - Po registraci se přihlášení k vaší aplikaci úspěšně dokončí.
5. Jakmile vaše aplikace dokončí integraci Intune APP SDK, kontaktujte msintuneappsdk@microsoft.com, aby se přidala do seznamu schválených aplikací pro [podmíněný přístup na základě aplikace](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use#app-based-conditional-access) .
6. Po přidání aplikace do seznamu schválených aplikací ověřte [konfiguraci certifikační autority založené na aplikaci](https://docs.microsoft.com/intune/app-based-conditional-access-intune-create) a zajištění úspěšného dokončení přihlášení k vaší aplikaci.

## <a name="app-protection-policy-without-device-enrollment"></a>Zásady ochrany aplikací bez registrace zařízení

### <a name="overview"></a>Přehled
Zásady ochrany aplikací Intune bez registrace zařízení, označované také jako APP-WE nebo MAM-WE, umožňují správu aplikací přes Intune bez nutnosti registrace zařízení do Intune MDM. APP – pracujeme s registracemi zařízení i bez něj. Portál společnosti je stále nutné nainstalovat do zařízení, ale uživatel se nemusí přihlašovat k Portál společnosti a zaregistrovat zařízení.

> [!NOTE]
> Všechny aplikace jsou nutné pro podporu zásad ochrany aplikací bez registrace zařízení.

### <a name="workflow"></a>Pracovní postupy

Když aplikace vytvoří nový uživatelský účet, měl by zaregistrovat účet pro správu pomocí sady Intune App SDK. Sada SDK zpracuje podrobnosti o registraci aplikace ve službě APP-WE; v případě potřeby se při výskytu selhání zopakují všechna registrace v příslušném časovém intervalu.

Aplikace může také v Intune App SDK zadat dotaz na stav registrovaného uživatele, aby bylo možné zjistit, jestli by měl být uživateli zablokovaný přístup k firemnímu obsahu. Pro správu může být zaregistrované víc účtů, ale v současné době se služba APP-WE může aktivně zaregistrovat jenom v jednom účtu. To znamená, že zásady ochrany aplikací můžou dostávat jenom jeden účet v aplikaci.

Aplikace je nutná k poskytnutí zpětného volání pro získání odpovídajícího přístupového tokenu z knihovny služby Azure Active Directory Authentication Library (ADAL) jménem sady SDK. Předpokládá se, že aplikace už používá ADAL k ověřování uživatelů a získání vlastních přístupových tokenů.

Když aplikace kompletně odebere účet, měl by tento účet zrušit jeho registraci, aby označoval, že by aplikace už neměla platit zásady pro tohoto uživatele. Pokud byl uživatel zaregistrovaný ve službě MAM, zruší se registrace uživatele a aplikace se vymaže.

### <a name="overview-of-app-requirements"></a>Přehled požadavků na aplikace

Aby bylo možné implementovat integraci s aplikacemi, musí vaše aplikace zaregistrovat uživatelský účet pomocí sady MAM SDK:

1. Aplikace _musí_ implementovat a zaregistrovat instanci rozhraní `MAMServiceAuthenticationCallback`. Instance zpětného volání by měla být registrována co nejdříve v životním cyklu aplikace (obvykle v metodě `onMAMCreate()` třídy aplikace).

2. Když se vytvoří uživatelský účet a uživatel se úspěšně přihlásí pomocí knihovny ADAL, _musí_ aplikace zavolat `registerAccountForMAM()`.

3. Po odebrání uživatelského účtu by aplikace měla zavolat `unregisterAccountForMAM()`, aby se účet odebral ze správy Intune.

    > [!NOTE]
    > Pokud se uživatel dočasně z aplikace odhlásí, aplikace nemusí volat `unregisterAccountForMAM()`. Volání může iniciovat vymazání k úplnému odebrání podnikových dat pro uživatele.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager
Všechna potřebná rozhraní API pro ověřování a registraci najdete v rozhraní @no__t 0. Odkaz na `MAMEnrollmentManager` lze získat následujícím způsobem:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr
```

Vrácená instance `MAMEnrollmentManager` je zaručena, že nebude mít hodnotu null. Metody rozhraní API spadají do dvou kategorií: **ověřování** a **Registrace účtu**.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Ověřování účtu
Tato část popisuje metody rozhraní API pro ověřování v `MAMEnrollmentManager` a jejich použití.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Aby mohla sada SDK požádat o token ADAL pro daného uživatele a ID prostředku, musí aplikace implementovat rozhraní `MAMServiceAuthenticationCallback`. Instance zpětného volání musí být poskytnuta `MAMEnrollmentManager` voláním metody `registerAuthenticationCallback()`. Pro opakované pokusy o registraci nebo vrácení se změnami zásad ochrany aplikací se může v průběhu životního cyklu aplikace vykonat token, takže se ideální místo pro registraci zpětného volání nachází v metodě `onMAMCreate()` podtřídy `MAMApplication` aplikace.

2. Metoda `acquireToken()` by měla získat přístupový token pro požadované ID prostředku pro daného uživatele. Pokud nemůže získat požadovaný token, měl by vracet hodnotu null.

    > [!NOTE]
    > Zajistěte, aby vaše aplikace využívala parametry `resourceId` a `aadId` předané do `acquireToken()`, takže se získal správný token.

    ```java
    class MAMAuthCallback implements MAMServiceAuthenticationCallback {
        public String acquireToken(String upn, String aadId, String resourceId) {
            return mAuthContext.acquireTokenSilentSync(resourceId, ClientID, aadId).getAccessToken();
        }
    }
    ```

3. V případě, že aplikace není schopna poskytnout token, když sada SDK volá `acquireToken()`, například pokud se tiché ověřování nepovede a nejedná se o nevhodnou dobu k zobrazení uživatelského rozhraní – aplikace může token zadat později voláním metody `updateToken()`. Do `updateToken()` se musí předat stejné hlavní název uživatele (UPN), ID AAD a ID prostředku, které vyžadovalo předchozí volání `acquireToken()`, a to společně s tokenem, který se nakonec získal. Aplikace by měla tuto metodu zavolat co nejdříve po vrácení hodnoty null ze zadaného zpětného volání.

    > [!NOTE]
    > Sada SDK bude pravidelně volat `acquireToken()` a získat tak token, takže volání `updateToken()` není naprosto povinné. Důrazně se ale doporučuje, protože může včas pomáhat registraci a vracení zásad ochrany aplikací.


### <a name="account-registration"></a>Registrace účtu
Tato část popisuje metody rozhraní API pro registraci účtu v `MAMEnrollmentManager` a jejich použití.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Chcete-li zaregistrovat účet pro správu, aplikace by měla volat `registerAccountForMAM()`. Uživatelský účet identifikuje jeho hlavní název uživatele (UPN) i jeho ID uživatele AAD. ID tenanta se taky vyžaduje k přidružení registračních dat k tenantovi AAD uživatele. Může být taky poskytnutá autorita uživatele, která umožňuje registraci pro konkrétní cloudy svrchovaného prostředí. Další informace najdete v části [svrchovaná registrace do cloudu](#sovereign-cloud-registration).  Sada SDK se může pokusit zaregistrovat aplikaci pro daného uživatele ve službě MAM. Pokud se registrace nezdaří, bude se periodicky pokoušet o registraci, dokud nebude účet zaregistrován. Doba opakování bude obvykle 12-24 hodin. Sada SDK poskytuje stav pokusů o registraci asynchronně prostřednictvím oznámení.

2. Vzhledem k tomu, že je vyžadováno ověřování AAD, je nejlepší čas k registraci uživatelského účtu po přihlášení uživatele k aplikaci a úspěšném ověření pomocí ADAL. ID AAD a ID tenanta uživatele se vrátí z ověřovacího volání ADAL jako součást objektu [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) .
    * ID tenanta pochází z metody `AuthenticationResult.getTenantID()`.
    * Informace o uživateli se nacházejí v podobjektu typu `UserInfo`, který pochází z `AuthenticationResult.getUserInfo()` a ID uživatele AAD načtené z tohoto objektu voláním `UserInfo.getUserId()`.

3. Aby bylo možné zrušit registraci účtu ze správy Intune, aplikace by měla volat `unregisterAccountForMAM()`. Pokud byl účet úspěšně zaregistrován a spravován, sada SDK zruší registraci účtu a vymaže jeho data. Periodické pokusy o registraci účtu se zastaví. Sada SDK poskytuje asynchronní stav žádosti o zrušení registrace prostřednictvím oznámení.

### <a name="sovereign-cloud-registration"></a>Registrace svrchovaného cloudu
Aplikace, které jsou ve službě [svrchovaného cloudu](https://www.microsoft.com/trustcenter/cloudservices/nationalcloud) , **musí** poskytovat `authority` pro `registerAccountForMAM()`.  To je možné dosáhnout poskytnutím `instance_aware=true` v [1.14.0 +](https://github.com/AzureAD/azure-activedirectory-library-for-android/releases/tag/v1.14.0) acquireToken EXTRAQUERYPARAMETERS v ADAL a následným vyvoláním `getAuthority()` na AuthenticationCallback AuthenticationResult.

```java
mAuthContext.acquireToken(this, RESOURCE_ID, CLIENT_ID, REDIRECT_URI, PromptBehavior.FORCE_PROMPT, "instance_aware=true",
        new AuthenticationCallback<AuthenticationResult>() {
            @Override
            public void onError(final Exception exc) {
                // authentication failed
            }

            @Override
            public void onSuccess(final AuthenticationResult result) {
                mAuthority = result.getAuthority();
                // handle other parts of the result
            }
        });
```

> [!NOTE]
> V souboru souboru AndroidManifest. XML nenastavujte položku meta-data `com.microsoft.intune.mam.aad.Authority`.

> [!NOTE]
> Ujistěte se, že je správně nastavená autorita v metodě `MAMServiceAuthenticationCallback::acquireToken()`.

#### <a name="currently-supported-sovereign-clouds"></a>Aktuálně podporované cloudy Svrchovan

1. Cloud Azure pro státní správu USA

### <a name="important-implementation-notes"></a>Důležité poznámky k implementaci

#### <a name="authentication"></a>Ověření
* Když aplikace volá `registerAccountForMAM()`, může krátce obdržet zpětné volání na svém rozhraní `MAMServiceAuthenticationCallback`, a to v jiném vlákně. V ideálním případě aplikace získala svůj vlastní token z knihovny ADAL před registrací účtu za účelem urychlení získání požadovaného tokenu. Pokud aplikace vrátí platný token ze zpětného volání, registrace bude pokračovat a aplikace získá konečný výsledek prostřednictvím oznámení.

* Pokud aplikace nevrátí platný token AAD, konečný výsledek pokusu o registraci bude `AUTHENTICATION_NEEDED`. Pokud aplikace obdrží tento výsledek prostřednictvím oznámení, důrazně se doporučuje urychlit proces registrace tím, že získá token pro uživatele a prostředek, který dřív požadoval `acquireToken()`, a zavolá metodu `updateToken()` pro zahájení procesu registrace. Zopakujte.

* K získání tokenu pro pravidelná vrácení se změnami zásad ochrany aplikací se taky zavolá registrovaný `MAMServiceAuthenticationCallback` aplikace. Pokud aplikace není schopna poskytnout token, když se požaduje, nebude dostávat oznámení, ale měl by se pokusit získat token a volat `updateToken()` v nejbližší vhodné době k urychlení procesu vrácení se změnami. Pokud není zadán token, zpětné volání bude i nadále voláno při dalším pokusu o vrácení se změnami.

* Podpora pro cloudy svrchovaného úřadu vyžaduje poskytnutí autority.

#### <a name="registration"></a>Registrace
* Pro usnadnění práce jsou metody registrace idempotentní; například `registerAccountForMAM()`will registrovat pouze účet a pokusit se o registraci aplikace, pokud účet ještě není zaregistrován a `unregisterAccountForMAM()` zruší registraci účtu pouze v případě, že je aktuálně zaregistrován. Následná volání nejsou žádná operace, takže nedochází k žádnému poškození v volání těchto metod více než jednou. Kromě toho není zaručená korespondence mezi voláními těchto metod a oznámení výsledků: tj. Pokud je zavolána `registerAccountForMAM()` pro identitu, která je již zaregistrována, oznámení se pro tuto identitu nemusí znovu odeslat. Je možné, že se odešlou oznámení, která neodpovídají jakýmkoli voláním těchto metod, protože sada SDK může pravidelně zkoušet registraci na pozadí a zrušení registrace se může aktivovat žádostmi o vymazání přijatými ze služby Intune.

* Metody registrace se dají volat pro libovolný počet různých identit, ale v současné době se může úspěšně zaregistrovat jenom jeden uživatelský účet. Pokud je více uživatelských účtů, které jsou licencovány pro Intune a na které cílí zásady ochrany aplikací, zaregistrovány současně nebo téměř ve stejnou dobu, nemusíte mít jistotu, že si bude nikdo obchodovat.

* Nakonec můžete zadat dotaz na `MAMEnrollmentManager` a zjistit, jestli je konkrétní účet zaregistrovaný, a získat jeho aktuální stav pomocí metody `getRegisteredAccountStatus()`. Pokud není zadaný účet zaregistrován, vrátí tato metoda **hodnotu null**. Pokud je účet zaregistrován, vrátí tato metoda stav účtu jako jeden z členů výčtu `MAMEnrollmentManager.Result`.

### <a name="result-and-status-codes"></a>Kód výsledku a stavu
Při prvním registraci účtu začíná ve stavu @no__t 0, což značí, že počáteční pokus o registraci služby MAM není úplný. Po dokončení pokusu o registraci bude odesláno oznámení s jedním z kódů výsledku v následující tabulce. Kromě toho metoda `getRegisteredAccountStatus()` vrátí stav účtu, takže aplikace může vždycky určit, jestli je přístup k podnikovému obsahu pro tohoto uživatele blokovaný. Pokud se pokus o registraci nezdaří, stav účtu se může v průběhu času změnit, protože sada SDK opakuje registraci na pozadí.

|Kód výsledku | Vysvětlení |
| -- | -- |
| `AUTHORIZATION_NEEDED` | Tento výsledek indikuje, že token nebyl poskytnut registrovanou instancí `MAMServiceAuthenticationCallback` aplikace, nebo je poskytnutý token neplatný.  Aplikace by měla získat platný token a volat `updateToken()`, pokud je to možné. |
| `NOT_LICENSED` | Uživatel nemá licenci na Intune nebo se nepovedlo kontaktovat službu Intune MAM.  Aplikace by měla pokračovat v nespravovaném (normálním) stavu a uživatel by neměl být zablokován.  Registrace se bude opakovat pravidelně v případě, že uživatel bude v budoucnu licencován. |
| `ENROLLMENT_SUCCEEDED` | Pokus o registraci byl úspěšný nebo uživatel je už zaregistrovaný.  V případě úspěšné registrace se před tímto oznámením pošle oznámení o aktualizaci zásad.  Přístup k firemním datům by měl být povolený. |
| `ENROLLMENT_FAILED` | Pokus o registraci se nezdařil.  Další podrobnosti najdete v protokolech zařízení.  Aplikace by neměla umožňovat přístup k podnikovým datům v tomto stavu, protože dříve bylo zjištěno, že uživatel má licenci pro Intune.|
| `WRONG_USER` | Pomocí služby MAM může zaregistrovat aplikaci jenom jeden uživatel na zařízení. Tento výsledek indikuje, že uživatel, pro kterého se tento výsledek doručí (druhý uživatel), cílí na zásady MAM, ale už je zaregistrovaný jiný uživatel. Vzhledem k tomu, že zásady MAM nejde pro druhého uživatele vyhovět, musí vaše aplikace neumožňovat přístup k datům tohoto uživatele (případně odebráním uživatele z vaší aplikace), pokud není registrace pro tohoto uživatele v pozdějším čase úspěšná. MAM se zobrazí výzva s možností odebrat existující účet, a to souběžně s doplňováním tohoto `WRONG_USER`. Pokud uživatel obdrží odpověď lidského uživatele na zjištěnou hodnotu, bude to opravdu možné později zaregistrovat druhého uživatele. Dokud se druhý uživatel zaregistruje, MAM se bude pravidelně pokoušet o registraci. |
| `UNENROLLMENT_SUCCEEDED` | Zrušení registrace bylo úspěšné.|
| `UNENROLLMENT_FAILED` | Žádost o zrušení registrace se nezdařila.  Další podrobnosti najdete v protokolech zařízení. Obecně platí, že k této chybě nedojde, dokud aplikace předá hlavní název uživatele (UPN) (bez hodnoty null nebo prázdné). Neexistuje žádná přímá a spolehlivá náprava, kterou může aplikace trvat. Pokud se tato hodnota obdrží při zrušení registrace platného hlavního názvu uživatele (UPN), ohlaste ji prosím týmu Intune MAM jako chybu.|
| `PENDING` | Probíhá prvotní pokus o registraci uživatele.  Aplikace může blokovat přístup k podnikovým datům, dokud není výsledek registrace znám, ale není to nutné. |
| `COMPANY_PORTAL_REQUIRED` | Uživatel má licenci na Intune, ale aplikaci nejde zaregistrovat, dokud se na zařízení nenainstaluje aplikace Portál společnosti. Sada Intune App SDK se pokusí zablokovat přístup k aplikaci pro daného uživatele a nasměrovat je k instalaci aplikace Portál společnosti (podrobnosti najdete níže). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Přepsání výzvy pro Portál společnosti požadavku (volitelné)
Pokud se přijme výsledek `COMPANY_PORTAL_REQUIRED`, sada SDK zablokuje použití aktivit, které používají identitu, pro kterou se požádalo o registraci. Místo toho sada SDK způsobí, že tyto aktivity zobrazí výzvu ke stažení Portál společnosti. Pokud chcete tomuto chování v aplikaci zabránit, můžou aktivity implementovat `MAMActivity.onMAMCompanyPortalRequired`.

Tato metoda je volána před tím, než sada SDK zobrazí své výchozí blokující uživatelské rozhraní. Pokud aplikace změní identitu aktivity nebo zruší registraci uživatele, který se pokusil o registraci, sada SDK aktivitu neblokuje. V této situaci je až do aplikace, abyste se vyhnuli úniku firemních dat. Identitu aktivity budou moct změnit jenom aplikace s více identitami (popsaná později).

Pokud explicitně nezdědíte `MAMActivity` (protože nástroj pro sestavení provede tuto změnu), ale přesto je potřeba toto oznámení zpracovat, můžete místo toho použít `MAMActivityBlockingListener`.

### <a name="notifications"></a>Oznámení
Pokud aplikace zaregistruje oznámení typu **MAM_ENROLLMENT_RESULT**, pošle se `MAMEnrollmentNotification`, aby se aplikace informovala o dokončení žádosti o registraci. @No__t-0 bude přijato prostřednictvím rozhraní `MAMNotificationReceiver`, jak je popsáno v části [Register for Notifications from SDK](#register-for-notifications-from-the-sdk) .

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}
```

Metoda `getEnrollmentResult()` vrací výsledek žádosti o registraci.  Vzhledem k tomu, že `MAMEnrollmentNotification` rozšiřuje `MAMUserNotification`, je k dispozici také identita uživatele, k němuž byl proveden pokus o registraci. Aby bylo možné přijímat tato oznámení, musí aplikace implementovat rozhraní `MAMNotificationReceiver`, které je podrobně popsáno v části [Registrace pro oznámení z SDK](#register-for-notifications-from-the-sdk) .

Stav registrovaného uživatelského účtu se může po přijetí oznámení o registraci změnit, ale ve všech případech se nemění (například pokud se obdrží oznámení `AUTHORIZATION_NEEDED` po více informativním výsledku, jako je například `WRONG_USER`, bude se jednat o další informativní výsledek. udržováno jako stav účtu).  Po úspěšné registraci účtu zůstane stav `ENROLLMENT_SUCCEEDED`, dokud nebude účet nezaregistrován nebo smazán.

## <a name="app-ca-with-policy-assurance"></a>CA aplikace se zárukou zásad

### <a name="overview"></a>Přehled
S využitím certifikační autority aplikace (podmíněný přístup) se zásadou zabezpečení je přístup k prostředkům podmíněný na základě zásad Intune App Protection.  Služba AAD to vynutila tím, že vyžaduje, aby se aplikace zaregistrovala a spravovala aplikací předtím, než udělí token pro přístup k CA aplikace s chráněným prostředkem zásad.  Aplikace musí používat zprostředkovatele ADAL pro získání tokenu a instalace je stejná, jak je popsáno výše v části [podmíněný přístup](#conditional-access).

### <a name="adal-changes"></a>ADAL – změny
Knihovna ADAL má nový kód chyby, který informuje aplikaci o tom, že selhání získání tokenu bylo způsobeno tím, že není kompatibilní se správou aplikací.  Pokud aplikace obdrží tento kód chyby, musí volat sadu SDK, aby se pokusila opravit dodržování předpisů tím, že zaregistruje aplikaci a použije zásady. Metoda `onError()` rozhraní ADAL `AuthenticationCallback` přijme výjimku a kód chyby `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED`.  V tomto případě lze výjimku přetypovat na `IntuneAppProtectionPolicyRequiredException`, ze kterého lze extrahovat další parametry pro použití v souladu s oprava (viz Ukázka kódu níže). Po úspěšné opravě se aplikace může znovu pokusit o získání tokenu prostřednictvím ADAL.

> [!NOTE]
> Tento nový kód chyby a další podpora pro certifikační autoritu aplikací pomocí zásad správy vyžaduje verzi 1.15.0 (nebo vyšší) knihovny ADAL.

### <a name="mamcompliancemanager"></a>MAMComplianceManager
Rozhraní `MAMComplianceManager` se používá v případě, že je v ADAL přijata chyba požadovaná zásadou.  Obsahuje metodu `remediateCompliance()`, která by měla být volána k pokusu o vložení aplikace do stavu kompatibility. Odkaz na `MAMComplianceManager` lze získat následujícím způsobem:

```java
MAMComplianceManager mgr = MAMComponents.get(MAMComplianceManager.class);

// make use of mgr
```

Vrácená instance `MAMComplianceManager` je zaručena, že nebude mít hodnotu null.

```java
package com.microsoft.intune.mam.policy;

public interface MAMComplianceManager {
    void remediateCompliance(String upn, String aadId, String tenantId, String authority, boolean showUX);
}
```

Metoda `remediateCompliance()` se zavolala k pokusu o vložení aplikace pod správu, aby splňovala podmínky pro AAD, které udělí požadovaný token.  První čtyři parametry lze extrahovat z výjimky přijaté metodou ADAL `AuthenticationCallback.onError()` (viz Ukázka kódu níže).  Konečný parametr je logická hodnota, která určuje, jestli se při pokusu o dodržování předpisů zobrazuje uživatelské rozhraní.  Toto je jednoduché rozhraní pro zablokování, které se poskytuje jako výchozí pro aplikace, které v průběhu této operace nemusejí zobrazovat přizpůsobené uživatelské prostředí.  Bude blokovat jenom tehdy, když probíhá náprava dodržování předpisů a výsledný výsledek se nezobrazí.  Aplikace by měla zaregistrovat přijímač oznámení, aby zpracovával úspěch nebo neúspěch pokusu o nápravu dodržování předpisů (viz níže).

Metoda `remediateCompliance()` může provést registraci MAM v rámci zřizování dodržování předpisů.  Aplikace může obdržet oznámení o registraci, pokud zaregistroval příjemce oznámení pro oznámení o registraci.  Registrovaná @no__ta aplikace-0 bude mít k získání tokenu pro registraci MAM k dispozici metodu `acquireToken()`. `acquireToken()` se bude volat před tím, než aplikace získá svůj vlastní token, takže všechny úlohy vytváření účtů nebo účtů, které aplikace provede po úspěšném pořízení tokenu, se ještě nemusely udělat.  Zpětné volání musí být schopné získat token v tomto případě.  Pokud nemůžete vrátit token z `acquireToken()`, pokus o nápravu kompatibility se nezdaří.  Pokud zavoláte `updateToken()` později s platným tokenem pro požadovaný prostředek, náprava kompatibility se zopakuje okamžitě se zadaným tokenem.

> [!NOTE]
> Získání tichého tokenu bude stále možné v `acquireToken()`, protože uživatel už je s průvodcem nainstalován a před přijetím chyby `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED` se zařízení zaregistruje.  Výsledkem je, že zprostředkovatel má v mezipaměti platný obnovovací token, který umožňuje, aby tiché acqisition požadovaného tokenu bylo úspěšné.

Tady je ukázka přijetí chyby vyžadované zásadou v metodě @no__t 0 a volání `MAMComplianceManager` pro zpracování této chyby.

```java
public void onError(@Nullable Exception exc) {
    if (exc instanceof AuthenticationException && 
        ((AuthenticationException) exc).getCode() == ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED) {

        final IntuneAppProtectionPolicyRequiredException policyRequiredException = 
            (IntuneAppProtectionPolicyRequiredException) ex;

        final String upn = policyRequiredException.getAccountUpn();
        final String aadId = policyRequiredException.getAccountUserId();
        final String tenantId = policyRequiredException.getTenantId();
        final String authority = policyRequiredException.getAuthorityURL();

        MAMComplianceManager complianceManager = MAMComponents.get(MAMComplianceManager.class);
        complianceManager.remediateCompliance(upn, aadId, tenantId, authority, showUX);
    }
}
```

### <a name="status-notifications"></a>Oznámení o stavu
Pokud aplikace zaregistruje oznámení typu **COMPLIANCE_STATUS**, pošle se `MAMComplianceNotification`, aby se informovalo o konečném stavu pokusu o nápravu kompatibility. @No__t-0 bude přijato prostřednictvím rozhraní `MAMNotificationReceiver`, jak je popsáno v části [Register for Notifications from SDK](#register-for-notifications-from-the-sdk) .

```java
public interface MAMComplianceNotification extends MAMUserNotification {
    MAMCAComplianceStatus getComplianceStatus();
    String getComplianceErrorTitle();
    String getComplianceErrorMessage();
}
```

Metoda `getComplianceStatus()` vrátí výsledek pokusu o nápravu kompatibility jako hodnotu z výčtu `MAMCAComplianceStatus`.

|Kód stavu | Vysvětlení |
| -- | -- |
| Neznámý | Stav není známý. To může znamenat neočekávaný důvod selhání. Další informace najdete v protokolech Portál společnosti. |
| KOMPATIBILNÍ | Náprava dodržování předpisů byla úspěšná a aplikace je teď kompatibilní se zásadami. Získání tokenu ADAL by se mělo opakovat. |
| NOT_COMPLIANT | Pokus o nápravu dodržování předpisů se nezdařil.  Aplikace není kompatibilní a získání tokenu ADAL by se nemělo opakovat, dokud neopravíte chybový stav.  Další informace o chybě se odesílají s MAMComplianceNotification. |
| SERVICE_FAILURE | Došlo k chybě při pokusu o načtení dat dodržování předpisů ze služby Intune. Další informace najdete v protokolech Portál společnosti. |
| NETWORK_FAILURE | Při připojování ke službě Intune došlo k chybě. Aplikace by se po obnovení připojení k síti měla znovu pokusit o získání tokenu. |
| CLIENT_ERROR | Pokus o nápravu dodržování předpisů se nezdařil z nějakého důvodu týkajícího se klienta.  Například bez tokenu nebo špatného uživatele. Další informace o chybě se odesílají s MAMComplianceNotification. |
| ULOŽENÉ | Pokus o nápravu dodržování předpisů se nezdařil, protože při překročení časového limitu nebyla od služby přijata odpověď na stav. Aplikace by se měla znovu pokusit o získání tokenu později. |
| COMPANY_PORTAL_REQUIRED | Aby bylo možné úspěšně provést nápravu dodržování předpisů, musí být na zařízení nainstalovaná Portál společnosti.  Pokud je už Portál společnosti na zařízení nainstalovaná, je potřeba restartovat aplikaci.  V takovém případě se zobrazí dialogové okno s výzvou, aby uživatel aplikaci restartoval. |

Pokud je stav dodržování předpisů `MAMCAComplianceStatus.COMPLIANT`, aplikace by měla znovu iniciovat původní pořízení tokenu (pro svůj vlastní prostředek). Pokud se pokus o nápravu kompatibility nepovede, metody `getComplianceErrorTitle()` a `getComplianceErrorMessage()` vrátí lokalizované řetězce, které může aplikace zobrazit koncovému uživateli, pokud se zvolí.  Většina chybových případů není aplikací remediable, takže v případě obecného případu může být nejlepším řešením selhání při vytváření nebo přihlašování účtů a umožnit uživateli opakovat akci později.  Pokud je chyba trvalá, může vám protokol MAM určit příčinu.  Koncový uživatel může protokoly odeslat pomocí pokynů, které najdete [tady](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android "Posílání e-mailových protokolů firemní podpoře").

Vzhledem k tomu, že `MAMComplianceNotification` rozšiřuje `MAMUserNotification`, je k dispozici také identita uživatele, u kterého došlo k pokusu o nápravu.

Tady je příklad registrace přijímače pomocí anonymní třídy pro implementaci rozhraní MAMNotificationReceiver:

```java
final MAMNotificationReceiverRegistry notificationRegistry = MAMComponents.get(MAMNotificationReceiverRegistry.class);
// create a receiver
final MAMNotificationReceiver receiver = new MAMNotificationReceiver() {
    public boolean onReceive(MAMNotification notification) {
        if (notification.getType() == MAMNotificationType.COMPLIANCE_STATUS) {
            MAMComplianceNotification complianceNotification = (MAMComplianceNotification) notification;
            
            // take appropriate action based on complianceNotification.getComplianceStatus()
            
            // unregister this receiver if no longer needed
            notificationRegistry.unregisterReceiver(this, MAMNotificationType.COMPLIANCE_STATUS);
        }
        return true;
    }
};
// register the receiver
notificationRegistry.registerReceiver(receiver, MAMNotificationType.COMPLIANCE_STATUS);
```

> [!NOTE]
> Příjemce oznámení musí být zaregistrován před voláním `remediateCompliance()`, aby se předešlo konfliktu časování, který by mohl způsobit vynechání oznámení.

### <a name="implementation-notes"></a>Poznámky k implementaci
> [!NOTE]
> **Důležitá změna!**  <br>
> Metoda `MAMServiceAuthenticationCallback.acquireToken()` aplikace by měla předat *hodnotu false* pro nový příznak `forceRefresh` na `acquireTokenSilentSync()`.
> Dřív se vám doporučuje předat *hodnotu true* , aby se vyřešil problém s aktualizací tokenů od zprostředkovatele, ale byl nalezen problém se službou ADAL, který by mohl v některých scénářích zabránit získání tokenů, pokud je tento příznak *pravdivý*.
```java
AuthenticationResult result = acquireTokenSilentSync(resourceId, clientId, userId, /* forceRefresh */ false);
```

> [!NOTE]
> Pokud chcete při pokusu o nápravu zobrazit vlastní blokující uživatelské rozhraní, měli byste předat *hodnotu false* , aby parametr showUX `remediateCompliance()`. Před voláním `remediateCompliance()` je nutné nejprve zobrazit vaše uživatelské rozhraní a zaregistrovat naslouchací proces oznámení.  Tím zabráníte konfliktu časování, ve kterém by nebylo možné oznámení nastavovat, pokud `remediateCompliance()` selže velmi rychle.  Například metoda `onCreate()` nebo `onMAMCreate()` podtřídy Activity je ideálním místem pro registraci naslouchacího procesu oznámení a pak volání `remediateCompliance()`.  Parametry pro `remediateCompliance()` se dají předat vašemu UŽIVATELSKÉmu prostředí jako další.  Po přijetí oznámení o stavu dodržování předpisů můžete zobrazit výsledek nebo jednoduše dokončit aktivitu.

> [!NOTE]
> `remediateCompliance()` zapíše účet a pokusí se o registraci.  Po získání hlavního tokenu se volání `registerAccountForMAM()` nevyžaduje, ale v takovém případě to není nijak poškozeno. Na druhé straně, pokud se aplikaci nepovede získat token a chtějí odebrat uživatelský účet, musí volat `unregisterAccountForMAM()`, aby se účet odebral a zabránilo se opakovaným pokusům o registraci na pozadí.

## <a name="protecting-backup-data"></a>Ochrana zálohovaných dat
Od Androidu Marshmallow (API 23) má Android dva způsoby, jak aplikaci zálohovat svá data. Každá možnost je k dispozici pro vaši aplikaci a vyžaduje jiné kroky, aby byla zajištěna správná implementace ochrany dat v Intune. V následující tabulce si můžete prohlédnout odpovídající akce vyžadované pro správné chování ochrany dat.  Další informace o metodách zálohování najdete v příručce k [rozhraní Android API](https://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Automatické zálohování pro aplikace
Android začal nabízet [Automatické úplné zálohování](https://developer.android.com/guide/topics/data/autobackup.html) na disk Google pro aplikace na zařízeních s Androidem Marshmallow, bez ohledu na cílové rozhraní API aplikace. Pokud jste v souboru souboru AndroidManifest. XML explicitně nastavili `android:allowBackup` na **hodnotu false**, aplikace nebude nikdy zařazená do fronty pro zálohování pomocí Androidu a firemní data zůstanou v aplikaci. V takovém případě není nutná žádná další akce.

Ve výchozím nastavení je však atribut `android:allowBackup` nastaven na hodnotu true, i když v souboru manifestu není zadáno `android:allowBackup`. To znamená, že všechna data aplikace se automaticky zálohují do účtu disku Google uživatele, což je výchozí chování, které představuje **riziko úniku dat**. Proto sada SDK vyžaduje změny uvedené níže, aby se zajistilo použití ochrany dat.  Pokud chcete, aby vaše aplikace běžela na zařízeních s Androidem Marshmallow, je důležité postupovat podle níže uvedených pokynů k zajištění řádné ochrany zákaznických dat.  

Intune umožňuje využívat všechny [funkce automatického zálohování](https://developer.android.com/guide/topics/data/autobackup.html) , které jsou dostupné z Androidu, včetně možnosti definovat vlastní pravidla v XML, ale pokud chcete zabezpečit svá data, musíte postupovat podle následujících kroků:

1. Pokud vaše aplikace **nepoužívá vlastní třídy backupagent, použijte výchozí** MAMBackupAgent a umožněte tak automatickým úplným zálohám, které jsou kompatibilní se zásadami Intune. V manifestu aplikace vložte následující:

    ```xml
    android:fullBackupOnly="true"
    android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```
    
2. **[Nepovinné]** Pokud jste implementovali volitelné vlastní třídy backupagent, musíte se ujistit, že používáte MAMBackupAgent nebo MAMBackupAgentHelper. Přečtěte si následující oddíly. Zvažte přechod na používání služby Intune **MAMDefaultFullBackupAgent** (popsané v kroku 1), která nabízí snadnou zálohu v Androidu M a vyšších verzích.

3. Pokud se rozhodnete, jaký typ plné zálohy by měla vaše aplikace obdržet (nefiltrovaný, filtrovaný nebo žádný), budete muset nastavit atribut `android:fullBackupContent` na hodnotu true, false nebo prostředek XML ve vaší aplikaci.

4. Pak _**musíte**_ zkopírovat cokoli, co vložíte do `android:fullBackupContent` do značky metadat s názvem `com.microsoft.intune.mam.FullBackupContent` v manifestu.

    **Příklad 1**: Pokud chcete, aby měla vaše aplikace úplné zálohy bez vyloučení, nastavte atribut `android:fullBackupContent` a značku metadat `com.microsoft.intune.mam.FullBackupContent` na **hodnotu true**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Příklad 2**: Pokud chcete, aby vaše aplikace používala vlastní třídy backupagent a odhlásila se od úplného použití zásad Intune, automatické zálohování, musíte nastavit atribut a značku metadat na **false**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Příklad 3**: Pokud chcete, aby měla vaše aplikace úplné zálohy podle vašich vlastních pravidel definovaných v souboru XML, nastavte atribut a značku metadat na stejný prostředek XML:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```

### <a name="keyvalue-backup"></a>Zálohování klíč/hodnota
Možnost [zálohování klíč/hodnota](https://developer.android.com/guide/topics/data/keyvaluebackup.html) je dostupná pro všechna rozhraní API 8 + a nahrává data aplikací do [služby zálohování Androidu](https://developer.android.com/google/backup/index.html). Množství dat na uživatele vaší aplikace je omezené na 5 MB. Použijete-li zálohu klíč/hodnota, je nutné použít **BackupAgentHelper** nebo **třídy backupagent**.

### <a name="backupagenthelper"></a>BackupAgentHelper
BackupAgentHelper je snazší implementovat než třídy backupagent z pohledu nativních funkcí Androidu a integrace s MAM Intune. BackupAgentHelper umožňuje vývojářům zaregistrovat celé soubory a sdílené předvolby pro **FileBackupHelper** a **SharedPreferencesBackupHelper** (v uvedeném pořadí), které se pak při vytvoření přidají do BackupAgentHelper. Postupujte podle následujících kroků a použijte BackupAgentHelper s Intune MAM:

1. Pokud chcete využít zálohu s více identitami BackupAgentHelper, postupujte podle příručky pro Android a [rozšíření BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).

2. Požádejte třídu, aby rozšířila MAM ekvivalent BackupAgentHelper, FileBackupHelper a SharedPreferencesBackupHelper.

|Třída Androidu | Ekvivalent MAM |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Podle těchto pokynů povede k úspěšnému zálohování a obnovování více identit.

### <a name="backupagent"></a>Třídy backupagent

Třídy backupagent vám umožní být mnohem konkrétnější o tom, jaká data se zálohují. Vzhledem k tomu, že vývojář je poměrně zodpovědný za implementaci, je nutné mít k dispozici více kroků pro zajištění odpovídající ochrany dat z Intune. Vzhledem k tomu, že je většina práce na vás vložená, vývojářům se integrace Intune trochu zapojí.

**Integrace MAM:**

1. Pečlivě si přečtěte příručku k Androidu pro [zálohování klíč/hodnota](https://developer.android.com/guide/topics/data/keyvaluebackup.html) a konkrétně [Rozšiřte třídy backupagent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) , abyste zajistili, že vaše implementace třídy backupagent splňuje pokyny pro Android.

2. Zvětšete třídu `MAMBackupAgent`.

**Zálohování s více identitami:**

1. Před zahájením zálohování ověřte, že soubory nebo datové vyrovnávací paměti, které plánujete zálohovat, jsou ve skutečnosti **povolené správcem IT, aby se mohl zálohovat** ve scénářích s více identitami. Poskytneme vám funkci `isBackupAllowed` v `MAMFileProtectionManager` a `MAMDataProtectionManager`, abyste ji zjistili. Pokud soubor nebo datová vyrovnávací paměť není povolená k zálohování, neměli byste je dál zahrnovat do zálohy.

2. V určitém okamžiku během zálohování, pokud chcete zálohovat identity pro soubory, které jste si vyrezervovali v kroku 1, je nutné volat `backupMAMFileIdentity(BackupDataOutput data, File … files)` se soubory, ze kterých plánujete extrahovat data. Tato akce automaticky vytvoří nové entity zálohování a zapíše je do `BackupDataOutput` za vás. Tyto entity budou automaticky využity při obnovení.

**Obnovení více identit:**

Příručka pro zálohování dat určuje obecný algoritmus pro obnovení dat vaší aplikace a poskytuje ukázku kódu v části [rozšíření třídy backupagent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) . Aby bylo možné úspěšně obnovit více identit, je nutné postupovat podle obecné struktury uvedené v této ukázce kódu s zvláštní pozorností pro následující:

1. Pokud chcete projít entity zálohování, musíte použít smyčku `while(data.readNextHeader())`. V předchozím kódu `data` je název místní proměnné pro **MAMBackupDataInput** , který se předá do vaší aplikace při obnovení.

2. Pokud `data.getKey()` se neshoduje s klíčem, který jste napsali v `onBackup`, je nutné volat `data.skipEntityData()`. Bez provedení tohoto kroku se může stát, že obnovení nebude úspěšné. V předchozím kódu `data` je název místní proměnné pro **MAMBackupDataInput** , který se předá do vaší aplikace při obnovení.

3. Vyhněte se vrácení při využívání entit zálohování v konstrukci `while(data.readNextHeader())`, protože entity, které automaticky píšete, budou ztraceny. V předchozím kódu `data` je název místní proměnné pro **MAMBackupDataInput** , který se předá do vaší aplikace při obnovení.

## <a name="multi-identity-optional"></a>Více identit (volitelné)

### <a name="overview"></a>Přehled
Sada Intune App SDK ve výchozím nastavení uplatní zásady na aplikaci jako celek. Multi-identity je volitelná funkce ochrany aplikací Intune, kterou je možné povolit, aby se zásady na úrovni jednotlivých identit používaly. To vyžaduje podstatně větší účast mezi aplikacemi než jiné funkce ochrany aplikací.

> [!NOTE]
> Chybějící správná účast aplikace může vést k únikům dat a dalším problémům se zabezpečením.

Jakmile uživatel zařízení nebo aplikaci zaregistruje, SDK tuto identitu zaregistruje a bude ji považovat za primární spravovanou identitu Intune. Jiní uživatelé v aplikaci budou považováni za nespravované s nastavením zásad bez omezení.

> [!NOTE]
> V současné době se pro každé zařízení podporuje jenom jedna spravovaná identita Intune.

Identita je definována jako řetězec. Identity rozlišují **malá**a velká písmena a požadavky na sadu SDK pro identitu nemusí vracet stejnou velikost písmen, která byla původně použita při nastavování identity.

Aplikace *musí* sadu SDK informovat, když chce změnit aktivní identitu. V některých případech sada SDK aplikaci upozorní také v případě, že se vyžaduje změna identity. Ve většině případů ale MAM nemůže znát, jaká data se zobrazují v uživatelském rozhraní, nebo se v daném čase používají ve vlákně a spoléhá na to, že aplikace nastavila správnou identitu, aby se předešlo úniku dat. V následujících částech se pro některé konkrétní scénáře, které vyžadují akci aplikace, zavolá.

### <a name="enabling-multi-identity"></a>Povolení více identit
Ve výchozím nastavení se všechny aplikace považují za aplikace s jedinou identitou. Zadáním následujících metadat v souboru souboru AndroidManifest. XML můžete deklarovat aplikaci, která bude s více identitami vědět.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Nastavení identity
Vývojáři můžou nastavit identitu uživatele aplikace na následujících úrovních se sestupnou prioritou:

  1. Úroveň vlákna
  2. `Context` (všeobecně `Activity`) úroveň
  3. Úroveň procesu

Identita nastavená na úrovni vlákna nahrazuje identitu nastavenou na úrovni `Context`, která nahrazuje identitu nastavenou na úrovni procesu. Identita nastavená u `Context` se používá jenom v příslušných přidružených scénářích. Operace v/v souborů nemají například přidruženou `Context`. Nejčastěji budou aplikace nastavovat identitu `Context` na `Activity`. Aplikace *nesmí* zobrazit data pro spravovanou identitu, pokud není identita `Activity` nastavená na stejnou identitu. Obecně platí, že identita na úrovni procesu je užitečná pouze v případě, že aplikace funguje pouze s jedním uživatelem v každém vlákně. Mnoho aplikací nemusí být nutné je využít.

Pokud vaše aplikace používá kontext `Application` k získání systémových služeb, ujistěte se, že byla nastavena identita vlákna nebo procesu nebo zda jste nastavili identitu uživatelského rozhraní v kontextu `Application` vaší aplikace.

Pro zpracování zvláštních případů při aktualizaci identity uživatelského rozhraní pomocí `setUIPolicyIdentity` nebo `switchMAMIdentity` lze obě metody předat sadu hodnot `IdentitySwitchOption`.

* `IGNORE_INTENT`: použijte, pokud požadujete přepínač identity, který by měl ignorovat záměr přidružený k aktuální aktivitě.
  Například:

  1. Vaše aplikace obdrží záměr ze spravované identity obsahující spravovaného dokumentu a aplikace zobrazí dokument.
  2. Uživatel přepne na svou osobní identitu, takže vaše aplikace si vyžádá přepínač identity uživatelského rozhraní. V osobní identitě už aplikace nezobrazuje dokument, takže při vyžádání přepínače identity použijete `IGNORE_INTENT`.

  Pokud není nastavená, SDK bude předpokládat, že nejnovější záměr se v aplikaci pořád používá. Tím dojde k tomu, že zásady pro novou identitu budou považovat záměr za příchozí data a používat její identitu.

>[!NOTE]
> Vzhledem k tomu, že `CLIPBOARD_SERVICE` se používá pro operace uživatelského rozhraní, sada SDK používá identitu uživatelského rozhraní aktivity popředí pro operace `ClipboardManager`.
> Následující metody v `MAMPolicyManager` lze použít k nastavení identity a načtení dříve nastavených hodnot identity.

```java
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback, final EnumSet<IdentitySwitchOption> options);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);
  ```

>[!NOTE]
> Identitu aplikace můžete vymazat nastavením na hodnotu null.
>
> Prázdný řetězec může sloužit jako identita, která nikdy nebude mít zásady ochrany aplikací.

#### <a name="results"></a>Výsledky
Všechny metody použité k nastavení identity vrátí zpět výsledné hodnoty prostřednictvím `MAMIdentitySwitchResult`. Mohou být vráceny čtyři hodnoty:

| Návratová hodnota | Scénář |
|--            |--        |
| `SUCCEEDED`    | Změna identity byla úspěšná. |
| `NOT_ALLOWED`  | Změna identity není povolená. K tomu dojde, pokud je proveden pokus o nastavení identity uživatelského rozhraní (`Context`), pokud je v aktuálním vlákně nastavena jiná identita. |
| `CANCELLED`    | Uživatel zrušil změnu identity, a to obvykle kliknutím na tlačítko zpět na příkazovém řádku kódu PIN nebo ověřování. |
| `FAILED`       | Změna identity z nespecifikovaného důvodu se nezdařila.|

Před zobrazením nebo použitím podnikových dat by aplikace měla zajistit, aby byl přepínač identity úspěšný. V současné době se přepínače identity procesů a vláken vždy zdaří pro aplikace s podporou více identit. Vyhrazujeme si ale právo přidat podmínky selhání. Přepnutí identity uživatelského rozhraní může u neplatných argumentů selhat, pokud by došlo ke konfliktu s identitou vlákna, nebo pokud uživatel zruší požadavky na podmíněné spuštění (například stisknutím tlačítka zpět na obrazovce PIN kódu). Výchozím chováním při přepnutí identity uživatelského rozhraní na aktivitu je dokončení aktivity (viz `onSwitchMAMIdentityComplete` níže).

V případě nastavování identity `Context` prostřednictvím `setUIPolicyIdentity` je výsledek hlášen asynchronně. Pokud je `Context` `Activity`, sada SDK nezjistí, jestli se změna identity zdařila, až po podmíněném spuštění, které může vyžadovat, aby uživatel zadal PIN nebo firemní přihlašovací údaje. Aplikace může pro příjem tohoto výsledku implementovat `MAMSetUIIdentityCallback` nebo může pro objekt zpětného volání předat hodnotu null. Všimněte si, že pokud je provedeno volání `setUIPolicyIdentity`, zatímco výsledek z předchozího volání `setUIPolicyIdentity` *ve stejném kontextu* ještě nebyl doručen, nové zpětné volání nahradí starou a původní zpětné volání nikdy neobdrží výsledek.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Identitu aktivity můžete také nastavit přímo pomocí metody v `MAMActivity` namísto volání `MAMPolicyManager.setUIPolicyIdentity`. K tomu použijte následující metodu:

```java
     public final void switchMAMIdentity(final String newIdentity, final EnumSet<IdentitySwitchOption> options);
```

Můžete také přepsat metodu v `MAMActivity`, pokud chcete, aby aplikace byla informována o výsledku pokusů o změnu identity této aktivity.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

Pokud nepřepíšete `onSwitchMAMIdentityComplete` (nebo zavoláte metodu `super`), v případě neúspěšného přepínače identity u aktivity dojde k dokončení aktivity. Pokud přepíšete metodu, musíte se starat o to, aby se podniková data nezobrazovala po neúspěšném přepnutí identity.

>[!NOTE]
> Přepnutí identity může vyžadovat opětovné vytvoření aktivity. V tomto případě se zpětné volání `onSwitchMAMIdentityComplete` doručí do nové instance aktivity.


### <a name="implicit-identity-changes"></a>Implicitní změny identity
Kromě schopnosti aplikace nastavit identitu, vlákno nebo identitu kontextu se můžou měnit na základě příchozího přenosu dat z jiné aplikace spravované přes Intune, která má zásady ochrany aplikací.

#### <a name="examples"></a>Příklady
1. Pokud se aktivita spustí z `Intent` odeslaného jinou aplikací MAM, nastaví se identita aktivity na základě efektivní identity v jiné aplikaci v bodě odeslání `Intent`.

2. U služeb se identita vlákna nastaví podobně po dobu trvání `onStart` nebo volání `onBind`. Volání do `Binder` vráceného z `onBind` také dočasně nastaví identitu vlákna.

3. Volání do `ContentProvider` podobně nastaví identitu vlákna po dobu jejich trvání.


    Kromě toho interakce uživatele s aktivitou může způsobit přepnutí implicitní identity.

    **Příklad:** Uživatel, který zruší výzvu k autorizaci během `Resume`, bude mít za následek implicitní přepnutí na prázdnou identitu.

    Aplikace je dána příležitostí k tomu, aby se tyto změny dozvěděla a v případě, že ji musí, může aplikace zakázat. `MAMService` a `MAMContentProvider` zveřejňují následující metodu, kterou můžou podtřídy přepsat:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchResultCallback callback);
    ```

    Ve třídě `MAMActivity` je v metodě k dispozici další parametr:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchReason reason,
      final AppIdentitySwitchResultCallback callback);
    ```

    * @No__t-0 zachytí zdroj implicitního přepínače a může přijmout hodnoty `CREATE`, `RESUME_CANCELLED` a `NEW_INTENT`.  Důvod `RESUME_CANCELLED` se použije, když obnovení aktivity způsobí zobrazení uživatelského rozhraní pro PIN, ověřování nebo jiné dodržování předpisů a uživatel se pokusí toto uživatelské rozhraní zrušit, obvykle v případě použití tlačítka zpět.


    * @No__t-0 je následující:

      ```java
      public interface AppIdentitySwitchResultCallback {
          /**
            * @param result
            *            whether the identity switch can proceed.
            */
          void reportIdentitySwitchResult(AppIdentitySwitchResult result);
        }
        ```

      Kde ```AppIdentitySwitchResult``` je buď `SUCCESS` nebo `FAILURE`.

Metoda `onMAMIdentitySwitchRequired` se volá u všech implicitních změn identity kromě těch, které se provedly pomocí pořadače vráceného z `MAMService.onMAMBind`. Výchozí implementace `onMAMIdentitySwitchRequired` okamžitě volá:

* `reportIdentitySwitchResult(FAILURE)`, pokud je důvodem `RESUME_CANCELLED`.

* `reportIdentitySwitchResult(SUCCESS)` ve všech ostatních případech.

  Neočekává se, že většina aplikací bude muset blokovat nebo zpozdit přepnutí identity jiným způsobem, ale pokud ji aplikace potřebuje, je potřeba vzít v úvahu následující body:

  * Pokud je přepínač identity zablokován, výsledek je stejný, jako kdyby nastavení sdílení `Receive` zakázal příchozí přenos dat.

  * Pokud služba běží na hlavním vlákně, `reportIdentitySwitchResult` se **musí** volat synchronně nebo dojde k zablokování vlákna uživatelského rozhraní.

  * Pro vytvoření **`Activity`** bude `onMAMIdentitySwitchRequired` volána před `onMAMCreate`. Pokud musí aplikace zobrazit uživatelské rozhraní, aby určila, jestli má být povolen přepínač identity, musí se toto uživatelské rozhraní zobrazit pomocí *jiné* aktivity.

  * Pokud je v **`Activity`** požadován přepínač na prázdnou identitu s důvodem jako `RESUME_CANCELLED`, aplikace musí upravit obnovenou aktivitu a zobrazit tak data konzistentní s tímto přepínačem identity.  Pokud to není možné, aplikace by měla přepínač odmítat a uživatel se znovu vyzve k dodržování zásad pro obnovení identity (třeba zobrazením obrazovky pro zadání kódu PIN).

    > [!NOTE]
    > Aplikace s více identitami bude vždycky přijímat příchozí data ze spravovaných i nespravovaných aplikací. Je zodpovědný za to, že aplikace zachází s daty ze spravovaných identit spravovaným způsobem.

  Pokud je požadovaná identita spravovaná (kontrolu pomocí `MAMPolicyManager.getIsIdentityManaged`), ale aplikace nemůže tento účet používat (například proto, že se v aplikaci musí nejdřív nastavit účty, například e-mailové účty), přepínač identity by měl být zamítnutý.

#### <a name="build-plugin--tool-considerations"></a>Požadavky na modul plug-in nebo nástroj sestavení
Pokud explicitně nedědíte z `MAMActivity`, `MAMService` nebo `MAMContentProvider` (protože povolíte nástrojům sestavení, aby tuto změnu provedl), ale stále potřebují zpracovávat přepínače identity, můžete místo toho implementovat `MAMActivityIdentityRequirementListener` (pro `Activity`) nebo `MAMIdentityRequirementListener` (pro `Service` nebo `ContentProviders`). .
K výchozímu chování pro `MAMActivity.onMAMIdentitySwitchRequired` lze přistup voláním statické metody `MAMActivity.defaultOnMAMIdentitySwitchRequired(activity, identity,
reason, callback)`.

Podobně pokud potřebujete přepsat `MAMActivity.onSwitchMAMIdentityComplete`, můžete implementovat `MAMActivityIdentitySwitchListener` bez explicitního dědění z `MAMActivity`.

### <a name="preserving-identity-in-async-operations"></a>Zachování identity v asynchronních operacích
Je běžné, že operace s vláknem uživatelského rozhraní odesílají úlohy na pozadí do jiného vlákna. Aplikace s více identitami bude chtít zajistit, aby tyto úlohy na pozadí pracovaly s odpovídající identitou, což je často stejná identita, jakou používá aktivita, která je odeslala. Sada MAM SDK poskytuje `MAMAsyncTask` a `MAMIdentityExecutors` jako pohodlí pro zajištění podpory pro zachování identity.
Ty je nutné použít, pokud asynchronní operace může zapisovat podniková data do souboru nebo může komunikovat s jinými aplikacemi.

#### <a name="mamasynctask"></a>MAMAsyncTask
Chcete-li použít `MAMAsyncTask`, jednoduše z něj zdědí místo `AsyncTask` a nahradí přepsání `doInBackground` a `onPreExecute` s `doInBackgroundMAM` a `onPreExecuteMAM` v uvedeném pořadí. Konstruktor `MAMAsyncTask` přijímá kontext aktivity. Například:

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }

    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
}
```

### <a name="mamidentityexecutors"></a>MAMIdentityExecutors
@no__t – 0 umožňuje zabalit existující instanci `Executor` nebo `ExecutorService` jako zachovávání identity `Executor` @ no__t-4 @ no__t-5 s `wrapExecutor` a @no__t 7. Například

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

### <a name="file-protection"></a>Ochrana souborů
Každý soubor má v době vytvoření přiřazenou identitu na základě identity vlákna a procesu. Tato identita se bude používat pro šifrování souborů i pro selektivní vymazání. Šifrují se jenom soubory, jejichž identita je spravovaná a má zásady vyžadující šifrování. Při vymazání výchozích selektivních funkcí sady SDK budou smazány pouze soubory přidružené ke spravované identitě, pro které bylo vyžádáno vymazání. Aplikace může zadat dotaz na identitu souboru nebo ji změnit pomocí třídy `MAMFileProtectionManager`.

```java
public final class MAMFileProtectionManager {

   /**
    * Protect a file or directory. This will synchronously trigger whatever protection is required for the file, and will tag the
    * file for future protection changes. If an identity is set on a directory, it is set recursively on all files and
    * subdirectories. New files or directories will inherit their parent directory's identity. If MAM is operating in offline mode,
    * this method will silently do nothing.
    *
    * @param identity
    *       Identity to set.
    * @param file
    *       File to protect.
    *
    * @throws IOException
    *       If the file cannot be protected.
    */
   public static void protect(final File file, final String identity) throws IOException;

   /**
     * Protect a file obtained from a content provider. This is intended to be used for
     * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
     * It may also be used with descriptors referring to private files owned by this app.
     * It is not intended to be used for files owned by other apps and such usage will fail. If
     * creating a new file via a content provider exposed by another MAM-integrated app, the new
     * file identity will automatically be set correctly if the ContentResolver in use was
     * obtained via a Context with an identity or if the thread identity is set.
     *
     * This will synchronously trigger whatever protection is required for the file, and will tag
     * the file for future protection changes. If an identity is set on a directory, it is set
     * recursively on all files and subdirectories. If MAM is operating in offline mode, this
     * method will silently do nothing.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     *
     * @throws IOException
     *             If the file cannot be protected.
     */
    public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

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

   /**
    * Get the protection info on a file.
    *
    * @param file
    *            File or directory to get information on.
    * @return File protection info, or null if there is no protection info.
    * @throws IOException
    *             If the file cannot be read or opened.
    */
    public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

}

public interface MAMFileProtectionInfo {
    String getIdentity();
}
 ```

#### <a name="app-responsibility"></a>Zodpovědnost aplikace
MAM nemůže automaticky odvodit relaci mezi čtenými soubory a daty zobrazenými v `Activity`. Aplikace *musí* před zobrazením firemních dat správně nastavit identitu uživatelského rozhraní. To zahrnuje data načtená ze souborů. Pokud soubor pochází mimo aplikaci (buď z `ContentProvider`, nebo se čte z veřejně zapisovatelného umístění), *musí* se aplikace před zobrazením informací přečtených ze souboru pokusit určit identitu souboru (pomocí `MAMFileProtectionManager.getProtectionInfo`). Pokud `getProtectionInfo` hlásí neprázdnou identitu bez hodnoty null, *musí* být Identita uživatelského rozhraní nastavená tak, aby odpovídala této identitě (pomocí `MAMActivity.switchMAMIdentity` nebo `MAMPolicyManager.setUIPolicyIdentity`). Pokud se přepínač identity nezdařil, data ze souboru se *nesmí* zobrazit.

Vzorový tok může vypadat nějak takto:
* Uživatel vybere dokument, který se otevře v aplikaci.
  * Během otevřeného toku aplikace potvrdí před čtením dat z disku identitu, která by se měla použít k zobrazení obsahu:

    ```java
    MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
    if (info != null)
        MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback, EnumSet.noneOf<IdentitySwitchOption.class>)
    ```

  * Aplikace počká, dokud se výsledek neohlásí zpětnému volání.
  * Pokud je nahlášený výsledek neúspěšný, aplikace nezobrazuje dokument.
* Aplikace otevře a vykreslí soubor.
  
#### <a name="single-identity-to-multi-identity-transition"></a>Přechod s jednou identitou na více identit
Pokud aplikace, která byla dříve vydaná s integrací Intune s jednou identitou, se později integruje s více identitami, budou mít dříve nainstalované aplikace nějaký přechod (není k dispozici žádné žádné přidružené prostředí). Aplikace není *nutná* k tomu, aby provedla žádné explicitní zpracování tohoto přechodu. Všechny soubory vytvořené před přechodem se budou nadále považovat za spravované (takže zůstanou zašifrované, pokud jsou zapnuté zásady šifrování). V případě potřeby můžete rozpoznat upgrade a použít `MAMFileProtectionManager.protect` k označení určitých souborů nebo adresářů s prázdnou identitou (což odebere šifrování, pokud byly zašifrované).

#### <a name="offline-scenarios"></a>Offline scénáře
Označení identity souboru je citlivé na offline režim. Je třeba vzít v úvahu následující body:

* Pokud Portál společnosti není nainstalovaná, nemůžou být soubory označené označením identity.

* Pokud je Portál společnosti nainstalovaná, ale aplikace nemá zásady MAM služby Intune, nejde spolehlivě označit soubory pomocí identity.

* Když se označení identity souboru zpřístupní, všechny dříve vytvořené soubory se považují za osobní/nespravované (patří do identity s prázdným řetězcem), pokud nebyla aplikace dřív nainstalovaná jako spravovaná aplikace s jedinou identitou. v takovém případě se považují za patří zaregistrovanému uživateli.

### <a name="directory-protection"></a>Ochrana adresáře
Adresáře mohou být chráněny pomocí stejné metody `protect`, která se používá k ochraně souborů. Ochrana adresáře se rekurzivně aplikuje na všechny soubory a podadresáře obsažené v adresáři a na nové soubory vytvořené v adresáři. Vzhledem k tomu, že se ochrana adresářů používá rekurzivně, může dokončení volání `protect` nějakou dobu trvat u velkých adresářů. Z tohoto důvodu aplikace, které používají ochranu na adresář, který obsahuje velký počet souborů, mohou chtít spustit `protect` asynchronně ve vlákně na pozadí.

### <a name="data-protection"></a>Data Protection
Není možné označit soubor jako patřící k více identitám. Aplikace, které musí ukládat data patřící různým uživatelům ve stejném souboru, to můžou provádět ručně pomocí funkcí poskytovaných `MAMDataProtectionManager`. To umožňuje aplikaci šifrovat data a spojit je s určitým uživatelem. Šifrovaná data jsou vhodná pro ukládání na disk v souboru. Můžete zadat dotaz na data přidružená k identitě a data lze později dešifrovat.

Aplikace, které využívají `MAMDataProtectionManager`, by měly implementovat přijímač pro oznámení `MANAGEMENT_REMOVED`. Po dokončení tohoto oznámení již nebudou vyrovnávací paměti, které byly chráněny prostřednictvím této třídy, čitelné, pokud bylo při ochraně vyrovnávací paměti povoleno šifrování souborů. Aplikace může tuto situaci napravit voláním `MAMDataProtectionManager.unprotect` ve všech vyrovnávacích pamětech během tohoto oznámení. V případě, že je žádoucí zachovat informace o identitě, je také bezpečné volat ochranu v rámci tohoto oznámení. šifrování je zaručeno, že bude během oznámení zakázáno.

```java

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

### <a name="content-providers"></a>Poskytovatelé obsahu
Pokud aplikace poskytuje podniková data kromě `ParcelFileDescriptor` prostřednictvím `ContentProvider`, musí aplikace zavolat metodu `isProvideContentAllowed(String)` v `MAMContentProvider` a předat hlavní název uživatele (UPN) identity vlastníka (hlavní název uživatele) pro obsah. Pokud tato funkce vrací hodnotu false, *nesmí* být obsah vrácen volajícímu. Popisovače souborů, které se vrátí přes poskytovatele obsahu, se automaticky zpracují podle identity souboru.

Pokud nedědíte `MAMContentProvider` explicitně a místo toho umožníte nástrojům sestavení provést tuto změnu, můžete zavolat statickou verzi stejné metody: `MAMContentProvider.isProvideContentAllowed(provider,
contentIdentity)`.

### <a name="selective-wipe"></a>Selektivní vymazání
Pokud se aplikace s více identitami registruje pro oznámení @no__t 0, je zodpovědností aplikace odebrat všechna data pro uživatele, který se vymaže, včetně všech souborů, které jsou označené jako identity jako patřící tomuto uživateli. Pokud aplikace Odebere ze souboru uživatelská data, ale přeje si ponechat v souboru jiná data, *musí* změnit identitu souboru (prostřednictvím `MAMFileProtectionManager.protect` na osobního uživatele nebo prázdnou identitu). Pokud se zásada šifrování používá, všechny zbývající soubory patřící uživateli, který se vymaže, se dešifruje a po vymazání se nebudou mít k aplikaci přístup.

Aplikace, která se registruje pro @no__t – 0, neobdrží výhodu výchozího chování selektivního vymazání sady SDK. U aplikací pracujících s více identitami může být tato ztráta důležitější, protože výchozí selektivní vymazání MAM vymaže jenom soubory, jejichž identita cílí na vymazání. Pokud si chce aplikace s více identitami MAM výchozí selektivní vymazání, které se _**má provést při**_ vymazání, měli byste se zaregistrovat pro oznámení @no__t 2. Toto oznámení pošle sada SDK hned předtím, než provede MAM výchozí selektivní vymazání. Aplikace by nikdy neměla zaregistrovat `WIPE_USER_DATA` a `WIPE_USER_AUXILIARY_DATA`.

Výchozí selektivní vymazání ukončí aplikaci řádným způsobem, dokončuje aktivity a ukončuje proces aplikace. Pokud vaše aplikace přepisuje výchozí selektivní vymazání, možná budete chtít, abyste aplikaci zavřeli ručně, abyste zabránili uživateli v přístupu k datům v paměti, když dojde k vymazání.

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Povolení cílené konfigurace MAM pro aplikace pro Android (volitelné)
Páry klíč-hodnota specifické pro aplikaci můžou být nakonfigurované v konzole Intune pro [mam](https://docs.microsoft.com/intune/app-configuration-policies-managed-app) a [Android Enterprise](https://docs.microsoft.com/intune/app-configuration-policies-use-android).
Tyto páry klíč-hodnota nejsou v Intune vůbec interpretovány, ale jsou předány do aplikace. Aplikace, které chtějí přijmout takovou konfiguraci, mohou použít třídy `MAMAppConfigManager` a `MAMAppConfig`. Pokud je u stejné aplikace cíleno více zásad, může být pro stejný klíč k dispozici více konfliktních hodnot.

> [!NOTE] 
> Nastavení konfigurace pro doručení prostřednictvím MAM – nemůžeme delievered v `offline` (Pokud Portál společnosti není nainstalovaná).  V tomto případě se v tomto případě do prázdné identity do@no__t ručí jenom Android Enterprise AppRestrictions.

### <a name="get-the-app-config-for-a-user"></a>Získání konfigurace aplikace pro uživatele
Konfigurace aplikace může být načtena takto:
```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
```

Pokud není k dispozici žádný MAM uživatel, ale vaše aplikace by stále chtěla načíst konfiguraci Androidu Enterprise (která nebude cílená na konkrétního uživatele), můžete předat hodnotu null nebo prázdný řetězec.

### <a name="conflicts"></a>Konflikty
Hodnota nastavená v konfiguraci aplikace MAM přepíše hodnotu se stejnou klíčovou sadou v konfiguraci Android Enterprise config. 

Pokud správce nakonfiguruje konfliktní hodnoty pro stejný klíč (například cílící na různé sady konfigurací aplikace se stejným klíčem na více skupin, které obsahují stejného uživatele), Intune nezpůsobí automatický překlad tohoto konfliktu a provede všechny hodnoty. k dispozici pro vaši aplikaci. 

Vaše aplikace může požádat o všechny hodnoty daného klíče z objektu `MAMAppConfig`:
```java
List<Boolean> getAllBooleansForKey(String key)
List<Long> getAllIntegersForKey(final String key)
List<Double> getAllDoublesForKey(final String key)
List<String> getAllStringsForKey(final String key)
```

nebo si vyžádejte hodnotu, kterou chcete vybrat:
```java
Boolean getBooleanForKey(String key, BooleanQueryType queryType)
Long getIntegerForKey(String key, NumberQueryType queryType)
Double getDoubleForKey(String key, NumberQueryType queryType)
String getStringForKey(String key, StringQueryType queryType)

enum BooleanQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns true if any of the values are true.
     */
    Or,
    /**
     * In case of conflict, returns false if any of the values are false.
     */
    And
}

enum NumberQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns the minimum Integer.
     */
    Min,
    /**
     * In case of conflict, returns the maximum Integer.
     */
    Max
}

enum StringQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns the first result ordered alphabetically.
     */
    Min,

    /**
     * In case of conflict, returns the last result ordered alphabetically.
     */
    Max
}
```

Aplikace může také vyžádat nezpracovaná data jako seznam sad párů klíč-hodnota.

```java
List<Map<String, String>> getFullData()
```

### <a name="full-example"></a>Úplný příklad
```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
String fooValue = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    fooValue = chooseBestValue(values);
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
Long barValue = appConfig.getIntegerForKey("bar", MAMAppConfig.NumberQueryType.Min);
```

### <a name="notification"></a>Oznámení
Konfigurace aplikace přidá nový typ oznámení:
* **REFRESH_APP_CONFIG**: Toto oznámení se odesílá v `MAMUserNotification` a informuje aplikaci o tom, že jsou k dispozici nová konfigurační data aplikace.

### <a name="further-reading"></a>Další čtení
Další informace o tom, jak vytvořit zásady konfigurace cílené aplikace v MAM v Androidu, najdete v části o konfiguraci cílené aplikace MAM v tématu [Jak používat Microsoft Intune zásady konfigurace aplikací pro Android](https://docs.microsoft.com/intune/app-configuration-policies-managed-app).

Konfiguraci aplikace je také možné nakonfigurovat pomocí Graph API. Informace najdete v tématu [Graph API docs pro cílenou konfiguraci mam](https://docs.microsoft.com/graph/api/resources/intune-mam-targetedmanagedappconfiguration).

## <a name="style-customization-optional"></a>Přizpůsobení stylu (volitelné)
Zobrazení generovaná sadou MAM SDK je možné vizuálně přizpůsobit, aby lépe odpovídala aplikaci, ve které je integrovaná. Můžete přizpůsobit barvy primárního, sekundárního a pozadí a také velikost loga aplikace. Přizpůsobení stylu je volitelné a výchozí nastavení bude použito, pokud není nakonfigurován žádný vlastní styl.

### <a name="how-to-customize"></a>Jak přizpůsobit
Aby se změny stylu projevily v zobrazeních MAM Intune, musíte nejdřív vytvořit soubor XML přepsání stylu. Tento soubor by měl být umístěn v adresáři "/res/XML" vaší aplikace a můžete ho pojmenovat podle vaší možnosti. Níže je uveden příklad formátu, který tento soubor musí sledovat.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>
```

Je potřeba znovu použít prostředky, které už existují v rámci vaší aplikace. Například je třeba definovat zelenou barvu v souboru Colors. XML a odkazovat na ni zde. Nemůžete použít šestnáctkový kód barvy #0000ff. Maximální velikost loga aplikace je 110 DIP (DP). Můžete použít menší obrázek loga, ale dodržování maximální velikosti vám poskytne nejlepší výsledky hledání. Pokud překročíte limit 110 DIP, obrázek se škáluje dolů a může způsobit rozostření.

Níže je uveden úplný seznam povolených atributů stylu, prvky uživatelského rozhraní, které řídí, jejich názvy položek atributů XML a typ prostředku, který je pro každý z nich očekáván.

|Atribut Style | Ovlivněné prvky uživatelského rozhraní | Název položky atributu | Očekávaný typ prostředku |
| -- | -- | -- | -- |
| Barva pozadí | Barva pozadí obrazovky pro připnutí <Br>Barva výplně pole pro připnutí | background_color | Barva |
| Barva popředí | Barva textu popředí <br> Ohraničení pole pro PIN kód ve výchozím stavu <br> Znaky (včetně nepovolených znaků) v poli pro připnutí, když uživatel zadá kód PIN| foreground_color | Barva|
| Doplňková barva | Při zvýraznění ohraničení pole připnout <br> Vytváření |accent_color | Barva |
| Logo aplikace | Velká ikona, která se zobrazí na obrazovce pro PIN aplikací Intune | logo_image | Kreslicí |

## <a name="default-enrollment-optional"></a>Výchozí registrace (volitelné)
Následují pokyny pro vyžadování výzvy uživateli při spuštění aplikace pro automatický zápis služby APP-WE (Tento **výchozí zápis** v této části říkáme), vyžadování zásad ochrany aplikací Intune, aby mohli používat vaše služby Intune Protected Users. Integrovaná obchodní aplikace pro Android SDK Také se zabývá tím, jak povolit jednotné přihlašování pro podnikovou aplikaci pro Android, která je integrovaná s SDK. Tato možnost **není podporovaná** pro aplikace pro Store, které můžou používat uživatelé bez Intune.

> [!NOTE] 
> Výhody **výchozího zápisu** zahrnují zjednodušenou metodu získání zásad ze služby App-We pro aplikaci na zařízení.

> [!NOTE] 
> **Výchozím zápisem** je vědomá podpora cloudu.

Pomocí následujících kroků povolte výchozí registraci:

1. Pokud vaše aplikace integruje ADAL nebo potřebujete povolit jednotné přihlašování, [nakonfigurujte knihovnu ADAL](#configure-azure-active-directory-authentication-library-adal) po [běžné konfiguraci #2 konfigurace ADAL](#common-adal-configurations) . V takovém případě tento krok můžete přeskočit.
   
2. Povolte výchozí registraci tak, že do manifestu vložíte následující hodnotu:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />
   ```
   > [!NOTE] 
   > To musí být jediná MAM-WE Integration v aplikaci. Pokud dojde k dalším pokusům o volání rozhraní API MAMEnrollmentManager, dojde ke konfliktům.

3. Povolte zásady MAM vyžadované vložením následující hodnoty v manifestu:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />
   ```
   > [!NOTE] 
   > Tím uživatel vynutí stažení Portál společnosti na zařízení a před použitím dokončí výchozí tok registrace.

## <a name="limitations"></a>Omezení

### <a name="policy-enforcement-limitations"></a>Omezení vynucení zásad

* **Použití překladačů obsahu**: zásady služby Intune pro přenos nebo přijetí můžou blokovat nebo částečně blokovat použití překladače obsahu pro přístup k poskytovateli obsahu v jiné aplikaci. To způsobí, že metody `ContentResolver` vrátí hodnotu null nebo vyvolají chybovou hodnotu (například `openOutputStream` vyvolá `FileNotFoundException`, pokud je zablokované). Aplikace může určit, jestli selhání při zápisu dat pomocí překladače obsahu způsobila zásada (nebo by způsobila zásada), a to voláním:

    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```

    nebo pokud není k dispozici žádná přidružená aktivita:

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    V tomto druhém případě se aplikace s více identitami musí postarat o správné nastavení identity vlákna (nebo předání explicitní identity volání `getPolicy`).

### <a name="exported-services"></a>Exportované služby
Soubor souboru AndroidManifest. XML, který je součástí sady Intune App SDK, obsahuje **službu mamnotificationreceiverservice**, který musí být exportovanou službou, aby mohla portál společnosti odesílat oznámení do spravované aplikace. Služba zkontroluje volajícího, aby bylo zajištěno, že budou zasílání oznámení povolena pouze Portál společnosti.

### <a name="reflection-limitations"></a>Omezení reflexe
Některé základní třídy MAM (například `MAMActivity`, `MAMDocumentsProvider`) obsahují metody (založené na původních základních třídách Android), které používají parametry nebo návratové typy, jsou přítomny jenom nad rámec určitých úrovní rozhraní API. Z tohoto důvodu nemusí být vždy možné použít reflexi k zobrazení výčtu všech metod komponent aplikace. Toto omezení není omezené na MAM, jedná se o stejné omezení, které by se mělo použít, pokud aplikace sama implementovala tyto metody ze základních tříd Androidu.

### <a name="robolectric"></a>Robolectric
Testování chování sady SDK MAM v rámci Robolectric se nepodporuje. V MAM se vyskytly známé problémy, které jsou v Robolectric v důsledku chování přítomného v Robolectric, které je přesně Nenapodobují na skutečných zařízeních nebo emulátorech.

Pokud potřebujete testovat aplikaci v rámci Robolectric, doporučuje se přesunout logiku třídy aplikace do pomocné rutiny a vytvořit APK testování částí pomocí třídy aplikace, která nedědí od MAMApplication.

## <a name="expectations-of-the-sdk-consumer"></a>Očekávání příjemce sady SDK
Intune SDK udržuje kontrakt poskytovaný rozhraním Android API, i když podmínky selhání mohou být v důsledku vynucení zásad spouštěny častěji. Tyto osvědčené postupy pro Android omezí pravděpodobnost selhání:

* Android SDK funkce, které mohou vracet hodnotu null, mají vyšší pravděpodobnost vrácení hodnoty null nyní.  Chcete-li minimalizovat problémy, zajistěte, aby byly na správných místech kontroly hodnoty null.

* Funkce, které je možné zkontrolovat, musí být zkontrolovány prostřednictvím jejich náhradních rozhraní API pro MAM.

* Všechny odvozené funkce musí volat do své verze Super třídy.

* Vyhněte se použití jakéhokoli rozhraní API nejednoznačným způsobem. Například použití `Activity.startActivityForResult` bez kontroly requestCode způsobí neobvyklé chování.

## <a name="telemetry"></a>Telemetrie

Sada Intune App SDK pro Android neřídí shromažďování dat z vaší aplikace. Aplikace Portál společnosti ve výchozím nastavení protokoluje data generovaná systémem. Tato data se odešlou do Microsoft Intune. V rámci zásad Microsoftu neshromažďujeme žádné osobní údaje.

> [!NOTE]
> Pokud se koncoví uživatelé neodesílají tato data, musí se vypnout telemetrie v části nastavení v aplikaci Portál společnosti. Další informace najdete v tématu [vypnutí shromažďování dat Microsoftu o využití](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Doporučené osvědčené postupy pro Android

* Všechny projekty knihovny by měly sdílet stejný balíček Android: Package, kde je to možné. V době běhu nedojde k selhání v neúspěšném pokusu. Toto je čistě problém při sestavení. Novější verze sady Intune App SDK odeberou některé redundance.

* Použijte nejnovější Android SDK nástroje pro sestavení.

* Odeberte všechny nepotřebné a nepoužívané knihovny (například Android. support. v4).

## <a name="testing"></a>Testování
Projděte si [Průvodce testováním](app-sdk-android-testing-guide.md).
