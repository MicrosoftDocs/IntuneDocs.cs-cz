---
title: "Portál helpdesku pro řešení potíží"
titleSuffix: Intune on Azure
description: "Pracovníci helpdesku používají portál pro řešení potíží, aby pomohli uživatelům s řešením technických problémů."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Pomoc uživatelům prostřednictvím portálu pro řešení potíží v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portál pro řešení potíží umožňuje operátorům helpdesku a správcům Intune zobrazit informace o uživatelích a použít je k řešení jejich žádostí o pomoc. Pokud má organizace mezi svými pracovníky i operátory helpdesku, může přiřadit roli **operátora helpdesku** skupině uživatelů, kteří potom mohou prostřednictvím okna Řešení potíží pomáhat uživatelům.

Když například uživatel kontaktuje podporu ohledně technického problému s Intune, zadá operátor helpdesku jméno uživatele. Intune zobrazí relevantní informace, které mohou přispět k vyřešení mnoha problémů první úrovně, jako je například stav uživatele, chyba při instalaci aplikace nebo problémy s dodržováním předpisů. Lze tak vyřešit například tyto problémy:
- Zařízení neodpovídá
-   Zařízení nedokáže získat nastavení sítě VPN nebo Wi-Fi
-   Instalace aplikace se nezdařila


## <a name="add-help-desk-operators"></a>Přidání operátorů helpdesku
Jako správce Intune máte dvě možnosti, jak můžete uživatelům přiřadit oprávnění operátora helpdesku:
- Přiřadit předdefinovanou roli **operátora helpdesku**
- Vytvořit a přiřadit vlastní roli

## <a name="assign-help-desk-operator-role"></a>Přiřazení role operátora helpdesku
Jako správce Intune můžete přiřadit roli operátora helpdesku skupině uživatelů. Portál pro správu pak mohou využívat všichni členové dané skupiny. Pro přístup k portálu Intune je potřeba, aby měl každý operátor helpdesku licenci Intune. Podívejte se, [jak přiřadit licence pro Intune](licenses-assign.md).

1. Přihlaste se k portálu Intune jako správce Intune a vyberte **Role Intune**.
2. V úloze **Role Intune** vyberte **Operátor helpdesku** > **Přiřazení** a potom vyberte **Přiřadit**.
  ![Snímky obrazovky portálu Intune se zvýrazněnými rolemi Intune a seznamem předdefinovaných rolí včetně role operátora helpdesku se zvýrazněnou položkou Přiřazení a červeným rámečkem okolo položky Přiřadit](./media/help-desk-user-assign.png)
3. Zadejte **Název přiřazení** (to je povinná položka), **Popis přiřazení** (tuto položku zadávat nemusíte) a potom přiřaďte **Členy (Skupiny)** a **Rozsah (Skupiny)**.
4. Členové role Operátor helpdesku nyní mohou používat portál pro řešení potíží.

Další informace o rolích Intune najdete v článku [Role Intune (RBAC)](role-based-access-control.md).

## <a name="create-a-custom-role-for-troubleshooting"></a>Vytvoření vlastní role pro řešení potíží
Jako správce Intune můžete vytvořit vlastní roli, která uživatelům umožní využívat portál pro řešení potíží a zajistí jim oprávnění podle potřeb vaší organizace. Další informace o rolích Intune najdete v článku [Role Intune (RBAC)](role-based-access-control.md).

![Snímky obrazovky portálu Intune se zvýrazněnými rolemi Intune a seznamem předdefinovaných rolí včetně role operátora helpdesku](./media/help-desk-user-add.png)

Pokud se konzola Intune používá pro helpdeskové zobrazení, měla by mít vlastní role operátora helpdesku následující oprávnění:
- Mobilní aplikace: Číst
- Spravované aplikace: Číst
- Spravovaná zařízení: Číst
- Organizace: Číst

## <a name="access-the-troubleshooting-portal"></a>Přístup k portálu pro řešení potíží

Pracovníci helpdesku a správci Intune mají přístup k portálu pro řešení potíží dvěma způsoby:
- Ve webovém prohlížeči otevřete [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting).
- V portálu Intune přejděte na **Nápověda a podpora** > **Řešení potíží**.

![Snímek obrazovky s úlohou Řešení potíží Intune a s odkazem Vybrat uživatele](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Použití portálu pro řešení potíží

Na portálu pro řešení potíží můžete zvolit **Vybrat uživatele** a zobrazit informace o uživatelích. Informace o uživateli vám mohou pomoci porozumět aktuálnímu stavu uživatelů a jejich zařízení. Na portálu pro řešení potíží se zobrazí následující podrobnosti o řešení potíží:
- **Stav tenanta**
- **Stav uživatele**
- **Zařízení** a akce zařízení
- **Členství ve skupině**
- **Stav ochrany aplikace**
