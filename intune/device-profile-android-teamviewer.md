---
title: "Použití TeamVieweru ke vzdálené správě zařízení"
titlesuffix: Azure portal
description: "Přečtěte si, jak vzdáleně spravovat zařízení pomocí TeamVieweru."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8bb3061baf42b011c98cf7b196e939448f91cff4
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/20/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Poskytování vzdálené pomoci pro zařízení spravovaná pomocí Intune

Intune vám prostřednictvím softwaru [TeamViewer](https://www.teamviewer.com) (kupuje se zvlášť) umožňuje poskytovat vzdálenou pomoc uživatelům zařízení, která spravujete. Informace v tomto tématu vám pomůžou začít tuto možnost využívat.

## <a name="before-you-start"></a>Než začnete

### <a name="supported-devices"></a>Podporovaná zařízení

Vzdálenou správu podporují tato zařízení spravovaná pomocí Intune:

- Zařízení s Androidem spravovaná pomocí Intune
- Zařízení s Windows spravovaná pomocí Intune a používající Windows 10, Windows 10 Mobile a novější.

>[!NOTE]
>Windows Holographic (HoloLens), Windows Team (Surface Hub) a Windows 10 S software TeamViewer nepodporuje.



### <a name="required-permissions"></a>Požadovaná oprávnění

Zkontrolujte, jestli má uživatel portálu Azure Portal přiřazená jako [role Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) následující oprávnění:
- Aby mohl správce změnit nastavení Konektoru pro TeamViewer, udělte mu oprávnění **Aktualizovat Vzdálenou pomoc**.
- Aby mohl správce iniciovat novou žádost o vzdálenou pomoc, udělte mu oprávnění **Požádat o Vzdálenou pomoc**. Uživatelé s oprávněním **Požádat o Vzdálenou pomoc** můžou požádat o zahájení relace pro libovolného uživatele. Neomezuje je při tom žádný rozsah přiřazení rolí v Intune. Rozsahy přiřazení rolí Intune neomezují zařízení nebo uživatele, pro které lze iniciovat žádosti o Vzdálenou pomoc.

>[!NOTE]
>Tím, že povolíte TeamViewer, umožníte Konektoru pro TeamViewer služby Intune vytvářet relace TeamVieweru, číst data služby Active Directory a ukládat přístupový token účtu TeamVieweru.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurace Konektoru pro TeamViewer služby Intune

Než budete moct poskytovat vzdálenou pomoc pro zařízení, je nutné pomocí následujících kroků nakonfigurovat konektor Intune pro TeamViewer:


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Nastavení** > **Konektor pro TeamViewer**.
5. V okně **Konektor pro TeamViewer** klikněte na **Povolit**, potom zobrazte licenční smlouvu služby TeamViewer a přijměte ji.
6. Zvolte **Přihlásit se k TeamVieweru pro autorizaci**.
7. Otevře se webová stránka TeamVieweru. Zadejte přihlašovací údaje pro svoji licenci TeamVieweru a pak klikněte na **Přihlásit se**.


## <a name="how-to-remotely-administer-a-device"></a>Vzdálená správa zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Spravovat** > **Všechna zařízení**.
5. Vyberte zařízení, které chcete vzdáleně spravovat, a v okně vlastností zařízení zvolte **Další** > **Nová relace Vzdálené pomoci**.
6. Až se Intune ke službě TeamViewer připojí, zobrazí se některé informace o zařízení. Vzdálenou relaci spustíte volbou **Připojit**.

![Příklad TeamVieweru pro Android](./media/android-teamviewer.png)

V okně TeamVieweru můžete na zařízení provádět různé vzdálené akce, třeba vzdálené řízení zařízení. Úplné informace o akcích, které můžete provádět, najdete v [dokumentaci k TeamVieweru](https://www.teamviewer.com/support/documents/).

Až budete hotovi, okno TeamVieweru zavřete.

## <a name="next-steps"></a>Další kroky

Koncovému uživateli se na zařízení u ikony aplikace Portál společnosti zobrazí příznak oznámení. Oznámení se zobrazí také při otevření aplikace. Potom může žádost o vzdálenou pomoc přijmout.

