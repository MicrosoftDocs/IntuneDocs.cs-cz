---
title: "Ochrana aplikací a dat"
description: "Toto téma popisuje různé funkce a možnosti Intune, které jsou k dispozici, aby pomáhaly chránit vaše firemní aplikace a data."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 09b7a1d4901a52845719e8d7094f665b12b91ab4
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="protect-apps-and-data-with-microsoft-intune"></a>Ochrana dat a aplikací pomocí Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune chrání firemní data prostřednictvím několika technologických vrstev. Ve vrstvě identity podmíněný přístup chrání služby tím, že umožňuje přístup jenom ze spravovaných a kompatibilních zařízení. V klientské aplikační vrstvě chrání správa mobilních aplikací (MAM) před únikem informací. Zabraňuje přesunu dat do nechráněných aplikací nebo úložišť a v případě ztráty nebo odcizení zařízení vymaže data. Doporučujeme používat tyto dvě vrstvy ochrany společně. Zabezpečíte tak data a zajistíte produktivitu mobilních pracovních sil.

Důležitým prvním krokem k ochraně dat společnosti je implementace podmíněného přístupu. To provedete tak, že zajistíte, aby zařízení přistupující k těmto datům využívala bezpečnostní ochranu, jako jsou silná hesla nebo šifrování, a že tato zařízení nemají jailbreak. Intune umožňuje nastavit podmínky, které zařízení musí dodržovat, aby jim byl povolen přístup k datům a e-mailům společnosti.

[Podmíněný přístup](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) je určený dvěma typy zásad, které můžete nastavit v Intune:
- [Zásady dodržování předpisů](introduction-to-device-compliance-policies-in-microsoft-intune.md) určují kompatibilitu zařízení. Vyhodnocují nastavení a podmínky, jako jsou:
  - Kódy PIN a hesla: Můžete vytvořit pravidla, která vyžadují hesla k odemknutí zařízení, definují vyžadovanou složitost hesel a určují další nastavení související s hesly.
  - Šifrování: Můžete omezit přístup k zařízením, která jsou šifrovaná.
  - Zařízení nemá jailbreak ani root: Intune může zjistit, jestli má zaregistrované zařízení jailbreak. Můžete nastavit zásady tak, aby u takových zařízení blokovaly přístup.
- [Zásady podmíněného přístupu](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) můžete nakonfigurovat pro konkrétní službu, jako je Exchange Online nebo SharePoint Online. U každé služby můžete definovat, na které skupiny uživatelů se tyto zásady mají vztahovat. Můžete například zkontrolovat, že všichni ve finančním oddělení mají přístup k firemnímu e-mailu jenom z kompatibilních zaregistrovaných zařízení.

Zabezpečení přístupu k prostředkům společnosti je jenom prvním krokem při ochraně firemních dat. I nadále potřebujete mít možnost chránit tato data poté, co k nim zařízení získá přístup. Data se teď dají kopírovat, přesunout, uložit do jiného umístění nebo sdílet. Intune tento problém řeší tím, že poskytuje možnost omezit přesun dat vytvořením sady pravidel, jako jsou následující:
- Blokování kopírování a vložení nebo zamezení přesunu dat mimo pracovní kontext
- Zamezení zálohování do osobního cloudového úložiště a použití příkazu Uložit jako
- Zabezpečení přístupu aplikací vyžadováním zadání kódu PIN, hesla nebo podnikových přihlašovacích údajů
- Otevírání všech webových odkazů v prohlížeči spravovaném v Intune (Intune Managed Browser)

Tyto sady pravidel se označují jako [zásady správy mobilních aplikací (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). Zásady MAM můžete použít u aplikací spuštěných na zařízeních, která můžete nebo nemusíte spravovat.  

Data společnosti můžete chránit použitím zásad MAM pro zařízení, která jsou **zaregistrovaná v Intune**, zařízení, která jsou **zaregistrovaná a spravovaná jiným řešením správy mobilních zařízení (MDM) třetí strany**, nebo zařízení, která **nejsou registrovaná v žádném řešení MDM**, jako jsou třeba vlastní zařízení jednotlivých zaměstnanců.

Aby bylo možné aplikaci přidružit k zásadě MAM, musí mít začleněnou sadu Microsoft Intune App Software Development Kit (SDK) nebo můžete použít nástroj App Wrapping.

Například aplikace Microsoft Office mají sadu Intune App SDK integrovanou. Úplný seznam podporovaných aplikací najdete v [galerii mobilních aplikací Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) na stránce aplikací pro Microsoft Intune od partnerů. Pokud zvolíte aplikaci, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.

Můžete taky [povolit vlastním obchodním aplikacím](/intune/apps-prepare-mobile-application-management) použití se zásadami MAM.

Když dojde ke ztrátě nebo odcizení zařízení nebo když uživatel přestane pracovat ve vaší společnosti, můžete kromě omezení přesunu dat taky [selektivně vymazat firemní data](wipe-managed-company-app-data-with-microsoft-intune.md) a ponechat tak v zařízení jenom osobní data.

