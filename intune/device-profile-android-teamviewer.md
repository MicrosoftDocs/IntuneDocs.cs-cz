---
title: "Použití TeamVieweru pro vzdáleně spravovaná zařízení s Androidem"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak vzdáleně spravovat zařízení s Androidem pomocí TeamVieweru."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15a005ae2b84c7bd4f913f892089965c10f3b23e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune

Intune vám pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se kupuje zvlášť, umožňuje poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Androidem. K nastavení a zahájení práce použijte informace v tomto tématu.

## <a name="before-you-start"></a>Než začnete

### <a name="required-permissions"></a>Požadovaná oprávnění

Zkontrolujte, jestli má uživatel portálu Azure Portal přiřazená jako [role Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) následující oprávnění:
- Aby mohl správce změnit nastavení Konektoru pro TeamViewer, udělte mu oprávnění **Aktualizovat Vzdálenou pomoc**.
- Aby mohl správce iniciovat nastavení nové vzdálené pomoci, udělte mu oprávnění **Požádat o Vzdálenou pomoc**. Uživatelé s tímto oprávněním můžou požadovat zahájení relace pro libovolného uživatele. Neomezuje to žádný rozsah přiřazení rolí Intune. Rozsahy přiřazení rolí Intune neomezují zařízení nebo uživatele, pro které lze iniciovat žádosti o Vzdálenou pomoc.

>[!NOTE]
>Tím, že povolíte TeamViewer, umožníte Konektoru pro TeamViewer služby Intune vytvářet relace TeamVieweru, číst data služby Active Directory a ukládat přístupový token účtu TeamVieweru.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurace Konektoru pro TeamViewer služby Intune

Předtím, než budete moct poskytovat vzdálenou pomoc pro zařízení s Androidem, je nutné pomocí následujících kroků nakonfigurovat Konektor pro TeamViewer služby Intune:


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

Až budete hotoví, zavřete okno TeamVieweru.

## <a name="end-user-notifications"></a>Oznámení koncovému uživateli

Koncovému uživateli se zobrazí na jeho zařízení u ikony aplikace Portál společnosti příznak oznámení. Při otevření aplikace se mu také zobrazí oznámení. Potom může žádost o vzdálenou pomoc přijmout.

