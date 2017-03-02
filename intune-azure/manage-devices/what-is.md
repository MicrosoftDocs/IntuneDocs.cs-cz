---
title: "Správa zařízení pomocí Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Zjistěte, jak můžete zobrazit zařízení spravovaná přes Intune a provádět s nimi různé operace."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 5ed437eca48375def0e4da9715693325845f53a9
ms.lasthandoff: 02/16/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Úloha **Zařízení a skupiny** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy. Tuto úlohu zpřístupníte takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení a skupiny**.

    ![Úloha Zařízení a skupiny](./media/devices-and-groups-workload.png)

Pak vyberte jednu z těchto možností:

- **Přehled** – získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
- **Spravovat** – volbou možnosti **Všechna zařízení** zobrazíte seznam všech spravovaných zařízení.
    Když vyberete některé zařízení v tomto seznamu, otevře se okno <*název zařízení*> **Přehled**, kde můžete vybrat jednu z těchto možností:
    - **Přehled** – zobrazí se obecné informace o tomto zařízení, například název, vlastník, jestli se jedná o vlastní zařízení uživatele, kdy se naposledy přihlásilo a další. Navíc můžete u tohoto zařízení vzdáleně provést následující akce (ne všechny akce jsou podporované na všech platformách zařízení):
        - **Odebrat firemní data** – odebere jen firemní data spravovaná přes Intune. Osobní data ze zařízení neodebere. Zařízení už nebude spravované přes Intune a nebude mít přístup k podnikovým prostředkům (nepodporuje se u zařízení s Windows, která jsou připojená ke službě Azure Active Directory).
        - **Obnovení továrního nastavení** – vrátí zařízení na výchozí nastavení. Zařízení už nebude spravované přes Intune a odeberou se jak firemní, tak osobní data. Tuto akci nejde vrátit zpět.
        - **Vzdálené uzamčení** – uzamkne zařízení. Vlastník zařízení musí k jeho odemčení použít heslo. Vzdáleně můžete uzamknout jen zařízení s nastaveným PIN kódem nebo heslem.
        - **Resetovat heslo** – vygeneruje pro zařízení nové heslo, které se zobrazí v okně <*název zařízení*> **Přehled**.
        - **Vynechat zámek aktivace** – odebere zámek aktivace ze zařízení s iOSem bez Apple ID a hesla uživatele. Když zámek aktivace vynecháte, zařízení ho znovu zapne při spuštění aplikace Najít iPhone. Zámek aktivace vynechejte jenom v případě, že máte k zařízení fyzický přístup.
        - **Režim ztráty** – režim ztráty můžete povolit při odcizení zařízení. To vám umožní zadat zprávu a telefonní číslo, které se zobrazí na uzamčené obrazovce zařízení.
        - **Restartovat** – způsobí, že se zařízení restartuje. Vlastník zařízení není na restartování automaticky upozorněn, takže může přijít o to, na čem pracuje.
        ![Přehled zařízení](http://i.imgur.com/4Rx4VXm.png)
        
    - **Hardware** – zobrazí podrobnější informace o zařízení, například volný úložný prostor, model a výrobce.
    ![Inventář hardwaru spravovaných zařízení](./media/hardware-inventory.png)
    - **Zjištěné aplikace** – zobrazí seznam všech nainstalovaných aplikací, které služba Intune našla na zařízení.
    ![Uzel zjištěných aplikací](./media/detected-applications.png)
- **Monitorování** – volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a aktuální stav těchto akcí.
![Monitorování akcí zařízení](./media/monitor-device-actions.png)

