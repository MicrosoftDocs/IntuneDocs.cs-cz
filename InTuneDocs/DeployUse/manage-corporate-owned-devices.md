---
title: "Správa zařízení ve vlastnictví firmy | Microsoft Intune"
description: "Registrace zařízení patřících společnosti může probíhat různě. Záleží vždy na typu zařízení, způsobu nákupu a potřebách organizace."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 7577cbab528d88635e8551bf8de1ffd49becaa84


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Registrace zařízení vlastněných společností pomocí Intune

Zařízení vlastněná organizací nebo společností můžete do Intune zaregistrovat kvůli správě různým způsobem. Záleží na typu zařízení, způsobu jeho nákupu a potřebách organizace. Můžete také nainstalovat aplikaci Portál společnosti a používat ji k registraci a správě zařízení patřících společnosti, například ve scénářích BYOD (Přineste si vlastní zařízení).

## <a name="enroll-corporate-owned-ios-devices"></a>Registrace zařízení s iOS vlastněných společností

Pro scénáře CYOD (Vyberte si vlastní zařízení) jsou vhodné způsoby registrace zařízení vlastněných společností. V prostředí CYOD organizace zaplatí zařízení, které si uživatel vybere, a organizace ho spravuje.

Pokud uživatelům nabídnete zařízení s iOSem, ze kterých si mohou vybrat, můžete předem nakonfigurovat jejich registraci, aby bylo zařízení spravované v Intune od okamžiku, kdy ho uživatel zapne. Intune podporuje registraci prostřednictvím [programu Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) nebo s použitím nástroje Apple Configurator spuštěného na počítači Mac pro [přímou](ios-direct-enrollment-in-microsoft-intune.md) registraci nebo registraci pomocí [průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Přečtěte si, jak [zaregistrovat zařízení s iOSem patřící společnosti](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Vytvoření účtu správce registrace zařízení

V Intune stačí vytvořit jeden účet správce registrace zařízení (DEM), který můžete použít ke správě velkého počtu mobilních zařízení v organizaci. Po vytvoření účtu DEM může jeho pověřený správce registrovat více než 15 zařízení, což je povolený počet u standardního uživatele.

Účet DEM můžete použít ke správě jenom těch zařízení, která nepoužívá jeden konkrétní uživatel. Tyto typy zařízení se hodí například pro aplikace POS a jednoúčelové aplikace, ale nehodí se pro uživatele, kteří potřebují přístup k e-mailu nebo k prostředkům společnosti.

Přečtěte si, jak [použít účet DEM k registraci zařízení patřících společnosti](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Registrace zařízení s Windows 10 Enterprise patřících společnosti

Pokud ve společnosti používáte Azure Active Directory Premium nebo Microsoft Enterprise Mobility Suite, můžete [registrovat zařízení s Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Když uživatel přidá do zařízení pracovní nebo školní účet, bude zařízení automaticky označené jako „vlastněné společností“.

## <a name="import-imei-numbers"></a>Import čísel IMEI

Řada výrobců mobilních zařízení uvádí na svých výrobcích jedinečné číslo, které se nazývá IMEI (International Mobile Equipment Identity). U zařízení, která organizace vlastní, můžete čísla IMEI importovat. Zařízení, které spravujete v Intune, bude označené jako zařízení patřící společnosti.

Přečtěte si, jak [používat čísla IMEI k označení zařízení vlastněných společností](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Identifikace zařízení vlastněných společností

V seznamu zařízení má **Vlastnictví** hodnotu **Firemní**. Zařízení vlastněné společností má jednu z těchto vlastností:

 - K registraci zařízení byl [použit účet DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - K registraci zařízení byl [použit program Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) nebo [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md).
 - Výrobce zařízení používá k [označení čísla IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).
 - Zařízení je zaregistrované v [Azure Active Directory nebo v Enterprise Mobility Suite jako zařízení s Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).



<!--HONumber=Nov16_HO2-->


