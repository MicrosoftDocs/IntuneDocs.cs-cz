---
title: "Správa zařízení v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Zjistěte, jak můžete zobrazit zařízení spravovaná přes Intune a provádět s nimi různé operace."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 957192c744bf05cd835dfae60b6bb521b8f8b26b
ms.lasthandoff: 03/15/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy. Tuto úlohu zpřístupníte takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.

Pak vyberte jednu z těchto možností:

- **Přehled** – získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
- **Spravovat** – volbou možnosti **Všechna zařízení** zobrazíte seznam všech spravovaných zařízení.
    Když vyberete některé zařízení v tomto seznamu, otevře se okno <*název zařízení*> **Přehled**, kde můžete vybrat jednu z těchto možností:
    - **Přehled** – zobrazí se obecné informace o tomto zařízení, například název, vlastník, jestli se jedná o vlastní zařízení uživatele, kdy se naposledy přihlásilo a další. 
                
    - **Hardware** – zobrazí podrobnější informace o zařízení, například volný úložný prostor, model a výrobce.
    ![Inventář hardwaru spravovaných zařízení](./media/hardware-inventory.png)
    - **Zjištěné aplikace** – zobrazí seznam všech nainstalovaných aplikací, které služba Intune našla na zařízení.
    ![Uzel zjištěných aplikací](./media/detected-applications.png)
- **Monitorování** – volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a aktuální stav těchto akcí.
![Monitorování akcí zařízení](./media/monitor-device-actions.png)
- **Nápověda a podpora** – zobrazí odkazy na dokumentaci týkající se odstraňování potíží a podpory.

## <a name="available-device-actions"></a>Dostupné akce zařízení

Navíc můžete u tohoto zařízení vzdáleně provést následující akce (ne všechny akce jsou podporované na všech platformách zařízení):

### <a name="remove-company-data"></a>**Odebrat firemní data**
Odebere jenom firemní data spravovaná přes Intune. Osobní data ze zařízení neodebere. Zařízení už nebude spravované přes Intune a nebude mít přístup k podnikovým prostředkům (nepodporuje se u zařízení s Windows, která jsou připojená ke službě Azure Active Directory).

### <a name="factory-reset"></a>**Obnovit výrobní nastavení**
Vrátí zařízení na výchozí nastavení. Zařízení už nebude spravované přes Intune a odeberou se jak firemní, tak osobní data. Tuto akci nejde vrátit zpět.

### <a name="remote-lock"></a>**Vzdálené uzamčení**
Uzamkne zařízení. Vlastník zařízení musí k jeho odemčení použít heslo. Vzdáleně můžete uzamknout jen zařízení s nastaveným PIN kódem nebo heslem.

### <a name="reset-passcode"></a>**Resetovat heslo**
Vygeneruje pro zařízení nového heslo, které se zobrazí v okně <*název zařízení*> **Přehled**.

### <a name="bypass-activation-lock"></a>**Vynechat zámek aktivace**
Odebere zámek aktivace ze zařízení s iOSem bez Apple ID a hesla uživatele. Když zámek aktivace vynecháte, zařízení ho znovu zapne při spuštění aplikace Najít iPhone. Zámek aktivace vynechejte jenom v případě, že máte k zařízení fyzický přístup.

### <a name="lost-mode"></a>**Režim ztráty**
Režim ztráty můžete zapnout při ztrátě nebo odcizení zařízení s iOSem. To vám umožní zadat zprávu a telefonní číslo, které se zobrazí na uzamčené obrazovce zařízení. Provedete to následujícím způsobem:
1.    V okně vlastností pro zařízení s iOSem zvolte **Více** > **Režim ztráty**.
2.    V okně **Režim ztráty** zapněte režim ztráty, zadejte zprávu, která se má zobrazit, a volitelně také kontaktní telefonní číslo.
3.    Klikněte na **OK**.
Když zapnete režim ztráty, zablokujete veškeré možnosti použití zařízení. Koncový uživatel nebude mít k zařízení přístup, dokud režim ztráty nevypnete. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zjistit, kde se zařízení nachází.

### <a name="locate-device"></a>**Najít zařízení**
Pomocí této vzdálené akce můžete zobrazit polohu ztraceného nebo odcizeného zařízení s iOSem na mapě. Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je v režimu dohledu. Než tuto akci použijete, musíte pro zařízení zapnout režim ztráty.
1.    V okně vlastností pro zařízení s iOSem zvolte **Více** > **Najít zařízení**.
2.    Poloha nalezeného zařízení se zobrazí v okně **Najít zařízení**. 
    ![Okno Najít zařízení](./media/locate-device.png)

### <a name="restart"></a>**Restartovat**
Restartuje zařízení. Vlastník zařízení není na restartování automaticky upozorněn, takže může přijít o to, na čem pracuje.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Do Intune se neodesílají žádné informace o poloze zařízení, dokud tuto akci nezapnete.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Doporučujeme, abyste při konfiguraci režimu ztráty zadali do zprávy, která se má zobrazit na zamykací obrazovce, informace o tom, že údaje o poloze se dají zjistit.

