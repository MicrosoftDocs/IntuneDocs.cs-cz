---
title: Nastavení omezení registrace v Microsoft Intune
titleSuffix: ''
description: Omezení registrace podle platformy a nastavení limitu pro registraci zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d96cd3e6496bbfde35a666bfcf4a1f6427e45173
ms.sourcegitcommit: 11ae6a37527ef5b3ac042743950254f3ef559c53
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2019
ms.locfileid: "72280245"
---
# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce Intune můžete vytvořit a spravovat omezení registrace, která definují, jaká zařízení se můžou registrovat ke správě pomocí Intune, včetně těchto:
- počet zařízení
- operační systémy a verze: můžete vytvořit více omezení a použít je u různých skupin uživatelů. Můžete nastavit [pořadí priorit](#change-enrollment-restriction-priority) pro různá omezení.

>[!NOTE]
>Omezení registrace nejsou bezpečnostní funkce. Napadená zařízení můžou poskytovat zavádějící informace svůj znak. Tato omezení představují nejlepší bariéru pro uživatele, kteří nejsou škodliví.

Konkrétní omezení registrace, která můžete vytvořit, zahrnují:

- Maximální počet zaregistrovaných zařízení.
- Platformy zařízení, které se můžou zaregistrovat:
  - Správce zařízení s Androidem
  - Pracovní profil Android Enterprise
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- Verze operačního systému platformy pro iOS, Správce zařízení s Androidem, pracovní profil Android Enterprise, Windows a Windows Mobile. (Dá se použít jenom verze Windows 10. Pokud je povoleno Windows 8.1, ponechte toto prázdné.)
  - Minimální verze
  - Maximální verze
- Omezte zařízení v osobním vlastnictví (jenom iOS, Správce zařízení s Androidem, pracovní profil Android Enterprise, macOS, Windows a Windows Mobile).

## <a name="default-restrictions"></a>Výchozí omezení

Výchozí omezení se automaticky poskytují pro omezení registrace typu zařízení i omezení registrace zařízení. Můžete změnit možnosti pro výchozí nastavení. Výchozí omezení se vztahují na všechny registrace uživatelů a uživatelů. Tato výchozí nastavení můžete přepsat vytvořením nových omezení s vyšší prioritou.

## <a name="create-a-device-type-restriction"></a>Vytvoří omezení typu zařízení.

1. Přihlaste se k Azure Portal.
2. Vyberte **Další služby**, vyhledejte **Intune**a pak zvolte **Intune**.
3. Vyberte **registrace zařízení** > **omezení registrace** >  omezení**Create**a omezení**typu zařízení** > .
    @no__t – 0Screen Cap pro vytvoření omezení typu zařízení @ no__t-1
4. Na stránce **základy** poskytněte omezení **název** a volitelný **Popis**.
5. Kliknutím na tlačítko **Další** přejdete na stránku **Nastavení platformy** .
6. V části **platforma**vyberte možnost **Povolení** pro platformy, u kterých chcete toto omezení omezit.
    @no__t – 0Screen Cap pro výběr nastavení platformy @ no__t-1
7. V části **verze**vyberte minimální a maximální verze, které mají povolené platformy podporovat. Omezení verze se vztahují jenom na zařízení zaregistrovaná ve Portál společnosti.
     Mezi podporované formáty verzí patří:
    - Správce zařízení s Androidem a pracovní profil Android Enterprise podporují hlavní. podverze. rev. Build.
    - iOS podporuje hlavní_verze. podverze. rev. Verze operačního systému se nevztahují na zařízení Apple, která se registrují pomocí Program registrace zařízení, Apple School Manageru nebo aplikace Apple Configuratoru.
    - Windows podporuje jenom hlavní_verze. podverze. Build. rev jenom pro Windows 10.
    > [!Note]
    > Windows 10 neposkytuje během registrace číslo rev, takže pokud zadáte v 10.0.17134.100 a zařízení bude 10.0.17134.174, bude během registrace zablokované.

8. V části **osobní vlastnictví**vyberte **Povolit** pro platformy, které chcete povolit jako zařízení v osobním vlastnictví.
9. Kliknutím na tlačítko **Další** přejdete na stránku **přiřazení** .
10. Zvolte **Vybrat skupiny, které chcete zahrnout** , a potom pomocí vyhledávacího pole vyhledejte skupiny, které chcete zahrnout do tohoto omezení. Omezení platí pouze pro skupiny, ke kterým je přiřazena. Pokud omezení nepřiřazujte aspoň na jednu skupinu, nebude to mít žádný vliv. Pak zvolte **Vybrat**. 
    @no__t – 0Screen Cap pro výběr nastavení platformy @ no__t-1
11. Kliknutím na tlačítko **Další** přejdete na stránku **Revize + vytvořit** .
12. Vyberte **vytvořit** a vytvořte tak omezení.
13. Nové omezení se vytvoří s prioritou hned nad výchozí hodnotou. Prioritu můžete [změnit](#change-enrollment-restriction-priority).


## <a name="create-a-device-limit-restriction"></a>Vytvoření omezení limitu počtu zařízení

1. Přihlaste se k Azure Portal.
2. Vyberte **Další služby**, vyhledejte **Intune**a pak zvolte **Intune**.
3. Vyberte **registrace zařízení** > **omezení registrace** >  omezení**Vytvoření**omezení**počtu zařízení** > .
    @no__t – 0Screen Cap pro vytváření omezení limitu počtu zařízení @ no__t-1
4. Na stránce **základy** poskytněte omezení **název** a volitelný **Popis**.
5. Kliknutím na tlačítko **Další** přejdete na stránku **omezení počtu zařízení** .
6. V poli **limit počtu zařízení**vyberte maximální počet zařízení, která může uživatel zaregistrovat.
    @no__t – 0Screen Cap pro výběr limitu zařízení @ no__t-1
7. Kliknutím na tlačítko **Další** přejdete na stránku **přiřazení** .
8. Zvolte **Vybrat skupiny, které chcete zahrnout** , a potom pomocí vyhledávacího pole vyhledejte skupiny, které chcete zahrnout do tohoto omezení. Omezení platí pouze pro skupiny, ke kterým je přiřazena. Pokud omezení nepřiřazujte aspoň na jednu skupinu, nebude to mít žádný vliv. Pak zvolte **Vybrat**. 
    @no__t – 0Screen limit pro výběr skupin @ no__t-1
11. Kliknutím na tlačítko **Další** přejdete na stránku **Revize + vytvořit** .
12. Vyberte **vytvořit** a vytvořte tak omezení.
13. Nové omezení se vytvoří s prioritou hned nad výchozí hodnotou. Prioritu můžete [změnit](#change-enrollment-restriction-priority).

Během registrace BYOD se uživatelům zobrazí oznámení, které jim oznámí, že dosáhli maximálního počtu zaregistrovaných zařízení. Například v systému iOS:

![oznámení o limitu zařízení s iOS](./media/enrollment-restrictions-set/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Omezení limitu počtu zařízení se nevztahují na tyto typy zápisu Windows:
> - Spoluspravované registrace
> - Registrace objektů zásad skupiny
> - Azure Active Directory připojené registrace
> - Registrace do hromadné Azure Active Directory připojené
> - Registrace autopilotu
> - Registrace správce registrace zařízení
>
> Omezení limitu počtu zařízení pro tyto typy registrace se neuplatňují, protože se považují za scénáře sdíleného zařízení.
> Můžete nastavit omezení pro tyto typy zápisu [v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).


## <a name="change-enrollment-restrictions"></a>Změna omezení registrace

Nastavení omezení registrace můžete změnit podle následujících kroků. Tato omezení neovlivňují zařízení, která jsou už zaregistrovaná. U zařízení zaregistrovaných v [agentovi Intune PC agent](../fundamentals/manage-windows-pcs-with-microsoft-intune.md) nejde tuto funkci zablokovat.

1. Přihlaste se k Azure Portal.
2. Vyberte **Další služby**, vyhledejte **Intune**a pak zvolte **Intune**.
3. Vyberte **registrace zařízení** > **omezení registrace** > zvolte omezení, u kterého chcete změnit **vlastnosti**>.
4. Klikněte na tlačítko **Upravit** vedle nastavení, které chcete změnit.
5. Na stránce **Upravit** proveďte požadované změny a přejděte na stránku **Revize + Uložit** a pak zvolte **Uložit**.


## <a name="blocking-personal-android-devices"></a>Blokování osobních zařízení s Androidem
- Pokud zablokujete registraci zařízení s osobním vlastnictvím zařízení s Androidem, můžou se zařízení s Androidem Enterprise Work profilů pořád zaregistrovat.
- Ve výchozím nastavení jsou nastavení zařízení vašeho pracovního profilu Android Enterprise shodná s nastavením vašich zařízení pro správce zařízení s Androidem. Až změníte pracovní profil pro Android Enterprise nebo nastavení Správce zařízení s Androidem, to už neplatí.
- Pokud zablokujete osobní registraci pracovních profilů pro Android Enterprise, můžou se registrovat jenom zařízení s Androidem ve vlastnictví firmy v Android Enterprise Working Profiles.

## <a name="blocking-personal-windows-devices"></a>Blokování osobních zařízení s Windows
Pokud zablokujete registraci zařízení s Windows osobně vlastněných společností, Intune zkontroluje, jestli má každá nová žádost o registraci Windows oprávnění k podnikové registraci. Neautorizované registrace budou zablokovány.

Následující metody jsou způsobilé k autorizaci jako registrace podnikového systému Windows:
- Registrace uživatele používá [účet správce registrace zařízení]( device-enrollment-manager-enroll.md).
- Zařízení se registruje pomocí automatických [pilotů Windows](enrollment-autopilot.md).
- Zařízení se zaregistruje u automatického pilotního nasazení Windows, ale v nastavení Windows se nejedná o možnost jenom registrace MDM.
- Číslo IMEI zařízení je uvedené v části **registrace zařízení**@no__t **[identifikátory podnikových zařízení](corporate-identifiers-add.md)** -1. (Není podporováno pro Windows Phone 8,1.)
- Zařízení se zaregistruje prostřednictvím [balíčku hromadného zřizování](windows-bulk-enroll.md).
- Zařízení se registruje prostřednictvím objektu zásad skupiny nebo [automatického zápisu z SCCM pro spolusprávu](https://docs.microsoft.com/sccm/comanage/quickstart-paths#bkmk_path1).
 
Intune označí jako firemní tyto registrace. Protože ale nenabízí řízení Intune pro správu jednotlivých zařízení, zablokují se:
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [Azure Active Directory JOIN během instalace systému Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [Azure Active Directory JOIN z nastavení systému Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Zablokují se taky tyto metody osobní registrace:
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) pomocí [možnosti Přidat pracovní účet z nastavení systému Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- Možnost [registrace MDM pouze]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) z nastavení systému Windows.

\*. tyto nebudou zablokovány, pokud jsou zaregistrovány s autopilotem.


## <a name="change-enrollment-restriction-priority"></a>Změna priority omezení registrace

Priorita se používá v případě, že uživatel existuje ve více skupinách, kterým jsou přiřazena omezení. Na uživatele se vztahuje jenom omezení s nejvyšší prioritou přiřazená ke skupině, ve které se nacházejí. Například Jana je ve skupině A přiřazená k omezení priority 5 a také ve skupině B přiřazené k omezení 2. Jana je předmětem pouze omezení priority 2.

Když vytvoříte omezení, přidá se do seznamu bezprostředně nad výchozí.

Registrace zařízení zahrnuje výchozí omezení pro omezení typu zařízení i omezení počtu zařízení. Tato dvě omezení platí pro všechny uživatele, pokud nejsou přepsána omezeními s vyšší prioritou.

Prioritu můžete změnit bez výchozího omezení.

1. Přihlaste se k Azure Portal.
2. Vyberte **Další služby**, vyhledejte **Intune**a pak zvolte **Intune**.
3. Vyberte **registrace zařízení**@no__t 1 –**omezení registrace**.
4. Najeďte myší na omezení v seznamu priorit.
5. Pomocí tří svislých teček přetáhněte prioritu na požadované místo v seznamu.
