---
title: Přiřazení aplikací do skupin v Microsoft Intune
titleSuffix: ''
description: Naučte se, jak přiřadit aplikaci Intune skupinám uživatelů nebo zařízení pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f0f00b635a04f4ffe5bc09489b9909e9243ee98
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731246"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Přiřazení aplikací do skupin pomocí Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Po [přidání aplikace](apps-add.md) do Microsoft Intune ji můžete přiřadit uživatelům a zařízením. Je důležité si uvědomit, že aplikaci můžete zařízení přiřadit bez ohledu na to, jestli je zařízení spravované pomocí Intune.

> [!NOTE]
> Dostupný záměr nasazení není pro skupiny zařízení podporován, jsou podporovány pouze skupiny uživatelů.

Následující tabulka obsahuje různé možnosti pro přiřazení aplikací uživatelům a zařízením:

|   | Zařízení zaregistrovaná v Intune | Zařízení nezaregistrovaná v Intune |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Přiřadit uživatelům | Ano | Ano |
| Přiřadit zařízením | Ano | Ne |
| Přiřadit zabalené aplikace nebo aplikace obsahující sadu Intune SDK (kvůli zásadám ochrany aplikací) | Ano | Ano |
| Přiřadit aplikace jako K dispozici | Ano | Ano |
| Přiřadit aplikace jako Povinné | Ano | Ne |
| Odinstalovat aplikace | Ano | Ne |
| Dostávat aktualizace aplikací z Intune | Ano | Ne |
| Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti | Ano | Ne |
| Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti | Ano | Ano |

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i zakoupené v obchodu s aplikacemi) zařízením, která nejsou zaregistrovaná v Intune.
>
> Pokud chtějí uživatelé získat aktualizace aplikací na zařízeních, která nejsou zaregistrovaná v Intune, musí přejít na Portál společnosti organizace a aktualizace aplikací nainstalovat ručně.

