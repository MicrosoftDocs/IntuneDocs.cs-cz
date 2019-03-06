---
title: Řešení potíží při registraci zařízení
description: Doporučení pro řešení potíží s registrací zařízení
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/09/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32f167def5e96061b0d69665c2c5b81a29d03389
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57461358"
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Řešení potíží s registrací do služby Intune

Tento článek obsahuje doporučení pro řešení potíží s registrací zařízení. Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md), ve kterém najdete další způsoby, jak získat nápovědu.


## <a name="initial-troubleshooting-steps"></a>První kroky při řešení potíží

Než začnete řešit potíže, ujistěte se, že jste správně nakonfigurovali Intune pro povolení registrace. Můžete si prostudovat informace o těchto požadavcích na konfiguraci:

-   [Příprava registrace zařízení v Microsoft Intune](setup-steps.md)
-   [Nastavení správy zařízení s iOSem a Mac OS](ios-enroll.md)
-   [Nastavení správy pro zařízení s Windows](windows-enroll.md)
-   [Nastavení správy zařízení s Androidem](android-enroll.md) – nejsou třeba žádné další kroky

Můžete také zkontrolovat správné nastavení času a data na zařízení uživatele:

1. Restartujte zařízení.
2. Zkontrolujte, že nastavení času a data se přibližně shoduje s časem GMT (interval -12 až +12 hodin vzhledem k času GMT, podle časového pásma koncového uživatele).
3. Odinstalujte a znovu nainstalujte Portál společnosti Intune (pokud se používá).

Uživatelé spravovaných zařízení můžou pro vaši potřebu shromažďovat protokoly registrace a diagnostiky. Pokyny pro uživatele ke shromažďování protokolů najdete tady:

