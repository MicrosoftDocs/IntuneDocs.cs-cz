---
title: "Přímá registrace zařízení s iOS | Microsoft Intune"
description: "Použijte nástroj Apple Configurator k přímé registraci zařízení s iOS vlastněných společností pomocí předdefinované zásady tak, že je připojíte přes USB do počítače Mac."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 2d2db078bbbce5945bf536a845cd8e4fa8f62c7e


---

# Přímá registrace zařízení s iOS pomocí nástroje Apple Configurator
Intune podporuje registraci firemních zařízení s iOS pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac. Tento proces neprovede reset továrního nastavení zařízení a registruje ho s předdefinovanými zásadami. Tato metoda je určená pro počítače s nastavením **Bez přidružení uživatele** a vyžaduje, abyste zařízení s iOS připojili pomocí USB k počítači Mac a nastavili firemní registraci. Když zařízení s iOS registrujte přímo, můžete ho registrovat bez získání sériového čísla zařízení. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. Aplikace Portál společnosti se pro zařízení s přímou registrací nepodporuje. Tyto pokyny předpokládají, že používáte Apple Configurator 2.0 na počítači Mac.

1.  **Vytvořte profil zařízení.** Profil registrace zařízení definuje nastavení, která se pro zařízení použijí. Jestli jste to ještě neudělali, vytvořte profil registrace zařízení pro zařízení iOS zaregistrovaná v Apple Configuratoru.

    1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a klikněte na **Přidat…**.

        ![Stránka pro vytvoření profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

    2.  Zadejte podrobnosti profilů zařízení:

        -   **Název** – Název profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Popis** – Popis profilu registrace zařízení. (Uživatelé ho nevidí.)

        -   **Přidružení uživatele** – Určuje, jak se budou zařízení registrovat. Pro přímou registraci vyberte **Bez přidružení uživatele**.

        -   **Předběžné přiřazení skupiny zařízení** – Do této skupiny na začátku patří všechna zařízení nasazená s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Profil přidáte kliknutím na **Uložit profil**.

5.  **Exportujte profil jako soubor .mobileconfig pro nasazení na zařízení iOS.** Vyberte profil zařízení, který jste vytvořili. Vyberte **Exportovat…** na hlavním panelu. Vyberte **Stáhnout profil** a uložte stažený soubor .mobileconfig.

6.  **Přeneste soubor.** Zkopírujte stažený soubor .mobileconfig do počítače Mac.
    > [!NOTE]
    > Adresa URL registračního profilu platí dva týdny od data exportu. Pokud chcete zaregistrovat zařízení s iOS prostřednictvím Pomocníka s nastavením po době delší než dva týdny, musíte exportovat novou adresu URL registračního profilu.
7.  **Připravte zařízení pomocí Apple Configuratoru.** Zařízení iOS jsou připojená k počítači Mac a zaregistrovaná do správy mobilních zařízení.

    1.  Na počítači Mac spusťte **Apple Configurator 2.0**.

    2.  Zařízení s iOS připojte k počítači Mac pomocí kabelu USB. Zavřete aplikace **Photos**, **iTunes** a další aplikace, které se otevřou při zjištění zařízení.

    3.  V nástroji Apple Configurator klikněte na připojené zařízení s iOS a potom na tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.

    4.  Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a vyberte **Přidat**. Profil se přidá do zařízení.  Pokud má zařízení nastavenou možnost **Bez dohledu**, instalace bude vyžadovat přijetí na zařízení.

8.  **Nainstalujte profil.** Teď můžete profil nainstalovat na zařízení s iOS. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití.  Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.

    1.  Odemkněte zařízení s iOS.

    2.  V dialogovém okně **Nainstalovat profil** pro **Profil správy** klepněte na **Instalovat**.

    3.  Zadejte **Heslo zařízení** nebo **Apple ID**, pokud je potřeba.

    4.  Přijměte **Upozornění** a klepněte na **Instalovat**.

    5.  Přijměte **Vzdálené upozornění** a klepněte na **Důvěřovat**.

    6.  Až okno **Profil nainstalován** potvrdí, že se profil **nainstaloval**, vyberte **Hotovo**.

9. **Ověřte profil.**
    Na zařízení s iOS otevřete **Nastavení**, přejděte na **Obecné** &gt; **Správa zařízení** &gt; **Profil správy** &gt; a zkontrolujte, jestli je uvedená instalace profilu. Zkontrolujte taky omezení zásad iOS a nainstalované aplikace. Zobrazení omezení zásad a aplikací na zařízení může trvat až 10 minut.

10. **Distribuujte zařízení** Zařízení s iOS je teď zaregistrované v Intune a spravované.



<!--HONumber=Jul16_HO3-->


