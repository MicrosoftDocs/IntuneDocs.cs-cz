---
title: Odesílání vlastních oznámení uživatelům pomocí Microsoft Intune
titleSuffix: Microsoft Intune
description: Použití Intune k vytváření a odesílání vlastních nabízených oznámení uživatelům zařízení s iOS a Androidem
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/18/2019
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
ms.openlocfilehash: 3a4314abec83bc31cd6fe178873ba5bce7bf1a0c
ms.sourcegitcommit: 864fdf995c2b41f104a98a7e2665088c2864774f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68680101"
---
# <a name="send-custom-notifications-in-intune"></a>Odesílání vlastních oznámení v Intune  

Pomocí Microsoft Intune můžete odesílat vlastní oznámení uživatelům spravovaných zařízení s iOS a Androidem. Tyto zprávy se zobrazí jako standardní nabízená oznámení z aplikace Portál společnosti v zařízení uživatele, stejně jako oznámení z jiných aplikací na zařízení. Zařízení s Windows nepodporují vlastní oznámení Intune.   

Vlastní zprávy s oznámením obsahují krátký nadpis a tělo zprávy o 500 nebo méně znaků. Tyto zprávy lze přizpůsobit pro jakýkoli obecný účel komunikace.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Běžné scénáře odesílání vlastních oznámení  

- Použijte vlastní oznámení pro upozornění konkrétních uživatelů o nové aplikaci, která je k dispozici v Portál společnosti.  
- Upozorněte všechny zaměstnance změny v plánu, jako jsou uzávěry při sestavování v důsledku inclement počasí.  

## <a name="considerations-for-using-custom-notifications"></a>Předpoklady pro používání vlastních oznámení  

**Konfigurace zařízení**:  
- Aby mohli uživatelé přijímat vlastní oznámení, musí mít zařízení nainstalovanou aplikaci Portál společnosti. Musí mít taky nakonfigurovaná oprávnění, aby mohla aplikace Portál společnosti posílat nabízená oznámení. Portál společnosti vyzve uživatele, aby povolili oznámení při každém instalaci nebo aktualizaci.  
- V Androidu je Služby Google Play požadovaná závislost.  
- Zařízení musí být zaregistrované v MDM.

**Vytváření oznámení**:  
- Pokud chcete vytvořit zprávu, použijte účet, ke kterému je přiřazená role Intune, která zahrnuje oprávnění **aktualizace** pro **organizaci**. Postup přiřazení oprávnění uživateli najdete v tématu [přiřazení rolí](role-based-access-control.md#role-assignments) .  
- Vlastní oznámení jsou omezená na 50 znaků a zprávy 500-Character.  
- Intune neukládá odeslané zprávy. Chcete-li znovu odeslat zprávu, je nutné tuto zprávu znovu vytvořit.  
- Můžete poslat až 25 zpráv za hodinu. Toto omezení je na úrovni tenanta.  
- Každé oznámení může přímo cílit až na 25 skupin. Vnořené skupiny se do tohoto součtu nepočítají.  
- Skupiny můžou obsahovat uživatele nebo zařízení, ale zprávy se odesílají jenom uživatelům a odesílají se do každého zařízení s iOS nebo Androidem, které uživatel zaregistroval.  

**Doručení**:  
- Po odeslání oznámení Intune pokusy o doručení po dobu až jedné hodiny.  
- Intune pošle zprávy do aplikace Portál společnosti uživatelů a pak vytvoří nabízené oznámení. Aby bylo možné oznámení na zařízení přidat, nemusí být uživatelé přihlášeni do aplikace.  
- Intune a aplikace Portál společnosti nemůžou zaručit doručení vlastního oznámení. Vlastní oznámení se můžou zobrazovat i po několika hodinách, pokud je to u všech, takže by se nemuseli používat pro naléhavé zprávy.  
- Vlastní oznamovací zprávy z Intune se na zařízeních zobrazují jako standardní nabízená oznámení. Pokud je aplikace Portál společnosti v zařízení se systémem iOS otevřená při přijetí oznámení, zobrazí se v aplikaci oznámení místo nabízeného oznámení.  
- Vlastní oznámení můžete zobrazit na zamykací obrazovce na zařízeních s iOS i Androidem v závislosti na nastavení zařízení.  
- V zařízeních s Androidem můžou mít další aplikace přístup k datům ve vlastních oznámeních. Nepoužívejte je pro citlivou komunikaci.  
- Uživatelé zařízení, kteří se nedávno zaregistrovali, nebo uživatelé, kteří se odebrali ze skupiny, můžou dál obdržet vlastní oznámení, které se následně pošle do této skupiny.  Podobně platí, že pokud přidáte uživatele do skupiny po odeslání vlastního oznámení do skupiny, je možné, že nově přidaná zpráva se použije k přijetí zprávy s oznámením, která byla dříve odeslána.  

## <a name="send-a-custom-notification"></a>Odeslání vlastního oznámení  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) pomocí účtu, který má oprávnění k vytváření a odesílání oznámení, a v **zařízení** > **odesílají vlastní oznámení**.  

2. Na kartě základy zadejte následující příkaz a pokračujte výběrem **Další** .  
   - **Title** – zadejte název tohoto oznámení. Názvy jsou omezeny na 50 znaků.  
   - **Tělo** – zadejte zprávu. Zprávy jsou omezené na 500 znaků.

   ![Vytvoření vlastního oznámení](./media/custom-notifications/custom-notifications.png)  

3. Na kartě **přiřazení** vyberte skupiny, kterým chcete poslat toto vlastní oznámení, a pak pokračujte výběrem další.  

4. Na kartě **Revize + vytvořit** zkontrolujte informace a až budete připraveni odeslat oznámení, vyberte **vytvořit**.  

Intune zpracovává zprávy, které vytvoříte hned. Jediným potvrzením, že se zpráva poslala, je oznámení Intune, které potvrdí, že se poslalo vlastní oznámení.  

![Potvrzení odeslaného oznámení](./media/custom-notifications/notification-sent.png)  

Intune nesleduje vlastní oznámení, která odesíláte, a zařízení neprotokolují příjem mimo centrum oznámení zařízení.  

## <a name="receive-a-custom-notification"></a>Přijetí vlastního oznámení  

Na zařízení uživatelé uvidí vlastní oznamovací zprávy, které Intune odesílají jako standardní nabízené oznámení z aplikace Portál společnosti. Tato oznámení jsou podobná nabízeným oznámením, která uživatelé dostanou z jiných aplikací na zařízení.  

Pokud je v zařízeních se systémem iOS po přijetí oznámení otevřená aplikace Portál společnosti, zobrazí se v aplikaci oznámení místo nabízeného oznámení.  

Oznámení zůstane, dokud ho uživatel nezavře.  

## <a name="next-steps"></a>Další kroky  
[Správa zařízení](device-management.md)
