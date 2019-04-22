---
title: Vytvoření profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidat nebo konfigurovat profil konfigurace zařízení v Microsoft Intune. Vyberte typ platformy, nakonfigurujte nastavení a přidejte značku oboru.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898849"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Vytvořte profil zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profily zařízení umožňují přidat a nakonfigurovat nastavení a potom nasdílejte tato nastavení do zařízení ve vaší organizaci. [Použít nastavení a funkcí v zařízeních pomocí profilů zařízení](device-profiles.md) obsahuje další podrobnosti, včetně toho, co můžete dělat.

V tomto článku najdete:

- Jsou uvedené kroky k vytvoření profilu.
- Ukazuje, jak přidat značku oboru pro "filtrování" profil.
- Obsahuje aktualizace vrácení se změnami cyklů, když zařízení ho obdrží profily a všechny aktualizace profilu.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.

2. Vyberte **Konfigurace zařízení**. Máte následující možnosti:

    - **Přehled**: Zobrazí stav profilů a poskytuje další podrobnosti o profilech, které jste přiřadili uživatelům a zařízením.
    - **Správa**: Vytvoření profilů zařízení tím, že nahrajete vlastní [skripty prostředí PowerShell](intune-management-extension.md) ke spuštění v rámci profilu a přidejte datové tarify do zařízení pomocí [karty eSIM](esim-device-configuration.md).
    - **Monitorování**: Zkontrolovat stav profilu úspěchu nebo selhání a také zobrazit protokoly vašich profilů.
    - **Instalační program**: Přidat certifikační autoritu SCEP nebo PFX, nebo povolit [služby Telecom Expense Management](telecom-expenses-monitor.md) v profilu.

3. Vyberte **profily** > **vytvořit profil**. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro profil. Profily pojmenujte, abyste je později mohli snadno identifikovat. Například je název profilu dobré **e-mailový profil WP pro celou firmu**.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Zvolte platformu zařízení. Možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

   - **Typ profilu**: Vyberte typ nastavení, které chcete vytvořit. V zobrazeném seznamu závisí **platformy** zvolíte.
   - **Nastavení**: Informace o nastaveních pro jednotlivé typy profilů najdete v následujících článcích:

       - [Šablony pro správu](administrative-templates-windows.md)
       - [Vlastní](custom-settings-configure.md)
       - [Optimalizace doručení](delivery-optimization-windows.md)
       - [Funkce zařízení](device-features-configure.md)
       - [Omezení zařízení](device-restrictions-configure.md)
       - [Upgrade a režim přepínač Edition](edition-upgrade-configure-windows-10.md)
       - [Vzdělávání](education-settings-configure.md)
       - [E-mailu](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Ochrana identit](identity-protection-configure.md)  
       - [Veřejný terminál](kiosk-settings.md)
       - [Certifikát PKCS](certficates-pfx-configure.md)
       - [Certifikát SCEP](certificates-scep-configure.md)
       - [Důvěryhodný certifikát](certificates-configure.md)
       - [Aktualizovat zásady](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Ochrana ATP v programu Windows Defender](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     Pokud vyberete třeba **iOS** pro platformu, možností typu profilu vypadat podobně jako následující profil:

     ![Vytvoření profilu iOS v Intune](./media/create-device-profile.png)

4. Až budete hotovi, vyberte **OK** > **vytvořit** uložte provedené změny. Profil se vytvoří a zobrazí v seznamu.

## <a name="scope-tags"></a>Značky oboru

Po přidání nastavení můžete také přidat značky oboru profilu. Značky oboru přiřazení a filtrovat zásady na konkrétní skupiny, jako je například zaměstnance personálního oddělení nebo všechny USA síťovým Adaptérem.

Další informace o značky oboru, a co můžete dělat, najdete v části [pomocí RBAC a značky oboru pro distribuované IT](scope-tags.md).

### <a name="add-a-scope-tag"></a>Přidat značku oboru

1. Vyberte **obor (značky)**.
2. Vyberte **přidat** a vytvořte novou značku oboru. Nebo vyberte existující značky oboru ze seznamu.
3. Vyberte **OK** uložte provedené změny.

## <a name="refresh-cycle-times"></a>Aktualizovat doby cyklů

Intune používá následující cyklů aktualizace kontrolu aktualizací konfigurace profilů:

| Platforma | Aktualizovat cyklu|
| --- | --- |
| iOS | Každých 6 hodin |
| macOS | Každých 6 hodin |
| Android | Každých 8 hodin |
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin |
| Windows Phone | Každých 8 hodin |
| Windows 8.1 | Každých 8 hodin |

Pokud zařízení zaregistrovalo nedávno, vrácení se změnami se spustí častěji:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| macOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows 10 zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows 8.1 | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 

Kdykoli můžete uživatelům otevřete aplikaci portál společnosti a synchronizovat zařízení okamžitě zkontroloval aktualizace profilu.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
