---
title: Import nastavení Wi-Fi pro zařízení s Windows v Microsoft Intune – Azure | Microsoft Docs
description: Exportujte nastavení Wi-Fi ze zařízení s Windows jako soubor XML pomocí nástroje netsh wlan. Potom importem tohoto souboru do Intune vytvořte profil Wi-Fi pro zařízení s Windows 8.1, Windows 10 a Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 578ff40d4d66553d3c18d808329b36cb1691e8b8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395347"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Import nastavení Wi-Fi pro zařízení s Windows v Intune

Pro zařízení s Windows můžete importovat konfigurační profil Wi-Fi, který jste předtím exportovali do souboru. **Pro zařízení, na kterých běží Windows 10 a vyšší, můžete také [vytvořit profil Wi-Fi](wi-fi-settings-windows.md) přímo v Intune**.

Platí pro:  
- Windows 8.1 a vyšší
- Windows 10 a novější
- Windows 10 Desktop nebo Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Export nastavení Wi-Fi ze zařízení s Windows

Ve Windows použijte k exportu stávajícího profilu Wi-Fi do souboru XML, který dokáže Intune přečíst, nástroj `netsh wlan`. Aby bylo možné profil úspěšně používat, musí se klíč vyexportovat jako prostý text.

Na počítači s Windows, který už má nainstalovaný požadovaný profil WiFi, použijte tento postup:

1. Vytvořte místní složku pro exportované profily Wi-Fi, například **c:\WiFi**.
2. Otevřete příkazový řádek jako správce.
3. Spusťte příkaz `netsh wlan show profiles` a uveďte název profilu, který chcete exportovat. V tomto příkladu je název profilu **WiFiNázev**.
4. Spustit `netsh wlan export profile name="ProfileName" folder=c:\Wifi` příkazu. Tento příkaz vytvoří v cílové složce soubor profilu Wi-Fi s názvem **Wi-Fi-WiFiNázev.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>Import nastavení Wi-Fi do Intune

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu omezení zařízení.

    > [!IMPORTANT]
    > - Název **musí** být stejný jako atribut name v souboru XML profilu Wi-Fi. V opačném případě dojde k chybě.
    > - Pokud exportujete profil Wi-Fi s předsdíleným klíčem, **musíte** do příkazu přidat `key=clear`. Zadejte například `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`.
    > - Při použití předsdíleného klíče ve Windows 10 se v Intune zobrazí chyba odstranění problému. Když k ní dojde, profil Wi-Fi se správně přiřadí k zařízení a profil bude fungovat podle očekávání.
    > - Pokud exportujete profil Wi-Fi s předsdíleným klíčem, ověřte si, že je soubor chráněný. Klíč má formát prostého textu, takže jeho ochranu zajišťujete vy.

4. V části **Platforma** vyberte **Windows 8.1 a novější**.
5. V části **Typ profilu** vyberte **Import Wi-Fi**.
6. Proveďte konfiguraci následujících nastavení:
    - **Název připojení**: Zadejte název připojení Wi-Fi. Tento název se zobrazí koncovým uživatelům, když budou procházet dostupné Wi-Fi sítě.
    - **XML profilu**: Vyberte tlačítko Procházet a vyberte soubor XML obsahující nastavení profilu sítě Wi-Fi, který chcete importovat.
    - **Obsah souboru**: Zobrazuje kód XML pro konfigurační profil, který jste vybrali.
7. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

[Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších dostupných platforem
