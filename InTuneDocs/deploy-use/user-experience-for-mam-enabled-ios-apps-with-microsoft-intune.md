---
title: "Aplikace pro iOS se zásadami ochrany aplikací | Dokumentace Microsoftu"
description: "Toto téma popisuje, co můžete očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 665d3347636d5ec0c698ffb93b768028c9d59ce3
ms.openlocfilehash: fba18027039a0e49c5301f9d1a16947e97408034
ms.lasthandoff: 03/07/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Toto téma popisuje uživatelské prostředí u aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jen v případě, že se aplikace používají v pracovním kontextu, například když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo používá soubory, které jsou uložené na firemním OneDrivu.

##  <a name="access-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se uživateli při prvním použití aplikace výzva k jejímu restartování.  Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na zařízeních, která jsou **zaregistrovaná pro správu přes Intune**, se uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná.

##  <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Zásady ochrany aplikací se používají jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

 Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu.  U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

##  <a name="manage-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací jen na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný. Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.
  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** neblokují druhý uživatelský účet, ale na tento druhý uživatelský účet nemají zásady ochrany aplikací vliv.  

  * U aplikací **OneDrive** a **Outlook** můžete používat jenom jeden pracovní účet. U těchto aplikací nejde přidat více pracovních účtů. Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.

* Pokud zařízení obsahuje před nasazením zásad ochrany aplikací několik uživatelských účtů, bude zásadami ochrany aplikací služby Intune spravován ten účet, u kterého se zásady ochrany aplikací nasadí dřív.


Přečtěte si následující ukázkový scénář, abyste lépe pochopili, jak se pracuje s více uživatelskými účty.

Uživatel A pracuje ve dvou společnostech – ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby byl účet přidružený ke společnosti Y spravován pomocí zásad ochrany aplikací, musíte odebrat uživatelský účet přidružený ke společnosti X.

### <a name="add-a-second-account"></a>Přidání druhého účtu

Pokud používáte zařízení s iOSem, může se při pokusu o přidání druhého pracovního účtu na zařízení zobrazit zpráva o blokování. Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Viz taky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

