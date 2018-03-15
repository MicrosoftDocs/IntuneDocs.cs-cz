---
title: "Aplikace pro iOS a zásady jejich ochrany"
titlesuffix: Microsoft Intune
description: "Zjistěte, co můžete očekávat od aplikace pro iOS, která má zásady ochrany."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13833d41603e24e4471f0bb5fdda40d000f29a34
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Přečtěte si informace pro uživatelské prostředí u aplikací iOS se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jenom v případě, že se aplikace používají k práci. Například při přístupu k aplikaci pomocí pracovního účtu nebo když zobrazujete soubory uložené na OneDrivu vaší společnosti.
##  <a name="accessing-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se uživateli při prvním použití aplikace výzva k restartování aplikace.  Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování. Následující snímek obrazovky ukazuje toto chování při použití aplikace Skype:


![Snímek obrazovky zařízení s iOSem, na kterém je výzva k zadání kódu PIN](./media/ios-pin-prompt.png)

U zařízení, která jsou **zaregistrovaná pro správu v Intune**, se uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná:

![Snímek obrazovky zařízení s iOSem, na kterém je zpráva „Spravované vaší společností“ a výzva k zadání kódu PIN](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Použití aplikací s podporou víc identit

Zásady ochrany aplikací se projeví, jenom když se uživatel pokusí o přístup k pracovním datům.  Když chce uživatel použít aplikaci pro osobní účely, může se aplikace chovat jinak. 

Pro aplikace, které podporují více identit, použije Intune zásady ochrany aplikací, jenom pokud uživatel zobrazuje pracovní data.  Uživateli se například může zobrazit výzva k zadání kódu PIN.  V **aplikaci Outlook** se výzva zobrazí uživateli při spuštění. V **aplikaci OneDrive** se zobrazí výzva, když uživatel použije pracovní účet.  V aplikaci Microsoft **Word**, **PowerPoint** a **Excel** se zobrazí výzva, když uživatel zobrazuje dokumenty na OneDrivu.
##  <a name="managing-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.
  * **Microsoft Word**, **Excel** a **PowerPoint** nebudou blokovat přístup k dalším uživatelským účtům. Na tyto uživatelské účty se ale nebudou vztahovat zásady ochrany aplikací.

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Můžete však ze zařízení odebrat uživatele a pak přidat jiného.

* Před nasazením zásad ochrany aplikací může mít zařízení několik existujících uživatelských účtů. V takovém případě spravují zásady ochrany aplikací Intune první účet, na který jsou nasazené zásady ochrany aplikací.


Přečtěte si následující ukázkový scénář, kde se dozvíte, jak Intune zachází s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech: ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby uživatelský účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musí uživatel A odebrat uživatelský účet společnosti X.
### <a name="adding-a-second-account"></a>Přidání druhého účtu

Pokud používáte zařízení s iOSem, může se při pokusu o přidání druhého pracovního účtu na stejném zařízení zobrazit zpráva o blokování.  Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

![Snímek obrazovky s dialogem obsahujícím zprávu o blokování a možnosti Ano a Ne](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Viz taky
[Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)
