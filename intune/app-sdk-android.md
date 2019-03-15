---
title: Microsoft Intune App SDK pro Android – Příručka pro vývojáře
description: Microsoft Intune App SDK pro Android umožňuje začlenit správu mobilních aplikací (MAM) Intune do vaší aplikace pro Android.
keywords: Sada SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e2edb7f3f09b29a9916a52bd97fb7cfbba87226d
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566746"
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Microsoft Intune App SDK pro Android – Příručka pro vývojáře

> [!NOTE]
> Možná si budete chtít nejdříve přečíst článek [Přehled sady Intune App SDK](app-sdk.md), který vysvětluje aktuální funkce sady SDK a popisuje postup přípravy integrace na jednotlivých podporovaných platformách.

Sada Microsoft Intune App SDK pro Android umožňuje začlenit do vaší nativní aplikace pro Android zásady ochrany aplikací Intune (označované také jako **zásady APP** nebo MAM). Aplikace spravovaná prostřednictvím Intune je aplikace integrovaná se sadou Intune App SDK. Správci Intune můžou zásady ochrany aplikací snadno nasadit do vaší aplikace spravované prostřednictvím Intune, když Intune tuto aplikaci aktivně spravuje.


## <a name="whats-in-the-sdk"></a>Co je v sadě SDK

Sada Intune App SDK obsahuje tyto soubory:

