---
title: "Aplikace pro iOS se zásadami ochrany aplikací | Intune Azure Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Toto téma popisuje, co očekávat, když aplikaci pro iOS spravují zásady ochrany aplikací."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 5a4ce6d6248378ba48cddeaefb941c139dd990f6
ms.lasthandoff: 02/18/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací
[!INCLUDE[azure_preview](../includes/azure_preview.md)] Toto téma popisuje činnosti uživatelů aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jenom v případě, že se aplikace používají v pracovním kontextu: třeba pro přístup k aplikacím pomocí pracovního účtu nebo pro přístup k souborům uloženým v umístění OneDrivu pro danou společnost.
##  <a name="accessing-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se koncovému uživateli při prvním použití aplikace výzva k restartování aplikace.  Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování. Následující snímek obrazovky ukazuje toto chování při použití aplikace Skype:


![Snímek obrazovky zařízení s iOSem, na kterém je výzva k zadání kódu PIN](../media/ios-pin-prompt.png)

U zařízení, která jsou **zaregistrovaná pro správu v Intune**, se koncovému uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná:

![Snímek obrazovky zařízení s iOSem, na kterém je zpráva „Spravované vaší společností“ a výzva k zadání kódu PIN](../media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Použití aplikací s podporou víc identit

Zásady ochrany aplikací se použijí jenom při použití aplikace v pracovním kontextu, takže v závislosti na kontextu (pracovní nebo osobní účely) se může chování aplikací lišit.  

U aplikací podporujících více identit použije Intune zásady ochrany aplikací jenom v případě, že koncový uživatel používá danou aplikaci v pracovním kontextu.  Koncovému uživateli se například při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN.  U **aplikace Outlook** se koncovému uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** k tomu dojde, když koncový uživatel použije pracovní účet.  U aplikací Microsoft **Word**, **PowerPoint* a **Excel** k tomu dojde, když koncový uživatel přistupuje k dokumentům uloženým v umístění OneDrive pro firmy pro danou společnost.
##  <a name="managing-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.
  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** neblokují druhý uživatelský účet, ale na tento druhý uživatelský účet nemají zásady ochrany aplikací vliv.  

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.

* Pokud zařízení obsahuje před nasazením zásad ochrany aplikací víc uživatelských účtů, budou zásady ochrany aplikací služby Intune spravovat ten účet, u kterého se zásady ochrany aplikací nasadí dřív.


Přečtěte si níže uvedený ukázkový scénář, abyste lépe pochopili, jak se pracuje s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech, **společnosti X** a **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musíte uživatelský účet přidružený ke společnosti X odebrat.
### <a name="adding-a-second-account"></a>Přidání druhého účtu

Pokud používáte zařízení s iOSem, může se při pokusu o přidání druhého pracovního účtu na stejném zařízení zobrazit zpráva o blokování.  Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

![Snímek obrazovky s dialogem obsahujícím zprávu o blokování a možnosti Ano a Ne](../media/ios-switch-user.PNG)

## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-android-apps.md)
### <a name="see-also"></a>Související témata
[Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)
