---
title: "Povolené a blokované aplikace pro KNOX"
description: "Vlastní profil pro vytvoření seznamu povolených a blokovaných aplikací pro KNOX."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ee5279c91eeaa2d75044a156ebe9c4b100bd8047
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se Samsung Knox Standardem

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Postupy v tomto tématu použijte k vytvoření vlastní zásady Microsoft Intune, která obsahuje jeden z těchto seznamů:

- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace v tomto seznamu nebude možné spouštět ani v případě, že již byly nainstalované v okamžiku nasazení zásady.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Je možné instalovat jen aplikace uvedené na seznamu. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení můžou využívat jenom zařízení se Samsung Knox Standardem.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>Vytvoření seznamu povolených nebo blokovaných aplikací

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) vyberte **Zásady** &gt; **Zásady konfigurace** &gt; **Přidat**.
2. V dialogovém okně **Vytvořit novou zásadu** rozbalte **Android**, zvolte **Vlastní konfigurace** a potom **Vytvořit zásadu**.
3. Zadejte název a nepovinný popis zásady, pak v části **Nastavení OMA-URI** zvolte **Přidat**.
4. V dialogovém okně **Přidat nebo upravit nastavení OMA-URI** zadejte následující informace: Pro seznam aplikací, jejichž spouštění není v zařízení povoleno:
    
    - **Název nastavení.** Zadejte **PreventStartPackages**.
    - **Popis nastavení.** Zadejte volitelný popis, např.: Seznam zakázaných aplikací.
    -   **Datový typ.** Z rozevíracího seznamu vyberte položku **String** (Řetězec).
    -   **OMA-URI.** Zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -   **Hodnota.** Zadejte seznam názvů balíčků aplikací, které chcete zakázat. Jako oddělovač můžete použít **; : ,** nebo **|**. (Příklad: package1;package2;)

    Pro seznam aplikací, které si uživatelé můžou nainstalovat z obchodu Google Play, s vyloučením všech ostatních:

    - **Název nastavení.** Zadejte **AllowInstallPackages**.
    - **Popis nastavení.** Zadejte volitelný popis, např.: Seznam aplikací povolených pro instalaci z Google Play.
    - **Datový typ.** Z rozevíracího seznamu vyberte položku **String** (Řetězec).
    - **OMA-URI.** Zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Hodnota.** Zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|**. (Příklad: package1;package2;)

4. Zvolte **OK** a potom **Uložit změny**. 

>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

Nastavení aplikace se použijí, jakmile se cílené zařízení službě přihlásí.


## <a name="deploy-the-policy"></a>Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a pak klikněte na **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** vyberte jednu nebo víc skupin, do kterých chcete zásadu nasadit, a potom zvolte **Přidat** &gt; **OK**.

 
Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

### <a name="see-also"></a>Viz taky
[Nastavení zásad konfigurace pro Android a Samsung KNOX v Microsoft Intune](android-policy-settings-in-microsoft-intune.md)
