---
title: "Vlastní nastavení Intune pro zařízení s Windows Holographic for Business"
titlesuffix: Azure portal
description: "Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Vlastní nastavení zařízení s Windows Holographic for Business v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Vlastní** profil Microsoft Intune pro Windows Holographic for Business použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Windows Holographic for Business zpřístupňuje řadu nastavení poskytovatelů konfiguračních služeb (CSP). Základní informace o CSP najdete v [úvodu o poskytovatelích konfiguračních služeb (CSP) pro IT specialisty](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Konkrétní poskytovatele CSP, které podporuje Windows Holographic, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Pokud hledáte konkrétní nastavení, mějte na paměti, že [profil omezení zařízení s Windows Holographic for Business](device-restrictions-windows-holographic.md) obsahuje řadu integrovaných nastavení, která nevyžadují, abyste zadali vlastní hodnoty.

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte v okně **Vytvořit profil** možnost **Nastavení**.
3. V okně **Vlastní nastavení OMA-URI** klikněte na tlačítko **Přidat**, abyste mohli přidat novou hodnotu. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
4. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace. Použijte informace v seznamu v tomto tématu, kde zjistíte, jaká nastavení můžete použít:
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
5. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.
Profil se vytvoří a zobrazí se v okně se seznamem profilů.

## <a name="supported-custom-settings"></a>Podporovaná vlastní nastavení

Windows Holographic for Business podporuje tato vlastní nastavení:


|Název nastavení|OMA-URI|Datový typ  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Celé číslo (0 – není povoleno, 1 – povoleno)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Celé číslo (0 – není povoleno, 1 – povoleno)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Jak najít zásady, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které Windows Holographic podporuje, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows Holographic. V tabulce v tématu Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto tématu. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si téma pro dané nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.


