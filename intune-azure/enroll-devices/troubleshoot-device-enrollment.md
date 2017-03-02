---
title: "Řešení potíží při registraci zařízení"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak můžete řešit potíže s registrací zařízení."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9fff350240e4313994056bc5aebf82e204ab3c62
ms.lasthandoff: 02/18/2017


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Řešení potíží s registrací do služby Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Toto téma obsahuje doporučení pro řešení potíží s registrací zařízení. Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), ve kterém najdete další způsoby, jak získat nápovědu.


## <a name="initial-troubleshooting-steps"></a>První kroky při řešení potíží

Než začnete řešit potíže, ujistěte se, že jste správně nakonfigurovali Intune pro povolení registrace. Odkazy na postup registrace pro jednotlivé platformy najdete v tématu [Registrace zařízení s Androidem a Standard Knox](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices.md).

Uživatelé spravovaných zařízení můžou pro vaši potřebu shromažďovat protokoly registrace a diagnostiky. Pokyny pro uživatele ke shromažďování protokolů najdete tady:

- [Odeslání chyb registrace zařízení s Androidem správci IT](https://docs.microsoft.com/intune/enduser/send-enrollment-errors-to-your-it-admin-android)
- [Odeslání chyb zařízení s iOSem správci IT](https://docs.microsoft.com/intune/enduser/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Obecné problémy s registrací
K těmto problémům může docházet na všech platformách zařízení.

### <a name="device-cap-reached"></a>Dosažení limitu zařízení
**Problém:** Při registraci se uživateli na zařízení zobrazí chyba, na zařízení se systémem iOS třeba chyba **Portál společnosti není dočasně k dispozici**, a protokol DMPdownloader.log v Configuration Manageru obsahuje chybu **DeviceCapReached**.

**Řešení:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Kontrola počtu zaregistrovaných a povolených zařízení

Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune na portálu Azure Portal přejděte na **Registrovat zařízení** > **Omezení registrace** a zkontrolujte, že uživatel nemá přidružených více zařízení, než je povolený maximální počet 15 zařízení.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Správci můžou zařízení odstraňovat na portálu služby Azure Active Directory.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Odstranění zařízení na portálu služby Azure Active Directory

1.  Přejděte na adresu [http://aka.ms/accessaad](http://aka.ms/accessaad) nebo zvolte **Správce** &gt; **Azure AD** na webu [https://portal.office.com](https://portal.office.com).

2.  Použijte odkaz v levé části stránky a přihlaste se pod svým ID organizace.

3.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (zvolte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory**).

4.  Vyberte možnost **Active Directory** a potom vyberte svoji organizaci.

5.  Vyberte kartu **Uživatelé** .

6.  Vyberte uživatele, jehož zařízení chcete odstranit.

7.  Zvolte **Zařízení**.

8.  Odeberte zařízení podle potřeby, třeba zařízení, která už se nepoužívají, nebo zařízení s nesprávnými definicemi.

> [!NOTE]

> Limitu registrace zařízení se můžete vyhnout tak, že použijete správce registrace zařízení, jak je popsané v tématu [Registrace zařízení pomocí správce registrace zařízení](/intune-azure/enroll-devices/enroll-devices-using-device-enrollment-manager.md).
>
> Pokud se pro přihlašovací jméno uživatele, jehož účet přidáte do skupiny správců registrace zařízení, vynucuje zásada podmíněného přístupu, nebude možné dokončit registraci.

### <a name="company-portal-temporarily-unavailable"></a>Portál společnosti není dočasně k dispozici
**Problém:** Uživateli se na zařízení se zobrazí chyba **Portál společnosti není dočasně k dispozici**.

**Řešení:**

1.  Odeberte ze zařízení aplikaci Portál společnosti Intune.

2.  Otevřete v zařízení prohlížeč, přejděte na adresu [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)a pokuste se přihlásit uživatele.

3.  Pokud se uživateli nepodaří přihlásit, požádejte ho, ať vyzkouší jinou síť.

4.  Pokud to nepomůže, zkontrolujte, jestli správně proběhla synchronizace přihlašovacích údajů uživatele se službou Azure Active Directory.

5.  Pokud se uživatel úspěšně přihlásí, zařízení se systémem iOS zobrazí výzvu k instalaci aplikace Portál společnosti Intune a k registraci. V zařízení se systémem Android budete muset aplikaci Portál společnosti Intune nainstalovat ručně. Potom se můžete znovu zkusit přihlásit.

### <a name="mdm-authority-not-defined"></a>Není definována autorita MDM
**Problém:** Zobrazí se chyba **Není definována autorita MDM**.

**Řešení:**

1.  Zkontrolujte, jestli je nastavená správná autorita pro správu mobilních zařízení (MDM) pro typ služby Intune, který používáte (tj. pro Intune, Office 365 nebo System Center Configuration Manager s Intune). Pokyny najdete v tématu [Nastavení autority pro správu mobilních zařízení](https://docs.microsoft.com/en-us/intune-azure/enroll-devices/set-mdm-authority).

    > [!NOTE]
    > Jakmile jednou nastavíte autoritu MDM, můžete ji změnit jedině tak, že se obrátíte na podporu, jak je popsáno v tématu [Jak získat podporu pro Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

2.  Ověřte správnou synchronizaci přihlašovacích údajů uživatele se službou Azure Active Directory tím, že zkontrolujete, jestli hlavní název uživatele (UPN) odpovídá údajům služby Active Directory na portálu účtů.
    Pokud hlavní název uživatele neodpovídá údajům služby Active Directory:

    1.  Vypněte na místním serveru službu DirSync.

    2.  Odstraňte neodpovídajícího uživatele ze seznamu uživatelů na **portálu účtů Intune** .

    3.  Počkejte zhruba hodinu, aby měla služba Azure dost času odebrat nesprávná data.

    4.  Znovu zapněte službu DirSync a zkontrolujte, jestli je teď uživatel správně synchronizovaný.

3.  Pokud používáte nástroj System Center Configuration Manager se službou Intune, zkontrolujte, jestli má uživatel platné ID uživatele cloudu:

    1.  Otevřete nástroj SQL Management Studio.

    2.  Připojte se k příslušné databázi.

    3.  Otevřete složku databází a vyberte a otevřete složku **CM_název_db**, kde název_db odpovídá názvu databáze zákazníka.

    4.  Nahoře zvolte **Nový dotaz** a spusťte tyto dotazy:

        -   Zobrazení všech uživatelů: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Pokud chcete zobrazit konkrétní uživatele, použijte tento dotaz, kde %testuser1% představuje adresu username@domain.com pro uživatele, kterého chcete vyhledat: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Po napsání dotazu zvolte **!Execute**.
        Když se vrátí výsledky, vyhledejte ID uživatele cloudu.  Pokud se žádné ID nenajde, nemá daný uživatel licenci pro používání služby Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Pokud název společnosti obsahuje speciální znaky, není možné vytvořit zásadu ani registrovat zařízení
**Problém:** Nemůžete vytvořit zásadu nebo zaregistrovat zařízení.

**Řešení:** V [Centru pro správu Office 365](https://portal.office.com/) odeberte zvláštní znaky z názvu společnosti a uložte informace o společnosti.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Pokud máte více ověřených domén, není možné se přihlásit nebo zaregistrovat zařízení
**Problém:** Pokud do AD FS přidáte druhou ověřenou doménu, nemusí být uživatelé s příponou hlavního názvu uživatele (UPN) druhé domény schopni se přihlásit na portály nebo zaregistrovat zařízení.


**Řešení:** Zákazníci, kteří mají předplatné Microsoft Office 365, využívají jednotné přihlašování (SSO) prostřednictvím služby AD FS 2.0 a mají pro přípony UPN uživatelů v rámci organizace více domén nejvyšší úrovně (třeba @contoso.com nebo @fabrikam.com)), musí pro každou příponu nasadit samostatnou instanci federační služby AD FS 2.0.  K dispozici je nyní [kumulativní aktualizace pro službu AD FS 2.0](http://support.microsoft.com/kb/2607496), která ve spojení s přepínačem **SupportMultipleDomain** umožňuje zajistit, aby AD FS server tento scénář podporoval bez vyžadování dalších serverů služby AD FS 2.0. Další informace najdete na [tomto blogu](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problémy na zařízeních s Androidem
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Zařízení se nepodařilo registrovat ve službě Intune a jeho stav v konzole pro správu se zobrazuje jako Není v pořádku
**Problém:** Některá zařízení Samsung s Androidem verze 4.4.x a 5.x můžou ukončit registraci ve službě Intune. Pokud se zařízení nezaregistrují, platí pro ně tyto podmínky:

- Nemůžou přijímat zásady, aplikace a vzdálené příkazy ze služby Intune.
- V konzole pro správu se jako stav správy zobrazuje **Není v pořádku**.
- Uživatelé chránění zásadami podmíněného přístupu můžou ztratit přístup k podnikovým prostředkům.

Společnost Samsung potvrdila, že software Samsung Smart Manager dodávaný s některými zařízeními Samsung může deaktivovat Portál společnosti Intune a jeho součásti. Když je Portál společnosti v neaktivním stavu, nemůže běžet na pozadí a v důsledku toho ani kontaktovat službu Intune.

**Řešení 1:**

Řekněte uživatelům, aby aplikaci Portál společnosti spouštěli ručně. Po restartování aplikace se zařízení zaregistruje pomocí služby Intune.

> [!IMPORTANT]
> Ruční spuštění aplikace Portál společnosti je dočasné řešení, protože Samsung Smart Manager může aplikaci Portál společnosti znovu deaktivovat.

**Řešení 2:**

Řekněte uživatelům, aby se pokusili upgradovat na Android 6.0. Problém s deaktivací neplatí pro zařízení s Androidem 6.0. Pokud chcete zkontrolovat, jestli je k dispozici aktualizace, můžete přejít na **Settings (Nastavení)** > **About device (O zařízení)** > **Download updates manually (Stáhnout aktualizace ručně)** a dále postupovat podle výzev zařízení.

**Řešení 3:**

Pokud řešení 2 nefunguje, nechte uživatele provést následující postup, aby Smart Manager vyloučil aplikaci Portál společnosti:

1. Na zařízení spusťte aplikaci Smart Manager.

  ![Výběr ikony Smart Manager na zařízení](./media/smart-manager-app-icon.png)

2. Zvolte dlaždici **Battery** (Baterie).

  ![Výběr dlaždice Battery](./media/smart-manager-battery-tile.png)

3. V části **App power saving** (Úspora energie aplikace) nebo **App optimization** (Optimalizace aplikace) vyberte **Detail** (Podrobnosti).

  ![Výběr možnosti Detail (Podrobnosti) v části App power saving (Úspora energie aplikace) nebo App optimization (Optimalizace aplikace)](./media/smart-manager-app-power-saving-detail.png)

4. V seznamu aplikací vyberte **Portál společnosti**.

  ![Výběr aplikace Portál společnosti ze seznamu aplikací](./media/smart-manager-company-portal.png)

5. Zvolte **Turned off** (Vypnuto).

  ![Výběr možnosti Turned off (Vypnuto) v dialogovém okně App optimization (Optimalizace aplikace)](./media/smart-manager-app-optimization-turned-off.png)

6. V části **App power saving** (Snížení spotřeby aplikace) nebo **App optimization** (Optimalizace aplikace) ověřte, že je Portál společnosti vypnutý.

  ![Ověření, že je Portál společnosti vypnutý](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Neúspěch instalace profilu
**Problém:** Na zařízení s Androidem se zobrazí chybová zpráva **Instalace profilu se nezdařila**.

**Řešení:**

1.  Zkontrolujte, jestli má uživatel přiřazenou příslušnou licenci pro verzi služby Intune, kterou používáte.

2.  Zkontrolujte, jestli už není zařízení zaregistrované pomocí jiného poskytovatele správy mobilních zařízení (MDM) a jestli už v něm není nainstalovaný profil správy.

3.  Potvrďte, že Chrome pro Android je výchozím prohlížečem a že jsou povolené soubory cookie.

### <a name="android-certificate-issues"></a>Problémy s certifikáty Androidu

**Problém:** Uživatelům se na zařízení zobrazí následující zpráva: *Nemůžete se přihlásit, protože vašemu zařízení chybí požadovaný certifikát.*

**Řešení 1**:

Požádejte uživatele, aby postupovali podle pokynů v článku [Zařízení nemá požadovaný certifikát](https://docs.microsoft.com/intune/enduser/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Pokud se chyba i potom stále zobrazuje, zkuste Řešení 2.

**Řešení 2**:

Pokud se uživatelům stále zobrazuje chyba chybějícího certifikátu po tom, co zadali své podnikové přihlašovací údaje a byli přesměrováni na federované přihlašování, možná na vašem serveru Active Directory Federation Services (AD FS) chybí zprostředkující certifikát.

K chybě certifikátu dochází proto, že zařízení s Androidem vyžadují, aby [zpráva Hello serveru SSL](https://technet.microsoft.com/library/cc783349.aspx) obsahovala zprostředkující certifikáty, ale výchozí instalace serveru AD FS nebo serveru proxy AD FS v současnosti odesílá ve zprávě Hello serveru SSL na zprávu Hello klienta SSL jenom certifikát SSL služby AD FS.

Pokud chcete problém vyřešit, naimportujte certifikáty do osobních certifikátů počítačů na serveru nebo proxy serverech AD FS následujícím způsobem:

1.    Na servery a proxy serverech AD FS spusťte konzolu Správa certifikátů pro místní počítač tak, že kliknete pravým tlačítkem na **Start**, vyberete **Spustit** a zadáte příkaz **certlm.msc**.
2.    Rozbalte **Osobní** a vyberte **Certifikáty**.
3.    Najděte certifikát pro vaši komunikaci služby AD FS (veřejně podepsaný certifikát) a poklikáním zobrazte jeho vlastnosti.
4.    Vyberte kartu **Cesta k certifikátu**, kde uvidíte nadřazené certifikáty certifikátu.
5.    U každého nadřazeného certifikátu vyberte **Zobrazit certifikát**.
6.    Vyberte kartu **Podrobnosti** a vyberte **Kopírovat do souboru**.
7.    Postupujte podle pokynů průvodce a vyexportujte nebo uložte veřejný klíč certifikátu do požadovaného umístění souborů.
8.    Naimportujte nadřazené certifikáty, které jste ve 3. kroku vyexportovali, do složky Místní počítač\Osobní\Certifikáty, a to tak, že pravým tlačítkem kliknete na **Certifikáty**, vyberete **Všechny úkoly** > **Importovat** a pak podle výzev průvodce certifikáty naimportujete.
9.    Restartujte servery AD FS.
10.    Výše uvedené kroky zopakujte na všech serverech a proxy serverech AD FS.
Teď už by měl uživatel být schopný se ze zařízení s Androidem k aplikaci Portál společnosti přihlásit.

**Pokud chcete ověřit, jestli se certifikát správně nainstaloval**:

Následující kroky popisují jednom jeden z mnoha způsobů a nástrojů, pomocí kterých můžete ověřit, jestli se certifikát správně nainstaloval.

1. Přejděte na [bezplatný nástroj Digicert](ttps://www.digicert.com/help/).
2. Zadejte plně kvalifikovaný název domény serveru AD FS (například sts.contoso.com) a vyberte **CHECK SERVER** (Zkontrolovat server).

Pokud je certifikát serveru správně nainstalovaný, uvidíte ve výsledcích všechny značky zaškrtnutí. Pokud výše popsaný problém přetrvává, zobrazí se v sekcích výsledné sestavy „Certificate name matches“ (Název certifikátu odpovídá) a „SSL Certificate is correctly Installed“ (Certifikát SSL je správně nainstalovaný) červený symbol X.


## <a name="ios-issues"></a>Problémy na zařízeních s iOSem

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Zařízení nejsou aktivní nebo s nimi nemůže konzola správce komunikovat
**Problém:** Zařízení s iOSem se neregistrují ve službě Intune. Zařízení se musí pravidelně registrovat ve službě, aby si zachovala přístup ke chráněným podnikovým prostředkům. Pokud se zařízení nezaregistrují, platí pro ně tyto podmínky:

- Nemůžou přijímat zásady, aplikace a vzdálené příkazy ze služby Intune.
- V konzole pro správu se jako stav správy zobrazuje **Není v pořádku**.
- Uživatelé chránění zásadami podmíněného přístupu můžou ztratit přístup k podnikovým prostředkům.

**Řešení:** Podělte se s koncovými uživateli o následující řešení, která jim pomůžou znovu získat přístup k podnikovým prostředkům.

Když uživatel spustí aplikaci Portál společnosti v iOSu, aplikace mu sdělí, jestli zařízení ztratilo kontakt s Intune. Pokud aplikace zjistí, že zařízení nemá kontakt, pokusí se automaticky synchronizovat s Intune a znovu se připojit. Uživateli se zobrazí vložené oznámení **Probíhá pokus o synchronizaci...** . 

  ![Oznámení Probíhá pokus o synchronizaci](./media/ios_cp_app_trying_to_sync_notification.png)

Pokud se synchronizace zdaří, zobrazí se v aplikaci Portál společnosti v iOSu vložené oznámení **Úspěšná synchronizace**, které označuje, že zařízení je v pořádku.

  ![Oznámení Úspěšná synchronizace](./media/ios_cp_app_sync_successful_notification.png)

Pokud se synchronizace nezdaří, uživatelům se v aplikaci Portál společnosti v iOSu zobrazí vložené oznámení **Nelze synchronizovat**. 

  ![Oznámení Nelze synchronizovat](./media/ios_cp_app_unable_to_sync_notification.png)

Pokud chcete problém opravit, musíte vybrat tlačítko **Nastavit**, které se nachází vpravo od oznámení **Nelze synchronizovat**. Po výběru tlačítka Nastavit se zobrazí obrazovka pro nastavení firemního přístupu, kde můžete podle zobrazovaných pokynů zaregistrovat zařízení. 

  ![Obrazovka Nastavení firemního přístupu](./media/ios_cp_app_company_access_setup.png)

Po registraci se zařízení vrátí do stavu správné funkce a znovu získá přístup k podnikovým prostředkům.

### <a name="profile-installation-failed"></a>Neúspěch instalace profilu
**Problém:** V zařízení s iOSem se zobrazí chyba **Instalace profilu se nezdařila**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Postup řešení potíží při neúspěšné instalaci profilu

1.  Zkontrolujte, jestli má uživatel přiřazenou příslušnou licenci pro verzi služby Intune, kterou používáte.

2.  Zkontrolujte, jestli už není zařízení zaregistrované pomocí jiného poskytovatele správy mobilních zařízení (MDM) a jestli už v něm není nainstalovaný profil správy.

3.  Přejděte na adresu [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) a po zobrazení výzvy se pokuste profil nainstalovat.

4.  Potvrďte nastavení výchozích prohlížečů Safari (pro iOS) a povolení souborů cookie.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Zaregistrovaná zařízení s iOSem se při používání nástroje System Center Configuration Manager se službou Intune nezobrazí v konzole
**Problém:** Uživatel registruje zařízení s iOSem, to se ale nezobrazí v konzole pro správu nástroje Configuration Manager. Zařízení neindikuje, že je zaregistrované. Možné příčiny:

- Je možné, že jste konektor služby Intune zaregistrovali na jednom účtu a potom jste ho zaregistrovali na jiném účtu.
- Mohli jste si stáhnout certifikát MDM z jednoho účtu a použít ho na jiný účet.


**Řešení:** Proveďte tyto kroky:

1. Zakažte iOS v rámci konektoru služby Windows Intune.
    1. Pravým tlačítkem klikněte na předplatné služby Intune a vyberte **Vlastnosti**.
    1. Na kartě iOS zrušte zaškrtnutí políčka Povolit registraci zařízení se systémem iOS.



2. V SQL spusťte následující kroky pro databázi CAS DB.

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
3. Restartujte službu SMS Executive nebo restartujte CM Server.

4. Získejte nový certifikát APN a nahrajte ho. To uděláte tak, že pravým tlačítkem kliknete na předplatné služby Intune v levém podokně nástroje Configuration Manager. Vyberte **Vytvořit žádost o certifikát APNs** a postupujte podle pokynů.
5. 
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problémy při použití nástroje System Center Configuration Manager se službou Intune

### <a name="mobile-devices-disappear"></a>Mobilní zařízení zmizí

**Problém:** Po úspěšné registraci mobilního zařízení do nástroje Configuration Manager dané zařízení zmizí z kolekce mobilních zařízení, ale pořád má profil pro správu a je uvedené v bráně CSS.

**Řešení:** K této situaci může dojít, pokud máte vlastní proces, který odebírá zařízení nepřipojená k doméně, nebo pokud uživatel vyřadil zařízení z předplatného. Pokud chcete ověřit a zkontrolovat, který proces nebo uživatelský účet odebral zařízení z konzoly nástroje Configuration Manager, zjistěte podle následujícího postupu, jak bylo zařízení odebrané.

1.  V konzole pro správu nástroje Configuration Manager vyberte **Monitorování** &gt; **Stav systému** &gt; **Dotazy stavových zpráv**.

2.  Klikněte pravým tlačítkem na **Manuálně odstraněné prostředky členů kolekce** a vyberte **Zobrazit zprávy**.

3.  Zvolte příslušný čas/datum nebo období posledních 12 hodin.

4.  Najděte příslušné zařízení a podívejte se, jak došlo k jeho odebrání. Následující příklad ukazuje, že zařízení odebral účet SCCMInstall prostřednictvím neznámé aplikace.

    ![Snímek obrazovky pro diagnostiku odstranění zařízení](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Zkontrolujte, jestli nemá Configuration Manager naplánovanou úlohu, skript nebo jiný proces, který by mohl automaticky odstraňovat zařízení nepřipojená k doméně, mobilní zařízení nebo související zařízení.




### <a name="other-ios-enrollment-errors"></a>Další chyby registrace zařízení s iOSem

Můžete si zobrazit seznam [chyb registrace zařízení s iOSem](https://docs.microsoft.com/intune/enduser/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios), na které může koncový uživatel narazit. Seznam poskytuje informace o chybových zprávách, které se mohou zobrazit koncovým uživatelům, a postupech, pomocí kterých můžete problémy vyřešit.

## <a name="pc--issues"></a>Potíže s počítačem

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>Počítač už je zaregistrovaný – chyba hr 0x8007064c
**Problém:** Registrace selže s chybou **Počítač už je zaregistrovaný**. V protokolu registrace se zobrazuje chyba **hr 0x8007064c**.

K této chybě může dojít v případě, že byl počítač zaregistrován již dříve nebo je na něm klonovaná image počítače, který už je zaregistrovaný. Na počítači se stále nachází certifikát předchozího účtu.

**Řešení:**

1.. V nabídce **Start** zadejte **Spustit** -> **MMC**.
1. Zvolte **Soubor** > **Přidat nebo odebrat moduly snap-in**.
1. Poklikejte na **Certifikáty**, zvolte **Účet počítače** > **Další** a vyberte **Místní počítač**.
1. Poklikejte na **Certifikáty (místní počítač)** a zvolte **Osobní/Certifikáty**.
1. Vyhledejte certifikát Intune, který vystavila certifikační autorita Sc_Online_Issuing. Pokud existuje, odstraňte ho.
1. Pokud existuje klíč registru **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**, odstraňte ho a s ním i všechny podklíče.
1. Zkuste se znovu zaregistrovat.
1. Pokud ani tak není možné počítač zaregistrovat, vyhledejte a odstraňte klíč **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**, pokud existuje.
1. Zkuste se znovu zaregistrovat.

    > [!IMPORTANT]
    > Tato část, metoda nebo úloha obsahují kroky, které vám pomohou s úpravou registru. Pokud ale budete měnit registr a uděláte tam něco špatně, můžete mít velké problémy s počítačem. Proto je důležité, abyste pečlivě postupovali podle těchto kroků. Než začnete registr měnit, pro jistotu si ho zazálohujte. Pak budete moct v případě problémů registr obnovit.
    > Další informace o tom, jak zálohovat a obnovovat registr najdete v tématu [Postup zálohování a obnovení registru v systému Windows](https://support.microsoft.com/en-us/kb/322756).

## <a name="general-enrollment-error-codes"></a>Obecné kódy chyb registrace

|Kód chyby|Možný problém|Navržené řešení|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |Na hodinách klientského počítače není nastavený správný čas.|Zkontrolujte, jestli jsou na klientském počítači správně nastavené hodiny a časové pásmo.|
|0x80240438, 0x80CF0438, 0x80CF402C|Nedá se připojit ke službě Intune. Zkontrolujte nastavení proxy serveru klienta.|Ověřte, že Intune konfiguraci proxy serveru na klientském počítači podporuje a že má klientský počítač přístup na internet.|
|0x80240438, 0x80CF0438|Není nakonfigurované nastavení proxy serveru v Internet Exploreru a v místním systému.|Nedá se připojit ke službě Intune. Zkontrolujte nastavení proxy serveru klienta a ověřte, že Intune konfiguraci proxy serveru na klientském počítači podporuje a že má klientský počítač přístup na internet.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Registrační balíček je zastaralý.|Z pracovního prostoru Správa si stáhněte aktuální balíček klientského softwaru a nainstalujte ho.|
|0x80043002, 0x80CF3002|Účet je v režimu údržby.|Když je účet v režimu údržby, nemůžete registrovat nové klientské počítače. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu.|
|0x80043003, 0x80CF3003|Účet je odstraněný.|Ověřte, že je váš účet a předplatné Intune pořád aktivní. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu.|
|0x80043005, 0x80CF3005|Klientský počítač byl vyřazen z provozu.|Pár hodin počkejte, odeberte z počítače všechny starší verze klientského softwaru s pak zkuste nainstalovat klientský software znova.|
|0x80043006, 0x80CF3006|Bylo dosaženo maximálního počtu licencí povolených pro účet.|Abyste mohli ve službě zaregistrovat víc klientských počítačů, musí si vaše organizace koupit další licence.|
|0x80043007, 0x80CF3007|Ve složce s instalačním programem se nenašel soubor certifikátu.|Než začnete s instalací, extrahujte všechny soubory. Žádné extrahované soubory nepřejmenovávejte ani nepřemísťujte: všechny soubory musí být ve stejné složce, jinak se instalace nepovede.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|Software nejde nainstalovat, protože se čeká na restartování klientského počítače.|Restartujte počítač a pak zkuste nainstalovat klientský software znova.|
|0x80070032|Na klientském počítači se nenašel nejmíň jeden softwarový produkt, který je podmínkou pro instalaci klientského softwaru.|Ujistěte se, že jsou na klientském počítači nainstalované všechny požadované aktualizace, a pak zkuste nainstalovat klientský software znova.|
|0x80043008, 0x80CF3008|Nepodařilo se spustit službu Microsoft Online Management Updates.|Kontaktujte podporu podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).|
|0x80043009, 0x80CF3009|Klientský počítač je ve službě už zaregistrovaný.|Abyste mohli klientský počítač ve službě zaregistrovat znovu, musíte ho nejdřív vyřadit.|
|0x8004300B, 0x80CF300B|Instalační balíček klientského softwaru nejde spustit, protože verze Windows, která běží na klientovi, není podporovaná.|Intune nepodporuje verzi Windows, která běží na klientském počítači.|
|0xAB2|Instalační služba systému Windows nemohla získat přístup k modulu VBScript runtime pro vlastní akci.|Tato chyba je způsobená nějakou vlastní akcí založenou na dynamických knihovnách DLL (Dynamic-Link Library). Při odstraňování problémů s knihovnou DLL budete nejspíš muset použít nástroje popsané v [článku&19803;8 znalostní báze podpory Microsoftu: Užitečné nástroje při problémech s balíčky a nasazením](https://support.microsoft.com/en-us/kb/198038).|
|0x80cf0440|Připojení ke koncovému bodu služby bylo ukončeno.|Zkušební nebo placený účet je pozastaven. Vytvořte nový zkušební nebo placený účet a pak opakujte pokus o registraci.|




### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

