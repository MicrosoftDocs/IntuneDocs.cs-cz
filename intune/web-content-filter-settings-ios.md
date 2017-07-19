---
title: "Nastavení filtru webového obsahu v Intune pro zařízení s iOSem"
titleSuffix: Intune on Azure
description: "Přečtěte si informace o tom, jaká nastavení slouží k povolení a blokování přístupu k webovým stránkám ze zařízení s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fb2ce8ed9db6ff808cac2ee8ff46ee865dbdf35
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Nastavení filtru webového obsahu pro zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí těchto nastavení můžete konfigurovat adresy URL, které koncoví uživatelé webových prohlížečů na zařízeních s iOSem můžou nebo nemůžou navštívit. Ke konfiguraci adres URL můžete použít dvě metody:

- **Konfigurovat adresy URL** – použijte integrovaný webový filtr společnosti Apple, který hledá výrazy nevhodné pro děti jako neslušná slova nebo sexuálně explicitní výrazy. Tato funkce vyhodnocuje každou webovou stránku při načítání a snaží se identifikovat a blokovat nevhodný obsah. Můžete také konfigurovat adresy URL, které filtr nekontroluje, nebo adresy URL, které jsou blokované, bez ohledu na nastavení filtru.

- **Jenom konkrétní weby** (jenom pro webový prohlížeč Safari) – tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel smí navštěvovat **jenom** tyto weby. Žádné jiné weby navštívit nejde. Tuto možnost použijte jenom v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.
Pokud nezadáte žádné adresy URL, koncoví uživatelé nebudou mít přístup k žádným webům s výjimkou webů microsoft.com, microsoft.net a apple.com.



## <a name="get-started"></a>Začínáme

1. V okně Funkce zařízení zvolte **Filtr webového obsahu (jenom pod dohledem)**.
2. V okně **Filtr webového obsahu** zvolte **Typ filtru**, který chcete nakonfigurovat:
    - **Nenakonfigurováno** – neprovádí se žádné filtrování.
    - **Konfigurovat adresy URL**
    - **Jenom konkrétní weby**
3. Potom v závislosti na použitém typu filtru zvolte jeden z následujících postupů:


## <a name="configure-urls"></a>Konfigurovat adresy URL

1. Podle potřeby v okně **Filtr webového obsahu** vyberte jedno z následujících nastavení:
    - **Povolené adresy URL** – v okně **Povolené adresy URL** zadejte adresy URL, které chcete povolit (pomocí obcházení webového filtru Apple), a po každé z nich použijte Enter.
    - **Blokované adresy URL** – v okně **Blokované adresy URL** zadejte adresy URL, které chcete blokovat (bez ohledu na nastavení webového filtru Apple), a po každé z nich použijte Enter.
2. Po skončení klikněte na tlačítko **OK**.


## <a name="specific-websites-only"></a>Jenom konkrétní weby

1. V okně **Filtr webového obsahu** nakonfigurujte pro každý web, který chcete povolit, následující nastavení:
    - **Adresa URL** – zadejte adresu URL webu, který chcete povolit, třeba **http://www.contoso.com**.
    - **Cesta k záložce** – zadejte cestu, kam chcete uložit záložku, třeba **/Contoso/Obchodní aplikace**. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
    - **Název** – zadejte popisný název záložky.
2. Po zadání údajů pro jednotlivé weby klikněte na **Přidat**.
3. Po skončení klikněte na tlačítko **OK**.

>[!IMPORTANT] 
> Intune automaticky povoluje tyto adresy URL:
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Dokončení

Zvolením **OK** se vraťte do okna **Vytvořit profil** a pak zvolte **Vytvořit**.

## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).
