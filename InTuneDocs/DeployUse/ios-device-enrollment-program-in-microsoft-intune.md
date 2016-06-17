---
# required metadata

title: Správa Apple DEP pro zařízení s iOS pomocí Microsoft Intune| Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrace zařízení s iOS vlastněných společností do programu DEP (Device Enrollment Program)
Microsoft Intune umožňuje nasadit profil registrace, který „vzduchem“ zaregistruje zařízení s iOS zakoupená prostřednictvím programu DEP (Device Enrollment Program). Registrační balíček může zahrnovat možnosti Pomocníka s nastavením pro zařízení. U zařízení zaregistrovaných v programu DEP uživatelé nemůžou registraci zrušit.

## Správa Apple DEP pro zařízení s iOS pomocí Microsoft Intune
Aby vaše společnost mohla pomocí programu Apple DEP (Device Enrollment Program) spravovat zařízení s iOS, která sama vlastní, musí se do tohoto programu zapojit a musí prostřednictvím něj získat zařízení. Podrobnosti o tomto procesu najdete na  [https://deploy.apple.com](https://deploy.apple.com). K výhodám tohoto programu patří bezobslužné nastavení zařízení, kdy jednotlivá zařízení není potřeba připojovat k počítači pomocí USB.

Abyste mohli v programu DEP registrovat zařízení iOS vlastněná společností, potřebujete od společnosti Apple token DEP. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token taky umožňuje Intune odesílat společnosti Apple registrační profil a přiřazovat k těmto profilům zařízení.

1.  **Zahájení správy zařízení se systémem iOS v Microsoft Intune**
    Před registrací zařízení do programu iOS Device Enrollment Program (DEP) musíte pro službu Intune povolit správu zařízení iOS.

2.  **Získání šifrovacího klíče**
    Jako uživatel s oprávněním správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správce** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a klikněte na **Stáhnout šifrovací klíč**. Uložte soubor šifrovacího klíče (.pem) místně. Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

      ![Aktualizace tokenu DEP (Device Enrollment Program)](../media/dev-sa-ios-dep.png)

3.  **Získání tokenu DEP (Device Enrollment Program)**
    Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID. Toto Apple ID musíte v budoucnosti použít k obnovení tokenu DEP.

    1.  V [portálu programu DEP (Device Enrollment Program)](https://deploy.apple.com) přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a potom klikněte na **Přidat server MDM**..

    2.  Zadejte **název serveru MDM** a potom klikněte na **Další**. Název serveru slouží pro vaši informaci, abyste dokázali server MDM identifikovat. Není to název nebo adresa URL serveru Microsoft Intune.

    3.  Zobrazí se dialogové okno **Přidat &lt;název_serveru&gt;**. Klikněte na **Zvolit soubor…** a zvolte soubor .pem. Potom klikněte na **Další**..

    4.  V dialogovém okně **Přidat &lt;název_serveru&gt;** se zobrazí odkaz s **vaším tokenem serveru**. Stáhněte si soubor tokenu serveru (.p7m) do počítače a potom klikněte na **Hotovo**..

    Soubor certifikátu (.p7m) se používá k navázání vztahu důvěryhodnosti mezi serverem Intune a serverem programu DEP (Device Enrollment Program) společnosti Apple.

4.  **Přidání tokenu DEP do Intune**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Správce** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a klikněte na **Nahrát token DEP**. **Vyberte** soubor s certifikátem (.p7m), zadejte svoje **Apple ID** a klikněte na **Nahrát**..

5.  **Přidání zásad registrace podnikových zařízení**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a klikněte na **Přidat**. Zadejte **obecné** podrobnosti, včetně **názvu** a **popisu**, zadejte, jestli zařízení přiřazená k profilu uživatele mají spřažení s uživatelem nebo jestli patří do skupiny, a pak povolte nastavení **Nakonfigurujte nastavení DEP (Device Enrollment Program) pro tuto zásadu** , aby se podporoval program DEP.  **Podokna Pomocníka s nastavením** definují nastavení zařízení iOS nakonfigurovaná v průběhu instalace.

      ![Podokno Pomocníka s nastavením](../media/pol-sa-corp-enroll.png)

6.  **Přiřazení zařízení DEP (Device Enrollment Program) pro správu**
    Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID. Přejděte na **Program nasazení** &gt; **Program DEP (Device Enrollment Program)** &gt; **Spravovat zařízení**. Zadejte, jak budete **volit zařízení**a zadejte podrobné informace o zařízení: **Sériové číslo**, **Číslo objednávky**nebo **Nahrát soubor CSV**. Potom vyberte **Přiřadit k serveru** a vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune. Potom klikněte na **OK**..

7.  **Synchronizace zařízení spravovaných v rámci programu DEP**
    Jako uživatel s oprávněním správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správce** &gt; **Správa mobilních zařízení** &gt; **iOS** &gt; **Program DEP (Device Enrollment Program)** a klikněte na **Synchronizovat**. Žádost o synchronizaci se pošle společnosti Apple. Chcete-li po synchronizaci zobrazit zařízení spravovaná programem DEP, přejděte v [konzole pro správu Microsoft Intune](http://manage.microsoft.com) na **Skupiny** &gt; **Všechna zařízení vlastněná společností**. V pracovním prostoru **Všechna zařízení ve vlastnictví firmy** mají spravovaná zařízení u položky **Stav** nastavení „Nekontaktované“, dokud se zařízení nezapne a nespustí se Pomocník s nastavením pro registraci zařízení.

    Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy v rámci DEP platí v Intune následující omezení:
     -  Úplná synchronizace DEP může být spuštěna maximálně jednou za 7 dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která Apple přiřadil Intune, bez ohledu na to, jestli už byla dříve synchronizovaná. Pokud dojde k pokusu o úplnou synchronizaci do 7 dnů od předchozí úplné synchronizace, aktualizuje Intune pouze sériová čísla, která ještě nejsou uvedená v Intune.
     -  Jakékoli žádosti o synchronizaci se přiřadí 10 minut na dokončení. Během této doby nebo do vykonání požadavku je tlačítko Synchronizovat neaktivní.

8.  **Distribuce zařízení uživatelům**
    Zařízení vlastněná vaší společností se teď dají distribuovat uživatelům. Pokud je zařízení s iOS zapnuté, zaregistruje se jeho správa službou Intune.



### Související témata
[Příprava registrace zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


