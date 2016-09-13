---
title: "Kategorizace zařízení pomocí mapování skupin zařízení | Microsoft Intune"
description: "Mapování skupin zařízení Microsoft Intune slouží k seskupení zařízení do kategorií, které definujete, aby bylo možné zjednodušit správu těchto zařízení."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 727d28cff074124b5401f6c2931f87df3a9d2d23
ms.openlocfilehash: 7b1c6f0e380c03d048686462682fc1cee85b7cfa


---

# Kategorizace zařízení pomocí mapování skupin zařízení v Microsoft Intune
**Mapování skupin zařízení** Microsoft Intune slouží k seskupení zařízení do kategorií, které definujete, aby bylo možné zjednodušit správu těchto zařízení. 

Mapování skupin zařízení používá následující postup:
1. Vytvoříte skupiny zařízení Intune pro všechny kategorie, které chcete použít.
2. Nakonfigurujete pravidla mapování skupin zařízení, která mapují kategorii, kterou zvolíte, na skupinu zařízení, kterou jste vytvořili.
3. Když koncoví uživatelé registrují svá zařízení, musí zvolit kategorii z nakonfigurovaných kategorií. Poté této volbě se jejich zařízení automaticky přidá do příslušné skupiny zařízení, kterou jste vytvořili.
4. Pak můžete použít tyto skupiny zařízení při nasazování zásad a aplikací.

Příklady kategorií:
* Osobní
* Zařízení POS
* Předváděcí zařízení
* Prodej
* Účtárna
* Správce

Nicméně lze nakonfigurovat kategorie libovolně.

## Postup konfigurace mapování skupin zařízení
1. Pro každou kategorii zařízení, kterou chcete použít, vytvořte skupinu zařízení Intune. Informace o postupu při vytváření skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**.
3. V pracovním prostoru **Správa** rozbalte položku **Správa mobilních zařízení** a pak zvolte **Mapování skupin zařízení**.
4. Na stránce **Mapování skupin zařízení** povolte mapování skupin zařízení.
5. Pokud chcete vytvořit nové pravidlo mapování, zvolte **Přidat**.
6. V dialogovém okně **Přidat pravidlo mapování skupin zařízení** zadejte název kategorie, kterou chcete vytvořit, a potom z rozevíracího seznamu vyberte kolekci zařízení, na kterou chcete mapovat tuto kategorii. Až skončíte, zvolte **Přidat**.
7. Po dokončení přidávání kategorií a skupin zvolte **Uložit**.

Když nyní uživatelé registrují svá zařízení, zobrazí se jim seznam nakonfigurovaných kategorií. Po volbě kategorie a dokončení registrace se jejich zařízení přidá do skupiny zařízení, která odpovídá kategorii, kterou zvolili.

### Viz taky
[Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Aug16_HO5-->


