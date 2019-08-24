---
title: Rychlý Start – zásada dodržování předpisů heslem pro zařízení s Androidem
titleSuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k nastavení délky hesla, která se vyžaduje pro zařízení s Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30c4d5976b7f743a12a9691878e2b7031e373b1d
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "70001833"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Rychlý Start Vytvoření zásad dodržování předpisů pro hesla pro zařízení s Androidem

V tomto rychlém startu použijete Microsoft Intune a nastavíte, že uživatelé firemních zařízení s Androidem musí zadat heslo o určité délce, aby získali přístup k informacím na svých zařízeních s Androidem. 

Zásada dodržování předpisů Intune pro zařízení určuje pravidla a nastavení, která zařízení musí splňovat, aby bylo považováno za dodržující předpisy. Zásady dodržování předpisů s podmíněným přístupem můžete použít k povolení nebo blokování přístupu k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů.

> [!IMPORTANT]
> Kromě nastavení hesla byste také měli zvážit další nastavení zabezpečení systému pro ochranu pracovníků. Další informace najdete v tématu [Systémové nastavení zabezpečení](compliance-policy-create-android-for-work.md).

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune. 

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

V tomto rychlém startu použijete Intune a nastavíte, že zaměstnanci používající Android musí zadat heslo o určité délce, aby na svých zařízeních s Androidem získali přístup k informacím.

1. V Intune vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Jako **Název** přidejte **Dodržování předpisů v Androidu**. Přidejte také **Popis**.
3. U možnosti **Platforma** vyberte **Android**. 
4. Vyberte **Nastavení** > **Zabezpečení systému** a zobrazte okno **Zabezpečení systému** Androidu.
5. Klikněte na **Vyžadovat** vedle **Vyžadovat heslo k odemknutí mobilních zařízení**.
6. V poli **požadovaný typ hesla**vyberte **aspoň číslice** .
7. Vedle volby **Minimální délka hesla** zadejte **6**. 

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Až budete hotovi, kliknutím na **OK** > **OK** > **Vytvořit** vytvořte tuto zásadu.

Pokud se vám podařilo zásadu vytvořit, zobrazí se v seznamu zásad dodržování předpisů zařízeními. 

## <a name="clean-up-resources"></a>Vyčištění prostředků

Až tuto zásadu nebudete potřebovat, odstraňte ji. Uděláte to tak, že tuto zásadu dodržování předpisů vyberete a kliknete na **Odstranit**.

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste v Intune vytvořili zásadu dodržování předpisů pro firemní zařízení s Androidem, která vyžaduje zadání hesla o minimální délce šesti znaků. Další informace o vytváření zásad dodržování předpisů najdete v článku [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý Start Odesílání oznámení na zařízení nedodržující předpisy](quickstart-send-notification.md)
