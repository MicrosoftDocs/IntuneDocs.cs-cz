---
title: "Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější"
titleSuffix: Intune on Azure
description: "Jak naimportovat nastavení Wi-Fi z Windows do profilu Wi-Fi v Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4ef9bf6ed3f731afada55d2af71d56367f4638d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U zařízení, na kterých běží Windows 8.1. nebo Windows 10 Desktop či Mobile, můžete importovat konfigurační profil Wi-Fi, který jste předtím exportovali do souboru.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Export nastavení Wi-Fi ze zařízení s Windows

Ve Windows použijte k exportu stávajícího profilu Wi-Fi do souboru XML, který dokáže Intune přečíst, nástroj **netsh wlan**. Na počítači s Windows, který už má nainstalovaný požadovaný profil Wi-Fi, postupujte podle následujícího postupu.
1. Vytvořte místní složku pro exportované profily Wi-Fi, například **c:\WiFi**.
1. Otevřete příkazový řádek jako správce.
1. Spusťte příkaz **netsh wlan show profiles** a poznamenejte si název profilu, který chcete exportovat. V tomto příkladu je název profilu **WiFiNázev**.
1. Spusťte tento příkaz: **netsh wlan export profile name="NázevProfilu" folder=c:\Wifi**. Tím v cílové složce vytvoříte soubor profilu Wi-Fi s názvem **Wi-Fi-WiFiNázev.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>Import nastavení Wi-Fi do Intune

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně s profily zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro omezení zařízení.
5. V rozevíracím seznamu **Platforma** zvolte **Windows 8.1 a novější**.
6. V rozevíracím seznamu **Profil** zvolte **Import Wi-Fi**.
7. V okně **Základní Wi-Fi** nakonfigurujte tyto údaje:
    - **Název připojení** – zadejte název tohoto připojení Wi-Fi. Tento název se zobrazí koncovým uživatelům, když budou procházet dostupné Wi-Fi sítě.
    - **XML profilu** – klikněte na tlačítko Procházet a vyberte soubor XML obsahující nastavení profilu Wi-Fi, která chcete naimportovat do Intune.
    - **Obsah souboru** – zobrazuje kód XML vybraného konfiguračního profilu.
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
