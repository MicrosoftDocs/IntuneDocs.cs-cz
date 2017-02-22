---
title: "Registrace zařízení s macOS v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se registrovat zařízení s macOS v Intune Azure Preview."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrace zařízení s macOS v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jako správce Intune můžete spravovat zařízení s macOS. Ve výchozím nastavení portál Azure Portal umožňuje uživatelům registrovat jejich zařízení s macOS. Stačí jenom, abyste uživatelům dali pokyn, aby přešli na [web Portál společnosti](http://portal.manage.microsoft.com) a zaregistrovali svá zařízení s macOS. 

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- [Konfigurace domén](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority MDM](set-mdm-authority.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](/intune-azure/manage-apps/company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Nastavení registrace zařízení s macOS

Ve výchozím nastavení je služba Intune už nastavená tak, aby umožňovala registraci zařízení s macOS. 

Pokud chcete zobrazit nastavení pro povolení nebo blokování registrace zařízení s macOS, přejděte na portálu Azure Portal do okna Intune a zvolte **Registrace** > **Omezení registrace**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Pokyny k registraci pro koncové uživatele najdete v článku [Registrace zařízení s macOS do Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Použití zařízení s iOSem nebo macOS s Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


