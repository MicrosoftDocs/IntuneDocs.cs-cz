---
ms.openlocfilehash: fbfff91d2993becc99e2132285bef78d245ff50e
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61497936"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Povolení automatické registrace pro Windows 10

Automatická registrace umožňuje uživatelům zaregistrovat zařízení s Windows 10 do Intune, když přidávají pracovní účet do svého osobního zařízení nebo připojují zařízení vlastněná společností k Azure Active Directory. Na pozadí se uživatelovo zařízení zaregistruje a připojí ke službě Azure Active Directory. Po registraci je zařízení spravováno přes Intune.

**Požadavky**
- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Odběr služby Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Přihlaste se k [portál pro správu Azure](https://portal.azure.com) (https://manage.windowsazure.com) a vyberte **Azure Active Directory**.

   ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-azure-main.png)

2. Vyberte **Mobilita (MDM a MAM)**.

   ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-mdm.png)

3. Vyberte **Microsoft Intune**.

   ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-intune.png)

4. Konfigurujte **Obor uživatele MDM**. Zadejte, která uživatelská zařízení by měla být spravována přes službu Microsoft Intune. Tato uživatelská zařízení se systémem Windows 10 budou automaticky zaregistrována pro správu přes službu Microsoft Intune.

   - **Žádné**
   - **Některé**
   - **Vše**

   ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-scope.png)

5. Použijte výchozí hodnoty pro následující adresy URL:
   - **Adresa URL podmínek použití MDM**
   - **Adresa URL zjišťování MDM**
   - **Adresa URL s předpisy služby MDM**

6. Vyberte **Uložit**.

Ve výchozím nastavení není pro službu povolené dvoufaktorové ověřování. Při registraci zařízení ale dvoufaktorové ověřování doporučujeme. Před vyžádáním dvoufaktorového ověřování pro tuto službu musíte v Azure Active Directory nakonfigurovat zprostředkovatele dvoufaktorového ověřování a u uživatelských účtů nakonfigurovat vícefaktorové ověřování. Informace najdete v článku [Začínáme s Azure Multi-Factor Authentication Serverem](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
