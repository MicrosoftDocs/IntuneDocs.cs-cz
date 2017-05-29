---
title: "Registrace zařízení s macOS v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se registrovat zařízení s macOS v Intune Azure Preview."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c10a28a51e9f6bed99a657cd940b00f3114e4588
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrace zařízení s macOS v Intune Azure Preview

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune umožňuje spravovat zařízení se systémem macOS. Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svá zařízení tak, že přejdou na [web Portál společnosti](http://portal.manage.microsoft.com) a budou postupovat podle pokynů. Až budou zařízení se systémem macOS pod správou, můžete [pro zařízení se systémem macOS vytvořit vlastní nastavení](custom settings-macos.md). Další možnosti budou brzy k dispozici.

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- [Konfigurace domén](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority MDM](mdm-authority-set.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Nastavení registrace zařízení s macOS

Intune již standardně umožňuje registraci zařízení se systémem macOS.

Pokud chcete u zařízení se systémem macOS registraci blokovat, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md#set-device-type-restrictions).

Jestliže chcete nastavit maximální počet zařízení, která může uživatel zaregistrovat, přečtěte si téma [Nastavení omezení limitu počtu zařízení](enrollment-restrictions-set.md#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Je potřeba koncovým uživatelům sdělit, že mají přejít na [web Portál společnosti](http://portal.manage.microsoft.com) a podle pokynů zaregistrovat svá zařízení. Můžete jim také poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Použití zařízení s iOSem nebo macOS s Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)

