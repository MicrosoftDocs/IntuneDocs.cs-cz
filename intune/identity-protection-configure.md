---
title: PIN kód používáte k přihlášení na zařízení s Windows 10 pomocí Microsoft Intune – Azure | Dokumentace Microsoftu
description: Použití Windows Hello pro firmy umožňuje uživatelům přihlašovat do zařízení pomocí kódu PIN, otisku prstu a další. Vytvoření profilu konfigurace ochrany identit v zařízení s Intune pro Windows 10 s těmito nastaveními a přiřaďte profil ke skupinám uživatelů a skupin zařízení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d52c140a8cf408955d8a8d4cbce6038349b5b66b
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57395810"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Použití Windows Hello pro firmy na zařízeních s Windows 10 pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows Hello pro firmy je metoda pro přihlašování do Windows zařízení tak, že nahradíte hesla, čipové karty a virtuální čipové karty. Intune obsahuje vestavěné nastavení, takže správci můžou konfigurovat a používat Windows Hello pro firmy. Například můžete použít tato nastavení:

- Povolit Windows Hello pro firmy pro zařízení a uživatelů
- Nastavit požadavky na PIN kód zařízení, včetně minimální nebo maximální délku PIN kódu
- Povolit gesta, třeba otisk prstu, který mohou uživatelé (nebo nemůže používat) pro přihlášení k zařízení

Tato funkce je dostupná pro zařízení s následujícími systémy:

- Windows 10 a novější
- Windows 10 Mobile
- Windows Holographic for Business

Intune používá "konfiguračních profily" vytvořit a přizpůsobit nastavení pro potřeby vaší organizace. Po přidání těchto funkcí v profilu, push nebo nasazení těchto nastavení do skupiny uživatelů a zařízení ve vaší organizaci.

V tomto článku se dozvíte, jak vytvořit profil konfigurace zařízení. Seznam všech nastavení, a co dělají, naleznete v tématu [nastavení zařízení Windows 10 a povolit Windows Hello pro firmy](identity-protection-windows-settings.md).

## <a name="create-the-device-profile"></a>Vytvoření profilu zařízení

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte **Windows 10 a novější**. Windows Hello pro firmy se podporuje jen na zařízeních s Windows 10 a novějšími.
    - **Typ profilu**: Vyberte **Identity protection**.
    - **Konfigurovat Windows Hello pro firmy**: Zvolte, jak chcete konfigurovat Windows Hello pro firmy. Možnosti:

        - **Není nakonfigurováno**: [Zřídí Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) na zařízení. Pokud profily ochrany identit přiřazujete jen uživatelům, kontext zařízení nastaví výchozí hodnotu **Nenakonfigurováno**.
        - **Zakázané**: Tuto možnost vyberte, pokud nechcete použít Windows Hello pro firmy. Tato možnost zakáže Windows Hello pro firmy pro všechny uživatele.
        - **Povolené**: Výběrem této možnosti [zřízení]((https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning))a nakonfigurujte Windows Hello pro firmy nastavení v Intune. Zadejte nastavení, které chcete konfigurovat. Seznam všech nastavení, a co dělají naleznete v tématu:

            - [Nastavení zařízení Windows 10 a povolit Windows Hello pro firmy](identity-protection-windows-settings.md)

4. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Profil se vytvoří a zobrazí v seznamu profilů. Dále [přiřadit](device-profile-assign.md) tento profil ke skupinám uživatelů a zařízení podle svých potřeb.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>Další postup

- Zobrazit seznam všech [nastavení a co dělají](identity-protection-windows-settings.md).
- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
