---
title: "Používání zásad konfigurace mobilních aplikací pro iOS"
description: "Zásady konfigurace mobilních aplikací v Intune slouží k poskytování nastavení, která se můžou požadovat, když uživatelé spustí aplikaci pro iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f13baeec9e0a38ac27ae42d1bc766cf22d73634
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zásady konfigurace mobilních aplikací v Microsoft Intune slouží k poskytování nastavení, která se můžou požadovat, když uživatelé spustí aplikaci. Aplikace může například vyžadovat, aby uživatelé zadali:

-   Vlastní číslo portu

-   Nastavení jazyka

-   Nastavení zabezpečení

-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace mobilních aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásady nasadit tato nastavení pro uživatele dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Tyto zásady nenasazujte přímo na uživatele a zařízení. Místo toho přidružíte zásadu k aplikaci, a pak nasadíte aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Nasazení aplikací pomocí Microsoft Intune](deploy-apps.md).

## <a name="configure-a-mobile-app-configuration-policy"></a>Konfigurace zásady konfigurace mobilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** &gt; **Přehled** &gt; **Přidat zásadu**.

2.  V seznamu zásad rozbalte **iOS**, zvolte **Konfigurace mobilních aplikací** a pak zvolte **Vytvořit zásadu**.

    > [!TIP]
    > Pro tento typ zásad můžete konfigurovat jenom vlastní nastavení. Doporučená nastavení nejsou dostupná.

3.  V části **Obecné** stránky **Vytvořit zásadu** zadejte název a nepovinný popis zásady konfigurace mobilních aplikací.

4.  V části **Zásada konfigurace mobilních aplikací** stránky zadejte nebo vložte do pole seznam vlastností XML obsahující požadovaná konfigurační nastavení aplikace. Formát seznamu vlastností XML se bude lišit v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.

    > [!TIP]
    > Další informace o seznamech vlastností XML najdete v tématu [Vysvětlení seznamů vlastností XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) v knihovně iOS Developer Library.

5.  Klikněte na **Ověřit**, abyste zkontrolovali, že zadaný kód XML má platný formát seznamu vlastností.

    > [!IMPORTANT]
    > Když kliknete na **Ověřit**, Intune zkontroluje, že zadaný kód XML má platný formát. Nekontroluje, že seznam vlastností XML bude fungovat s aplikací, ke které je přidružený.

6.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** .

## <a name="information-about-the-xml-file-format"></a>Informace o formátu souboru XML

Intune podporuje v seznamu vlastností následující typy dat:
    
- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; nebo &lt;false /&gt;
     
Další informace o typech dat najdete v tématu [Informace o seznamech vlastností](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) v knihovně iOS Developer Library.

Intune dál v seznamu vlastností podporuje následující typy tokenů:
- \{\{userprincipalname\}\} – (Příklad: **John@contoso.com**)
- \{\{mail\}\} – (Příklad: **John@contoso.com**)
- \{\{partialupn\}\} – (Příklad: **Jan**)
- \{\{accountid\}\} – (Příklad: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Příklad: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Příklad: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Příklad: **Jiri Polak**)
- \{\{serialnumber\}\} – (Příklad: **F4KN99ZUG5V2**) pro zařízení s iOSem
- \{\{serialnumberlast4digits\}\} – (Příklad: **G5V2**) pro zařízení s iOSem
    
Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a>Přidružení zásady konfigurace mobilních aplikací k aplikaci
Po vytvoření musíte zásadu konfigurace mobilních aplikací přiřadit k aplikaci iOS, na kterou se mají nastavení v zásadě konfigurace vztahovat.

Postupujte podle kroků pro vytvoření nasazení aplikace v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) a [Nasazení aplikací pomocí Microsoft Intune](deploy-apps-in-microsoft-intune.md). Až v průvodci přejdete na stránku **Konfigurace mobilních aplikací**, z rozevíracího seznamu **Zásady konfigurace aplikací** vyberte zásady, které chcete k aplikaci přidružit.

Potom pokračujte v nasazení a monitorování nasazení aplikace obvyklým způsobem.

Při spuštění aplikace nasazené do zařízení se aplikace spustí s nastavením, které jste nakonfigurovali v zásadě konfigurace mobilních aplikací.

> [!TIP]
> V případě konfliktu jedné nebo více zásad konfigurace mobilních aplikací se nevynutí ani jedna zásada. Konflikt se ohlásí v **Řídicím panelu** konzoly pro správu Intune.

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a>Příklad formátu pro soubor XML konfigurace mobilních aplikací

Když vytvoříte soubor konfigurace mobilních aplikací, můžete pomocí tohoto formátu zadat jednu nebo několik následujících hodnot:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```
