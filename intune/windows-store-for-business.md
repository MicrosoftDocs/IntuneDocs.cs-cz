---
title: "Správa aplikací z Windows Storu pro firmy"
titleSuffix: Intune on Azure
description: "Zjistěte, jak můžete synchronizovat aplikace z Windows Storu pro firmy do Intune a pak je přiřadit a sledovat."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de6ed7623e33a50bdf8452cbf1bad9c648b13d04
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Správa aplikací zakoupených ve Windows Storu pro firmy v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


[Windows Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svoji organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete spravovat hromadně zakoupené aplikace pomocí portálu Intune. Například:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole pro správu Intune. Tyto aplikace můžete přiřadit stejně jako všechny ostatní aplikace.
* V konzole pro správu Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatečný počet licencí, blokuje Intune přiřazení a instalaci aplikací.

## <a name="before-you-start"></a>Než začnete

Než začnete synchronizovat a přiřazovat aplikace z Windows Storu pro firmy, přečtěte si následující informace:

- Nakonfigurujte Intune jako autoritu správy mobilních zařízení pro svoji organizaci.
- Musíte mít zaregistrovaný účet ve Windows Storu pro firmy.
- Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
- Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Windows Storem pro firmy.
- Intune synchronizuje aplikace s online i offline licencemi, které jste zakoupili ve Windows Storu pro firmy.
- V Intune se synchronizují jenom offline aplikace, které jsou bezplatné.
- Pokud chcete tuto funkci použít, musí být zařízení připojená ke službě Active Directory Domain Services nebo k síti na pracovišti.
- Zaregistrovaná zařízení musí používat Windows 10 verze 1511 nebo novější.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Přidružení účtu ve Windows Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte **Microsoft Intune**.

> [!NOTE]
> Dřív bylo možné přidružit k Windows Storu pro firmy pouze jeden nástroj pro správu na přiřazování aplikací. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## <a name="configure-synchronization"></a>Konfigurace synchronizace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1. V okně **Mobilní aplikace** zvolte **Nastavení** > **Windows Store pro firmy**.
2. Klikněte na **Povolit**.
3. Pokud jste to ještě neudělali, klikněte na odkaz pro registraci Windows Storu pro firmy a podle předchozího postupu přidružte svůj účet.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se aplikace z Windows Storu pro firmy zobrazují na portálu Intune. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené ve Windows Storu do Intune.

## <a name="synchronize-apps"></a>Synchronizace aplikací

1. V úloze **Mobilní aplikace** zvolte **Nastavení** > **Windows Store pro firmy**.
2. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené ve Windows Storu do Intune.

## <a name="assign-apps"></a>Přiřazení aplikací

Aplikace ze Storu se přiřazují stejně jako jakékoli jiné aplikace Intune. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md). Místo toho, abyste aplikace přiřazovali na stránce **Všechny aplikace**, je ale budete přiřazovat na stránce **Licencované aplikace**.

Offline aplikace mohou být cílené na skupiny uživatelů, skupiny zařízení nebo skupiny s uživateli a zařízeními.
Offline aplikace se dají nainstalovat pro konkrétního uživatele na zařízení nebo pro všechny uživatele na zařízení. 


Když přiřadíte aplikaci z Windows Storu pro firmy, využije licenci každý uživatel, který si ji nainstaluje. Když využijete všechny dostupné licence přiřazené aplikace, nebudete už moct přiřadit žádné další kopie. Proveďte jednu z následujících akcí:
* Odinstalovat aplikaci z některých zařízení.
* Omezit rozsah aktuálního přiřazení tak, aby jeho cílem byli jen uživatelé, pro které máte dost licencí.
* Zakoupit ve Windows Storu pro firmy další kopie příslušné aplikace.