## <a name="assign-an-app"></a>Přiřazení aplikace

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V části nabídky **Spravovat** vyberte **Aplikace**.
5. V podokně **Aplikace** vyberte aplikaci, kterou chcete přiřadit.
6. V části nabídky **Spravovat** vyberte **Přiřazení**.
7. Vyberte **Přidat skupinu**. Tím se otevře podokno **Přidat skupinu** týkající se aplikace.
8. Pro konkrétní aplikaci vyberte **typ přiřazení**:
   - **K dispozici pro zaregistrovaná zařízení**: přiřaďte aplikaci skupinám uživatelů, kteří můžou aplikaci instalovat z aplikace Portál společnosti nebo webu.
   - **K dispozici s registrací i bez ní**: Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. Uživatelům musí být přiřazena licence Intune, viz [licence Intune](../fundamentals/licenses.md).
   - **Povinné**: Aplikace se nainstaluje na zařízení ve vybraných skupinách. Některé platformy mohou mít další výzvy, aby koncový uživatel mohl potvrdit před zahájením instalace aplikace.
   - **Odinstalace**: aplikace se odinstaluje ze zařízení ve vybraných skupinách, pokud Intune tuto aplikaci do zařízení dřív nainstaloval pomocí stejného nasazení prostřednictvím "dostupného pro zaregistrovaná zařízení" nebo "povinného" přiřazení. Po nasazení nelze odebrat webové odkazy.

     > [!NOTE]
     > **Jenom pro aplikace pro iOS**:
     > - Pokud chcete nakonfigurovat, co se stane se spravovanými aplikacemi, když už zařízení nejsou spravovaná, můžete vybrat zamýšlené nastavení v části **odinstalace při odebírání zařízení**. Další informace najdete v tématu [Nastavení odinstalace aplikací pro aplikace spravované v iOS](apps-deploy.md#app-uninstall-setting-for-ios-managed-apps).
     > - Pokud jste vytvořili profil VPN pro iOS, který obsahuje nastavení sítě VPN pro jednotlivé aplikace, můžete vybrat profil sítě VPN v části **VPN**. Při spuštění aplikace se připojení VPN otevře. Další informace najdete v článku o [nastavení VPN pro zařízení s iOSem](../vpn-settings-ios.md).
     >
     > **Pouze pro aplikace pro Android**: Pokud nasadíte aplikaci pro Android, která je **k dispozici s registrací nebo bez registrace**, stav hlášení bude k dispozici pouze v zaregistrovaných zařízeních.
     >
     > K **dispozici pro zaregistrovaná zařízení**: aplikace se zobrazuje jenom jako dostupná, pokud je uživatel přihlášený k Portál společnosti primární uživatel, který zařízení zaregistroval, a aplikace se vztahuje na zařízení.

9. Pokud chcete vybrat skupiny uživatelů, které toto přiřazení aplikace ovlivní, vyberte **Zahrnuté skupiny**.
10. Po vybrání jedné nebo více skupin, které se mají zahrnout, zvolte **Vybrat**.
11. V podokně **Přiřadit** vyberte **OK**. Tím výběr zahrnutých skupin dokončíte.
12. Pokud se rozhodnete některé skupiny uživatelů vyloučit, aby nebyly přiřazením aplikace ovlivněné, klikněte na **Vyloučit skupiny**.
13. Pokud jste se rozhodli některé skupiny vyloučit, ve **Vybrat skupiny** zvolte **Vybrat**.
14. V podokně **Přidat skupinu** vyberte **OK**.
15. V podokně **Přiřazení** aplikace vyberte **Uložit**.

Aplikace je teď přiřazená do skupin, které jste vybrali. Další informace o zahrnutí a vyloučení přiřazení aplikací najdete v článku [Zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Řešení konfliktů mezi záměry aplikace

Jednu skupinu je zabráněno zacílené pro přiřazení více aplikací. Pokud je ale uživatel nebo zařízení členem více skupin, které jsou přiřazené k různým záměrům, bude výsledkem konflikt. Vytváření konfliktů přiřazení pro aplikace se nedoporučuje.
Informace v následující tabulce vám pomohou pochopit výsledný záměr při výskytu konfliktu:

| Záměr skupiny 1 | Záměr skupiny 2 | Výsledný záměr |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Uživatel: Povinné|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné|Uživatel: Není k dispozici|Požadováno|
|Uživatel: Povinné|Uživatel: Odinstalace|Požadováno|
|Uživatel: K dispozici|Uživatel: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Uživatel: Odinstalace|Odinstalovat|
|Uživatel: Není k dispozici|Uživatel: Odinstalace|Odinstalovat
|Uživatel: Povinné|Zařízení: Povinné|Existuje obojí, Intune zpracovává Povinné.
|Uživatel: Povinné|Zařízení: Odinstalace|Existuje obojí, Intune překládá Povinné.
|Uživatel: K dispozici|Zařízení: Povinné|Existuje obojí, Intune překládá Povinné (Povinné a K dispozici).
|Uživatel: K dispozici|Zařízení: Odinstalace|Existuje obojí, Intune překládá K dispozici.<br><br>Aplikace se zobrazí na Portálu společnosti.<br><br>Pokud je už aplikace nainstalovaná (jako požadovaná aplikace s předchozím záměrem), aplikace se odinstaluje.<br><br>Pokud ale uživatel vybere **instalaci z Portálu společnosti**, aplikace se instaluje a záměr odinstalace se nedodrží.|
|Uživatel: Není k dispozici|Zařízení: Povinné|Požadováno|
|Uživatel: Není k dispozici|Zařízení: Odinstalace|Odinstalovat|
|Uživatel: Odinstalace|Zařízení: Povinné|Existuje obojí, Intune překládá Povinné.|
|Uživatel: Odinstalace|Zařízení: Odinstalace|Existuje obojí, Intune překládá Odinstalaci.|
|Zařízení: Povinné|Zařízení: Odinstalace|Požadováno|
|Uživatel: Povinné a K dispozici|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Odinstalace|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Povinné|Existuje obojí, Povinné a K dispozici
|Uživatel: Povinné a K dispozici|Zařízení: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Odinstalace|Existuje obojí, Intune překládá Povinné (Povinné a K dispozici).
|Uživatel: Není k dispozici|Zařízení: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Zařízení: Není k dispozici|K dispozici|
|Uživatel: Povinné|Zařízení: Není k dispozici|Požadováno|
|Uživatel: K dispozici bez registrace|Uživatel: Povinné a K dispozici|Povinné a K dispozici
|Uživatel: K dispozici bez registrace|Uživatel: Povinné|Požadováno
|Uživatel: K dispozici bez registrace|Uživatel: Není k dispozici|Není k dispozici
|Uživatel: K dispozici bez registrace|Uživatel: K dispozici|K dispozici|
|Uživatel: K dispozici bez registrace|Zařízení: Povinné|Povinné a K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Není k dispozici|K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Odinstalace|Odinstalace a K dispozici bez registrace.<br><br>Pokud uživatel nenainstaloval aplikaci z Portálu společnosti, provede se odinstalace.<br><br>Pokud uživatel aplikaci nainstaluje z Portálu společnosti, bude mít instalace prioritu před odinstalací.|

> [!NOTE]
> Jenom pro spravované aplikace pro App Store (iOS) platí, že pokud je přidáte do Microsoft Intune a přiřadíte jako **Povinné**, vytvoří se automaticky se záměry **Povinné** i **K dispozici**.<br><br>
> Aplikace iOS pro App Store (nikoli aplikace iOS VPP), které jsou cílené se záměrem Povinné, se na zařízení vynutí při ohlášení zařízení a zobrazí se také v aplikaci Portál společnosti.<br><br>
> Pokud se v nastavení **odinstalovat při odebrání zařízení** vyskytnou konflikty, aplikace se ze zařízení neodebere, když už zařízení není spravované.

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Spravované Google Play nasazení aplikace na nespravovaná zařízení
U zařízení s Androidem v neregistrovaných zásadách ochrany aplikací bez nasazení (APP-WE) můžete použít spravovaný Google Play k nasazení aplikací pro Store a obchodních aplikací (LOB) uživatelům. Spravované Google Play aplikace cílené na **k dispozici s nebo bez registrace** se zobrazí v aplikaci Obchod Play na zařízení koncového uživatele, a ne v aplikaci Portál společnosti. Koncový uživatel bude procházet a instalovat aplikace nasazené tímto způsobem z aplikace Play. Vzhledem k tomu, že se aplikace instalují ze spravovaných Google Play, nebude muset koncový uživatel měnit nastavení zařízení, aby bylo možné instalovat aplikace z neznámých zdrojů. to znamená, že zařízení budou bezpečnější. Pokud vývojář aplikace publikuje novou verzi aplikace, která je nainstalovaná na zařízení uživatele, aplikace se automaticky aktualizuje přehráním. 

Postup přiřazení spravované aplikace Google Play k nespravovaným zařízením:

1. Připojte svého tenanta Intune ke spravovaným Google Play. Pokud jste to už udělali kvůli tomu, abyste mohli spravovat pracovní profil platformy Android Enterprise, vyhrazená nebo plně spravovaná zařízení, nemusíte to dělat znovu.
2. Do konzoly Intune přidejte aplikace ze spravovaných Google Play.
3. Cílit na spravované Google Play aplikace jako **k dispozici s registrací nebo bez registrace** do požadované skupiny uživatelů. **Vyžadované** a **odinstalace** cílení aplikace nejsou pro neregistrovaná zařízení podporovaná.
4. Přiřaďte zásady ochrany aplikací ke skupině uživatelů.
5. Když koncový uživatel otevře aplikaci Portál společnosti, zobrazí se zpráva oznamující, že v aplikaci Obchod Play jsou pro ně k dispozici aplikace.  Uživatel může klepnutím na toto oznámení přejít přímo do aplikace Play, aby se zobrazily podnikové aplikace, nebo můžou na aplikaci Obchod Play přejít samostatně.
6. Koncový uživatel může rozbalit kontextovou nabídku v aplikaci Obchod Play a přepnout mezi svým osobním účtem Google (tam, kde vidí své osobní aplikace), a jejich pracovním účtem (kde se budou zobrazovat v aplikacích pro Store a LOB). Koncoví uživatelé nainstalují aplikace klepnutím na instalovat v aplikaci Obchod Play.

Po vydání selektivního vymazání aplikace v konzole Intune se pracovní účet automaticky odebere z aplikace Obchod Play a koncový uživatel z tohoto bodu už nebude zobrazovat pracovní aplikace v katalogu aplikací Obchod Play. Když se pracovní účet odebere ze zařízení, aplikace nainstalované z Obchod Play zůstanou nainstalované na zařízení a neodinstaluje se. 

## <a name="app-uninstall-setting-for-ios-managed-apps"></a>Nastavení odinstalace aplikace pro aplikace spravované v iOS
V případě zařízení se systémem iOS si můžete vybrat, co se stane se spravovanými aplikacemi při zrušení registrace zařízení v Intune nebo odebrání profilu správy pomocí nastavení **odinstalovat při odebrání zařízení** . Toto nastavení platí jenom pro aplikace po zaregistrování zařízení a aplikace se nainstalují jako spravované. Nastavení nelze konfigurovat pro webové aplikace ani pro webové odkazy. 

Výchozí hodnoty pro nastavení jsou předem vyplněné pro nová přiřazení následujícím způsobem:

|Typ aplikace pro iOS | Výchozí nastavení pro možnost odinstalovat při odebrání zařízení |
|--------------------|----------------|
| Obchodní aplikace | Ano |
| Aplikace pro Store | Ne |
| Aplikace VPP | Ne |
| Buit – v aplikaci | Ne |

>[!NOTE]
>**Typy přiřazení "dostupné":** Pokud aktualizujete toto nastavení pro skupiny "k dispozici pro zaregistrovaná zařízení" nebo "k dispozici v rámci nebo bez registrace", uživatelé, kteří už mají spravovanou aplikaci, nebudou mít aktualizované nastavení, dokud zařízení nesynchronizují s Intune a znovu nenainstaluje aplikaci. 
>
>**Již existující přiřazení:** Přiřazení, která existovala před zavedením tohoto nastavení, se nezmění a všechny spravované aplikace se při odebrání zařízení ze správy odeberou.

## <a name="next-steps"></a>Další kroky

Další informace o sledování přiřazení aplikací najdete v článku o [monitorování aplikací](apps-monitor.md).
