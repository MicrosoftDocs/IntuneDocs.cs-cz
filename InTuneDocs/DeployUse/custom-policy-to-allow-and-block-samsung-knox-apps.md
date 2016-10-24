---
title: "Povolené a blokované aplikace pro KNOX | Microsoft Intune"
description: "Vlastní profil pro vytvoření seznamu povolených a blokovaných aplikací pro KNOX."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c7679d624ba22b2a062ef2534a642e38a5f57fde
ms.openlocfilehash: 273627573f58e1bde4fd19c548ce87639f25ca4b



---
# Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX

Postupy v tomto tématu použijte k vytvoření vlastní zásady Microsoft Intune, která obsahuje jeden z těchto seznamů:

- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace v tomto seznamu nebude možné spouštět ani v případě, že již byly nainstalované v okamžiku nasazení zásady.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Je možné instalovat jen aplikace uvedené na seznamu. Z obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.

## Vytvoření seznamu povolených nebo blokovaných aplikací

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) vyberte **Zásady** &gt; **Zásady konfigurace** &gt; **Přidat**.
2. V dialogovém okně **Vytvořit novou zásadu** rozbalte **Android**, zvolte **Vlastní konfigurace** a potom **Vytvořit zásadu**.
3. Zadejte název a nepovinný popis zásady, pak v části **Nastavení OMA-URI** zvolte **Přidat**.
4. V dialogovém okně **Přidat nebo upravit nastavení OMA-URI** zadejte následující informace: Pro seznam aplikací, jejichž spouštění není v zařízení povoleno:
    
    - **Název nastavení.** Zadejte **PreventStartPackages**.
    - **Popis nastavení.** Zadejte volitelný popis, např.: Seznam zakázaných aplikací.
    -   **Datový typ.** Z rozevíracího seznamu vyberte položku **String** (Řetězec).
    -   **OMA-URI.** Zadejte **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -   **Hodnota.** Zadejte seznam názvů balíčků aplikací, které chcete povolit. Jako oddělovač můžete použít **; : ,** nebo **|**. (Příklad: package1;package2;)

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


## Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a pak klikněte na **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** vyberte jednu nebo víc skupin, do kterých chcete zásadu nasadit, a potom zvolte **Přidat** &gt; **OK**.

 
Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

### Související témata
[Nastavení zásad konfigurace pro Android a Samsung KNOX v Microsoft Intune](android-policy-settings-in-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


