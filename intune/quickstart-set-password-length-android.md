---
title: Rychlý start – vytvoření zásady dodržování předpisů pro hesla pro zařízení s Androidem
titlesuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k nastavení délky hesla, která se vyžaduje pro zařízení s Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62ae0c7b9a00c3e07bb49261ca1a20bd5ef5db15
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57397227"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Rychlý start: Vytvoření zásady dodržování předpisů hesla pro zařízení s Androidem

V tomto rychlém startu použijete Microsoft Intune a nastavíte, že uživatelé firemních zařízení s Androidem musí zadat heslo o určité délce, aby získali přístup k informacím na svých zařízeních s Androidem. 

Zásada dodržování předpisů Intune pro zařízení určuje pravidla a nastavení, která zařízení musí splňovat, aby bylo považováno za dodržující předpisy. Pomocí zásad dodržování předpisů a podmíněného přístupu můžete povolit nebo zablokovat přístup k firemním prostředkům. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů.

> [!IMPORTANT]
> Kromě nastavení hesla byste také měli zvážit další nastavení zabezpečení systému pro ochranu pracovníků. Další informace najdete v tématu [Systémové nastavení zabezpečení](compliance-policy-create-android-for-work.md#system-security-settings).

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
6. Vedle volby **Minimální délka hesla** zadejte **6**. 

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Až budete hotovi, kliknutím na **OK** > **OK** > **Vytvořit** vytvořte tuto zásadu.

Pokud se vám podařilo zásadu vytvořit, zobrazí se v seznamu zásad dodržování předpisů zařízeními. 

## <a name="clean-up-resources"></a>Vyčištění prostředků

Až tuto zásadu nebudete potřebovat, odstraňte ji. Uděláte to tak, že tuto zásadu dodržování předpisů vyberete a kliknete na **Odstranit**.

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste v Intune vytvořili zásadu dodržování předpisů pro firemní zařízení s Androidem, která vyžaduje zadání hesla o minimální délce šesti znaků. Další informace o vytváření zásad dodržování předpisů najdete v článku [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Odesílání oznámení do zařízení nedodržující předpisy](quickstart-send-notification.md)
