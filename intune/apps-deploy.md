---
title: Přiřazení aplikací do skupin v Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak přiřadit aplikace Intune do skupin uživatelů nebo zařízení.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 96b95fcbfdc970976e24553972c5890f35cfddb2
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329474"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Přiřazení aplikací do skupin pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Po [přidání aplikace](apps-add.md) do Microsoft Intune ji můžete přiřadit uživatelům a zařízením. Je důležité si uvědomit, že aplikaci můžete zařízení přiřadit bez ohledu na to, jestli je zařízení spravované pomocí Intune. 

Následující tabulka obsahuje různé možnosti pro přiřazení aplikací uživatelům a zařízením:

||||
|-|-|-|-|
|&nbsp;|**Zařízení zaregistrovaná v Intune**|**Zařízení nezaregistrovaná v Intune**|
|Přiřadit uživatelům|Ano|Ano|
|Přiřadit zařízením|Ano|Ne|
|Přiřadit zabalené aplikace nebo aplikace obsahující sadu Intune SDK (kvůli zásadám ochrany aplikací)|Ano|Ano|
|Přiřadit aplikace jako K dispozici|Ano|Ano|
|Přiřadit aplikace jako Povinné|Ano|Ne|
|Odinstalovat aplikace|Ano|Ne|
|Dostávat aktualizace aplikací z Intune|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti|Ano|Ano|

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i zakoupené v obchodu s aplikacemi) zařízením, která nejsou zaregistrovaná v Intune.
>
> Pokud chtějí uživatelé získat aktualizace aplikací na zařízeních, která nejsou zaregistrovaná v Intune, musí přejít na Portál společnosti organizace a aktualizace aplikací nainstalovat ručně.

## <a name="to-assign-an-app"></a>Přiřazení aplikace

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V nabídce **Intune** zvolte **Klientské aplikace**.
4. V části nabídky **Spravovat** vyberte **Aplikace**.
5. V podokně **Aplikace** vyberte aplikaci, kterou chcete přiřadit.
6. V části nabídky **Spravovat** vyberte **Přiřazení**.
7. Vyberte **Přidat skupinu**. Tím se otevře podokno **Přidat skupinu** týkající se aplikace.
8. Pro konkrétní aplikaci vyberte **typ přiřazení**:
   - **K dispozici zaregistrovaným zařízením**: Uživatelé instalují aplikaci z aplikace nebo webu Portál společnosti.
   - **K dispozici s registrací i bez ní**: Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. Aplikace ze spravovaného obchodu Google Play tuto možnost nepodporují. 
   - **Povinné**: Aplikace se nainstaluje na zařízení ve vybraných skupinách.
   - **Odinstalovat**: Aplikace se odinstaluje ze zařízení ve vybraných skupinách.

     > [!NOTE]
     > **Jenom pro aplikace pro iOS** : Pokud jste vytvořili profil VPN iOSu, který obsahuje nastavení sítě VPN podle aplikací, můžete profil VPN ve **VPN** vybrat. Při spuštění aplikace se připojení VPN otevře. Další informace najdete v článku o [nastavení VPN pro zařízení s iOSem](vpn-settings-ios.md).

9. Pokud chcete vybrat skupiny uživatelů, které toto přiřazení aplikace ovlivní, vyberte **Zahrnuté skupiny**.
10. Po vybrání jedné nebo více skupin, které se mají zahrnout, zvolte **Vybrat**.
11. V podokně **Přiřadit** vyberte **OK**. Tím výběr zahrnutých skupin dokončíte.
12. Pokud se rozhodnete některé skupiny uživatelů vyloučit, aby nebyly přiřazením aplikace ovlivněné, klikněte na **Vyloučit skupiny**.
13. Pokud jste se rozhodli některé skupiny vyloučit, ve **Vybrat skupiny** zvolte **Vybrat**.
14. V podokně **Přidat skupinu** vyberte **OK**.
15. V podokně **Přiřazení** aplikace vyberte **Uložit**.

