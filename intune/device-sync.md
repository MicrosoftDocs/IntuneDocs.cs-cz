---
title: "Synchronizace zařízení v Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak synchronizovat zařízení s Intune a načíst nejnovější zásady a akce."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f784143535188c6bee2082c5717b752f08c5490
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchronizace zařízení s Intune s cílem načíst nejnovější zásady a akce


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Synchronizovat** vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované ohlášení.

## <a name="supported-platforms"></a>Podporované platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Synchronizace zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Synchronizovat**.
7. Kliknutím na **Ano** akci potvrďte.


## <a name="retriable-error-codes"></a>Kódy chyb umožňujících opakovaný pokus

Když správce spustí akci zařízení **Synchronizovat**, aplikace iOS a Android, které selhaly, ale vyvolaly kód chyby umožňující opakovaný pokus, budou pro zařízení dostupné. Aplikace, které vyvolaly kód chyby neumožňující opakovaný pokus, ale musí počkat sedm dní, než můžou být pro zařízení znovu dostupné.


| Kód chyby  | Navrhovaný popis                                                                                                                  | Opakovaný pokus |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Došlo k neznámé chybě.                                                                                                             | Ne        |
| 2016330897 | Časový limit vašeho připojení k Intune vypršel. Resetujte připojení.                                                                             | Ano       |
| 2016330896 | Ztratili jste připojení k internetu. Resetujte připojení.                                                                            | Ano       |
| 2016330895 | Ztratili jste připojení k internetu. Resetujte připojení.                                                                            | Ano       |
| 2016330894 | Ztratili jste připojení k internetu. Resetujte připojení.                                                                            | Ano       |
| 2016330893 | Ztratili jste připojení k internetu. Resetujte připojení.                                                                            | Ano       |
| 2016330892 | Mezinárodní roaming je zakázaný.                                                                                                     | Ne        |
| 2016330891 | Během telefonního hovoru nejde získat přístup k mobilnímu datovému připojení pro toto zařízení. Počkejte na dokončení telefonního hovoru. | Ano       |
| 2016330890 | Pro tato zařízení nešlo v tuto chvíli  použít mobilní síť.                                                   | Ne        |
| 2016330889 | Nepovedlo se navázat zabezpečené připojení. Resetujte připojení.                                                                                   | Ano       |
| 2016330888 | Nepovedlo se vyhodnotit důvěryhodnost serveru.                                                                                                | Ne        |

## <a name="next-steps"></a>Další kroky

V části **Akce zařízení** zobrazíte stav akce Synchronizovat. 
