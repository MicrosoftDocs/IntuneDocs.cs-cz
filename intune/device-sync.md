---
title: Synchronizace zařízení pomocí Microsoft Intune – Azure | Dokumentace Microsoftu
description: Můžete synchronizovat zařízení zaregistrovaná nebo spravovaná v Microsoft Intune, abyste získali nejnovější zásady a akce. Postup zahrnuje synchronizaci pomocí portálu Azure Portal a zobrazení kódů chyb, které umožňují opakovaný pokus.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f13e00abad5b48dcd7996cf9df1cc5756f250d3
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57388112"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Synchronizace zařízení s cílem načíst nejnovější zásady a akce pomocí Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akce zařízení **Synchronizovat** vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny. Tato funkce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované vrácení se změnami.

## <a name="supported-platforms"></a>Podporované platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizace zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a pak vyberte **Microsoft Intune**. 
3. V **Intune** vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte **Synchronizovat**.
5. Potvrďte zvolením **Ano**.

Stav akce Synchronizovat zobrazíte přes **Zařízení** > **Akce zařízení**.

Standardní Intune zásady vrácení se změnami frekvencí v můžete najít [časového cyklu aktualizace](device-profiles.md).

## <a name="retryable-error-codes"></a>Kódy chyb umožňujících opakovaný pokus

Když správce spustí akci zařízení **Synchronizovat**, aplikace pro iOS a Android, které selhaly, ale vyvolaly kód chyby umožňující opakovaný pokus, budou pro zařízení stále dostupné. Aplikace, které vyvolaly kód chyby neumožňující opakovaný pokus, ale musí počkat sedm dní, než budou pro zařízení znovu dostupné.


| Kód chyby  | Navrhovaný popis | Možnost opakovaného pokusu |
|---|---|---|
| 2016330898 | Došlo k neznámé chybě. | Ne |
| 2016330897 | Časový limit vašeho připojení k Intune vypršel. Resetujte připojení. | Ano |
| 2016330896 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330895 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330894 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330893 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano|
| 2016330892 | Mezinárodní roaming je zakázaný. | Ne|
| 2016330891 | Během telefonního hovoru nejde získat přístup k mobilnímu datovému připojení pro toto zařízení. Počkejte na dokončení telefonního hovoru. | Ano|
| 2016330890 | Pro tato zařízení nešlo v tuto chvíli  použít mobilní síť. | Ne|
| 2016330889 | Nepovedlo se navázat zabezpečené připojení. Resetujte připojení. | Ano|
| 2016330888 | Nepovedlo se vyhodnotit důvěryhodnost serveru. | Ne|

## <a name="next-steps"></a>Další postup

Můžete [zkontrolovat podrobnosti](device-inventory.md) zařízení.
 
