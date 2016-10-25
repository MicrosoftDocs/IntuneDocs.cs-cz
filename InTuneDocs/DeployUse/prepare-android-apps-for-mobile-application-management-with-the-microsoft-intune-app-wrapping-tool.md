---
title: "Zabalení aplikací pro Android pomocí nástroje App Wrapping Tool | Microsoft Intune"
description: "Informace v tomto tématu popisují, jak zabalit aplikace pro Android beze změny vlastního kódu aplikace. Připravte aplikace, abyste mohli použít zásady správy mobilních aplikací."
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
ms.sourcegitcommit: fe3a9f2fd9ce9a3c3f776dcfd9ad3347a63d0fc1
ms.openlocfilehash: e623755cf926020bcb66d8a6d40e5cce9b46b0ae


---

# Příprava aplikací pro Android na správu mobilních aplikací pomocí nástroje Intune App Wrapping Tool
Díky nástroji **Microsoft Intune App Wrapping Tool for Android** můžete omezit funkce interních aplikací pro Android a tím změnit jejich chování, aniž byste měnili kód samotných aplikací.

Jde o nástroj příkazového řádku Windows, který běží v PowerShellu a vytvoří okolo vaší aplikace pro Android tzv. „obálku“. Po zabalení aplikace můžete změnit její funkce nakonfigurováním [zásad správy mobilní aplikace](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) v Intune.


