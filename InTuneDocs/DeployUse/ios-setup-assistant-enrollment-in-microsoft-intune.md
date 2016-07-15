---
title: "Registrace Pomocníka s nastavením pro zařízení s iOS v Microsoft Intune | Microsoft Intune"
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
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f3637e79e7b6f93820e775932653c41879f369fe
ms.openlocfilehash: b9cb10ccb26d4f61d63fb2dc6c18be48cc0a3182


---

# Registrace zařízení s iOS s nástrojem Apple Configurator pomocí Pomocníka s nastavením
Intune podporuje registraci firemních zařízení s iOS pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac. Tento proces obnoví tovární nastavení zařízení a připraví ho na spuštění Pomocníka s nastavením novým uživatelem zařízení s předinstalovanými zásadami společnosti.


## Registrace Pomocníka s nastavením pro zařízení s iOS v Microsoft Intune
Pomocí Apple Configuratoru můžete v zařízeních s iOS obnovit tovární nastavení a připravit je pro nového uživatele.  Tato metoda předpokládá, že používáte Apple Configurator 2.0, a vyžaduje, abyste zařízení s iOS připojili k počítači Mac pomocí USB a nastavili firemní registraci. K povolení aplikace Portál společnosti Intune většina scénářů vyžaduje, aby zásady použité na zařízení s iOS zahrnovaly *přidružení uživatele*.

