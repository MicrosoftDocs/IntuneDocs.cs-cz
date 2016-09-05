---
title: "Správa zařízení ve vlastnictví firmy | Microsoft Intune"
description: "Zařízení vlastněná společností (COD) mohou být spravovaná několika různými způsoby v závislosti na zařízení, způsobu jeho koupě a potřebách organizace."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: ecfeb73efed4a47256275120c52de232c556adfe
ms.openlocfilehash: 58efadf2f9fc34a31070aff93e86083583630caa


---

# Registrace zařízení vlastněných společností pomocí Microsoft Intune
Zařízení vlastněná společností nebo organizací (COD) se mohou do Intune zaregistrovat několika různými způsoby v závislosti na zařízení, způsobu jeho koupě a potřebách organizace. Zařízení vlastněná společností jde také registrovat a spravovat nainstalováním aplikace Portál společnosti jako ve scénářích BYOD (Přineste si vlastní zařízení).

## Zařízení s iOS ve vlastnictví firmy
Tato metoda registrace je vhodná pro scénáře Vyberte si vlastní zařízení (CYOD), ve kterých organizace koupí zařízení pro uživatele, ale chce si zachovat jejich správu. Pokud organizace koupila zařízení s iOS, můžete předkonfigurovat registraci, aby bylo zařízení spravované od prvního zapnutí uživatelem. Intune podporuje registraci prostřednictvím [programu Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) nebo s použitím nástroje Apple Configurator spuštěného na počítači Mac pro [přímou](ios-direct-enrollment-in-microsoft-intune.md) registraci nebo registraci pomocí [průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrace zařízení iOS vlastněných společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Správce registrace zařízení
Organizace mohou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem nazývaným účet správce registrace. Po vytvoření účtu správce registrace zařízení může být tento účet použitý manažerem k registraci více než standardních pěti zařízení povolených ve výchozím nastavení běžným uživatelům. Registrace zařízení pomocí správce registrace zařízení funguje pouze u zařízení, která nepoužívá konkrétní uživatel. Tato zařízení jsou vhodná například pro aplikace POS nebo aplikace nástrojů, ale nejsou vhodná pro uživatele, kteří potřebují přístup k e-mailu nebo firemním prostředkům.

[Registrace firemních zařízení pomocí správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Registrace firemních stolních počítačů s Windows 10

Pokud má vaše organizace Azure Active Directory Premium (AADP) nebo Enterprise Management Suite (EMS), můžete [zaregistrovat Windows 10 pro podniky](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview), takže budou automaticky označené jako „vlastněné společností“, když uživatelé přidají svůj pracovní nebo školní účet.

## Identifikace zařízení jako vlastněných společností

Zařízení vlastněná společností jsou v seznamech zařízení uvedená v oddílu **Vlastnictví** jako **Firemní**. Zařízení je možné identifikovat jako vlastněná společností následujícími způsoby:

 - [Registrovaná pomocí správce registrace zařízení (DEM)](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Registrovaná pomocí [programu DEP](ios-device-enrollment-program-in-microsoft-intune.md) společnosti Apple nebo nástroje [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - [Předem deklarovaná zařízení pomocí kódů IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Registrace Azure Active Directory/Enterprise Management Suite zařízení s Windows 10](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### Číslo IMEI (International Mobile Equipment Identity)

Čísla IMEI jsou běžnou vlastností zařízení u celé řady výrobců mobilních zařízení. Správci Intune mohou importovat čísla IMEI pro zařízení, která společnost vlastní. Když se stane zařízení spravovaným v Intune, je označené jako zařízení vlastněné společností.

[Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO4-->


