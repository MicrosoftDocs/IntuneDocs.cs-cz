---
title: "Ochrana dat a aplikací | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ded7bd6c971a9448ad6e6492ebc5e42dfcb5d76e
ms.openlocfilehash: 9445b4b171eb2102d73cf0e866e85b535274eee2


---

# Ochrana dat a aplikací pomocí Microsoft Intune


Intune chrání firemní data prostřednictvím několika technologických vrstev.  Ve vrstvě identity podmíněný přístup chrání služby tím, že umožňuje přístup jenom ze spravovaných a kompatibilních zařízení.  V klientské aplikační vrstvě správa mobilních aplikací (MAM) chrání před ztrátou dat. Zabraňuje v přesunu dat do nechráněných aplikací nebo úložišť a v případě ztráty nebo odcizení zařízení vymaže data.  Tyto dvě vrstvy ochrany by se měly používat společně. Zabezpečí se tak data a zajistí produktivita mobilních pracovních sil.

Důležitým krokem při ochraně firemních dat je implementace podmíněného přístupu, která zajišťuje, že zařízení sloužící pro přístup k těmto datům využívají ochranu zabezpečení, jako jsou silná hesla nebo šifrování, a nemají jailbreak. Microsoft Intune vám dává možnost nastavit podmínky, které zařízení musí dodržovat, aby se jim povolil přístup k datům a e-mailům společnosti.

[Podmíněný přístup](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) je určený dvěma typy zásad, které můžete nastavit v Intune:
- [Zásady dodržování předpisů](introduction-to-device-compliance-policies-in-microsoft-intune.md) určují kompatibilitu zařízení. Vyhodnocují nastavení a podmínky, jako jsou:
  - Kódy PIN a hesla: Můžete vytvořit pravidla, která vyžadují hesla k odemknutí zařízení, složitost hesel a další nastavení související s hesly.
  - Šifrování: Můžete omezit přístup k zařízením, která jsou šifrovaná.
  - Zařízení nemá jailbreak ani root: Intune může zjistit, jestli má zaregistrované zařízení jailbreak, a je možné nastavit zásady tak, aby k takovým zařízením blokovaly přístup.
- [Zásady podmíněného přístupu](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) se konfigurují pro konkrétní službu, jako je Exchange Online nebo SharePoint Online. U každé služby můžete definovat, na které skupiny uživatelů se tyto zásady mají vztahovat. Můžete například zkontrolovat, že všichni ve finančním oddělení mají přístup k firemnímu e-mailu jenom z kompatibilních zaregistrovaných zařízení.

Zabezpečení přístupu k prostředkům společnosti je jenom prvním krokem při ochraně firemních dat. Dál je potřeba mít možnost chránit tato data, jakmile k nim zařízení získá přístup. Data se teď dají kopírovat, přesunout, uložit do jiného umístění nebo sdílet. Intune tento problém řeší tím, že poskytuje možnost omezit přesun dat vytvořením sady pravidel, jako jsou následující:
- Blokovat kopírování a vložení nebo zabránit přesunu dat mimo pracovní kontext.
- Zabránit zálohování do osobního cloudového úložiště a zabránit použití příkazu Uložit jako.
- Zabezpečit přístup k aplikacím chráněným MAM tím, že se vyžaduje zadání kódu PIN, hesla nebo firemních přihlašovacích údajů.
- Otvírat všechny webové odkazy v prohlížeči Intune Managed Browser.

Tyto sady pravidel se označují jako [zásady správy mobilních aplikací (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  Zásady správy mobilních aplikací (MAM) je možné použít pro aplikace běžící na zařízení, která mohou nebo nemusí být spravovaná vámi.  Firemní data můžete chránit pomocí zásad MAM pro zařízení, která jsou zaregistrovaná v Intune, zařízení, která jsou zaregistrovaná a spravovaná jiným řešením MDM třetí strany, nebo zařízení, která nemusí být spravovaná vámi, jako jsou třeba vlastní zařízení jednotlivých zaměstnanců.

Aby bylo možné aplikaci přidružit k zásadě MAM, musí mít začleněnou sadu Microsoft Intune App Software Development Kit (SDK) nebo používat nástroj App Wrapping.

Aplikace Microsoft Office mají sadu App SDK integrovanou. Úplný seznam podporovaných aplikací najdete v [galerii mobilních aplikací Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na stránce partnerů pro aplikace Microsoft Intune. Pokud zvolíte aplikaci, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.

Můžete taky [povolit vlastním obchodním aplikacím](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) použití se zásadami MAM.

Když dojde ke ztrátě nebo odcizení zařízení nebo když uživatel přestane pracovat ve vaší společnosti, můžete kromě omezení přesunu dat taky [selektivně vymazat firemní data](wipe-managed-company-app-data-with-microsoft-intune.md) a ponechat v zařízení jenom osobní data.



<!--HONumber=Jun16_HO4-->


