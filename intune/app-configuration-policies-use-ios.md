---
title: "Použití zásad konfigurace aplikací v Intune pro iOS"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak používat zásady konfigurace aplikací pro účely předání konfiguračních dat do aplikace pro iOS, při jejím spuštění."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Použití zásad konfigurace aplikací v Intune pro iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, která se mohou vyžadovat, když uživatelé spustí aplikaci pro iOS. Aplikace může například vyžadovat, aby uživatelé zadali:

-   Vlastní číslo portu

-   Nastavení jazyka

-   Nastavení zabezpečení

-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásad přiřadit tato nastavení uživatelům dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

> [!TIP]
> Tento typ zásad je nyní k dispozici pouze pro zařízení se systémem iOS 8.0 a novějším. Podporuje následující typy instalací aplikací:
>
> -   **Spravované aplikace pro iOS z obchodu s aplikacemi**
> -   **Balíček aplikace pro iOS**
>
> Další informace o typech instalace aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Vytvoření zásad konfigurace aplikací

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Zásady konfigurace aplikací**.

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

Potom pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.

Spuštěná aplikace přiřazená zařízení se spustí s nastavením, které jste nakonfigurovali v zásadách konfigurace aplikací.

> [!TIP]
> V případě konfliktu jedné nebo více zásad konfigurace aplikací se nevynutí žádná zásada.

## <a name="create-a-mam-targeted-configuration-policy"></a>Vytvoření zásady konfigurace cílené na MAM
Konfigurace určená pro správu mobilních aplikací (MAM) umožňuje aplikacím přijímat konfigurační data prostřednictvím sady SDK aplikace Intune. Formát a varianty těchto dat musí vlastník aplikace nebo její vývojář definovat a oznámit zákazníkům, kteří využívají Intune. Správci Intune mohou konfigurační data zacílit a nasadit prostřednictvím konzoly Intune Azure. Data konfigurace cílené na MAM lze předávat do aplikací s podporou MAM-WE prostřednictvím služby MAM. Seznam povolených/zakázaných adres URL má například [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser). Konfigurační data aplikace se odešlou přímo do aplikace přes službu MAM, nikoliv prostřednictvím kanálu MDM. [Zásady konfigurace aplikací MDM](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) představují nativní řešení prostřednictvím správy mobilních zařízení (MDM). Od konfigurace cílené na MAM se liší hlavně v tom, že zařízení, na kterém je aplikace spuštěná, nemusí být v MDM zaregistrované. Konfigurace cílená na MAM je k dispozici pro iOS i Android. Pro iOS musí mít aplikace začleněnou sadu Intune App SDK pro iOS (verze 7.0.1) a musí se účastnit nastavení konfigurace aplikace. Zásadu konfigurace cílené na MAM vytvoříte tímto způsobem: 

1. Přihlaste se k **portálu Azure Portal**.

2. Vyberte **Intune > Mobilní aplikace – Zásady konfigurace aplikací**.

3. V okně **Zásady konfigurace aplikací** vyberte možnost **Přidat**.

4. Zadejte **název** a volitelný **popis** nastavení konfigurace aplikace a potom vyberte **Nezaregistrováno přes Intune**.

5. Klikněte na **Vyberte požadované aplikace** a potom v okně **Cílové aplikace** zvolte aplikace pro požadované platformy. <br>
**Poznámka:** U obchodních aplikací klikněte na **Další aplikace**. Zadejte ID balíčku vaší aplikace.

6. Kliknutím na **OK** se vraťte do okna **Přidat konfiguraci aplikace**.

7. Vyberte možnost **Definovat konfiguraci**. V okně **Konfigurace** definujte dvojice klíč-hodnota, které budou určovat konfiguraci.

8. Když jste hotovi, klikněte na **OK**.

9. V okně **Přidat konfiguraci aplikace** vyberte možnost **Vytvořit**.

Vytvoří se nová konfigurace, která se zobrazí v okně Konfigurace aplikací.

Potom pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.

Aplikace přiřazená zařízení (integrovaná se sadou Intune APP SDK) se spustí s nastavením, které jste nakonfigurovali v zásadě konfigurace cílené na MAM. Součástí přiřazené aplikace musí být podporovaná verze sady Intune APP SDK. Další informace o požadavcích na použití zásad konfigurace cílené na MAM při vývoji aplikací najdete v článku [Průvodce integrací sady Intune APP SDK pro iOS](https://docs.microsoft.com/intune/app-sdk-ios).

Další informace o možnostech rozhraní Graph API s ohledem na hodnoty konfigurace cílené na MAM najdete v článku [Referenční informace pro Graph API: Konfigurace cílená na MAM](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

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
