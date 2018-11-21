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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 64f8b31c4fab5b247ae466df52a0b965f1be813b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179962"
---
# <a name="erase-all-data-from-a-macos-device"></a>Vymazání všech dat ze zařízení s macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ze zařízení s macOS můžete vymazat veškerá data, včetně operačního systému. Zařízení se také odebere ze správy v Intune. Koncoví uživatelé nedostanou žádné upozornění.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) přejděte na **Zařízení** > **Všechna zařízení** a zvolte zařízení, které chcete vymazat.
![Snímek obrazovky](./media/device-erase/choosedevice.png)
2. Klikněte na **Další** > **Vymazat** a zadejte 6 číslic pro **PIN kód pro obnovení**. Je to PIN kód, který je potřeba předat uživateli, aby si mohl na zařízení znovu nainstalovat operační systém. Nezapomeňte si tento PIN kód poznamenat, protože po dokončení akce vymazání se už nezobrazí.
![Snímek obrazovky](./media/device-erase/providepin.png)
3. Kliknutím na **OK** vymažte zařízení.
