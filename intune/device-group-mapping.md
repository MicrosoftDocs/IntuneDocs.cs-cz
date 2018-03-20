---
title: "Kategorizace zařízení do skupin v Intune"
titleSuffix: Microsoft Intune
description: "Zjistěte, jak můžete pomocí kategorizace zařízení do skupin zajistit snadnější správu."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d07b025881ea78299d617205ce5ba39bb92a1231
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Snadnější správa pomocí kategorizace zařízení do skupin

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kategorie zařízení v Microsoft Intune slouží k automatickému přidávání zařízení do skupin na základě kategorií, které definujete, aby byla správa těchto zařízení jednodušší.

Pro kategorie zařízení se používá následující pracovní postup:
1. Vytvoření kategorií, ze kterých si mohou uživatelé vybrat při registraci svého zařízení
2. Když koncoví uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Pokud chce koncový uživatel zařízení s Windows zařadit do některé kategorie, musí použít web Portál společnosti (podrobnější informace najdete v části **Po konfiguraci skupin zařízení** v tomto článku).
3. Do těchto skupin pak můžete nasadit zásady a aplikace.

Můžete vytvořit libovolné kategorie zařízení, například:
- Zařízení POS
- Předváděcí zařízení
- Prodej
- Účtárna
- Manager

## <a name="how-to-configure-device-categories"></a>Jak konfigurovat kategorie zařízení

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Krok 1: Vytvoření kategorií zařízení v okně Intune na portálu Azure Portal
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení**.
2. V okně **Registrace zařízení** zvolte **Kategorie zařízení**.
3. Na stránce **Kategorie zařízení** zvolte **Vytvořit**, abyste mohli přidat novou kategorii.
4. V okně **Vytvořit kategorii zařízení** zadejte **název** nové kategorie a případně i její **popis**.
5. Až skončíte, klikněte na **Vytvořit**. Novou kategorii uvidíte v seznamu kategorií.

Název kategorie zařízení použijete při vytváření skupin zabezpečení Azure Active Directory v kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2: Vytvoření skupin zabezpečení Azure Active Directory
V tomto kroku vytvoříte na webu Azure Portal dynamické skupiny na základě kategorie zařízení a názvu kategorie zařízení.

Další postup najdete v článku o [použití atributů k vytváření rozšířených pravidel](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) v dokumentaci k Azure Active Directory.

Pomocí informací v tomto oddílu můžete vytvořit skupinu zařízení s rozšířeným pravidlem využívajícím atribut **deviceCategory**. Příklad: **device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*".

Až nakonfigurujete skupiny zařízení, bude se uživatelům při registrování jejich zařízení zobrazovat seznam nakonfigurovaných kategorií. Až si zvolí kategorii a dokončí registraci, přidá se jejich zařízení do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Zobrazení kategorií spravovaných zařízení

1.  V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Zařízení**.

2.  V části **Spravovat** klikněte na **Všechna zařízení**.

3.  V seznamu zařízení zkontrolujte sloupec **Kategorie zařízení**.

Pokud sloupec **Kategorie zařízení** není zobrazený, klikněte na **Sloupce**, zvolte v seznamu položku **Kategorie zařízení** a pak klikněte na **Použít**.

### <a name="to-change-the-category-of-a-device"></a>Změna kategorie zařízení

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Zařízení**.
2. V okně **Zařízení** v části **Spravovat** zvolte **Všechna zařízení**.
3. Zvolte v seznamu požadované zařízení a pak v okně s vlastnostmi zařízení v části **Spravovat** zvolte **Vlastnosti**.
4. V dalším okně můžete pro vybrané zařízení změnit nastavení **Kategorie zařízení** na kterýkoliv z názvů kategorií, které jste dříve nakonfigurovali.

## <a name="after-you-configure-device-groups"></a>Po konfiguraci skupin zařízení

Když koncoví uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Potom, co zvolí kategorii a dokončí registraci, se jejich zařízení přidá do skupiny zařízení Intune nebo do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

Koncoví uživatelé s Windows by měli k výběru kategorie použít web Portál společnosti.

Bez ohledu na platformu můžou koncoví uživatelé po registraci zařízení vždy přejít na portal.manage.microsoft.com. Uživatelé by měli mít přístup k webu Portál společnosti a měli by přejít na **Moje zařízení**. Na této stránce můžou zvolit zaregistrované zařízení a pak vybrat kategorii.

Když vyberete kategorii, přidá se zařízení automaticky k příslušné vámi vytvořené skupině. Pokud je už zařízení zaregistrované před tím, než nakonfigurujete kategorie, zobrazí se koncovým uživatelům na webu Portál společnosti oznámení o zařízení a žádost, aby při příštím přístupu k aplikaci Portál společnosti v iOSu nebo Androidu vybrali kategorii.

## <a name="further-information"></a>Další informace
- Kategorii zařízení můžete upravit na portálu Azure Portal, ale musíte ručně aktualizovat všechny skupiny zabezpečení Azure Active Directory, které na tuto kategorii odkazují.

- Pokud některou kategorii odstraníte, zobrazí se u všech zařízení, která jsou do ní zařazená, hodnota **Nepřiřazeno**.
