---
title: Přidání vlastních nastavení do zařízení s Androidem Enterprise v Microsoft Intune – Azure | Microsoft Docs
description: Přidání nebo vytvoření vlastního profilu pro zařízení s Androidem Enterprise v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd2ab7ad8eb155719695bede1f539d5c264d455b
ms.sourcegitcommit: eb2e420b304c7da9d3be5ef49a676cba66766d2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74319831"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Použití vlastních nastavení u zařízení s Androidem Enterprise v Microsoft Intune

Pomocí Microsoft Intune můžete přidat nebo vytvořit vlastní nastavení pro zařízení se systémem Android Enterprise Work Profile pomocí vlastního profilu. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily pro Android Enterprise používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) k ovládání funkcí zařízení s Androidem Enterprise. Nastavení většinou používají výrobci mobilních zařízení k ovládání těchto funkcí.

Intune podporuje následující omezený počet vlastních profilů pro Android Enterprise:

- ./Vendor/MSFT/WiFi/Profile/SSID/Settings: [Vytvoření profilu Wi-Fi s předsdíleným klíčem](wi-fi-profile-shared-key.md) obsahuje několik příkladů.
- ./Vendor/MSFT/VPN/Profile/Name/PackageList: [Vytvoření profilu sítě VPN pro jednotlivé aplikace](android-pulse-secure-per-app-vpn.md) obsahuje několik příkladů.
- ./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste: viz [příklad](#example) v tomto článku. Toto nastavení je také k dispozici v uživatelském rozhraní. Další informace najdete v tématu [nastavení zařízení s Androidem Enterprise pro povolení nebo omezení funkcí](device-restrictions-android-for-work.md).

Pokud potřebujete další nastavení, přečtěte si téma [OEMConfig for Android Enterprise](android-oem-configuration-overview.md).

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s Androidem Enterprise. Najdete zde také příklad na vytvoření vlastního profilu, který blokuje kopírování a vložení.

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `android enterprise custom profile`.
    - **Popis:** Zadejte popis profilu.
    - **Platforma:** Zvolte **Android Enterprise**.
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

## <a name="example"></a>Příklad

V tomto příkladu vytvoříte vlastní profil, který na zařízeních s Androidem Enterprise zakazuje kopírovat a vkládat obsah mezi pracovními a osobními aplikacemi.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `android ent block copy paste custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma:** Zvolte **Android Enterprise**.
    - **Typ profilu:** Zvolte **Vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název:** Zadejte třeba `Block copy and paste`.
    - **Popis:** Zadejte třeba `Blocks copy/paste between work and personal apps`.
    - **OMA-URI:** Zadejte `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Datový typ**: Zvolte **Logická hodnota**, takže hodnota tohoto nastavení OMA-URI bude **Pravda** nebo **Nepravda**.
    - **Hodnota**: Zvolte **Pravda**.

5. Po zadání nastavení byste měli mít podobné prostředí jako na následujícím obrázku:

    ![Blokování kopírování a vkládání v pracovním profilu Androidu](./media/custom-settings-android-for-work/custom-policy-afw-copy-paste.png)

Když tento profil přiřadíte spravovaným zařízením s Androidem Enterprise, bude kopírování a vkládání mezi aplikacemi v pracovních a osobních profilech zablokované.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak [vytvořit profil na zařízeních s Androidem](../custom-settings-android.md).
