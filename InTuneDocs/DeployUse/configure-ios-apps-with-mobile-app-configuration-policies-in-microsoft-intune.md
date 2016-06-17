---
# required metadata

title: Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune
Zásady konfigurace mobilních aplikací v Microsoft Intune slouží k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci. Aplikace může například vyžadovat, aby uživatel zadal:

-   Vlastní číslo portu při spuštění

-   Nastavení jazyka

-   Nastavení zabezpečení

-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadá uživatel špatně, můžete to zvýšit zatížení vašeho helpdesku a také zpomalit přijímání nových aplikací.

Zásady konfigurace mobilních aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásady nasadit tato nastavení pro uživatele dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatel nemusí provádět žádnou akci.

Tyto zásady nenasazujte přímo na uživatele a zařízení. Místo toho přidružíte zásadu k aplikaci, a pak nasadíte aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 7.1 a novějším a podporuje následující typy instalací aplikací:
> 
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
> 
> Další informace o typech instalace aplikací najdete v tématu [Nasazení aplikací pomocí Microsoft Intune](deploy-apps.md)..

## Konfigurace zásady konfigurace mobilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Přehled** &gt; **Přidat zásadu**..

2.  V seznamu zásad rozbalte **iOS**, klikněte na **Konfigurace mobilních aplikací**a pak klikněte na **Vytvořit zásadu**..

    > [!TIP]
    > Můžete konfigurovat jenom vlastní nastavení pro tento typ zásad. Doporučená nastavení nejsou dostupná.

3.  V části **Obecné** stránky **Vytvořit zásadu** zadejte název a nepovinný popis zásady konfigurace mobilních aplikací.

4.  V části **Zásada konfigurace mobilních aplikací** stránky zadejte nebo vložte do pole seznam vlastností XML obsahující požadovaná konfigurační nastavení aplikace.

    > [!TIP]
    > Další informace o seznamech vlastností XML najdete v tématu [Vysvětlení seznamů vlastností XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) v knihovně iOS Developer Library.
    > 
    > Formát seznamu vlastností XML se bude lišit v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.
    > 
    > Intune podporuje v seznamu vlastností následující typy dat:
    > 
    > &lt;celé číslo&gt;
    > &lt;reálné číslo&gt;
    > &lt;řetězec&gt;
    > &lt;pole&gt;
    > &lt;dict&gt;
    > &lt;true /&gt; nebo &lt;false /&gt;
    > 
    > Další informace o typech dat najdete v tématu [Informace o seznamech vlastností](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) v knihovně iOS Developer Library.
    >
        > Intune dál v seznamu vlastností podporuje následující typy tokenů:
    >    
    > \{\{userprincipalname\}\} – (příklad: **John@contoso.com**))
    > \{\{mail\}\} – (příklad: **John@contoso.com**))
    > \{\{partialupn\}\} – (příklad: **John**))
    > \{\{accountid\}\} – (příklad: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**))
    > \{\{deviceid\}\} – (příklad: **b9841cd9-9843-405f-be28-b2265c59ef97**))
    > \{\{userid\}\} – (příklad: **3ec2c00f-b125-4519-acf0-302ac3761822**))
    > \{\{username\}\} – (příklad: **John Doe**))
    > \{\{serialnumber\}\} – (příklad: **F4KN99ZUG5V2**) pro zařízení s iOS
    > \{\{serialnumberlast4digits\}\} – (příklad: **G5V2**) pro zařízení s iOS
>
> Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.




5.  Klikněte na **Ověřit** , abyste zkontrolovali, že zadaný kód XML má platný formát seznamu vlastností.

    > [!IMPORTANT]
    > Když kliknete na **Ověřit**, Intune zkontroluje, že zadaný kód XML má platný formát. Nekontroluje, že seznam vlastností XML bude fungovat s aplikací, ke které je přidružen.

6.  Po dokončení klikněte na **Uložit zásadu**..

Nová zásada se zobrazí v uzlu **Zásady konfigurace** .

## Přidružení zásady konfigurace mobilních aplikací k aplikaci
Po vytvoření musíte zásadu konfigurace mobilních aplikací přiřadit k aplikaci iOS, na kterou se mají nastavení v zásadě konfigurace vztahovat.

Postupujte podle kroků pro vytvoření nasazení aplikace v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) a [Nasazení aplikací pomocí Microsoft Intune](deploy-apps-in-microsoft-intune.md). Až v průvodci přejdete na stránku **Konfigurace mobilních aplikací**, z rozevíracího seznamu **Zásady konfigurace aplikací** vyberte zásady, které chcete k aplikaci přidružit.

Potom pokračujte v nasazení a monitorování nasazení aplikace obvyklým způsobem.

Při spuštění aplikace nasazené do zařízení se aplikace spustí s nastavením, které jste nakonfigurovali v zásadě konfigurace mobilních aplikací.

> [!TIP]
> V případě konfliktu jedné nebo více zásad konfigurace mobilních aplikací se nevynutí ani jedna zásada a konflikt se ohlásí v **Řídicím panelu **konzoly pro správu..

## Příklad formátu pro soubor XML konfigurace mobilních aplikací

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




<!--HONumber=May16_HO1-->


