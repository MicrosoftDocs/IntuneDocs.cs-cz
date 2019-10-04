---
title: Registrace zařízení se systémem iOS – registrace uživatele
titleSuffix: Microsoft Intune
description: Přečtěte si, jak nastavit registraci uživatele pro iOS a iPadOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57162664d6ca3a35696e56088c4e86acadf45371
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955457"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>Nastavení registrace uživatele pro iOS a iPadOS (Preview)

Můžete nastavit Intune pro registraci zařízení s iOS a iPadOS pomocí procesu registrace uživatele od společnosti Apple. Registrace uživatele poskytuje správcům zjednodušenou podmnožinu možností správy ve srovnání s jinými metodami registrace.

Další informace o možnostech, které jsou k dispozici pro zápis uživatele, najdete v tématu věnovaném [akcím registrace uživatelů, heslům a dalším možnostem](ios-user-enrollment-supported-actions.md).

> [!NOTE]
> Podpora registrace uživatelů společnosti Apple v Intune je momentálně ve verzi Preview.

## <a name="prerequisites"></a>Požadavky
- [Autorita pro správu mobilních zařízení (MDM)](../fundamentals/mdm-authority-set.md)
- [Apple MDM push Certificate](apple-mdm-push-certificate-get.md)
- [Spravovaná Apple ID](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web).

## <a name="create-a-user-enrollment-profile-in-intune"></a>Vytvoření profilu registrace uživatele v Intune

Registrační profil definuje nastavení použité pro skupinu zařízení během registrace. 

1. Na portálu Intune vyberte **registrace zařízení** > **registrace Apple** > **typy registrace (Preview)**  > **vytvořit profil** > **iOS**. V tomto profilu určíte, jaké možnosti registrace budou mít koncoví uživatelé iOS a iPadOS na zařízeních, která nejsou zaregistrovaná prostřednictvím podnikové metody Apple. Pokud byste chtěli provést změny, můžete tento profil po jeho vytvoření upravit.

    ![Vytvořit registrační profil Apple](./media/ios-user-enrollment/create-profile.png)

2. Na stránce **základy** zadejte **název** a **Popis** profilu pro účely správy. Uživatelé tyto podrobnosti nevidí. Pomocí tohoto pole **název** můžete vytvořit dynamickou skupinu v Azure Active Directory. Pomocí názvu profilu definujte parametr enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [Azure Active Directory dynamických skupinách](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices).

    ![Stránka základy](./media/ios-user-enrollment/basics-page.png)


3. Vyberte **Další**.

4. Na stránce **Nastavení** se můžete rozhodnout, že uživatelům dáte možnost výběru typu zápisu, který budou používat. Alternativně můžete nastavit výchozí nastavení.

    ![Stránka nastavení](./media/ios-user-enrollment/settings-page.png)

    - Pokud chcete, aby všichni uživatelé v tomto profilu používali zápis uživatele, postupujte takto:
        1. Pokud **chcete, aby uživatel vybral typ zařízení**, vyberte **nenakonfigurované**.
        2. **Jako výchozí typ registrace**vyberte **registrace uživatele**.
    - Pokud chcete, aby všichni uživatelé v tomto profilu používali registraci zařízení, postupujte podle následujících kroků:
        1. Pokud **chcete, aby uživatel vybral typ zařízení**, vyberte **nenakonfigurované**.
        2. Jako **výchozí typ registrace**vyberte **registrace zařízení**.
    - Pokud chcete všem uživatelům v této skupině dát možnost zvolit typ registrace, který se má použít, vyberte možnost **požadováno** , aby **uživatel vybral typ zařízení**. Když uživatelé registrují svá zařízení, budou mít možnost zvolit si **vlastní nastavení tohoto zařízení** a **(společnost) Toto zařízení vlastní**. Pokud zvolí předchozí, zařízení se zaregistruje pomocí registrace uživatele. Pokud si tyto možnosti zvolí, zařízení se zaregistruje pomocí registrace zařízení. Pokud uživatel zvolí **Toto zařízení jako vlastní**, získá další možnost zabezpečení celého zařízení nebo pouze zabezpečené aplikace a data související s prací. Výběr koncového uživatele, který vlastní zařízení, určuje, který typ registrace se na zařízení implementuje. Tato volba uživatele se neprojeví v atributu vlastnictví zařízení v Intune. Další informace o uživatelském prostředí najdete v tématu [nastavení přístupu zařízení s iOS k prostředkům společnosti](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).
    
    > [!NOTE]
    > Následující upozornění je nepřesné a bude odebráno z uživatelského rozhraní.
    > "Pokud chcete mít podmíněný přístup k práci na zařízeních, která cílí na registraci uživatelů, budete muset aplikaci Azure Authenticator nainstalovat jako požadovanou aplikaci pro tuto skupinu uživatelů, aby se povolilo jednotné přihlašování a Workplace Join."
    > Jako správce není nutné provádět žádnou akci, abyste mohli aplikaci ověřovatele nabízet vašim uživatelům. Vaši uživatelé budou mít pokyn v rámci Portál společnosti k instalaci ověřovací aplikace k dokončení procesu registrace uživatele, aby tyto scénáře správně fungovaly.

5. Vyberte **Další**.

6. Na stránce **přiřazení** vyberte skupiny uživatelů obsahující uživatele, kterým chcete tento profil přiřadit. Můžete se rozhodnout přiřadit profil všem uživatelům nebo konkrétním skupinám. Všichni uživatelé ve vybraných skupinách použijí vybraný typ registrace. Skupiny zařízení nejsou podporované pro scénáře registrace uživatelů, protože tato funkce je založená na identitách uživatelů, nikoli na zařízeních. Můžete se rozhodnout přiřadit profil všem uživatelům nebo konkrétním skupinám.

    ![Stránka přiřazení](./media/ios-user-enrollment/assignments-page.png)

7. Vyberte **Další**.

8. Na stránce **Kontrola a vytváření** Zkontrolujte své volby a pak vyberte **vytvořit** a přiřaďte profil uživatelům.

    ![Stránka přiřazení](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Priorita profilu

Po vytvoření více než jednoho profilu typu registrace můžete změnit pořadí priorit, ve kterém se používají.

1. V Intune v Azure Portal vyberte **registrace zařízení** >  registrace**Apple** > **typy registrace (Preview)** .
2. Profily v seznamu můžete přetáhnout v pořadí, v jakém se mají použít.

V případě konfliktů mezi profily pro každého uživatele se pro uživatele použije profil s vyšší prioritou.


