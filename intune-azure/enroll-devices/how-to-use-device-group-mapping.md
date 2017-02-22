---
title: "Použití kategorií zařízení v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se používat kategorie zařízení, které uživatelé můžou volit, když si registrují svá zařízení v Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1609ed2f127fe9d7d1f1c3b3e923bd12f1088200
ms.openlocfilehash: 41b3cfb8006a7390094d01b4f0fdc38417e858be


---

# <a name="map-device-groups"></a>Mapování skupin zařízení


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kategorie zařízení v Microsoft Intune slouží k automatickému přidávání zařízení do skupin na základě kategorií, které definujete, aby byla správa těchto zařízení jednodušší.

Pro kategorie zařízení se používá následující pracovní postup:
1.    Vytvořte kategorie, ze kterých uživatelé budou volit při registraci zařízení.
4.    Když koncoví uživatelé registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Pokud je zařízení už zaregistrované, bude koncový uživatel požádán o výběr kategorie při příštím přístupu k aplikaci Portál společnosti.


Můžete vytvořit libovolné kategorie zařízení, například:
- Zařízení POS
- Předváděcí zařízení
- Prodej
- Účtárna
- Manager

## <a name="how-to-configure-device-categories"></a>Jak konfigurovat kategorie zařízení

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Krok 1: Vytvoření kategorií zařízení v okně Intune na portálu Azure Portal
1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Registrovat zařízení**.
3. V okně **Registrace** zvolte **Kategorie zařízení**.
4. V okně **Kategorie zařízení** zvolte **Vytvořit**, abyste mohli přidat novou kategorii.
5. V dalším okně zadejte **název** nové kategorii a volitelně i její **popis**.
6. Až skončíte, klikněte na **Vytvořit**. Kategorie, kterou jste právě vytvořili, se objeví v seznamu kategorií.

Název kategorie zařízení použijete při vytváření skupin zabezpečení Azure Active Directory v kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2: Vytvoření skupin zabezpečení Azure Active Directory
V tomto kroku vytvoříte na webu Azure Portal dynamické skupiny na základě kategorie zařízení a názvu kategorie zařízení.

Pokud chcete pokračovat, přečtěte si téma [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) v dokumentaci služby Azure Active Directory. 

Pomocí informací v tomto oddílu můžete vytvořit skupinu zařízení s rozšířeným pravidlem využívajícím atribut **deviceCategory**. Příklad: (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Až nakonfigurujete skupiny zařízení, bude se uživatelům při registrování jejich zařízení zobrazovat seznam nakonfigurovaných kategorií. Až si zvolí kategorii a dokončí registraci, přidá se jejich zařízení do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Zobrazení kategorií spravovaných zařízení
1.    V okně Intune na portálu Azure Portal zvolte **Zařízení a skupiny**.

2.    V části **Spravovat** klikněte na **Všechna zařízení**.

3.    V seznamu zařízení zkontrolujte sloupec **Kategorie**.

Pokud sloupec **Kategorie** není zobrazený, klikněte na **Sloupce**, zvolte v seznamu položku **Kategorie** a pak klikněte na **Použít**.

### <a name="to-change-the-category-of-a-device"></a>Změna kategorie zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Zařízení a skupiny**.
4. V okně **Zařízení a skupiny** zvolte **Spravovat** > **Všechna zařízení**.
5. Zvolte požadované zařízení v seznamu a pak v okně s vlastnostmi zařízení zvolte **Spravovat** > **Vlastnosti**.
6. V dalším okně můžete pro vybrané zařízení změnit nastavení **Kategorie zařízení** na kterýkoliv z názvů kategorií, které jste dříve nakonfigurovali.



## <a name="further-information"></a>Další informace
- Kategorii zařízení můžete upravit na portálu Azure Portal, ale pokud to uděláte, musíte ručně aktualizovat všechny skupiny zabezpečení Azure Active Directory, které na tuto kategorii odkazují.

- Pokud nějakou kategorii odstraníte, bude se u všech zařízení, která k ní byla přiřazená, následně zobrazovat název kategorie **Nepřiřazeno**.





<!--HONumber=Feb17_HO2-->


