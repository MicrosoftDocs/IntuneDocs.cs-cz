---
title: "Použití TeamVieweru pro vzdáleně spravovaná zařízení s Androidem"
titlesuffix: Azure portal
description: "Přečtěte si, jak vzdáleně spravovat zařízení s Androidem pomocí TeamVieweru."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da908316989598134edc7ab46491890f81676db6
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune

Intune vám prostřednictvím softwaru [TeamViewer](https://www.teamviewer.com) (kupuje se zvlášť) umožňuje poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Androidem. Informace v tomto tématu vám pomůžou začít tuto možnost využívat.

## <a name="before-you-start"></a>Než začnete

### <a name="required-permissions"></a>Požadovaná oprávnění

Zkontrolujte, jestli má uživatel portálu Azure Portal přiřazená jako [role Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) následující oprávnění:
- Aby mohl správce změnit nastavení Konektoru pro TeamViewer, udělte mu oprávnění **Aktualizovat Vzdálenou pomoc**.
- Aby mohl správce iniciovat novou žádost o vzdálenou pomoc, udělte mu oprávnění **Požádat o Vzdálenou pomoc**. Uživatelé s oprávněním **Požádat o Vzdálenou pomoc** můžou požádat o zahájení relace pro libovolného uživatele. Neomezuje je při tom žádný rozsah přiřazení rolí v Intune. Rozsahy přiřazení rolí Intune neomezují zařízení nebo uživatele, pro které lze iniciovat žádosti o Vzdálenou pomoc.

>[!NOTE]
>Tím, že povolíte TeamViewer, umožníte Konektoru pro TeamViewer služby Intune vytvářet relace TeamVieweru, číst data služby Active Directory a ukládat přístupový token účtu TeamVieweru.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurace Konektoru pro TeamViewer služby Intune

Než budete moct poskytovat vzdálenou pomoc pro zařízení s Androidem, je nutné pomocí následujících kroků nakonfigurovat Konektor pro TeamViewer služby Intune:


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Nastavení** > **Konektor pro TeamViewer**.
5. V okně **Konektor pro TeamViewer** klikněte na **Povolit**, potom zobrazte licenční smlouvu služby TeamViewer a přijměte ji.
6. Zvolte **Přihlásit se k TeamVieweru pro autorizaci**.
7. Otevře se webová stránka TeamVieweru. Zadejte přihlašovací údaje pro svoji licenci TeamVieweru a pak klikněte na **Přihlásit se**.


## <a name="how-to-remotely-administer-an-android-device"></a>Vzdálená správa zařízení s Androidem

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Spravovat** > **Všechna zařízení**.
5. Vyberte zařízení, které chcete vzdáleně spravovat, a v okně vlastností zařízení zvolte **Další** > **Nová relace Vzdálené pomoci**.
6. Až se Intune ke službě TeamViewer připojí, zobrazí se některé informace o zařízení s Androidem. Vzdálenou relaci spustíte volbou **Připojit**.

![Okna TeamVieweru pro Android](./media/android-teamviewer.png)

V okně TeamVieweru můžete na zařízení s Androidem provádět různé vzdálené akce, například vzdálené řízení zařízení. Úplné informace o akcích, které můžete provádět, najdete v [dokumentaci k TeamVieweru](https://www.teamviewer.com/support/documents/).

Až budete hotovi, okno TeamVieweru zavřete.

## <a name="end-user-notifications"></a>Oznámení pro koncového uživatele

Koncovému uživateli se na zařízení u ikony aplikace Portál společnosti zobrazí příznak oznámení. Oznámení se zobrazí také při otevření aplikace. Potom může žádost o vzdálenou pomoc přijmout.

