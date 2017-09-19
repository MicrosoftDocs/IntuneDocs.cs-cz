---
title: "Používání kategorií zařízení v Intune"
titleSuffix: Azure portal
description: "Naučte se používat kategorie zařízení, které uživatelé můžou volit, když si registrují svoje zařízení v Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e34b9cd030244db4bdde78eedbb0f874f49fa1e1
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="map-device-groups"></a>Mapování skupin zařízení


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kategorie zařízení v Microsoft Intune slouží k automatickému přidávání zařízení do skupin na základě kategorií, které definujete, aby byla správa těchto zařízení jednodušší.

Pro kategorie zařízení se používá následující pracovní postup:
1. Vytvořte kategorie, ze kterých uživatelé budou volit při registraci zařízení.
3. Když koncoví uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Pokud chcete přiřadit kategorii k zařízení s Windows, musí koncoví uživatelé používat web Portál společnosti (podrobnosti najdete v části **Po konfiguraci skupin zařízení** v tomto tématu).
4. Do těchto skupin pak můžete nasadit zásady a aplikace.

Můžete vytvořit libovolné kategorie zařízení, například:
- Zařízení POS
- Předváděcí zařízení
- Prodej
- Účtárna
- Manager

## <a name="how-to-configure-device-categories"></a>Jak konfigurovat kategorie zařízení

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Krok 1: Vytvoření kategorií zařízení v okně Intune na portálu Azure Portal
1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
3. V okně **Registrace zařízení** zvolte **Kategorie zařízení**.
4. V okně **Kategorie zařízení** zvolte **Vytvořit**, abyste mohli přidat novou kategorii.
5. V dalším okně zadejte **název** nové kategorii a případně i její **popis**.
6. Až skončíte, klikněte na **Vytvořit**. Kategorie, kterou jste právě vytvořili, se objeví v seznamu kategorií.

Název kategorie zařízení použijete při vytváření skupin zabezpečení Azure Active Directory v kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2: Vytvoření skupin zabezpečení Azure Active Directory
V tomto kroku vytvoříte na webu Azure Portal dynamické skupiny na základě kategorie zařízení a názvu kategorie zařízení.

Pokud chcete pokračovat, přečtěte si téma [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) v dokumentaci služby Azure Active Directory. 

Pomocí informací v tomto oddílu můžete vytvořit skupinu zařízení s rozšířeným pravidlem využívajícím atribut **deviceCategory**. Příklad: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Až nakonfigurujete skupiny zařízení, bude se uživatelům při registrování jejich zařízení zobrazovat seznam nakonfigurovaných kategorií. Až si zvolí kategorii a dokončí registraci, přidá se jejich zařízení do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Zobrazení kategorií spravovaných zařízení

1.  Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune na portálu Azure Portal zvolte **Zařízení a skupiny**.

3.  V části **Spravovat** klikněte na **Všechna zařízení**.

4.  V seznamu zařízení zkontrolujte sloupec **Kategorie**.

Pokud sloupec **Kategorie** není zobrazený, klikněte na **Sloupce**, zvolte v seznamu položku **Kategorie** a pak klikněte na **Použít**.

### <a name="to-change-the-category-of-a-device"></a>Změna kategorie zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení a skupiny**.
4. V okně **Zařízení a skupiny** zvolte **Spravovat** > **Všechna zařízení**.
5. Zvolte požadované zařízení v seznamu a pak v okně s vlastnostmi zařízení zvolte **Spravovat** > **Vlastnosti**.
6. V dalším okně můžete pro vybrané zařízení změnit nastavení **Kategorie zařízení** na kterýkoliv z názvů kategorií, které jste dříve nakonfigurovali.

## <a name="after-you-configure-device-groups"></a>Po konfiguraci skupin zařízení

Když koncoví uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Potom, co zvolí kategorii a dokončí registraci, se jejich zařízení přidá do skupiny zařízení Intune nebo do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

Pokud chcete přiřadit kategorii k zařízení s Windows, musí koncoví uživatelé používat po registraci zařízení web Portál společnosti (portal.manage.microsoft.com). Na zařízení s Windows přejděte na web a potom na možnost **Nabídka** > **Moje zařízení**. Vyberte zaregistrované zařízení na stránce a potom vyberte kategorii. 

Když vyberete kategorii, přidá se zařízení automaticky k příslušné vámi vytvořené skupině. Pokud je už zařízení zaregistrované před tím, než nakonfigurujete kategorie, zobrazí se koncovým uživatelům na webu Portál společnosti oznámení o zařízení a žádost, aby při příštím přístupu k aplikaci Portál společnosti v iOSu nebo Androidu vybrali kategorii.

## <a name="further-information"></a>Další informace
- Kategorii zařízení můžete upravit na portálu Azure Portal, ale pokud to uděláte, musíte ručně aktualizovat všechny skupiny zabezpečení Azure Active Directory, které na tuto kategorii odkazují.

- Pokud nějakou kategorii odstraníte, bude se u všech zařízení, která k ní byla přiřazená, následně zobrazovat název kategorie **Nepřiřazeno**.


