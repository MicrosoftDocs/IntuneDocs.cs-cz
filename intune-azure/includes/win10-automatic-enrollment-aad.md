## <a name="enable-windows-10-automatic-enrollment"></a>Povolení automatické registrace pro Windows 10

Automatický zápis umožňuje registraci i uživatelům počítačů se systémem Windows 10 nebo zařízení Windows 10 Mobile, které patří jiným společnostem nebo soukromníkům. Stačí v Intune zadat pracovní nebo školní účet a souhlasit se správou. Opravdu je to takhle jednoduché. Na pozadí se uživatelovo zařízení zaregistruje a připojí ke službě Azure Active Directory. Po registraci je zařízení spravováno přes Intune.

**Požadavky**
- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Odběr služby Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Přihlaste se k [portálu pro správu Azure](https://portal.azure.com) (https://manage.windowsazure.com) a vyberte **Azure Active Directory**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-azure-main.png)

2. Vyberte **Mobilita (MDM a MAM)**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-mdm.png)

3. Vyberte **Microsoft Intune**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-intune.png)

4. Nakonfigurujte, kteří uživatelé se automaticky zaregistrují.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-scope.png)

  Použijte výchozí hodnoty pro následující adresy URL:
  - **Registrace MDM**
  - **Podmínky použití MDM**
  - **Dodržování předpisů MDM**

5. Zadejte, která uživatelská zařízení by měla být spravována přes službu Microsoft Intune. Tato uživatelská zařízení se systémem Windows 10 budou automaticky zaregistrována pro správu přes službu Microsoft Intune.

  - **Vše**
  - **SKUPINY**
  - **Žádné**

6. Vyberte **Uložit**.
