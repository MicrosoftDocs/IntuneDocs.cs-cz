---
title: "Registrace zařízení s iOSem pomocí pomocníka s nastavením | Dokumentace Microsoftu"
description: "Použití nástroje Apple Configurator k registraci zařízení s iOSem patřících společnosti, aby bylo možné obnovit jejich tovární nastavení a připravit je ke spuštění pomocníka s nastavením (Setup Assistant)."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a2e840797c06322b9efc59438e0675e57b7cdb24
ms.openlocfilehash: facae5f49b52760dcea0653bd261e16e13e11bbf


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Použití pomocníka s nastavením k registraci zařízení s iOSem v Apple Configuratoru

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune podporuje registraci zařízení s iOSem patřících společnosti pomocí [Apple Configuratoru](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac. Tento postup obnoví tovární nastavení zařízení a připraví ho ke spuštění pomocníka s nastavením a k instalaci zásad společnosti pro nového uživatele.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

Apple Configurator umožňuje obnovit na zařízení s iOSem tovární nastavení a připravit ho k nastavení pro nového uživatele. U tohoto způsobu je potřeba zařízení s iOSem připojit k počítači Mac přes USB, aby bylo možné nastavit firemní registraci. Předpokládá se použití Apple Configuratoru 2.0. K povolení aplikace Portál společnosti služby Intune většina scénářů vyžaduje, aby zásady použité na zařízení s iOSem zahrnovaly **přidružení uživatele**.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Předpoklady pro registraci zařízení s iOSem pomocí Apple Configuratoru s pomocníkem s nastavením (Setup Assistant)

- [Nainstalujte certifikát služby APN](set-up-ios-and-mac-management-with-microsoft-intune.md).

- Je nutné, abyste měli fyzický přístup k zařízením s iOSem – zařízení musí být v továrním nastavení, kdy nejsou chráněná heslem.

- Obstarejte si sériová čísla zařízení – viz článek [Zjištění sériového čísla zařízení s iOSem](https://support.apple.com/en-us/HT204308).

- Připravte si propojovací kabely USB.

- Připravte si počítač Mac s [Apple Configuratorem 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).


## <a name="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Postup při registraci zařízení s iOSem pomocí Apple Configuratoru s pomocníkem s nastavením

Následující postup vysvětluje, jak zaregistrovat zařízení s iOSem hned od začátku pomocí Apple Configuratoru s pomocníkem s nastavením. Když se zařízení přidávají nebo odebírají z organizace, budete asi některé z těchto kroků opakovat, například přidávání nebo odebírání sériových čísel, jak je popsáno níže.

### <a name="create-mobile-device-groups-optional"></a>Vytvoření skupin mobilních zařízení (volitelné)

Jestli podnik potřebuje ke správě zařízení skupiny mobilních zařízení, můžete je volitelně vytvořit. Další informace najdete v tématu [Použití skupin pro správu uživatelů a zařízení v Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="create-a-profile-for-devices"></a>Vytvořte profil zařízení.

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení.

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a zvolte **Přidat**.

  ![Vytvoření profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

2. Zadejte podrobnosti profilů zařízení:

   -   **Název** – název profilu registrace zařízení (uživatelé ho nevidí).

   -   **Popis:** – popis profilu registrace zařízení (uživatelé ho nevidí).

   -   **Podrobnosti registrace** – určuje způsob registrace zařízení.

       -   **Vyzvat k přidružení uživatele** – při počátečním nastavení musí mít zařízení přiřazeného uživatele, aby umožňovalo přístup k datům a e-mailu společnosti. **Přidružení uživatele** – je potřeba nastavit pro zařízení spravovaná v programu DEP, která patří uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací.

       -   **Bez přidružení uživatele** – zařízení nemá přidruženého uživatele. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

   -   **Předběžné přiřazení skupiny zařízení** – na začátku patří do této skupiny všechna zařízení nasazená s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

   > [!Important]
   > Přiřazení skupin se přesouvají z Intune do Azure Active Directory. Jakmile účet Intune obdrží příslušnou aktualizaci, možnost **Přiřadit zařízení k této skupině** se nebude zobrazovat. [Přečtěte si další informace](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

   -  **Program DEP (Device Enrollment Program)** – tento program se nedá použít při registraci pomocí průvodce nastavením. Zkontrolujte, že je přepínač nastavený do polohy **Vypnuto**.

3.  Profil přidáte kliknutím na **Uložit profil**.

### <a name="add-ios-devices-to-enroll-with-setup-assistant"></a>Přidejte zařízení s iOS, která chcete zaregistrovat prostřednictvím pomocníka s nastavením.

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy** &gt; **Všechna zařízení** a zvolte **Přidat zařízení**. 

   Zařízení můžete přidat dvěma způsoby:

   ![Dialog Přidat zařízení](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   -  **Odesláním souboru CSV se sériovými čísly** – vytvořte seznam oddělený čárkami (.csv), který bude bez záhlaví a bude mít dva sloupce. Soubor může obsahovat maximálně 5000 zařízení, ale nesmí být větší než 5 MB.

    |||
    |-|-|
    |&lt;Sériové č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
    |&lt;Sériové č.&2;&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|

  Soubor .csv v textovém editoru:

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

  -  **Ručním přidáním podrobností o zařízeních**&mdash; – zadejte sériové číslo a případné poznámky nebo detaily pro až 15 zařízení.

  V podokně **Zkontrolovat zařízení** můžete sériová čísla potvrdit. Můžete se také rozhodnout, jestli chcete přepsat **Podrobnosti** pro sériová čísla, která se importují znovu, nebo můžete zrušit zaškrtnutí políčka **Přepsat** a zachovat aktuální podrobnosti. 

> [!NOTE] 
> V existující konzole správce Intune můžou správci přijímat přidružené podrobnosti z nahraného CSV a přepsat existující podrobnosti pro jednotlivá sériová čísla. V novém portálu Azure Portal budete moct jenom přepsat podrobnosti pro všechna sériová čísla nebo ignorovat nové podrobnosti pro všechna sériová čísla.

  > [!NOTE]
  > Pokud později budete chtít zařízení vlastněná firmou ze správy pomocí služby Intune odebrat, budete asi muset přejít do skupiny zařízení **Podle sériového čísla iOSu** v části **Firemní předregistrovaná zařízení** a odebrat sériové číslo zařízení z Intune, aby se registrace zařízení deaktivovala. Pokud Intune provádí postup zotavení po havárii přibližně v době odebrání sériových čísel, bude potřeba ověřit, že jsou ve skupině jenom sériová čísla aktivních zařízení.

2. Vyberte **Další**.

3. Vyberte zařízení k registraci. Sériová čísla, která jsou zaregistrovaná nebo byla zaregistrovaná jiným způsobem, nejdou importovat. Pokračujte výběrem položky **Další**.

### <a name="assign-a-profile"></a>Přiřazení profilu

V seznamu dostupných profilů vyberte profil, který se přiřadí přidaným zařízením. Zkontrolujte **podrobnosti registračního profilu** a zvolte **Dokončit**. Ručně přidaným zařízením můžete přiřadit libovolný registrační profil.

> [!Important]
> V současné době můžete v Intune určit výchozí profil registrace zařízení, což znamená, že nová sériová čísla se automaticky přiřazují tomuto výchozímu profilu, když se synchronizují nová sériová čísla se službou Apple DEP. Když tenanta v blízké budoucnosti migrujete do nového portálu Azure Portal, nebudete už moct nastavit výchozí profil a přiřazovat sériová čísla automaticky k tomuto profilu. Místo toho budete muset přiřazovat sériová čísla k profilu vy. [Další informace](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-ios-devices-using-device-enrollment-program)

### <a name="export-a-profile-to-deploy-to-ios-devices"></a>Exportujte profil, který se má nasadit na zařízení se systémem iOS.

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a vyberte profil zařízení nasazovaný u mobilních zařízení. 

2. Na hlavním panelu zvolte **Exportovat**. Zkopírujte a uložte **URL profilu**. Později URL odešlete do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními iOS.

  Podpora Apple Configuratoru 2 vyžaduje úpravu adresy URL profilu 2.0. Uděláte to tak, že tento kód:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Nahradíte tímto kódem:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   V následujícím postupu odešlete tuto adresu URL profilu do služby Apple DEP pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOS.



### <a name="prepare-the-device-with-apple-configurator"></a>Připravte zařízení pomocí nástroje Apple Configurator.

Zařízení iOS jsou připojená k počítači Mac a zaregistrovaná do systému správy mobilních zařízení.

1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.

   > [!WARNING]
   > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.

2. V podokně předvoleb vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Vyberte **Další**.

3. Zadejte **název** a **adresu URL pro registraci** serveru MDM z 6. kroku – Registrace pomocníka s nastavením pro zařízení s iOSem v Microsoft Intune. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

   Upozornění na neověřenou adresu URL serveru můžete ignorovat. Vyberte **Další** a pokračujte až do konce průvodce.

4.  Mobilní zařízení s iOSem připojte kabelem USB k počítači Mac.

    > [!WARNING]
    > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Při spuštění pomocníka s nastavením by zařízení měla mít nastavenou **úvodní obrazovku**.

5.  Vyberte **Připravit**. V podokně přípravy zařízení s iOSem vyberte **Ručně** a pak zvolte **Další**.

6. V podokně registrace na serveru MDM vyberte název vytvořeného serveru a zvolte **Další**.

7. V podokně dohledu nad zařízeními vyberte úroveň dohledu a zvolte **Další**.

8. V podokně vytvoření organizace zvolte **Organizace** nebo vytvořte novou organizaci a zvolte **Další**.

9. V podokně konfigurace pomocníka s nastavením iOS vyberte kroky, které se budou zobrazovat uživateli, a zvolte **Připravit**. Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  

10. Až se dokončí příprava zařízení s iOSem, můžete odpojit kabel USB.  

### <a name="distribute-devices"></a>Distribuujte zařízení.

Zařízení jsou připravená na registraci ve společnosti. 

Vypněte zařízení a rozdejte je uživatelům. Když uživatelé zařízení zapnou, spustí se pomocník s nastavením.


### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


