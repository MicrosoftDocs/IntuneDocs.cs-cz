---
title: "Správa zařízení ve vlastnictví firmy | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 69cf07aa0747448e0ef3384b5b5132e0e76aed45
ms.openlocfilehash: e07053b9b26afacc03e45f2cb104eda6088a1e05


---

# Registrace zařízení vlastněných společností pomocí Microsoft Intune
Zařízení vlastněná společností nebo organizací (COD) se mohou do Intune zaregistrovat několika různými způsoby v závislosti na zařízení, způsobu jeho koupě a potřebách organizace.

## Zařízení s iOS ve vlastnictví firmy
Tato metoda registrace je vhodná pro scénáře Vyberte si vlastní zařízení (CYOD), ve kterých organizace koupí zařízení pro uživatele, ale chce si zachovat jejich správu. Pokud organizace koupila zařízení s iOS, můžete předkonfigurovat registraci, aby bylo zařízení spravované od prvního zapnutí uživatelem. Intune podporuje registraci prostřednictvím [programu Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) nebo s použitím nástroje Apple Configurator spuštěného na počítači Mac pro [přímou](ios-direct-enrollment-in-microsoft-intune.md) registraci nebo registraci pomocí [průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrace zařízení iOS vlastněných společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Správce registrace zařízení
Organizace mohou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem nazývaným účet správce registrace. Po vytvoření účtu správce registrace zařízení může být tento účet použitý manažerem k registraci více než standardních pěti zařízení povolených ve výchozím nastavení běžným uživatelům. Registrace zařízení pomocí správce registrace zařízení funguje pouze u zařízení, která nepoužívá konkrétní uživatel. Tato zařízení jsou vhodná například pro aplikace POS nebo aplikace nástrojů, ale nejsou vhodná pro uživatele, kteří potřebují přístup k e-mailu nebo firemním prostředkům.

[Registrace firemních zařízení pomocí správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Číslo IMEI (International Mobile Equipment Identity)
Čísla IMEI jsou běžnou vlastností zařízení u celé řady výrobců mobilních zařízení. Správci Intune mohou importovat čísla IMEI pro zařízení, která společnost vlastní. Když se stane zařízení spravovaným v Intune, může být označené jako zařízení vlastněné společností a být cílem příslušné zásady.

[Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jun16_HO5-->


