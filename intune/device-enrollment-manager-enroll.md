---
title: Registrace zařízení pomocí účtu správce registrace zařízení
titlesuffix: Microsoft Intune
description: Naučte se používat účet správce registrace zařízení k registraci zařízení v Intune. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7ff5a63b6afb619fbbe762d23208c1058e99943
ms.sourcegitcommit: b96568a77d3cb6f602e7577446996fe7dde169bd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2018
ms.locfileid: "51610137"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Registrace zařízení pomocí účtu správce registrace zařízení

Jeden účet Azure Active Directory s účtem správce registrace zařízení (DEM) můžete použít k registraci až 1000 mobilních zařízení. Správce registrace zařízení je oprávnění Intune, které můžete použít pro uživatelský účet AAD. Toto oprávnění umožňuje zaregistrovat až 1000 zařízení. Účet správce registrace zařízení je užitečný ve scénářích, kdy jsou zařízení zaregistrovaná a připravená na předání uživatelům.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Omezení zařízení zaregistrovaných pomocí účtu DEM

Pro uživatelské účty správce registrace zařízení a zařízení, která jsou zaregistrovaná pod účtem správce registrace zařízení, platí následující omezení:

  - Zařízení nemůžete vymazat z Portálu společnosti. Zařízení zaregistrované pod účtem uživatele DEM nemůžete vymazat v Intune na webu Azure Portal.
  - V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.
  - Uživatelské účty DEM nemůžou používat aplikace z programu Apple Volume Purchase Program (VPP) s uživatelskou licencí Apple VPP, protože ke správě těchto aplikací potřebujete Apple ID jednotlivých uživatelů.
  - Aplikace VPP je možné instalovat do zařízení, pokud tato zařízení mají licence Apple VPP.
  - Zařízení, které jsou zablokovaná pro podmíněný přístup s výjimkou Windows 10 1803 +


## <a name="add-a-device-enrollment-manager"></a>Přidání správce registrace zařízení

1.  V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Správci registrace zařízení**.

2.  Vyberte **Přidat**.

3.  V okně **Přidat uživatele** zadejte hlavní název uživatele (UPN) pro uživatele DEM a vyberte **Přidat**. Uživatel DEM se přidá do seznamu uživatelů DEM.

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

