---
title: "Portál helpdesku pro řešení potíží"
titleSuffix: Intune on Azure
description: "Pracovníci helpdesku používají portál pro řešení potíží, aby pomohli uživatelům s řešením technických problémů."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 08/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 32d3d014abc48eb2c3d0e10a71dc7f4616c49db8
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/12/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Použití portálu pro řešení potíží k poskytování pomoci uživatelům

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portál pro řešení potíží umožňuje operátorům helpdesku a správcům Intune zobrazit informace o uživatelích a použít je k řešení jejich žádostí o pomoc. Pokud má organizace mezi svými pracovníky i operátory helpdesku, může přiřadit roli **operátora helpdesku** skupině uživatelů, kteří potom mohou prostřednictvím okna Řešení potíží pomáhat uživatelům.

Když například uživatel kontaktuje podporu ohledně technického problému s Intune, zadá operátor helpdesku jméno uživatele. Intune zobrazuje užitečná data, která vám můžou pomoct s řešením řady problémů úrovně 1 včetně těchto:
- Stav uživatele
- Přiřazení
- Chyba při instalaci aplikace
- Problémy se shodou
- Zařízení neodpovídá
-   Zařízení nedokáže získat nastavení sítě VPN nebo Wi-Fi
-   Instalace aplikace se nezdařila

## <a name="add-help-desk-operators"></a>Přidání operátorů helpdesku
Jako správce Intune můžete přiřadit roli operátora helpdesku skupině uživatelů. Členové této skupiny můžou používat portál pro správu k řešení problémů uživatelů. Pro přístup k portálu Intune je potřeba, aby měl každý operátor helpdesku licenci Intune. Podívejte se, [jak přiřadit licence pro Intune](licenses-assign.md).

Přidání uživatelů helpdesku:
1. V případě potřeby [přidejte uživatele do Intune](users-add.md).
2. [Vytvořte skupinu helpdesku](groups-add.md) a přidejte do ní uživatele.
3. [Přiřaďte roli RBAC operátora helpdesku](role-based-access-control.md#built-in-roles).

  ![Snímky obrazovky portálu Intune se zvýrazněnými rolemi Intune a seznamem předdefinovaných rolí včetně role operátora helpdesku](./media/help-desk-user-add.png) Můžete také [vytvořit vlastní roli](role-based-access-control.md#custom-roles), kterou můžete dále upravit, abyste operátorům helpdesku poskytli potřebný přístup.  Operátoři helpdesku potřebují následující oprávnění, aby mohli řešit potíže uživatelů:
    - Mobilní aplikace: Číst
    - Spravované aplikace: Číst
    - Spravovaná zařízení: Číst
    - Organizace: Číst
    - Zásady dodržování předpisů zařízením: Číst
    - Konfigurace zařízení: Číst

4. Abyste operátorům helpdesku poskytli oprávnění k zobrazení stavu služby a otvírání lístků podpory pro Intune, [udělte uživatelům oprávnění správce](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) jako **Správce služeb**. Neudělujte oprávnění **Správce služby Intune**, protože tato role adresáře má víc práv, než operátoři helpdesku potřebují.

## <a name="access-the-troubleshooting-portal"></a>Přístup k portálu pro řešení potíží

Pracovníci helpdesku a správci Intune mají přístup k portálu pro řešení potíží dvěma způsoby:
- Otevřením adresy [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) ve webovém prohlížeči zobrazte jenom portál pro řešení potíží.
  ![Snímek obrazovky konzoly pro řešení potíží](./media/help-desk-console.png)
- Přihlaste se k portálu Azure Portal, zvolte **Další služby** > **Monitorování + správa** > **Intune** a pak přejděte na **Nápověda a podpora** > **Řešení potíží**.

Kliknutím na **Vybrat uživatele** zobrazíte uživatele a podrobnosti o něm.

## <a name="use-the-troubleshooting-portal"></a>Použití portálu pro řešení potíží

Na portálu pro řešení potíží můžete zvolit **Vybrat uživatele** a zobrazit informace o uživatelích. Informace o uživateli vám mohou pomoci porozumět aktuálnímu stavu uživatelů a jejich zařízení. Na portálu pro řešení potíží se zobrazí následující podrobnosti o řešení potíží:
- **Stav účtu**
- **Stav uživatele**
- **Zařízení** s akcemi zařízení
- **Členství ve skupině**
- **Stav ochrany aplikace**
