---
title: "Resetování hesla na zařízeních s Windows pomocí služby Intune"
titlesuffix: Azure portal
description: "Naučte se používat službu Intune k resetování hesla na zařízeních s Windows, na kterých je integrovaná služba Microsoft PIN Reset Service."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c00d52f3ed06e1810d8b537c2232221ac8f53bd
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Resetování hesla pomocí služby Intune na zařízeních s Windows, na kterých je integrovaná služba Microsoft PIN Reset Service

Funkce resetování hesla pro zařízení s Windows, na kterých je integrovaná služba Microsoft PIN Reset Service, vám umožňuje vygenerovat nové heslo pro zařízení se systémem Windows 10 Mobile. Zařízení musí mít aktualizaci Windows 10 Creators Update nebo novější.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno ve Windows 10 Creators Update a novějších verzích (při připojení k Azure AD)
- Windows Phone – nepodporováno
- iOS – nepodporováno
- macOS – nepodporováno
- Android – nepodporováno


## <a name="before-you-start"></a>Než začnete

Než budete moct vzdáleně resetovat heslo na vámi spravovaných zařízeních s Windows, musíte službu PIN Reset Service nasadit do svého tenanta Intune a nakonfigurovat spravovaná zařízení. Tohoto nastavení dosáhnete, když se budete řídit těmito pokyny:

### <a name="connect-intune-with-the-pin-reset-service"></a>Propojení služby Intune se službou PIN Reset Service

1. Přejděte na web [Microsoft PIN Reset Service Integration](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) a přihlaste se pomocí účtu správce tenanta, který používáte ke správě svého tenanta Intune.
2. Po přihlášení klikněte na **Accept** (Přijmout), abyste službě PIN Reset Service udělili přístup ke svému účtu.<br>
![Stránka oprávnění služby PIN Reset Service](./media/pin-reset-service-application.png)
3. Na portálu Azure Portal můžete ověřit, že služby Intune a PIN Reset Service byly integrovány z okna Podnikové aplikace – Všechny aplikace, jak je vidět na následujícím snímku obrazovky:<br>
![Aplikace PIN Reset Service v Azure](./media/pin-reset-service-home-screen.png)
4. Přihlaste se na [tento web](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) opět pomocí svého účtu správce tenanta Intune a zvolte **Accept** (Přijmout), abyste službě udělili přístup ke svému účtu.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Konfigurace zařízení s Windows, aby používaly službu PIN Reset Service

Pokud chcete nakonfigurovat službu PIN Reset Service na vámi spravovaných zařízeních s Windows, můžete k zapnutí této funkce použít [vlastní zásady zařízení s Windows 10 v Intune](custom-settings-windows-10.md). Zásady nakonfigurujte pomocí následujících poskytovatelů konfiguračních služeb (CSP) pro zásady Windows:


- **Pro zařízení** - **./Device/Vendor/MSFT/PassportForWork/*ID tenanta*/Policies/EnablePinRecovery**

*ID tenanta* je ID adresáře služby Azure Active Directory, které získáte na stránce **Vlastnosti** služby Azure Active Directory.

Nastavte hodnotu pro tohoto poskytovatele konfiguračních služeb na **True**.

## <a name="steps-to-reset-the-passcode"></a>Postup resetování hesla

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Spravovat** > **Všechna zařízení**.
5. Vyberte zařízení, u kterého chcete resetovat heslo, a potom v okně Vlastnosti zařízení zvolte **Nové heslo**.
6. Zobrazené potvrzení potvrďte možností **Ano**. Vygeneruje se heslo, které zůstane na portálu zobrazeno dalších sedm dní.

## <a name="next-steps"></a>Další kroky

Pokud se resetování hesla nepodaří, zobrazí se na portálu odkaz, ze kterého můžete získat další informace.


