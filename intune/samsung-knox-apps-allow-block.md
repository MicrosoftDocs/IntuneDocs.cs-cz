---
title: Zásady Microsoft Intune k povolení/blokování aplikací pro Samsung Knox
titleSuffix: ''
description: Vytvořte vlastní profil, který zařízením se zabezpečením Samsung Knox Standard povolí nebo zablokuje aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: edff9ca3e292a2b5653a8b156a8deaa02bb79e9d
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "71303174"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Použití vlastních zásad v Microsoft Intune, které v povolí nebo blokují aplikace pro zařízení se zabezpečením Samsung Knox Standard 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Postupy v tomto článku použijte k vytvoření vlastní zásady Microsoft Intune, která obsahuje jeden z těchto seznamů:

- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace v tomto seznamu nebude možné spouštět ani v případě, že již byly nainstalované v okamžiku nasazení zásady.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Je možné instalovat jen aplikace uvedené na seznamu. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou používat jenom zařízení se spuštěnou aplikací Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Vytvoření seznamu povolených nebo blokovaných aplikací

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
2. V podokně se seznamem profilů zvolte **Vytvořit profil**.
3. V podokně **Vytvořit profil** zadejte **Název** a nepovinně **Popis** profilu zařízení.
2. Jako **Platformu** zvolte **Android** a jako **Typ profilu** zvolte **Vlastní**.
3. Klikněte na **Nastavení**.
3. V podokně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
4. V dialogovém okně **Přidat nebo upravit nastavení OMA-URI** zadejte tato nastavení:

   Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění:

   - **Název** – zadejte **PreventStartPackages**.
   - **Popis** – zadejte volitelný popis, např.: Seznam zakázaných aplikací.
   - **Datový typ** – z rozevíracího seznamu zvolte **Řetězec**.
   - **OMA-URI** – zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**.
   - **Hodnota** – zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|** . (Příklad: package1;package2;)

   Pro seznam aplikací, které si uživatelé můžou nainstalovat z obchodu Google Play, s vyloučením všech ostatních:
   - **Název** – zadejte **AllowInstallPackages**.
   - **Popis** – zadejte volitelný popis, například Seznam aplikací povolených pro instalaci z Google Play.
   - **Datový typ** – z rozevíracího seznamu zvolte **Řetězec**.
   - **OMA-URI** – zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**.
   - **Hodnota** – zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|** . (Příklad: package1;package2;)

4. Klikněte na **OK** a pak v podokně **Vytvořit profil** zvolte **Vytvořit**.

>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

Nastavení aplikace se použijí, jakmile se cílené zařízení službě přihlásí.


<!---## Assign the custom profile--->
