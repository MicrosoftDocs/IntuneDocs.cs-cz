---
title: Zabalení aplikací pro Android pomocí nástroje pro zabalení aplikace Intune
description: Naučte se zabalit aplikace pro Android beze změny samotného kódu aplikace. Připravte aplikace, abyste mohli použít zásady správy mobilních aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfea74c70b81cadfa06c578dc33cdad401fa9e45
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940056"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Příprava aplikací pro Android na zásady ochrany aplikací pomocí nástroje pro zabalení aplikace Intune

Pomocí nástroje pro zabalení aplikace Microsoft Intune pro Android můžete změnit chování interních aplikací pro Android omezením funkcí aplikace beze změny samotného kódu aplikace.

Tento nástroj je aplikace příkazového řádku Windows, která běží v prostředí PowerShell a vytváří obálku kolem vaší aplikace pro Android. Po zabalení aplikace můžete změnit funkčnost aplikace konfigurací [zásad správy mobilních aplikací](../apps/app-protection-policies.md) v Intune.

Před spuštěním nástroje si přečtěte téma [požadavky na zabezpečení při spuštění nástroje pro zabalení aplikace](#security-considerations-for-running-the-app-wrapping-tool). Nástroj si můžete stáhnout tak, že přejdete na [Nástroj pro zabalení aplikace Microsoft Intune pro Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) na GitHubu.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Splnění požadavků na používání nástroje pro zabalení aplikace

- Nástroj pro zabalení aplikace musíte spustit na počítači se systémem Windows 7 nebo novějším.

- Vstupní aplikace musí být platný balíček aplikace pro Android s příponou. apk a:

  - Nedá se zašifrovat.
  - Nesmí už být zabalený nástrojem pro zabalení aplikace Intune.
  - Musí být napsaný pro Android 4,0 nebo novější.

- Aplikace musí být vyvinutá nástrojem nebo pro vaši společnost. Tento nástroj nemůžete použít pro aplikace stažené z Obchod Google Play.

- Chcete-li spustit nástroj pro zabalení aplikace, je třeba nainstalovat nejnovější verzi [Java Runtime Environment](https://java.com/download/) a poté zkontrolovat, zda byla proměnná cesty Java v proměnných prostředí systému Windows nastavena na hodnotu C:\ProgramData\Oracle\Java\javapath. Další nápovědu najdete v [dokumentaci Java](https://java.com/download/help/).

    > [!NOTE]
    > V některých případech může 32 verze Java způsobit problémy s pamětí. Je vhodné nainstalovat 64 bitovou verzi.

- Android vyžaduje, aby byly všechny balíčky aplikací (. apk) podepsané. Informace o tom, jak znovu **použít** stávající certifikáty a celkové pokyny k podpisovým certifikátům, najdete v tématu [Používání podpisových certifikátů a balení aplikací](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps). Nástroj Java executable. exe se používá ke generování **nových** přihlašovacích údajů potřebných k podepsání zabalené výstupní aplikace. Všechna hesla, která jsou nastavena, musí být zabezpečená, ale Poznamenejte si je, protože jsou potřeba ke spuštění nástroje pro zabalení aplikace.

    > [!NOTE]
    > Nástroj pro zabalení aplikace v Intune nepodporuje pro podepisování aplikací rozhraní Google v2 a nadcházející schémata podpisů v3. Po zabalení souboru. apk pomocí nástroje pro zabalení aplikace Intune doporučujeme použít [Nástroj Apksigner poskytnutý v Google]( https://developer.android.com/studio/command-line/apksigner). Tím se zajistí, že jakmile se aplikace dostane k zařízením koncových uživatelů, může je správně spustit pomocí standardů Androidu. 

- Volitelné Někdy může aplikace dosáhnout limitu velikosti spustitelného souboru Dalvik (DEX), protože třídy sady Intune MAM SDK, které jsou přidány během zabalení. Soubory DEX jsou součástí kompilace aplikace pro Android. Nástroj pro zabalení aplikace Intune automaticky zpracovává přetečení souborů DEX při zabalení pro aplikace s minimální úrovní rozhraní API 21 nebo vyšší (jako [v. 1.0.2501.1](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android/releases)). Pro aplikace s minimální úrovní rozhraní API < 21 by osvědčeným postupem bylo zvýšení minimální úrovně rozhraní API pomocí příznaku `-UseMinAPILevelForNativeMultiDex` obálky. Aby zákazníci nemohli zvýšit minimální úroveň rozhraní API aplikace, jsou k dispozici následující alternativní DEX přetečení. V některých organizacích to může vyžadovat spolupráci s tím, že aplikace kompiluje (tj. tým sestavení aplikace):
* Pomocí ProGuard můžete eliminovat nepoužívané odkazy na třídy z primárního souboru DEX aplikace.
* Pro zákazníky, kteří používají 3.1.0 nebo novější modul plug-in Android Gradle, zakažte [D8 dexer](https://android-developers.googleblog.com/2018/04/android-studio-switching-to-d8-dexer.html).  

## <a name="install-the-app-wrapping-tool"></a>Instalace nástroje pro zabalení aplikace

1. Z [úložiště GitHubu](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)si stáhněte instalační soubor InstallAWT. exe pro nástroj pro zabalení aplikace Intune pro Android do počítače s Windows. Otevřete instalační soubor.

2. Přijměte licenční smlouvu a dokončete instalaci.

Poznamenejte si složku, do které jste nástroj nainstalovali. Výchozí umístění je: C:\Program Files (x86) \Microsoft Intune Mobile Application Management\Android\App zabalení nástroje.

## <a name="run-the-app-wrapping-tool"></a>Spuštění nástroje pro zabalení aplikace

1. Na počítači s Windows, na který jste nainstalovali nástroj pro zabalení aplikace, otevřete okno PowerShellu.

2. Ze složky, do které jste nástroj nainstalovali, importujte modul PowerShell nástroje pro zabalení aplikace:

   ```PowerShell
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Spusťte nástroj pomocí příkazu **Invoke-AppWrappingTool** , který obsahuje následující syntaxi použití:

   ```PowerShell
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   Následující tabulka podrobně popisuje vlastnosti příkazu **Invoke-AppWrappingTool** :

|Vlastnost|Informace o|Příklad|
|-------------|--------------------|---------|
|**-InputPath**&lt;String @ no__t-2|Cesta ke zdrojové aplikaci pro Android (. apk)| |
 |**-OutputPath**&lt;String @ no__t-2|Cesta k výstupní aplikaci pro Android Pokud se jedná o stejnou cestu k adresáři jako InputPath, balení se nezdaří.| |
|**-KeyStorePath**&lt;String @ no__t-2|Cesta k souboru úložiště klíčů, který obsahuje pár veřejného a privátního klíče pro podepisování.|Ve výchozím nastavení se soubory úložiště klíčů ukládají do složky C:\Program Files (x86) \Java\jreX.X.X_XX\bin. ". |
|**-KeyStorePassword**&lt;SecureString @ no__t-2|Heslo použité k dešifrování úložiště klíčů. Android vyžaduje, aby byly všechny balíčky aplikací (. apk) podepsané. Vygenerujte KeyStorePassword pomocí nástroje Java Tool. Další informace o [úložišti klíčů](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) Java si můžete přečíst tady.| |
|**-Jiné**@no__t – 1String @ no__t-2|Název klíče, který se má použít k podepsání.| |
|**-Heslo**@no__t – 1SecureString @ no__t-2|Heslo použité k dešifrování privátního klíče, který se použije k podepisování.| |
|**-SigAlg**&lt;SecureString @ no__t-2| Volitelné Název algoritmu podpisu, který se má použít k podepsání. Algoritmus musí být kompatibilní s privátním klíčem.|Příklady: SHA256withRSA, SHA1withRSA|
|**-UseMinAPILevelForNativeMultiDex**| Volitelné Pomocí tohoto příznaku zvyšte minimální úroveň rozhraní API u zdrojové aplikace pro Android na 21. Tento příznak zobrazí výzvu k potvrzení, protože bude omezen na to, kdo může tuto aplikaci nainstalovat. Uživatelé můžou potvrzovací dialog přeskočit připojením parametru-Confirm: $false ke svému příkazu PowerShellu. Příznak by měli používat jenom zákazníci v aplikacích s minimálním rozhraním API < 21, které se nepodařilo úspěšně zabalit kvůli chybám přetečení DEX. | |
| **@no__t – 1CommonParameters @ no__t – 2** | Volitelné Příkaz podporuje běžné parametry PowerShellu, jako je verbose a ladění. |


- Seznam společných parametrů najdete na [webu Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Chcete-li zobrazit podrobné informace o použití nástroje, zadejte příkaz:

    ```PowerShell
    Help Invoke-AppWrappingTool
    ```

**Případě**

Importujte modul prostředí PowerShell.

```PowerShell
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```

Spusťte nástroj pro zabalení aplikace v nativní aplikaci HelloWorld. apk.

```PowerShell
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Pak se zobrazí výzva k zadání hesla pro **KeyStorePassword** a **heslo**. Zadejte přihlašovací údaje, které jste použili k vytvoření souboru úložiště klíčů.

Zabalená aplikace a soubor protokolu se vygenerují a uloží do zadané výstupní cesty.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Jak často mám znovu zabalit aplikaci pro Android pomocí nástroje pro zabalení aplikace Intune?
Hlavní scénáře, ve kterých byste museli znovu zabalit aplikace, jsou následující:
* Aplikace sama vydala novou verzi. Předchozí verze aplikace byla zabalena a nahrána do konzoly Intune.
* Nástroj pro zabalení aplikace Intune pro Android vydala novou verzi, která umožňuje opravy chyb klíčů nebo nové, konkrétní funkce zásad ochrany aplikací Intune. K tomu dochází každých 6-8 týdnů prostřednictvím úložiště GitHub pro [nástroj Microsoft Intune pro zabalení aplikace pro Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android).

Mezi Doporučené postupy pro přebalení patří: 
* Údržba podpisových certifikátů použitých během procesu sestavení najdete v tématu opětovné [použití podpisových certifikátů a balení aplikací](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps) .

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Znovu použití podpisových certifikátů a balení aplikací
Android vyžaduje, aby všechny aplikace byly podepsány platným certifikátem, aby je bylo možné nainstalovat na zařízení s Androidem.

Zabalené aplikace je možné podepsat buď jako součást procesu zabalení, nebo *po* zabalení pomocí stávajících podpisových nástrojů (veškeré informace o podepisování v aplikaci před zabalením se zruší). Je-li to možné, měly by být při zabalení použity podpisové informace, které již byly použity během procesu sestavování. V některých organizacích to může vyžadovat spolupráci s těmi, kdo vlastní informace o úložišti klíčů (tj. tým pro vytváření aplikací). 

Pokud se předchozí podpisový certifikát nedá použít nebo pokud aplikace ještě nebyla nasazená, můžete vytvořit nový podpisový certifikát podle pokynů v [příručce pro vývojáře pro Android](https://developer.android.com/studio/publish/app-signing.html#signing-manually).

Pokud byla aplikace dříve nasazena s jiným podpisovým certifikátem, aplikaci po upgradu nelze odeslat do Intune. Pokud je vaše aplikace podepsaná jiným certifikátem, než je ten, na kterém je aplikace vytvořená, dojde k porušení scénářů upgradu aplikace. V takovém případě by se měly pro upgrady aplikací zachovat všechny nové podpisové certifikáty. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Požadavky na zabezpečení při spuštění nástroje pro zabalení aplikace
Aby nedocházelo k potenciálnímu falšování identity, zpřístupnění informací a zvýšení oprávnění k útokům:

- Ujistěte se, že vstupní obchodní aplikace, výstupní aplikace a úložiště klíčů Java jsou ve stejném počítači s Windows, na kterém je spuštěný Nástroj pro zabalení aplikace.

- Importujte výstupní aplikaci do Intune na stejném počítači, na kterém je nástroj spuštěný. Další informace o nástroji Java Tool najdete v části [Nástroj](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) .

- Pokud je výstupní aplikace a nástroj v cestě UNC (Universal Naming Convention) a nespouštíte nástroj a vstupní soubory na stejném počítači, nastavte prostředí jako zabezpečené pomocí [protokolu IPSec (Internet Protocol Security)](https://wikipedia.org/wiki/IPsec) nebo [zprávy serveru. Podepisování bloků (SMB)](https://support.microsoft.com/kb/887429).

- Ujistěte se, že aplikace pochází z důvěryhodného zdroje.

- Zabezpečte výstupní adresář, který obsahuje zabalenou aplikaci. Zvažte použití adresáře na úrovni uživatele pro výstup.

## <a name="see-also"></a>Viz také:
- [Rozhodněte se, jak připravit aplikace na správu mobilních aplikací pomocí Microsoft Intune](../developer/apps-prepare-mobile-application-management.md)

- [Microsoft Intune App SDK pro Android – příručka pro vývojáře](../developer/app-sdk-android.md)