Před spuštěním nástroje zkontrolujte [Důležité informace o zabezpečení při spuštění nástroje pro zabalení aplikace](#security-considerations-for-running-the-app-wrapping-tool). Nástroj si můžete stáhnout ze stránky [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) na GitHubu.



## Krok 1: Splnění požadavků na používání nástroje App Wrapping

-   Nástroj pro zabalení aplikace se musí spustit v počítači s Windows 7 nebo novějším systémem.

-   Vstupní aplikace musí mít podobu platného balíčku aplikace pro Android s příponou **.apk**, pro který platí toto:

    -   Nedá se zašifrovat.

    -   Nesmí už být zabalený nástrojem Intune App Wrapping Tool.
    -   Musí být napsaný pro Android 4.0 nebo vyšší.

-   Aplikace musí být vyvinutá vaší společností nebo pro ni. Tento nástroj se nedá používat u aplikací stažených z obchodu Google Play.

-   Pokud chcete spustit nástroj pro zabalení aplikace, nainstalujte nejnovější verzi [prostředí Java Runtime](http://java.com/download/) a ověřte, jestli je proměnná cesty Java v proměnných prostředí Windows nastavená na **C:\ProgramData\Oracle\Java\javapath**. Další nápovědu najdete v [dokumentaci k Javě](http://java.com/download/help/).

    > [!NOTE]
    > V některých případech může 32bitová verze Javy způsobit potíže s pamětí. Doporučujeme nainstalovat místo toho 64bitovou verzi.

- Android vyžaduje, aby byly všechny balíčky aplikací (.apks) podepsané. Ke generování uživatelského jména a hesla potřebného k podepsání zabalené výstupní aplikace použijte nástroj Java Key Tool. Klíče, které může nástroj pro zabalení aplikace použít k podepsání zabalené výstupní aplikace, se dají generovat třeba pomocí následujícího příkazu, kde se využívá spustitelný Java soubor **keytool.exe**.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Tímto příkazem se pomocí algoritmu RSA generuje pár klíčů (veřejný klíč a přidružený privátní klíč o velikosti 2 048 bitů) a veřejný klíč se pak zabalí do certifikátu X.509 v3 podepsaného jeho držitelem, který je uložený jako řetěz certifikátů s jedním prvkem. Tento řetěz certifikátů a privátní klíč jsou uložené v nové položce úložiště klíčů s názvem „mykeystorefile“ a označené aliasem „mykeyalias“. Položka úložiště klíčů je platná po dobu 50 000 dní.

    Příkaz vás vyzve k zadání hesel k úložišti klíčů a ke klíči. Používejte zabezpečená a těžko odhadnutelná hesla, ale dejte pozor, abyste je nezapomněli, protože je později budete potřebovat ke spuštění nástroje pro zabalení aplikace.

    Jestli se chcete o nástroji Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) a [úložišti klíčů](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) v Javě dozvědět něco víc, projděte si podrobnou dokumentaci na webu společnosti Oracle.

## Krok 2: Instalace nástroje App Wrapping

1.  Z [úložiště GitHubu](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) si do počítače s Windows stáhněte instalační soubor **InstallAWT.exe** nástroje Intune App Wrapping Tool for Android a otevřete ho.

2.  Přijměte licenční smlouvu a dokončete instalaci.

Poznamenejte si složku, do které jste nainstalovali nástroj. Výchozí umístění: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Krok 3: Spuštění nástroje App Wrapping

1.  Na počítači s Windows, na který jste nainstalovali nástroj pro zabalení aplikace, otevřete v režimu správce okno PowerShell.

2.  Ze složky, do které jste nástroj nainstalovali, importujte modul PowerShell nástroje pro zabalení aplikace:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Spusťte nástroj pomocí příkazu **invoke-AppWrappingTool**, který má tuto syntaxi:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Podrobný popis vlastností příkazu **invoke-AppWrappingTool** uvádí následující tabulka:

|Vlastnost|Informace|Příklad|
|-------------|--------------------|---------|
|**-InputPath**&lt;řetězec&gt;|Cesta ke zdrojové aplikaci pro Android (.apk).| |
|**-OutputPath**&lt;řetězec&gt;|Cesta k „výstupní“ aplikaci pro Android. Když je to cesta ke stejnému adresáři jako InputPath, vytváření balíčků selže.| |
|**-KeyStorePath**&lt;řetězec&gt;|Cesta k souboru úložiště klíčů, který obsahuje pár veřejného a privátního klíče pro podepisování.|Soubory úložiště klíčů jsou ve výchozím nastavení uložené ve složce C:\Program Files (x86)\Java\jreX.X.X_XX\bin. |
|**-KeyStorePassword**&lt;řetězec zabezpečení&gt;|Heslo použité k dešifrování úložiště klíčů. Android vyžaduje, aby všechny balíčky aplikace (.apk) byly podepsané. Ke generování hesla k úložišti klíčů (parametr KeyStorePassword) použijte nástroj Java Key Tool. Tady se o [úložišti klíčů](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) dozvíte něco víc.| |
|**-KeyAlias**&lt;řetězec&gt;|Název klíče, který se má použít pro podepisování.| |
|**-KeyPassword**&lt;řetězec zabezpečení&gt;|Heslo použité k dešifrování privátního klíče, který se použije pro podepisování.| |
|**-SigAlg**&lt;řetězec zabezpečení&gt;| (Volitelně) Název podpisového algoritmu, který se má použít k podepsání. Algoritmus musí být kompatibilní s privátním klíčem.|Příklady: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Volitelně) Příkaz podporuje běžné parametry PowerShellu, třeba verbose, debug atd. |


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
Spusťte nástroj pro zabalení aplikace u nativní aplikace **HelloWorld.apk**. 
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Pak se zobrazí výzva k zadání parametrů **KeyStorePassword** a **KeyPassword**. Zadejte uživatelské jméno a heslo, které jste použili k vytvoření souboru úložiště klíčů.

Zabalená aplikace se generuje a uloží se souborem protokolu do zadané výstupní cesty.

## Důležité informace o zabezpečení při spuštění nástroje pro zabalení aplikace
Pro zabránění potenciálnímu falšování identity, zpřístupnění informací a zvýšení oprávnění pro útoky zajistěte toto:

-   Vstupní obchodní aplikace, výstupní aplikace a úložiště klíčů v Javě musí být na stejném počítači s Windows, na kterém běží nástroj pro zabalení aplikace.

-   Výstupní aplikaci naimportujte do konzoly Intune na stejném počítači, na kterém je spuštěný i nástroj. Další informace o příkazu keytool Javy najdete v tématu [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Pokud jsou výstupní aplikace a nástroj v cestě Universal Naming Convention (UNC) a nespustíte nástroj a vstupní soubory na stejném počítači, nakonfigurujte prostředí tak, aby bylo zabezpečené, pomocí protokolů [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) nebo [podepsání protokolu Server Message Block (SMB)](https://support.microsoft.com/en-us/kb/887429).

-   Aplikace musí pocházet z důvěryhodného zdroje.

-   Zabezpečte výstupní adresář, který obsahuje zabalenou aplikaci. Zvažte použití adresáře na úrovni uživatele pro výstup.



### Související témata
- [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


