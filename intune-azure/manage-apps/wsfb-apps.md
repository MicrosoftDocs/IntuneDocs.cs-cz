---
title: "Správa aplikací z Windows Storu pro firmy"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Zjistěte, jak můžete synchronizovat aplikace z Windows Storu pro firmy do Intune a pak je přiřadit a sledovat."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d02d7c3367e18c96cc1d72de3a3a0ef581ef63ff
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Správa aplikací zakoupených ve Windows Storu pro firmy v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


[Windows Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svoji organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete spravovat hromadně zakoupené aplikace pomocí portálu Intune. Například:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole pro správu Intune a můžete je přiřadit stejně jako všechny ostatní aplikace.
* V konzole pro správu Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatečný počet licencí, Intune blokuje nasazení a instalaci aplikací.

## <a name="before-you-start"></a>Než začnete
Než začnete synchronizovat a nasazovat aplikace z Windows Storu pro firmy, přečtěte si následující informace:
* Musíte nakonfigurovat Intune jako autoritu správy mobilních zařízení pro svoji organizaci.
* Musíte mít zaregistrovaný účet ve Windows Storu pro firmy.
* Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
* Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Windows Storem pro firmy.
* Intune synchronizuje jenom aplikace s online licencemi, které jste zakoupili ve Windows Storu pro firmy.
* Pokud chcete tuto funkci použít, musí být zařízení připojená ke službě Active Directory Domain Services nebo k síti na pracovišti.
* Zaregistrovaná zařízení musí používat Windows 10 verze 1511 nebo novější.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Přidružení účtu ve Windows Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte **Microsoft Intune**.

> [!NOTE]
> Pokud k nasazování aplikací pro Windows Store pro firmy používáte více než jeden nástroj pro správu, mohli jste k Windows Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## <a name="configure-synchronization"></a>Konfigurace synchronizace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
1. V okně **Mobilní aplikace** zvolte **Nastavení** > **Windows Store pro firmy**.
2. Klikněte na **Povolit**.
3. Pokud jste to ještě neudělali, klikněte na odkaz pro registraci Windows Storu pro firmy a podle předchozího postupu přidružte svůj účet.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se mají aplikace z Windows Storu pro firmy zobrazovat na portálu Intune. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené ve Windows Storu do Intune.

## <a name="synchronize-apps"></a>Synchronizace aplikací

1. V úloze **Spravovat aplikace** zvolte **Nastavení** > **Windows Store pro firmy**.
2. Kliknutím na **Synchronizovat** přeneste aplikace zakoupené ve Windows Storu do Intune.

## <a name="assign-apps"></a>Přiřazení aplikací

Aplikace ze Storu se přiřazují stejně jako všechny ostatní aplikace v Intune. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](deploy-apps.md). Místo toho, abyste aplikace přiřazovali na stránce **Všechny aplikace**, je ale budete přiřazovat na stránce **Licencované aplikace**.

Když přiřadíte aplikaci z Windows Storu pro firmy, využije licenci každý uživatel, který si ji nainstaluje. Když využijete všechny dostupné licence nasazené aplikace, už nebudete moct nasadit žádné další kopie. Musíte provést některý z těchto kroků:
* Odinstalovat aplikaci z některých zařízení.
* Snížit rozsah aktuálního nasazení tak, aby jeho cílem byli jenom uživatelé, pro které máte dostatek licencí.
* Zakoupit ve Windows Storu pro firmy další kopie příslušné aplikace.

> [!Important]
> Nasazené aplikace jsou dostupné jenom pro uživatele, který zařízení původně zaregistroval. Ostatní uživatelé k nim nemají přístup.

