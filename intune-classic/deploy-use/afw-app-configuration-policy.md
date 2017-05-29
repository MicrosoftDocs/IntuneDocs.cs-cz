---
title: "Zásady konfigurace aplikací pro Android for Work | Dokumentace Microsoftu"
description: "Zásady konfigurace mobilních aplikací v Intune umožňují dodat nastavení, která se můžou vyžadovat, když uživatelé spustí aplikaci pro Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 69cee5763cb8a24b4a3be6e981bcd46512bfc3ba
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Konfigurace aplikací pro Android for Work pomocí zásad konfigurace mobilních aplikací v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zásady konfigurace mobilních aplikací v Microsoft Intune slouží k poskytování nastavení, která se můžou požadovat, když uživatelé spustí aplikaci. Aplikace může například vyžadovat, aby uživatelé zadali:

-   Vlastní číslo portu
-   Nastavení jazyka
-   Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, může to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace mobilních aplikací umožňují nasazení těchto nastavení na zařízení před tím, než uživatelé spustí aplikaci. Nastavení se zadá automaticky a uživatelé nemusí provádět žádnou akci.

Aby bylo možné využít zásady konfigurace aplikací, musí vývojář aplikace konfigurace, které vytvoří, zpřístupnit. Například Google Chrome zpřístupňuje nastavení, která umožňují nastavit výchozí záložky, povolené a zakázané weby a další možnosti. Informace o tom, jestli jsou tato nastavení podporovaná a jak se zadávají v zásadách, vám sdělí vývojář aplikace.

Zásadu konfigurace aplikace nasadíte stejným uživatelům, jakým jste nasadili aplikaci, kterou chcete konfigurovat. Nastavení aplikace se použijí při spuštění aplikace.

## <a name="configure-a-mobile-app-configuration-policy"></a>Konfigurace zásady konfigurace mobilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** &gt; **Přehled** &gt; **Přidat zásadu**.

2.  V seznamu zásad rozbalte **Android for Work**, zvolte **Zásady konfigurace mobilních aplikací (Android for Work)** a pak zvolte **Vytvořit zásadu**.

    > [!TIP]
    > Pro tento typ zásad můžete konfigurovat jenom vlastní nastavení. Doporučená nastavení nejsou dostupná.

3.  V části **Obecné** stránky **Vytvořit zásadu** zadejte název a nepovinný popis zásady konfigurace mobilních aplikací.

4. V sekci **Zásady konfigurace mobilních aplikací** této stránky zadejte následující informace:
    - **ID balíčku aplikace, pro kterou tato konfigurace platí** – ID balíčku najdete v části id= adresy URL stránky této aplikace v obchodě Google Play. Například ID balíčku pro aplikaci Microsoft Excel je **com.microsoft.office.excel**.
    - Do textového pole zadejte data nastavení aplikace, která chcete konfigurovat. Tato nastavení získáte od dodavatele aplikace. Ne všechny aplikace tato nastavení podporují.
5.  Kliknutím na **Ověřit** zkontrolujte, že zadaná data mají platný formát seznamu vlastností.

    > [!IMPORTANT]
    > Při kliknutí na **Ověřit** Intune zkontroluje, že zadaná data mají platný formát. Nekontroluje, jestli tato data budou fungovat s aplikací, ke které jsou přidružená.

6.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** .


## <a name="deploy-the-app-configuration-policy"></a>Nasazení zásady konfigurace aplikace
Po vytvoření musíte zásadu konfigurace aplikace nasadit stejným uživatelům, jakým jste nasadili aplikaci, pro kterou budou tato nastavení platit.

Informace o nasazení zásad najdete v tématu [Nasazení zásady konfigurace](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

Informace o nasazení aplikací do zařízení s Androidem for Work najdete v tématu [Jak nasadit aplikace pro Android for Work pomocí Intune](android-for-work-apps.md).

Při spuštění aplikace nasazené do zařízení se aplikace spustí s nastavením, které jste nakonfigurovali v zásadě konfigurace mobilních aplikací.

> [!TIP]
> Pro každou aplikaci nasaďte uživateli jen jednu zásadu konfigurace aplikace.

