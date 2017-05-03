---
title: "Nastavení konfigurace sdíleného zařízení v Intune pro iOS"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete zobrazit informace na zamykací obrazovce zařízení s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 2bc107054f438d5ed72de87dec85900f871c0acc
ms.lasthandoff: 04/19/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Nastavení konfigurace sdíleného zařízení pro zobrazení zpráv na zamykací obrazovce zařízení s iOSem

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Nastavení konfigurace sdíleného zařízení vám umožňuje zadat volitelný text, který bude zobrazovat v přihlašovacím okně a na zamykací obrazovce (například zpráva „Při ztrátě vrátit“ a informace z inventárního štítku majetku). 

>[!IMPORTANT]
> Tato funkce se podporuje na zařízeních pod dohledem, která používají iOS 9.3 a novější.

1. V okně **Funkce zařízení** zvolte **Konfigurace sdíleného zařízení (jenom pod dohledem)**.
2. V okně **Konfigurace sdíleného zařízení (jenom pod dohledem)** nakonfigurujte následující údaje:
    - **Informace z inventárního štítku majetku** – zadejte informace o inventárním štítku zařízení. Příklad: **Majetek společnosti Contoso Corp**. Zadané informace se použijí u všech zařízení, kterým přiřadíte tento profil.
    - **Poznámka pod čarou na zamykací obrazovce** – zadejte poznámku, která v případě ztráty nebo odcizení může pomoci vrátit zařízení do správných rukou. Příklad: **Pokud zařízení najdete, zavolejte na číslo „telefonní číslo“**.
3. Po dokončení zvolte **OK** a postupně se vraťte do okna **Vytvořit profil**. Potom zvolte **Vytvořit**. 

