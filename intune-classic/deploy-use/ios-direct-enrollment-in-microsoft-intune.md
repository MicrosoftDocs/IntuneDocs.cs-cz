---
title: Přímá registrace zařízení s iOSem
description: Použijte nástroj Apple Configurator k přímé registraci zařízení s iOSem vlastněných společností pomocí předdefinované zásady tak, že je připojíte přes USB do počítače Mac.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c4c98c6b279ecc99d2220a7e5071a1f92af1ea8b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>Přímá registrace zařízení s iOSem pomocí Apple Configuratoru

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune podporuje registraci zařízení s iOSem patřících společnosti v nástroji [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěném na počítači Mac. Tento proces neprovede reset továrního nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tento způsob registrace je určený pro zařízení **bez přidruženého uživatele** a vyžaduje, abyste zařízení s iOSem připojili přes USB k počítači Mac a nastavili firemní registraci.

Při přímé registraci zařízení s iOSem můžete zařízení zaregistrovat i bez získání jeho sériového čísla. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. U zařízení zaregistrovaných přímo není podporovaná aplikace Portál společnosti. Tyto pokyny předpokládají, že používáte Apple Configurator 2.0 na počítači Mac.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

1. Pokud jste to ještě neudělali, vytvořte profil registrace zařízení pro zařízení s iOSem zaregistrovaná prostřednictvím Apple Configuratoru. Profil registrace zařízení definuje nastavení, která se pro zařízení použijí.

   1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Zásady** &gt; **Registrace podnikového zařízení** a zvolte **Přidat**.

      ![Stránka pro vytvoření profilu registrace zařízení](../media/pol-sa-corp-enroll.png)

   2. Zadejte podrobnosti profilů zařízení:

      - **Název:** Název registračního profilu zařízení. (Uživatelé ho nevidí.)

      - **Popis:** Popis registračního profilu zařízení. (Uživatelé ho nevidí.)

      - **Přidružení uživatele:** Určuje způsob registrace zařízení. U přímé registrace vyberte **Bez přidružení uživatele**.

      - **Předběžné přiřazení skupiny zařízení:** Do této skupiny patří na začátku všechna zařízení s tímto profilem. Po registraci můžete zařízení přiřadit někomu jinému.

        [!INCLUDE [groups deprecated](../includes/group-deprecation.md)]


   3. Profil přidáte kliknutím na **Uložit profil**.

2. Profil nasazovaný na zařízení s iOSem exportujte jako soubor .mobileconfig:

   1.   Vyberte vytvořený profil zařízení.

   2.   Na hlavním panelu zvolte **Exportovat**.

   3.   Vyberte **Stáhnout profil** a uložte stažený soubor .mobileconfig.

3. Přeneste stažený soubor .mobileconfig tím, že ho zkopírujete do počítače Mac.
   > [!NOTE]
   > Adresa URL registračního profilu platí dva týdny od data exportu. Pokud chcete zaregistrovat zařízení s iOSem prostřednictvím Pomocníka s nastavením po době delší než dva týdny, musíte exportovat novou adresu URL registračního profilu.

4. Připravte zařízení v Apple Configuratoru. Zařízení iOS jsou připojená k počítači Mac a zaregistrovaná do systému správy mobilních zařízení.

   1.  Na počítači Mac otevřete **Apple Configurator 2.0**.

   2.  Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete aplikace **Photos**, **iTunes** a další aplikace, které se otevřou při zjištění zařízení.

   3.  V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.

   4.  Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení.  Pokud má zařízení nastavenou možnost **Bez dohledu**, instalace bude vyžadovat přijetí na zařízení.

5. Teď můžete profil nainstalovat na zařízení s iOSem. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.

   1.  Odemkněte zařízení s iOSem.

   2.  V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.

   3.  Zadejte **Heslo zařízení** nebo **Apple ID**, pokud je potřeba.

   4.  Potvrďte **upozornění** a zvolte **Instalovat**.

   5.  Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.

   6.  Jakmile okno **Profil nainstalován** potvrdí, že se profil **nainstaloval**, zvolte **Hotovo**.

6. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** &gt; **Správa zařízení** &gt; **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

7. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.
