---
title: "Registrace zařízení s Androidem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se registrovat zařízení s Androidem v Intune Azure Preview."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: b2cbabea781840df0a2a283f803dc76520590aba
ms.lasthandoff: 04/19/2017


---

# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune umožňuje spravovat zařízení s Androidem včetně zařízení používajících Samsung Knox Standard. Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svoje zařízení tak, že si stáhnou aplikaci Intune Company Portal, která je dostupná na Google Play, a pak otevřou tuto aplikaci a zaregistrují se podle pokynů. Když jsou zařízení s Androidem pod správou, můžete [vytvořit zásady dodržování předpisů](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [spravovat aplikace](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) a další.

U zařízení, která používají Samsung KNOX Standard, je teď podporována správa více uživatelů pomocí Intune. To znamená, že koncoví uživatelé se můžou k zařízení přihlašovat a ze zařízení odhlašovat pomocí svých přihlašovacích údajů Azure AD. Zařízení je centrálně spravované bez ohledu na to, jestli se zrovna používá. Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně aplikují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

## <a name="prerequisite"></a>Předpoklad

Při přípravě na správu mobilních zařízení musíte nastavit autoritu MDM na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](set-mdm-authority.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení, takže je možné, že ji už máte nastavenou.

## <a name="set-up-android-enrollment"></a>Nastavení registrace zařízení s Androidem

Standardně už je služba Intune nastavená tak, aby umožňovala registraci zařízení používajících Android a Samsung Knox Standard.

Pokud chcete blokovat registraci zařízení s Androidem nebo blokovat jenom zařízení s Androidem v osobním vlastnictví, přečtěte si téma [Nastavení omezení typu zařízení](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

Jestliže chcete nastavit maximální počet zařízení, která může uživatel zaregistrovat, přečtěte si téma [Nastavení omezení limitu počtu zařízení](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Budete muset říct koncovým uživatelům, že mají přejít na web Google Play a stáhnout si aplikaci Portál společnosti služby Intune a pak aplikaci otevřít a zaregistrovat svá zařízení podle pokynů. Aplikace provede uživatele procesem registrace a zobrazí informace o tom, co můžou očekávat a co uvidí nebo neuvidí správci IT na svých zařízeních.

Uživatelům také můžete poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem Android v Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Použití zařízení Android s Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)

