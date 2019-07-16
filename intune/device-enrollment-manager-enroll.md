---
title: Registrace zařízení pomocí účtu správce registrace zařízení
titleSuffix: Microsoft Intune
description: Naučte se používat účet správce registrace zařízení k registraci zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f2548e0ff3d4406f64d2091001c38056fe585896
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883534"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Registrace zařízení v Intune pomocí účtu správce registrace zařízení

Jeden účet Azure Active Directory s účtem správce registrace zařízení (DEM) můžete použít k registraci až 1000 mobilních zařízení. Správce registrace zařízení je oprávnění Intune, které můžete použít pro uživatelský účet AAD. Toto oprávnění umožňuje zaregistrovat až 1000 zařízení. Účet správce registrace zařízení je užitečný ve scénářích, kdy jsou zařízení zaregistrovaná a připravená na předání uživatelům.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Omezení zařízení zaregistrovaných pomocí účtu DEM

Pro uživatelské účty správce registrace zařízení a zařízení, která jsou zaregistrovaná pod účtem správce registrace zařízení, platí následující omezení:

- Uživateli účtu DEM musí být přiřazena licence Intune.
- Zařízení nemůžete vymazat z Portálu společnosti. Zařízení zaregistrované pod účtem uživatele DEM nemůžete vymazat v Intune na webu Azure Portal.
- V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.
- Uživatelské účty DEM nemůžou používat aplikace z programu Apple Volume Purchase Program (VPP) s uživatelskou licencí Apple VPP, protože ke správě těchto aplikací potřebujete Apple ID jednotlivých uživatelů.
- Aplikace VPP je možné instalovat do zařízení, pokud tato zařízení mají licence Apple VPP.
- Zařízení, které jsou zablokovaná pro podmíněný přístup s výjimkou Windows 10 1803 +
- Všechna zařízení zaregistrovaná pomocí účtů DEM musí být řádně licencovaná, aby je bylo možné spravovat přes Intune. Licence může být Uživatelská licence pro Intune nebo licence k zařízení v Intune.



## <a name="add-a-device-enrollment-manager"></a>Přidání správce registrace zařízení

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Správci registrace zařízení**.

2. Vyberte **Přidat**.

3. V okně **Přidat uživatele** zadejte hlavní název uživatele (UPN) pro uživatele DEM a vyberte **Přidat**. Uživatel DEM se přidá do seznamu uživatelů DEM.

## <a name="permissions-for-dem"></a>Oprávnění pro DEM

Role globálního správce nebo správce služby Intune pro Azure AD je potřeba:
- k přiřazení oprávnění DEM uživatelskému účtu Azure AD,
- k zobrazení všech uživatelů DEM.

Pokud uživatel nemá přiřazenou roli globálního správce ani správce služby Intune, ale má povolené oprávnění ke čtení pro přiřazenou roli Správci registrace zařízení, může zobrazit jenom uživatele DEM, které sám vytvořil.


## <a name="remove-device-enrollment-manager-permissions"></a>Odebrání oprávnění správce registrace zařízení

Odebrání správce registrace zařízení neovlivní zaregistrovaná zařízení.

**Odebrání správce registrace zařízení**

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** a potom zvolte **Správci registrace zařízení**.
2. V okně **Správci registrace zařízení** vyberte uživatele DEM a pak vyberte **Odstranit**.

