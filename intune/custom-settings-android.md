---
title: Přidání vlastních nastavení pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte vlastní profil pro zařízení s Androidem k vytvoření profilu Wi-Fi s předsdíleným klíčem, vytvoření profilu sítě VPN pro jednotlivé aplikace nebo povolení/blokování aplikací pro zařízení se Samsung Knox Standard v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0195e138b59fae019fa2bc02aadf211257a65cac
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022046"
---
# <a name="custom-settings-for-android-devices---intune"></a>Vlastní nastavení pro zařízení s Androidem – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vlastní profily používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ke konfiguraci různých funkcí na zařízeních s Androidem. Tato nastavení obvykle používají výrobci mobilních zařízení k řízení funkcí na zařízení.

Pomocí vlastního profilu můžete nakonfigurovat a přiřadit následující nastavení Androidu. Tato nastavení nejsou součástí zásad Intune:

- [Vytvoření profilu Wi-Fi s předsdíleným klíčem](/intune/wi-fi-profile-shared-key)
- [Vytvoření profilu sítě VPN pro jednotlivé aplikace](/intune/android-pulse-secure-per-app-vpn)
- [Povolení a blokování aplikací pro zařízení se Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Tímto typem profilu se v současnosti dají konfigurovat jenom uvedená nastavení. Zařízení s Androidem nezveřejňují úplný seznam nastavení OMA-URI, která můžete konfigurovat. Pokud chcete vidět další nastavení, pak pro ně hlasujte na [webu Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Nastavení vlastního profilu pro zařízení s Androidem

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com). 
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vytvořte vlastní profil pomocí platformy Android. Postup je popsaný v [Konfiguraci vlastního nastavení v Microsoft Intune](custom-settings-configure.md).
4. Ve **Vlastním nastavení OMA-URI** vyberte **Přidat** a pak vyberte **Přidat řádek**.
5. Zadejte tyto vlastnosti:

   - **Název** – zadejte jedinečný název pro nastavení OMA-URI, abyste ho snadno našli.
   - **Popis** – zadejte popis, který nastavení stručně charakterizuje, a další důležité podrobnosti.
   - **Datový typ** –zadejte datový typ, který pro toto nastavení OMA-URI používáte. Vyberte z možností **Řetězec**, **Řetězec (XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka** nebo **Logická hodnota**.
   - **OMA-URI** –zadejte OMA-URI, který chcete.
   - **Hodnota** – zadejte hodnotu, kterou chcete přidružit k uvedenému OMA-URI.

6. Výběrem **OK** uložte změny. Podle potřeby přidejte další nastavení.

## <a name="next-steps"></a>Další kroky

Po dokončení nastavení se vytvoří profil, který se zobrazí v seznamu. Pokud chcete tento profil přiřadit ke skupinám, přečtěte si článek [Přiřazení profilů zařízení](device-profile-assign.md).