**Požadavky**
* Fyzický přístup k zařízením s iOS – Zařízení musí být nenakonfigurovaná (obnovení továrního nastavení) a nesmí být chráněná heslem.
* Sériová čísla zařízení – [Jak zjistit sériové číslo systému iOS](https://support.apple.com/en-us/HT204308)
* Propojovací kabely USB
* Počítač Mac s nástrojem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Vytvořte skupinu mobilních zařízení (volitelné).** Pokud vaše firma potřebuje ke správě zařízení skupiny mobilních zařízení, vytvořte je. [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Vytvořte profil zařízení.** Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Jestli jste to ještě neudělali, vytvořte profil registrace zařízení pro zařízení iOS zaregistrovaná v Apple Configuratoru.

    ###### Vytvoření profilu

    1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Zařízení ve vlastnictví firmy** a vyberte **Přidat…**.

    ![Vytvoření profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

    2.  Zadejte podrobnosti profilů zařízení:

        -   **Název** – Název profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Popis** – Popis profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Podrobnosti registrace** – Určují, jak se budou zařízení registrovat.

            -   **Výzva k přidružení uživatele** – Při počátečním nastavení zařízení s iOS se dá zařízení spojit s uživatelem a potom mu umožnit přístup k firemním datům a e-mailu. Ve většině scénářů použití Pomocníka s nastavením je vhodná možnost **Výzva k přidružení uživatele**.
            Tento režim podporuje různé scénáře:

                -   **Osobní zařízení vlastněné společností** – „Vyberte si vlastní zařízení“ (CYOD). Podobá se vlastním soukromým nebo osobním zařízením s tím, že správce má určitá privilegia, třeba právo zařízení vymazat, resetovat, spravovat nebo zrušit jeho registraci. Uživatel zařízení může instalovat aplikace a má i většinu dalších oprávnění k používání zařízení, pokud je neblokují zásady správy.

                -   **Účet správce registrace zařízení** – K registraci zařízení se použije zvláštní účet správce Intune. Zařízení je možné spravovat jako soukromý účet, ale instalovat aplikace, vymazat, resetovat nebo spravovat zařízení nebo zrušit jeho registraci může jenom uživatel, který zná pověřovací údaje správce registrace. Informace o registraci zařízení sdíleného mnoha uživateli prostřednictvím společného účtu najdete v tématu [Registrace zařízení vlastněných společností pomocí správce registrace zařízení v Microsoft Intune](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

            -   **Bez přidružení uživatele** – Zařízení nemá určeného uživatele. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují spřažení s uživatelem, jsou zakázané nebo nefungují.

        -   **Předběžné přiřazení skupiny zařízení** – Do této skupiny na začátku patří všechna zařízení nasazená s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

        >[!Important]
        >Přiřazení skupiny způsobí přesun z Intune do Azure Active Directory. [Další informace](http://go.microsoft.com/fwlink/?LinkID=787064)

          -  **Program DEP (Device Enrollment Program)** – Program Apple DEP (Device Enrollment Program) se při registraci prostřednictvím Pomocníka s nastavením nedá použít. Zkontrolujte, jestli je přepínač nastavený do polohy **Vypnuto**.

    3.  Profil přidáte kliknutím na **Uložit profil**.

3.  **Přidejte zařízení s iOS, která chcete zaregistrovat, v Pomocníkovi nastavením.** V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy** &gt; **Všechna zařízení** a vyberte **Přidat zařízení…**. Zařízení můžete přidat dvěma způsoby:

    ![Dialog Přidat zařízení](../media/pol-SA-enroll-iOS-SetupAssistant.png)

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
    > Pokud později musíte zařízení vlastněná firmou ze správy pomocí služby Intune odebrat, může být potřeba odebrat sériové číslo zařízení z Intune ve skupině zařízení **Podle sériového čísla iOS** v části **Firemní předregistrovaná zařízení** a deaktivovat tak registraci zařízení.  Pokud Intune provádí postup pro zotavení po havárii v době, kdy se odebírala sériová čísla, je potřeba ověřit, jestli jsou v dané skupině dostupná sériová čísla jenom aktivních zařízení.

    Vyberte **Další**.

4.  **Vyberte zařízení k registraci.** Potvrďte zařízení k registraci. Sériová čísla, která jsou zaregistrovaná nebo byla zaregistrovaná jiným způsobem, nejdou importovat. Pokračujte výběrem položky **Další**.

5.  **Přiřaďte profil.** V seznamu dostupných profilů vyberte profil, který se přiřadí přidávaným zařízením. Zkontrolujte **Podrobnosti registračního profilu** a potom vyberte **Dokončit**. Ručně přidaná zařízení se dají přiřadit k libovolnému registračnímu profilu.

6.  **Exportujte profil, který se nasadí na zařízení s iOS.** V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a vyberte profil, který se u mobilních zařízení nasadí. Vyberte **Exportovat…** na hlavním panelu. Zkopírujte a uložte **URL profilu**. Později URL odešlete do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními iOS.
    Podpora Apple Configuratoru 2 vyžaduje úpravu adresy URL profilu 2.0. Nahraďte tuto adresu:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    s

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   V následujícím postupu odešlete tuto adresu URL profilu do služby Apple DEP pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOS.



7.  **Připravte zařízení pomocí Apple Configuratoru.** Zařízení s iOS jsou připojená k počítači Mac a zaregistrovaná do správy mobilních zařízení.

    1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.

         > [!WARNING]
         > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Doporučuje se, aby byla zařízeních ve chvíli jejich připojení nastavená obrazovka **Hello**.

    2. V podokně Předvolby vyberte **Servery** a výběrem symbolu „+“ pod levým podoknem spusťte průvodce serveru MDM. Vyberte **Další**.

    3. Pro server MDM z kroku 6 výše zadejte položky **Název** a **Enrollment URL** (Adresa URL pro registraci). Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

       Pokud se zobrazí upozornění týkající se požadavků na profil důvěryhodnosti Apple TV, můžete možnost **Profil důvěryhodnosti** klidně zrušit výběrem šedého symbolu „X“. Také můžete klidně ignorovat všechna upozornění týkající se certifikátu ukotvení. Pokračujte výběrem položky **Další** až do ukončení průvodce.

    4.  V podokně **Servery** vyberte Upravit vedle profilu nového serveru. Ujistěte se, že adresa URL pro registraci přesně odpovídá adrese URL exportované z Intune. Pokud se adresy liší, znovu zadejte původní adresu URL a kliknutím na **Uložit** uložte profil registrace exportovaný z Intune.

    5.  Mobilní zařízení iOS připojte adaptérem USB k počítači Apple.

        > [!WARNING]
        > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Doporučuje se, aby byla při spouštění Pomocníka s nastavením na zařízení zobrazená **úvodní obrazovka**.

    6.  Vyberte **Připravit**. V podokně **Připravit zařízení iOS** vyberte možnost **Ručně** a vyberte **Další**.

    7. V podokně **Enrollment URL** (Zaregistrovat na serveru MDM) vyberte název serveru, který jste vytvořili, a vyberte **Další**.

    8. V podokně **Supervise Devices** (Dohled nad zařízeními) vyberte úroveň dohledu a potom vyberte **Další**.

    9. V podokně **Vytvořit organizaci** vyberte **organizaci** nebo vytvořte novou a potom vyberte **Další**.

    10. V podokně **Configure iOS Setup Assistant** (Konfigurovat Pomocníka s nastavením iOS) vyberte kroky, které se budou zobrazovat uživateli, a potom vyberte **Připravit**. Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  

    11. Až se dokončí příprava zařízení s iOS, můžete odpojit kabel USB.  

8.  **Distribuujte zařízení.** Zařízení jsou připravená na registraci ve společnosti. Vypněte zařízení a rozdejte je uživatelům. Po zapnutí zařízení se spustí Pomocník s nastavením.



### Viz taky
[Příprava registrace zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO1-->


