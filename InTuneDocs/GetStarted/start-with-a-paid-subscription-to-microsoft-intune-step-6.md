---
title: "Vytvoření zásad a publikování aplikace | Microsoft Intune"
description: "Vytvořte zásady a publikujte ukázkovou aplikaci pro předplatné Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: 748df2b7af8cf1679f31435f89730170ca723dc4


---

# Vytvoření zásad a publikování aplikace
Intune nabízí nastavení, které pomáhá řídit nastavení zabezpečení na mobilních zařízeních, spravovat nastavení brány Windows Firewall a Endpoint Protection pro počítače a nasazovat aplikace. Další informace najdete v tématech [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) a [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Pomocí Intune můžete provádět dva typy instalace aplikací. První je **požadovaná instalace**, která aplikaci automaticky nasadí do spravovaných počítačů. Druhá je **dostupná instalace**, která nasadí aplikaci nebo odkaz na aplikaci na Portálu společnosti Intune, aby si mohli uživatelé vybrat, jestli ji chtějí mít nainstalovanou na počítači nebo na mobilním zařízení.

V následujícím postupu nastavíte zásady konfigurace mobilních zařízení a zásady brány firewall počítače s Windows a nakonfigurujete Skype jako instalaci dostupnou pro mobilní zařízení po jejich registraci.

> [!TIP]
> Po přidání a nasazení nových zásad zdědí všichni uživatelé nebo zařízení ve skupině, do které jste zásadu nasadili, tato nastavení jako svoje základní zásady. Podrobnosti těchto zásad můžete později kdykoli zkontrolovat nebo upravit v pracovním prostoru zásad.


## Vytvoření a nasazení zásady konfigurace mobilních zařízení

1.  Otevřete [konzolu pro správu Intune](https://manage.microsoft.com/).

2.  V levém podokně vyberte ikonu **Zásady**.

    ![admin-console-policy-workspace](./media/policy.png)

3.  V seznamu **Úlohy** na stránce **Přehled zásad** vyberte **Přidat zásadu**.

4.  V seznamu zásad rozbalte platformu, pro kterou chcete vytvořit zásadu, a pak vyberte **Všeobecná konfigurace** > **Vytvoření a nasazení zásad s doporučeným nastavením** > **Vytvořit zásadu**.

> [!NOTE]
> Vzhledem k tomu, že existuje mnoho možností, ze kterých můžete vybírat, nejsou žádná doporučená nastavení pro zásady konfigurace zařízení. Musíte vytvořit vlastní zásadu konfigurace zařízení.


5.  Při zobrazení výzvy **Vyberte skupiny, do kterých chcete nasadit tuto zásadu** zvolte skupinu v seznamu dostupných skupin a potom vyberte **Přidat** > **OK**.

Vaše zásada se zobrazí v seznamu zásad konfigurace a byla nasazena do skupiny **Uživatelé Intune**. Nastavení zásady zobrazíte tak, že na zásadu dvakrát kliknete.

## Publikování aplikace Skype pro mobilní zařízení

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) vyberte ikonu **Aplikace** a pak zvolte **Aplikace** > **Přidat aplikaci**. Po zobrazení výzvy zadejte své přihlašovací údaje do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > Při prvním spuštění **Intune Software Publisheru** může instalace aplikace chvíli trvat.

2.  Přečtěte si upozornění zabezpečení a vyberte **Spustit**.

3.  Na stránce **Než začnete** vyberte **Další**.

4.  Na stránce **Instalace softwaru** v části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení** vyberte **Externí odkaz**.

5.  Zadejte externí odkaz pro software v části **Zadejte adresu URL** a vyberte **Další**. Ujistěte se, že adresa URL začíná **http://**. Pro aplikaci Skype použijte odkaz dole odpovídající platformě mobilního zařízení, kterou používáte:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 nebo Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Na stránce **Popis softwaru** zadejte informace k softwaru, které mají uživatelé vidět na portálu společnosti, a vyberte **Další**. Dostupná jsou tato nastavení (tento příklad se týká Skypu):

    -   **Vydavatel:** Zadejte název vydavatele (Microsoft).

    -   **Název:** Zadejte **Skype**

    -   **Popis:** Zadejte popis softwaru, třeba **Komunikační aplikace Skype**

    -   **Kategorie:** Vyberte kategorii, která nejlíp odpovídá tomuto softwaru, třeba **Spolupráce**

    -   **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti:** Pokud vyberete tuto možnost, zobrazí se tato aplikace na portálu společnosti na mobilních zařízeních přednostně.

    -   **Ikona:** Vyberte, jestli chcete softwaru přiřadit ikonu. Maximální velikost volitelné ikony je 250 x 250 pixelů a doporučená velikost je 32 x 32 pixelů.

7.  Na stránce **Souhrn** zkontrolujte zadané informace o softwaru a vyberte **Odeslat**. Průvodce ukončíte výběrem **Zavřít**.

8.  V [konzole pro správu Intune](https://manage.microsoft.com/) vyberte **Aplikace** > **Aplikace** > **Skype** > **Spravovat nasazení**.

9. Na stránce **Vybrat skupiny** vyberte **Uživatelé Intune** pro nasazení softwaru do této skupiny uživatelů a potom vyberte **Přidat** > **Další**.

10. Na stránce **Akce nasazení** vyberte **Dostupná instalace** ze sloupce **Schválení** pro vaši skupinu.

11. Klikněte na **Dokončit**.

Aplikace Skype je teď dostupná k instalaci na mobilních zařízeních z portálu společnosti, ale nejdřív je potřeba na počítačích a mobilních zařízeních nainstalovat software [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].


### Další kroky
Gratulujeme! Právě jste dokončili krok 6 *úvodní příručky Intune*.

>[!div class="step-by-step"]

>[&larr; **Organizace uživatelů a zařízení**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Přizpůsobení portálu společnosti** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Oct16_HO4-->


