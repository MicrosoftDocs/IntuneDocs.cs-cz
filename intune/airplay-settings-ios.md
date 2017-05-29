---
title: "Nastavení Airplay pro zařízení s iOSem v Intune"
titleSuffix: Intune Azure preview
description: "Zjistěte, jak můžete Intune využít k tomu, aby se zařízení s iOSem automaticky připojovala k zařízením kompatibilním s AirPlay."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ad2f20603261ec0eac4156facd3fd23b2982f517
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Nastavení Airplay pro zařízení s iOSem v Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Tato nastavení pomůžou připojovat zařízení s iOSem, která spravujete, k zařízením kompatibilním s AirPlay (například Apple TV) ve vaší síti.
Díky tomu můžete:

- **Nakonfigurovat seznam zařízení a hesel** – Zřiďte zařízení s názvy a hesly pro zařízení AirPlay, aby se mohla automaticky připojovat, když jsou v dosahu. Pokud zadáte heslo, pak koncoví uživatelé při připojování zadávat nemusejí.
- **Nakonfigurovat povolené cíle** – Nakonfigurujte seznam zařízení s AirPlay (podle ID zařízení). Koncoví uživatelé uvidí a budou se moct připojit jenom k zařízením, která zadáte (jenom pro zařízení pod dohledem).

## <a name="get-started"></a>Začínáme

1. V okně **Funkce zařízení** zvolte **AirPlay**.
2. V okně **AirPlay** zvolte jednu nebo obě z následujících akcí:

## <a name="configure-a-device-and-password-list"></a>Konfigurace seznamu zařízení a hesel

1. V okně **Hesla** zadejte **Název zařízení** a **Heslo** zařízení s Airplay, například **Contoso Apple TV**.
2. Po zadání údajů zařízení klikněte na **Přidat**. Zařízení se zobrazí v seznamu **Název zařízení**.
3. Přidejte další zařízení podle potřeby. Po dokončení zvolte **OK**.


## <a name="configure-allowed-destinations"></a>Konfigurace povolených cílů

1. V okně **Povolené cíle (jenom pod dohledem)* zadejte **ID zařízení** zařízení s Airplay, například 52:46:CD:51:83:4C.
2. Po zadání ID zařízení klikněte na **Přidat**. ID se zobrazí v seznamu **ID zařízení**.
3. Přidejte další zařízení podle potřeby. Po dokončení zvolte **OK**.

Zařízení a hesla nebo povolené cíle můžete také naimportovat ze souboru hodnot oddělených čárkami (csv).



