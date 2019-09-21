---
title: Odesílání vlastních oznámení uživatelům pomocí Microsoft Intune
titleSuffix: Microsoft Intune
description: Použití Intune k vytváření a odesílání vlastních nabízených oznámení uživatelům zařízení s iOS a Androidem
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ae28db2f7f0488318a8c83774db48fa0f133d85
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163168"
---
# <a name="send-custom-notifications-in-intune"></a>Odesílání vlastních oznámení v Intune  

Pomocí Microsoft Intune můžete odesílat vlastní oznámení uživatelům spravovaných zařízení s iOS a Androidem. Tyto zprávy se zobrazí jako standardní nabízená oznámení z aplikace Portál společnosti a z aplikace Microsoft Intune na zařízení uživatele, stejně jako oznámení z jiných aplikací na zařízení. Zařízení macOS a Windows nepodporují vlastní oznámení Intune.   

Vlastní zprávy s oznámením obsahují krátký nadpis a tělo zprávy o 500 nebo méně znaků. Tyto zprávy lze přizpůsobit pro jakýkoli obecný účel komunikace.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Běžné scénáře odesílání vlastních oznámení  

- Upozorněte všechny zaměstnance změny v plánu, jako jsou uzávěry při sestavování z důvodu inclement počasí.
- Pošle uživateli oznámení o jednom zařízení, aby mohl sdělit naléhavou žádost, třeba restartování zařízení, aby se instalace aktualizace dokončila. 

## <a name="considerations-for-using-custom-notifications"></a>Předpoklady pro používání vlastních oznámení

**Konfigurace zařízení** 

- Aby uživatelé mohli přijímat vlastní oznámení, musí mít zařízení nainstalovanou aplikaci Portál společnosti nebo aplikaci Microsoft Intune. Musí mít taky nakonfigurovaná oprávnění, aby mohla aplikace Portál společnosti nebo aplikace Microsoft Intune posílat nabízená oznámení. V případě potřeby se aplikace Portál společnosti a aplikace Microsoft Intune můžou vyzvat uživatele, aby povolili oznámení.  
- V Androidu je Služby Google Play požadovaná závislost.  
- Zařízení musí být zaregistrované v MDM.

**Oprávnění**:
- Aby bylo možné odesílat oznámení do skupin, musí mít váš účet v Intune následující oprávnění RBAC: > **Aktualizace**organizace.
- Aby bylo možné odesílat oznámení do zařízení, váš účet musí mít v Intune následující oprávnění RBAC: *Vzdálené úlohy* > **odesílají vlastní oznámení**.

