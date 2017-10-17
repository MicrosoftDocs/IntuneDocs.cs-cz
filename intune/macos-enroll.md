---
title: "Registrace zařízení s macOS v Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak zaregistrovat zařízení s macOS v Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3afe710918ff8433b04861de2ad183e699c83023
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="enroll-macos-devices-in-intune"></a>Registrace zařízení s macOS v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení se systémem macOS. Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svá zařízení tak, že přejdou na [web Portál společnosti](http://portal.manage.microsoft.com) a budou postupovat podle pokynů. Až budou zařízení se systémem macOS pod správou, můžete [pro zařízení se systémem macOS vytvořit vlastní nastavení](custom-settings-macos.md). Další možnosti budou brzy k dispozici.

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- [Konfigurace domén](custom-domain-name-configure.md)
- [Nastavení autority MDM](mdm-authority-set.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Nastavení registrace zařízení s macOS

Intune již standardně umožňuje registraci zařízení se systémem macOS.

Pokud chcete u zařízení se systémem macOS registraci blokovat, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Je potřeba koncovým uživatelům sdělit, že mají přejít na [web Portál společnosti](http://portal.manage.microsoft.com) a podle pokynů zaregistrovat svá zařízení. Můžete jim také poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení s iOSem nebo macOS s Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
