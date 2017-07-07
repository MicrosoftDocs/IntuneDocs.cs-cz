---
title: "Vlastní nastavení pro zařízení s Windows 10 v Intune"
titleSuffix: Intune on Azure
description: "Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bda9e939e2d4aba4c4d005ea55ba65bec9c6e217
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Vlastní nastavení zařízení s Windows 10 v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Vlastní** profil Microsoft Intune pro Windows 10 a Windows 10 Mobile použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Ve Windows 10 je přístupná řada nastavení CSP, například [poskytovatel konfiguračních služeb pro zásady (CSP pro zásady)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Pokud hledáte konkrétní nastavení, mějte na paměti, že [profil omezení zařízení s Windows 10](device-restrictions-windows-10.md) obsahuje řadu nastavení, která jsou integrovaná do služby Intune a nevyžadují, abyste zadali vlastní hodnoty.

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

## <a name="example"></a>Příklad
Na snímku obrazovky níže je nastavení **Connectivity/AllowVPNOverCellular** povolené. To umožňuje zařízení s Windows 10 spustit připojení VPN přes mobilní síť.

> ![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Jak najít zásady, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které systém Windows 10 podporuje, najdete v [referencích poskytovatelů konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) v knihovně dokumentace systému Windows.

Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows 10. V tabulce v tématu Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto tématu. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si téma pro dané nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.


