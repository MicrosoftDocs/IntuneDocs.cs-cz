---
title: Nastavení registrace pro zařízení s macOSem
titlesuffix: Microsoft Intune
description: Přečtěte si, jak nastavit registraci zařízení s macOSem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8cddb69ac85e45acde8a846df3b5413c3b75bf
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Nastavení registrace pro zařízení s macOSem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení se systémem macOS. Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svá zařízení tak, že přejdou na [web Portál společnosti](http://portal.manage.microsoft.com) a budou postupovat podle pokynů. Až budou zařízení se systémem macOS pod správou, můžete [pro zařízení se systémem macOS vytvořit vlastní nastavení](custom-settings-macos.md). Další možnosti budou brzy k dispozici.

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- [Konfigurace domén](custom-domain-name-configure.md)
- [Nastavení autority MDM](mdm-authority-set.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](apple-mdm-push-certificate-get.md)

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení uživatelských licencí si uživatelé můžou stáhnout aplikaci Portál společnosti pro macOS z App Storu a podle pokynů v aplikaci si zařízení zaregistrovat.

## <a name="company-owned-ios-devices"></a>Zařízení s iOSem patřící společnosti
U organizací, které svým uživatelům zařízení pořizují, Intune podporuje registraci zařízení s macOSem patřících společnosti pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="set-up-macos-enrollment"></a>Nastavení registrace zařízení s macOS

Intune již standardně umožňuje registraci zařízení se systémem macOS.

Pokud chcete u zařízení se systémem macOS registraci blokovat, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Sdělte koncovým uživatelům, že mají přejít na [web Portál společnosti](https://portal.manage.microsoft.com) a podle pokynů zaregistrovat svoje zařízení. Můžete jim také poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení s macOS s Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Registrace virtuálních počítačů s macOS pro účely testování

> [!NOTE]
> Virtuální počítače s macOS se podporují pouze pro testování. Neměli byste je používat jako produkční zařízení pro koncové uživatele. 

Virtuální počítače s macOS pro testování můžete zaregistrovat pomocí softwaru Parallels Desktop nebo VMware Fusion. 

Pro Parallels Desktop musíte nastavit typ hardwaru a sériové číslo virtuálního počítače, aby ho služba Intune mohla rozpoznat. Podle pokynů softwaru Parallels k [nastavení typu hardwaru](http://kb.parallels.com/123594) a [sériového čísla](http://kb.parallels.com/123455) nakonfigurujte potřebná nastavení pro testování. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

U softwaru VMware Fusion musíte [upravit soubor .vmx](https://kb.vmware.com/s/article/1014782), abyste mohli nastavit model hardwaru a sériové číslo virtuálního počítače. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

## <a name="user-approved-enrollment"></a>Registrace schválená uživatelem

Registrace MDM schválená uživatelem je typ registrace macOS, kterou můžete využít ke správě určitých nastavení citlivých na zabezpečení. Další informace najdete v [dokumentaci podpory Apple](https://support.apple.com/HT208019).

Aby byla registrace schválená uživatelem, musí koncový uživatel po registraci pomocí Portálu společnosti pro macOS ručně zadat schválení pomocí předvoleb systému. Pokyny k tomu poskytuje Portál společnosti pro macOS pro uživatele v macOS 10.13.2 a novějším.

Pokud chcete zjistit, jestli je zařízení schválené uživatelem, přejděte na portál Intune a pak zvolte **Zařízení** > **Všechna zařízení**> vyberte zařízení > **Hardware**. Zaškrtněte políčko **User Approved** (Schválené uživatelem).