---
title: "Zabalení aplikací pro Android pomocí nástroje App WrappingTool | Microsoft Intune"
description: "V tomto článku se naučíte balit aplikace pro Android beze změny samotného kódu aplikace. Připravte aplikace, abyste mohli použít zásady správy mobilních aplikací."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b25c7d7063ce586bb1cd960534f3e2ed57f6aec4
ms.openlocfilehash: 7c61ad6a3122793ddd66547b7040f978705b540c


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Příprava aplikací pro Android na správu mobilních aplikací pomocí nástroje Intune App Wrapping Tool

Pokud chcete změnit chování interních aplikací pro Android tím, že omezíte jejich funkce – beze změny samotného kódu aplikace – použijte nástroj Microsoft Intune App Wrapping Tool for Android.

Jde o nástroj příkazového řádku Windows, který běží v PowerShellu a který vytvoří okolo vaší aplikace pro Android obálku. Po zabalení aplikace můžete změnit její funkce nakonfigurováním [zásad správy mobilní aplikace](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) v Intune.


Před spuštěním nástroje si přečtěte část [Důležité informace o zabezpečení při spuštění nástroje App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool). Nástroj si můžete stáhnout ze stránky [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) na GitHubu.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Splnění požadavků na používání nástroje App Wrapping Tool

-   Nástroj App Wrapping Tool je možné spustit na počítači se systémem Windows 7 nebo novějším.

-   Vstupní aplikace musí být platný balíček aplikace pro Android, který má příponu souboru .apk a splňuje následující požadavky:

    -   Nesmí být zašifrovaný.
    -   Nesmí být už jednou zabalený nástrojem Intune App Wrapping Tool.
    -   Musí být napsaný pro systém Android 4.0 nebo novější.

-   Aplikaci musí vyvinout vaše společnost nebo je tato aplikace vyvinuta pro ni. Tento nástroj se nedá používat u aplikací stažených z obchodu Google Play.

-   Pokud chcete nástroj App Wrapping Tool spustit, musíte mít nainstalovanou nejnovější verzi [prostředí Java Runtime](http://java.com/download/). Potom zkontrolujte, jestli je proměnná cesty Java v proměnných prostředí Windows nastavená na C:\ProgramData\Oracle\Java\javapath. Další nápovědu najdete v [dokumentaci k Javě](http://java.com/download/help/).

    > [!NOTE]
    > V některých případech může 32bitová verze Javy způsobit potíže s pamětí. Proto je vhodné nainstalovat 64bitovou verzi.

- Android vyžaduje, aby byly všechny balíčky aplikací (.apk) podepsané. Ke generování přihlašovacích údajů potřebných k podpisu zabalené výstupní aplikace použijte Java keytool. Klíče pro nástroj App Wrapping Tool použité k podpisu zabalené výstupní aplikace můžete vygenerovat například následujícím příkazem, který ke generování klíčů používá spustitelný Java soubor keytool.exe.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    V tomto příkladu se ke generování dvojice klíčů (veřejný klíč a spojený privátní klíč o velikosti 2048 bitů) použije šifrovací algoritmus RSA. Tento algoritmus pak zabalí veřejný klíč do certifikátu X.509 v3 podepsaného svým držitelem, který se uloží jako řetěz certifikátu s jedním prvkem. Tento řetěz certifikátů a privátní klíč jsou uložené v nové položce úložiště klíčů s názvem „mykeystorefile“ a označené aliasem „mykeyalias“. Položka úložiště klíčů je platná po dobu 50 000 dní.

    Příkaz vás vyzve k zadání hesel k úložišti klíčů a ke klíči. Používejte hesla, která jsou bezpečná, ale nezapomeňte si je poznamenat, protože je budete potřebovat ke spuštění nástroje App Wrapping Tool.

    Jestli se chcete o nástroji Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) a [úložišti klíčů](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) v Javě dozvědět něco víc, projděte si podrobnou dokumentaci na webu společnosti Oracle.

## <a name="install-the-app-wrapping-tool"></a>Instalace nástroje App Wrapping Tool

1.  Z [úložiště GitHubu](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) si do počítače s Windows stáhněte instalační soubor InstallAWT.exe nástroje Intune App Wrapping Tool for Android. Otevřete instalační soubor.

