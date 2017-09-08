## <a name="enable-windows-10-automatic-enrollment"></a>Povolení automatické registrace pro Windows 10

Automatická registrace umožňuje uživatelům, aby si svoje zařízení s Windows 10 zaregistrovali v Intune. Při registraci si uživatelé přidají pracovní účet do svého vlastního zařízení nebo připojí zařízení, která patří společnosti, ke službě Azure Active Directory. Na pozadí se zařízení zaregistruje a připojí ke službě Azure Active Directory. Po registraci je zařízení spravováno přes Intune.

**Požadavky**
- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Odběr služby Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com) a vyberte **Azure Active Directory**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-azure-main.png)

2. Vyberte **Mobilita (MDM a MAM)**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-mdm.png)

3. Vyberte **Microsoft Intune**.

  ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-intune.png)

4. Konfigurujte **Obor uživatele MDM**. Zadejte, která uživatelská zařízení by měla být spravována přes službu Microsoft Intune. Tato zařízení s Windows 10 se mohou automaticky zaregistrovat pro správu přes Microsoft Intune.

  - **Žádné**
  - **Některé**
  - **Vše**

   ![Snímek obrazovky portálu Azure Portal](../media/auto-enroll-scope.png)

5. Použijte výchozí hodnoty pro následující adresy URL:
    - **Adresa URL podmínek použití MDM**
    - **Adresa URL zjišťování MDM**
    - **Adresa URL s předpisy služby MDM**

    > [!IMPORTANT]
    > Pokud u skupiny povolíte jak **obor uživatele MAM**, tak i automatickou registraci MDM (**obor uživatele MDM**), povolí se jenom MAM. Při připojení osobního zařízení k pracovnímu prostoru se pro uživatele v dané skupině přidá jenom MAM. Zařízení se v MDM neregistrují automaticky.

6. Vyberte **Uložit**.

Ve výchozím nastavení není pro službu povolené dvoufaktorové ověřování. Při registraci zařízení ale dvoufaktorové ověřování doporučujeme. Pokud chcete povolit dvoufaktorové ověřování, nakonfigurujte v Azure AD zprostředkovatele dvoufaktorového ověřování a u uživatelských účtů nakonfigurujte vícefaktorové ověřování. Informace najdete v článku [Začínáme s Azure Multi-Factor Authentication Serverem](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
