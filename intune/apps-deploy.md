---
title: "Přiřazení aplikací do skupin v Microsoft Intune"
titlesuffix: 
description: "Po přidání aplikace do Microsoft Intune bude vhodné ji přiřadit do skupin uživatelů nebo zařízení."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eba329be463fbf0593638bd4cf41c404a17f9cc0
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Přiřazení aplikací do skupin pomocí Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Po přidání aplikace do Microsoft Intune ji můžete přiřadit k uživatelům a zařízením.

Aplikace se dají přiřadit k zařízením, ať už jsou spravované službou Intune nebo ne. Následující tabulka vám pomůže pochopit různé možnosti pro přiřazení aplikací uživatelům a zařízením:

||||
|-|-|-|-|
|&nbsp;|Zařízení zaregistrovaná v Intune|Zařízení nezaregistrovaná v Intune|
|Přiřadit uživatelům|Ano|Ano|
|Přiřadit zařízením|Ano|Ne|
|Přiřadit zabalené aplikace nebo aplikace obsahující sadu Intune SDK (kvůli zásadám ochrany aplikací)|Ano|Ano|
|Přiřadit aplikace jako K dispozici|Ano|Ano|
|Přiřadit aplikace jako Povinné|Ano|Ne|
|Odinstalovat aplikace|Ano|Ne|
|Dostávat aktualizace aplikací z Intune|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti.|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti.|Ano|Ano|

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i koupené ve Storu) k zařízením, která nejsou zaregistrovaná v Intune.<br></br><br></br>
> Pokud chtějí uživatelé získat aktualizace aplikací na zařízeních, která nejsou zaregistrovaná v Intune, musí přejít na portál společnosti a aktualizace aplikací ručně nainstalovat.

## <a name="how-to-assign-an-app"></a>Postup přiřazení aplikace

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1. V úloze **Mobilní aplikace** zvolte v části **Spravovat** možnost **Aplikace**.
2. V okně se seznamem aplikací klikněte na aplikaci, kterou chcete přiřadit.
3. V okně **Přehled** konkrétní aplikace vyberte v části **Spravovat** možnost **Přiřazení**.
4. Výběrem možnosti **Přidat skupinu** zobrazíte okno **Přidat skupinu** pro danou aplikaci.
5. Pro konkrétní aplikaci zvolte **typ přiřazení**:
    - **K dispozici zaregistrovaným zařízením** – Uživatelé instalují aplikaci z aplikace nebo webu Portál společnosti.
    - **K dispozici s registrací i bez ní** – Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. Všimněte si, že typ **Aplikace Android for Work** tuto možnost nepodporuje. 
    - **Povinné** – Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat** – Aplikace se odinstaluje ze zařízení ve vybraných skupinách.

    > [!NOTE]
    > **Jenom pro aplikace pro iOS** – Pokud jste vytvořili profil VPN iOSu, který obsahuje nastavení sítě VPN podle aplikací, můžete ho ve **VPN** vybrat. Při spuštění aplikace se připojení VPN otevře. Další informace najdete v článku o [nastavení VPN pro zařízení s iOSem](vpn-settings-ios.md).

6. Výběrem možnosti **Zahrnuté skupiny** zvolte skupiny uživatelů, které budou přiřazením aplikace ovlivněny.
7. Jakmile vyberete jednu nebo více skupin, které se mají zahrnout, klikněte na **Vybrat**.
8. Klikněte na **OK** v okně **Přiřadit** a dokončete výběr zahrnutých skupin.
9. Pokud se rozhodnete vyloučit jakékoli skupiny uživatelů, tak aby nebyly přiřazením aplikace ovlivněny, klikněte na **Vyloučit skupiny**.
10. Pokud jste se rozhodli některé skupiny vyloučit, klikněte na **Vybrat** v okně **Vybrat skupiny**.
11. Klikněte na tlačítko **OK** v okně **Přidat skupinu**.
12. Klikněte na **Uložit** v okně **Přiřazení** a svá přiřazení uložte.

Aplikace je teď přiřazená do skupin, které jste vybrali. Další informace o zahrnutí a vyloučení přiřazení aplikací najdete v článku [Zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Řešení konfliktů mezi záměry aplikace

Někdy je tatáž aplikace přiřazena více skupinám, ale s různými záměry. V těchto případech si můžete dohledat výsledný záměr v níže uvedené tabulce.

||||
|-|-|-|
|Záměr skupiny 1|Záměr skupiny 2|Výsledný záměr|
|Uživatel: Povinné|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné|Uživatel: Není k dispozici|Povinné|
|Uživatel: Povinné|Uživatel: Odinstalace|Povinné|
|Uživatel: K dispozici|Uživatel: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Uživatel: Odinstalace|Odinstalace|
|Uživatel: Není k dispozici|Uživatel: Odinstalace|Odinstalace
|Uživatel: Povinné|Zařízení: Povinné|Existuje obojí, zpracování bránou je povinné
|Uživatel: Povinné|Zařízení: Odinstalace|Existuje obojí, řešení bránou je povinné
|Uživatel: K dispozici|Zařízení: Povinné|Existuje obojí, řešení bránou je povinné (Povinné a K dispozici)
|Uživatel: K dispozici|Zařízení: Odinstalace|Existuje obojí, řešení bránou je k dispozici<br>Aplikace se zobrazí na Portálu společnosti.<br>Pokud je už aplikace nainstalovaná (jako požadovaná aplikace s předchozím záměrem), pak se aplikace odinstaluje.<br>Pokud ale uživatel klikne na portálu společnosti na instalaci, aplikace se instaluje a záměr odinstalace není dodržen.|
|Uživatel: Není k dispozici|Zařízení: Povinné|Povinné|
|Uživatel: Není k dispozici|Zařízení: Odinstalace|Odinstalace|
|Uživatel: Odinstalace|Zařízení: Povinné|Existuje obojí, řešení bránou je povinné|
|Uživatel: Odinstalace|Zařízení: Odinstalace|Existuje obojí, řešení bránou prostřednictvím odinstalace|
|Zařízení: Povinné|Zařízení: Odinstalace|Povinné|
|Uživatel: Povinné a K dispozici|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Odinstalace|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Povinné|Existuje obojí, Povinné a K dispozici
|Uživatel: Povinné a K dispozici|Zařízení: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Odinstalace|Existuje obojí, řešení bránou je povinné Povinné + K dispozici
|Uživatel: Není k dispozici|Zařízení: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Zařízení: Není k dispozici|K dispozici|
|Uživatel: Povinné|Zařízení: Není k dispozici|Povinné|
|Uživatel: K dispozici bez registrace|Uživatel: Povinné a K dispozici|Povinné a K dispozici
|Uživatel: K dispozici bez registrace|Uživatel: Povinné|Povinné
|Uživatel: K dispozici bez registrace|Uživatel: Není k dispozici|Není k dispozici
|Uživatel: K dispozici bez registrace|Uživatel: K dispozici|K dispozici|
|Uživatel: K dispozici bez registrace|Zařízení: Povinné|Povinné a K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Není k dispozici|K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Odinstalace|Odinstalace a K dispozici bez registrace.<br>Pokud uživatel nenainstaloval aplikaci z portálu společnosti, provede se odinstalace.<br>Pokud uživatel aplikaci nainstaluje z portálu společnosti, bude mít instalace prioritu před odinstalací.|

>[!NOTE]
>Pouze pro spravované aplikace pro App Store (iOS) platí, že pokud je přidáte do Microsoft Intune a přiřadíte jako **Povinné**, vytvoří se automaticky se záměry **Povinné** i **K dispozici**.

## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).
