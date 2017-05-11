---
title: "Portál helpdesku pro řešení potíží | Dokumentace Microsoftu"
titleSuffix: Intune Azure preview
description: "Pracovníci helpdesku používají portál pro řešení potíží, aby pomohli uživatelům s řešením technických problémů."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 4916b66e1f2eeabb42401645dbece28dad28eb19
ms.contentlocale: cs-cz
ms.lasthandoff: 04/26/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Pomoc uživatelům prostřednictvím portálu pro řešení potíží v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Portál pro řešení potíží umožňuje operátorům helpdesku a správcům Intune zobrazit uživatele a jejich zařízení a provádět úlohy řešení technických problémů Intune.

## <a name="add-help-desk-operators"></a>Přidání operátorů helpdesku
Jako správce Intune můžete uživatelům přiřadit oprávnění operátora helpdesku. Uživatelé helpdesku pak budou moci zobrazit portál Intune, ale nebudou moci zobrazit ani provádět jiné úlohy správy než úlohy řešení potíží.

1. Jako správce Intune se přihlaste k [portálu Azure](https:portal.azure.com), vyberte **Další služby** > **Monitorování a správa** > **Intune**.
2. V levém navigačním podokně vyberte **Role Intune**.
3. V úloze **Role Intune** vyberte **Operátor helpdesku** a potom vyberte **Přiřadit**.
4. Zadejte **Název přiřazení** (to je povinná položka), **Popis přiřazení** (tuto položku zadávat nemusíte) a potom přiřaďte **Členy (Skupiny)** a **Rozsah (Skupiny)**.
5. Členové role Operátor helpdesku nyní mohou používat portál pro řešení potíží.

Další informace o rolích Intune najdete v článku [Role Intune (RBAC)](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control).

## <a name="access-the-troubleshooting-portal"></a>Přístup k portálu pro řešení potíží

Pracovníci helpdesku a správci Intune mají přístup k portálu pro řešení potíží dvěma způsoby:
- Na [portálu Azure](https://portal.azure.com) vyberte **Další služby** > **Monitorování a správa** > **Intune** a potom v levém navigačním podokně vyberte **Řešení potíží**. V levém navigačním podokně jsou zobrazené i další úlohy, ty ale nejsou dostupné.

![Snímek obrazovky s úlohou Řešení potíží Intune a s odkazem Vybrat uživatele](media/help-desk-user.png)
- Ve webovém prohlížeči otevřete [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting). Viditelný je jenom portál Řešení potíží.

## <a name="use-the-troubleshooting-portal"></a>Použití portálu pro řešení potíží

Na portálu pro řešení potíží si pomocí možnosti **Vybrat uživatele** můžete zobrazit informace o uživateli. Informace o uživateli vám mohou pomoci porozumět aktuálnímu stavu uživatelů a jejich zařízení. Na portálu pro řešení potíží se zobrazí následující podrobnosti o uživatelích a zařízeních Intune:
- Informace o uživatelském účtu
- Členství ve skupině uživatelů
- Podrobnosti o zařízení

Uživatelé helpdesku mohou na zařízeních provádět také vzdálené úlohy, například **Vzdálené uzamčení**.

