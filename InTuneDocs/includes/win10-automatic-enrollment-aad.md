## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Nastavení automatické registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium

Automatický zápis umožňuje registraci i uživatelům počítačů se systémem Windows 10 nebo zařízení Windows 10 Mobile, které patří jiným společnostem nebo soukromníkům. Stačí v Intune zadat pracovní nebo školní účet a souhlasit se správou. Opravdu je to takhle jednoduché. Na pozadí se uživatelovo zařízení zaregistruje a připojí ke službě Azure Active Directory. Po registraci je zařízení spravováno přes Intune.

**Požadavky**
- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Odběr služby Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Na [portálu pro správu Azure](https://manage.windowsazure.com) (https://manage.windowsazure.com) přejděte na uzel **Služby Active Directory** a vyberte svůj adresář.

2. Vyberte kartu **Aplikace**. V seznamu aplikací se objeví **Microsoft Intune**.

    ![Aplikace Azure AD s Microsoft Intune](../media/aad-intune-app.png)

3. Vyberte šipku pro **Microsoft Intune**. Uvidíte stránku, na které můžete nakonfigurovat Microsoft Intune.

4. Výběrem možnosti **Konfigurovat** spusťte konfiguraci automatické registrace MDM v Microsoft Intune.

5. Použijte výchozí hodnoty pro následující adresy URL:

  - **Registrace MDM**
  - **Podmínky použití MDM** 
  - **Dodržování předpisů MDM**

6.  Zadejte, která uživatelská zařízení by měla být spravována přes službu Microsoft Intune. Tato uživatelská zařízení se systémem Windows 10 budou automaticky zaregistrována pro správu přes službu Microsoft Intune.

  - **Vše**
  - **SKUPINY**
  - **Žádné**

7. Vyberte **Uložit**.
