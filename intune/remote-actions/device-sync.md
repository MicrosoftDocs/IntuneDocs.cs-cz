---
title: Synchronizace zařízení s Microsoft Intune – Azure | Microsoft Docs
description: Můžete synchronizovat zařízení zaregistrovaná nebo spravovaná v Microsoft Intune, abyste získali nejnovější zásady a akce. Postup zahrnuje synchronizaci pomocí portálu Azure Portal a zobrazení kódů chyb, které umožňují opakovaný pokus.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 21167b226556100e7e9920f31f859d6d6ce2a7bb
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415533"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Synchronizace zařízení s cílem načíst nejnovější zásady a akce pomocí Intune


Akce zařízení **Synchronizovat** vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny. Tato funkce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované vrácení se změnami.

## <a name="supported-platforms"></a>Podporované platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizace zařízení

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). 
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, vyberte zařízení a otevřete jeho podokno *přehledu* a pak vyberte **synchronizovat**.
5. Potvrďte zvolením **Ano**.

Stav akce Synchronizovat zobrazíte přes **Zařízení** > **Akce zařízení**.

Standardní frekvence vrácení se změnami zásad služby Intune najdete v [časech obnovy cyklů](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retryable-error-codes"></a>Kódy chyb umožňujících opakovaný pokus

Když správce spustí akci zařízení **synchronizovat** , aplikace pro iOS/IPadOS a Android, které selhaly a zvýšily kód chyby umožňující Opakovaný pokus, jsou pořád k dispozici pro zařízení. Aplikace, které vyvolaly kód chyby neumožňující opakovaný pokus, ale musí počkat sedm dní, než budou pro zařízení znovu dostupné.


| Kód chyby  | Navrhovaný popis | Možnost opakovaného pokusu |
|---|---|---|
| 2016330898 | Došlo k neznámé chybě. | Ne |
| 2016330897 | Vypršel časový limit vašeho připojení k Intune. Obnovte připojení. | Ano |
| 2016330896 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330895 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330894 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano |
| 2016330893 | Ztratili jste připojení k internetu. Resetujte připojení. | Ano|
| 2016330892 | Mezinárodní roaming je zakázaný. | Ne|
| 2016330891 | K mobilnímu datovému připojení pro toto zařízení nelze připomenout během telefonního hovoru. Počkejte na dokončení telefonního hovoru. | Ano|
| 2016330890 | Pro tato zařízení nešlo v tuto chvíli V tuto chvíli se tato zařízení nedala použít. | Ne|
| 2016330889 | Nepovedlo se navázat zabezpečené připojení. Resetujte připojení. | Ano|
| 2016330888 | Nepovedlo se vyhodnotit důvěryhodnost serveru. | Ne|

## <a name="next-steps"></a>Další kroky

Můžete [zkontrolovat podrobnosti](device-inventory.md) zařízení.
 
