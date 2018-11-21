---
title: Nastavení filtru webového obsahu v Microsoft Intune pro zařízení s iOSem
titlesuffix: ''
description: Přečtěte si, jaká nastavení Microsoft Intune můžete použít k povolení a blokování přístupu k webovým stránkám ze zařízení s iOSem.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: af2029fb42cf132ea8df01f1b4152653ed6e4a26
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187884"
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Nastavení filtru webového obsahu pro zařízení s iOSem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení Microsoft Intune, která můžete použít k řízení přístupu prohlížeče k adresám URL ze zařízení s iOSem.

Ke konfiguraci adres URL můžete použít dvě metody:

- **Konfigurovat adresy URL** – použijte integrovaný webový filtr společnosti Apple, který hledá výrazy nevhodné pro děti jako neslušná slova nebo sexuálně explicitní výrazy. Tato funkce vyhodnocuje každou webovou stránku při načítání a snaží se identifikovat a blokovat nevhodný obsah. Můžete také konfigurovat adresy URL, které filtr nekontroluje, nebo adresy URL, které jsou blokované, bez ohledu na nastavení filtru.

- **Jenom konkrétní weby** (jenom pro webový prohlížeč Safari) – tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel smí navštěvovat **jenom** tyto weby. Žádné jiné weby navštívit nejde. Tuto možnost použijte jenom v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.
Pokud nezadáte žádné adresy URL, koncoví uživatelé nebudou mít přístup k žádným webům s výjimkou webů microsoft.com, microsoft.net a apple.com.

## <a name="get-started"></a>Začínáme

1. Na stránce Funkce zařízení zvolte **Filtr webového obsahu (jenom pod dohledem)**.
2. Na stránce **Filtr webového obsahu** zvolte **Typ filtru**, který chcete nakonfigurovat:
    - **Nenakonfigurováno** – neprovádí se žádné filtrování.
    - **Konfigurovat adresy URL**
    - **Jenom konkrétní weby**
3. Potom v závislosti na použitém typu filtru zvolte jeden z následujících postupů:


## <a name="configure-urls"></a>Konfigurovat adresy URL

1. Podle potřeby na stránce **Filtr webového obsahu** vyberte jedno z následujících nastavení:
   - **Povolené adresy URL** – na stránce **Povolené adresy URL** zadejte adresy URL, které chcete povolit (pomocí obcházení webového filtru Apple), a po každé z nich použijte Enter.
     > [!NOTE]
     > Adresy URL, které tady zadáte, nechcete vystavit webovému filtru Apple. Tyto adresy URL nepředstavují seznam jediných povolených webů. Pokud požadujete toto, použijte možnost **Jenom konkrétní weby**.

   - **Blokované adresy URL** – na stránce **Blokované adresy URL** zadejte adresy URL, které chcete blokovat (bez ohledu na nastavení webového filtru Apple), a po každé z nich použijte Enter.
2. Po skončení klikněte na tlačítko **OK**.


## <a name="specific-websites-only"></a>Jenom konkrétní weby

1. V podokně **Filtr webového obsahu** nakonfigurujte pro každý web, který chcete povolit, následující nastavení:
    - **Adresa URL** – zadejte adresu URL webu, který chcete povolit, třeba `https://www.contoso.com`.
    - **Cesta k záložce** – zadejte cestu, kam chcete uložit záložku, třeba **/Contoso/Obchodní aplikace**. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
    - **Název** – zadejte popisný název záložky.
2. Po zadání údajů pro jednotlivé weby klikněte na **Přidat**.
3. Po skončení klikněte na tlačítko **OK**.

> [!IMPORTANT]
> Intune automaticky povoluje tyto adresy URL.
> - <www.microsoft.com>
> - <www.microsoft.net>
> - <www.apple.com>

## <a name="finish-up"></a>Dokončení

Zvolením **OK** se vraťte do podokna **Vytvořit profil** a pak zvolte **Vytvořit**.

## <a name="next-steps"></a>Další postup

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).
