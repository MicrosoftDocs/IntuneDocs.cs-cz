---
title: "Vlastní nastavení Microsoft Intune pro zařízení s Windows 10"
titlesuffix: 
description: "Podívejte se na nastavení, která je možné nakonfigurovat ve vlastním profilu Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 156d37874529b4ae5a8176d7e9a8873cf440c32c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Vlastní nastavení Microsoft Intune pro zařízení s Windows 10 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Vlastní** profil Microsoft Intune pro Windows 10 a Windows 10 Mobile použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Ve Windows 10 je dostupných mnoho nastavení Poskytovatele konfiguračních služeb (CSP), například [Poskytovatel konfiguračních služeb pro zásady (CSP pro zásady)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Pokud hledáte konkrétní nastavení, mějte na paměti, že [profil omezení zařízení s Windows 10](device-restrictions-windows-10.md) obsahuje řadu nastavení, která jsou integrovaná do služby Intune a nevyžadují, abyste zadali vlastní hodnoty.

## <a name="configure-custom-settings"></a>Konfigurace vlastního nastavení

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte na stránce **Vytvořit profil** možnost **Nastavení**.
3. Na stránce **Vlastní nastavení OMA-URI** klikněte na tlačítko **Přidat**, abyste mohli přidat novou hodnotu. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
4. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace. Použijte informace v seznamu v tomto článku, kde zjistíte, jaká nastavení můžete použít:
    - **Název nastavení** – Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis nastavení** – Volitelně zadejte popis nastavení.
    - **Datový typ** – Vybírejte z těchto typů:
        - **Řetězec**
        - **Řetězec (XML)**
        - **Datum a čas**
        - **Celé číslo**
        - **Číslo s plovoucí desetinnou čárkou**
        - **Logická hodnota**
    - **OMA-URI (rozlišuje velká a malá písmena)** – Uveďte, který OMA-URI chcete nastavit.
    - **Hodnota** – Zadejte hodnotu, která má být k uvedenému OMA-URI přidružena.
5. Až to budete mít, vraťte se na stránku **Vytvořit profil** a klikněte na **Vytvořit**.
Profil se vytvoří a zobrazí se na stránce se seznamem profilů.

## <a name="example"></a>Příklad
Na snímku obrazovky níže je nastavení **Connectivity/AllowVPNOverCellular** povolené. To umožňuje zařízení s Windows 10 spustit připojení VPN přes mobilní síť.

> ![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Jak najít zásady, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které systém Windows 10 podporuje, najdete v [referencích poskytovatelů konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) v knihovně dokumentace systému Windows.

Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows 10. V tabulce v článku týkajícím se Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto článku. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si článek týkající se daného nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.


