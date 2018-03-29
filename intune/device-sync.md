---
title: Synchronizace zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Můžete synchronizovat zařízení zaregistrovaná nebo spravovaná v Microsoft Intune, abyste získali nejnovější zásady a akce. Postup zahrnuje synchronizaci pomocí portálu Azure Portal a zobrazení kódů chyb, které umožňují opakovaný pokus.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7af71a2d5c3ad871e69424cf6afbf7c364bb888d
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Synchronizace zařízení s cílem načíst nejnovější zásady a akce pomocí Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Synchronizovat** vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny. Tato funkce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované vrácení se změnami.

## <a name="supported-platforms"></a>Podporované platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizace zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a pak vyberte **Microsoft Intune**. 
3. V **Intune** vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte **Synchronizovat**.
5. Potvrďte zvolením **Ano**.


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

## <a name="next-steps"></a>Další kroky

- K zobrazení stavu akce Synchronizovat vyberte **Akce zařízení**. 
