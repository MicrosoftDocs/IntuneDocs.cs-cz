---
title: Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější
titleSuffix: Microsoft Intune
description: Jak naimportovat nastavení Wi-Fi z Windows do profilu Wi-Fi v Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 157416738e4607d5022f1c3c7ed8251a8e32fe3e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pro zařízení s Windows 8.1, Windows 10 Desktop, Windows 10 Mobile nebo Windows Holographic for Business můžete importovat konfigurační profil Wi-Fi, který jste si předtím vyexportovali do souboru.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Export nastavení Wi-Fi ze zařízení s Windows

Ve Windows použijte k exportu stávajícího profilu Wi-Fi do souboru XML, který dokáže Intune přečíst, nástroj **netsh wlan**. Aby bylo možné profil úspěšně používat, musí se klíč vyexportovat jako prostý text.

Na počítači s Windows, který už má nainstalovaný požadovaný profil WiFi, použijte tento postup:

1. Vytvořte místní složku pro exportované profily Wi-Fi, například **c:\WiFi**.
2. Otevřete příkazový řádek jako správce.
3. Spusťte příkaz `netsh wlan show profiles` a uveďte název profilu, který chcete exportovat. V tomto příkladu je název profilu **WiFiNázev**.
4. Spusťte příkaz `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Ten vytvoří v cílové složce soubor profilu Wi-Fi s názvem **Wi-Fi-WiFiNázev.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>Import nastavení Wi-Fi do Intune

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **název** a **popis** profilu omezení zařízení.

    > [!IMPORTANT]
    > - Název **musí** být stejný jako atribut name v souboru XML profilu Wi-Fi. V opačném případě dojde k chybě.
    > - Pokud exportujete profil Wi-Fi s předsdíleným klíčem, **musíte** do příkazu přidat `key=clear`. Zadejte například `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`.
    > - Při použití předsdíleného klíče ve Windows 10 se v Intune zobrazí chyba odstranění problému. Když k ní dojde, profil Wi-Fi se správně přiřadí k zařízení a profil bude fungovat podle očekávání.
    > - Pokud exportujete profil Wi-Fi s předsdíleným klíčem, ověřte si, že je soubor chráněný. Klíč má formát prostého textu, takže jeho ochranu zajišťujete vy.

5. V části **Platforma** vyberte **Windows 8.1 a novější**.
6. V části **Typ profilu** vyberte **Import Wi-Fi**.
7. Proveďte konfiguraci následujících nastavení:
  - **Název připojení**: Zadejte název připojení Wi-Fi. Tento název se zobrazí koncovým uživatelům, když budou procházet dostupné Wi-Fi sítě.
  - **XML profilu**: Vyberte tlačítko Procházet a zvolte soubor XML obsahující nastavení profilu Wi-Fi, která chcete naimportovat do Intune.
  - **Obsah souboru**: Zobrazuje kód XML vybraného konfiguračního profilu.
8. Po dokončení vyberte **OK** a potom **Vytvořit**.

Profil se vytvoří a objeví se v seznamu profilů.
