---
title: "Registrace zařízení s Androidem v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se registrovat zařízení s Androidem v Intune Azure Preview."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Správce Intune může na Portálu společnosti povolit správu zařízení s Androidem, včetně zařízení se sadou Samsung Knox Standard. Uživatelé pak mohou k registraci svých zařízení použít aplikaci Portál společnosti, která je k dispozici v obchodě Google Play.

## <a name="prerequisite"></a>Předpoklad

Při přípravě na správu mobilních zařízení musíte nastavit autoritu MDM na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](set-mdm-authority.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení, takže je možné, že ji už máte nastavenou. 

## <a name="set-up-android-enrollment"></a>Nastavení registrace zařízení s Androidem

Ve výchozím nastavení je služba Intune nastavená tak, aby umožňovala registraci zařízení s Androidem a sadou Samsung Knox Standard. 

Pokud chcete zobrazit nastavení pro povolení nebo blokování registrace zařízení s Androidem, přejděte na portálu Azure Portal do okna Intune a zvolte **Registrace** > **Omezení registrace**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Androidem v Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Použití zařízení Android s Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


