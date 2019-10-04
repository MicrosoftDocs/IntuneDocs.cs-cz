---
ms.openlocfilehash: 6f5b0c8df86cf5bf1206c1cccb879e37c7944a21
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71912754"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Povolit automatickou registraci Windows 10

Automatický zápis umožňuje uživatelům zaregistrovat svá zařízení s Windows 10 v Intune. K registraci uživatelé přidávají svůj pracovní účet do svých zařízení v osobním vlastnictví nebo připojí zařízení vlastněná společností Azure Active Directory. Na pozadí zařízení zaregistruje a spojí Azure Active Directory. Po registraci se zařízení spravuje přes Intune.

**Požadovaný**

- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Předplatné Microsoft Intune

### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Přihlaste se k [Azure Portal](https://portal.azure.com)a vyberte **Azure Active Directory**.

   ![Snímek obrazovky Azure Portal](../enrollment/media/windows-enroll/auto-enroll-azure-main.png)

2. Vyberte **mobilita (MDM a mam)** .

   ![Snímek obrazovky Azure Portal](../enrollment/media/windows-enroll/auto-enroll-mdm.png)

3. Vyberte **Microsoft Intune**.

   ![Snímek obrazovky Azure Portal](../enrollment/media/windows-enroll/auto-enroll-intune.png)

4. Nakonfigurujte **obor uživatele MDM**. Zadejte, která uživatelská zařízení by měla být spravovaná pomocí Microsoft Intune. Tato zařízení s Windows 10 se můžou automaticky zaregistrovat pro správu pomocí Microsoft Intune.

   - **Žádné** – automatický zápis se zakázanou MDM
   - **Některé** – vyberte **skupiny** , které můžou automaticky registrovat svoje zařízení s Windows 10.
   - **Všichni** – všichni uživatelé můžou automaticky zaregistrovat svoje zařízení s Windows 10.

      > [!IMPORTANT]
      > U zařízení BYOD má přednost obor uživatele MAM, pokud jsou povolené obory uživatelů MAM i obor uživatele MDM (Automatická registrace MDM) pro všechny uživatele (nebo stejné skupiny uživatelů). Zařízení bude používat zásady Windows Information Protection (nedokončené výroby) (Pokud je nakonfigurujete) místo registrace MDM.
      >
      > U podnikových zařízení má obor uživatele MDM přednost, pokud je povolený oba obory. Zařízení zaregistrovaná v MDM.

   > [!NOTE]
   > Obor uživatele MDM musí být nastavený na skupinu Azure AD, která obsahuje uživatelské objekty.

   ![Snímek obrazovky Azure Portal](../enrollment/media/windows-enroll/auto-enroll-scope.png)

5. Použijte výchozí hodnoty pro následující adresy URL:
    - **Adresa URL pro Podmínky použití MDM**
    - **Adresa URL zjišťování MDM**
    - **Adresa URL dodržování předpisů MDM**

6. Vyberte **Uložit**.

Ve výchozím nastavení není služba dvojúrovňové ověřování pro službu povolená. Při registraci zařízení se však doporučuje dvojúrovňové ověřování. Pokud chcete povolit dvojúrovňové ověřování, nakonfigurujte ve službě Azure AD zprostředkovatele dvojúrovňového ověřování a nakonfigurujete uživatelské účty pro službu Multi-Factor Authentication. Viz [Začínáme s Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
