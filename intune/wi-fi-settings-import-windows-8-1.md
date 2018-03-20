---
title: "Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější"
titleSuffix: Microsoft Intune
description: "Jak naimportovat nastavení Wi-Fi z Windows do profilu Wi-Fi v Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 890a10ecf4212656c189adaf46bb2839898758c1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
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

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
4. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
5. V podokně s profily klikněte na **Vytvořit profil**.
6. V podokně **Vytvořit profil** zadejte **název** a **popis** profilu pro omezení zařízení.


   > [!WARNING]
   > Název **musí** být stejný jako atribut name v souboru XML profilu Wi-Fi, jinak dojde k chybě.

7. V rozevíracím seznamu **Platforma** zvolte **Windows 8.1 a novější**.
8. V rozevíracím seznamu **Profil** zvolte **Import Wi-Fi**.
9. V podokně **Wi-Fi** nakonfigurujte následující nastavení:
    - **Název připojení** – zadejte název tohoto připojení Wi-Fi. Tento název se zobrazí koncovým uživatelům, když budou procházet dostupné Wi-Fi sítě.
    - **XML profilu** – klikněte na tlačítko Procházet a vyberte soubor XML obsahující nastavení profilu Wi-Fi, která chcete naimportovat do Intune.
    - **Obsah souboru** – zobrazuje kód XML vybraného konfiguračního profilu.
10. Až to budete mít, zvolte **OK**, vraťte se zpět do podokna **Vytvořit profil** a vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.
