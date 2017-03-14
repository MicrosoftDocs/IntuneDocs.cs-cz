---
title: "Registrace zařízení – správce registrace zařízení"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se používat účet správce registrace zařízení k registraci zařízení v Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b4629d98f935ab2fac95144940e2a58a1b1e7c5c
ms.lasthandoff: 02/18/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Registrace zařízení pomocí správce registrace zařízení

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *správce registrace zařízení* (DEM – Device Enrollment Manager) je speciální uživatelský účet, který může zaregistrovat až 1 000 zařízení. Do účtu DEM můžete přidat existující uživatele a udělit jim tak speciální možnosti DEM. Každé zaregistrované zařízení používá jednu licenci. Zařízení zaregistrovaná pomocí účtu správce registrace zařízení doporučujeme používat jako sdílená zařízení, nikoli jako osobní zařízení („BYOD“).  

Abyste mohli uživatele přidat jako správce registrace zařízení, musí tito uživatelé existovat na portálu Azure Portal. Z důvodu optimálního zabezpečení by uživatel DEM neměl být současně i správcem Intune.

>[!NOTE]
>Metodu registrace pomocí správce registrace zařízení (DEM) nejde použít s těmito dalšími metodami registrace: [Apple Configurator s Pomocníkem s nastavením](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md), [Apple Configurator s přímou registrací](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) nebo [Program registrace zařízení (DEP)](enroll-ios-devices-using-device-enrollment-program.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Příklad scénáře využití správce registrace zařízení

Restaurace chce pro své číšníky pořídit padesát tabletů POS a monitory na objednávky pro pracovníky kuchyně. Zaměstnanci nikdy nepotřebují přístup k datům společnosti a nepotřebují se přihlašovat jako uživatelé. Správce Intune vytvoří účet správce registrace zařízení a přidá vedoucího restaurace k účtu DEM, čímž mu v podstatě dá nadřízené možnosti DEM. Nadřízený nyní může zaregistrovat padesát zařízení pomocí přihlašovacích údajů DEM.

Správci registrace zařízení můžou být jenom uživatelé v konzole Intune. Správce registrace zařízení nemůže být správcem služby Intune.

Uživatel DEM může:

-   Zaregistrovat v Intune až 1 000 zařízení.
-   Přihlásit se k webu Portál společnosti a získat firemní aplikace.
-   Konfigurovat přístup k datům společnosti tak, že na tablety nasadí aplikace specifické pro jednotlivé role.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Omezení zařízení zaregistrovaných pomocí účtu DEM

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení mají následující omezení:

  - Neexistuje žádný konkrétní uživatel zařízení. Z tohoto důvodu neexistuje ani žádný přístup k e-mailům nebo datům společnosti. Sítě VPN však mohou aplikacím zařízení stále poskytovat přístup k datům.

  - Není možný podmíněný přístup, protože u podmíněného přístupu se jedná o scénáře pro konkrétní uživatele.

  - Uživatel DEM nemůže přes Portál společnosti zrušit registraci zařízení zaregistrovaného pomocí účtu DEM. Tuto možnost má správce Intune, ale uživatel DEM nikoli.

  - V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.
 
  - Uživatelé nemůžou používat aplikace v rámci programu Apple VPP (Volume Purchase Program), protože ke správě těchto aplikací jsou vyžadovaná Apple ID jednotlivých uživatelů.
 
  - (Pouze iOS) Pokud pomocí DEM zaregistrujete zařízení s iOSem, nemůžete k registraci zařízení využít Apple Configurator ani Program registrace zařízení Apple (DEP).


> [!NOTE]
> Pokud chcete nasadit aplikace společnosti na zařízení spravovaná správcem registrace zařízení, nasaďte aplikaci Portál společnosti jako **požadovanou instalaci** na uživatelský účet správce registrace zařízení.
> Kvůli zvýšení výkonu se při zobrazení aplikace Portál společnosti v zařízení správce registrace zařízení zobrazuje pouze místní zařízení. Vzdálenou správu jiných zařízení správce registrace zařízení lze provádět jenom v konzole pro správu Intune.


## <a name="add-a-device-enrollment-manager"></a>Přidání správce registrace zařízení

1.  Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2.  V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Správci registrace zařízení**.

3.  Vyberte **Přidat**.

4.  V okně **Přidat uživatele** zadejte hlavní název uživatele (UPN) pro uživatele DEM a vyberte **Přidat**. Uživatel DEM se přidá do seznamu uživatelů DEM.

## <a name="remove-a-device-enrollment-manager"></a>Odebrání správce registrace zařízení

Odebrání správce registrace zařízení nemá vliv na zaregistrovaná zařízení. Po odebrání správce registrace zařízení nastane tento stav:

-   Odebrání uživatele ze seznamu uživatelů DEM nemá vliv na zaregistrovaná zařízení, která jsou dál plně spravovaná.

-   Přihlašovací údaje k odebranému účtu správce registrace zařízení zůstávají platné.

-   Odebraný správce registrace zařízení dál nemůže mazat nebo vyřazovat zařízení.

-   Odebraný správce registrace zařízení nemůže registrovat další zařízení, pokud nebyl dosažen limit pro jednotlivá zařízení, který nakonfiguroval správce Intune.

**Odebrání správce registrace zařízení**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Správci registrace zařízení**.

3. V okně **Správci registrace zařízení** klikněte pravým tlačítkem na uživatele DEM a vyberte **Odebrat**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Zobrazení vlastností správce registrace zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Správci registrace zařízení**.

3. V okně **Správci registrace zařízení** klikněte pravým tlačítkem na uživatele DEM a vyberte **Vlastnosti**.

