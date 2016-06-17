---
# required metadata

title: Přímá registrace zařízení s iOS v Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Přímá registrace zařízení s iOS pomocí nástroje Apple Configurator
Intune podporuje registraci firemních zařízení s iOS pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac. Tento proces neprovede reset továrního nastavení zařízení a registruje ho s předdefinovanými zásadami. Tato metoda je určená pro počítače s nastavením **Bez přidružení uživatele** a vyžaduje, abyste zařízení s iOS připojili pomocí USB k počítači Mac a nastavili firemní registraci. Aplikace Portál společnosti se pro zařízení s přímou registrací nepodporuje. Tyto pokyny předpokládají, že používáte Apple Configurator 2.0 na počítači Mac.

1.  **Vytvořte profil zařízení.**
    Profil registrace zařízení definuje nastavení, která se pro zařízení použijí. Jestli jste to ještě neudělali, vytvořte profil registrace zařízení pro zařízení iOS zaregistrovaná v Apple Configuratoru.

    #### Vytvoření profilu

    1.  V[konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a klikněte na **Přidat…**..

        ![Vytvoření stránky profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

    2.  Zadejte podrobnosti profilů zařízení:

        -   **Název** – Název profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Popis** – Popis profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Přidružení uživatele** – Určuje, jak se budou zařízení registrovat. Pro přímou registraci vyberte **Bez přidružení uživatele**..

        -   **Předběžné přiřazení skupiny zařízení** – Do této skupiny na začátku patří všechna zařízení nasazená s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

    3.  Jestli chcete profil přidat, klikněte na **Uložit profil** .

2.  **Přidejte zařízení iOS, která chcete zaregistrovat pomocí nástroje Apple Configurator.**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Skupiny** &gt; **Všechna zařízení** &gt; **Firemní předregistrovaná zařízení** &gt; **Podle sériového čísla iOS** a klikněte na **Přidat zařízení…**.

    ![Průvodce nastavením iOS](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Zařízení můžete přidat dvěma způsoby:

    -   **Odesláním souboru CSV se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce a bude bez záhlaví. Soubor může obsahovat maximálně 5000 zařízení a nesmí být větší než 5 MB.

        |||
        |-|-|
        |&lt;Sériové č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
        |&lt;Sériové č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|
        V textovém editoru vypadá soubor .csv takhle:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Ručním přidáním podrobností o zařízeních** – Zadejte sériové číslo a podrobnosti až o pěti zařízeních a potom klikněte na **Další**..

    > [!NOTE]
    > Pokud později musíte zařízení vlastněná firmou ze správy Intune odebrat, musíte odebrat sériové číslo zařízení z Intune ve skupině **Zařízení vlastněná firmou** a deaktivovat tak registraci zařízení.  Pokud Intune provádí postup pro zotavení po havárii v době, kdy se odebírala sériová čísla, je potřeba ověřit, jestli jsou v dané skupině dostupná sériová čísla jenom aktivních zařízení.

3.  **Vyberte zařízení k registraci.**
    Potvrďte zařízení k registraci. Sériová čísla, která jsou zaregistrovaná nebo byla zaregistrovaná jiným způsobem, nejdou importovat. Pokračujte kliknutím na položku **Další** .

4.  **Přiřaďte profil.**
    V seznamu dostupných profilů vyberte profil, který se přiřadí přidávaným zařízením. Zkontrolujte **podrobnosti registračního profilu**a potom klikněte na **Dokončit**. Ručně přidaná zařízení se dají přiřadit k libovolnému registračnímu profilu.

5.  **Vyberte profil, který se nasadí na zařízení s iOS.**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a vyberte profil, který se u mobilních zařízení nasadí. Tento profil by měl být stejný jako profil, který jste přiřadili k nasazení v předchozím kroku. Klikněte na možnost **Exportovat…** na hlavním panelu. Klikněte na **Stáhnout profil** a uložte stažený soubor .mobileconfig.

6.  **Přeneste soubor.**
    Zkopírujte stažený soubor .mobileconfig do počítače Mac.
    > [!NOTE]
    > Adresa URL registračního profilu platí dva týdny od data exportu. Pokud chcete zaregistrovat zařízení s iOS prostřednictvím Pomocníka s nastavením po době delší než dva týdny, musíte exportovat novou adresu URL registračního profilu.
7.  **Připravte zařízení pomocí nástroje Apple Configurator.**
    Zařízení iOS jsou připojená k počítači Mac a zaregistrovaná do správy mobilních zařízení.

    1.  Na počítači Mac spusťte **Apple Configurator 2.0**..

    2.  Zařízení s iOS připojte k počítači Mac pomocí kabelu USB. Zavřete aplikace **Photos**, **iTunes** a další aplikace, které se otevřou při zjištění zařízení.

    3.  V nástroji Apple Configurator klikněte na připojené zařízení s iOS a potom na tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Klikněte na **Profily**. .

    4.  Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a klikněte na **Přidat**. Profil se přidá do zařízení.  Pokud má zařízení nastavenou možnost **Bez dohledu**, instalace bude vyžadovat přijetí na zařízení.

8.  **Nainstalujte profil.**
    Teď můžete profil nainstalovat na zařízení s iOS. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití.  Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.

    ###### Dokončení přijetí profil pro zařízení s iOS bez dohledu

    1.  Odemkněte zařízení s iOS.

    2.  V dialogovém okně **Nainstalovat profil** pro **Profil správy** klepněte na **Instalovat**..

    3.  Zadejte **Heslo zařízení** nebo **Apple ID**, pokud je potřeba.

    4.  Přijměte **Upozornění** a klepněte na **Instalovat**..

    5.  Přijměte **Vzdálené upozornění** a klepněte na **Důvěřovat**..

    6.  Až okno **Profil nainstalován** potvrdí, že se profil **nainstaloval**, klikněte na **Hotovo**..

9. **Zkontrolujte profil.**
    Na zařízení s iOS otevřete **Nastavení**, přejděte na **Obecné** &gt; **Správa zařízení** &gt; **Profil správy** &gt; a zkontrolujte, jestli je uvedená instalace profilu. Zkontrolujte taky omezení zásad iOS a nainstalované aplikace. Zobrazení omezení zásad a aplikací na zařízení může trvat až 10 minut.

10. **Distribuujte zařízení.**
    Zařízení s iOS je teď zaregistrované v Intune a spravované.


### Související témata
[Příprava registrace zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


