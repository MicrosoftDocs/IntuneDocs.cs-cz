---
title: Nastavení registrace pro zařízení s macOSem
titlesuffix: Microsoft Intune
description: Přečtěte si, jak nastavit registraci zařízení s macOSem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5ffd2dca10db3df6abdcd5fa9603f1f58a37a078
ms.sourcegitcommit: e0d55bdda1a818ffe4cfc0ef0592833e22f65a89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290532"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Nastavení registrace pro zařízení s macOSem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení s macOS tak, abyste uživatelům umožnili přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete nastavit registraci zařízení s macOS ve vlastnictví společnosti a zařízení s macOS v osobním vlastnictví (možnost Přineste si vlastní zařízení neboli BYOD). 

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- [Konfigurace domén](custom-domain-name-configure.md)
- [Nastavení autority MDM](mdm-authority-set.md)
- [Vytvoření skupin](groups-add.md)
- [Konfigurace aplikace Portál společnosti](company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Zařízení se systémem macOS vlastněná uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení licencí uživatelům si uživatelé můžou zaregistrovat svoje zařízení takto:
- přechodem na [web Portál společnosti](https://portal.manage.microsoft.com) nebo
- stažením aplikace Portál společnosti.
Můžete také odeslat je odkaz na postup online registrace: [Registrace zařízení s macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení s macOS s Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Zařízení s macOS ve vlastnictví společnosti
U organizací, které svým uživatelům zařízení pořizují, Intune podporuje následující způsoby registrace zařízení s macOS ve vlastnictví společnosti:
- [Program registrace zařízení Apple (DEP)](device-enrollment-program-enroll-macos.md): Organizace můžou nakupovat zařízení s macOS prostřednictvím Apple zařízení registrace programu (DEP). Program DEP umožňuje vzdáleně (bezdrátově) nasadit registrační profil, který umožní správu těchto zařízení.
- [Správce registrace zařízení (DEM)](device-enrollment-manager-enroll.md): Můžete použít účet DEM k registraci až 1000 zařízení.

## <a name="block-macos-enrollment"></a>Blokování registrace zařízení s macOS
Intune ve výchozím nastavení umožňuje registraci zařízení s macOS. Pokud chcete u zařízení se systémem macOS registraci blokovat, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Registrace virtuálních počítačů s macOS pro účely testování

> [!NOTE]
> Virtuální počítače s macOS se podporují pouze pro testování. Neměli byste je používat jako produkční zařízení pro koncové uživatele. 

Virtuální počítače s macOS pro testování můžete zaregistrovat pomocí softwaru Parallels Desktop nebo VMware Fusion. 

Pro Parallels Desktop musíte nastavit typ hardwaru a sériové číslo virtuálního počítače, aby ho služba Intune mohla rozpoznat. Postupujte podle pokynů softwaru Parallels k nastavení typu hardwaru a [sériové číslo](http://kb.parallels.com/123455) nastavení potřebná nastavení pro testování. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

U softwaru VMware Fusion musíte [upravit soubor .vmx](https://kb.vmware.com/s/article/1014782), abyste mohli nastavit model hardwaru a sériové číslo virtuálního počítače. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

## <a name="user-approved-enrollment"></a>Registrace schválená uživatelem

Registrace MDM schválená uživatelem je typ registrace macOS, kterou můžete využít ke správě určitých nastavení citlivých na zabezpečení. Další informace najdete v [dokumentaci podpory Apple](https://support.apple.com/HT208019).

Aby byla registrace schválená uživatelem, musí koncový uživatel po registraci pomocí Portálu společnosti pro macOS ručně zadat schválení pomocí předvoleb systému. Pokyny k tomu poskytuje Portál společnosti pro macOS pro uživatele v macOS 10.13.2 a novějším.

Pokud chcete zjistit, jestli je zařízení schválené uživatelem, přejděte na portál Intune a pak zvolte **Zařízení** > **Všechna zařízení**> vyberte zařízení > **Hardware**. Zaškrtněte políčko **User Approved** (Schválené uživatelem).

## <a name="next-steps"></a>Další postup

Až budou zařízení s macOS zaregistrovaná, můžete [pro zařízení s macOS vytvořit vlastní nastavení](custom-settings-macos.md).
