---
title: "Správa Apple DEP pro zařízení s iOSem | Dokumentace Microsoftu"
description: "Nasaďte registrační profil, který umožňuje bezdrátovou registraci zařízení s iOSem koupených prostřednictvím programu DEP (Device Enrollment Program) pro zařízení s iOSem, aby bylo možné je spravovat."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d5facd519f53ea8534445ad95ae9221cf537b50a
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>Registrace zařízení s iOSem vlastněných společností do programu DEP (Device Enrollment Program)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune umožňuje nasadit registrační profil, který bezdrátově zaregistruje zařízení s iOSem zakoupená prostřednictvím programu DEP (Device Enrollment Program). Registrační balíček může zahrnovat možnosti Pomocníka s nastavením pro zařízení.

>[!NOTE]
>Registrace DEP se nedá použít s metodou [správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
>Pokud navíc uživatelé registrují zařízení s iOSem (pomocí aplikace Portál společnosti) a sériová čísla těchto zařízení se pak naimportují a přiřadí k profilu DEP, zruší se tím registrace zařízení v Intune.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a>Předpoklady pro registraci zařízení s iOSem pomocí správy programu Apple DEP

- [Nainstalujte certifikát služby APN](set-up-ios-and-mac-management-with-microsoft-intune.md).

- Vaše organizace se musí připojit k programu Apple DEP a získat zařízení prostřednictvím tohoto programu. Podrobnosti o tomto procesu najdete na [https://deploy.apple.com](https://deploy.apple.com). Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

- Abyste mohli v programu DEP registrovat zařízení s iOSem vlastněná společností, potřebujete od společnosti Apple token DEP. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token taky umožňuje Intune odesílat společnosti Apple registrační profil a přiřazovat k těmto profilům zařízení.

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a>Postup při registraci zařízení s iOSem pomocí správy programu Apple DEP

Následující postup vysvětluje, jak zaregistrovat zařízení s iOSem hned od začátku pomocí správy programu Apple DEP. Když se zařízení přidávají nebo odebírají z organizace, budete asi některé z těchto kroků opakovat, například přidávání nebo odebírání sériových čísel, jak je popsáno níže.

### <a name="get-an-encryption-key"></a>Získání šifrovacího klíče

1. Přihlaste se jako správce a otevřete [konzolu pro správu Microsoft Intune](https://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a zvolte **Stáhnout šifrovací klíč**.

2. Uložte soubor šifrovacího klíče (.pem) místně. Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

![Aktualizace tokenu DEP (Device Enrollment Program)](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a>Získání tokenu DEP (Device Enrollment Program)

1. Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pod firemním Apple ID. Toto Apple ID budete muset později použít k obnovení tokenu DEP.

2.  Na portálu programu DEP (Device Enrollment Program) přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a pak zvolte **Přidat server MDM**.

3.  Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

4.  Otevře se dialog **Přidat server &lt;název_serveru&gt;**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

5.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.

   Soubor certifikátu (.p7m) se používá k navázání vztahu důvěryhodnosti mezi serverem Intune a serverem programu DEP (Device Enrollment Program) společnosti Apple.

### <a name="add-the-dep-token-to-intune"></a>Přidání tokenu DEP do Intune

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Správce** &gt; **Správa mobilního zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)**.

2. Zvolte **Nahrát token DEP**. **Vyhledejte** soubor certifikátu (.p7m), zadejte své **Apple ID** a zvolte **Nahrát**.

### <a name="add-the-corporate-device-enrollment-policy"></a>Přidání zásad registrace podnikových zařízení

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a zvolte **Přidat**.

2. Zadejte **obecné** podrobnosti, jako je **Název** a **Popis**, a určete, jestli zařízení přiřazená k profilu mají přidruženého uživatele nebo patří skupině:

   - **Vyzvat k přidružení uživatele**: Při počátečním nastavení je možné zařízení spojit s uživatelem a potom mu umožnit přístup k firemním datům a e-mailu. U zařízení spravovaných v programu DEP, která patří uživatelům a potřebují používat portál společnosti (tzn. instalovat aplikace), je potřeba nastavit **přidružení uživatele**. Při registraci na zařízeních v programu DEP s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání. Novým uživatelům, kteří si musejí změnit heslo, když se poprvé přihlásí, se během registrace na zařízení DEP nezobrazí výzva. Také uživatelům, u jejichž hesel vypršela platnost, se během registrace DEP nezobrazí výzva k resetování hesla a budou muset heslo resetovat z jiného zařízení.

       >[!NOTE]
       >Program DEP s přidružením uživatele vyžaduje aktivaci [uživatelského jména / smíšeného koncového bodu WS-Trust 1.3](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints), aby mohl požádat o token uživatele. [Přečtěte si další informace o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   - **Bez přidružení uživatele**: K zařízení není přidružený žádný uživatel. Toto přidružení použijte u zařízení, která plní úkoly bez přístupu k místním uživatelským datům. Aplikace, které vyžadují přidružené uživatele, včetně aplikace Portál společnosti používané k instalaci obchodních aplikací, nebudou fungovat.

   Můžete také vybrat možnost **Přiřadit zařízení k této skupině**. Pokud chcete vybrat skupinu, zvolte **Vybrat**.

   > [!Important]
   > Přiřazení skupin se přesouvají z Intune do Azure Active Directory. Jakmile účet Intune obdrží příslušnou aktualizaci, možnost **Přiřadit zařízení k této skupině** se nebude zobrazovat. [Přečtěte si další informace](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

3. Povolte nastavení **Nakonfigurujte nastavení DEP (Device Enrollment Program) pro tuto zásadu**, které zajistí podporu programu DEP.

      ![Podokno Pomocníka s nastavením](../media/pol-sa-corp-enroll.png)

   Pro zařízení spravovaná pomocí programu DEP jsou dostupná následující nastavení:

   - **Oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.
   - **Telefonní číslo podpory** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko **Potřebuji nápovědu**.
   - **Režim přípravy** – Nastaví se při aktivaci. Bez obnovení továrního nastavení zařízení se nedá změnit:
       - **Bez dohledu** – Omezené možnosti správy.
       - **Pod dohledem** – Nabízí víc možností správy a ve výchozím nastavení má zakázaný zámek aktivace.
   - **Uzamknout registrační profil k zařízení** – Nastaví se při aktivaci a bez obnovení továrního nastavení se nedá změnit.
       - **Zakázat** – Umožňuje odebrání profilu správy z nabídky **Nastavení**.
       - **Povolit** (vyžaduje **Režim přípravy** = **Pod dohledem**) – Zakáže nastavení iOSu, které by mohlo povolovat odebrání profilu správy.
   - **Možnosti Pomocníka s nastavením** – Nastavení jsou volitelná a dají se nastavit později v nabídce **Nastavení** systému iOS.
        - **Heslo** – Při aktivaci se zobrazí výzva k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem (třeba pomocí beznabídkového režimu, který omezuje zařízení na jednu aplikaci).
       - **Zjišťování polohy** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu služby.
       - **Obnovit** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu k zálohování do úložiště iCloud.
       - **Apple ID** – Pokud je povolené, vyzve iOS uživatele při pokusu Intune o instalaci aplikace bez ID, aby zadali Apple ID. Apple ID je potřeba ke stahování aplikací pro iOS z App Storu, včetně těch instalovaných službou Intune.
       - **Podmínky a ujednání** – V případě povolení Pomocník nastavení vyzve uživatele k přijetí podmínek a ujednání společnosti Apple během aktivace.
       - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
       - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
       - **Zvětšení** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
       - **Siri** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
       - **Posílat diagnostická data do Applu** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
   -  **Povolí podrobnější správu přes Apple Configurator** –Nastavení možnosti **Zakázat** zabrání synchronizaci souborů s iTunes nebo správu přes Apple Configurator. Místo použití tohoto nastavení k povolení ručního nasazení s certifikátem nebo bez něj doporučujeme zvolit **Zakázat**, exportovat další konfiguraci z Apple Configuratoru a potom ji nasadit jako vlastní profil konfigurace pro iOS prostřednictvím Intune.
       - **Zakázat** – Brání zařízení v komunikaci přes USB (zakáže párování).
       - **Povolit** – Povolí komunikaci zařízení přes USB s libovolným počítačem PC nebo Mac.
       - **Vyžadovat certifikát** – Umožňuje párování s počítačem Mac s certifikátem importovaným do profilu registrace.

### <a name="assign-the-profile-to-devices"></a>Přiřazení profilu k zařízením

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a potom zvolte **Přiřadit**.

2. Zvolte zařízení, kterému chcete přiřadit profil, který jste vytvořili. Můžete zvolit **Všechna zařízení** nebo vyberte konkrétní zařízení a potom vyberte **Přidat**.

> [!Important]
> V současné době můžete v Intune určit výchozí profil registrace zařízení, což znamená, že nová sériová čísla se automaticky přiřazují k tomuto výchozímu profilu, když se synchronizují nová sériová čísla se službou Apple DEP. Když tenanta v blízké budoucnosti migrujete do nového portálu Azure Portal, nebudete už moct nastavit výchozí profil a přiřazovat sériová čísla automaticky k tomuto profilu. Místo toho budete muset přiřazovat sériová čísla k určitému profilu. [Další informace](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="assign-dep-devices-for-management"></a>Přiřazení zařízení DEP (Device Enrollment Program) pro správu

1. Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID.

2. Přejděte na **Program nasazení** &gt; **Program DEP (Device Enrollment Program)** &gt; **Spravovat zařízení**.

3. Zadejte, jak budete **volit zařízení**a zadejte podrobné informace o zařízení: **Sériové číslo**, **Číslo objednávky**nebo **Nahrát soubor CSV**.

4. Zvolte **Přiřadit k serveru**, zvolte &lt;název_serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

### <a name="synchronize-dep-managed-devices"></a>Synchronizace zařízení spravovaných v rámci programu DEP

Tímto postupem synchronizujete zařízení se službou Apple DEP a zařízení se tak objeví v konzole Intune.

1. Přihlaste se jako správce a otevřete [konzolu pro správu Microsoft Intune](https://manage.microsoft.com), přejděte na **Správce** &gt; **Správa mobilního zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a zvolte **Synchronizovat**. Žádost o synchronizaci se pošle společnosti Apple.

2. Pokud chcete po synchronizaci zobrazit zařízení spravovaná v programu DEP, přejděte v [konzole pro správu Microsoft Intune](https://manage.microsoft.com) na **Skupiny** &gt; **Všechna zařízení** &gt; **Firemní předregistrovaná zařízení** &gt; **Podle sériového čísla iOS**. V pracovním prostoru **Podle sériového čísla iOS** mají spravovaná zařízení u položky **Stav** nastavení „Nekontaktované“, dokud se zařízení nezapne a nespustí se Pomocník s nastavením pro registraci zařízení.

   Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy v rámci DEP platí v Intune následující omezení:

   - Úplná synchronizace programu DEP se nesmí spouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.

   - Každá žádost o synchronizaci má 10 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

### <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Zařízení vlastněná vaší společností se teď dají distribuovat uživatelům. Pokud je zařízení s iOSem zapnuté, zaregistruje se jeho správa službou Intune. Limit zařízení uživatelů platí na zařízení spravovaná pomocí DEP.

>[!NOTE]
>Když se uživatel pokusí zaregistrovat zařízení DEP v době, kdy je limit zařízení překročen, registrace selže, aniž by se zobrazilo upozornění.

## <a name="changes-to-intune-group-assignments"></a>Změny v přiřazení skupiny pro Intune

Od dubna 2017 se správa skupin zařízení přesouvá do služby Azure Active Directory. Po přechodu na skupiny Azure Active Directory se už přiřazení skupin nebude zobrazovat mezi možnostmi podnikových profilů zápisu. Jelikož se tato změna bude zavádět několik měsíců, je možné, že ji nezaznamenáte okamžitě. Po přesunu do nového portálu bude možné na základě názvů podnikových profilů registrace definovat nová dynamická přiřazení do skupin zařízení.

Po migraci se pro každou skupinu zařízení s Intune předem přiřazenou profilem registrace podnikového zařízení vytvoří odpovídající dynamická skupina zařízení v adresáři AAD založená na názvu profilu registrace podnikového zařízení. Nové názvy profilů mají formát *EnrollmentProfile:&lt;název přiřazeného profilu&gt;*. Uvedený postup zajistí, aby zařízení, která jsou zařazená do některé skupiny, byla do této skupiny zařízení zaregistrována automaticky i s nasazenými zásadami a aplikacemi.

K tomuto automatickému vytvoření skupiny dojde jenom jednou, a to při migraci skupin. Po migraci musí správci Intune skupiny vytvářet pomocí portálu Azure Portal. Podrobnosti o tom, jaký to má vliv na registraci firemních zařízení s iOSem, najdete v tématu [Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/) (Změny automatického seskupování pro firemní předregistrovaná zařízení s iOSem).

Můžete si také přečíst [článek o skupinách ve službě Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/), kde získáte další informace.

### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení](prerequisites-for-enrollment.md)

