---
title: "Aplikace pro iOS se zásadami ochrany aplikací | Dokumentace Microsoftu"
description: "Toto téma popisuje, co můžete očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 92a91fab353c78c751ae5eb25c9853df5cbcfe53
ms.contentlocale: cs-cz
ms.lasthandoff: 05/31/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Toto téma popisuje činnosti uživatelů při používání aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jen v případě, že se aplikace používají v pracovním kontextu, například když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo používá soubory, které jsou uložené na firemním OneDrivu.

##  <a name="access-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se uživateli při prvním použití aplikace výzva k jejímu restartování. Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na zařízeních, která jsou **zaregistrovaná pro správu přes Intune**, se uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná.

##  <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když jsou aplikace použité v pracovním kontextu.  

Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu.  U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

- Přečtěte si další informace o aplikacích, které podporují [MAM a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

Zásady ochrany aplikací se používají jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

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
