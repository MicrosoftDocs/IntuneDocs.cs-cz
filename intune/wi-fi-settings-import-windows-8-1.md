---
title: "Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější"
titleSuffix: Microsoft Intune
description: "Jak naimportovat nastavení Wi-Fi z Windows do profilu Wi-Fi v Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0113703cbdc58172edc9552146c7634aa1058e3b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pro zařízení s Windows 8.1, Windows 10 Desktop, Windows 10 Mobile nebo Windows Holographic for Business můžete importovat konfigurační profil Wi-Fi, který jste si předtím vyexportovali do souboru.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Export nastavení Wi-Fi ze zařízení s Windows

Ve Windows použijte k exportu stávajícího profilu Wi-Fi do souboru XML, který dokáže Intune přečíst, nástroj **netsh wlan**. Na počítači s Windows, který už má nainstalovaný požadovaný profil Wi-Fi, postupujte podle následujícího postupu.
1. Vytvořte místní složku pro exportované profily Wi-Fi, například **c:\WiFi**.
1. Otevřete příkazový řádek jako správce.
1. Spusťte příkaz **netsh wlan show profiles** a poznamenejte si název profilu, který chcete exportovat. V tomto příkladu je název profilu **WiFiNázev**.
1. Spusťte tento příkaz: **netsh wlan export profile name="NázevProfilu" folder=c:\Wifi**. Tím v cílové složce vytvoříte soubor profilu Wi-Fi s názvem **Wi-Fi-WiFiNázev.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>Import nastavení Wi-Fi do Intune

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. Na stránce **Intune** zvolte **Konfigurace zařízení**.
2. Na stránce **Konfigurace zařízení** zvolte **Správa** > **Profily**.
3. Na stránce s profily zvolte **Vytvořit profil**.
4. Na stránce **Vytvořit profil** zadejte **Název** a **Popis** profilu pro omezení zařízení.

   > [!WARNING]
   > Název **musí** být stejný jako atribut name v souboru XML profilu Wi-Fi, jinak dojde k chybě.

5. V rozevíracím seznamu **Platforma** zvolte **Windows 8.1 a novější**.
6. V rozevíracím seznamu **Profil** zvolte **Import Wi-Fi**.
7. Na stránce se **základním nastavením Wi-Fi** nakonfigurujte následující nastavení:
    - **Název připojení** – zadejte název tohoto připojení Wi-Fi. Tento název se zobrazí koncovým uživatelům, když budou procházet dostupné Wi-Fi sítě.
    - **XML profilu** – klikněte na tlačítko Procházet a vyberte soubor XML obsahující nastavení profilu Wi-Fi, která chcete naimportovat do Intune.
    - **Obsah souboru** – zobrazuje kód XML vybraného konfiguračního profilu.
8. Až to budete mít, vraťte se na stránku **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se na stránce se seznamem profilů.