Aplikace je teď přiřazená do skupin, které jste vybrali. Další informace o zahrnutí a vyloučení přiřazení aplikací najdete v článku [Zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Řešení konfliktů mezi záměry aplikace

Někdy je tatáž aplikace přiřazena do více skupin, ale s různými záměry. Když k tomu dojde, pomůžou vám výsledný záměr pochopit informace v následující tabulce:

||||
|-|-|-|
|**Záměr skupiny 1**|**Záměr skupiny 2**|**Výsledný záměr**|
|Uživatel: Povinné|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné|Uživatel: Není k dispozici|Povinné|
|Uživatel: Povinné|Uživatel: Odinstalace|Povinné|
|Uživatel: K dispozici|Uživatel: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Uživatel: Odinstalace|Odinstalace|
|Uživatel: Není k dispozici|Uživatel: Odinstalace|Odinstalace
|Uživatel: Povinné|Zařízení: Povinné|Existuje obojí, Intune zpracovává Povinné.
|Uživatel: Povinné|Zařízení: Odinstalace|Existuje obojí, Intune překládá Povinné.
|Uživatel: K dispozici|Zařízení: Povinné|Existuje obojí, Intune překládá Povinné (Povinné a K dispozici).
|Uživatel: K dispozici|Zařízení: Odinstalace|Existuje obojí, Intune překládá K dispozici.<br><br>Aplikace se zobrazí na Portálu společnosti.<br><br>Pokud je už aplikace nainstalovaná (jako požadovaná aplikace s předchozím záměrem), aplikace se odinstaluje.<br><br>Pokud ale uživatel vybere **instalaci z Portálu společnosti**, aplikace se instaluje a záměr odinstalace se nedodrží.|
|Uživatel: Není k dispozici|Zařízení: Povinné|Povinné|
|Uživatel: Není k dispozici|Zařízení: Odinstalace|Odinstalace|
|Uživatel: Odinstalace|Zařízení: Povinné|Existuje obojí, Intune překládá Povinné.|
|Uživatel: Odinstalace|Zařízení: Odinstalace|Existuje obojí, Intune překládá Odinstalaci.|
|Zařízení: Povinné|Zařízení: Odinstalace|Povinné|
|Uživatel: Povinné a K dispozici|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Odinstalace|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Povinné|Existuje obojí, Povinné a K dispozici
|Uživatel: Povinné a K dispozici|Zařízení: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Odinstalace|Existuje obojí, Intune překládá Povinné (Povinné a K dispozici).
|Uživatel: Není k dispozici|Zařízení: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Zařízení: Není k dispozici|K dispozici|
|Uživatel: Povinné|Zařízení: Není k dispozici|Povinné|
|Uživatel: K dispozici bez registrace|Uživatel: Povinné a K dispozici|Povinné a K dispozici
|Uživatel: K dispozici bez registrace|Uživatel: Povinné|Povinné
|Uživatel: K dispozici bez registrace|Uživatel: Není k dispozici|Není k dispozici
|Uživatel: K dispozici bez registrace|Uživatel: K dispozici|K dispozici|
|Uživatel: K dispozici bez registrace|Zařízení: Povinné|Povinné a K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Není k dispozici|K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Odinstalace|Odinstalace a K dispozici bez registrace.<br><br>Pokud uživatel nenainstaloval aplikaci z Portálu společnosti, provede se odinstalace.<br><br>Pokud uživatel aplikaci nainstaluje z Portálu společnosti, bude mít instalace prioritu před odinstalací.|

> [!NOTE]
> Jenom pro spravované aplikace pro App Store (iOS) platí, že pokud je přidáte do Microsoft Intune a přiřadíte jako **Povinné**, vytvoří se automaticky se záměry **Povinné** i **K dispozici**.<br><br>
> Aplikace iOS pro App Store (nikoli aplikace iOS VPP), které jsou cílené se záměrem Povinné, se na zařízení vynutí při ohlášení zařízení a zobrazí se také v aplikaci Portál společnosti.

## <a name="next-steps"></a>Další kroky

Další informace o sledování přiřazení aplikací najdete v článku o [monitorování aplikací](apps-monitor.md).
