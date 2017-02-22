---
title: "Jak používat zásady konfigurace aplikace Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si, jak používat zásady konfigurace aplikace pro účely předání konfiguračních dat do aplikace pro iOS, když se spustí."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 75e3f3f62dd392cda1530321b12cd27e9ee8847f

---

# <a name="how-to-use-intune-app-configuration-policies"></a>Použití zásad konfigurace aplikací v Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, která se můžou vyžadovat, když uživatelé spustí aplikaci. Aplikace může například vyžadovat, aby uživatelé zadali:

-   Vlastní číslo portu

-   Nastavení jazyka

-   Nastavení zabezpečení

-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásad přiřadit tato nastavení uživatelům dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci, a pak nasadíte aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](/intune-azure/manage-apps/add-apps).

## <a name="create-an-app-configuration-policy"></a>Vytvoření zásad konfigurace aplikací

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
1.  V úloze **Spravovat aplikace** zvolte **Spravovat** > **Zásady konfigurace aplikací**.

2.  V okně seznamu zásad zvolte **Přidat**.

3.  V okně **Přidat zásady konfigurace** zadejte název a volitelný popis pro zásady konfigurace aplikace.
4.  Zvolte **Přidružená aplikace** a pak v okně **Přidružená aplikace** zvolte spravovanou aplikaci, u které chcete použít konfiguraci.
5.  V okně **Přidat zásady konfigurace** zvolte **Nastavení konfigurace** a potom v okně Nastavení konfigurace, zvolte způsob, jak se mají určit hodnoty XML, které tvoří konfigurační profil:
    - **Zadat XML data** – zadejte nebo vložte seznam vlastností XML, který obsahuje požadované konfigurační nastavení aplikace. Formát seznamu vlastností XML se bude lišit v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.
    Intune zkontroluje, že má zadaný kód XML platný formát. Nekontroluje, že seznam vlastností XML bude fungovat s aplikací, ke které je přidružený.
    Další informace o seznamech vlastností XML najdete v tématu [Vysvětlení seznamů vlastností XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) v knihovně iOS Developer Library.
    - **Použít návrháře konfigurace** – umožňuje určit dvojice klíče a hodnoty XML přímo na portálu.
8. Až to budete mít, vraťte se do okna **Přidat zásady konfigurace** a klikněte na **Vytvořit**.

Zásady se vytvoří a zobrazí se v okně se seznamem zásad.

Potom pokračujte s [přiřazením](deploy-apps.md) a [sledováním](monitor-apps.md) aplikace jako obvykle.

Spuštěná aplikace přiřazená zařízení se spustí s nastavením, které jste nakonfigurovali v zásadách konfigurace aplikací.

> [!TIP]
> V případě konfliktu jedné nebo více zásad konfigurace aplikací se nevynutí žádná zásada.

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





## <a name="example-format-for-an-app-configuration-xml-file"></a>Příklad formátu pro soubor XML konfigurace aplikací

Když vytvoříte soubor konfigurace aplikací, můžete pomocí tohoto formátu zadat jednu nebo několik následujících hodnot:

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



<!--HONumber=Feb17_HO1-->


