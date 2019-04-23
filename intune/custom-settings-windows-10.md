---
title: Přidání vlastních nastavení pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte vlastní profil, abyste v Microsoft Intune mohli u zařízení s Windows 10 používat nastavení OMA-URI. K přidání vlastního nastavení použijte vlastní profil.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 44be460ee910818d52179da55151d1bceeb8b306
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61490314"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Použití vlastních nastavení pro zařízení s Windows 10 v Intune

V Microsoft Intune můžete vlastní profily použít k přidání nebo vytvoření vlastního nastavení pro zařízení s Windows 10. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily zařízení s Windows 10 používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ke konfiguraci různých funkcí. Tato nastavení obvykle používají výrobci mobilních zařízení k řízení funkcí na zařízení. 

Ve Windows 10 je k dispozici řada nastavení od poskytovatelů konfiguračních služeb (CSP), třeba [Poskytovatel konfiguračních služeb pro zásady (CSP pro zásady)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Pokud hledáte konkrétní nastavení, nezapomeňte, že řada integrovaných nastavení je v [restriktivním profilu zařízení s Windows 10](device-restrictions-windows-10.md). Takže možná nebude potřeba zadávat vlastní hodnoty.

V tomto článku najdete:

- Postup vytvoření vlastního profilu na zařízeních s Windows 10
- Seznam doporučených nastavení OMA-URI
- Příklad vlastního profilu, který otevře připojení k síti VPN

## <a name="create-the-profile"></a>Vytvoření profilu

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název profilu, jako například `windows 10 custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma**: Zvolte **Windows 10 a novější**.
    - **Typ profilu**: Zvolte **vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název**: Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis**: Zadejte popis, který bude shrnovat účel nastavení a další důležité podrobnosti.
    - **OMA-URI** (rozlišuje velikost písmen): Zadejte OMA-URI, které chcete použít jako nastavení.
    - **Datový typ**: Vyberte datový typ, který budete používat pro toto nastavení OMA-URI. Možnosti:

        - Řetězec
        - Řetězec (soubor XML)
        - Datum a čas
        - Celé číslo
        - Číslo s plovoucí desetinnou čárkou
        - Logická hodnota
        - Base64 (soubor)

    - **Hodnota**: Zadejte hodnotu dat, které chcete přidružit k uvedenému OMA-URI. Hodnota závisí na vybraném datovém typu. Pokud vyberete například **Datum a čas**, použijte k výběru hodnoty ovládací prvek pro výběr data.

    Po přidání nastavení můžete vybrat **Exportovat**. **Export** vytvoří seznam všech hodnot, které jste přidali do souboru hodnot oddělených čárkou (.csv).

5. Vyberte **OK** uložte provedené změny. Podle potřeby přidejte další nastavení.
6. Až to budete mít, zvolte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="example"></a>Příklad

V následujícím příkladu je zapnuté nastavení **Connectivity/AllowVPNOverCellular**. Toto nastavení umožňuje zařízení s Windows 10, které je připojené k mobilní síti, otevřít připojení k síti VPN.

![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Vyhledání zásad, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP) podporovaných systémem Windows 10 najdete v [referenčních informacích o poskytovatelích konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows 10. Informace o tom, jaké verze konfiguračních služeb každý poskytovatel podporuje, najdete v [referenčních informacích o poskytovatelích konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Intune navíc nepodporuje všechna nastavení, která jsou v [referenčních informacích o poskytovatelích konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference). Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si článek týkající se daného nastavení. Na každé stránce nastavení se zobrazuje podporovaná operace. Pro práci s Intune, musí podporovat nastavení **přidat**, **nahradit**, a **získat** operace. Pokud je hodnota vrácené **získat** operace neodpovídá hodnotě poskytnuté **přidat** nebo **nahradit** operace a pak Intune hlásí chybu dodržování předpisů.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).
