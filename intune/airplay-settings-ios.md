---
title: "Nastavení Airplay pro zařízení s iOSem v Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak můžete Intune využít k tomu, aby se zařízení s iOSem automaticky připojovala k zařízením kompatibilním s AirPlay."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9a1472d86a0a25e35ef26be1c579ff491437676b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Nastavení Airplay pro zařízení s iOSem v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tato nastavení pomůžou připojovat zařízení s iOSem, která spravujete, k zařízením kompatibilním s AirPlay (například Apple TV) ve vaší síti.
Díky tomu můžete:

- **Nakonfigurovat seznam zařízení a hesel** – Umožněte uživatelům automatické připojení k zařízením AirPlay, která jsou v dosahu. Zřiďte jim jméno a heslo zařízení AirPlay, aby je nemuseli zadávat při připojování.
- **Nakonfigurovat povolené cíle** – Nakonfigurujte seznam zařízení s AirPlay (podle ID zařízení). Koncoví uživatelé uvidí a můžou se připojit jenom k zařízením, která zadáte (jenom pro zařízení pod dohledem).

## <a name="get-started"></a>Začínáme

1. V okně **Funkce zařízení** zvolte **AirPlay**.
2. V okně **AirPlay** zvolte jednu nebo obě z následujících akcí:

## <a name="configure-a-device-and-password-list"></a>Konfigurace seznamu zařízení a hesel

1. V okně **Hesla** zadejte **Název zařízení** a **Heslo** zařízení s AirPlay, například **Contoso Apple TV**.
2. Po zadání údajů zařízení klikněte na **Přidat**. Zařízení se zobrazí v seznamu **Název zařízení**.
3. Přidejte další zařízení podle potřeby. Po dokončení zvolte **OK**.


## <a name="configure-allowed-destinations"></a>Konfigurace povolených cílů

1. V okně **Povolené cíle (jenom pod dohledem)** zadejte **ID zařízení** zařízení s AirPlay, například 52:46:CD:51:83:4C.
2. Po zadání ID zařízení klikněte na **Přidat**. ID se zobrazí v seznamu **ID zařízení**.
3. Přidejte další zařízení podle potřeby. Po dokončení zvolte **OK**.

Zařízení a hesla nebo povolené cíle můžete také naimportovat ze souboru hodnot oddělených čárkami (csv).


## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).

