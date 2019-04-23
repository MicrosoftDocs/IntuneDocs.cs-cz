---
title: Přidání vlastních nastavení do zařízení s Androidem Enterprise v Microsoft Intune – Azure | Microsoft Docs
description: Přidání nebo vytvoření vlastního profilu pro zařízení s Androidem Enterprise v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 494b8011b942026cf932b6f2f1851c5f0ffaadbb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61490348"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Použití vlastních nastavení u zařízení s Androidem Enterprise v Microsoft Intune

V Microsoft Intune můžete vlastní profil použít k přidání nebo vytvoření vlastních nastavení pro zařízení s Androidem Enterprise. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily pro Android Enterprise používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) k ovládání funkcí zařízení s Androidem Enterprise. Nastavení většinou používají výrobci mobilních zařízení k ovládání těchto funkcí.

Intune podporuje omezený počet vlastních profilů Androidu.

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s Androidem Enterprise. Najdete zde také příklad na vytvoření vlastního profilu, který blokuje kopírování a vložení.

## <a name="create-the-profile"></a>Vytvoření profilu

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název profilu, jako například `android enterprise custom profile`
    - **Popis**: Zadejte popis profilu
    - **Platforma**: Zvolte **Androidu Enterprise**
    - **Typ profilu**: Zvolte **vlastní**

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název**: Zadejte jedinečný název nastavení OMA-URI, takže budete moci snadno najít.
    - **Popis**: Zadejte popis, který bude shrnovat účel nastavení a další důležité podrobnosti.
    - **OMA-URI:** Zadejte OMA-URI, které chcete použít jako nastavení.
    - **Datový typ**: Vyberte datový typ, který budete používat pro toto nastavení OMA-URI. Možnosti:

      - Řetězec
      - Řetězec (soubor XML)
      - Datum a čas
      - Celé číslo
      - Číslo s plovoucí desetinnou čárkou
      - Logická hodnota
      - Base64 (soubor)

    - **Hodnota**: Zadejte hodnotu dat, které chcete přidružit k uvedenému OMA-URI. Hodnota závisí na vybraném datovém typu. Pokud vyberete například **Datum a čas**, použijte k výběru hodnoty ovládací prvek pro výběr data.

    Po přidání nastavení můžete vybrat **Exportovat**. **Export** vytvoří seznam všech hodnot, které jste přidali do souboru hodnot oddělených čárkou (.csv).

5. Vyberte **OK** uložte provedené změny. Podle potřeby přidejte další nastavení.
6. Až to budete mít, zvolte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="example"></a>Příklad

V tomto příkladu vytvoříte vlastní profil, který na zařízeních s Androidem Enterprise zakazuje kopírovat a vkládat obsah mezi pracovními a osobními aplikacemi.

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název profilu, jako například `android ent block copy paste custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma**: Zvolte **Androidu Enterprise**.
    - **Typ profilu**: Zvolte **vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název**: Zadejte něco jako `Block copy and paste`.
    - **Popis**: Zadejte něco jako `Blocks copy/paste between work and personal apps`.
    - **OMA-URI:** Zadejte `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Datový typ**: Zvolte **logická** tak hodnotu OMA-URI **True** nebo **False**.
    - **Hodnota**: Zvolte **True**.

5. Po zadání nastavení byste měli mít podobné prostředí jako na následujícím obrázku:

    ![Blokování kopírování a vkládání v pracovním profilu Androidu](./media/custom-policy-afw-copy-paste.png)

Když tento profil přiřadíte spravovaným zařízením s Androidem Enterprise, bude kopírování a vkládání mezi aplikacemi v pracovních a osobních profilech zablokované.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak [vytvořit profil na zařízeních s Androidem](custom-settings-android.md).