* **Microsoft.Intune.MAM.SDK.aar**: Komponenty SDK kromě souborů JAR knihovny podpory.
* **Microsoft.Intune.MAM.SDK.Suppnebot.v4.jar**: Knihovnu podpory třídy, která je nutná pro povolení MAM v aplikacích, které používají Android v4.
* **Microsoft.Intune.MAM.SDK.Suppnebot.v7.jar**: Knihovnu podpory třídy, která je nutná pro povolení MAM v aplikacích, které používají Android v7.
* **Microsoft.Intune.MAM.SDK.Support.v17.jar**: Třídy, která je nutná pro povolení MAM v aplikacích, které používají Android v17 knihovnu podpory. 
* **Microsoft.Intune.MAM.SDK.Support.Text.jar**: Třídy, která je nutná pro povolení MAM v aplikacích používajících Android podporují knihovny tříd v `android.support.text` balíčku.
* **Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: Tento soubor jar obsahuje zástupné procedury pro třídy systému Android, které jsou k dispozici jenom na novějších zařízeních, ale které odkazují metody v MAMActivity. Novější zařízení budou tyto zástupné třídy ignorovat. Tento soubor JAR je nutný jenom v případě, že aplikace provádí reflexi u tříd odvozených z MAMActivity. U většiny aplikací není nutné ho používat. Pokud chcete tento soubor JAR použít, musíte při vylučování všech jeho tříd z ProGuard postupovat opatrně. Všechny třídy budou v kořenovém balíčku „android“.
* **com.microsoft.intune.mam.build.jar**: Modul plug-in Gradle který [pomáhá při integraci sady SDK](#build-tooling).
* **CHANGELOG.txt**: Obsahuje záznam změn provedených v každé verzi sady SDK.
* **THIRDPARTYNOTICES.TXT**:  Všimněte si autorství, které uznává třetích stran OSS nebo kód, který se zkompiluje do vší aplikace.

## <a name="requirements"></a>Požadavky

### <a name="android-versions"></a>Verze androidu
Sada SDK podporuje Android API 19 (Android 4.4 +) až Android API 28 (Android 9.0).

### <a name="company-portal-app"></a>Aplikace Portál společnosti
Intune App SDK pro Android se při povolení zásad ochrany aplikací spoléhá na přítomnost [Portálu společnosti](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) v zařízení. Portál společnosti načítá zásady ochrany aplikací ze služeb Intune. Při inicializaci načte aplikace z Portálu společnosti zásadu a kód, který ji vynucuje.

> [!NOTE]
> Pokud Portál společnosti na zařízení chybí, chová se aplikace spravovaná prostřednictvím Intune jako běžná aplikace, která nepodporuje zásady ochrany aplikací Intune.

U ochrany aplikací bez registrace zařízení _**nemusí**_ uživatel registrovat zařízení přes aplikaci Portál společnosti.

## <a name="sdk-integration"></a>Integrace sady SDK

### <a name="sample-app"></a>Ukázková aplikace
Příklad toho, jak správně integrace s Intune App SDK je k dispozici na [Githubu](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App). V tomto příkladu [sestavení modulu plug-in Gradle](#gradle-build-plugin).

### <a name="referencing-intune-app-libraries"></a>Odkazování na knihovny Intune App

Intune App SDK je standardní knihovna pro Android, která nemá žádné externí závislosti. Soubor **Microsoft.Intune.MAM.SDK.aar** obsahuje jak rozhraní nutná pro povolení zásad ochrany aplikací, tak kód, který je podmínkou interoperability s Portálem společnosti Microsoft Intune.

Soubor **Microsoft.Intune.MAM.SDK.aar** musí být uváděn jako odkaz na knihovnu pro Android. To provede otevřením projektu aplikace v nástroji Android Studio, kliknutím na **File (Soubor) > New (Nový) > New module (Nový modul)** a výběrem možnosti **Import .JAR/.AAR Package (Importovat balíček .JAR/.AAR)**. Vyberte balíček archivu pro Android s názvem Microsoft.Intune.MAM.SDK.aar a vytvořte modul pro .AAR. Pravým tlačítkem myši klikněte na modul nebo moduly, které obsahují kód aplikace, a přejděte na **Module Settings (Nastavení modulu)** > **karta Dependencies (Závislosti)** > **ikona +** > **Module dependency (Závislost modulu)** > vyberte modul MAM SDK AAR, který jste právě vytvořili > **OK**. Tím se zajistí, že při sestavení projektu se modul zkompiluje se sadou SDK MAM.

Knihovny **Microsoft.Intune.MAM.SDK.Support.XXX.jar** navíc obsahují varianty Intune odpovídajících knihoven `android.support.XXX`. Nejsou součástí souboru Microsoft.Intune.MAM.SDK.aar pro případ, že není nutné, aby aplikace závisela na knihovnách podpory.

#### <a name="proguard"></a>ProGuard

Pokud je jako krok sestavení použitý [ProGuard](http://proguard.sourceforge.net/) (případně jiný mechanismus zmenšování nebo obfuskace), obsahuje sada SDK další konfigurační pravidla, která je nutné zahrnout. Při zahrnutí. Naše pravidla jsou automaticky integrovaná proguard krok AAR ve vašem sestavení, a jsou uloženy soubory nezbytné třídy.

Knihovna ADAL (Azure Active Directory Authentication Libraries) může mít vlastní omezení pro ProGuard. Pokud je součástí vaší aplikace, informujte se o těchto omezeních v dokumentaci pro ADAL.

### <a name="build-tooling"></a>Nástroje sestavení
Sada Intune App SDK je knihovna Androidu, která umožňuje vaší aplikaci podporovat zásady Intune a podílet se na jejich vynucení. Některé zásady vyžadují [pro vynucení explicitní účast vaší aplikace](#enable-features-that-require-app-participation), ale většina z nich se vynucuje poloautomaticky. Toto automatické vynucení vyžaduje, aby aplikace nahradily dědičnost z několika tříd Androidu dědičností z ekvivalentů MAM a obdobně nahradily volání určitých tříd systémové služby Androidu voláními ekvivalentů MAM. Konkrétní nutná nahrazení jsou podrobně uvedená [níže](#class-and-method-replacements).

Provádění těchto nahrazení ručně může být zdlouhavé. Místo toho sada SDK poskytuje nástroje sestavení (modul plug-in pro sestavení Gradle a nástroj příkazového řádku pro ostatní sestavení), které provedou nahrazení automaticky. Tyto nástroje transformují soubory tříd vygenerované při kompilaci Java a nezmění původní zdrojový kód.

Provedení nástroje [přímé nahrazení](#class-and-method-replacements) pouze. Nástroje neprovádí žádné složitější integrace SDK, jako jsou [zásady uložení jako](#enable-features-that-require-app-participation), [použití více identit](#multi-identity-optional), [registrace App-WE](#app-protection-policy-without-device-enrollment), [změny souboru AndroidManifest](#manifest-replacements) nebo [konfigurace ADAL](#configure-azure-active-directory-authentication-library-adal), a proto je třeba tyto kroky provést dříve, než u aplikace povolíte plnou podporu Intune. Pečlivě si pročtěte zbývající část této dokumentace, abyste se seznámili s body integrace, které se týkají vaší aplikace.

> [!NOTE]
> Tyto nástroje můžete spustit u projektu, u kterého jste již provedli částečnou nebo úplnou integraci sady SDK MAM prostřednictvím ručních nahrazení. Váš projekt musí i nadále uvádět sadu SDK MAM jako závislost.

### <a name="gradle-build-plugin"></a>Modul plug-in sestavení Gradle
Pokud aplikace neprovádí sestavení pomocí nástroje Gradle, přejděte na část [Integrace s nástrojem příkazového řádku](#command-line-build-tool). 

Modul plug-in App SDK se distribuuje v sadě SDK jako **GradlePlugin/com.microsoft.intune.mam.build.jar**. Aby Gradle mohl vyhledat modul plug-in, musíte ho přidat do cesty ke třídě skriptu sestavení. Modul plug-in závisí na nástroji [Javassist](https://jboss-javassist.github.io/javassist/), který také musíte přidat. Do cesty třídy je přidáte tak, že do kořene `build.gradle` přidáte následující kód.

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

Potom v souboru `build.gradle` projektu APK jednoduše použijte modul plug in jako
```groovy
apply plugin: 'com.microsoft.intune.mam'
```

Ve výchozím nastavení bude modul plug-in fungovat **pouze** u `project` závislostí.
Na testovací kompilaci nebude mít vliv. Můžete přidat konfiguraci, která zobrazí seznam:
*  projektů k vyloučení,
*  [externích závislostí k zahrnutí](#usage-of-includeexternallibraries), 
*  konkrétních tříd k vyloučení ze zpracování,
*  variant k vyloučení ze zpracování. Může se jednat buď o úplný název varianty, nebo o jednu příchuť. Například
     * Pokud má vaše aplikace typy sestavení `debug` a `release` s příchutěmi {`savory`, `sweet`} a {`vanilla`, `chocolate`}, můžete zadat
     * příchuť `savory` a vyloučit tak všechny varianty s příchutí „savory“, nebo zadat příchuť `savoryVanillaRelease` a vyloučit tak pouze tuto jednu přesnou variantu.

#### <a name="example-partial-buildgradle"></a>Ukázkový částečný soubor build.gradle

```groovy

apply plugin: 'com.microsoft.intune.mam'

dependencies {
    implementation project(':product:FooLib')
    implementation project(':product:foo-project')
    implementation fileTree(dir: "libs", include: ["bar.jar"])
    implementation fileTree(dir: "libs", include: ["zap.jar"])
    implementation "com.contoso.foo:zap-artifact:1.0.0"
    implementation "com.microsoft.bar:baz:1.0.0"

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
Toto by mělo následující důsledky:
* `:product:FooLib` se nepřepíše, protože tato závislost je zahrnuta v `excludeProjects`.
* `:product:foo-project` se přepíše s výjimkou závislosti `com.contoso.SplashActivity`, která se přeskočí, protože je v `excludeClasses`.
* `bar.jar` se přepíše, protože tento soubor je zahrnut v `includeExternalLibraries`.
* `zap.jar` se **nepřepíše**, protože se nejedná o projekt a není zahrnut v `includeExternalLibraries`.
* `com.contoso.foo:zap-artifact:1.0.0` se přepíše, protože je tato závislost zahrnuta v `includeExternalLibraries`.
* `com.microsoft.bar:baz:1.0.0` se přepíše, protože je tato závislost zahrnuta v `includeExternalLibraries` prostřednictvím zástupného znaku (`com.microsoft.*`).
* `com.microsoft.qux:foo:2.0` není přepsán i v případě, že vzhledem k tomu, že je explicitně vyloučila prostřednictvím negace vzor odpovídá zástupný znak stejný jako předchozí položce.

#### <a name="usage-of-includeexternallibraries"></a>Použití vlastnosti includeExternalLibraries

Vzhledem k tomu, že ve výchozím nastavení modul plug-in funguje pouze u závislostí projektu (které obvykle poskytuje funkce `project()`), všechny závislosti zadané funkcí `fileTree(...)` nebo získané z Mavenu nebo jiných zdrojů balíčků (např. `com.contoso.bar:baz:1.2.0`) je třeba zadat do vlastnosti `includeExternalLibraries` v případě, že potřebujete, aby je služba MAM zpracovávala na základě kritérií vysvětlených níže. Zástupné znaky (*) se podporují. Začátek položky s `!` je negace a je možné vyloučit knihoven, které by jinak byly zahrnuty pomocí zástupného znaku.

Při zadávání externích závislostí pomocí notace artefaktu doporučujeme vynechat komponentu verze v hodnotě `includeExternalLibraries`. Pokud verzi uvedete, musí se jednat o přesnou verzi. Dynamické specifikace verzí (např. `1.+`) se nepodporují.

Obecné pravidlo, pomocí něhož byste měli určit to, zda potřebujete do `includeExternalLibraries` zahrnout knihovny, se zakládá na dvou otázkách:
1. Má knihovna v sobě třídy, pro které existují ekvivalenty MAM? Příklady: `Activity`, `Fragment`, `ContentProvider`, `Service` atd.
2. Pokud ano, využije aplikace tyto třídy?

Pokud je odpověď na obě otázky Ano, musíte danou knihovnu do `includeExternalLibraries` zahrnout. 

| Scénář | Zahrnout ano či ne? |
|--|--|
| Do aplikace zahrnete prohlížeč PDF a když se uživatelé pokusí zobrazit PDF, použijete v aplikaci prohlížeč `Activity`. | Ano |
| Do aplikace zahrnete knihovnu HTTP za účelem rozšířeného webového výkonu. | Ne |
| Zahrnete knihovnu, jako je React Native, která obsahuje třídy odvozené z `Activity`, `Application` a `Fragment`, a v aplikaci tyto třídy použijete nebo dále odvodíte. | Ano |
| Zahrnete knihovnu, jako je React Native, která obsahuje třídy odvozené z `Activity`, `Application` a `Fragment`, ale použijete pouze statické pomocné rutiny nebo nástrojové třídy. | Ne |
| Zahrnete knihovnu, která obsahuje třídy odvozené z `TextView`, a v aplikaci tyto třídy použijete nebo dále odvodíte. | Ano |

#### <a name="reporting"></a>Generování sestav
Modul plug-in sestavení můžete vygenerovat sestavu html provedené změny. Chcete-li požádat o generování této sestavy, zadejte `report = true` v `intunemam` blok konfigurace. Pokud se generuje, sestava se zapíšou do `outputs/logs` v adresáři sestavení.

```groovy
intunemam {
    report = true
}
```

#### <a name="dependencies"></a>Závislosti

Modul plug-in Gradle má závislost na nástroji [Javassist](https://jboss-javassist.github.io/javassist/), který musí být dostupný pro zjištění závislostí Gradlu (jak jsme popsali výše). Javassist se používá výhradně v době sestavení při spuštění modulu plug-in. Do vaší aplikace se nepřidá žádný kód Javassist.

> [!NOTE] 
> Musíte používat verzi 3.0 nebo novější modulu plug-in Android Gradle a Gradle 4.1 nebo novější.

### <a name="command-line-build-tool"></a>Nástroj příkazového řádku
Pokud sestavení používá Gradle, přejděte na [další oddíl](#class-and-method-replacements).

Nástroj příkazového řádku je k dispozici ve složce `BuildTool` sady SDK. Má stejnou funkci jako modul plug-in Gradle podrobně popsaný výše, ale je možné ho integrovat do vlastních systémů sestavení nebo systémů sestavení, které Gradle nepoužívají. Je sice obecnější, ale současně je také složitější ho vyvolat, a proto byste měli používat modul plug-in Gradle všude tam, kde je to možné.

#### <a name="using-the-command-line-tool"></a>Použití nástroje příkazového řádku

Nástroj příkazového řádku lze vyvolat pomocí zadaných skriptů pomocných rutin, které se nacházejí v adresáři `BuildTool\bin`.

Nástroj očekává následující parametry.

| Parametr | Popis |
| -- | -- |
| `--input` | Seznam středníkem oddělených souborů JAR a adresářů souborů tříd, které se mají změnit. Seznam by měl obsahovat všechny soubory JAR a adresáře, které máte v úmyslu přepsat. |
| `--output` | Seznam středníkem oddělených souborů JAR a adresářů, do kterých se budou ukládat změněné třídy. Pro jednu výstupní položku by měla existovat jedna vstupní položka a položky by měly být uvedeny v pořadí. |
| `--classpath` | Cesta ke třídě sestavení. Může obsahovat jak soubory JAR, tak i adresáře tříd. |
| `--excludeClasses`| Seznam středníkem oddělených názvů tříd, které chcete z přepsání vyloučit. |

Všechny parametry jsou povinné s výjimkou parametru `--excludeClasses`, který je volitelný.

> [!NOTE] 
> Na unixových systémů se středníkem oddělovač příkazu. Aby nedošlo k prostředí z rozdělení příkazy, ujistěte se, že každý středníku se dostala mimo "\' nebo zabalovat úplné parametr v uvozovkách.

#### <a name="example-command-line-tool-invocation"></a>Ukázka vyvolání nástroje příkazového řádku

``` batch
> BuildTool\bin\BuildTool.bat --input build\product-foo-project;libs\bar.jar --output mam-build\product-foo-project;mam-build\libs\bar.jar --classpath build\zap.jar;libs\Microsoft.Intune.MAM.SDK\classes.jar;%ANDROID_SDK_ROOT%\platforms\android-27\android.jar --excludeClasses com.contoso.SplashActivity
```

Toto by mělo následující důsledky:

* Adresář `product-foo-project` se přepíše na `mam-build\product-foo-project`.
* `bar.jar` se přepíše na `mam-build\libs\bar.jar`.
* `zap.jar` se **nepřepíše**, protože je uveden pouze v `--classpath`.
* Třída `com.contoso.SplashActivity` se **nepřepíše**, ani když je v `--input`.

> [!NOTE] 
> Nástroj sestavení v současné době nepodporuje soubory AAR. Pokud systém sestavení při zpracování souborů AAR ještě neextrahoval soubor `classes.jar`, musíte ho vyextrahovat dříve, než vyvoláte nástroj sestavení.


## <a name="class-and-method-replacements"></a>Nahrazení tříd a metod

Základní třídy Androidu se musí nahradit odpovídajícími ekvivalenty MAM, aby bylo možné povolit správu Intune. Třídy SDK se pohybují mezi základní třídou Androidu a vlastní odvozenou verzí této třídy v aplikaci. Aktivita aplikace by například mohla mít výslednou hierarchii dědičnosti, která vypadá takto: `Activity` > `MAMActivity` >
`AppSpecificActivity`. Filtry vrstvy MAM volají systémové operace, aby mohly vaší aplikaci bez problémů poskytovat spravované zobrazení.

Kromě základních tříd mají povinné ekvivalenty MAM i některé třídy, které vaše aplikace používá bez odvození (např. `MediaPlayer`). [Je třeba nahradit i některé metody](#wrapped-system-services). Přesné podrobnosti jsou uvedeny níže.

Všechna nahrazení popsaná v tomto oddílu lze provést automaticky pomocí [nástrojů sestavení](#build-tooling) sady SDK. 



| Základní třída Android | Náhrada ze sady Intune App SDK |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.Dialog | MAMDialog |
| android.app.AlertDialog.Builder | MAMAlertDialogBuilder |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.ListFragment | MAMListFragment |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent (viz [PendingIntent](#pendingintent)) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (nutné jen v případě, že se třída Binder negeneruje z rozhraní AIDL (Android Interface Definition Language)) |
| android.media.MediaPlayer | MAMMediaPlayer |
| android.media.MediaMetadataRetriever | MAMMediaMetadataRetriever |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |
| android.support.multidex.MultiDexApplication | MAMMultiDexApplication |
| android.widget.TextView | MAMTextView |
| android.widget.AutoCompleteTextView | MAMAutoCompleteTextView |
| android.widget.CheckedTextView | MAMCheckedTextView |
| android.widget.EditText | MAMEditText |
| android.inputmethodservice.ExtractEditText | MAMExtractEditText |
| android.widget.MultiAutoCompleteTextView | MAMMultiAutoCompleteTextView |

> [!NOTE]
> I když není nutné, aby vaše aplikace používala vlastní odvozenou třídu `Application`, [přečtěte si část `MAMApplication` níže](#mamapplication).

### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.JobIntentService | MAMJobIntentService
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
| android.support.v4.content.WakefulBroadcastReceiver | MAMWakefulBroadcastReceiver

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.support.v7.app.AlertDialog.Builder | MAMAlertDialogBuilder |
| android.support.v7.app.AppCompatActivity | MAMAppCompatActivity |
| android.support.v7.widget.AppCompatAutoCompleteTextView | MAMAppCompatAutoCompleteTextView |
| android.support.v7.widget.AppCompatCheckedTextView | MAMAppCompatCheckedTextView |
| android.support.v7.widget.AppCompatEditText | MAMAppCompatEditText |
| android.support.v7.widget.AppCompatMultiAutoCompleteTextView | MAMAppCompatMultiAutoCompleteTextView |
| android.support.v7.widget.AppCompatTextView | MAMAppCompatTextView |

### <a name="microsoftintunemamsdksupportv17jar"></a>Microsoft.Intune.MAM.SDK.Support.v17.jar:
|Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.support.v17.leanback.widget.SearchEditText | MAMSearchEditText |

### <a name="microsoftintunemamsdksupporttextjar"></a>Microsoft.Intune.MAM.SDK.Support.Text.jar:
|Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.support.text.emoji.widget.EmojiAppCompatEditText | MAMEmojiAppCompatEditText |
| android.support.text.emoji.widget.EmojiAppCompatTextView | MAMEmojiAppCompatTextView |
| android.support.text.emoji.widget.EmojiEditText | MAMEmojiEditText |
| android.support.text.emoji.widget.EmojiTextView | MAMEmojiTextView |

### <a name="renamed-methods"></a>Přejmenované metody
V mnoha případech je metoda dostupná ve třídě Androidu označená v náhradní třídě MAM jako finální. Náhradní třída MAM pak poskytuje metodu s podobným názvem (obecně s příponou `MAM`), kterou byste měli přepsat místo toho. Třeba při odvozování od třídy `MAMActivity` musí `Activity` místo přepsání `onCreate()` a volání `super.onCreate()` přepsat `onMAMCreate()` a volat `super.onMAMCreate()`. Kompilátor Javy by měl vynutit finální omezení, která zabrání náhodnému přepsání původní metody místo jejího ekvivalentu MAM.

### <a name="mamapplication"></a>MAMApplication
Pokud vaše aplikace vytváří podtřídu `android.app.Application`, **musíte** místo ní vytvořit podtřídu `com.microsoft.intune.mam.client.app.MAMApplication`. Pokud vaše aplikace podtřídu `android.app.Application` nevytváří, **musíte** nastavit `"com.microsoft.intune.mam.client.app.MAMApplication"` jako atribut `"android:name"` ve značce`<application>` souboru AndroidManifest.xml.

### <a name="pendingintent"></a>PendingIntent
Namísto metody `PendingIntent.get*` musíte použít metodu `MAMPendingIntent.get*`. Pak můžete výslednou třídu `PendingIntent` použít obvyklým způsobem.

### <a name="wrapped-system-services"></a>Zabalené systémové služby
U některých tříd systémové služby je třeba volat statickou metodu obálkové třídy MAM místo přímého vyvolání požadované metody u instance služby. Například volání `getSystemService(ClipboardManager.class).getPrimaryClip()` se musí stát voláním `MAMClipboardManager.getPrimaryClip(getSystemService(ClipboardManager.class)`. Nedoporučujeme tato nahrazení provádět ručně. Nechme raději nástroj BuildPlugin, aby to udělal za nás.

| Třída Androidu | Náhrada ze sady Intune App SDK |
|--|--|
| android.content.ClipboardManager | MAMClipboard |
| android.content.ContentProviderClient | MAMContentProviderClientManagement |
| android.content.ContentResolver | MAMContentResolverManagement |
| android.content.pm.PackageManager | MAMPackageManagement |
| android.app.DownloadManager | MAMDownloadManagement |
| android.print.PrintManager | MAMPrintManagement |
| android.support.v4.print.PrintHelper | MAMPrintHelperManagement |
| android.view.View | MAMViewManagement |
| android.view.DragEvent | MAMDragEventManagement |

Některé třídy mají většina jejich metod např zabalené `ClipboardManager`, `ContentProviderClient`, `ContentResolver`, a `PackageManager` jiné třídy mají pouze jednu nebo dvě metody např zabalené `DownloadManager`, `PrintManager`, `PrintHelper`, `View`, a `DragEvent`. Obraťte se prosím vystavené třídy ekvivalentem MAM pro konkrétní metody, pokud nepoužijete BuildPlugin rozhraní API. 

### <a name="manifest-replacements"></a>Nahrazení manifestů
Některá nahrazení tříd uvedená výše je potřeba provést jak v manifestu, v tak kódu v jazyce Java. Zejména:
* Odkazy manifestu na `android.support.v4.content.FileProvider` je nutné vyměnit za `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.

## <a name="androidx-libraries"></a>Knihovny AndroidX
S příchodem Androidu P Google oznámil novou (přejmenovanou) sadu podpůrných knihoven s názvem AndroidX. Verze 28 je nejnovější hlavní vydanou verzí stávajících podpůrných knihoven Androidu.

Na rozdíl od podpůrných knihoven Androidu neposkytujeme varianty MAM knihoven AndroidX. Místo toho byste měli se sadou AndroidX nakládat jako s kteroukoli jinou externí knihovnou a měli byste ji nakonfigurovat tak, aby ji nástroj nebo modul plug-in sestavení přepsal. U sestavení Gradle toho lze dosáhnout tak, že do pole `includeExternalLibraries` konfigurace modulu plug-in vložíte `androidx.*`. Vyvolání nástroje příkazového řádku musí explicitně vypsat všechny soubory JAR.
## <a name="sdk-permissions"></a>Oprávnění sady SDK

Intune App SDK vyžaduje tři [oprávnění pro systém Android](https://developer.android.com/guide/topics/security/permissions.html) u aplikací, které ji integrují:

* `android.permission.GET_ACCOUNTS` (v případě potřeby se požaduje za běhu)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) tato oprávnění vyžaduje ke zprostředkovanému ověřování. Pokud nejsou tato oprávnění udělená aplikaci nebo je uživatel odvolá, zakážou se toky ověřování, které vyžadují zprostředkovatele (aplikace Portál společnosti).

## <a name="logging"></a>Protokolování

Abyste ze zaprotokolovaných dat získali co nejvíce, měli byste protokolování zahájit brzy. Nejlepším místem k zahájení protokolování je obvykle `Application.onMAMCreate()`.

Pokud chcete v aplikaci přijímat protokoly MAM, vytvořte [Java Handler](https://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) a přidejte ho do `MAMLogHandlerWrapper`. Tím se pro každou zprávu protokolu vyvolá v obslužné rutině aplikace `publish()`.

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

Některé zásady ochrany aplikací nemůže sada SDK implementovat sama o sobě. Aplikace může kontrolovat své chování a dosáhnout těchto funkcí přes několik rozhraní API, která najdete v následujícím rozhraní `AppPolicy`. K načtení instance `AppPolicy` použijte `MAMPolicyManager.getPolicy`.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
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
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether
 * file encryption is in use. File encryption is transparent to the app, and the app should not need
 * to make any business logic decisions based on this.
 * 
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
> `MAMPolicyManager.getPolicy` vždy vrátí zásadu aplikace, která není null, i když zařízení nebo aplikace nepodléhají zásadám správy Intune.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Příklad: Určení, zda je aplikace vyžaduje PIN kód

Pokud aplikace využívá vlastní kód PIN a správce nastavil sadu SDK tak, aby od uživatele vyžadovala zadání kódu PIN aplikace, možná ho bude potřeba zakázat. K určení, jestli je zásada zadávání PIN pro tuto aplikaci nakonfigurovaná, použijte pro aktuálního koncového uživatele toto volání:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Příklad: Určení primárního uživatele Intune

Kromě rozhraní API zobrazovaných v AppPolicy se pomocí API `getPrimaryUser()` definovaného v rámci rozhraní `MAMUserInfo` také zobrazuje hlavní název uživatele (**UPN**) . Hlavní název uživatele zobrazíte tímto voláním:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

Kompletní definici rozhraní MAMUserInfo vidíte níže:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Příklad: Určí, zda ukládání na zařízení nebo cloudové úložiště je povolený.

Spousta aplikací implementuje funkce, které koncovému uživateli umožňují uložit soubory místně nebo do služby cloudového úložiště. Intune App SDK umožňuje správcům IT nastavit ochranu před úniky dat tak, že použijí omezení zásad, která jsou vhodná pro jejich organizaci.  Jedno ze zásad, kterou IT může kontrolovat, je to, jestli koncový uživatel může ukládat do osobního nespravovaného úložiště dat. To zahrnuje ukládání do místního umístění, na kartu SD nebo do služeb zálohování třetích stran.

**K povolení této funkce je nutné zapojení aplikací.** Pokud aplikace umožňuje přímé ukládání do osobních nebo cloudových umístění, musíte implementací této funkce zajistit, aby správce IT měl kontrolu nad tím, jestli je ukládání do umístění povolené. Rozhraní API níže dá aplikaci vědět, jestli je na základě aktuálních zásad správce Intune povolené ukládání do osobního úložiště. Aplikace pak může tyto zásady vynutit, protože si je vědoma, že jejím prostřednictvím jsou koncovým uživatelům dostupná osobní úložiště dat.  

K určení, jestli je tato zásada vynucená, použije následující volání:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

`service` Parametr musí být jeden z následujících `SaveLocation` hodnoty:


- `SaveLocation.ONEDRIVE_FOR_BUSINESS`
- `SaveLocation.SHAREPOINT`
- `SaveLocation.LOCAL`
- `SaveLocation.OTHER`

`username` By se měl v hlavní název uživatele nebo uživatelské jméno nebo e-mailu přidružit se ukládají do cloudové služby (*není* nutně stejné jako uživatele, vlastnící se dokument uložil). Pokud mapování mezi hlavní název uživatele AAD a uživatelské jméno cloud service neexistuje nebo není znám uživatelského jména použijte hodnotu null.

Dříve se pro určování, jestli zásady uživatele umožňují ukládání dat do různých umístění, využívala funkce `getIsSaveToPersonalAllowed()` ze stejné třídy **AppPolicy**. Ta je teď **zastaralá** a neměla by se používat. Vyvolání ekvivalentní k funkci `getIsSaveToPersonalAllowed()` vidíte níže:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Pokud není požadované umístění uvedené ve výčtu parametrů **SaveLocation**, použijte `SaveLocation.OTHER`.


## <a name="register-for-notifications-from-the-sdk"></a>Registrace k oznámením z SDK

### <a name="overview"></a>Přehled
Intune App SDK umožňuje aplikaci, aby měla kontrolu nad chováním určitých zásad, jako je selektivní vymazání, pokud je správce IT nasadil. Jakmile správce IT tuto zásadu nasadí, služba Intune odešle sadě SDK oznámení.

Vaše aplikace se musí k oznámením ze sady SDK registrovat vytvořením třídy `MAMNotificationReceiver` a její registrací pomocí `MAMNotificationReceiverRegistry`. V `App.onCreate` se uvede příjemce a typ požadovaného oznámení, jak ukazuje tento příklad:

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

Rozhraní `MAMNotificationReceiver` jednoduše dostává oznámení ze služby Intune. Některá oznámení zpracovává přímo sada SDK, jiná vyžadují zapojení aplikace. Aplikace **musí** z oznámení vrátit hodnotu True nebo False. True musí vracet vždycky, pokud neselže některá z akcí, kterou se v důsledku oznámení pokusí provést.

* Toto selhání může být nahlášené službě Intune. Příkladem scénáře nahlášení je situace, kdy správce IT iniciuje vymazání dat uživatele a aplikaci se pak nepodaří data vymazat.

>[!NOTE]
> Blokování v `MAMNotificationReceiver.onReceive` je bezpečné, protože zpětné volání neběží na vlákně uživatelského rozhraní.

Rozhraní `MAMNotificationReceiver` tak, jak je definované v sadě SDK, vidíte níže:

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

Následující oznámení se odesílají do aplikace a některá z nich můžou vyžadovat zapojení aplikace:

* **WIPE_USER_DATA**: Toto oznámení se posílá ve `MAMUserNotification` třídy. Po přijetí tohoto oznámení by aplikace měla odstranit všechna data přidružená k podnikové identitě předané přes `MAMUserNotification`. Toto oznámení se momentálně odesílá při rušení registrace služby APP-WE. Během procesu registrace se obvykle zadává primární uživatelské jméno. Když si zaregistrujete toto oznámení, aplikace musí zajistit odstranění všech dat uživatele. Pokud si ho nezaregistrujete, použije se výchozí selektivní mazání.

* **WIPE_USER_AUXILIARY_DATA**: Aplikace můžou zaregistrovat toto oznámení, když chtějí, sada Intune App SDK provést výchozí selektivní vymazání, ale přesto chcete při tomto vymazání odebrat ještě některá pomocná data. Toto oznámení není k dispozici pro jednu identitu aplikace – pouze se pošle do aplikace s více identitami.

* **REFRESH_POLICY**: Toto oznámení se posílá ve `MAMUserNotification`. Po přijetí tohoto oznámení rozhodnutích zásad Intune uložených v mezipaměti aplikace musí být zrušena a aktualizovat. Pokud vaše aplikace neukládá závěry zásady, nemusí zaregistrovat toto oznámení.

* **REFRESH_APP_CONFIG**: Toto oznámení se posílá ve `MAMUserNotification`. Po přijetí tohoto oznámení musí být zrušena a aktualizovat všechna data uložená v mezipaměti konfigurace aplikace.

* **MANAGEMENT_REMOVED**: Toto oznámení se posílá ve `MAMUserNotification` a informuje aplikaci, že se chystá nebude spravovat. Jakmile k ukončení správy dojde, aplikace nebude moct číst šifrované soubory a data zašifrovaná pomocí funkce MAMDataProtectionManager, komunikovat se zašifrovanou schránkou a jinak fungovat v ekosystému spravovaných aplikací. Další podrobnosti najdete níže.

* **MAM_ENROLLMENT_RESULT**: Toto oznámení se posílá ve `MAMEnrollmentNotification` to oznámit sadě app, který aplikace-jsme pokus o registraci dokončí a stav tohoto pokusu.

* **COMPLIANCE_STATUS**: Toto oznámení se posílá ve `MAMComplianceNotification` informovat, výsledek pokus nápravy dodržování předpisů.

> [!NOTE]
> Aplikace by nikdy neměla zaregistrovat oznámení `WIPE_USER_DATA` i `WIPE_USER_AUXILIARY_DATA`.

### <a name="managementremoved"></a>MANAGEMENT_REMOVED

`MANAGEMENT_REMOVED` Oznámení znamená, že se zásadami MAM služby Intune nebude spravovat uživatele dříve – spravované podle zásad. Tato akce nevyžaduje vymazání dat uživatele nebo odhlášení uživatele (pokud byly zapotřebí, vymazání `WIPE_USER_DATA` bude odesláno oznámení). Velký počet aplikací nemusí potřebovat pro toto oznámení, ale aplikace, která používá `MAMDataProtectionManager` by měl [speciální poznamenejte toto oznámení](#data-protection).

Když volá aplikace MAM `MANAGEMENT_REMOVED` příjemce, bude mít následující hodnotu true:
* MAM dešifruje již dříve šifrované soubory (ale ne chráněných dat vyrovnávací paměti), které patří k aplikaci. Soubory na veřejných místech na sdcard, které nepatří přímo do aplikace (například dokumenty nebo stahování složek) nejsou dešifrovat.
* Nové soubory nebo chráněných dat vyrovnávací paměti vytvořené metody příjemce (nebo jakýkoli jiný kód spuštění po spuštění příjemce) nebudou šifrována.
* Aplikace má stále přístup k šifrovacím klíčům, tak bude úspěšné operace, jako jsou dešifrování dat vyrovnávací paměti.

Po návratu příjemce vaší aplikace ho už nebude mít přístup k šifrovacím klíčům.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurace knihovny ADAL (Azure Active Directory Authentication Library)

Nejprve si přečtěte pokyny pro integraci knihovny ADAL, které najdete v [úložišti na GitHubu](https://github.com/AzureAD/azure-activedirectory-library-for-android).

Sada SDK spoléhá na [knihovnu ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) s jejími scénáři [ověření](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) a podmíněného spuštění, což vyžaduje, aby byly aplikace nakonfigurovány s [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Hodnoty konfigurace se předávají sadě SDK prostřednictvím metadat AndroidManifest.

Když chcete konfigurovat svoji aplikaci a povolit správné ověření, přidejte do uzlu aplikace v souboru AndroidManifest.xml následující kód. Některé z těchto konfigurací jsou potřeba, jen když vaše aplikace používá ADAL pro ověřování obecně; v takovém případě budete potřebovat konkrétní hodnoty, které vaše aplikace používá k registraci v AAD. To slouží k zajištění, že koncovému uživateli se nezobrazí výzva k ověření dvakrát kvůli tomu, že AAD rozpozná hodnoty dvou samostatných registrací: jedné z aplikace a jedné ze sady SDK.

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

### <a name="adal-metadata"></a>Metadata knihovny ADAL

* **Authority** je používaná autorita AAD. Pokud tato hodnota chybí, použije se veřejné prostředí AAD.
    > [!NOTE]
    > Toto pole nenastavujte, pokud aplikace podporuje suverénní cloud.

* **ClientID** je ID klienta AAD (také označované jako ID aplikace) který se má použít. Pokud máte v Azure AD zaregistrováno ClientID vlastní aplikace, použijte ho. Pokud tato hodnota chybí, použije se výchozí hodnota Intune.

* **NonBrokerRedirectURI** je identifikátor URI pro přesměrování AAD, který se používá, pokud není zprostředkovatel. Pokud není zadaný, použije se výchozí hodnota `urn:ietf:wg:oauth:2.0:oob`. Tato hodnota se hodí pro většinu aplikací.

    * NonBrokerRedirectURI se používá pouze při SkipBroker hodnotu "true".

* **SkipBroker** umožňuje potlačit výchozí chování jednotného přihlašování ADAL účast. SkipBroker musí být zadán pouze pro aplikace, které určují ClientID **a** nepodporuje zprostředkované ověřování/celém zařízení jednotné přihlašování. V tomto případě by měla být nastavena na hodnotu "true". Většina aplikací nesmí nastavit parametr SkipBroker.

    * ClientID **musí** zadaný v manifestu zadejte SkipBroker hodnotu.

    * Pokud je zadán ClientID, výchozí hodnota je "false".

    * Když SkipBroker hodnotu "true", se použije NonBrokerRedirectURI. Aplikace, které nejsou integraci knihovny ADAL (a mají proto žádná ClientID) budou také ve výchozím nastavení hodnotu "true".

### <a name="common-adal-configurations"></a>Obvyklé konfigurace ADAL

V této části najdete běžné způsoby konfigurace aplikace s knihovnou ADAL. Vyhledejte konfiguraci vaší aplikace a nastavte parametry metadat ADAL (viz výše) na požadované hodnoty. Ve všech případech může být určen oprávnění v případě potřeby pro jiné než výchozí prostředí. Pokud není zadán, použije se veřejné produkční autority AAD.

#### <a name="1-app-does-not-integrate-adal"></a>1. Aplikace neintegruje ADAL.
Metadata knihovny ADAL **nesmí** nacházet v manifestu.

#### <a name="2-app-integrates-adal"></a>2. Aplikace integruje ADAL.

|Požadovaný parametr ADAL| Hodnota |
|--|--|
| ClientID | ClientID aplikace (u zaregistrovaných aplikací je generuje AzureAD) |

Může být určen autorita v případě potřeby.

Musíte registraci aplikace ve službě Azure AD a poskytnout vaší aplikaci přístup ke službě zásady ochrany aplikací:
* Informace o registraci aplikace s Azure AD najdete [tady](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
* Zkontrolujte, jestli jsou potom postup udělení oprávnění vaší aplikace pro Android ve službě app protection zásad (aplikace). Postupujte podle pokynů v [Začínáme s Intune SDK průvodce](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) v části "vaší aplikaci dáte přístup ke službě Intune app protection (volitelné)". 

Podívejte se také na požadavky pro [podmíněný přístup](#conditional-access), které najdete níže.


#### <a name="3-app-integrates-adal-but-does-not-support-brokered-authenticationdevice-wide-sso"></a>3. Aplikace integruje ADAL, ale nepodporuje zprostředkované ověřování/celém zařízení jednotné přihlašování

|Požadovaný parametr ADAL| Hodnota |
|--|--|
| ClientID | ClientID aplikace (u zaregistrovaných aplikací je generuje AzureAD) |
| SkipBroker | **True** (Pravda) |

V případě potřeby můžete zadat pole Authority a NonBrokerRedirectURI.

### <a name="conditional-access"></a>Podmíněný přístup

Podmíněný přístup je [funkce](https://docs.microsoft.com/azure/active-directory/develop/active-directory-conditional-access-developer) služby Azure Active Directory, pomocí níž je možné řídit přístup k prostředkům AAD. [Správci Intune mohou definovat pravidla podmíněného přístupu](https://docs.microsoft.com/intune/conditional-access), která umožní přístup k prostředkům pouze ze zařízení nebo aplikací spravovaných v Intune. Pokud chcete zajistit, že aplikace bude mít v případě potřeby přístup k prostředkům, postupujte podle kroků uvedených níže. Pokud vaše aplikace nevyžaduje přístupové tokeny AAD nebo používá pouze prostředky, které nelze chránit podmíněným přístupem, můžete tento postup přeskočit.

1. Postupujte podle [pokynů k integraci ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-android#how-to-use-this-library). 
   Zvláštní pozornost věnujte kroku 11, který se týká použití zprostředkovatele.
2. [Zaregistrujte si aplikaci ve službě Azure Active Directory] (https://docs.microsoft.com/azure/active-directory/active-directory-app-registration). 
   Identifikátor URI pro přesměrování najdete v pokynech k integraci ADAL uvedených výše.
3. Nastavte parametry metadat manifestu pro jednotlivé [běžné konfigurace ADAL](#common-adal-configurations), položka 2 výše.
4. Otestujte, že je vše nakonfigurováno správně. Uděláte to tak, že povolíte [podmíněný přístup na základě zařízení](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use) na portálu [Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExchangeConnectorMenu/aad/connectorType/2) a zkontrolujete následující:
    - Při přihlášení k aplikaci se zobrazí výzva k instalaci registraci Portálu společnosti Intune.
    - Po registraci se přihlášení k aplikaci úspěšně dokončí.
5. Jakmile se integrace sady Intune APP SDK dokončí, obraťte se na tým na adrese msintuneappsdk@microsoft.com se žádostí o přidání do seznamu schválených aplikací pro [podmíněný přístup na základě aplikace](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use#app-based-conditional-access).
6. Po přidání aplikace do seznamu schválených aplikací ji ověřte pomocí [konfigurace podmíněného přístupu na základě aplikace](https://docs.microsoft.com/intune/app-based-conditional-access-intune-create) a ujistěte se, že se přihlášení k aplikaci úspěšně dokončí.

## <a name="app-protection-policy-without-device-enrollment"></a>Zásady ochrany aplikací bez registrace zařízení

### <a name="overview"></a>Přehled
Zásady ochrany aplikací služby Intune bez registrace zařízení, označované také jako APP-WE nebo MAM-WE, umožňují správu aplikací přes Intune bez nutnosti registrace zařízení do Intune MDM. APP-WE funguje jak s registrací, tak i bez ní. Ačkoliv musí být na zařízení stále nainstalovaná aplikace Portál společnosti, nemusí se k ní uživatel přihlašovat ani dané zařízení registrovat.

> [!NOTE]
> Všechny aplikace musí podporovat zásady ochrany aplikací bez registrace zařízení.

### <a name="workflow"></a>Pracovní postup

Jakmile aplikace vytvoří nový uživatelský účet, měla by ho zaregistrovat ke správě sadou Intune App SDK. Ta zajistí podrobnosti registrace aplikace ke službě APP-WE, a pokud dojde k chybě, bude pokusy o registraci opakovat ve vhodných časových intervalech.

Aplikace se také může sady Intune App SDK dotazovat na stav zaregistrovaného uživatele, pokud potřebuje určit, jestli by měl být takovému uživateli zablokován přístup k podnikovému obsahu. Ke správě je možné zaregistrovat více účtů, ale aktivní registrace ke službě APP-WE je aktuálně možná vždy jen pro jeden účet. To znamená, že zásady ochrany aplikací se nemůžou vztahovat na více účtů aplikace současně.

Aplikace musí provést zpětné volání, aby mohla jménem sady SDK získat z knihovny ADAL příslušné přístupové tokeny. Předpokládá se, že aplikace už pro ověřování uživatelů ADAL využívá a získává vlastní přístupové tokeny.

Pokud aplikace zcela odebere účet, měla by ho také odregistrovat a tím aplikaci sdělit, že se na tohoto uživatele už nemají vztahovat zásady. Pokud byl uživatel zaregistrován ke službě MAM, dojde ke zrušení jeho registrace a vymazání aplikace.


### <a name="overview-of-app-requirements"></a>Přehled požadavků na aplikaci

Pro implementaci integrace služby APP-WE musí aplikace zaregistrovat uživatelský účet v sadě MAM SDK:

1. Aplikace _musí_ implementovat a zaregistrovat instanci rozhraní `MAMServiceAuthenticationCallback`. Instance zpětného volání by se měla do životního cyklu aplikace zaregistrovat co nejdříve (obvykle v metodě `onMAMCreate()` třídy aplikace).

2. Po vytvoření uživatelského účtu a úspěšném přihlášení uživatele k ADAL _musí_ aplikace volat `registerAccountForMAM()`.

3. Po odebrání uživatelského účtu by měla aplikace voláním `unregisterAccountForMAM()` odstranit účet ze správy Intune.

    > [!NOTE]
    > Pokud se uživatel z aplikace dočasně odhlásí, není nutné, aby aplikace `unregisterAccountForMAM()` volala. Volání by mohlo inicializovat vymazání, které by uživateli odebralo veškerá podniková data.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Všechna potřebná rozhraní API pro ověřování a registraci najdete v rozhraní `MAMEnrollmentManager`. Odkaz na `MAMEnrollmentManager` je možné získat tímto způsobem:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr
```

Je zaručeno, že vrácená instance rozhraní `MAMEnrollmentManager` nemá hodnotu null. Metody API spadají do dvou kategorií: **ověřování** a **registrace účtů**.

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

### <a name="account-authentication"></a>Ověřování účtů

V této části jsou popsány metody API pro ověřování, které jsou součástí rozhraní `MAMEnrollmentManager`, a způsob jejich použití.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Aby bylo možné povolit sadě SDK žádat token ADAL pro daného uživatele a ID prostředku, musí aplikace implementovat rozhraní `MAMServiceAuthenticationCallback`. Voláním metody `registerAuthenticationCallback()` musí být rozhraní `MAMEnrollmentManager` poskytnutá instance zpětného volání. V brzké fázi životního cyklu aplikace může být token potřeba k pokusům o registraci nebo ohlášení aktualizací zásad ochrany aplikací, takže zpětné volání je nejlepší zaregistrovat v metodě `onMAMCreate()` podtřídy `MAMApplication` aplikace.

2. Metoda `acquireToken()` by měla získat přístupový token pro požadované ID prostředku daného uživatele. Pokud ho získat nedokáže, měla by vrátit hodnotu null.

    > [!NOTE]
    > Ujistěte se, že vaše aplikace využívá `resourceId` a `aadId` parametry předány `acquireToken()` tak, aby získali správný token.

    ```
    class MAMAuthCallback implements MAMServiceAuthenticationCallback {
        public String acquireToken(String upn, String aadId, String resourceId) {
        return mAuthContext.acquireTokenSilentSync(resourceId, ClientID, aadId).getAccessToken();
        }
    }
    ```

3. V případě, že aplikace při volání metody `acquireToken()` sady SDK nedokáže token poskytnout (například tehdy, když se nezdaří bezobslužné ověření a není vhodná doba na zobrazení uživatelského rozhraní), může tak učinit později po volání metody `updateToken()`. Volání metody `updateToken()` musí kromě samotného tokenu předat také stejný hlavní název uživatele, ID AAD a ID prostředku, jako požadovalo předchozí volání (`acquireToken()`). Aplikace by měla tuto metodu volat co nejdříve poté, co dané zpětné volání vrátilo hodnotu null.

    > [!NOTE]
    > Sada SDK se bude snažit získat token pravidelným voláním metody `acquireToken()`, takže volání metody `updateToken()` není bezpodmínečně nutné. Ale je důrazně doporučujeme, jak může pomoct registrace a app protection zásad vrácení se změnami dokončit včas.


### <a name="account-registration"></a>Registrace účtů

V této části jsou popsány metody API pro registraci účtů, které jsou součástí rozhraní `MAMEnrollmentManager`, a způsob jejich použití.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Aby bylo možné zaregistrovat účet ke správě, měla by aplikace provést volání metody `registerAccountForMAM()`. Uživatelský účet definuje jeho hlavní název uživatele a ID uživatele služby AAD. K přidružení dat zápisu ke klientovi AAD příslušného uživatele je také potřeba ID klienta. Autorita uživatele mohou být rovněž poskytnuty Pokud chcete povolit registraci pro konkrétní suverénní cloudy; Další informace najdete v části [suverénní Cloud registrace](#sovereign-cloud-registration).  Sada SDK se může pokusit zaregistrovat aplikaci pro daného uživatele ve službě MAM. Pokud se registrace nezdaří, bude pokusy o registraci pravidelně opakovat až do doby, než dojde ke zrušení registrace účtu. Časový interval mezi jednotlivými pokusy je obvykle 12 až 24 hodin. Sada SDK informuje o stavu pokusů o registraci asynchronně prostřednictvím oznámení.

2. Protože ověřování AAD je povinné, bude nejlepší zaregistrovat uživatelský účet je poté, co uživatel je přihlášený k aplikaci a úspěšném ověření pomocí ADAL. AAD ID a ID tenanta daného uživatele jsou vráceny z ověřovací volání ADAL jako součást [ `AuthenticationResult` ](https://github.com/AzureAD/azure-activedirectory-library-for-android) objektu.
    * ID klienta pochází z metody `AuthenticationResult.getTenantID()`.
    * Informace o uživateli se nachází v podobjektu typu `UserInfo`, který pochází z `AuthenticationResult.getUserInfo()`, a ID uživatele AAD se získává z tohoto objektu voláním metody `UserInfo.getUserId()`.

3. Pokud chcete zrušit registraci účtu ve správě Intune, měla by aplikace provést volání metody `unregisterAccountForMAM()`. Pokud byl účet úspěšně zaregistrován a je spravován, sada SDK zruší jeho registraci a vymaže jeho data. Kromě toho se zastaví pravidelné pokusy o registraci. Sada SDK informuje o stavu žádosti o zrušení registrace asynchronně prostřednictvím oznámení.

### <a name="sovereign-cloud-registration"></a>Registrace v suverénním cloudu

Aplikace [podporující suverénní cloud](https://www.microsoft.com/trustcenter/cloudservices/nationalcloud) **musí** poskytovat `authority` metodě `registerAccountForMAM()`.  Toho lze dosáhnout tím, že v parametrech [1.14.0+](https://github.com/AzureAD/azure-activedirectory-library-for-android/releases/tag/v1.14.0) acquireToken extraQueryParameters knihovny ADAL poskytnete `instance_aware=true` a pak vyvoláte metodu `getAuthority()` u výsledku AuthenticationCallback AuthenticationResult.

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
> Nenastavujte `com.microsoft.intune.mam.aad.Authority` metadata položky v souboru AndroidManifest.xml.

> [!NOTE]
> Ujistěte se, že je autorita správně nastavena v metodě `MAMServiceAuthenticationCallback::acquireToken()`.

#### <a name="currently-supported-sovereign-clouds"></a>Momentálně podporované suverénní cloudy

1. Arlington

### <a name="important-implementation-notes"></a>Důležité poznámky k implementaci

#### <a name="authentication"></a>Ověřování

* Když aplikace volá `registerAccountForMAM()`, může brzy poté obdržet zpětné volání na rozhraní `MAMServiceAuthenticationCallback`, ale na odlišném vláknu. V ideálním případě aplikace získat vlastní token z knihovny ADAL ještě před registrací účtu, aby se urychlilo získání požadovaný token. Pokud aplikace vrátí platný token ze zpětného volání, registrace bude pokračovat a aplikace získá konečný výsledek prostřednictvím oznámení.

* V případě, že aplikace nevrátí platný token AAD, konečný výsledek pokusu o registraci bude `AUTHENTICATION_NEEDED`. Pokud aplikace obdrží tento výsledek prostřednictvím oznámení, se důrazně doporučuje urychlit proces registrace získáním token pro daného uživatele a prostředek již v minulosti požádali z `acquireToken()` a volání `updateToken()` metoda zahájit Opakujte proces registrace.

* Za účelem získání tokenu pro pravidelná ohlášení aktualizací zásad ochrany aplikací bude také voláno rozhraní `MAMServiceAuthenticationCallback` zaregistrované aplikací. Pokud aplikace nedokáže na žádost token poskytnout, nedostane oznámení, ale měla by se pokusit získat token a co nejdříve provést volání `updateToken()`, aby se urychlil proces ohlašování. V případě neposkytnutí tokenu se při dalším pokusu o ohlášení zpětné volání zopakuje.

* Podpora suverénních cloudů vyžaduje poskytování autority.

#### <a name="registration"></a>Registrace

* Pro usnadnění vaší práce jsou metody registrace idempotentní. `registerAccountForMAM()` například zaregistruje účet a pokusí se o registraci aplikace jen v případě, že účet dosud zaregistrovaný není. Podobně `unregisterAccountForMAM()` zruší registraci účtu jen tehdy, že je aktuálně zaregistrovaný. Následná volání nepředstavují operace, takže opakovaná volání těchto metod nejsou na škodu. Kromě toho není zaručena souvztažnost mezi voláním těchto metod a oznámení o výsledku: To znamená pokud `registerAccountForMAM` nazývá identitou, která je už zaregistrovaný, oznámení nemusí poslat znovu pro danou identitu. Může se stát, že se odešlou oznámení, která neodpovídají žádným voláním těchto metod, protože sada SDK může na pozadí opakovat pokusy o registraci, stejně jako může být zrušení registrace aktivováno žádostí o vymazání odeslanou službou Intune.

* Metody registrace můžou být volány u libovolného počtu identit, ale úspěšně je možné momentálně zaregistrovat vždy jen jeden uživatelský účet. Pokud se současně nebo přibližně ve stejnou dobu registruje více uživatelských účtů s licencí pro službu Intune, na které se vztahují zásady ochrany aplikací, není jisté, který z nich se skutečně zaregistruje.

* Pokud se chcete dozvědět, jestli je účet zaregistrovaný, můžete zadat dotaz na `MAMEnrollmentManager`. Pomocí metody `getRegisteredAccountStatus` také zjistíte jeho aktuální stav. Pokud účet není zaregistrovaný, vrátí metoda výsledek **null**. V opačném případě vrátí metoda stav účtu v rámci výčtu `MAMEnrollmentManager.Result`.

### <a name="result-and-status-codes"></a>Kódy výsledku a stavové kódy

Po registraci se účet nachází ve stavu `PENDING`, který značí, že prvotní pokus o registraci ve službě MAM ještě není dokončený. Jakmile se pokus o registraci dokončí, odešle se oznámení obsahující některý z kódů výsledku uvedených v tabulce níže. Kromě toho vrátí metoda `getRegisteredAccountStatus()` informaci o stavu účtu, aby mohla aplikace vždy určit, jestli nemá daný uživatel zablokovaný přístup k podnikovému obsahu. Pokud se pokus o registraci nezdaří, stav účtu se může postupem času změnit s tím, jak sada SDK opakuje další pokusy na pozadí.

|Kód výsledku | Vysvětlení |
| -- | -- |
|AUTHORIZATION_NEEDED | Tento výsledek značí, že instance `MAMServiceAuthenticationCallback` zaregistrovaná aplikací neposkytla token, nebo že je token neplatný.  Aplikace by měla získat platný token a pokud možno provést volání `updateToken()`. |
| NOT_LICENSED | Uživatel nemá licenci na službu Intune, nebo byl pokus o spojení se službou Intune MAM neúspěšný.  Aplikace by měla dál běžet v nespravovaném (normálním) stavu a uživatel by neměl být zablokovaný.  Pro případ, že by uživatel v budoucnu licenci získal, budou pravidelně probíhat pokusy o registraci. |
| ENROLLMENT_SUCCEEDED | Pokus o registraci proběhl úspěšně nebo už je uživatel zaregistrovaný.  V případě úspěšné registrace se ještě před tímto oznámením zašle oznámení o aktualizaci zásad.  Uživatel by měl mít povolený přístup k podnikovým datům. |
| ENROLLMENT_FAILED | Pokus o registraci selhal.  Další podrobnosti najdete v protokolech zařízení.  V tomto stavu by aplikace neměla umožňovat přístup k podnikovému obsahu, protože dříve určila, že má uživatel licenci na služby Intune.|
| WRONG_USER | Ke službě MAM může aplikaci zaregistrovat jen jeden uživatel na dané zařízení.  Aby bylo možné se úspěšně zaregistrovat jako jiný uživatel, musí se nejprve zrušit registrace všech zaregistrovaných aplikací.  Jinak se aplikace musí zaregistrovat jako primární uživatel.  Tato kontrola probíhá po kontrole licence, takže by uživatel neměl mít přístup k podnikovým datům až do chvíle, kdy se aplikace úspěšně zaregistruje.|
| UNENROLLMENT_SUCCEEDED | Zrušení registrace bylo úspěšné.|
| UNENROLLMENT_FAILED | Žádost o zrušení registrace selhala.  Další podrobnosti najdete v protokolech zařízení. |
| PENDING | Probíhá počáteční pokus o registraci pro daného uživatele.  Aplikace může – ale také nemusí – zablokovat přístup k podnikovým datům až do chvíle, kdy se dozví výsledek registrace. |
| COMPANY_PORTAL_REQUIRED | Uživatel má licenci na službu Intune, ale aplikaci není možné zaregistrovat, dokud se na zařízení nenainstaluje aplikace Portál společnosti. Sada Intune App SDK se pokusí zablokovat pro daného uživatele přístup k aplikaci a přesměrovat ho na instalaci Portálu společnosti (podrobnosti najdete níže). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Potlačení výzvy k instalaci aplikace Portál společnosti (volitelné)

Při obdržení výsledku `COMPANY_PORTAL_REQUIRED` zablokuje sada SDK aktivity využívající identitu, pro kterou byla registrace žádána. Místo toho sada SDK zajistí, aby tyto aktivity zobrazily výzvu ke stažení aplikace Portál společnosti. Pokud nechcete, aby k takovému chování došlo, můžou aktivity implementovat metodu `MAMActivity.onMAMCompanyPortalRequired`.

Tato metoda se volá ještě před tím, než sada SDK zobrazí svou výchozí zprávu o blokování. Pokud aplikace změní identitu aktivity nebo zruší registraci uživatele, který se pokusil o registraci, sada SDK tuto aktivitu nezablokuje. V takové situaci je na aplikaci, aby předešla úniku podnikových dat. Identitu aktivity budou moct změnit pouze aplikace s více identitami (popsané dále).

Pokud explicitně nezdědíte `MAMActivity` (protože tuto změnu provedou nástroje sestavení), ale potřebujete toto oznámení zpracovat, můžete místo toho implementovat `MAMActivityBlockingListener`.

### <a name="notifications"></a>Oznámení

Pokud aplikace zaregistruje oznámení typu **MAM_ENROLLMENT_RESULT**, `MAMEnrollmentNotification` se odešlou, aby bylo možné informovat aplikaci o dokončení žádosti o registraci. Prostřednictvím rozhraní `MAMNotificationReceiver` se bude zasílat `MAMEnrollmentNotification` (viz část [Registrace k oznámením z SDK](#register-for-notifications-from-the-sdk)).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}
```

Metoda `getEnrollmentResult()` vrací výsledek žádosti o registraci.  Vzhledem k tomu, že `MAMEnrollmentNotification` rozšiřuje `MAMUserNotification`, bude také k dispozici informace o identitě uživatele, za kterého byl pokus o registraci proveden. Aby bylo možné dostávat tato oznámení, musí aplikace implementovat rozhraní `MAMNotificationReceiver`. Další informace o oznámeních najdete v části [Registrace k oznámením z SDK](#register-for-notifications-from-the-sdk).

Při přijetí oznámení o registraci, ale nezmění se ve všech případech se může změnit stav zaregistrovaného uživatelského účtu (například pokud `AUTHORIZATION_NEEDED` přijetí oznámení po informativnějším výsledku, jako `WRONG_USER`, dál Výsledek bude udržovat jako stav účtu).  Po úspěšné registraci účtu se stav zůstanou jako `ENROLLMENT_SUCCEEDED` dokud účet je zrušit nebo nevymažete.

Při přijetí oznámení o registraci, ale nezmění se ve všech případech se může změnit stav zaregistrovaného uživatelského účtu (například pokud `AUTHORIZATION_NEEDED` přijetí oznámení po informativnějším výsledku, jako `WRONG_USER`, dál Výsledek bude udržovat jako stav účtu).  Po úspěšné registraci účtu se stav zůstanou jako `ENROLLMENT_SUCCEEDED` dokud účet je zrušit nebo nevymažete.

## <a name="app-ca-with-policy-assurance"></a>Podmíněný přístup aplikací s Assurance zásad

### <a name="overview"></a>Přehled
S aplikací podmíněným Přístupem (podmíněný přístup) se Assurance zásady je přístup k prostředkům conditionalized na použití zásad ochrany aplikací Intune.  AAD vynucuje tato aplikace je zaregistrovaná a spravovaná aplikace před udělením token pro přístup k Certifikační autoritu aplikace pomocí zásad Assurance chráněného prostředku.  Aplikace je potřeba použít zprostředkovatele ADAL pro získání tokenu a instalační program je stejný, jak je popsáno výše v [podmíněného přístupu](#conditional-access)

### <a name="adal-changes"></a>ADAL změny
Knihovna ADAL má nový kód chyby informuje aplikaci, která způsobila selhání k získání tokenu nedodržení předpisů pomocí správy aplikací.  Pokud aplikace obdrží tento kód chyby, je potřeba volat sady SDK se pokusit opravit registrace aplikace a použití zásad dodržování předpisů. Se přijal výjimku `onError()` metoda ADAL `AuthenticationCallback`a bude mít kód chyby: `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED`.  V takovém případě lze převést výjimky na `IntuneAppProtectionPolicyRequiredException`, ze které dalších parametrů může být extrahována pro použití v nápravou dodržování předpisů (viz následující ukázka kódu). Po úspěšném náprava aplikace můžete znovu zkusit získání tokenu pomocí ADAL.

> [!NOTE]
> Tento nový kód chyby a další podporu pro aplikaci certifikační Autority se zásady Assurance vyžadují verzi 1.15.0 (nebo vyšší) knihovny ADAL.

### <a name="mamcompliancemanager"></a>MAMComplianceManager

`MAMComplianceManager` Rozhraní se používá při přijetí chyby požadované zásady z ADAL.  Obsahuje `remediateCompliance()` metodu, která by měla být volána pokusu převést aplikaci do vyhovujícího stavu. Odkaz na `MAMComplianceManager` je možné získat tímto způsobem:

```java
MAMComplianceManager mgr = MAMComponents.get(MAMComplianceManager.class);

// make use of mgr
```

Je zaručeno, že vrácená instance rozhraní `MAMComplianceManager` nemá hodnotu null.

```java
package com.microsoft.intune.mam.policy;

public interface MAMComplianceManager {
    void remediateCompliance(String upn, String aadId, String tenantId, String authority, boolean showUX);
}
```

`remediateCompliance()` Metoda je volána k pokusí aplikaci pod správu splňují podmínky pro AAD poskytnout požadovaný token.  První čtyři parametry může být extrahována z výjimky přijatých ADAL `AuthenticationCallback.onError()` – metoda (viz následující ukázka kódu).  Poslední parametr je logická hodnota, která určuje, zda je zobrazen uživatelské prostředí při pokusu o dodržování předpisů.  Toto je jednoduché blokujících průběh styl rozhraní zadané jako výchozí pro aplikace, které nemají věcí a potřebovali si zobrazit vlastní uživatelské prostředí při této operaci.  Jenom se zablokuje, zatímco probíhá nápravy dodržování předpisů a které nezobrazí konečný výsledek.  Aplikace by měla zaregistrovat příjemce oznámení pro zpracování úspěšné nebo neúspěšné pokusy o nápravy dodržování předpisů (viz níže).

`remediateCompliance()` Metoda může provádět registrace MAM jako součást vytváření dodržování předpisů.  Aplikace může přijímat oznámení o registraci, pokud zaregistroval příjemce oznámení pro registraci oznámení.  Zaregistrované aplikace `MAMServiceAuthenticationCallback` bude mít jeho `acquireToken()` metodu volá za účelem získání tokenu pro registrace MAM. `acquireToken()` bude volána před provedením aplikace získala vlastní token, tak se účetnictví nebo účet vytvoření úkoly, které aplikace provádí po úspěšném získání tokenu nemusí mít dosud neudělali.  Zpětné volání musí být v tomto případě získat token.  Pokud se nedá vrátit tokenu z `acquireToken()`, se nezdaří pokus o nápravy dodržování předpisů.  Při volání `updateToken()` později pomocí platného tokenu pro požadovaný prostředek se nápravy dodržování předpisů se provede hned s daným tokenem.

> [!NOTE]
> Získání tokenu služby tichou bude stále možné v `acquireToken()` vzhledem k tomu, že uživatel bude mít již byl na základě instalace zprostředkovatele a registrace zařízení před `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED` přijetí chyby.  Výsledkem zprostředkovatele s platnou obnovovací token v mezipaměti, umožňuje bezobslužné acqisition nedokáže proběhla úspěšně.

Tady je ukázka pro příjem zásad vyžaduje Chyba v `AuthenticationCallback.onError()` metoda a volání `MAMComplianceManager` chybu zpracovat.

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

Pokud aplikace zaregistruje oznámení typu **COMPLIANCE_STATUS**, `MAMComplianceNotification` se odešlou, aby bylo možné informovat aplikaci konečný stav pokusů o nápravu dodržování předpisů. Prostřednictvím rozhraní `MAMNotificationReceiver` se bude zasílat `MAMComplianceNotification` (viz část [Registrace k oznámením z SDK](#register-for-notifications-from-the-sdk)).

```java
public interface MAMComplianceNotification extends MAMUserNotification {
    MAMCAComplianceStatus getComplianceStatus();
    String getComplianceErrorTitle();
    String getComplianceErrorMessage();
}
```

`getComplianceStatus()` Metoda vrací výsledek pokusu o nápravy dodržování předpisů jako hodnotu z `MAMCAComplianceStatus` výčtu.

|Stavový kód | Vysvětlení |
| -- | -- |
| NEZNÁMÝ | Stav není znám. To může znamenat z důvodu neočekávané chyby. Další informace najdete v protokolech portálu společnosti. |
| VYHOVUJÍCÍ | Dodržování předpisů nichž oprava proběhla úspěšně a aplikace je teď kompatibilní se zásadami. ADAL pořízení tokenu je třeba opakovat. |
| NOT_COMPLIANT | Opravit dodržování předpisů se nezdařilo.  Aplikace není kompatibilní s a ADAL získání tokenu by neměl opakovat, dokud nebude opravena chybového stavu.  Další informace o chybě se MAMComplianceNotification neposílají. |
| SERVICE_FAILURE | Došlo k chybě při pokusu o načtení dat dodržování předpisů z služby Intune. Další informace najdete v protokolech portálu společnosti. |
| NETWORK_FAILURE | Došlo k chybě připojení ke službě Intune. Aplikace by měl zkuste jeho získání tokenu znovu, když se obnoví připojení k síti. |
| CLIENT_ERROR | Pokus o dodržování předpisů napravit se nezdařil z nějakého důvodu související s klientem.  Například žádný token nebo nesprávné uživatel. Další informace o chybě se MAMComplianceNotification neposílají. |
| PENDING | Pokus o dodržování předpisů napravit se nezdařila, protože odpověď na stav kdyby byla přijata ze služby ještě, když byl překročen časový limit. Aplikace by měla zkuste jeho získání tokenu znovu později. |
| COMPANY_PORTAL_REQUIRED | Aplikace portál společnosti musí být nainstalovaný na zařízení mohl nápravy dodržování předpisů na úspěšné.  Pokud portál společnosti je už nainstalovaný na zařízení, aplikace se musí restartovat.  V takovém případě dialogové okno se zobrazí s žádostí o aplikaci restartovat. |

Pokud je stav dodržování předpisů `MAMCAComplianceStatus.COMPLIANT`, aplikace by mělo zahájit znovu její původní získání tokenu (pro vlastní prostředek). Pokud nápravy dodržování předpisů se nezdařilo, `getComplianceErrorTitle()` a `getComplianceErrorMessage()` metody vrátí lokalizované řetězce, které aplikace mohou zobrazit koncovým uživatelům, pokud se zvolí.  Většina případy chyb nejsou odstranitelné aplikace, takže pro tomto obecném případě může být vhodné přebírat služby při vytváření účtů nebo přihlášení a umožnit uživateli a zkuste to znovu později.  Pokud selhání je trvalý, protokoly MAM může pomoci určit příčinu.  Koncový uživatel může odeslat protokoly pomocí pokynů nalezen [tady](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android "protokolů firemní podpoře e-mailem").

Protože `MAMComplianceNotification` rozšiřuje `MAMUserNotification`, identitu uživatele, u kterého došlo k pokusu o opravě je také k dispozici.

Tady je příklad použití anonymní třídy k implementaci rozhraní MAMNotificationReceiver příjemce registrace:

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
> Příjemce oznámení musíte zaregistrovat před voláním `remediateCompliance()` , aby spor, který může mít za následek oznámení se vynechalo.

### <a name="implementation-notes"></a>Poznámky k implementaci

> [!NOTE]
> Aplikace `MAMServiceAuthenticationCallback.acquireToken()` musí projít metoda *true* pro novou `forceRefresh` příznak `acquireTokenSilentSync()` můžete vynutit aktualizaci ze zprostředkovatele.  Toto je ukládání do mezipaměti problém s tokeny ADAL, které můžou ovlivnit tokeny služby MAM. Obecně platí to vypadá takto:
```java
AuthenticationResult result = acquireTokenSilentSync(resourceId, clientId, userId, /* forceRefresh */ true);
```

> [!NOTE]
> Pokud chcete zobrazit vlastní blokující uživatelské prostředí při pokusu o nápravnou, je třeba předat *false* pro parametr showUX `remediateCompliance()`. Musíte zajistit zobrazit vaše uživatelského rozhraní a zaregistrujte vašeho naslouchací proces oznámení před voláním `remediateCompliance()`.  To zabrání časování, kde oznámení může chybět Pokud `remediateCompliance()` velmi rychle se nezdaří.  Například `onCreate()` nebo `onMAMCreate()` metoda podtřídy aktivity je ideálním místem pro registraci naslouchací proces oznámení a pak vyvolejte `remediateCompliance()`.  Parametry pro `remediateCompliance()` lze předat do vašeho uživatelského prostředí jako záměru funkce.  Při přijetí oznámení o stavu dodržování předpisů, můžete zobrazit výsledek nebo jednoduše dokončení aktivity.

> [!NOTE]
> `remediateCompliance()` zaregistruje účet a pokus o registraci.  Jakmile je hlavní token získán, volání `registerAccountForMAM()` není nezbytné, ale není na to škodu. Na druhé straně, pokud se aplikaci nepodaří získat jeho token a chce odebrat uživatelský účet, musí volat `unregisterAccountForMAM()` chcete účet odebrat a zabránit registraci opakování na pozadí.

## <a name="protecting-backup-data"></a>Ochrana dat zálohy

Od verze Android Marshmallow (API 23) má Android dvě možnosti, jak může aplikace zálohovat svá data. Obě možnosti se dají použít pro vaši aplikaci a k tomu, aby se zajistila správná implementace ochrany dat Intune, je potřeba udělat různé kroky. Přehled akcí požadovaných pro zajištění správné ochrany dat najdete v tabulce níže.  Další informace o metodách zálohování najdete v [průvodci rozhraním Android API](https://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Automatické zálohování pro aplikace

Na zařízeních s Androidem Marshmallow začal Android nabízet aplikacím [automatické úplné zálohování](https://developer.android.com/guide/topics/data/autobackup.html) na Disk Google bez ohledu na cílové rozhraní API aplikace. Pokud v souboru AndroidManifest.xml, explicitně nastavíte `android:allowBackup` na hodnotu **False**, Android nikdy nezařadí vaši aplikaci do fronty pro zálohy a podniková data zůstanou v aplikaci. V takovém případě není potřeba žádná další akce.

Ve výchozím nastavení je ale atribut `android:allowBackup` nastavený na hodnotu True, i když v souboru manifestu není specifikovaný parametr `android:allowBackup`. To znamená, že všechna data aplikace se automaticky zálohují do účtu Disku Google uživatele. Je to výchozí chování, které představuje určité **riziko úniku dat**. Proto sada SDK vyžaduje níže uvedené změny, které zajistí použití ochrany dat.  Pokud chcete svoji aplikaci spouštět na zařízeních s Androidem Marshmallow, měli byste postupovat podle níže uvedených pokynů k zajištění řádné ochrany zákaznických dat.  

Intune vám umožňuje využívat všechny [funkce automatického zálohování](https://developer.android.com/guide/topics/data/autobackup.html), které nabízí Android, včetně možnosti definovat vlastní pravidla v XML, musíte ale zabezpečit svoje data podle tohoto postupu:

1. Pokud vaše aplikace **nepoužívá** vlastní třídu BackupAgent, můžete použitím výchozí třídy MAMBackupAgent povolit automatické úplné zálohy, které splňují zásady Intune. Vložte do manifestu aplikace tento kód:

    ```xml
    android:fullBackupOnly="true"
    android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```


2. **[Volitelné]** Pokud implementujete nepovinnou vlastní třídu BackupAgent, zkontrolujte, že používáte MAMBackupAgent nebo MAMBackupAgentHelper. Více informací najdete v dalších částech. Zvažte možnost použití agenta Intune **MAMDefaultFullBackupAgent** (viz krok 1), který umožňuje v systému Android M a novějších verzích snadné zálohování.

3. Až se rozhodnete, jaký typ plné zálohy by měla vaše aplikace obdržet (nefiltrovaný, filtrovaný nebo žádný), budete muset v aplikaci nastavit atribut `android:fullBackupContent` na hodnotu True, False nebo prostředek XML.

4. Následně _**musíte**_ do značky metadat s názvem `com.microsoft.intune.mam.FullBackupContent` ve vašem manifestu zkopírovat všechno, co vložíte do `android:fullBackupContent`.

    **Příklad 1**: Pokud chcete, aby aplikace měla úplné zálohy bez vyloučení, jednak nastaveny `android:fullBackupContent` atribut a `com.microsoft.intune.mam.FullBackupContent` značku metadat na **true**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Příklad 2**: Pokud chcete aplikaci tak, aby pomocí jeho vlastní třídu BackupAgent a nechcete úplné, Intune zásady vyhovují řadě požadavků a automatické zálohování, je nutné nastavit atribut a značku metadat na **false**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Příklad 3**: Pokud chcete, aby aplikace měla úplné zálohy podle vašich vlastních pravidel definovaných v souboru XML, nastavte atribut a značku metadat na stejný prostředek XML:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Zálohování páru klíč-hodnota

Možnost [zálohování páru klíč-hodnota](https://developer.android.com/guide/topics/data/keyvaluebackup.html) zálohuje data aplikací do služby [Android Backup Service](https://developer.android.com/google/backup/index.html) a je k dispozici pro všechna rozhraní API od verze 8. Objem dat na uživatele aplikace je omezen na 5 MB. Pokud zálohování páru klíč-hodnota využíváte, použijte třídu **BackupAgentHelper** nebo **BackupAgent**.

### <a name="backupagenthelper"></a>BackupAgentHelper

Implementace třídy BackupAgentHelper je jednodušší než implementace třídy BackupAgent, a to jak z hlediska nativních funkcí Androidu, tak z hlediska integrace služby Intune MAM. BackupAgentHelper umožňuje vývojáři registrovat celé soubory a sdílené předvolby do třídy **FileBackupHelper** a **SharedPreferencesBackupHelper**, které se pak při vytvoření přidají do třídy BackupAgentHelper. Postup použití třídy BackupAgentHelper se službou Intune MAM je následující:

1. Pokud chcete využívat zálohu více identit s třídou BackupAgentHelper, přečtěte si pokyny o [rozšíření třídy BackupAgentHelper ](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper) v příručce pro Android.

2. Rozšiřte třídu BackupAgentHelper, FileBackupHelper nebo SharedPreferencesBackupHelper na příslušný ekvivalent ve službě MAM.

|Třída Androidu | Ekvivalent ve službě MAM |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Pokud se budete držet těchto pokynů, dosáhněte úspěšného zálohování a obnovy více identit.

### <a name="backupagent"></a>BackupAgent

Třída BackupAgent umožňuje explicitnější určení zálohovaných dat. Protože vývojář za implementaci do velké míry zodpovídá, vyžaduje se pro zajištění odpovídající ochrany dat ze služby Intune více kroků. Většina práce bude na vás jakožto na vývojáři a integrace služby Intune se tak zapojí o něco víc.

**Integrace služby MAM:**

1. Aby byla vaše implementace třídy BackupAgent v souladu s pokyny Androidu, pozorně si v příručce pro Android přečtěte informace o [zálohování páru klíč-hodnota](https://developer.android.com/guide/topics/data/keyvaluebackup.html) a hlavně o [rozšíření třídy BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent).

2. Nechte třídu rozšířit na `MAMBackupAgent`.

**Zálohování více identit:**

1. Před zahájením zálohování zkontrolujte, že soubory nebo datové vyrovnávací paměti, kterých se bude tato akce týkat, **mají správcem IT povolené zálohování** ve scénářích s více identitami. Aby to bylo možné určit, nabízíme vám funkci `isBackupAllowed` v `MAMFileProtectionManager` a `MAMDataProtectionManager`. Pokud soubor nebo datová vyrovnávací paměť nemá zálohování povolené, pak byste neměli pokračovat v jejich zahrnování do zálohování.

2. Když v určitém okamžiku během zálohování chcete zálohovat identity pro soubory zkontrolované v kroku 1, je potřeba volat `backupMAMFileIdentity(BackupDataOutput data, File … files)` se soubory, ze kterých plánujete extrahovat data. Tato akce automaticky vytvoří nové entity zálohování a zapíše je za vás do `BackupDataOutput` . Při obnovení se tyto entity automaticky využijí.

**Obnova více identit:**

V části [Rozšíření třídy BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) příručky zálohování dat najdete obecný algoritmus pro obnovu dat vaší aplikace a ukázku kódu. Pokud má obnova více identit proběhnout úspěšně, je potřeba dodržet obecnou strukturu danou tímto vzorovým kódem a věnovat zvláštní pozornost těmto bodům:

1. Je nutné použít smyčku `while(data.readNextHeader())`*, která projde entity zálohování.

2. Pokud se `data.getKey()`* neshoduje s klíčem zapsaným v `onBackup`, je nutné volat `data.skipEntityData()`*. Pokud tento krok neprovedete, záloha nemusí proběhnout úspěšně.

3. Při zobrazování entit zálohování se v konstruktoru `while(data.readNextHeader())`* nevracejte, protože automaticky zapsané entity budou ztraceny.

* Kde `data` je název místní proměnné pro **MAMBackupDataInput** předaný aplikaci při obnovení.

## <a name="multi-identity-optional"></a>Více identit (volitelné)

### <a name="overview"></a>Přehled
Intune App SDK ve výchozím nastavení uplatní zásady na aplikaci jako celek. Možnost používat více identit je volitelná funkce ochrany aplikací Intune, kterou můžete zapnout, pokud chcete zásady uplatňovat na úrovni jednotlivých identit. K tomu je od aplikace potřeba mnohem větší účast než u ostatních funkcí ochrany aplikací.

> [!NOTE]
>  V případě nesprávného zapojení aplikace může dojít k únikům dat a dalším potížím v souvislosti se zabezpečením.

Jakmile uživatel zařízení nebo aplikaci zaregistruje, zaregistruje tuto identitu také sada SDK a bude ji považovat za primární spravovanou identitu Intune. Ostatní uživatelé v aplikaci budou považováni za nespravované s nastavením zásad bez omezení.

> [!NOTE]
> V současné době je podporována jen jedna spravovaná identita Intune pro každé zařízení.

Identita se definuje jako řetězec. Identity **rozlišují malá a velká písmena**, ale žádosti odeslané sadě SDK je nemusí vrátit se stejnou velikostí písmen, s jakou byly nastaveny.

Pokud chce aplikace změnit aktivní identitu, musí informovat sadu *SDK*. V některých případech SDK také upozorní aplikaci, že je nutná změna identity. Ve většině případů však správa MAM nemůže vědět, jaká data se zobrazují v uživatelském rozhraní nebo používají u vlákna v daném okamžiku, a spoléhá na to, že aplikace nastaví správnou identitu, která zabrání úniku dat. V následujících částech najdete některé konkrétní scénáře, které vyžadují akci aplikace.

### <a name="enabling-multi-identity"></a>Povolení více identit

Ve výchozím nastavení se všechny aplikace považují za aplikace s jedinou identitou. U aplikace můžete deklarovat, že dokáže rozpoznat více identit tím, že do souboru AndroidManifest.xml umístíte následující metadata.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Nastavení Identity

Vývojáři můžou nastavit identitu uživatele aplikace na těchto úrovních se sestupnou prioritou:

  1. Úroveň vlákna
  2. `Context` (obecně `Activity`) úroveň
  3. Úroveň procesu

Identita nastavená na úrovni vlákna nahrazuje identitu nastavenou na úrovni objektu `Context`, která nahrazuje identitu nastavenou na úrovni procesu. Identita nastavená u `Context` slouží jen u vhodných přidružených scénářů. Vstupně-výstupní operace se soubory, například nemají přiřazený `Context`. Nejčastěji budou aplikace nastavovat `Context` identitu na `Activity`. Aplikace *musí* není-li zobrazit data pro spravovanou identitu `Activity` identita je nastavená na stejná identita. Obecně je identita na úrovni procesu užitečná pouze tehdy, když pracuje aplikace ve všech vláknech vždy jen s jediným uživatelem. Řada aplikací tuto možnost nemusí potřebovat využít.

Pokud vaše aplikace používá `Application` kontext k získání systémových služeb, ujistěte se, že byla nastavena identita vlákna nebo procesu a mají nastavit identitu uživatelského rozhraní ve vaší aplikaci `Application` kontextu.

Zpracovat speciální případy při aktualizaci identita uživatelského rozhraní s `setUIPolicyIdentity` nebo `switchMAMIdentity`, obě metody lze předat sadu `IdentitySwitchOption` hodnoty.

* `IGNORE_INTENT`: Použijte v případě žádosti o přepnutí identity, který se má ignorovat záměr přidružené k aktuální aktivitu.
  Příklad:

  1. Vaše aplikace obdrží záměru ze spravovaných identit obsahující spravovaného dokumentu a aplikace se zobrazí dokument.
  2. Uživatel přepne na své osobní identity, takže vaše aplikace požaduje Přepnutí identity uživatelského rozhraní. V osobní identitě vaší aplikace je už zobrazení dokumentu, proto použijete `IGNORE_INTENT` při vyžadování Přepnutí identity.

  Pokud ne sadu SDK bude předpokládat, že nejnovější záměr je stále používáno v aplikaci. To způsobí, že zásady pro novou identitu považovat za účelem příchozích dat a používat svoji identitu.

>[!NOTE]
> Protože `CLIPBOARD_SERVICE` se používá pro operace uživatelského rozhraní, sady SDK používá identita uživatelského rozhraní pro aktivity popředí `ClipboardManager` operace.
> Následující metody u třídy `MAMPolicyManager` můžete použít k nastavení identity a načtení dříve nastavených hodnot identity.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

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
> Identitu aplikace můžete vymazat tím, že ji nastavíte na hodnotu null.
>
> Prázdný řetězec může sloužit jako identita, která nikdy nebude mít zásady ochrany aplikací.

#### <a name="results"></a>Výsledky
Všechny metody nastavení identity vrátí zpět výsledné hodnoty přes `MAMIdentitySwitchResult`. Vrátit se můžou čtyři hodnoty:

| Vrácená hodnota | Scénář |
|--|--|
| SUCCEEDED | Změna identity byla úspěšná. |
| NOT_ALLOWED  | Změna identity není povolená. Dochází k tomu při pokusu o nastavení identity uživatelského rozhraní (Context), když je u aktuálního vlákna nastavená jiná identita. |
| CANCELLED | Uživatel zrušil změnu identity stisknutím tlačítka Zpět po zobrazení výzvy k zadání kódu PIN / ověřování. |
| FAILED | Změna identity se z neznámého důvodu nezdařila.|

Aplikace by měly zajistit, že přepnutí identity úspěšné před zobrazením nebo použitím podnikových dat. V současné době bude přepnutí identit procesů a vláken u aplikací s povolenými více identitami vždy úspěšné, vyhrazujeme si ale právo přidat podmínky týkající se chyb. Přepnutí identity uživatelského rozhraní nemusí být úspěšné při neplatných argumentech, pokud by došlo ke konfliktu s identitou vlákna, nebo v případě, že uživatel zruší akci, když se požaduje podmíněné spuštění (například stiskne tlačítko Zpět na obrazovce PIN kódu).


V případě nastavení identity objektu Context je výsledek nahlášený asynchronně. Pokud je objektem Context aktivita, sada SDK nebude vědět, jestli byla změna identity úspěšná, a to až do podmíněného spuštění, které může vyžadovat, aby uživatel zadal kód PIN nebo podnikové přihlašovací údaje. Aby se dosáhlo tohoto výsledku, měla by aplikace implementovat `MAMSetUIIdentityCallback`. Pro tento parametr můžete předat hodnotu null.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Namísto volání `MAMPolicyManager.setUIPolicyIdentity` můžete identitu aktivity také nastavit přímo díky metodě na `MAMActivity`. Použijte tuto metodu:

```java
     public final void switchMAMIdentity(final String newIdentity, final EnumSet<IdentitySwitchOption> options);
```

Metodu na `MAMActivity` můžete také přepsat, aby mohla být aplikace informovaná o výsledku pokusů změnit identitu této aktivity.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

Je-li přepsat `onSwitchMAMIdentityComplete` (nebo volání `super` metoda), přepnutí neúspěšné identity pro aktivitu bude výsledkem dokončení aktivity. Pokud přepíšete metodu, můžete musí zajistíme, že se firemní data nezobrazí po přepnutí identity se nezdařilo.

>[!NOTE]
> Přepnutí identity může vyžadovat nové vytvoření aktivity. Nové instanci aktivity se pak doručí zpětné volání `onSwitchMAMIdentityComplete`.


### <a name="implicit-identity-changes"></a>Implicitní změny identity

Kromě schopnosti aplikace nastavit identitu se může vlákno nebo identita objektu Context změnit na základě příchozího přenosu dat z jiné aplikace spravované prostřednictvím Intune, která používá zásady ochrany aplikací.

#### <a name="examples"></a>Příklady

  1. Pokud se aktivita spustí ze `Intent` odeslaného jinou aplikací MAM, nastaví se identita aktivity podle účinné identity v jiné aplikaci v místě odeslání `Intent`.

  2.  U služeb se identita vlákna nastaví podobně po dobu volání `onStart` nebo `onBind`. Volání do třídy `Binder` vrácená z `onBind` také dočasně nastaví identitu vlákna.

  3. Volání do `ContentProvider` podobně nastaví identitu vlákna po dobu jejich trvání.


  Kromě toho interakce uživatele s aktivitou může způsobit přepnutí implicitní identity.

  **Příklad:** Uživatel zruší výzvu k autorizaci během `Resume` povede k implicitnímu přepnutí na prázdnou identitu.

  Aplikace bude moct tyto změny rozpoznat a v případě potřeby je může zakázat. Třídy `MAMService` a `MAMContentProvider` zveřejňují následující metodu, kterou můžou podtřídy přepsat:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  V třídě `MAMActivity` je v metodě k dispozici další parametr:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * `AppIdentitySwitchReason` zachycuje zdroj implicitního přepnutí a může přijmout hodnoty `CREATE`, `RESUME_CANCELLED` a `NEW_INTENT`.  Důvod oznámení `RESUME_CANCELLED` se použije, když obnovení aktivity způsobí zobrazení uživatelského rozhraní pro zadání kódu PIN, ověřování nebo jiné dodržování předpisů a uživatel se pokusí toto uživatelské prostředí zrušit, obvykle použitím tlačítka Zpět.


  * `AppIdentitySwitchResultCallback` vypadá takto:

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    Kde ```AppIdentitySwitchResult``` je `SUCCESS` nebo `FAILURE`.

Metoda `onMAMIdentitySwitchRequired` se volá u všech implicitních změn identity s výjimkou změn provedených třídou Binder, která se vrátila z `MAMService.onMAMBind`. Výchozí implementace `onMAMIdentitySwitchRequired` okamžitě volají:

* `reportIdentitySwitchResult(FAILURE)` Když je důvod `RESUME_CANCELLED`.

* `reportIdentitySwitchResult(SUCCESS)` ve všech ostatních případech.

  Neočekává se, že většina aplikací bude chtít blokovat nebo zpozdit přepnutí identity jinak. Pokud to ale aplikace chce udělat, musíte vzít v úvahu tyto body:

  * Pokud je přepnutí identity blokované, je výsledek stejný, jako kdyby nastavení sdílení `Receive` zakázala příchozí přenos dat.

  * Pokud služba běží na hlavním vlákně, **musí** se `reportIdentitySwitchResult` volat synchronně, jinak přestane vlákno uživatelského rozhraní reagovat.

  * Pro **`Activity`** vytváření `onMAMIdentitySwitchRequired` bude volána před `onMAMCreate`. Pokud musí aplikace zobrazit uživatelské rozhraní, aby určila, jestli se má povolit přepnutí identity, musí se toto uživatelské rozhraní zobrazit pomocí *jiné* aktivity.

  * V **`Activity`**, pokud se požaduje přepnout na prázdnou identitu s odůvodněním, které jako `RESUME_CANCELLED`, musí aplikace upravit obnovenou aktivitu pro zobrazení dat, které jsou konzistentní s tímto přepnutím identity.  Pokud to není možné, aplikace by měla přepnutí odmítnout a uživatel se znovu vyzve k dodržování zásad pro obnovení identity (například zobrazením obrazovky pro zadání kódu PIN).

    > [!NOTE]
    > Aplikace s více identitami bude vždycky přijímat příchozí data ze spravovaných i nespravovaných aplikací. Aplikace musí zacházet s daty ze spravovaných identit řízeně.

  Pokud je požadovaná identita spravovaná (to si ověříte pomocí `MAMPolicyManager.getIsIdentityManaged`), ale aplikace nemůže tento účet používat (například kvůli tomu, že se v aplikaci musí nejprve nastavit e-mailové nebo jiné účty), mělo by se přepnutí identity odmítnout.

#### <a name="build-plugin--tool-considerations"></a>Důležité informace týkající se nástroje nebo modulu plug-in sestavení
Pokud Nedědit explicitně z `MAMActivity`, `MAMService`, nebo `MAMContentProvider` (protože je povoleno sestavení nástrojů k provedení této změny), ale potřebují ke zpracování přepnutí identit, můžete místo toho implementovat `MAMActivityIdentityRequirementListener` (pro `Activity`) nebo `MAMIdentityRequirementListener` (pro `Service` nebo `ContentProviders`).
K výchozímu chování `MAMActivity.onMAMIdentitySwitchRequired` se dostanete tak, že zavoláte statickou metodu `MAMActivity.defaultOnMAMIdentitySwitchRequired(activity, identity,
reason, callback)`.

A pokud potřebujete přepsat `MAMActivity.onSwitchMAMIdentityComplete`, můžete implementovat `MAMActivityIdentitySwitchListener` bez explicitního dědění z `MAMActivity`.

### <a name="preserving-identity-in-async-operations"></a>Zachování identity v asynchronních operacích
Operace vlákna uživatelského rozhraní běžně odesílají úlohy na pozadí do jiného vlákna. Aplikace s více identitami bude chtít zajistit, že tyto úlohy na pozadí probíhají pod správnou identitou. Často se jedná o stejnou identitu používanou aktivitou, která je odeslala. Z důvodu usnadnění a pomoci při zachování identity sada SDK MAM poskytuje `MAMAsyncTask` a `MAMIdentityExecutors`.
Toto musíte použít, pokud asynchronní operace napsat firemních dat do souboru nebo může komunikovat s jinými aplikacemi.

#### <a name="mamasynctask"></a>MAMAsyncTask

Použití `MAMAsyncTask`, jednoduše dědí z místo něj `AsyncTask` a nahradit přepsání `doInBackground` a `onPreExecute` s `doInBackgroundMAM` a `onPreExecuteMAM` v uvedeném pořadí. Konstruktor `MAMAsyncTask` převezme kontext aktivity. Příklad:

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
```

### <a name="mamidentityexecutors"></a>MAMIdentityExecutors
`MAMIdentityExecutors` umožňuje zabalit existující instanci `Executor` nebo `ExecutorService` jako `Executor`/`ExecutorService` s metodami `wrapExecutor` a `wrapExecutorService`. Například

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```
### <a name="file-protection"></a>Ochrana souborů

Každý soubor má identitu, která je s ním spojená v době vytvoření, podle identity vláken a procesů. Tato identita se používá pro šifrování souborů i selektivní vymazání. Šifrovat se budou jen soubory, jejichž identita je spravovaná a má zásady vyžadující šifrování. Výchozí selektivní vymazání funkcí sadou SDK vymaže jen soubory spojené s identitou, u které se požaduje vymazání. Aplikace může zadat dotaz na identitu souboru nebo ji změnit pomocí třídy `MAMFileProtectionManager`.

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

#### <a name="app-responsibility"></a>Odpovědnost aplikace
Správa MAM nemůže automaticky odvodit vztah mezi čtenými soubory a daty zobrazovanými ve třídách `Activity`. Aplikace *musí* před zobrazením podnikových dat správně nastavit identitu uživatelského rozhraní. To platí i pro data čtená ze souborů. Pokud soubor pochází z umístění mimo aplikaci (`ContentProvider` nebo je přečten z umístění s možností veřejného zápisu), *musí* se aplikace před zobrazením informací přečtených ze souboru pokusit určit identitu souboru (s použitím `MAMFileProtectionManager.getProtectionInfo`). Pokud `getProtectionInfo` oznámí identitu, která nemá hodnotu null a není prázdná, *musí* se identita uživatelského rozhraní nastavit tak, aby odpovídala této identitě (pomocí `MAMActivity.switchMAMIdentity` nebo `MAMPolicyManager.setUIPolicyIdentity`). Pokud se přepnutí identity nezdaří, *nesmí* se data ze souboru zobrazit.

Příklad postupu by mohl vypadat takto:
  * Uživatel vybere dokument otevřete v aplikaci.
  * Během otevírání (před přečtením dat z disku) potvrdí aplikace identitu, která se má použít k zobrazení obsahu.
    * MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
    * if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)
    * Aplikace čeká na oznámení výsledku pro zpětné volání.
    * Pokud je oznámený výsledek chyba, aplikace dokument nezobrazí.
  * Aplikace se otevře a vykreslí soubor.
  
#### <a name="single-identity-to-multi-identity-transition"></a>Jedinou identitou přechod více identit
Pokud aplikaci, která dříve vydané s jedinou identitou později v integrací Intune se integruje více identit, dříve nainstalované aplikace dojde k přechodu (není viditelné pro uživatele, neexistuje žádný přidružený uživatelského rozhraní). Aplikace není *požadované* dělat nic explicitní pro zpracování tohoto přechodu. Všechny soubory vytvořené dřív, než přechod dále bude považovat za spravované (tak zůstanou šifrovaná, pokud je zásada šifrování v). V případě potřeby můžete zjišťovat upgradu a použít `MAMFileProtectionManager.protect` označit konkrétní soubory nebo adresáře s prázdnou identitou (tím také odeberete šifrování, pokud byly šifrované).

#### <a name="offline-scenarios"></a>Offline scénáře

Označení identity souboru je citlivé na režim offline. Je potřeba vzít v úvahu tyto body:

  * Pokud není nainstalovaný portál společnosti, soubory nemůžou mít označenou identitu.

  * Pokud je Portál společnosti nainstalovaný, ale aplikace nemá zásady MAM Intune, nedá se u souborů spolehlivě označit identita.

  * Jakmile je označování identity souborů k dispozici, považují se všechny dříve vytvořené soubory za osobní/nespravované (patří do identity s prázdným řetězcem), pokud nebyla aplikace dříve nainstalovaná jako spravovaná aplikace s jedinou identitou. V takovém případě se má zato, že soubory patří zaregistrovanému uživateli.

### <a name="directory-protection"></a>Ochrana adresářů

Adresáře je možné chránit pomocí stejné metody `protect`, která se používá k ochraně souborů. Ochrana adresářů ale působí rekurzivně na všechny soubory a podadresáře, které jsou součástí daného adresáře, stejně jako nové soubory vytvořené v tomto umístění. Vzhledem k této vlastnosti může u velkých adresářů trvat volání `protect` delší dobu. Proto je u aplikací využívajících ochranu adresáře s velkým počtem souborů vhodné spustit metodu `protect` asynchronně na vlákně na pozadí.

### <a name="data-protection"></a>Data Protection

Soubor se nedá označit jako soubor, který má více identit. Aplikace, které musí ukládat data různých uživatelů ve stejném souboru, to můžou provádět ručně díky funkcím, které poskytuje `MAMDataProtectionManager`. Aplikace tak můžou šifrovat data a spojit je s určitým uživatelem. Šifrovaná data se hodí k ukládání na disk v souboru. Na data, která souvisejí s identitou, můžete zadávat dotazy a později je dešifrovat.

Aplikace využívající `MAMDataProtectionManager` by měly pro oznámení `MANAGEMENT_REMOVED` implementovat příjemce. Po dokončení tohoto oznámení už nebudou vyrovnávací paměti chráněné touto třídou čitelné, pokud bylo v době poskytování ochrany povoleno šifrování souborů. Aplikace může napravit tuto situaci voláním `MAMDataProtectionManager.unprotect` na všech vyrovnávacích pamětí průběhu oznámení. Pokud chcete zachovat informace o identitě, je v této době také bezpečné volat metodu protect, protože při probíhajícím oznámení se zaručuje, že šifrování bude zakázané.


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

Pokud aplikace poskytuje podniková data než `ParcelFileDescriptor` prostřednictvím `ContentProvider`, musí volat metodu `isProvideContentAllowed(String)` v `MAMContentProvider`, předávání identitu vlastníka UPN (hlavní název uživatele) pro obsah. Pokud tato funkce vrací hodnotu False, *nesmí* se obsah vrátit zpět volajícímu. Popisovače souborů, které se vrátí přes poskytovatele obsahu, se automaticky zpracují podle identity souboru.

Pokud Nedědit `MAMContentProvider` explicitně a místo toho povolit nástroje sestavení tak, aby tuto změnu, může volat statickou verzi stejnou metodu: `MAMContentProvider.isProvideContentAllowed(provider, contentIdentity)`.

### <a name="selective-wipe"></a>Selektivní vymazání

Pokud aplikace s více identitami zaregistruje oznámení `WIPE_USER_DATA`, je odpovědná za odebrání všech dat vymazávaného uživatele, a to včetně všech souborů, jejichž identita označuje, že patří danému uživateli. Pokud aplikace odebere data uživatele ze souboru, ale chce v souboru ponechat ostatní data, *musí* změnit identitu souboru (přes `MAMFileProtectionManager.protect` na osobní identitu uživatele nebo na prázdnou identitu). Pokud se používají zásady šifrování, všechny zbývající soubory, které patří vymazávanému uživateli, zůstanou zašifrované a po vymazání budou pro aplikaci nedostupné.

Aplikace, která zaregistruje `WIPE_USER_DATA`, nezíská výhodu sady SDK výchozího chování sady SDK při selektivním vymazání. U aplikací, které pracují s více identitami, to může být mnohem závažnější, protože výchozí selektivní vymazání MAM vymaže jen soubory, na jejichž identitu vymazání cílí. Pokud si aplikace pracující s více identitami přeje, aby výchozí selektivní vymazání MAM proběhlo, _**a**_ chce při vymazání provádět vlastní akce, měla by si zaregistrovat oznámení `WIPE_USER_AUXILIARY_DATA`. Toto oznámení odešle sada SDK těsně před tím, než provedete výchozí selektivní vymazání MAM. Aplikace by nikdy neměla zaregistrovat `WIPE_USER_DATA` a `WIPE_USER_AUXILIARY_DATA`.

Výchozí selektivní vymazání ukončíte aplikaci řádně, dokončení aktivity a ukončuje se proces aplikace. Pokud vaše aplikace přepisuje výchozí vymazání seletive, můžete zvažte možnost Zavřít aplikaci ručně tak, aby zabrání uživateli v přístupu k datům v paměti, když dojde k vymazání.


## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Povolení konfigurace určené pro správu mobilních aplikací pro Android (nepovinné)
Je možné nakonfigurovat páry klíč hodnota specifické pro aplikaci v konzole Intune pro [MAM-jsme](https://docs.microsoft.com/intune/app-configuration-policies-managed-app) a [Android pracovní profil aplikace](https://docs.microsoft.com/intune/app-configuration-policies-use-android).
Tyto páry klíč-hodnota se v Intune vůbec neinterpretují, ale předávají se do aplikace. Aplikace, které chtějí obdržet takovou konfiguraci, k tomu můžou použít třídy `MAMAppConfigManager` a `MAMAppConfig`. Pokud je stejná aplikace cílem více zásad, může být pro stejný klíč k dispozici více konfliktních hodnot.

> [!NOTE] 
> Konfigurace nastavení pro přes MAM delivery-jsme nemůže být delievered v `offline`.  Jenom Android Enterprise AppRestrictions bude doručena prostřednictvím `MAMUserNotification` na prázdnou identitu v tomto případě.

### <a name="example"></a>Příklad
```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + appConfig.getFullData());
String valueToUse = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    for (String value : values) {
        if (isCorrectValue(value)) {
            valueToUse = value;
        }
    }
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
LOGGER.info("Found value " + valueToUse);
```

### <a name="notification"></a>Oznámení
Konfigurace aplikace přidá nový typ oznámení:
* **REFRESH_APP_CONFIG**: Toto oznámení se posílá ve `MAMUserNotification` a informuje aplikaci, že je k dispozici nová konfigurační data aplikace.

Další informace možnostech rozhraní Graph API najdete v [referenčních informacích k rozhraní Graph API](https://developer.microsoft.com/graph/docs/concepts/overview). <br>

Další informace o vytváření zásad konfigurace aplikací určených pro MAM v Androidu najdete v části o konfiguraci aplikací určených pro MAM v článku [Použití zásad konfigurace aplikací v Microsoft Intune pro Android](https://docs.microsoft.com/intune/app-configuration-policies-use-android).

### <a name="further-reading"></a>Další čtení
Další informace možnostech rozhraní Graph API najdete v [referenčních informacích k rozhraní Graph API](https://developer.microsoft.com/graph/docs/concepts/overview). <br>

Další informace o vytváření zásad konfigurace aplikací určených pro MAM v Androidu najdete v části o konfiguraci aplikací určených pro MAM v článku [Použití zásad konfigurace aplikací v Microsoft Intune pro Android](https://docs.microsoft.com/intune/app-configuration-policies-use-android).

## <a name="style-customization-optional"></a>Přizpůsobení stylu (volitelné)

Vzhled zobrazení vygenerovaných sadou MAM SDK můžete upravit tak, aby lépe odpovídaly aplikaci, do které se budou integrovat. Přizpůsobit můžete primární a sekundární barvu, barvy pozadí i velikost loga aplikace. Přizpůsobení je volitelné, a pokud nenastavíte vlastní styl, použije se výchozí vzhled.


### <a name="how-to-customize"></a>Postup přizpůsobení
Aby se změny stylu použily u zobrazení sady Intune MAM, je potřeba nejprve vytvořit soubor XML s přepsáním stylu. Tento soubor by se měl nacházet v adresáři „/res/xml“ vaší aplikace a může mít jakýkoli název. Níže je uveden příklad formátování, které by měl soubor dodržovat.
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

Je nutné znovu použít prostředky, které už ve vaší aplikaci jsou. To například znamená, že definujete zelenou barvu v souboru colors.xml a v tomto kódu na ni odkážete. Kód barvy v šestnáctkovém formátu „#0000ff“ nejde použít. Maximální velikost loga aplikace je 110 dip (dp). Použít můžete i logo menší velikosti, ale s maximální velikostí dosáhnete nejlepšího vzhledu. Pokud překročíte limit 110 dip, obrázek se zmenší a může se rozmazat.

Níže najdete kompletní seznam povolených atributů stylu, prvků uživatelského rozhraní, které tyto atributy řídí, názvy položek příslušných atributů XML a očekávané typy prostředků.

|Atribut stylu | Ovlivněné prvky uživatelského rozhraní | Název položky atributu | Očekávaný typ prostředku |
| -- | -- | -- | -- |
| Barva pozadí | Barva pozadí obrazovky pro zadání PIN kódu <Br>Barva výplně pole pro zadání PIN kódu | background_color | Barva |
| Barva popředí | Barva textu na popředí <br> Ohraničení pole pro zadání PIN kódu ve výchozím stavu <br> Znaky (včetně obfuskovaných znaků) v poli po zadání PIN kódu uživatelem| foreground_color | Barva|
| Barva motivu | Ohraničení pole pro zadání PIN kódu při zvýraznění <br> Hypertextové odkazy |accent_color | Barva |
| Logo aplikace | Velká ikona, která se zobrazuje na obrazovce pro zadání PIN kódu aplikace Intune | logo_image | Nákres |

## <a name="default-enrollment-optional"></a>Výchozí registrace (volitelná)

Následující část obsahuje postup pro vyžadování výzvy uživateli při spuštění aplikace pro registraci služby APP-WE (v této části to označujeme jako **výchozí registraci**) a vyžadování zásad ochrany aplikací Intune, aby obchodní aplikaci pro Android, která je integrovaná se sadou SDK, mohli používat jenom uživatelé s ochranou Intune. Obsahuje také postup pro povolení jednotného přihlašování pro obchodní aplikaci pro Android, která je integrovaná se sadou SDK. Tento postup se **nepodporuje** u aplikací pro Store, které můžou používat uživatelé nevyužívající službu Intune.

> [!NOTE] 
> Mezi výhody **výchozí registrace** patří zjednodušený způsob získání zásad ze služby APP-WE pro aplikaci na daném zařízení.

> [!NOTE] 
> **Výchozí registraci** zohledňuje suverénních cloudů.

Povolte výchozí registraci pomocí následujících kroků:

1. Pokud vaše aplikace integruje ADAL, nebo je nutné povolit jednotné přihlašování, [nakonfigurujte ADAL](#configure-azure-active-directory-authentication-library-adal) následující [obvyklé konfigurace ADAL](#common-adal-configurations) #2. V opačném případě můžete tento krok přeskočit.
   
2. Povolte výchozí registraci tak, že do manifestu vložíte následující hodnotu:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />
   ```
   > [!NOTE] 
   > Musí jít o jedinou integraci MAM-WE v dané aplikaci. Pokud existují další pokusy o volání rozhraní API instance MAMEnrollmentManager, dojde ke konfliktům.

3. Povolte požadované zásady MAM tak, že do manifestu vložíte následující hodnotu:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />
   ```
   > [!NOTE] 
   > Tím vynutíte, aby si uživatel na zařízení stáhl Portál společnosti a před použitím provedl postup výchozí registrace.


## <a name="limitations"></a>Omezení

### <a name="file-size-limitations"></a>Omezení velikosti souborů

Omezení formátu spustitelných souborů Dalvik se stává problémem u rozsáhlých základů kódu, které běží bez [ProGuard](http://proguard.sourceforge.net/). Konkrétně může dojít k následujícím omezením:

1.  Limit 65 kB pro pole
2.  Limit 65 kB pro metody

### <a name="policy-enforcement-limitations"></a>Omezení vynucení zásad

* **Použití překladačů obsahu**: Zásady Intune "přenosu nebo příjmu" můžou blokovat nebo částečně blokovat použití překladače obsahu při přístupu k poskytovateli obsahu v jiné aplikaci. To způsobí, že `ContentResolver` metody vrátit hodnotu null nebo generují hodnotu selhání (například `openOutputStream` vyvolá `FileNotFoundException` Pokud blokován). Aplikace může určit, jestli selhání při zápisu dat pomocí překladače obsahu způsobila zásada (nebo by způsobila zásada), a to voláním:
    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```
    nebo (pokud není přidružená žádná aktivita):

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    Ve druhém případě musí aplikace s více identitami pečlivě správně nastavit identitu vlákna (nebo předat explicitní identitu do volání `getPolicy`).

### <a name="exported-services"></a>Exportované služby

 Soubor AndroidManifest.xml zahrnutý v sadě Intune App SDK obsahuje službu **MAMNotificationReceiverService**, která musí být exportovanou službou, aby umožňovala Portálu společnosti odesílat oznámení do spravované aplikace. Služba zkontroluje volajícího, aby zajistila, že odesílat oznámení může jenom portál společnosti.

### <a name="reflection-limitations"></a>Omezení reflexe
Některé základní třídy (například MAMActivity, MAMDocumentsProvider) obsahují metody (založené na původních základních třídách Androidu), které používají typy parametrů nebo návratové typy nacházející se nad určitými úrovněmi rozhraní API. Z tohoto důvodu nemusí být vždycky možné používat reflexi k výčtu všech metod součástí aplikací. Toto omezení se nevztahuje jenom na MAM. Jedná se o stejné omezení, které by se použilo v případě, že by aplikace samotná implementovala tyto metody ze základních tříd Androidu.

### <a name="robolectric"></a>Robolectric
Testování chování sady SDK MAM v rozhraní Robolectric se nepodporuje. Existují známé problémy, na kterém běží sada SDK MAM podle Robelectric kvůli chování nacházejí v části Robolectric, které není napodobují přesně na skutečných zařízeních nebo emulátorech.

Pokud potřebujete otestovat aplikaci v rozhraní Roboelectric, doporučujeme přesunout logiku třídy aplikace do pomocné rutiny a vytvořit balíček aplikace pro Android pro testování částí s třídou aplikace, která nedědí z aplikace MAMApplication.
## <a name="expectations-of-the-sdk-consumer"></a>Očekávání uživatele sady SDK

Intune SDK udržuje kontrakt poskytovaný rozhraním Android API, i když podmínky selhání můžou být vyvolány častěji v důsledku vynucení zásad. Tyto doporučené postupy pro Android sníží pravděpodobnost selhání:

* Funkce sady Android SDK, které můžou vrátit hodnotu null, mají vyšší pravděpodobnost vrácení hodnoty null.  Pokud chcete minimalizovat problémy, zajistěte, aby byly na správných místech kontroly hodnoty null.

* Vlastnosti, které jde zkontrolovat, musí být kontrolované pomocí příslušných rozhraní API náhradních sad MAM.

* Všechny odvozené funkce se musí provolat ke svým verzím v nadřazené třídě.

* Vyhněte se použití jakéhokoli rozhraní API nejednoznačný způsobem. Například použití `Activity.startActivityForResult` bez kontroly requestCode způsobí neobvyklé chování.

## <a name="telemetry"></a>Telemetrie

Sada Intune App SDK pro Android neřídí shromažďování dat z vaší aplikace. Aplikace Portál společnosti ve výchozím nastavení protokoluje telemetrická data. Tato data se odešlou do Microsoft Intune. V souladu se zásadami Microsoftu neshromažďujeme žádné identifikovatelné osobní údaje.

> [!NOTE]
> Pokud se koncoví uživatelé rozhodnou tato data neodesílat, musí v nastavení aplikace Portál společnosti vypnout telemetrii. Další informace najdete v článku [Vypnutí shromažďování dat Microsoftu o využití](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Doporučené osvědčené postupy pro Android

* Všechny projekty knihovny by měly sdílet stejný balíček android:package, kde je to možné. Protože je to čistě problém v době vytváření buildu, nedojde k selhání za běhu. Novější verze sady Intune App SDK odeberou některé z redundancí.

* Použijte nejnovější nástroje pro vytváření buildů sady SDK pro Android.

* Odeberte všechny nepotřebné a nepoužívané knihovny (například android.support.v4).
