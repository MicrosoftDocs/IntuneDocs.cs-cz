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
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0872eef38e3ea5a70ebb64d3ae3c62069045fa97
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754612"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>Nastavení registrace uživatele pro iOS a iPadOS (Preview)

Můžete nastavit Intune pro registraci zařízení s iOS a iPadOS pomocí procesu registrace uživatele od společnosti Apple. Registrace uživatele poskytuje správcům zjednodušenou podmnožinu možností správy ve srovnání s jinými metodami registrace.

Další informace o možnostech, které jsou k dispozici pro zápis uživatele, najdete v tématu věnovaném [akcím registrace uživatelů, heslům a dalším možnostem](ios-user-enrollment-supported-actions.md).

> [!NOTE]
> Podpora registrace uživatelů společnosti Apple v Intune je momentálně ve verzi Preview.

## <a name="prerequisites"></a>Požadované součásti
- [Autorita pro správu mobilních zařízení (MDM)](../fundamentals/mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Spravovaná Apple ID](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web).

## <a name="create-a-user-enrollment-profile-in-intune"></a>Vytvoření profilu registrace uživatele v Intune

Registrační profil definuje nastavení použité pro skupinu zařízení během registrace. 

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **zařízení** > **iOS** > **registrace ios** > **typy registrace (Preview)**  > **vytvořit profil** > **iOS/iPadOS**. V tomto profilu určíte, jaké možnosti registrace budou mít koncoví uživatelé iOS a iPadOS na zařízeních, která nejsou zaregistrovaná prostřednictvím podnikové metody Apple. Pokud byste chtěli provést změny, můžete tento profil po jeho vytvoření upravit.

    ![Vytvořit registrační profil Apple](./media/ios-user-enrollment/create-profile.png)

2. Na stránce **základy** zadejte **název** a **Popis** profilu pro účely správy. Uživatelé tyto podrobnosti nevidí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices).

    ![Základní informace o stránce](./media/ios-user-enrollment/basics-page.png)


3. Vyberte **Další**.

4. Na stránce **Nastavení** vyberte jednu z následujících možností pro **typ registrace**:

    ![Stránka Nastavení](./media/ios-user-enrollment/settings-page.png)

    - **Registrace zařízení**: všichni uživatelé v tomto profilu budou používat registraci zařízení.
    - **Zápis uživatele**: všichni uživatelé v tomto profilu použijí zápis uživatele.
    - **Určení podle výběru uživatele**: všichni uživatelé v této skupině budou mít možnost zvolit typ registrace, který se má použít. Když si uživatelé zaregistrují svá zařízení, uvidí možnost vybrat si **vlastní** zařízení a zařízení **(společnosti)** , které je vlastníkem tohoto zařízení. Pokud si tyto možnosti zvolí, zařízení se zaregistruje pomocí registrace zařízení. Pokud uživatel zvolí **Toto zařízení jako vlastní**, získá další možnost zabezpečení celého zařízení nebo pouze zabezpečené aplikace a data související s prací. Výběr, který typ registrace je implementován na zařízení, určí koncový uživatel, který vlastní zařízení. Tato volba uživatele se taky odráží v atributu vlastnictví zařízení v Intune. Další informace o uživatelském prostředí najdete v tématu [nastavení přístupu zařízení s iOS k prostředkům společnosti](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).
    
5. Vyberte **Další**.

6. Na stránce **přiřazení** vyberte skupiny uživatelů obsahující uživatele, kterým chcete tento profil přiřadit. Můžete se rozhodnout přiřadit profil všem uživatelům nebo konkrétním skupinám. Všichni uživatelé ve vybraných skupinách použijí vybraný typ registrace. Skupiny zařízení nejsou podporované pro scénáře registrace uživatelů, protože tato funkce je založená na identitách uživatelů, nikoli na zařízeních. Můžete se rozhodnout přiřadit profil všem uživatelům nebo konkrétním skupinám.

    ![Stránka přiřazení](./media/ios-user-enrollment/assignments-page.png)

7. Vyberte **Další**.

8. Na stránce **Kontrola a vytváření** Zkontrolujte své volby a pak vyberte **vytvořit** a přiřaďte profil uživatelům.

    ![Stránka přiřazení](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Priorita profilu

Po vytvoření více než jednoho profilu typu registrace můžete změnit pořadí priorit, ve kterém se používají.

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **zařízení** > **iOS** > **Registrace iOS** > **typy registrace (Preview)** .
2. Profily v seznamu můžete přetáhnout v pořadí, v jakém se mají použít.

V případě konfliktů mezi profily pro každého uživatele se pro uživatele použije profil s vyšší prioritou.


