---
title: Postup resetování hesla z webu Portál společnosti | Dokumentace Microsoftu
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e973e18a79c18af6b201194fc1a6534da5fa38a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838032"
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Resetování hesla zařízení z webu Portál společnosti

Pokud ztratíte kód PIN nebo heslo zařízení, můžete použít k jeho resetování [web Portál společnosti](https://portal.manage.microsoft.com).  

Používáte-li zařízení zaregistrované firmou, nemusí se vám možnost pro resetování hesla zobrazovat. V takovém případě kontaktujte svou firemní podporu, aby heslo resetovala za vás.

   > [!NOTE]
   > U hesel pro zařízení s Androidem 7.0 nebo novějším hesla resetovat nemůžete. Pokud heslo zapomenete, musíte zařízení obnovit do továrního nastavení. 

## <a name="reset-your-passcode"></a>Postup resetování hesla

1.  Otevřete [web Portál společnosti](https://portal.manage.microsoft.com) a vyberte tlačítko __nabídky__ > __Zařízení__.  

2. Vyberte zařízení, jehož heslo potřebujete resetovat.  

    ![Snímek obrazovky stránky Zařízení se dvěma dlaždicemi, které zobrazují neznámá zařízení s obecným názvem. Šedý banner pod zařízeními vyzývá uživatele k identifikaci používaného zařízení nebo přidání nového.](./media/rename-reset-device-step2-1808.png) 

3. Zvolte **Resetovat heslo**. Pokud se v horní části stránky možnost pro heslo nezobrazuje, vyberte **Více (…)** > **Resetovat heslo**.   

   ![Stránka podrobností o zařízení pro vybrané zařízení na webu Portál společnosti. V horní části stránky se nacházejí odkazy Přejmenovat, Odebrat, Resetovat zařízení, Resetovat heslo a Vzdálené uzamčení. ](./media/rename-reset-device-1808.png)   

    ![Přiblížená ikona Více zvýrazněná červenou šipkou](./media/rename-reset-device-step3-more-1808.png)  

4. Po zobrazení výzvy klikněte na **Odhlásit se**. Po zobrazení další výzvy se znovu přihlaste. Na web Portál společnosti se musíte přihlásit do pěti minut, jinak se heslo zařízení neresetuje.  

   > [!NOTE]
   > Opětovné přihlášení se vyžaduje pro potvrzení identity. Slouží jako ochrana před škodlivými pokusy o resetováním hesla.

   ![Ukázkové snímky obrazovky s výzvou k odhlášení z webu Portál společnosti Tlačítka pro vstup uživatele jsou Odhlásit se a Zrušit.](./media/iwp-reset-passcode-popup-1808.png)

5. Zobrazí se zpráva s upozorněním, že stávající heslo zařízení bude odebráno. Potvrďte kliknutím na **Resetovat heslo**.  
    > [!WARNING]
    > Po resetování hesla je většina osobních a firemních dat dostupná každému, kdo má fyzický přístup k zařízení. Pokud zařízení nemáte momentálně ve svém vlastnictví, resetování neprovádějte.  

   ![Ukázkový snímek obrazovky s druhou zprávou zobrazovanou při resetování hesla. Obsahuje odkaz na dokumentaci s dalšími informacemi o nastavení nového hesla a samostatná tlačítka pro resetování a zrušení.](./media/iwp-reset-passcode-popup2-1808.png) 

6. Pokud resetujete heslo zařízení s iOSem, stávající heslo se odebere. Na zařízeních s Windows a Androidem se vytvoří dočasné heslo pro odemknutí zařízení a nastavení nového. 

   > [!NOTE]
   > Dočasné heslo pro zařízení s Windows a Androidem najdete na webu Portál společnosti na stránce detailů zařízení. Pokyny pro jednotlivé operační systémy najdete v části [Nastavení nového hesla](reset-your-passcode-cpwebsite.md#set-up-a-new-passcode).  
   
7. Na zařízení přejděte na **Nastavení** a změňte dočasné heslo. 

8. V pravé horní části webu Portál společnosti se zobrazí příznak. Kliknutím si přečtěte upozornění a potvrďte, že se heslo úspěšně resetovalo.  

## <a name="set-up-a-new-passcode"></a>Nastavení nového hesla  

V této části najdete chování při resetování hesla a vytvoření dočasného hesla pro jednotlivé platformy.  

**Android**: Odebere existující heslo a vytvoří dočasné heslo tvořené písmena a číslice.

**iOS**: Odebere existující heslo a nevytvoří dočasné heslo. Pokud pro otevírání zařízení nebo nákupy používáte snímač otisku prstu Touch ID, je potřeba ho nastavit znovu.  

**Windows 10 Mobile**: Odebere existující heslo a vytvoří dočasné heslo tvořené písmena a číslice. Pokud je nastaveno rozpoznávání obličeje Windows Hello, bude na zařízení i nadále fungovat.
    
**Windows Phone 8.1**: Odebere existující heslo a vytvoří dočasné heslo tvořené čísla.  

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
