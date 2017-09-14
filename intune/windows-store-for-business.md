---
title: "Správa aplikací z Microsoft Storu pro firmy"
titlesuffix: Azure portal
description: "Zjistěte, jak můžete synchronizovat aplikace z Microsoft Storu pro firmy do Intune a pak je přiřazovat a sledovat."
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
ms.openlocfilehash: 649766b26a1061c4bce11235c04dcbe8570fcdc4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Správa aplikací zakoupených v Microsoft Storu pro firmy v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


[Microsoft Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svou organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete hromadně zakoupené aplikace spravovat z Azure Portalu. Například:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole pro správu Intune. Tyto aplikace můžete přiřadit stejně jako všechny ostatní aplikace.
* V konzole pro správu Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatečný počet licencí, blokuje Intune přiřazení a instalaci aplikací.

## <a name="before-you-start"></a>Než začnete

Než začnete synchronizovat a přiřazovat aplikace z Microsoft Storu pro firmy, přečtěte si následující informace:

- Nakonfigurujte Intune jako autoritu správy mobilních zařízení pro svoji organizaci.
- Musíte mít zaregistrovaný účet v Microsoft Storu pro firmy.
- Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
- Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Microsoft Storem pro firmy.
- Intune synchronizuje aplikace s online i offline licencemi, které jste zakoupili v Microsoft Storu pro firmy.
- V Intune se synchronizují jenom offline aplikace, které jsou bezplatné.
- Pokud chcete tuto funkci použít, musí být zařízení připojená ke službě Active Directory Domain Services nebo k síti na pracovišti.
- Zaregistrovaná zařízení musí používat Windows 10 verze 1511 nebo novější.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Přidružení účtu v Microsoft Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte **Microsoft Intune**.

> [!NOTE]
> Dřív bylo možné přidružit k Microsoft Storu pro firmy jenom jeden nástroj pro správu na přiřazování aplikací. Teď už jich můžete přidružit více, například Intune a Configuration Manager.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## <a name="configure-synchronization"></a>Konfigurace synchronizace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1. V okně **Mobilní aplikace** zvolte **Nastavení** > **Microsoft Store pro firmy**.
2. Klikněte na **Povolit**.
3. Pokud jste to ještě neudělali, klikněte na odkaz pro registraci Microsoft Storu pro firmy a podle předchozího postupu přidružte svůj účet.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se aplikace z Microsoft Storu pro firmy zobrazují na Azure Portalu. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené v Microsoft Storu do Intune.

## <a name="synchronize-apps"></a>Synchronizace aplikací

1. V úloze **Mobilní aplikace** zvolte **Nastavení** > **Microsoft Store pro firmy**.
2. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené v Microsoft Storu do Intune.

## <a name="assign-apps"></a>Přiřazení aplikací

Aplikace ze Storu se přiřazují stejně jako jakékoli jiné aplikace Intune. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md). Místo toho, abyste aplikace přiřazovali na stránce **Všechny aplikace**, je ale budete přiřazovat na stránce **Licencované aplikace**.

Offline aplikace mohou být cílené na skupiny uživatelů, skupiny zařízení nebo skupiny s uživateli a zařízeními.
Offline aplikace se dají nainstalovat pro konkrétního uživatele na zařízení nebo pro všechny uživatele na zařízení. 


Když přiřadíte aplikaci z Microsoft Storu pro firmy, využije licenci každý uživatel, který si ji nainstaluje. Když využijete všechny dostupné licence přiřazené aplikace, nebudete už moct přiřadit žádné další kopie. Proveďte jednu z následujících akcí:
* Odinstalovat aplikaci z některých zařízení.
* Omezit rozsah aktuálního přiřazení tak, aby jeho cílem byli jen uživatelé, pro které máte dost licencí.
* Zakoupit v Microsoft Storu pro firmy další kopie příslušné aplikace.


