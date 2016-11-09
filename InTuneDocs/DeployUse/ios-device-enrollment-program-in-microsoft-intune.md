---
title: "Správa Apple DEP pro zařízení s iOS | Microsoft Intune"
description: "Nasaďte registrační profil, který umožňuje bezdrátovou registraci zařízení s iOS koupených prostřednictvím programu DEP (Device Enrollment Program) pro zařízení s iOS, aby bylo možné je spravovat."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 1bc39e7e91b1511ffb99e92e569df0a7153cc06f


---

# <a name="enroll-corporateowned-device-enrollment-program-ios-devices"></a>Registrace zařízení s iOS vlastněných společností do programu DEP (Device Enrollment Program)
Microsoft Intune umožňuje nasadit registrační profil, který bezdrátově zaregistruje zařízení s iOS zakoupená prostřednictvím programu DEP (Device Enrollment Program). Registrační balíček může zahrnovat možnosti Pomocníka s nastavením pro zařízení. U zařízení zaregistrovaných prostřednictvím Programu registrace zařízení nemůžou uživatelé registraci zrušit.

## <a name="apple-dep-management-for-ios-devices-with-microsoft-intune"></a>Správa Apple DEP pro zařízení s iOS pomocí Microsoft Intune
Pokud chce organizace ke správě zařízení s iOS, která jsou v jejím vlastnictví, používat program DEP (Device Enrollment Program) společnosti Apple, musí se do tohoto programu zaregistrovat a získat zařízení jeho prostřednictvím. Podrobnosti o tomto procesu najdete na  [https://deploy.apple.com](https://deploy.apple.com). Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

Abyste mohli v programu DEP registrovat zařízení s iOS vlastněná společností, potřebujete od společnosti Apple token DEP. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token taky umožňuje Intune odesílat společnosti Apple registrační profil a přiřazovat k těmto profilům zařízení.

1.  **Zahájení správy zařízení se systémem iOS v Microsoft Intune**</br>
    Před registrací zařízení s iOS do programu DEP (Device Enrollment Program) musíte službě Intune povolit správu zařízení s iOS.

2.  **Získání šifrovacího klíče**</br>
    Přihlaste se jako správce a otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a zvolte **Stáhnout šifrovací klíč**. Uložte soubor šifrovacího klíče (.pem) místně. Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

      ![Aktualizace tokenu DEP (Device Enrollment Program)](../media/dev-sa-ios-dep.png)

3.  **Získejte token DEP (Device Enrollment Program).**</br>
    Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pod firemním Apple ID. Toto Apple ID budete muset později použít k obnovení tokenu DEP.

    1.  Na [portálu programu DEP (Device Enrollment Program)](https://deploy.apple.com) přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a pak zvolte **Přidat server MDM**.

    2.  Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

    3.  Otevře se dialog **Přidat server &lt;název_serveru&gt;**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

    4.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.

    Soubor certifikátu (.p7m) se používá k navázání vztahu důvěryhodnosti mezi serverem Intune a serverem programu DEP (Device Enrollment Program) společnosti Apple.

4.  **Přidejte token DEP do Intune.**</br>
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a zvolte **Nahrát token DEP**. **Vyhledejte** soubor certifikátu (.p7m), zadejte své **Apple ID** a zvolte **Nahrát**.

5.  **Přidání zásad registrace podnikových zařízení**</br>
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a zvolte **Přidat**.

    Zadejte **obecné** podrobnosti, jako je **Název** a **Popis**, a určete, jestli zařízení přiřazená k profilu mají přidruženého uživatele nebo patří skupině.
      - **Vyzvat k přidružení uživatele**: Při počátečním nastavení je možné zařízení spojit s uživatelem a potom mu umožnit přístup k firemním datům a e-mailu. U zařízení spravovaných v programu DEP, která patří uživatelům a potřebují používat portál společnosti (tzn. instalovat aplikace), je potřeba nastavit **přidružení uživatele**.</br> **Poznámka:** Zařízení DEP s přidružením uživatele nemohou podporovat vícefaktorové ověřování.

      > [!NOTE]
      > Program DEP s přidružením uživatele vyžaduje aktivaci uživatelského jména / smíšeného koncového bodu WS-Trust 1.3, aby mohl požádat o token uživatele.

      - **Bez přidružení uživatele**: K zařízení není přidružený žádný uživatel. Toto přidružení použijte u zařízení, která plní úkoly bez přístupu k místním uživatelským datům. Aplikace, které vyžadují přidružené uživatele, včetně aplikace Portál společnosti používané k instalaci obchodních aplikací, nebudou fungovat.

    Můžete také vybrat možnost **Přiřadit zařízení k této skupině**. Pokud chcete vybrat skupinu, zvolte **Vybrat...**

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Dál povolte nastavení **Nakonfigurujte nastavení DEP (Device Enrollment Program) pro tuto zásadu**, které zajistí podporu programu DEP.

      ![Podokno Pomocníka s nastavením](../media/pol-sa-corp-enroll.png)

     Pro zařízení spravovaná pomocí programu DEP jsou dostupná následující nastavení:

     - **Oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.
     - **Telefonní číslo podpory** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko **Potřebuji nápovědu**.
     - **Režim přípravy** – Nastaví se při aktivaci. Bez obnovení továrního nastavení zařízení se nedá změnit:
        - **Bez dohledu** – Omezené možnosti správy.
        - **Pod dohledem** – Nabízí víc možností správy a ve výchozím nastavení má zakázaný zámek aktivace.
     - **Uzamknout registrační profil k zařízení** – Nastaví se při aktivaci a bez obnovení továrního nastavení se nedá změnit.
        - **Zakázat** – Umožňuje odebrání profilu správy z nabídky **Nastavení**.
        - **Povolit** (vyžaduje nastavení **Režim přípravy**  =  **Pod dohledem**) – Zakáže nastavení iOS, které by mohlo povolovat odebrání profilu správy.
     - **Možnosti Pomocníka s nastavením** – Nastavení jsou volitelná a dají se nastavit později v nabídce **Nastavení** systému iOS.
        - **Heslo** – Při aktivaci se zobrazí výzva k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem (třeba pomocí celoobrazovkového režimu, který omezuje zařízení na jednu aplikaci).
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

6.  **Přiřazení zařízení DEP pro správu** Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID. Přejděte na **Program nasazení** &gt; **Program DEP (Device Enrollment Program)** &gt; **Spravovat zařízení**. Zadejte, jak budete **volit zařízení**a zadejte podrobné informace o zařízení: **Sériové číslo**, **Číslo objednávky**nebo **Nahrát soubor CSV**. Dále vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

7.  **Synchronizace zařízení spravovaných programem DEP** Přihlaste se jako uživatel s oprávněním správce a otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com). Přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a zvolte **Synchronizovat nyní**. Žádost o synchronizaci se pošle společnosti Apple. Pokud chcete po synchronizaci zobrazit zařízení spravovaná v programu DEP, přejděte v [konzole pro správu Microsoft Intune](http://manage.microsoft.com) na **Skupiny** &gt; **Všechna zařízení** &gt; **Firemní předregistrovaná zařízení** &gt; **Podle sériového čísla iOS**. V pracovním prostoru **Podle sériového čísla iOS** mají spravovaná zařízení u položky **Stav** nastavení „Nekontaktované“, dokud se zařízení nezapne a nespustí se Pomocník s nastavením pro registraci zařízení.

    Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy v rámci DEP platí v Intune následující omezení:
     -  Úplná synchronizace programu DEP se nesmí spouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -  Každá žádost o synchronizaci má 10 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

8.  **Distribuování zařízení uživatelům** Zařízení vlastněná vaší společností se teď dají distribuovat uživatelům. Pokud je zařízení s iOS zapnuté, zaregistruje se jeho správa službou Intune.

## <a name="changes-to-intune-group-assignments"></a>Změny v přiřazení skupiny pro Intune

Od listopadu se správa skupin zařízení přesune do služby Azure Active Directory. Po přechodu na skupiny Azure Active Directory se už přiřazení skupin nebude zobrazovat mezi možnostmi v části **Podnikový profil zápisu**. Jelikož se tato změna bude zavádět několik měsíců, je možné, že ji nezaznamenáte okamžitě. Po přesunu do nového portálu bude možné na základě názvů podnikových profilů registrace definovat nová dynamická přiřazení do skupin zařízení. Uvedený postup zajistí, aby zařízení, která jsou zařazená do některé skupiny, byla do této skupiny zařízení zaregistrována automaticky i s nasazenými zásadami a aplikacemi. [Další informace o skupinách Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### <a name="see-also"></a>Viz taky
[Předpoklady pro registraci zařízení](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO1-->


