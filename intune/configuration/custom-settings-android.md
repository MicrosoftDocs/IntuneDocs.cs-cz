---
title: Přidání vlastního nastavení do zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte vlastní profil pro zařízení s Androidem k vytvoření profilu Wi-Fi s předsdíleným klíčem, vytvoření profilu sítě VPN pro jednotlivé aplikace nebo povolení/blokování aplikací pro zařízení se Samsung Knox Standard v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17f0b30d0a8c706a7fdff1c7da722eeccdf097eb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "72495784"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Použití vlastních nastavení u zařízení s Androidem v Microsoft Intune

V Microsoft Intune můžete použít vlastní profil k přidání nebo vytvoření vlastního nastavení pro zařízení s Androidem. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily Androidu používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ke konfiguraci různých funkcí zařízení s Androidem. Nastavení většinou používají výrobci mobilních zařízení k ovládání těchto funkcí.

Pomocí vlastního profilu můžete nakonfigurovat a přiřadit následující nastavení Androidu. Intune má v sobě integrovaná následující nastavení:

- [Vytvoření profilu Wi-Fi s předsdíleným klíčem](/intune/wi-fi-profile-shared-key)
- [Vytvoření profilu sítě VPN pro jednotlivé aplikace](/intune/android-pulse-secure-per-app-vpn)
- [Povolení a blokování aplikací pro zařízení se Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Vlastní profil můžeme použít jenom ke konfiguraci uvedených nastavení. Zařízení s Androidem nezveřejňují úplný seznam nastavení OMA-URI, která můžete konfigurovat. Pokud chcete vidět další nastavení, pak pro ně hlasujte na [webu Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s Androidem.

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `android custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma**: Zvolte **Android**.
    - **Typ profilu:** Zvolte **Vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název:** Zadejte jedinečný název pro nastavení OMA-URI, abyste ho snadno našli.
    - **Popis:** Zadejte popis, který nastavení stručně charakterizuje, a další důležité podrobnosti.
    - **OMA-URI:** Zadejte nastavení OMA-URI, které chcete použít.
    - **Datový typ:** Zvolte datový typ, který pro toto nastavení OMA-URI použijete. Možnosti:

      - Řetězec
      - Řetězec (soubor XML)
      - Datum a čas
      - Celé číslo
      - Číslo s plovoucí desetinnou čárkou
      - Logická hodnota
      - Base64 (soubor)

    - **Hodnota:** Zadejte datovou hodnotu, kterou chcete přidružit k zadanému nastavení OMA-URI. Hodnota závisí na vybraném datovém typu. Pokud vyberete například **Datum a čas**, použijte k výběru hodnoty ovládací prvek pro výběr data.

    Po přidání nastavení můžete vybrat **Exportovat**. **Export** vytvoří seznam všech hodnot, které jste přidali do souboru hodnot oddělených čárkou (.csv).

5. Výběrem **OK** uložte změny. Podle potřeby přidejte další nastavení. 
6. Až to budete mít, zvolte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak [vytvořit profil na zařízeních s Androidem Enterprise](custom-settings-android-for-work.md).
