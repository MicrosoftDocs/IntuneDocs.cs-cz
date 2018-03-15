---
title: "Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem"
titlesuffix: Microsoft Intune
description: "Přečtěte si, jak používat zásady konfigurace aplikací pro účely předání konfiguračních dat do aplikace pro iOS při jejím spuštění."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee17ceae0af131f683341f2346f92ad5ef03ed16
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, když uživatelé spustí aplikaci pro iOS. Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použijí, když je aplikace zjistí (obvykle při prvním spuštění).

Zásady konfigurace aplikace pro skupinu můžete přiřadit skupině uživatelů a zařízení s použitím kombinace zahrnutí a vyloučení přiřazení. Jakmile přidáte zásady konfigurace aplikace, můžete u těchto zásad konfigurace aplikací nastavit přiřazení. Když nastavíte přiřazení zásad, můžete zahrnout a vyloučit skupiny uživatelů, na které se zásady vztahují. Když zvolíte možnost zahrnout jednu nebo více skupin, můžete zahrnout konkrétní nebo integrované skupiny. Mezi integrované skupiny patří **Všichni uživatelé**, **Všechna zařízení** a **Všichni uživatelé a všechna zařízení**. 

>[!NOTE]
>V Intune máte v konzole pohodlně k dispozici předem vytvořené skupiny **Všichni uživatelé** a **Všechna zařízení** s integrovanými optimalizacemi. Důrazně doporučujeme, abyste pro cílení na všechny uživatele a zařízení používali tyto skupiny a nepoužívali žádné skupiny Všichni uživatelé nebo Všechna zařízení, které byste sami vytvořili.

Když máte vybrané zahrnuté skupiny pro zásady konfigurace aplikace, můžete také konkrétní skupiny vyloučit.

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Vytvoření zásad konfigurace aplikací

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Zvolte úlohu **Mobilní aplikace**.
4. Ve skupině **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**<br>
      Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**<br>
      Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**<br>
      Zvolte **Spravovaná zařízení**.
6. V poli **Platforma** vyberte **iOS**.
7.  Zvolte **Přidružená aplikace**. Pak v podokně **Přidružená aplikace** zvolte spravovanou aplikaci, u které chcete použít danou konfiguraci, a vyberte **OK**.
8.  V podokně **Přidat zásady konfigurace** zvolte **Nastavení konfigurace**.
9. Vyberte **Formát nastavení konfigurace**. Vyberte jednu z těchto možností:
    - **[Použít návrháře konfigurace](#use-configuration-designer)**
    - **[Zadat XML data](#enter-xml-data)**
10. Po přidání informací XML, zvolte **OK** a potom **Přidat** a přidejte zásadu konfigurace. Zobrazí se podokno s přehledem zásad konfigurace.
11. Po výběru možnosti **Přiřazení** se zobrazí možnosti zahrnutí a vyloučení. 

    ![Snímek obrazovky s přiřazením zásad – karta Zahrnout](./media/app-config-policy01.png)
12. Na kartě **Zahrnout** vyberte **Všichni uživatelé**.

    ![Snímek obrazovky s přiřazením zásad – možnost rozevírací nabídky Všichni uživatelé](./media/app-config-policy02.png)
13. Vyberte kartu **Vyloučit**. 
14. Klikněte na možnost **Vybrat skupiny, které se vyloučí** a zobrazte tak související podokno.

    ![Snímek obrazovky s přiřazením zásad – okno Vybrat skupiny, které se vyloučí](./media/app-config-policy03.png)
15. Vyberte skupiny, které chcete vyloučit, a potom klikněte na **Vybrat**.

    >[!NOTE]
    >Pokud přidáváte skupinu a pro daný typ přiřazení už byla zahrnuta jakákoliv jiná skupina, je pro ostatní typy zahrnutí přiřazení předem vybraná a není ji možné změnit. Tato použitá skupina se tedy nedá použít jako vyloučená skupina.
16. Klikněte na **Uložit**.

## <a name="use-configuration-designer"></a>Použití návrháře konfigurace

Návrháře konfigurace můžete použít u aplikací jak v zařízeních, která jsou zaregistrovaná v Intune, tak i v zařízeních, která zaregistrovaná nejsou. Návrhář umožňuje nakonfigurovat konkrétní klíče a hodnoty konfigurace. Pro každou hodnotu musíte také zadat datový typ. Nastavení se aplikacím poskytne automaticky při jejich instalaci.

### <a name="add-a-setting"></a>Přidání nastavení

1. Pro každý klíč a hodnotu v konfiguraci nastavte:
   - **Konfigurační klíč**<br>
     Klíč, který jedinečně identifikuje konkrétní konfiguraci nastavení
   - **Typ hodnoty**<br>
     Datový typ konfigurační hodnoty. Mezi typy patří integer, real, string a boolean.
   - **Hodnota konfigurace**<br>
     Hodnota konfigurace
2. Zvolte **OK** a nastavte tak nastavení konfigurace.

### <a name="delete-a-setting"></a>Odstranění nastavení

1. Zvolte tři tečky (**...**) vedle příslušného nastavení.
2. Vyberte **Odstranit**.

Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.

## <a name="enter-xml-data"></a>Zadání XML dat

Můžete zadat nebo vložit seznam vlastností XML, který obsahuje nastavení konfigurace aplikace pro zařízení zaregistrovaná v Intune. Formát seznamu vlastností XML se liší v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.

Intune ověří formát XML. Intune ale nekontroluje, jestli seznam vlastností XML funguje s cílovou aplikací.

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
- \{\{userprincipalname\}\} – například **John@contoso.com**
- \{\{mail\}\} – například **John@contoso.com**
- \{\{partialupn\}\} – například **John**
- \{\{accountid\}\} – například **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\} – například **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\} – například **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} – například **John Doe**
- \{\{serialnumber\}\} – například **F4KN99ZUG5V2** (pro zařízení s iOSem)
- \{\{serialnumberlast4digits\}\} – například **G5V2** (pro zařízení s iOSem)

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.