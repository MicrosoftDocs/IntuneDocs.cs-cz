---
title: Kategorizace zařízení do skupin v Intune
titleSuffix: Microsoft Intune
description: Zjistěte, jak můžete pomocí kategorizace zařízení do skupin zajistit snadnější správu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f63c5a3dbeb7c8626ec1412dbcee661b82afc88
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896007"
---
# <a name="categorize-devices-into-groups"></a>Kategorizace zařízení do skupin

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Abychom usnadnili správu zařízení, můžete použít kategorií zařízení Microsoft Intune k automatickému přidávání zařízení do skupin podle kategorií, které definujete.

Pro kategorie zařízení se používá následující pracovní postup:
1. Vytvořte kategorie, z kterých si uživatelé při registraci svého zařízení můžou vybrat.
2. Když uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu, který jste nakonfigurovali. K přiřazení kategorie zařízení s Windows musí uživatelé použít web Portálu společnosti.
3. Do těchto skupin pak můžete nasadit zásady a aplikace.

Kategorie zařízení můžete vytvořit zcela podle svých potřeb. Příklad:
- Zařízení POS
- Předváděcí zařízení
- Prodej
- Účtárna
- Manager

## <a name="how-to-configure-device-categories"></a>Jak konfigurovat kategorie zařízení

### <a name="step-1-create-device-categories-on-the-intune-blade-of-the-azure-portal"></a>Krok 1: Vytvoření kategorií zařízení v okně Intune na portálu Azure Portal
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení**.
2. V okně **Registrace zařízení** zvolte **Kategorie zařízení**.
3. Na stránce **Kategorie zařízení** zvolte **Vytvořit**, abyste mohli přidat novou kategorii.
4. V okně **Vytvořit kategorii zařízení** zadejte **název** nové kategorie a případně i její **popis**.
5. Až to budete mít, vyberte **Vytvořit**. Novou kategorii uvidíte v seznamu kategorií.

Název kategorie zařízení použijete při vytváření skupin zabezpečení Azure Active Directory (Azure AD) v kroku 2.

### <a name="step-2-create-azure-active-directory-security-groups"></a>Krok 2: Vytvoření skupin zabezpečení Azure Active Directory
V tomto kroku vytvoříte na webu Azure Portal dynamické skupiny na základě kategorie zařízení a názvu kategorie zařízení.

Pokud chcete pokračovat, přečtěte si v dokumentaci služby Azure AD téma [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects).

S využitím informací v tomto oddílu můžete vytvořit skupinu zařízení s rozšířeným pravidlem využívajícím atribut **deviceCategory**. Příklad: **device.deviceCategory -eq** "*název kategorie zařízení, který jste získali z portálu Azure Portal*"

Až nakonfigurujete skupiny zařízení, bude se uživatelům při registrování jejich zařízení zobrazovat seznam nakonfigurovaných kategorií. Až si zvolí kategorii a dokončí registraci, přidá se jejich zařízení do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

### <a name="view-the-categories-of-devices-that-you-manage"></a>Zobrazení kategorií zařízení, která spravujete

1.  V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Zařízení**.

2.  V části **Spravovat** vyberte **Všechna zařízení**.

3.  V seznamu zařízení zkontrolujte sloupec **Kategorie zařízení**.

Pokud se sloupec **Kategorie zařízení** nezobrazuje, vyberte **Sloupce**. V seznamu zvolte **Kategorie zařízení** a vyberte **Použít**.

### <a name="change-the-category-of-a-device"></a>Změna kategorie zařízení

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Zařízení**.
2. V okně **Zařízení** v části **Spravovat** zvolte **Všechna zařízení**.
3. V seznamu vyberte požadované zařízení. Pak v okně s vlastnostmi zařízení v části **Spravovat** zvolte **Vlastnosti**.
4. V dalším okně můžete pro vybrané zařízení změnit nastavení **Kategorie zařízení** na kterýkoliv z názvů kategorií, které jste dříve nakonfigurovali.

## <a name="after-you-configure-device-groups"></a>Po konfiguraci skupin zařízení

Když uživatelé zařízení s iOSem a Androidem registrují svá zařízení, musí zvolit některou kategorii ze seznamu, který jste nakonfigurovali. Jakmile zvolí kategorii a dokončí registraci, jejich zařízení se přidá do skupiny zařízení Intune nebo do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

Uživatelé s Windows musí k výběru kategorie použít web Portál společnosti.

Bez ohledu na platformu můžou uživatelé po registraci zařízení vždycky použít stránku portal.manage.microsoft.com. Požádejte uživatele, ať přejdou na web Portál společnosti a na něm do části **Moje zařízení**. Na této stránce můžou zvolit zaregistrované zařízení a pak vybrat kategorii.

Když vyberete kategorii, přidá se zařízení automaticky k příslušné vámi vytvořené skupině. Pokud se zařízení už zaregistrovalo předtím, než jste nakonfigurovali kategorie, uživateli se oznámení o něm zobrazí na webu Portál společnosti. Uživatel se tak dozví, že má při příštím přístupu k aplikaci Portál společnosti v iOSu nebo Androidu vybrat kategorii.

## <a name="further-information"></a>Další informace
- Kategorii zařízení můžete upravit na portálu Azure Portal, ale musíte ručně aktualizovat všechny skupiny zabezpečení Azure AD, které na tuto kategorii odkazují.

- Pokud některou kategorii odstraníte, zobrazí se u všech zařízení, která jsou do ní zařazená, hodnota **Nepřiřazeno**.
