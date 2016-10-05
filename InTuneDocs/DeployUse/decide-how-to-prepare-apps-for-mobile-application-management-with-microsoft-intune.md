---
title: "Příprava aplikací pro správu mobilních aplikací | Microsoft Intune"
description: "Informace v tomto tématu vám pomohou rozhodnout, kdy byste měli použít nástroj App Wrapping a sadu App SDK, aby vaše vlastní obchodní aplikace mohly používat zásady správy mobilních aplikací."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df1b58d5ce94c985e71f3afbe228dba9438040dc
ms.openlocfilehash: d79c498fd775ee9b3d59761fec2fe6ebba116d6d


---

# Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune
Svým aplikacím můžete umožnit použití zásad správy mobilních aplikací (MAM) buď prostřednictvím nástroje Intune App Wrapping, nebo pomocí sady Intune App SDK. V tomto tématu se dozvíte, co tyto dvě metody obnáší a kdy je použít.

## Nástroj Intune App Wrapping
Nástroj App Wrapping se používá hlavně pro interní obchodní aplikace. Je to aplikace příkazového řádku, která vytvoří kolem aplikace obálku, a ta potom umožní správu aplikace pomocí zásad správy mobilních aplikací v Intune. 

K použití nástroje nepotřebujete zdrojový kód, ale potřebujete přihlašovací údaje k podepisování.  Další informace o přihlašovacích údajích k podepisování najdete v [blogu o Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Dokumentaci k nástroji App Wrapping najdete v tématech [Nástroj App Wrapping pro Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) a [Nástroj App Wrapping pro iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Nástroj App Wrapping **nepodporuje** aplikace v App Storu a Google Play Storu ani určité funkce, které vyžadují vývojářskou integraci (projděte si následující tabulku s porovnáním funkcí).

Pokud už je aplikace napsaná nebo pokud není dostupný zdrojový kód, použijte raději nástroj App Wrapping, ne sadu SDK.

**Další informace o nástroji App Wrapping pro MAM na zařízeních, která nejsou registrovaná do Intune, najdete v článku [Ochrana obchodních aplikací a dat na zařízeních neregistrovaných do Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)**.

### Podporované platformy vývoje aplikací

|**Nástroj App Wrapping** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Ano|Ano|
|**Android**| Ne |Ano|

## Sada Intune App SDK
Sada App SDK je určená hlavně zákazníkům, kteří mají aplikace v App Storu nebo Google Play Storu a chtějí mít možnost spravovat je pomocí Intune. Nicméně využít integraci sady SDK může jakákoli aplikace, i obchodní aplikace.

Další informace o sadě SDK najdete v tématu [Přehled](/intune/develop/intune-app-sdk). Pokud chcete začít používat sadu SDK, přečtěte si téma [Začínáme s Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started).

### Podporované platformy vývoje aplikací

|**Sada Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ano – použijte komponentu Xamarin sady Intune App SDK|Ano –použijte plugin Cordova sady Intune App SDK|
|**Android**| Ano – použijte komponentu Xamarin sady Intune App SDK|Ano –použijte plugin Cordova sady Intune App SDK|

## Porovnání funkcí
Tato tabulka obsahuje seznam nastavení, která můžete použít v sadě SDK a nástroji App Wrapping.

> [!NOTE]
> Nástroj App Wrapping se dá použít se samostatnou službu Intune nebo Intune s Configuration Managerem.

|Funkce|Sada App SDK|Nástroj App Wrapping|
|-----------|---------------------|-----------|
|Omezit zobrazování obsahu webu jenom na podnikový spravovaný prohlížeč|X|X|
|Zabránit zálohování Androidu, iTunes a iCloudu|X|X|
|Povolit aplikaci přenos dat do ostatních aplikací|X|X|
|Povolit aplikaci, aby přijímala data z jiných aplikací|X|X|
|Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích|X|X|
|Požadovat jednoduchý kód PIN pro přístup|X|X|
|Nahradit integrovaný PIN kód aplikace PIN kódem Intune|X||
|Určit počet pokusů o zadání PIN kódu před jeho obnovením|X|X|
|Vyžadovat otisk prstu místo PIN kódu (jenom iOS)<br></br>**Poznámka:** Dostupné jenom v prostředích, která používají jenom správu MAM.|X||
|Vyžadovat podnikové přihlašovací údaje pro přístup|X|X|
|Blokovat spuštění spravovaných aplikací v zařízení s jailbreakem nebo rootem|X|X|
|Zašifrovat data aplikací|X|X|
|Znovu zkontrolovat požadavky na přístup po zadaném počtu minut|X|X|
|Zadat období odkladu pro offline režim|X|X|
|Blokovat snímek obrazovky (jenom Android)|X|X|
|Úplné vymazání|X|X|
|Selektivní vymazání <br></br>**Poznámka:** V iOS platí, že při odebrání profilu pro správu se odebere taky příslušná aplikace.|X||
|Zabránit možnosti Uložit jako |X||
|Podpora víc identit|X||
|Podpora MAM bez registrace zařízení|X|X|
### Viz taky

[Nástroj nástroje pro zabalení aplikace Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Nástroj nástroje pro zabalení aplikace iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO4-->


