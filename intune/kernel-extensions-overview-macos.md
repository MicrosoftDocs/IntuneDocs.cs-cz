---
title: Vytvoření jádra rozšíření zařízení profilu macOS v Microsoft Intune – Azure | Dokumentace Microsoftu
titleSuffix: ''
description: Přidejte nebo vytvořte profil zařízení s macOS a pak nakonfigurujte jádra rozšíření povolit uživateli přepsat, přidejte identifikátor týmu a identifikátoru sady prostředků a team v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67404012"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Přidání rozšíření jádra s macOS v Intune

Na zařízeních s macOS můžete přidat funkce na úrovni jádra. Tyto funkce přístup k součásti operačního systému, který nemá přístup k pravidelné programy. Vaše organizace může mít specifické požadavky nebo požadavky, které nejsou k dispozici v aplikaci, funkce zařízení a tak dále. 

Chcete-li přidat rozšíření jádra, které jsou vždy moct načíst v zařízeních, přidejte "jádra rozšíření" (KEXT) v Microsoft Intune a pak tato rozšíření nasadíte do zařízení.

Například můžete mít antivirový program, který vyhledá vaše zařízení na škodlivý obsah. Můžete přidat tento virů programu jádra rozšíření jako rozšíření povolené jádra v Intune. Potom "přiřazení" rozšíření pro zařízení s macOS.

Pomocí této funkce mohou správci povolit uživatelům přepsat jádra rozšíření, přidat identifikátory týmu a přidání konkrétních jádra rozšíření v Intune.

Tato funkce platí pro:

- macOS 10.13.2 a novější

Chcete-li tuto funkci používat, musí být zařízení:

- Zaregistrovaná v Intune pomocí programu registrace zařízení Apple (DEP). [Automatická registrace zařízení s macOS](device-enrollment-program-enroll-macos.md) obsahuje další informace.

  NEBO

- Zaregistrovaná v Intune pomocí "registrace uživatele schváleno" (termín společnosti Apple). [Příprava pro změny rozšíření jádra v systému macOS High Sierra](https://support.apple.com/en-us/HT208019) (otevře web společnosti Apple) obsahuje další informace.

Intune používá "konfiguračních profily" vytvořit a přizpůsobit nastavení pro potřeby vaší organizace. Po přidání těchto funkcí v profilu, můžete pak push nebo nasadit profil pro zařízení s macOS ve vaší organizaci.

V tomto článku se dozvíte, jak vytvořit profil konfigurace zařízení v Intune pomocí rozšíření jádra.

> [!TIP]
> Další informace o rozšířeních jádra najdete v tématu [jádra rozšíření – přehled](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (otevře web společnosti Apple).

## <a name="what-you-need-to-know"></a>Co je potřeba vědět

- Rozšíření bez znaménka starší verze jádra mohou být přidány.
- Je nutné zadat identifikátor správnému týmu a ID jádra rozšíření prostředků. Intune nepodporuje ověřit hodnoty, které zadáte. Pokud zadáte nesprávné informace, rozšíření nebudou fungovat v zařízení.

> [!NOTE]
> Apple vydala informace týkající se přihlašování a notarization pro veškerý software. V systému macOS 10.14.5 a novější, jádro rozšíření nasazenými prostřednictvím Intune nemusí splňovat zásady notarization společnosti Apple.
>
> Informace o této zásadě notarization a všechny aktualizace nebo změny najdete v článku na následujících odkazech:
>
>  - [Vaše aplikace před distribucí notarizing](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (otevře web společnosti Apple) 
>  - [Příprava pro změny rozšíření jádra v systému macOS High Sierra](https://support.apple.com/en-us/HT208019) (otevře web společnosti Apple)

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte **macOS**
    - **Typ profilu**: Vyberte **rozšíření**.
    - **Nastavení**: Zadejte nastavení, které chcete konfigurovat. Seznam všech nastavení, a co dělají naleznete v tématu:

        - [macOS](kernel-extensions-settings-macos.md)

4. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Profil se vytvoří a zobrazí v seznamu. Nezapomeňte [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

## <a name="next-steps"></a>Další postup

Po vytvoření profilu je připraven k přiřazení. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).
