---
title: "Zásady pro povolení a blokování aplikací pro Samsung KNOX v Intune"
titlesuffix: Azure portal
description: "Vytvořte vlastní profil pro povolení a blokování aplikací pro zařízení se Samsung Knox Standardem."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7be589889cab1e04eeebdac7091c7ce573a3dcc9
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Použití vlastních zásad pro povolení a blokování aplikací pro zařízení se Samsung KNOX Standardem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Postupy v tomto tématu použijte k vytvoření vlastní zásady Microsoft Intune, která obsahuje jeden z těchto seznamů:

- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace v tomto seznamu nebude možné spouštět ani v případě, že již byly nainstalované v okamžiku nasazení zásady.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Je možné instalovat jen aplikace uvedené na seznamu. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení můžou využívat jenom zařízení se Samsung Knox Standardem.

## <a name="create-an-allowed-or-blocked-app-list"></a>Vytvoření seznamu povolených nebo blokovaných aplikací

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
2. V okně seznamu profilů zvolte **Vytvořit profil**.
3. V okně **Vytvořit profil** zadejte **Název** a nepovinně **Popis** profilu zařízení.
2. Jako **typ platformy** zvolte **Android** a jako typ profilu **Vlastní**.
3. Klikněte na **Nastavení**.
3. V okně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
4. V dialogovém okně **Přidat nebo upravit nastavení OMA-URI** zadejte následující informace:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění:

- **Název** – zadejte **PreventStartPackages**.
- **Popis** – zadejte volitelný popis, např.: Seznam zakázaných aplikací.
-   **Datový typ** – z rozevíracího seznamu zvolte **Řetězec**.
-   **OMA-URI** – zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**.
-   **Hodnota** – zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|**. (Příklad: package1;package2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Pro seznam aplikací, které si uživatelé můžou nainstalovat z obchodu Google Play, s vyloučením všech ostatních:
- **Název** – zadejte **AllowInstallPackages**.
- **Popis** – zadejte volitelný popis, například Seznam aplikací povolených pro instalaci z Google Play.
- **Datový typ** – z rozevíracího seznamu zvolte **Řetězec**.
- **OMA-URI** – zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**.
- **Hodnota** – zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|**. (Příklad: package1;package2;)

4. Klikněte na tlačítko **OK** a pak v okně **Vytvořit profil** zvolte **Vytvořit**.

>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

Nastavení aplikace se použijí, jakmile se cílené zařízení službě přihlásí.


<!---## Assign the custom profile--->
