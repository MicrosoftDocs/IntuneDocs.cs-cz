---
title: 'Rychlý start: Nastavení požadované délky hesla pro zařízení s Androidem'
titlesuffix: Microsoft Intune
description: V tomto rychlém startu nastavíte v Microsoft Intune délku hesla, která se vyžaduje pro zařízení s Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395275"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Rychlý start: Nastavení požadované délky hesla pro zařízení s Androidem

V tomto rychlém startu použijete Microsoft Intune a nastavíte, že uživatelé firemních zařízení s Androidem musí zadat heslo o určité délce, aby získali přístup k informacím na svých zařízeních s Androidem. 

> [!IMPORTANT]
> Kromě nastavení hesla byste také měli zvážit další nastavení zabezpečení systému pro ochranu pracovníků. Další informace najdete v tématu [Systémové nastavení zabezpečení](compliance-policy-create-android-for-work.md#system-security-settings).

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune. Intune najdete na webu Azure Portal, když zvolíte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení
1. V otevřeném okně **Microsoft Intune** vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Jako **Název** přidejte **Dodržování předpisů v Androidu**. Přidejte také **Popis**.
3. U možnosti **Platforma** vyberte **Android**. 
4. Vyberte **Nastavení** > **Zabezpečení systému** a zobrazte okno **Zabezpečení systému** Androidu.
5. V části **Heslo** klikněte vedle možnosti **Vyžadovat heslo k odemknutí mobilních zařízení** na **Vyžadovat**.
6. Vedle možnosti **Minimální délka hesla** zadejte **6**.  

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](./media/quickstart-set-password-length-android-01.png)

7. Až to budete mít, klikněte na **OK** a zavřete okno **Zabezpečení systému**. 
8. Kliknutím na **OK** zavřete okno **Zásady dodržování předpisů v Androidu**. 
9. Kliknutím na **Vytvořit** vytvořte zásadu.

Pokud se vám podařilo zásadu vytvořit, zobrazí se v seznamu **Dodržování předpisů zařízením – Zásady**. 

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste v Intune vytvořili zásadu dodržování předpisů pro firemní zařízení s Androidem, která vyžaduje zadání hesla o minimální délce šesti znaků.

> [!div class="nextstepaction"]
> [Nastavení automatické registrace](quickstart-setup-auto-enrollment.md)
