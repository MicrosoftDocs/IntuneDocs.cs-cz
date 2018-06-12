---
title: Vzdálená správa zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na role, které jsou potřeba pro použití TeamVieweru, jak nainstalovat konektor TeamVieweru a přečtěte si podrobné pokyny ke vzdálené správě zařízení pomocí Microsoft Intune na portálu Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 60d9398b80a30adee194470ac4e5c6c1efc0bd4c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744631"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Vzdálená správa zařízení s Intune pomocí TeamVieweru

Zařízení spravovaná pomocí Intune je možné spravovat vzdáleně pomocí [TeamVieweru](https://www.teamviewer.com). TeamViewer je program od jiného výrobce, který se kupuje samostatně. V tomto tématu můžete vidět, jak nakonfigurovat TeamViewer v rámci Intune a vzdáleně spravovat zařízení. 

## <a name="prerequisites"></a>Požadavky

- Používejte podporované zařízení. Vzdálenou správu podporují zařízení s Androidem, Windows, iOSem a macOS, která jsou spravovaná přes Intune. TeamViewer nemusí podporovat Windows Holographic (HoloLens), Windows Team (Surface Hub) nebo Windows 10 S. Informace týkající se aktualizací podpory najdete v části [TeamViewer](https://www.teamviewer.com).

- Správce Intune musí mít na portálu Azure Portal tyto [role Intune](role-based-access-control.md):  

    - **Aktualizovat vzdálenou pomoc**: Umožňuje správcům upravit nastavení konektoru TeamVieweru.
    - **Požádat o vzdálenou pomoc**: Umožňuje správcům zahájit pro libovolného uživatele novou relaci vzdálené pomoci. Uživatele s touto rolí neomezuje žádná role Intune, která je v daném rozsahu. Uživatelé nebo skupiny zařízení, kteří mají přiřazenou roli Intune v rámci rozsahu, si také můžou vyžádat vzdálenou pomoc. 

- Účet [TeamViewer](https://www.teamviewer.com) s přihlašovacími údaji

Když použijete TeamViewer, umožníte Konektoru pro TeamViewer služby Intune vytvářet relace TeamVieweru, číst data služby Active Directory a uložit přístupový token účtu TeamVieweru.

## <a name="configure-the-teamviewer-connector"></a>Konfigurace konektoru pro TeamViewer

Abyste mohli poskytovat vzdálenou pomoc pro zařízení, nakonfigurujte si s použitím následujícího postupu konektor pro TeamViewer a Intune:

1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.
2. V **Microsoft Intune** vyberte **Zařízení** a potom vyberte **Konektor pro TeamViewer**.
3. Vyberte **Připojit** a přijměte podmínky licenční smlouvy.
4. Zvolte **Přihlásit se k TeamVieweru pro autorizaci**.
5. Otevře se webová stránka TeamVieweru. Zadejte přihlašovací údaje pro svoji licenci TeamVieweru a pak se **přihlaste**.

## <a name="remotely-administer-a-device"></a>Vzdálená správa zařízení

Po konfiguraci konektoru jste připravení vzdáleně spravovat zařízení. Postupujte podle následujících pokynů: 

1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.
2. V **Microsoft Intune** vyberte **Zařízení** a potom **Všechna zařízení**.
3. V seznamu vyberte zařízení, které chcete vzdáleně spravovat. Ve vlastnostech zařízení vyberte **Nová relace Vzdálené pomoci**.
4. Až se Intune ke službě TeamViewer připojí, zobrazí se některé informace o zařízení. Ke spuštění vzdálené relace použijte možnost **Připojit**.

![Vzdálená správa zařízení s Androidem pomocí TeamVieweru – příklad](./media/android-teamviewer.png)

Když spustíte vzdálenou relaci, zobrazí se koncovému uživateli na zařízení na ikoně aplikace Portál společnosti příznak oznámení. Oznámení se zobrazí také při spuštění aplikace. Uživatel pak může přijmout žádost o vzdálenou pomoc.

V TeamVieweru můžete provést na zařízení řadu akcí, včetně převzetí řízení zařízení. Úplné podrobnosti s informacemi, co můžete dělat, najdete v tématu [Pokyny k TeamVieweru](https://www.teamviewer.com/support/documents/).

Až budete mít hotovo, okno TeamVieweru zavřete.