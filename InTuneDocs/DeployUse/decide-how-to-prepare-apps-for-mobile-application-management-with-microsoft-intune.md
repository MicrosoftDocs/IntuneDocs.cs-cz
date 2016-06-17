---
# required metadata

title: Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune
Svým aplikacím můžete umožnit použití zásad správy mobilních aplikací buď prostřednictvím nástroje Intune App Wrapping, nebo pomocí sady Intune App SDK. V tomto tématu se dozvíte, co tyto dvě metody obnáší a kdy je použít.

## Nástroj Intune App Wrapping
Nástroj App Wrapping se používá hlavně pro interní obchodní aplikace. Je to aplikace příkazového řádku, která vytvoří kolem aplikace obálku, a ta potom umožní správu aplikace pomocí zásad správy mobilních aplikací v Intune. K použití nástroje nepotřebujete zdrojový kód, ale potřebujete přihlašovací údaje k podepisování.  Další informace o přihlašovacích údajích k podepisování najdete na [blogu o Intune](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx). Dokumentaci k nástroji App Wrapping najdete v tématech [Nástroj App Wrapping pro Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) a [Nástroj App Wrapping pro iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)..

Nástroj App Wrapping nepodporuje aplikace v App Storu a Play Storu ani funkce, které vyžadují integraci doby vývoje (projděte si následující tabulku s porovnáním funkcí).

Pokud už je aplikace napsaná nebo pokud není dostupný zdrojový kód, použijte raději nástroj App Wrapping, ne sadu SDK.

## Sada Intune App SDK
Sada App SDK je určená hlavně zákazníkům, kteří mají aplikace v App Storu nebo Play Storu a chtějí je moct spravovat pomocí Intune. Integraci sady SDK ale může využít jakákoli aplikace, třeba i obchodní aplikace.

K integraci sady SDK potřebujete přístup ke zdrojovému kódu aplikace. Pokyny k integraci sady SDK najdete v tématu [Microsoft Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx)..

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

### Související témata
[Nástroj nástroje pro zabalení aplikace Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Nástroj nástroje pro zabalení aplikace iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


