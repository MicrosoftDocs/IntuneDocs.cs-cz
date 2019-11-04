---
title: Aplikace pro iOS a zásady jejich ochrany
description: Toto téma popisuje, co můžete očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1a3dcd7068a004f94b97b5ec6c43c609662a76d
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414558"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací

 Toto téma popisuje činnost koncového uživatele při použití aplikací, které používají zásady ochrany aplikací. Zásady ochrany aplikací se použijí jen v případě, že se aplikace používají v pracovním kontextu, například když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo používá soubory, které jsou uložené na firemním OneDrivu.

## <a name="access-apps"></a>Přístup k aplikacím

Pokud zařízení **není zaregistrované v Intune**, zobrazí se uživateli při prvním použití aplikace výzva k jejímu restartování. Aby se pro aplikaci mohly použít zásady ochrany aplikací, je nutné restartování.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Na zařízeních, která jsou **zaregistrovaná pro správu přes Intune**, se uživateli zobrazí zpráva, že jeho aplikace je teď spravovaná.

## <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Aplikace, které podporují více identit, umožňují pro přístup ke stejným aplikacím používat různé účty (pracovní a osobní). Zásady ochrany aplikací se použijí, jen když jsou aplikace použité v pracovním kontextu.  

Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu.  U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

Zásady ochrany aplikací se používají jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

## <a name="manage-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Aplikace s podporou více identit umožňují uživatelům přidat více účtů.  Aplikace Intune podporuje jenom jeden spravovaný účet.  Aplikace Intune neomezuje počet nespravovaných účtů.

Když je v aplikaci spravovaný účet:

- Pokud se uživatel pokusí přidat druhý spravovaný účet, zobrazí se mu výzva k výběru spravovaného účtu, který se má použít.  Druhý účet se odebere.
- Pokud správce IT přidá zásady pro druhý existující účet, zobrazí se uživateli výzva k výběru spravovaného účtu, který se má použít.  Druhý účet se odebere.

Přečtěte si následující ukázkový scénář, abyste lépe pochopili, jak se pracuje s více uživatelskými účty.

Uživatel A funguje pro dvě společnosti –**společnosti X** a **firmu Y**. Uživatel A má pro každou společnost pracovní účet a obě služby používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **před** **firmou Y**. Účet, který je přidružený ke **společnosti X** , získá nejdřív zásady ochrany aplikací. Pokud chcete, aby uživatelský účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musíte odebrat uživatelský účet přidružený ke společnosti X a přidat uživatelský účet přidružený ke společnosti Y.

### <a name="add-a-second-account"></a>Přidání druhého účtu

Pokud používáte zařízení s iOSem, může se při pokusu o přidání druhého pracovního účtu na zařízení zobrazit zpráva o blokování. Účty se zobrazí a můžete zvolit účet, který chcete odebrat.

## <a name="next-steps"></a>Další kroky

[Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](end-user-mam-apps-android.md)