**Vytváření oznámení**:  
- Pokud chcete vytvořit zprávu, použijte účet, ke kterému je přiřazená role Intune, která zahrnuje oprávnění **aktualizace** pro **organizaci**. Postup přiřazení oprávnění uživateli najdete v tématu [přiřazení rolí](role-based-access-control.md#role-assignments) .  
- Vlastní oznámení jsou omezená na 50 znaků a zprávy 500-Character.  
- Intune neukládá odeslané zprávy. Chcete-li znovu odeslat zprávu, je nutné tuto zprávu znovu vytvořit.  
- Do skupin za hodinu můžete poslat až 25 zpráv. Toto omezení je na úrovni tenanta. Toto omezení se nevztahuje na odesílání oznámení jednotlivcům.
- Když odesíláte zprávy do jednotlivých zařízení, můžete do stejného zařízení poslat až 10 zpráv za hodinu. 
- Oznámení můžete odesílat více uživatelům nebo zařízením přiřazením oznámení do skupin. Při použití skupin se může každé oznámení směrovat přímo na 25 skupin. Vnořené skupiny se do tohoto součtu nepočítají.  

  Skupiny můžou obsahovat uživatele nebo zařízení, ale zprávy se odesílají jenom uživatelům a každému zařízení s iOS nebo Androidem, které uživatel zaregistroval.  
- Oznámení můžete odesílat do jediného zařízení. Místo používání skupin vyberte zařízení a pak použijte [akci vzdáleného zařízení](device-management.md#available-device-actions) k odeslání vlastního oznámení.  

**Doručení**:  
- Intune pošle zprávy do aplikace Portál společnosti uživatelů nebo do aplikace Microsoft Intune, která pak vytvoří nabízené oznámení. Aby bylo možné oznámení na zařízení přidat, nemusí být uživatelé přihlášeni do aplikace.  
- Intune i aplikace Portál společnosti a aplikace Microsoft Intune nemůžou zaručit doručení vlastního oznámení. Vlastní oznámení se můžou zobrazovat i po několika hodinách, pokud je to u všech, takže by se nemuseli používat pro naléhavé zprávy.  
- Vlastní oznamovací zprávy z Intune se na zařízeních zobrazují jako standardní nabízená oznámení. Pokud je aplikace Portál společnosti v zařízení se systémem iOS otevřená při přijetí oznámení, zobrazí se v aplikaci oznámení místo nabízeného oznámení.  
- Vlastní oznámení můžete zobrazit na zamykací obrazovce na zařízeních s iOS i Androidem v závislosti na nastavení zařízení.  
- V zařízeních s Androidem můžou mít další aplikace přístup k datům ve vlastních oznámeních. Nepoužívejte je pro citlivou komunikaci.  
- Uživatelé zařízení, kteří se nedávno zaregistrovali, nebo uživatelé, kteří byli odebráni ze skupiny, můžou dál dostávat vlastní oznámení, které se později pošle do této skupiny.  Podobně platí, že pokud přidáte uživatele do skupiny po odeslání vlastního oznámení do skupiny, je možné, že nově přidaná zpráva byla přijata k přijetí dříve odeslané zprávy s oznámením.  

## <a name="send-a-custom-notification-to-groups"></a>Odeslání vlastního oznámení do skupin  

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973) se k Intune pomocí účtu, který má oprávnění k vytváření a odesílání oznámení, a v **zařízení** > **odesílají vlastní oznámení**.  

2. Na kartě základy zadejte následující příkaz a pokračujte výběrem **Další** .  
   - **Title** – zadejte název tohoto oznámení. Názvy jsou omezeny na 50 znaků.  
   - **Tělo** – zadejte zprávu. Zprávy jsou omezené na 500 znaků.

   ![Vytvoření vlastního oznámení](./media/custom-notifications/custom-notifications.png)  

3. Na kartě **přiřazení** vyberte skupiny, kterým chcete poslat toto vlastní oznámení, a pak pokračujte výběrem další.  

4. Na kartě **Revize + vytvořit** zkontrolujte informace a až budete připraveni odeslat oznámení, vyberte **vytvořit**.  

Intune zpracovává zprávy, které vytvoříte hned. Jediným potvrzením, že se zpráva poslala, je oznámení Intune, které potvrdí, že se poslalo vlastní oznámení.  

![Potvrzení odeslaného oznámení](./media/custom-notifications/notification-sent.png)  

Intune nesleduje vlastní oznámení, která odesíláte, a zařízení neprotokolují příjem mimo centrum oznámení zařízení.  

## <a name="send-a-custom-notification-to-a-single-device"></a>Odeslání vlastního oznámení na jedno zařízení  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) pomocí účtu, který má oprávnění k vytváření a odesílání oznámení, a pak na **zařízení** > **všechna zařízení**.  

2. Vyberte zařízení, pro které chcete odeslat oznámení.  

3. Na stránce **Přehled** zařízení vyberte **... Další** možnost v levé horní části stránky.  

4. Vyberte akci **Odeslat vlastní oznámení** a otevřete podokno *Odeslat vlastní oznámení* , kde zadáte následující podrobnosti zprávy:  

   - **Title** – zadejte název tohoto oznámení. Názvy jsou omezeny na 50 znaků.  
   - **Tělo** – zadejte zprávu. Zprávy jsou omezené na 500 znaků.  

5. Vyberte **Odeslat** a odešlete tak vlastní oznámení do zařízení. Na rozdíl od oznámení, která odesíláte do skupin, nekonfigurujte přiřazení ani před odesláním zprávy zkontrolovat.  

Intune zpracovává zprávu hned. Jediným potvrzením, že zpráva byla odeslána, je oznámení Intune, které obdržíte v konzole nástroje, ve kterém se zobrazí text zprávy, kterou jste odeslali.  

## <a name="receive-a-custom-notification"></a>Přijetí vlastního oznámení  

Na zařízení uživatelé uvidí vlastní oznamovací zprávy, které Intune odesílají jako standardní nabízené oznámení z aplikace Portál společnosti nebo z aplikace Microsoft Intune. Tato oznámení jsou podobná nabízeným oznámením, která uživatelé dostanou z jiných aplikací na zařízení.  

Pokud je v zařízeních se systémem iOS po přijetí oznámení otevřená aplikace Portál společnosti, zobrazí se v aplikaci oznámení místo nabízeného oznámení.  

Oznámení zůstane, dokud ho uživatel nezavře.  

## <a name="next-steps"></a>Další kroky  

[Správa zařízení](device-management.md)
