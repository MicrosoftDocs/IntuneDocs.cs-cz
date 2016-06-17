---
# required metadata

title: Kategorizace zařízení pomocí mapování skupin zařízení v Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

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
1. Pro každou kategorii zařízení, kterou chcete použít, vytvořte skupinu zařízení Intune. Informace o vytvoření skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)..
2. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Správce**..
3. V pracovním prostoru **Správa** rozbalte položku **Správa mobilního zařízení** a potom klikněte na **Mapování skupin zařízení**..
4. Na stránce **Mapování skupin zařízení** povolte mapování skupin zařízení.
5. Pokud chcete vytvořit nové pravidlo mapování, klikněte na **Přidat**.
6. V dialogovém okně **Přidat pravidlo mapování skupin zařízení** zadejte název kategorie, kterou chcete vytvořit, a potom z rozevíracího seznamu vyberte kolekci zařízení, na kterou chcete mapovat tuto kategorii. Až skončíte, klikněte na **Přidat**.
7. Po dokončení přidávání kategorií a skupin klikněte na **Uložit**..

Když nyní uživatelé registrují svá zařízení, zobrazí se jim seznam nakonfigurovaných kategorií. Po volbě kategorie a dokončení registrace se jejich zařízení přidá do skupiny zařízení, která odpovídá kategorii, kterou zvolili.

### Související témata
[Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO1-->


