---
title: Nastavení registrace pro zařízení s macOSem
titleSuffix: Microsoft Intune
description: Přečtěte si, jak nastavit registraci zařízení s macOSem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec0e22c55e337d6ffe9b617c3858982859995b77
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729682"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Nastavení registrace pro zařízení s macOSem v Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune umožňuje spravovat zařízení s macOS tak, abyste uživatelům umožnili přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete nastavit registraci zařízení s macOS ve vlastnictví společnosti a zařízení s macOS v osobním vlastnictví (možnost Přineste si vlastní zařízení neboli BYOD). 

## <a name="prerequisites"></a>Požadované součásti

Před nastavením registrace zařízení s macOS zajistěte splnění následujících požadavků:

- Ujistěte [se, že vaše zařízení má nárok na registraci zařízení Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Konfigurace domén](../fundamentals/custom-domain-name-configure.md)
- [Nastavení autority MDM](../fundamentals/mdm-authority-set.md)
- [Vytvoření skupin](../fundamentals/groups-add.md)
- [Konfigurace aplikace Portál společnosti](../apps/company-portal-app.md)
- Přiřazení uživatelských licencí v [centru pro správu Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](../enrollment/apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Zařízení se systémem macOS vlastněná uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení licencí uživatelům si uživatelé můžou zaregistrovat svoje zařízení takto:
- přechodem na [web Portál společnosti](https://portal.manage.microsoft.com) nebo
- stažením aplikace Portál společnosti.
Můžete jim také poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](../fundamentals/end-user-educate.md)
- [Použití zařízení s macOS s Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Zařízení s macOS ve vlastnictví společnosti
U organizací, které svým uživatelům zařízení pořizují, Intune podporuje následující způsoby registrace zařízení s macOS ve vlastnictví společnosti:
- [Program registrace zařízení (DEP) společnosti Apple](device-enrollment-program-enroll-macos.md): Organizace můžou pořizovat zařízení s macOS prostřednictvím Programu registrace zařízení (DEP) společnosti Apple. Program DEP umožňuje vzdáleně (bezdrátově) nasadit registrační profil, který umožní správu těchto zařízení.
- [Správce registrace zařízení (DEM)](device-enrollment-manager-enroll.md): Pomocí účtu DEM můžete zaregistrovat až 1 000 zařízení.

## <a name="block-macos-enrollment"></a>Blokování registrace zařízení s macOS
Intune ve výchozím nastavení umožňuje registraci zařízení s macOS. Pokud chcete u zařízení se systémem macOS registraci blokovat, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Registrace virtuálních počítačů s macOS pro účely testování

> [!NOTE]
> Virtuální počítače s macOS se podporují pouze pro testování. Neměli byste je používat jako produkční zařízení pro koncové uživatele. 

Virtuální počítače s macOS pro testování můžete zaregistrovat pomocí softwaru Parallels Desktop nebo VMware Fusion. 

Pro Parallels Desktop musíte nastavit typ hardwaru a sériové číslo virtuálního počítače, aby ho služba Intune mohla rozpoznat. Podle pokynů pro rovnoběžky nastavte typ hardwaru a [sériové číslo](http://kb.parallels.com/123455) pro nastavení potřebných nastavení pro testování. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

U softwaru VMware Fusion musíte [upravit soubor .vmx](https://kb.vmware.com/s/article/1014782), abyste mohli nastavit model hardwaru a sériové číslo virtuálního počítače. Doporučujeme, abyste nastavili stejný typ hardwaru u zařízení, na kterém běží virtuální počítače, i u samotných virtuálních počítačů, které vytváříte. Tento typ hardwaru najdete v **nabídce Apple** > **O tomto Macu** > **Systémový profil** > **Identifikátor modelu**. 

## <a name="user-approved-enrollment"></a>Registrace schválená uživatelem

Registrace MDM schválená uživatelem je typ registrace macOS, kterou můžete využít ke správě určitých nastavení citlivých na zabezpečení. Další informace najdete v [dokumentaci podpory Apple](https://support.apple.com/HT208019).

Aby byla registrace schválená uživatelem, musí koncový uživatel po registraci pomocí Portálu společnosti pro macOS ručně zadat schválení pomocí předvoleb systému. Pokyny k tomu poskytuje Portál společnosti pro macOS pro uživatele v macOS 10.13.2 a novějším.

Pokud chcete zjistit, jestli je zařízení schválené uživatelem, přejděte na portál Intune a pak zvolte **Zařízení** > **Všechna zařízení**> vyberte zařízení > **Hardware**. Zaškrtněte políčko **User Approved** (Schválené uživatelem).

## <a name="next-steps"></a>Další kroky

Až budou zařízení s macOS zaregistrovaná, můžete [pro zařízení s macOS vytvořit vlastní nastavení](../configuration/custom-settings-macos.md).
