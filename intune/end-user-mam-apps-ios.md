---
title: "Aplikace pro iOS a zásady jejich ochrany"
description: "Toto téma popisuje, co můžete očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0a9d17f8066ddd16c06322cf9cc64457daff87f1
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 Toto téma popisuje činnosti uživatelů při používání aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jen v případě, že se aplikace používají v pracovním kontextu, například když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo používá soubory, které jsou uložené na firemním OneDrivu.

##  <a name="access-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se uživateli při prvním použití aplikace výzva k jejímu restartování. Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na zařízeních, která jsou **zaregistrovaná pro správu přes Intune**, se uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná.

##  <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když jsou aplikace použité v pracovním kontextu.  

Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu.  U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

Zásady ochrany aplikací se používají jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

##  <a name="manage-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Aplikace s podporou více identit umožňují uživatelům přidat více účtů.  Aplikace Intune podporuje jenom jeden spravovaný účet.  Aplikace Intune neomezuje počet nespravovaných účtů.

Když je v aplikaci spravovaný účet:
*   Pokud se uživatel pokusí přidat druhý spravovaný účet, zobrazí se mu výzva k výběru spravovaného účtu, který se má použít.  Druhý účet se odebere.
*   Pokud správce IT přidá zásady pro druhý existující účet, zobrazí se uživateli výzva k výběru spravovaného účtu, který se má použít.  Druhý účet se odebere.

Přečtěte si následující ukázkový scénář, abyste lépe pochopili, jak se pracuje s více uživatelskými účty.

Uživatel A pracuje ve dvou společnostech – ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací jako první. Pokud chcete, aby uživatelský účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musíte odebrat uživatelský účet přidružený ke společnosti X a přidat uživatelský účet přidružený ke společnosti Y.

### <a name="add-a-second-account"></a>Přidání druhého účtu

Pokud používáte zařízení s iOSem, může se při pokusu o přidání druhého pracovního účtu na zařízení zobrazit zpráva o blokování. Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](end-user-mam-apps-android.md)
