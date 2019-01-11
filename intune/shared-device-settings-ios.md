---
title: Přizpůsobení zamykací obrazovky na zařízeních s Iosem pomocí Microsoft Intune – Azure | Dokumentace Microsoftu
titlesuffix: ''
description: Přečtěte si o nastaveních Microsoft Intune, které lze použít k zobrazení informací na zamykací obrazovce zařízení s Iosem pomocí nastavení konfigurace sdíleného zařízení pro iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203072"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Přidání vlastních zpráv do zamknutí obrazovky a přihlašovací okno na zařízení s Iosem pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení Microsoft Intune, kterými můžete zobrazit informace na iOS zámek obrazovky a přihlašovací okno zařízení. 

Pomocí těchto nastavení můžete zobrazit vlastní zprávu nebo textu v přihlašovacím okně a na zamykací obrazovce. Například můžete zadat zprávu "Při ztrátě vrátit..." a informace z inventárního štítku.

Tato nastavení podporují zařízení pod dohledem s iOSem 9.3 a novějším.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure Portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu.
4. V **platformy**vyberte **iOS**. V **typ profilu**vyberte **funkcí na zařízeních**.
5. V **nastavení**vyberte **zpráva na zamčené obrazovce (jenom pod dohledem)**. Proveďte konfiguraci následujících nastavení:

    - **Informace z inventárního štítku**: Zadejte informace o inventárním štítku zařízení. Zadejte například `123xyz`.

        Text, který zadáte, se zobrazí v přihlašovacím okně a na zamykací obrazovce zařízení.

    - **Zamykací obrazovka Poznámka pod čarou**: Pokud ke ztrátě nebo odcizení zařízení, zadejte poznámku, která může pomoci vrátit zařízení. Můžete zadat libovolný text, který má v poli. Zadejte třeba `If found, call Contoso at ...`.

    Zařízení tokeny lze také přidat informace specifické pro zařízení s těmito poli. Chcete-li zobrazit sériové číslo, zadejte například `Serial Number: {{serialnumber}}`. Text se zobrazí na zamykací obrazovce, podobně jako `Serial Number 123456789ABC`. Při vstupu do proměnné, je potřeba použít složené závorky `{{ }}`. [Konfigurace tokenů aplikace](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) obsahuje seznam proměnných, které lze použít. Můžete také použít `deviceName` nebo libovolné jiné hodnoty konkrétní zařízení.

6. Až budete hotovi, vyberte **OK** > **OK** > **vytvořit**. Váš profil se zobrazí v seznamu.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).
