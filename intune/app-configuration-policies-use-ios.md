---
title: "Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem | Dokumentace Microsoftu"
titlesuffix: Azure portal
description: "Přečtěte si, jak používat zásady konfigurace aplikací pro účely předání konfiguračních dat do aplikace pro iOS při jejím spuštění."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d293ff6001ef937c7da0055e6642aa5a1226bd2e
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, když uživatelé spustí aplikaci pro iOS. Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použijí, když je aplikace zjistí (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Vytvoření zásad konfigurace aplikací

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. Zvolte úlohu **Mobilní aplikace**.
4. Ve skupině **Spravovat** klikněte na **Zásady konfigurace aplikací** a pak klikněte na **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**  
      Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**  
      Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**  
      Zvolte **Spravovaná zařízení**.
6. Jako **platformu** vyberte **iOS**.
7.  Zvolte **Přidružená aplikace** a pak v okně **Přidružená aplikace** zvolte spravovanou aplikaci, u které chcete použít konfiguraci.
8.  V okně **Přidat zásady konfigurace** zvolte **Nastavení konfigurace**.
9. Vyberte **Formát nastavení konfigurace**. Vyberte jednu z těchto možností:
    - **[Použít návrháře konfigurace](#Use-the-configuration-designer)**
    - **[Zadat XML data](#enter-xml-data)**
10. Klikněte na **OK** a pak na **Přidat**.

## <a name="use-configuration-designer"></a>Použití návrháře konfigurace

Návrháře konfigurace můžete použít u aplikací jak v zařízeních, která jsou zaregistrovaná v Intune, tak i v zařízeních, která zaregistrovaná nejsou. Návrhář umožňuje nakonfigurovat konkrétní klíče a hodnoty konfigurace. Pro každou hodnotu musíte také zadat datový typ. Nastavení se aplikaci poskytne automaticky při její instalaci.

### <a name="add-a-setting"></a>Přidání nastavení

1. Pro každý klíč a hodnotu v konfiguraci nastavte: <ul><li>**Konfigurační klíč**<br>Slouží k jedinečné identifikaci konkrétní konfigurace nastavení.</li><li>**Typ hodnoty**<br>Datový typ konfigurační hodnoty. Mezi typy patří integer, real, string a boolean.</li><li>**Hodnota konfigurace**<br>Hodnota konfigurace</li></ul>
2. Klikněte na **OK** a zadejte nastavení konfigurace.

### <a name="delete-a-setting"></a>Odstranění nastavení

1. Vedle nastavení klikněte na tři tečky (...).
2. Vyberte **Odstranit**.

Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.

## <a name="enter-xml-data"></a>Zadání dat XML

Můžete zadat nebo vložit seznam vlastností XML, který obsahuje nastavení konfigurace aplikace pro zařízení zaregistrovaná v Intune. Formát seznamu vlastností XML se liší v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.

Intune ověří formát XML. Intune ale nekontroluje, jestli bude seznam vlastností XML fungovat s cílovou aplikací.
Další informace o seznamech vlastností XML najdete v tématu [Vysvětlení seznamů vlastností XML].

Další informace o seznamech vlastností XML:

  -  Přečtěte si článek [Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Projděte si informace uvedené v článku [Vysvětlení seznamů vlastností XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) v knihovně pro vývojáře aplikací pro iOS.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Příklad formátu pro soubor XML konfigurace aplikací

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
### <a name="supported-xml-plist-data-types"></a>Podporované datové typy v seznamu vlastností XML

Intune podporuje v seznamu vlastností následující typy dat:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; nebo &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Tokeny použité v seznamu vlastností

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

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.