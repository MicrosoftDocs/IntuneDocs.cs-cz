---
title: Vymazání zařízení s macOS
titleSuffix: Microsoft Intune
description: Přečtěte si, jak ze zařízení s macOS vymažete všechna data, včetně operačního systému.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d99bef78d635f98f9c888d8096247f314ade6a52
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="erase-all-data-from-a-macos-device"></a>Vymazání všech dat ze zařízení s macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ze zařízení s macOS můžete vymazat veškerá data, včetně operačního systému. Zařízení se také odebere ze správy v Intune. Koncoví uživatelé nedostanou žádné upozornění.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) přejděte na **Zařízení** > **Všechna zařízení** a zvolte zařízení, které chcete vymazat.
![Snímek obrazovky](./media/device-erase/choosedevice.png)
2. Klikněte na **Další** > **Vymazat** a zadejte 6 číslic pro **PIN kód pro obnovení**. Je to PIN kód, který je potřeba předat uživateli, aby si mohl na zařízení znovu nainstalovat operační systém. Nezapomeňte si tento PIN kód poznamenat, protože po dokončení akce vymazání se už nezobrazí.
![Snímek obrazovky](./media/device-erase/providepin.png)
3. Kliknutím na **OK** vymažte zařízení.
