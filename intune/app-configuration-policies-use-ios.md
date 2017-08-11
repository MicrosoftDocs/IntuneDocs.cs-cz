---
title: "Použití zásad konfigurace aplikací v Intune pro iOS"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak používat zásady konfigurace aplikací pro účely předání konfiguračních dat do aplikace pro iOS, při jejím spuštění."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b261834c85a9dd3cbc6f8fae40933dd7a79acf93
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Použití zásad konfigurace aplikací v Intune pro iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, která se použijí, když uživatelé spustí aplikaci pro iOS. Aplikace může například vyžadovat, aby uživatelé zadali:

-   Vlastní číslo portu

-   Nastavení jazyka

-   Nastavení zabezpečení

-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásad přiřadit tato nastavení uživatelům dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci. Aplikace musejí být napsané tak, aby podporovaly používání konfigurací aplikací. Další informace získáte od dodavatele aplikace.

Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Vytvoření zásad konfigurace aplikací
1.  Přihlaste se k portálu Azure Portal.
2.  Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Intune** zvolte **Mobilní aplikace**.
4.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Zásady konfigurace aplikací**.
5.  V okně seznamu zásad zvolte **Přidat**.
6.  V okně **Přidat zásady konfigurace** zadejte **Název** a volitelný **Popis** pro zásady konfigurace aplikace.
7.  Jako **Typ registrace zařízení** vyberte jednu z těchto možností:
    - **Zaregistrováno přes Intune** – pro aplikace, které jsou spravované pomocí Intune.
    - **Nezaregistrováno přes Intune** – pro aplikace, které nejsou spravované pomocí Intune nebo jsou spravované jiným řešením.
8.  Jako **platformu** zvolte **iOS** (jenom pro zařízení zaregistrovaná přes Intune).
9.  Zvolte **Přidružená aplikace** a pak v okně **Přidružená aplikace** zvolte spravovanou aplikaci, u které chcete použít konfiguraci.
10. V okně **Přidat zásady konfigurace** zvolte **Nastavení konfigurace**.
11. V okně **Nastavení konfigurace** zvolte způsob, jak se mají určit hodnoty XML, které tvoří konfigurační profil:
    - **Zadat XML data**(jenom pro zařízení zaregistrovaná přes Intune) – zadejte nebo vložte seznam vlastností XML, který obsahuje požadované konfigurační nastavení aplikace. Formát seznamu vlastností XML se liší v závislosti na aplikaci, kterou konfigurujete. Podrobnosti o přesném formátu, který se má použít, získáte od dodavatele aplikace.
Intune zkontroluje, že má zadaný kód XML platný formát. Nekontroluje, jestli seznam vlastností XML funguje s aplikací, ke které je přidružený.
Další informace o seznamech vlastností XML najdete v tématu [Vysvětlení seznamů vlastností XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) v knihovně iOS Developer Library.
    - **Použít návrháře konfigurace** (bez ohledu na to, jestli je zařízení zaregistrováno přes Intune) – umožňuje určit dvojice klíče a hodnoty XML přímo na portálu.
11. Až to budete mít, vraťte se do okna **Přidat zásady konfigurace** a klikněte na **Vytvořit**.

Zásady se vytvoří a zobrazí se v okně se seznamem zásad.



>[!Note]
>Pomocí sady [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) můžete připravit, aby se obchodní aplikace spravovaly pomocí zásad ochrany aplikací Intune a zásad konfigurace aplikací bez ohledu na to, jestli je zařízení zaregistrováno přes Intune. Můžete třeba použít zásadu konfigurace aplikací ke konfiguraci povolených a blokovaných adres URL pro [Intune Managed Browser](app-configuration-managed-browser.md). Když je aplikace s těmito zásadami kompatibilní, můžete ji pomocí zásad nakonfigurovat.


Když se přiřazená aplikace na zařízení spustí, použijí se nastavení, která jste nakonfigurovali v zásadách konfigurace aplikací.
Informace o tom, co se stane, když jedna nebo více zásad aplikací kolidují, najdete v dokumentaci k aplikaci, kterou konfigurujete.

>[!Tip]
>K provedení těchto úkolů můžete použít také Graph API. Podrobnosti najdete v [referenčních informacích o cílové konfiguraci MAM pomocí Graph API](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


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

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.