2.  Přijměte licenční smlouvu a dokončete instalaci.

Poznamenejte si složku, do které jste nainstalovali nástroj. Výchozí umístění je: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Spuštění nástroje App Wrapping Tool

1.  Na počítači s Windows, na který jste nainstalovali nástroj App Wrapping Tool, otevřete v režimu správce okno PowerShellu.

2.  Ze složky, do které jste nástroj nainstalovali, naimportujte modul PowerShell nástroje App Wrapping Tool:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Spusťte nástroj příkazem **invoke-AppWrappingTool**, který má následující syntaxi použití:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Podrobný popis vlastností příkazu **invoke-AppWrappingTool** uvádí následující tabulka:

|Vlastnost|Informace|Příklad|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Cesta ke zdrojové aplikaci pro Android (.apk).| |
|**-OutputPath**&lt;String&gt;|Cesta k výstupní aplikaci pro Android. Když je to cesta ke stejnému adresáři jako InputPath, vytváření balíčků selže.| |
|**-KeyStorePath**&lt;String&gt;|Cesta k souboru v úložišti klíčů s dvojicí veřejného a privátního klíče, které se používají k podpisu.|Ve výchozím nastavení jsou soubory v úložišti klíčů uložené ve složce „C:\Program Files (x86)\Java\jreX.X.X_XX\bin“. |
|**-KeyStorePassword**&lt;SecureString&gt;|Heslo použité k dešifrování úložiště klíčů. Android vyžaduje, aby všechny balíčky aplikace (.apk) byly podepsané. Ke generování hesla k úložišti klíčů (parametr KeyStorePassword) použijte nástroj Java keytool. Další informace o úložišti klíčů Java si můžete přečíst [tady](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).| |
|**-KeyAlias**&lt;String&gt;|Název klíče, který se má použít pro podepisování.| |
|**-KeyPassword**&lt;SecureString&gt;|Heslo použité k dešifrování privátního klíče, který se použije pro podepisování.| |
|**-SigAlg**&lt;SecureString&gt;| (Volitelně) Název podpisového algoritmu, který se má použít k podepsání. Algoritmus musí být kompatibilní s privátním klíčem.|Příklady: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Volitelně) Příkaz podporuje běžné parametry PowerShellu, jako je verbose a debug. |


- Seznam společných parametrů najdete v [Centru skriptů Microsoftu](https://technet.microsoft.com/library/hh847884.aspx).

- Pokud chcete zobrazit podrobné informace o použití tohoto nástroje, zadejte tento příkaz:

    ```
    Help Invoke-AppWrappingTool
    ```

**Příklad:**

Naimportujte modul PowerShellu.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Spusťte nástroj App Wrapping Tool na nativní aplikaci HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Zobrazí se výzva k zadání parametrů **KeyStorePassword** a **KeyPassword**. Zadejte uživatelské jméno a heslo, které jste použili k vytvoření souboru úložiště klíčů.

Zabalená aplikace a soubor protokolu se vygenerují a uloží do zadané výstupní cesty.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Důležité informace o zabezpečení při spuštění nástroje App Wrapping Tool
Pro zabránění potenciálnímu falšování identity, zpřístupnění informací a zvýšení oprávnění pro útoky zajistěte toto:

-   Vstupní obchodní aplikace (LOB), výstupní aplikace a úložiště klíčů Java KeyStore musí být na stejném počítači s Windows, na kterém běží nástroj App Wrapping Tool.

-   Výstupní aplikaci naimportujte do konzoly Intune na stejném počítači, na kterém je spuštěný i nástroj. Další informace o nástroji Java keytool viz [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Pokud se výstupní aplikace a nástroj sice nacházejí v cestě UNC (Universal Naming Convention), ale vy nespouštíte nástroj a vstupní soubory na stejném počítači, použijte k nastavení zabezpečení prostředí podpis [protokolu IPsec (Internet Protocol Security)](http://en.wikipedia.org/wiki/IPsec) nebo [protokolu SMB (Server Message Block)](https://support.microsoft.com/en-us/kb/887429).

-   Aplikace musí pocházet z důvěryhodného zdroje.

-   Zabezpečte výstupní adresář se zabalenou aplikací. Zvažte použití adresáře na úrovni uživatele pro výstup.

### <a name="see-also"></a>Související témata
- [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO1-->


