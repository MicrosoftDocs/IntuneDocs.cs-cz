---
title: "Vytvoření zásad a publikování aplikace pro uživatele | Dokumentace Microsoftu"
description: "Vytvoření zásad a publikování aplikace při registraci bezplatné 30denní zkušební verze Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 21d1e624069117d905dc7aced33b70abeb0e1109
ms.lasthandoff: 04/14/2017


---


# <a name="create-policies-and-publish-an-app-to-evaluation-users"></a>Vytvoření zásad a publikování aplikace pro testovací uživatele

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune nabízí nastavení, které pomáhá řídit nastavení zabezpečení na mobilních zařízeních, spravovat nastavení brány Windows Firewall a Endpoint Protection pro počítače a nasazovat aplikace. Pokud chcete Intune používat pro zařízení, která nakonfigurujete pro použití v produkčním prostředí po skončení testování, je bezpodmínečně nutné postupovat podle pokynů v tématech [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) a [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Pomocí Intune můžete provádět dva typy instalace aplikací. První je **požadovaná instalace**, která aplikaci automaticky nasadí do spravovaných zařízení. Druhá je **dostupná instalace**, která nasadí aplikaci nebo odkaz na aplikaci na portálu společnosti Intune, aby si mohli uživatelé vybrat, jestli ji chtějí mít nainstalovanou na počítači nebo na mobilním zařízení.

Než použijete Intune k nasazení aplikací, zkontrolujte, že máte příslušné licence k publikování, distribuci a použití aplikace. Pracovní prostor **Licence** umožňuje přidávat a spravovat informace o licenční smlouvě pro aplikace nebo software zakoupené prostřednictvím multilicenční smlouvy s Microsoftem a pro aplikace nebo software Microsoftu nebo jiného subjektu než Microsoftu zakoupené jiným způsobem. Potom můžete vytvořit sestavy licencí, které budou zobrazovat informace o využití spravovaných licencí ve vaší společnosti, abyste měli pořád přehled, nebo informace o aktivitě využití licencí.

V následujícím postupu nastavíte zásady konfigurace mobilního zařízení a zásady brány firewall počítače s Windows a nakonfigurujete Skype jako instalaci dostupnou pro mobilní zařízení po jejich registraci. Po přidání a nasazení nových zásad zdědí všichni uživatelé nebo zařízení ve skupině, do které jste zásadu nasadili, tato nastavení jako svoje základní zásady. Podrobnosti těchto zásad můžete později kdykoli zkontrolovat nebo upravit v pracovním prostoru **Zásady** v konzole pro správu.

## <a name="create-and-deploy-a-mobile-device-configuration-policy"></a>Vytvoření a nasazení zásady konfigurace mobilních zařízení

1.  Otevřete [konzolu pro správu Intune](https://manage.microsoft.com/).

2.  V levém podokně vyberte ikonu **Zásady**.

3.  V seznamu **Úlohy** na stránce **Přehled zásad** vyberte **Přidat zásadu**.

4.  V seznamu zásad rozbalte platformu, pro kterou chcete vytvořit zásadu, vyberte **Všeobecná konfigurace**, zvolte **Vytvoření a nasazení vlastních zásad** a potom zvolte **Vytvořit zásadu**.

5.  Po zobrazení výzvy **Vyberte skupiny, do kterých chcete nasadit tuto zásadu** vyberte ze seznamu položku **Moji uživatelé zkušební verze** a zvolte **Přidat** &gt; **OK**.

Vaše zásada se zobrazí v seznamu zásad konfigurace a byla nasazena do skupiny **Moji uživatelé zkušební verze** . Nastavení zásady zobrazíte tak, že na zásadu dvakrát kliknete.

## <a name="publish-the-skype-app-for-mobile-devices"></a>Publikování aplikace Skype pro mobilní zařízení

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte ikonu **Aplikace** a pak zvolte **Aplikace** &gt; **Přidat aplikaci**. Po zobrazení výzvy zadejte své přihlašovací údaje Intune.

    > [!NOTE]
    > Při prvním spuštění **Intune Software Publisheru** může instalace aplikace chvíli trvat.

2.  Přečtěte si upozornění zabezpečení a zvolte **Spustit**.

3.  Na stránce **Než začnete** vyberte **Další**.

4.  Na stránce **Instalace softwaru** v části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení**vyberte **Externí odkaz**.

5.  Zadejte externí odkaz pro software v části **Zadejte adresu URL** a vyberte **Další**. Ujistěte se, že adresa URL začíná na **https://**. Pro aplikaci Skype použijte odkaz dole odpovídající platformě mobilního zařízení, kterou používáte:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8.1:** [http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na stránce **Popis softwaru** zadejte informace k softwaru, které mají uživatelé vidět na portálu společnosti, a vyberte **Další**. Dostupná jsou tato nastavení (tento příklad se týká Skypu):

    -   **Vydavatel:** Zadejte název vydavatele, **Microsoft**.

    -   **Název:** Zadejte **Skype**

    -   **Popis:** Zadejte popis softwaru, třeba **Komunikační aplikace Skype**

    -   **Kategorie:** Vyberte kategorii, která nejlíp odpovídá tomuto softwaru, třeba **Spolupráce**

    -   **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti:** Po výběru této možnosti bude při prohlížení na mobilních zařízeních aplikace zřetelně zobrazená na portálu společnosti.

    -   **Ikona:**  (Volitelné) Určete, jestli chcete k softwaru přidružit ikonu. Maximální velikost ikony je 250 x 250 pixelů, ale doporučená velikost je 32 x 32 pixelů.

7.  Na stránce **Souhrn** zkontrolujte zadané informace o softwaru a vyberte **Odeslat**. Průvodce ukončíte výběrem **Zavřít**.

8.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Aplikace** &gt; **Aplikace** &gt; **Skype** &gt; **Spravovat nasazení**.

9. Na stránce **Vybrat skupiny** vyberte položku **Moji uživatelé zkušební verze** pro nasazení softwaru v této skupině uživatelů a potom zvolte **Přidat** &gt; **Další**.

10. Na stránce **Akce nasazení** vyberte **Dostupná instalace** ze sloupce **Schválení** pro vaši skupinu.

11. Klikněte na **Dokončit**.

## <a name="install-the-skype-app"></a>Instalace aplikace Skype
Na mobilním zařízení otevřete portál společnosti, zvolte **Aplikace** a pak nainstalujte Microsoft Skype.

Tím končí příručka pro správu mobilních zařízení v Intune, ale další informace o Intune můžete získat kliknutím na odkazy v části Další kroky.
## <a name="next-steps"></a>Další kroky
Získejte další informace o ostatních [možnostech Intune](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md).

Přečtěte si o [běžných způsobech použití Intune](common-ways-to-use-intune.md).

Přejděte na [placené předplatné](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md).

