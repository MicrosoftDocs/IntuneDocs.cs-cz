---
title: "Aplikace pro iOS se zásadami MAM | Microsoft Intune"
description: "Toto téma popisuje, co máte očekávat, když je vaše aplikace pro iOS spravovaná pomocí zásad správy mobilních aplikací."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Co očekávat, když ke správě své aplikace pro iOS používáte zásady MAM
 Toto téma popisuje činnost uživatele aplikací se zásadami MAM. Zásady správy mobilních aplikací (MAM) se použijí jenom v případě, že se aplikace používají k práci: třeba pro přístup k aplikacím pomocí pracovního účtu nebo pro přístup k souborům uloženým v umístění OneDrive pro danou společnost.
##  Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se koncovému uživateli při prvním použití aplikace výzva k restartování aplikace.  Restartování se vyžaduje, aby se pro aplikaci mohly použít zásady MAM. Následující snímek obrazovky ukazuje toto chování při použití aplikace Skype:


![Snímek obrazovky zařízení s iOS, na kterém je výzva k zadání kódu PIN](../media/appmanagement/iOS_AppPINPrompt.png)

U zařízení, která jsou **zaregistrovaná pro správu v Intune**, se koncovému uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná:

![Snímek obrazovky zařízení s iOS, na kterém je zpráva „Spravované vaší společností“ a výzva k zadání kódu PIN](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Použití aplikací s podporou víc identit

Zásady MAM se použijí jenom při použití aplikace k práci, takže v závislosti na kontextu (pracovní nebo osobní účely) se může chování aplikací lišit.  

U aplikací podporujících více identit Intune použije zásady MAM jenom v případě, že koncový uživatel používá danou aplikaci k práci.  Koncovému uživateli se například při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN.  U **aplikace Outlook** se koncovému uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** k tomu dojde, když koncový uživatel použije pracovní účet.  U aplikací Microsoft **Word**, **PowerPoint* a **Excel** k tomu dojde, když koncový uživatel přistupuje k dokumentům uloženým v umístění OneDrive pro firmy pro danou společnost.
##  Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad MAM jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale zásady ovlivňují jenom prvního uživatele, který získá zásady MAM.
  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** druhý uživatelský účet neblokují, ale na tento druhý uživatelský účet nemají zásady MAM vliv.  

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.

* Pokud zařízení obsahuje před nasazením zásad MAM víc uživatelských účtů, bude zásadami MAM služby Intune spravovaný ten účet, do kterého se zásady MAM nasadí dřív.


Přečtěte si níže uvedený ukázkový scénář, abyste lépe pochopili, jak se pracuje s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech, **společnosti X** a **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad MAM. **Společnost X** nasadí zásady MAM **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady MAM, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby byl účet přidružený ke společnosti Y spravovaný pomocí zásad MAM, musíte odebrat uživatelský účet přidružený ke společnosti X.
### Přidání druhého účtu

Pokud používáte zařízení s iOS, může se při pokusu o přidání druhého pracovního účtu na stejném zařízení zobrazit zpráva o blokování.  Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

![Snímek obrazovky s dialogem obsahujícím zprávu o blokování a možnosti Ano a Ne](../media/AppManagement/iOS_SwitchUser.PNG)
## Další kroky
[Co očekávat, když ke správě své aplikace pro Android používáte zásady MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Viz taky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


