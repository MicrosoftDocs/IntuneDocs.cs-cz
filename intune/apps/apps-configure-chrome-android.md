---
title: Konfigurace Google Chrome pro zařízení s Androidem pomocí Intune
titleSuffix: Microsoft Intune
description: Použijte zásady konfigurace Intune s Google Chrome pro zařízení s Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f667940cc238fe243b05c7ab6f1459f63f18faa
ms.sourcegitcommit: 2c8a41ee95a3fde150667a377770e51b621ead65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/06/2019
ms.locfileid: "73635475"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Konfigurace Google Chrome pro zařízení s Androidem pomocí Intune 

Pomocí zásad konfigurace aplikací Intune můžete nakonfigurovat Google Chrome pro zařízení s Androidem. Nastavení aplikace lze automaticky použít. Můžete například konkrétně nastavit záložky a adresy URL, které chcete blokovat nebo zakázat.

## <a name="prerequisites"></a>Požadované součásti

- Zařízení s Androidem Enterprise uživatele musí být zaregistrované v Intune. Další informace najdete v tématu [Nastavení registrace zařízení s pracovním profilem v Androidu Enterprise](~/enrollment/android-work-profile-enroll.md).
- Google Chrome se přidá jako spravovaná aplikace Google Play. Další informace o spravovaných Google Play najdete v tématu [připojení účtu Intune k vašemu spravovanému Google Playmu účtu](~/enrollment/connect-intune-android-enterprise.md).

## <a name="add-the-google-chrome-app-to-intune"></a>Přidání aplikace Google Chrome do Intune

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V podokně **Intune** vyberte **klientské aplikace** > **aplikace** > **Přidat** a pak přidejte **spravovanou Google Play** aplikaci.
3. Přejít na Managed Google Play, hledejte pomocí **Google Chrome** a schvalte.

    ![Hledání a schvalování Google Chrome](~/apps/media/apps-configure-chrome-android/search.png)

4. Přiřaďte Google Chrome k skupině uživatelů jako požadovaný typ aplikace. Google Chrome se nasadí automaticky, když se zařízení zaregistruje do Intune.

Další podrobnosti o přidání spravované aplikace Google Play do Intune najdete v tématu [spravované aplikace Google Play Storu](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps).

## <a name="add-app-configuration-for-managed-ae-devices"></a>Přidat konfiguraci aplikace pro spravovaná zařízení s AE

1. V podokně [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) vyberte **zásady konfigurace aplikací** > **Přidat**.
2. Přidejte název zásady, vyberte **spravovaná zařízení** v části typ registrace zařízení a **Android** pod platformou.

    ![Přidat zásady konfigurace Google Chrome](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. Klikněte na **přidružená aplikace** a vyberte **Google Chrome**.

    ![Výběr Google Chrome v části přidružená aplikace](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Klikněte na **nastavení konfigurace**, vyberte **použít Návrhář konfigurací**a pak klikněte na **Přidat** a vyberte konfigurační klíče.

    ![Přidat návrháře konfigurace použití](~/apps/media/apps-configure-chrome-android/configuration.png)

    Níže je uveden příklad běžných nastavení:
    - **Zablokovat přístup k seznamu adres URL**: `["*"]`
    - **Povolení přístupu k seznamu adres URL**: `["baidu.com", "yahoo.com", "chrome://*"]`
    - **Spravované záložky**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Dostupnost režimu anonymním**: `Incognito mode disabled`

    Po přidání nastavení konfigurace pomocí návrháře konfigurace budou uvedená v tabulce. 

    ![Společná nastavení](~/apps/media/apps-configure-chrome-android/common-settings.png)

    Výše uvedená nastavení vytvoří záložky a povolí přístup ke všem webům kromě `baidu.com`, `yahoo.com` a `chrome://`.

5. Kliknutím na **OK** a **Přidat** přidejte zásady konfigurace do Intune.
6. Přiřaďte tyto zásady konfigurace ke skupině uživatelů. Další informace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](~/apps/apps-deploy.md). 

## <a name="verify-the-device-settings"></a>Ověření nastavení zařízení

Jakmile je zařízení s Androidem zaregistrované v Androidu Enterprise, automaticky se nasadí spravovaná aplikace Google Chrome s ikonou portfolia.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Spusťte Google Chrome a zobrazí se použitá nastavení.

   Záložky<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   Blokovaná adresa URL:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   Adresa URL pro povolení:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Karta anonymním:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Odstraňování potíží

1. Podívejte se na portál Intune, kde můžete monitorovat stav nasazení zásad.

    ![Monitorovat stav nasazení zásad](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Spusťte Google Chrome a navštivte **Chrome://Policy**. Můžeme potvrdit, jestli se nastavení úspěšně používala.

    ![Potvrzení nastavení se úspěšně zavedla.](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Další informace

- [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem Enterprise](~/app-configuration-policies-use-android.md)
- [Seznam zásad pro Chrome Enterprise](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Další kroky

- Další informace o plně spravovaných zařízeních s Androidem Enterprise najdete v tématu [Nastavení registrace v Intune pro Android Enterprise plně spravovat zařízení](~/enrollment/android-fully-managed-enroll.md).
