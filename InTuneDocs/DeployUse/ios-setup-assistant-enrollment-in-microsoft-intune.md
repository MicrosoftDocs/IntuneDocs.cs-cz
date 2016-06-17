---
# required metadata

title: Registrace Pomocníka s nastavením pro zařízení s iOS v Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrace zařízení s iOS s nástrojem Apple Configurator pomocí Pomocníka s nastavením
Intune podporuje registraci firemních zařízení s iOS pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac. Tento proces obnoví tovární nastavení zařízení a připraví ho na spuštění Pomocníka s nastavením novým uživatelem zařízení s předinstalovanými zásadami společnosti.


## Registrace Pomocníka s nastavením pro zařízení s iOS v Microsoft Intune
Pomocí Apple Configuratoru můžete v zařízeních s iOS obnovit tovární nastavení a připravit je pro nového uživatele.  Tato metoda předpokládá, že používáte Apple Configurator 2.0, a vyžaduje, abyste zařízení s iOS připojili k počítači Mac pomocí USB a nastavili firemní registraci. K povolení aplikace Portál společnosti Intune většina scénářů vyžaduje, aby zásady použité na zařízení s iOS zahrnovaly*přidružení uživatele*.

**Požadavky**
* Fyzický přístup k zařízením s iOS – Zařízení musí být nenakonfigurovaná (obnovení továrního nastavení) a nesmí být chráněná heslem.
* Sériová čísla zařízení – [Jak zjistit sériové číslo systému iOS](https://support.apple.com/en-us/HT204308)
* Propojovací kabely USB
* Počítač Mac s nástrojem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Vytvořte skupinu mobilních zařízení** (volitelné)
    Jestli podnik potřebuje ke správě zařízení skupiny mobilních zařízení, vytvořte je. [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Vytvořte profil zařízení.**
    Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Jestli jste to ještě neudělali, vytvořte profil registrace zařízení pro zařízení iOS zaregistrovaná v Apple Configuratoru.

    ###### Vytvoření profilu

    1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Zařízení ve vlastnictví firmy** a klikněte na **Přidat**..

    ![Vytvoření profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

    2.  Zadejte podrobnosti profilů zařízení:

        -   **Název** – Název profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Popis** – Popis profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Podrobnosti registrace** – Určují, jak se budou zařízení registrovat.

            -   **Výzva k přidružení uživatele** – Při počátečním nastavení zařízení s iOS se dá zařízení spojit s uživatelem a potom mu umožnit přístup k firemním datům a e-mailu. Ve většině scénářů použití Pomocníka s nastavením je vhodná možnost **Výzva k přidružení uživatele**..
            Tento režim podporuje různé scénáře:

                -   **Osobní zařízení vlastněné společností** – „Vyberte si vlastní zařízení“ (CYOD). Podobá se vlastním soukromým nebo osobním zařízením s tím, že správce má určitá privilegia, třeba právo zařízení vymazat, resetovat, spravovat nebo zrušit jeho registraci. Uživatel zařízení může instalovat aplikace a má i většinu dalších oprávnění k používání zařízení, pokud je neblokují zásady správy.

                -   **Účet správce registrace zařízení** – K registraci zařízení se použije zvláštní účet správce Intune. Zařízení je možné spravovat jako soukromý účet, ale instalovat aplikace, vymazat, resetovat nebo spravovat zařízení nebo zrušit jeho registraci může jenom uživatel, který zná pověřovací údaje správce registrace. Informace o registraci zařízení sdíleného mnoha uživateli prostřednictvím společného účtu najdete v tématu [Registrace zařízení vlastněných společností pomocí správce registrace zařízení v Microsoft Intune](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)..

            -   **Bez přidružení uživatele** – Zařízení nemá určeného uživatele. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují spřažení s uživatelem, jsou zakázané nebo nefungují.

        -   **Předběžné přiřazení skupiny zařízení** – Do této skupiny na začátku patří všechna zařízení nasazená s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

          -  **Program DEP (Device Enrollment Program)** – Program Apple DEP (Device Enrollment Program) se při registraci prostřednictvím Pomocníka s nastavením nedá použít. Zkontrolujte, jestli je přepínač nastavený do polohy **Vypnuto**..

    3.  Jestli chcete profil přidat, klikněte na **Uložit profil** .

3.  **Přidejte zařízení s iOS, která chcete zaregistrovat prostřednictvím Pomocníka s nastavením.**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy** &gt; **Všechna zařízení** a klikněte na **Přidat zařízení**. Zařízení můžete přidat dvěma způsoby:

    ![Dialogové okno Přidat zařízení](../media/pol-SA-enroll-iOS-SetupAssistant.png)

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

    -   **Ručním přidáním podrobností o zařízeních** – Zadejte sériové číslo a podrobnosti až o pěti zařízeních.

    > [!NOTE]
    > Pokud později musíte zařízení vlastněná firmou ze správy pomocí služby Intune odebrat, musíte odebrat sériové číslo zařízení z Intune ve skupině **Zařízení vlastněná firmou** a deaktivovat tak registraci zařízení.  Pokud Intune provádí postup pro zotavení po havárii v době, kdy se odebírala sériová čísla, je potřeba ověřit, jestli jsou v dané skupině dostupná sériová čísla jenom aktivních zařízení.

    Pak klikněte na **Další**..

4.  **Vyberte zařízení k registraci.**
    Potvrďte zařízení k registraci. Sériová čísla, která jsou zaregistrovaná nebo byla zaregistrovaná jiným způsobem, nejdou importovat. Pokračujte kliknutím na položku **Další** .

5.  **Přiřaďte profil.**
    V seznamu dostupných profilů vyberte profil, který se přiřadí přidávaným zařízením. Zkontrolujte **podrobnosti registračního profilu**a potom klikněte na **Dokončit**. Ručně přidaná zařízení se dají přiřadit k libovolnému registračnímu profilu.

6.  **Exportujte profil, který se má nasadit na zařízení se systémem iOS.**
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a vyberte profil, který se u mobilních zařízení nasadí. Klikněte na možnost **Exportovat…** na hlavním panelu. Zkopírujte a uložte **URL profilu**. Později URL odešlete do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními iOS.
    Podpora Apple Configuratoru 2 vyžaduje úpravu adresy URL profilu 2.0. Nahraďte tuto adresu:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    s

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   V následujícím postupu odešlete tuto adresu URL profilu do služby Apple DEP pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOS.

    > [!NOTE]
    > Adresa URL registračního profilu platí dva týdny od data exportu. Pokud chcete zaregistrovat zařízení s iOS prostřednictvím Pomocníka s nastavením po době delší než dva týdny, musíte exportovat novou adresu URL registračního profilu.

7.  **Připravte zařízení pomocí nástroje Apple Configurator.**
    Zařízení iOS jsou připojená k počítači Mac a zaregistrovaná do správy mobilních zařízení.

    1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek klikněte na **Apple Configurator 2** a potom na **Předvolby**..

         > [!WARNING]
         > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Doporučuje se, aby byla zařízeních ve chvíli jejich připojení nastavená obrazovka **Hello**.

    2. V podokně Předvolby vyberte **Servery** a kliknutím na symbol „+“ pod levým podoknem spusťte průvodce serveru MDM. Klikněte na **Další**..

    3. Pro server MDM z kroku 6 výše zadejte položky **Název** a **Enrollment URL** (Adresa URL pro registraci). Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovaný z Intune. Klikněte na **Další**..  

       Pokud se zobrazí upozornění týkající se požadavků na profil důvěryhodnosti Apple TV, můžete možnost **Profil důvěryhodnosti** klidně zrušit kliknutím na šedý symbol „X“. Také můžete klidně ignorovat všechna upozornění týkající se certifikátu ukotvení. Pokračujte klikáním na **Další** až do ukončení průvodce.

    4.  V podokně **Servery** klikněte na Upravit vedle profilu nového serveru. Ujistěte se, že adresa URL pro registraci přesně odpovídá adrese URL exportované z Intune. Pokud se adresy liší, znovu zadejte původní adresu URL a kliknutím na **Uložit** uložte profil registrace exportovaný z Intune.

    5.  Mobilní zařízení iOS připojte adaptérem USB k počítači Apple.

        > [!WARNING]
        > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Doporučuje se, aby byla při spouštění Pomocníka s nastavením na zařízení zobrazená **úvodní obrazovka**.

    6.  Klikněte na **Připravit**. V podokně **Připravit zařízení iOS** vyberte možnost **Ručně** a potom klikněte na **Další**..

    7. V podokně **Enroll in MDM Server** (Zaregistrovat na serveru MDM) vyberte název serveru, který jste vytvořili, a klikněte na **Další**..

    8. V podokně **Dohled nad zařízeními** vyberte úroveň dohledu a potom klikněte na **Další**..

    9. V podokně **Vytvořit organizaci** vyberte **organizaci** nebo vytvořte novou a potom klikněte na **Další**..

    10. V podokně **Konfigurovat Pomocníka s nastavením iOS** vyberte kroky, které se budou zobrazovat uživateli, a potom klikněte na **Připravit**. Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  

    11. Až se dokončí příprava zařízení s iOS, můžete odpojit kabel USB.  

8.  **Distribuujte zařízení.**
    Zařízení jsou připravená na registraci ve společnosti. Vypněte zařízení a rozdejte je uživatelům. Po zapnutí zařízení se spustí Pomocník s nastavením.



### Související témata
[Příprava registrace zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


