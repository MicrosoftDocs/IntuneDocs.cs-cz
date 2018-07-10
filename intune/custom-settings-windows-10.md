---
title: Vlastní nastavení zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Nakonfiguruje pro zařízení s Windows 10 vlastní nastavení OMA-URI s použitím vlastního profilu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232822"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Vlastní nastavení OMA-URI pro zařízení s Windows 10 – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

K nasazení nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) můžete v Microsoft Intune použít **vlastní** profil pro Windows 10 a Windows 10 Mobile. Tato nastavení se použijí ke kontrole funkcí zařízení. Ve Windows 10 je k dispozici řada nastavení od poskytovatelů konfiguračních služeb (CSP), třeba [Poskytovatel konfiguračních služeb pro zásady (CSP pro zásady)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Pokud hledáte určité nastavení, pamatujte, že [profil omezení zařízení s Windows 10](device-restrictions-windows-10.md) obsahuje řadu nastavení integrovaných do Intune, která nevyžadují vlastní hodnoty.

## <a name="configure-custom-settings"></a>Konfigurace vlastního nastavení

1. K vytvoření nového konfiguračního profilu použijte typ profilu **Vlastní**. Postup je v článku o [konfiguraci vlastního nastavení zařízení](custom-settings-configure.md).
2. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat** a vytvořte nové nastavení. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
3. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace:

- **Název:** Zadejte jedinečný název nastavení OMA-URI, abyste ho v seznamu poznali.
- **Popis:** Můžete zadat popis nastavení, který není povinný.
- **OMA-URI (rozlišuje velká a malá písmena)**: Zadejte, který OMA-URI chcete nastavit.
- **Datový typ**: Vybírejte z těchto typů:
  - **Řetězec**
  - **Řetězec (XML)**
  - **Datum a čas**
  - **Celé číslo**
  - **Číslo s plovoucí desetinnou čárkou**
  - **Logická hodnota**
  - **Base64**
- **Hodnota:** Zadejte hodnotu nebo soubor, které chcete přidružit k zadanému OMA-URI.

4. Až to budete mít, vyberte **OK**. V nabídce **Vytvořit profil** vyberte **Vytvořit**. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="example"></a>Příklad
V následujícím příkladu je zapnuté nastavení **Connectivity/AllowVPNOverCellular**. Toto nastavení umožňuje zařízení s Windows 10, které je připojené k mobilní síti, otevřít připojení k síti VPN.

![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Vyhledání zásad, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP) podporovaných systémem Windows 10 najdete v [referenčních informacích o poskytovatelích konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows 10. Informace o tom, jaké verze konfiguračních služeb každý poskytovatel podporuje, najdete v [referenčních informacích o poskytovatelích konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Ani Intune nepodporuje všechna uvedená nastavení. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si článek týkající se daného nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.