- [Odeslání chyb registrace zařízení s Androidem správci IT](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Odeslání chyb zařízení s iOSem správci IT](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Obecné problémy s registrací
K těmto problémům může docházet na všech platformách zařízení.

### <a name="device-cap-reached"></a>Dosažení limitu zařízení
**Problém:** Uživatel obdrží chybu během registrace (jako je **portál společnosti dočasně nedostupný**) a protokol DMPdownloader.log v Configuration Manageru obsahuje chybu **DeviceCapReached**.

**Řešení:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Kontrola počtu zaregistrovaných a povolených zařízení

Podle následujícího postupu zkontrolujte, jestli nemá uživatel přiřazeno více zařízení, než je maximální povolený počet:

1. V Intune zvolte **Registrace zařízení** > **Omezení registrace** > **Omezení limitů počtů zařízení**. Poznamenejte si hodnotu uvedenou ve sloupci **Limit počtu zařízení**.

2. V Intune zvolte **Uživatelé** > **Všichni uživatelé** > vyberte požadovaného uživatele > **Zařízení**. Poznamenejte si počet zařízení.

3. Pokud počet zaregistrovaných zařízení uživatele se už rovná počtu uvedenému v omezení limitu počtu zařízení, nemůže si daný uživatel žádná další zařízení zaregistrovat, dokud:
    - [nebudou odebrána existující zařízení](devices-wipe.md), nebo
    - nezvýšíte limit počtu zařízení [nastavením omezení zařízení](enrollment-restrictions-set.md#set-device-limit-restrictions).

Pokud se chcete vyhnout dosažení limitu počtu zařízení, nezapomínejte odebírat zastaralá zařízení.

> [!NOTE]
> 
> Limitu registrace zařízení se můžete vyhnout tak, že použijete účet správce registrace zařízení, jak je popsáno v tématu [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](device-enrollment-manager-enroll.md).
> 
> Pokud se pro přihlašovací údaje uživatele, jehož účet přidáte do účtu správců registrace zařízení, vynucuje zásada podmíněného přístupu, nebude možné dokončit registraci.

### <a name="company-portal-temporarily-unavailable"></a>Portál společnosti není dočasně k dispozici
**Problém:** Uživatelé dostanou **portál společnosti dočasně nedostupný** na zařízení.

**Řešení:**

1.  Odeberte ze zařízení aplikaci Portál společnosti Intune.

2.  Otevřete na zařízení prohlížeč, přejděte na adresu [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) a pokuste se přihlásit uživatele.

3.  Pokud se uživateli nepodaří přihlásit se, měl by zkusit jinou síť.

4.  Pokud to nepomůže, zkontrolujte, jestli správně proběhla synchronizace přihlašovacích údajů uživatele se službou Azure Active Directory.

5.  Pokud se uživatel úspěšně přihlásí, zařízení se systémem iOS zobrazí výzvu k instalaci aplikace Portál společnosti Intune a k registraci. Na zařízení s Androidem budete muset aplikaci Portál společnosti Intune nainstalovat ručně. Potom se můžete zkusit znovu zaregistrovat.

### <a name="mdm-authority-not-defined"></a>Není definována autorita MDM
**Problém:** Uživatel obdrží **není definována autorita MDM** chyby.

**Řešení:**

1.  Ověřte, že je [správně nastavená](mdm-authority-set.md) autorita MDM.
    
2.  Ověřte, jestli synchronizace přihlašovacích údajů uživatele se službou Azure Active Directory proběhla správně. Můžete ověřit, že uživatele (UPN) odpovídá údajům služby Active Directory v Centru pro správu Microsoftu 365.
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

        -   Pokud chcete zobrazit konkrétní uživatele, použijte tento dotaz, kde %testuser1% zastupuje adresu username@domain.com pro uživatele, kterého chcete vyhledat: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Po napsání dotazu zvolte **!Execute**.
        Když se vrátí výsledky, vyhledejte ID uživatele cloudu.  Pokud se žádné ID nenajde, nemá daný uživatel licenci pro používání služby Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Pokud název společnosti obsahuje speciální znaky, není možné vytvořit zásadu ani registrovat zařízení
**Problém:** Nelze vytvořit zásadu ani registrovat zařízení.

**Řešení:** V [centra pro správu služeb Microsoft 365](https://admin.microsoft.com/), odeberte speciální znaky z názvu společnosti a uložte informace o společnosti.

### <a name="unable-to-sign-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Pokud máte více ověřených domén, není možné se přihlásit nebo zaregistrovat zařízení
**Problém:** Tomuto problému může dojít, pokud do AD FS přidáte druhou ověřenou doménu. Uživatelé s příponou hlavního názvu uživatele (UPN) druhé domény nemusí být schopni přihlásit se na portály nebo zaregistrovat zařízení.


<strong>Řešení:</strong> Zákazníci společnosti Microsoft Office 365 jsou nutné k nasazení samostatné instanci služby AD FS 2.0 federační služby pro každou příponu Pokud jsou:
- používají jednotné přihlašování (SSO) prostřednictvím služby AD FS 2.0 a
- mají pro přípony UPN uživatelů v rámci své organizace více domén nejvyšší úrovně (například @contoso.com nebo @fabrikam.com).


[Kumulativní aktualizace pro službu AD FS 2.0](http://support.microsoft.com/kb/2607496) ve spojení s přepínačem <strong>SupportMultipleDomain</strong> umožňuje zajistit, aby server AD FS podporoval tento scénář bez vyžadování dalších serverů služby AD FS 2.0. Další informace najdete v [tomto blogu](https://blogs.technet.microsoft.uucom/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problémy na zařízeních s Androidem

### <a name="android-enrollment-errors"></a>Chyby registrace zařízení s Androidem

Následující tabulka obsahuje chyby, které se můžou koncovým uživatelům zobrazit při registraci zařízení s Androidem v Intune.

|Chybová zpráva|Problém|Řešení|
|---|---|---|
|**Správce IT musí přiřadit licence pro přístup**<br>Váš správce IT vám neudělil přístup k této aplikaci. Požádejte ho o pomoc nebo to zkuste znovu později.|Zařízení není možné zaregistrovat, protože účet uživatele nemá potřebnou licenci.|Aby si mohli uživatelé zaregistrovat svoje zařízení, musí mít přiřazenou potřebnou licenci. Tato zpráva znamená, že uživatel má špatný typ licence pro danou autoritu pro správu mobilních zařízení. Uživatelům se tato chyba například zobrazí, pokud platí obě následující podmínky:<ol><li>Jako autorita pro správu mobilních zařízení je nastavená služba Intune.</li><li>Uživatel používá licenci nástroje System Center 2012 R2 Configuration Manager.</li></ol>Přečtěte si informace o tom, jak [přiřadit licence Intune k uživatelským účtům](/intune/licenses-assign).|
|**Správce IT musí nastavit autoritu MDM**<br>Zdá se, že váš správce IT nenastavil autoritu MDM. Požádejte ho o pomoc nebo to zkuste znovu později.|Autorita pro správu mobilních zařízení není definovaná.|Autorita pro správu mobilních zařízení není v Intune nastavená. Přečtěte si, jak [nastavit autoritu pro správu mobilních zařízení](/intune/mdm-authority-set).|


### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Zařízení se nepodařilo registrovat ve službě Intune a jeho stav v konzole pro správu se zobrazuje jako Není v pořádku
**Problém:** Některá zařízení Samsung, na kterých běží s Androidem verze 4.4.x a 5.x můžou ukončit registraci ve službě Intune zaregistrovat. Pokud se zařízení nezaregistrují, platí pro ně tyto podmínky:

- Nemůžou přijímat zásady, aplikace a vzdálené příkazy ze služby Intune.
- V konzole pro správu se jako stav správy zobrazuje **Není v pořádku**.
- Uživatelé chránění zásadami podmíněného přístupu můžou ztratit přístup k podnikovým prostředkům.

Software Samsung Smart Manager, který se dodává s některými zařízeními Samsung, může deaktivovat Portál společnosti Intune a jeho součásti. Když je Portál společnosti v neaktivním stavu, nemůže běžet na pozadí a nemůže kontaktovat službu Intune.

**Řešení 1:**

Řekněte uživatelům, aby aplikaci Portál společnosti spouštěli ručně. Po restartování aplikace se zařízení zaregistruje pomocí služby Intune.

> [!IMPORTANT]
> Ruční spuštění aplikace Portál společnosti je dočasné řešení, protože Samsung Smart Manager může aplikaci Portál společnosti znovu deaktivovat.

**Řešení 2:**

Řekněte uživatelům, aby se pokusili upgradovat na Android 6.0. Problém s deaktivací neplatí pro zařízení s Androidem 6.0. Pokud chcete zkontrolovat, jestli je k dispozici aktualizace, přejděte na **Settings (Nastavení)** > **About device (O zařízení)** > **Download updates manually (Stáhnout aktualizace ručně)** a dále postupujte podle pokynů.

**Řešení 3:**

Pokud řešení 2 nefunguje, nechte uživatele provést následující postup, aby Smart Manager vyloučil aplikaci Portál společnosti:

1. Na zařízení spusťte aplikaci Smart Manager.

   ![Výběr ikony Smart Manager na zařízení](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-icon.png)

2. Zvolte dlaždici **Battery** (Baterie).

   ![Výběr dlaždice Battery](./media/troubleshoot-device-enrollment-in-intune/smart-manager-battery-tile.png)

3. V části **App power saving** (Úspora energie aplikace) nebo **App optimization** (Optimalizace aplikace) vyberte **Detail** (Podrobnosti).

   ![Výběr možnosti Detail (Podrobnosti) v části App power saving (Úspora energie aplikace) nebo App optimization (Optimalizace aplikace)](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-power-saving-detail.png)

4. V seznamu aplikací vyberte **Portál společnosti**.

   ![Výběr aplikace Portál společnosti ze seznamu aplikací](./media/troubleshoot-device-enrollment-in-intune/smart-manager-company-portal.png)

5. Zvolte **Turned off** (Vypnuto).

   ![Výběr možnosti Turned off (Vypnuto) v dialogovém okně App optimization (Optimalizace aplikace)](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-optimization-turned-off.png)

6. V části **App power saving** (Snížení spotřeby aplikace) nebo **App optimization** (Optimalizace aplikace) ověřte, že je Portál společnosti vypnutý.

   ![Ověření, že je Portál společnosti vypnutý](./media/troubleshoot-device-enrollment-in-intune/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Neúspěch instalace profilu
**Problém:** Uživatel obdrží **instalace profilu se nezdařila** chyba na zařízení s Androidem.

**Řešení:**

1.  Zkontrolujte, jestli má uživatel přiřazenou příslušnou licenci pro verzi služby Intune, kterou používáte.

2.  Zkontrolujte, jestli už zařízení není zaregistrované pomocí jiného poskytovatele správy mobilních zařízení (MDM).

3. Zkontrolujte, jestli už v zařízení není nainstalovaný profil správy.

4.  Potvrďte, že Chrome pro Android je výchozím prohlížečem a že jsou povolené soubory cookie.

### <a name="android-certificate-issues"></a>Problémy s certifikáty Androidu

**Problém**: Uživatelé dostanou tuto zprávu na svém zařízení: *Nemůžete se přihlásit protože vašemu zařízení chybí požadovaný certifikát.*

**Řešení 1**:

Uživatel možná bude moct načíst chybějící certifikát podle pokynů v tématu [Zařízení nemá požadovaný certifikát](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Pokud chyba přetrvává, vyzkoušejte Řešení 2.

**Řešení 2**:

Uživatelům se může po tom, co zadali svoje podnikové přihlašovací údaje a byli přesměrováni na federované přihlašování, nadále zobrazovat chyba chybějícího certifikátu. V tom případě může tato chyba znamenat, že na vašem serveru Active Directory Federation Services (AD FS) chybí zprostředkující certifikát.

Příčinou chyby certifikátu je, že zařízení s Androidem vyžadují zahrnutí zprostředkujících certifikátů do odpovědi [SSL Server hello](https://technet.microsoft.com/library/cc783349.aspx). Momentálně výchozí instalace serveru AD FS nebo proxy serveru WAP – AD FS odesílá v odpovědi SSL Server hello na zprávu SSL Client hello jenom certifikát SSL služby AD FS.

Pokud chcete problém vyřešit, naimportujte certifikáty do osobních certifikátů počítačů na serveru nebo proxy serverech AD FS následujícím způsobem:

1.  Na serveru ADFS a proxy serveru klikněte pravým tlačítkem myši na **Start** > **Spustit** > **certlm.msc** a spusťte konzolu pro správu certifikátů místního počítače.
2.  Rozbalte **Osobní** a zvolte **Certifikáty**.
3.  Najděte certifikát pro vaši komunikaci služby AD FS (veřejně podepsaný certifikát) a poklikáním zobrazte jeho vlastnosti.
4.  Zvolte kartu **Cesta k certifikátu**, kde uvidíte nadřazené certifikáty certifikátu.
5.  U každého nadřazeného certifikátu zvolte **Zobrazit certifikát**.
6.  Zvolte **Podrobnosti** > **Kopírovat do souboru**.
7.  Postupujte podle pokynů průvodce a vyexportujte nebo uložte veřejný klíč nadřazeného certifikátu do umístění souborů podle vlastního výběru.
8.  Klikněte pravým tlačítkem myši na **Certifikáty** > **Všechny úkoly** > **Importovat**.
9.  Postupujte podle pokynů průvodce a naimportujte nadřazené certifikáty do **Místní počítač\Osobní\Certifikáty**.
10. Restartujte servery AD FS.
11. Výše uvedené kroky zopakujte na všech serverech a proxy serverech AD FS.

K ověření správné instalace certifikátu můžete použít diagnostický nástroj, který je dostupný na [https://www.digicert.com/help/](https://www.digicert.com/help/). Do pole **Server Address** (Adresa serveru) zadejte plně kvalifikovaný název domény serveru AD FS (například sts.contso.com) a klikněte na **Check Server** (Zkontrolovat server).

**Pokud chcete ověřit, jestli se certifikát správně nainstaloval**:

Následující kroky popisují jednom jeden z mnoha způsobů a nástrojů, pomocí kterých můžete ověřit, jestli se certifikát správně nainstaloval.

1. Přejděte na [bezplatný nástroj Digicert](ttps://www.digicert.com/help/).
2. Zadejte plně kvalifikovaný název domény serveru AD FS (například sts.contoso.com) a vyberte **CHECK SERVER** (Zkontrolovat server).

Pokud je certifikát serveru správně nainstalovaný, uvidíte ve výsledcích všechny značky zaškrtnutí. Pokud výše popsaný problém přetrvává, zobrazí se v sekcích výsledné sestavy „Certificate name matches“ (Název certifikátu odpovídá) a „SSL Certificate is correctly Installed“ (Certifikát SSL je správně nainstalovaný) červený symbol X.


## <a name="ios-issues"></a>Problémy na zařízeních s iOSem

### <a name="ios-enrollment-errors"></a>Chyby registrace zařízení se systémem iOS
Následující tabulka obsahuje chyby, které se můžou koncovým uživatelům zobrazit při registraci zařízení s iOsem v Intune.

|Chybová zpráva|Problém|Řešení|
|-------------|-----|----------|
|NoEnrollmentPolicy|Nepovedlo se najít žádné zásady registrace|Zkontrolujte, že jsou nastavené všechny požadavky registrace, například certifikát služby APNs (Apple Push Notification Service), a že je povolené nastavení „iOS jako platforma“. Pokyny najdete v tématu [Nastavení správy zařízení s iOSem a MacOS](ios-enroll.md).|
|DeviceCapReached|Už máte příliš mnoho registrovaných mobilních zařízení.|Než bude moct uživatel zaregistrovat další mobilní zařízení, musí odebrat jedno ze svých aktuálně zaregistrovaných mobilních zařízení z Portálu společnosti. Přečtěte si pokyny pro typ zařízení, které používáte: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios), [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Došlo k potížím s certifikátem, který umožňuje komunikaci mobilního zařízení s podnikovou sítí.<br /><br />|Služba APNs (Apple Push Notification Service) poskytuje kanál pro kontakt se zaregistrovanými zařízeními s iOSem. Registrace bude neúspěšná a zobrazí se tato zpráva, pokud:<ul><li>kroky k získání certifikátu APNs nebyly provedeny, nebo</li><li>platnost certifikátu APNs vypršela.</li></ul>Přečtěte si informace o nastavení uživatelů v tématu [Synchronizace služby Active Directory a přidání uživatelů do Intune](users-add.md) a článku o [uspořádání uživatelů a zařízení](groups-add.md).|
|AccountNotOnboarded|Došlo k potížím s certifikátem, který umožňuje komunikaci mobilního zařízení s podnikovou sítí.<br /><br />|Služba APNs (Apple Push Notification Service) poskytuje kanál pro kontakt se zaregistrovanými zařízeními s iOSem. Registrace bude neúspěšná a zobrazí se tato zpráva, pokud:<ul><li>kroky k získání certifikátu APNs nebyly provedeny, nebo</li><li>platnost certifikátu APNs vypršela.</li></ul>Další informace najdete v tématu [Nastavení správy iOS a Mac s Microsoft Intune](ios-enroll.md).|
|DeviceTypeNotSupported|Uživatel se možná pokusil o registraci zařízení s jiným systémem než iOS. Typ mobilního zařízení, které se pokoušíte registrovat, není podporovaný.<br /><br />Potvrďte, že na zařízení běží systém iOS verze 8.0 nebo novější.<br /><br />|Zkontrolujte, jestli na zařízení uživatele běží systém iOS verze 8.0 nebo novější.|
|UserLicenseTypeInvalid|Zařízení nemůžete zaregistrovat, protože uživatelský účet ještě není členem požadované skupiny uživatelů.<br /><br />|Uživatelé můžou svoje zařízení registrovat až potom, co se stanou členy správné skupiny uživatelů. Tato zpráva znamená, že uživatel má špatný typ licence pro danou autoritu pro správu mobilních zařízení. Uživatelům se tato chyba například zobrazí, pokud platí obě následující podmínky:<ol><li>Jako autorita pro správu mobilních zařízení je nastavená služba Intune.</li><li>Uživatel používá licenci nástroje System Center 2012 R2 Configuration Manager.</li></ol>Další informace najdete v následujících článcích:<br /><br />Přečtěte si článek [Nastavení správy iOS a Mac pomocí Microsoft Intune](ios-enroll.md) a informace, jak nastavit uživatele, v článku [Synchronizace služby Active Directory a přidání uživatelů do Intune](users-add.md) a článku o [uspořádání uživatelů a zařízení](groups-add.md).|
|MdmAuthorityNotDefined|Autorita pro správu mobilních zařízení není definovaná.<br /><br />|Autorita pro správu mobilních zařízení není v Intune nastavená.<br /><br />Projděte si položku #1 v "krok 6: V části registrace mobilních zařízení a instalace aplikace" [Začínáme s 30denní zkušební verzí Microsoft Intune](free-trial-sign-up.md).|

### <a name="devices-are-inactive-or-the-admin-console-cant-communicate-with-them"></a>Zařízení nejsou aktivní nebo s nimi nemůže konzola správce komunikovat
**Problém:** Zařízení s iOSem se neregistrují ve službě Intune. Zařízení se musí pravidelně registrovat ve službě, aby si zachovala přístup ke chráněným podnikovým prostředkům. Pokud se zařízení nezaregistrují, platí pro ně tyto podmínky:

- Nemůžou přijímat zásady, aplikace a vzdálené příkazy ze služby Intune.
- V konzole pro správu se jako stav správy zobrazuje **Není v pořádku**.
- Uživatelé chránění zásadami podmíněného přístupu můžou ztratit přístup k podnikovým prostředkům.

**Řešení:** Následující řešení sdílejte s koncovými uživateli k jim pomůžou znovu získat přístup k firemním prostředkům.

Když uživatel spustí aplikaci Portál společnosti v iOSu, aplikace mu sdělí, jestli zařízení ztratilo kontakt s Intune. Pokud aplikace zjistí, že zařízení nemá kontakt, pokusí se automaticky synchronizovat s Intune a znovu se připojit (uživateli se zobrazí zpráva **Probíhá pokus o synchronizaci...**). ).

  ![Oznámení Probíhá pokus o synchronizaci](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_trying_to_sync_notification.png)

Pokud se synchronizace zdaří, zobrazí se v aplikaci Portál společnosti v iOSu vložené oznámení **Úspěšná synchronizace**, které označuje, že zařízení je v pořádku.

  ![Oznámení Úspěšná synchronizace](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_sync_successful_notification.png)

Pokud se synchronizace nezdaří, uživatelům se v aplikaci Portál společnosti v iOSu zobrazí vložené oznámení **Nelze synchronizovat**.

  ![Oznámení Nelze synchronizovat](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_unable_to_sync_notification.png)

Pokud chcete problém opravit, musíte vybrat tlačítko **Nastavit**, které se nachází vpravo od oznámení **Nelze synchronizovat**. Po výběru tlačítka Nastavit se zobrazí obrazovka pro nastavení firemního přístupu, kde můžete podle zobrazovaných pokynů zaregistrovat zařízení.

  ![Obrazovka Nastavení firemního přístupu](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_company_access_setup.png)

Po registraci se zařízení vrátí do stavu správné funkce a znovu získá přístup k podnikovým prostředkům.

### <a name="verify-ws-trust-13-is-enabled"></a>Ověření, že koncový bod WS-Trust 1.3 je povolený
**Problém:** Zařízení s iOSem a programem registrace zařízení (DEP) není možné zaregistrovat.

Registrace zařízení s programem DEP s přidružením uživatele vyžaduje aktivaci koncového bodu WS-Trust 1.3 Username/Mixed, aby bylo možné požádat o token uživatele. Active Directory má tento koncový bod ve výchozím nastavení povolený. Seznam povolených koncových bodů získáte použitím rutiny PowerShellu Get-AdfsEndpoint a vyhledáním koncového bodu trust/13/UsernameMixed. Příklad:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Další informace najdete v [dokumentaci k rutině Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

Další informace najdete v tématu [Doporučené postupy zabezpečení služby AD FS](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs). Získání pomoci při určování, jestli máte koncový bod WS-Trust 1.3 Username/Mixed ve svém zprostředkovateli identity federace povolený:
- Pokud používáte službu ADFS, obraťte se na podporu Microsoftu.
- Obraťte se na poskytovatele identity třetí strany.


### <a name="profile-installation-failed"></a>Neúspěch instalace profilu
**Problém:** Uživatel obdrží **instalace profilu se nezdařila** chyba na zařízení s Iosem.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Postup řešení potíží při neúspěšné instalaci profilu

1.  Zkontrolujte, jestli má uživatel přiřazenou příslušnou licenci pro verzi služby Intune, kterou používáte.

2.  Zkontrolujte, jestli už zařízení není zaregistrované pomocí jiného poskytovatele správy mobilních zařízení (MDM).

3. Zkontrolujte, jestli už v zařízení není nainstalovaný profil správy.

4.  Přejděte na [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) a po zobrazení výzvy zkuste profil nainstalovat.

5.  Potvrďte nastavení výchozích prohlížečů Safari (pro iOS) a povolení souborů cookie.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Zaregistrovaná zařízení s iOSem se při používání nástroje System Center Configuration Manager se službou Intune nezobrazí v konzole
**Problém:** Uživatel registruje zařízení s Iosem ale nezobrazí v konzole pro správu nástroje Configuration Manager. Zařízení neindikuje, že je zaregistrované. Možné příčiny:

- Konektor služby Microsoft Intune v lokalitě nástroje Configuration Manager nekomunikuje se službou Intune.
- Součást Data Discovery Manager (ddm) nebo State Manager (statmgr) nezpracovává zprávy ze služby Intune.
- Mohli jste si stáhnout certifikát MDM z jednoho účtu a použít ho na jiný účet.


**Řešení:** Zkontrolujte možné chyby následující soubory protokolu:

- dmpdownloader.log
- ddm.log
- statmgr.log

Příklady toho, co máte v těchto souborech protokolu hledat, budou brzy přidány.


### <a name="users-ios-device-is-stuck-on-an-enrollment-screen-for-more-than-10-minutes"></a>Uživatelské zařízení s iOSem uvízlo na obrazovce registrace po dobu více než 10 minut

**Problém**: Registrace zařízení můžou uváznout ve buď dvě obrazovky:
- Čekání na finální konfiguraci ze zdroje „Microsoft“
- Aplikace Asistovaný přístup není k dispozici. Kontaktujte správce.

Tento problém může nastat, když:
- dojde k dočasnému výpadku služeb Apple, nebo
- registrace pro iOS je nastavená tak, aby se použily tokeny VPP, jak je uvedeno v tabulce, ale s tokenem VPP je něco v nepořádku.

| Nastavení registrace | Hodnota |
| ---- | ---- |
| Platforma | iOS |
| Spřažení uživatele | Zaregistrovat s přidružením uživatele |
|Ověřit na Portálu společnosti místo v Průvodci nastavením Applu | Ano |
| Nainstalovat Portál společnosti pomocí VPP | Použít token: adresa tokenu |
| Spustit Portál společnosti v režimu Jedna aplikace, dokud neproběhne ověření | Ano |

**Rozlišení**: Pokud chcete problém vyřešit, musíte:
1. Určení, jestli je s tokenem VPP něco v nepořádku, a případná oprava tokenu VPP
2. Identifikace zařízení, která jsou blokovaná
3. Vymazání ovlivněných zařízení
4. Předání pokynu uživateli, aby proces registrace znovu zahájil

#### <a name="determine-if-theres-something-wrong-with-the-vpp-token"></a>Určení, jestli je s tokenem VPP něco v nepořádku
1. Přejděte na **Intune** > **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > název tokenu > **Profily** > název profilu > **Spravovat** > **Vlastnosti**.
2. Zkontrolujte vlastnosti, abyste zjistili, jestli se zobrazují nějaké chyby, které se podobají těmto:
    - Platnost tohoto tokenu vypršela.
    - Na tento token se nevztahují licence pro Portál společnosti.
    - Tento token používá jiná služba.
    - Tento token používá jiný tenant.
    - Tento token se odstranil.
3. Odstraňte problémy s tokenem.

#### <a name="identify-which-devices-are-blocked-by-the-vpp-token"></a>Identifikace zařízení, která token VPP blokuje
1. Přejděte na **Intune** > **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > název tokenu > **Zařízení**.
2. Vyfiltrujte sloupec **Stav profilu** podle hodnoty **Blokováno**.
3. Poznamenejte si sériová čísla všech zařízení s hodnotou **Blokováno**.

#### <a name="remotely-wipe-the-blocked-devices"></a>Vzdálené vymazání blokovaných zařízení
Po odstranění problémů s tokenem VPP je nutné vymazat zařízení, která jsou blokovaná.
1. Přejděte na **Intune** > **Zařízení** > **Všechna zařízení** > **Sloupce** > **Sériové číslo** > **Použít**. 
2. Každé blokované zařízení vyberte v seznamu **Všechna zařízení** a zvolte **Vymazání** > **Ano**.

#### <a name="tell-the-users-to-restart-the-enrollment-process"></a>Předání pokynu uživatelům, aby proces registrace znovu zahájili
Po vymazání blokovaných zařízení můžete uživatelům předat pokyn, aby proces registrace znovu zahájili.

## <a name="macos-issues"></a>Problémy s macOS

### <a name="macos-enrollment-errors"></a>Chyby registrace zařízení s macOS
**Chybová zpráva 1:** *Zdá se, že používáte virtuální počítač. Ověřte, že je virtuální počítač plně nakonfigurovaný, a to včetně sériového čísla a modelu hardwaru. Pokud nejde o virtuální počítač, kontaktujte prosím podporu.*  

**Chybová zpráva 2:** *Došlo k potížím při přidávání zařízení do správy. Tento problém může být způsobený tím, že používáte virtuální počítač, máte zakázané sériové číslo nebo toto zařízení už je přiřazené k někomu jinému. Zjistěte, jak tyto problémy můžete vyřešit, nebo se obraťte na firemní podporu.*

**Problém:** Tato zpráva může být výsledkem některého z následujících důvodů:  
* Virtuální počítač s macOS není správně nakonfigurovaný.  
* Povolili jste omezení zařízení, která vyžadují, aby zařízení bylo ve firemním vlastnictví nebo mělo v Intune zaregistrované sériové číslo.  
* Zařízení už je zaregistrované a je v Intune pořád přiřazené k někomu jinému.  

**Řešení:** Nejprve obraťte se na vaše uživatele a zjistí problémy, které má vliv na jejich zařízení. Pak proveďte nejvhodnější z následujících řešení:
* Pokud uživatel registruje virtuální počítač kvůli testování, ověřte, že je plně nakonfigurovaný, aby služba Intune dokázala rozpoznat jeho sériové číslo a model hardwaru. Přečtěte si další informace o tom, jak v Intune [nastavit virtuální počítače](macos-enroll.md#enroll-virtual-macos-machines-for-testing).  
* Pokud má vaše organizace zapnuté omezení registrace, které blokuje osobní zařízení s macOS, musíte do Intune ručně [přidat sériové číslo osobního zařízení](corporate-identifiers-add.md#manually-enter-corporate-identifiers).  
* Pokud je zařízení v Intune pořád přiřazené k jinému uživateli, nepoužil jeho předchozí vlastník aplikaci Portál společnosti, aby ho odebral nebo obnovil tovární nastavení. Záznam zastaralého zařízení vyčistíte v Intune takto:  

    1. Přejděte na [Intune na webu Azure Portal](https://portal.manage.microsoft.com) a přihlaste se pomocí přihlašovacích údajů správce.
    2. Přejděte na Intune > **Zařízení** > **Všechna zařízení**.  
    3. Najděte zařízení s problematickou registrací. Výsledky můžete upřesnit hledáním podle názvu zařízení nebo adresy MAC/hardwaru.
    4. Vyberte toto zařízení > **Odstranit**. Odstraňte všechny ostatní záznamy spojené s tímto zařízením.  

## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problémy při použití nástroje System Center Configuration Manager se službou Intune
### <a name="mobile-devices-disappear"></a>Mobilní zařízení zmizí
**Problém:** Po úspěšné registraci mobilního zařízení do Configuration Manageru, dané zařízení zmizí z kolekce mobilních zařízení. Dané zařízení ale pořád má profil pro správu a je uvedené v bráně CSS.

**Řešení:** Tomuto problému může dojít, protože:
- máte vlastní proces, který odebírá zařízení nepřipojená k doméně, nebo 
- uživatel vyřadil zařízení z předplatného.
Pokud chcete ověřit a zkontrolovat, který proces nebo uživatelský účet odebral zařízení z konzoly nástroje Configuration Manager, postupujte podle následujících kroků.

#### <a name="check-how-device-was-removed"></a>Zjištění způsobu odebrání zařízení

1.  V konzole pro správu nástroje Configuration Manager vyberte **Monitorování** &gt; **Stav systému** &gt; **Dotazy stavových zpráv**.

2.  Klikněte pravým tlačítkem na **Manuálně odstraněné prostředky členů kolekce** a vyberte **Zobrazit zprávy**.

3.  Vyberte příslušný čas/datum nebo období posledních 12 hodin.

4.  Najděte příslušné zařízení a podívejte se, jak došlo k jeho odebrání. Následující příklad ukazuje, že zařízení odebral účet SCCMInstall prostřednictvím neznámé aplikace.

    ![Snímek obrazovky pro diagnostiku odstranění zařízení](./media/troubleshoot-device-enrollment-in-intune/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Zkontrolujte, jestli nemá Configuration Manager naplánovanou úlohu, skript nebo jiný proces, který by mohl automaticky odstraňovat zařízení nepřipojená k doméně, mobilní zařízení nebo související zařízení.

### <a name="other-ios-enrollment-errors"></a>Další chyby registrace zařízení s iOSem
Seznam chyb registrace zařízení s iOSem najdete v dokumentaci v části [Řešení potíží s registrací zařízení s iOSem v Microsoft Intune](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune).

## <a name="pc-issues"></a>Problémy na počítači

|Chybová zpráva|Problém|Řešení|
|---|---|---|
|**Správce IT musí přiřadit licence pro přístup**<br>Váš správce IT vám neudělil přístup k této aplikaci. Požádejte ho o pomoc nebo to zkuste znovu později.|Zařízení není možné zaregistrovat, protože účet uživatele nemá potřebnou licenci.|Aby si mohli uživatelé zaregistrovat svoje zařízení, musí mít přiřazenou potřebnou licenci. Tato zpráva znamená, že uživatel má špatný typ licence pro danou autoritu pro správu mobilních zařízení. Uživatelům se tato chyba například zobrazí, pokud platí obě následující podmínky: <ol><li>Jako autorita pro správu mobilních zařízení je nastavená služba Intune.</li><li>Uživatel používá licenci nástroje System Center 2012 R2 Configuration Manager.</li></ol>Přečtěte si informace o tom, jak [přiřadit licence Intune k uživatelským účtům](https://docs.microsoft.com/intune/licenses-assign).|



### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>Počítač už je zaregistrovaný – chyba hr 0x8007064c
**Problém:** Registrace selže s chybou **počítač je už zaregistrovaný**. V protokolu registrace se zobrazuje chyba **hr 0x8007064c**.

Důvodem může být to, že počítač:
- byl zaregistrován dříve, nebo
- je na něm klonovaná image počítače, který už je zaregistrovaný.
Na počítači se stále nachází certifikát předchozího účtu.

**Řešení:**

1. V nabídce **Start** zadejte **Spustit** -> **MMC**.
1. Zvolte **Soubor** > **Přidat nebo odebrat moduly snap-in**.
1. Poklikejte na **Certifikáty**, zvolte **Účet počítače** > **Další** a vyberte **Místní počítač**.
1. Poklikejte na **Certifikáty (místní počítač)** a zvolte **Osobní/Certifikáty**.
1. Vyhledejte certifikát Intune, který vystavila certifikační autorita Sc_Online_Issuing. Pokud existuje, odstraňte ho.
1. Pokud následující klíč registru existuje, odstraňte ho: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** a všechny.
1. Zkuste se znovu zaregistrovat.
1. Pokud počítač zaregistrovat, vyhledejte a odstraňte tento klíč, pokud existuje: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Zkuste se znovu zaregistrovat.

    > [!IMPORTANT]
    > Tato část, metoda nebo úloha obsahují kroky, které vám pomohou s úpravou registru. Pokud ale budete měnit registr a uděláte tam něco špatně, můžete mít velké problémy s počítačem. Proto je důležité, abyste pečlivě postupovali podle těchto kroků. Než začnete registr měnit, pro jistotu si ho zazálohujte. Pak budete moct v případě problémů registr obnovit.
    > Další informace o tom, jak zálohovat a obnovovat registr, najdete v tématu [Postup zálohování a obnovení registru v systému Windows](https://support.microsoft.com/kb/322756).

## <a name="general-enrollment-error-codes"></a>Obecné kódy chyb registrace

|Kód chyby|Možný problém|Navržené řešení|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |Na hodinách klientského počítače není nastavený správný čas.|Zkontrolujte, jestli jsou na klientském počítači správně nastavené hodiny a časové pásmo.|
|0x80240438, 0x80CF0438, 0x80CF402C|Nedá se připojit ke službě Intune. Zkontrolujte nastavení proxy serveru klienta.|Ověřte, že Intune podporuje konfiguraci proxy serveru na klientském počítači. Ověřte, že klientský počítač má přístup na internet.|
|0x80240438, 0x80CF0438|Není nakonfigurované nastavení proxy serveru v Internet Exploreru a v místním systému.|Nedá se připojit ke službě Intune. Zkontrolujte nastavení proxy serveru klienta. Ověřte, že Intune podporuje konfiguraci proxy serveru na klientském počítači. Ověřte, že klientský počítač má přístup na internet.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Registrační balíček je zastaralý.|Z pracovního prostoru Správa si stáhněte aktuální balíček klientského softwaru a nainstalujte ho.|
|0x80043002, 0x80CF3002|Účet je v režimu údržby.|Když je účet v režimu údržby, nemůžete registrovat nové klientské počítače. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu.|
|0x80043003, 0x80CF3003|Účet je odstraněný.|Ověřte, že je váš účet a předplatné Intune pořád aktivní. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu.|
|0x80043005, 0x80CF3005|Klientský počítač byl vyřazen z provozu.|Pár hodin počkejte, odeberte z počítače všechny starší verze klientského softwaru s pak zkuste nainstalovat klientský software znova.|
|0x80043006, 0x80CF3006|Bylo dosaženo maximálního počtu licencí povolených pro účet.|Abyste mohli ve službě zaregistrovat další klientské počítače, musí si vaše organizace koupit další licence.|
|0x80043007, 0x80CF3007|Ve složce s instalačním programem se nenašel soubor certifikátu.|Než začnete s instalací, extrahujte všechny soubory. Extrahované soubory nepřejmenovávejte ani nepřesunujte: všechny soubory musí být ve stejné složce, jinak se instalace nepovede.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|Software nejde nainstalovat, protože se čeká na restartování klientského počítače.|Restartujte počítač a pak zkuste nainstalovat klientský software znova.|
|0x80070032|Na klientském počítači se nenašel minimálně jeden softwarový produkt, který je podmínkou pro instalaci klientského softwaru.|Ujistěte se, že jsou na klientském počítači nainstalované všechny požadované aktualizace, a pak zkuste nainstalovat klientský software znova.|
|0x80043008, 0x80CF3008|Nepodařilo se spustit službu Microsoft Online Management Updates.|Kontaktujte podporu podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](get-support.md).|
|0x80043009, 0x80CF3009|Klientský počítač je ve službě už zaregistrovaný.|Abyste mohli klientský počítač ve službě zaregistrovat znovu, musíte ho nejdřív vyřadit.|
|0x8004300B, 0x80CF300B|Instalační balíček klientského softwaru nejde spustit, protože verze Windows, která běží na klientovi, není podporovaná.|Intune nepodporuje verzi Windows, která běží na klientském počítači.|
|0xAB2|Instalační služba systému Windows nemohla získat přístup k modulu VBScript runtime pro vlastní akci.|Tato chyba je způsobená nějakou vlastní akcí založenou na dynamických knihovnách DLL (Dynamic-Link Library). Při řešení potíží s knihovny DLL, budete nejspíš muset použít nástroje, které jsou popsány v [kb198038 odborné pomoci společnosti Microsoft: Užitečné nástroje při problémech nasazení a balíček](https://support.microsoft.com/kb/198038).|
|0x80cf0440|Připojení ke koncovému bodu služby bylo ukončeno.|Zkušební nebo placený účet je pozastaven. Vytvořte nový zkušební nebo placený účet a pak opakujte pokus o registraci.|




### <a name="next-steps"></a>Další postup
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](get-support.md).
