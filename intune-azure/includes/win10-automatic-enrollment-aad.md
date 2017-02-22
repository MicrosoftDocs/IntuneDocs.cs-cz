## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Nastavení automatické registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium

Automatický zápis umožňuje registraci i uživatelům počítačů se systémem Windows 10 nebo zařízení Windows 10 Mobile, které patří jiným společnostem nebo soukromníkům. Stačí v Intune zadat pracovní nebo školní účet a souhlasit se správou. Opravdu je to takhle jednoduché. Na pozadí se uživatelovo zařízení zaregistruje a připojí ke službě Azure Active Directory. Po registraci je zařízení spravováno přes Intune.

**Požadavky**
- Předplatné Azure Active Directory Premium ([zkušební předplatné](http://go.microsoft.com/fwlink/?LinkID=816845))
- Odběr služby Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurace automatického zápisu MDM

1. Na [portálu pro správu Azure](https://portal.azure.com) (https://manage.windowsazure.com) přejděte na uzel **Služby Active Directory** a vyberte svůj adresář.

2. Vyberte kartu **Aplikace**. V seznamu aplikací se objeví **Microsoft Intune**.

    ![Aplikace Azure AD s Microsoft Intune](../media/aad-intune-app.png)

3. Vyberte šipku pro **Microsoft Intune**. Otevře se stránka, na které můžete nakonfigurovat Microsoft Intune.

4. Výběrem možnosti **Konfigurovat** spusťte konfiguraci automatické registrace MDM v Microsoft Intune.

5. Zadejte adresy URL pro Intune:

  - **Adresa URL registrace do MDM** – Použijte výchozí hodnotu.
  - **Adresa URL pro podmínky použití MDM** – Použijte výchozí hodnotu. Tato adresa URL zobrazí podmínky použití pro uživatele při registraci zařízení.
  - **Adresa URL pro stav souladu s MDM** – Použijte výchozí hodnotu. Pokud zařízení nesplňuje požadavky, zobrazí se u dané adresy URL zpráva **Přístup byl odepřen**. Tato adresa URL odkazuje na stránku, která uživatelům vysvětlí, proč jejich zařízení nevyhovuje zásadám a jak toho mohou znovu dosáhnout.

6.  Zadejte, která uživatelská zařízení by měla být spravována přes službu Microsoft Intune. Tato uživatelská zařízení se systémem Windows 10 budou automaticky zaregistrována pro správu přes službu Microsoft Intune.

  - **Vše**
  - **SKUPINY**
  - **Žádné**

7. Vyberte **Uložit**.


<!--HONumber=Feb17_HO2-->


