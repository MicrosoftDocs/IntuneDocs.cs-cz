---
title: "Kategorizace zařízení pomocí mapování skupin zařízení | Microsoft Intune"
description: "Mapování skupin zařízení Microsoft Intune slouží k seskupení zařízení do kategorií, které definujete, aby bylo možné zjednodušit správu těchto zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: 84850f4e9136e6304e51991d6ab0a0ae2a37e7a7


---

# Kategorizace zařízení pomocí mapování skupin zařízení v Microsoft Intune
**Mapování skupin zařízení** v Microsoft Intune slouží k automatickému přidávání zařízení do skupin na základě kategorií, které definujete, aby byla správa těchto zařízení jednodušší. 

Mapování skupin zařízení používá následující postup:
1. Vytvořte kategorie, ze kterých uživatelé budou volit při registraci zařízení.
2. Vytvoříte skupiny nebo použijete existující skupiny pro každou kategorii, kterou chcete použít. Podle verze Intune, kterou používáte, to budou buď skupiny Intune, nebo skupiny zabezpečení Azure Active Directory.
2. Nakonfigurujete pravidla, která mapují kategorii, kterou zvolíte, na skupinu zařízení, kterou jste vytvořili.
3. Když koncoví uživatelé registrují svá zařízení, musí zvolit některou kategorii ze seznamu nakonfigurovaných kategorií. Po této volbě se jejich zařízení automaticky přidá do příslušné skupiny, kterou jste vytvořili. Pokud je zařízení už zaregistrované, bude koncový uživatel požádán o výběr kategorie při příštím přístupu k aplikaci Portál společnosti.
4. Do těchto skupin pak můžete nasadit zásady a aplikace.

Můžete vytvořit libovolné kategorie zařízení, například:
* Zařízení POS
* Předváděcí zařízení
* Prodej
* Účtárna
* Správce

## Důležité informace o změně ve správě skupin Intune

Na základě vaší zpětné vazby momentálně sjednocujeme prostředí pro vyváření skupin a cílů v rámci Enterprise Mobility + Security. Z tohoto důvodu brzy převedeme skupiny Intune na skupiny zabezpečení Azure Active Directory. Po této změně už nebudete moct vytvářet skupiny pomocí Intune. Místo toho je vytvoříte na webu Azure Portal. Dojde k tomu postupně, přičemž úplné podrobnosti o této změně a jejím načasování najdete v [tomto tématu](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### Který postup v tomto tématu byste měli použít ke konfiguraci mapování skupin zařízení?

Vzhledem k postupné implementaci skupin zabezpečení Azure Active Directory musíte otevřít pracovní prostor **Skupiny** v [konzole pro správu Intune](https://manage.microsoft.com) a zjistit, který postup máte použít:

-  Pokud uvidíte odkaz na Azure Portal, skupiny Intune už nepoužíváte. Použijte níže uvedený postup [Jak nakonfigurovat mapování skupin zařízení (u skupin Azure Active Directory)](##How-to-configure-device-group-mapping-(for-Azure-Active-Directory-groups).
-  Pokud odkaz na Azure Portal nevidíte, pořád používáte skupiny Intune. Použijte níže uvedený postup [Jak nakonfigurovat mapování skupin zařízení (u skupin Intune)](##How-to-configure-device-group-mapping-(for-Intune-groups).

## Jak nakonfigurovat mapování skupin zařízení u skupin Intune
1. Pro každou kategorii zařízení, kterou chcete použít, vytvořte skupinu zařízení Intune, nebo vyberte existující skupinu. Informace o postupu při vytváření skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**.
3. V pracovním prostoru **Správa** rozbalte položku **Správa mobilních zařízení** a pak zvolte **Mapování skupin zařízení**.
4. Na stránce **Mapování skupin zařízení** povolte mapování skupin zařízení.
5. Pokud chcete vytvořit nové pravidlo mapování, zvolte **Přidat**.
6. V dialogovém okně **Přidat pravidlo mapování skupin zařízení** zadejte název kategorie, kterou chcete vytvořit, a potom z rozevíracího seznamu vyberte kolekci zařízení, na kterou chcete mapovat tuto kategorii. Až skončíte, zvolte **Přidat**.
7. Po dokončení přidávání kategorií a skupin zvolte **Uložit**.



## Jak nakonfigurovat mapování skupin zařízení u skupin Azure Active Directory

### Krok 1: Vytvoření kategorií zařízení v konzole pro správu Intune
1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**.
3. V pracovním prostoru **Správa** rozbalte **Správa mobilních zařízení** a pak zvolte **Kategorie zařízení**.
4. Na stránce **Kategorie zařízení** uvidíte seznam, kde můžete konfigurovat kategorie zařízení: 
- Můžete zadat název a kliknutím na **Přidat** ho přidat jako novou kategorii zařízení.
- Některou kategorii můžete také vybrat a pak ji **Odstranit**.

Název kategorie zařízení použijete při vytváření skupin zabezpečení Azure Active Directory v kroku 2.

### Krok 2: Vytvoření skupin zabezpečení Azure Active Directory

V tomto kroku vytvoříte na webu Azure Portal dynamické skupiny na základě kategorie zařízení a názvu kategorie zařízení.

Pokud chcete pokračovat, přečtěte si téma [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) v dokumentaci služby Azure Active Directory.
Pomocí informací v tomto tématu vytvořte skupinu zařízení s rozšířeným pravidlem pomocí atributu **deviceCategory**.
Příklad: (**device.deviceCategory -eq** "<*název kategorie zařízení, který jste získali z konzoly pro správu Intune*>")


## Po konfiguraci skupin zařízení

Když uživatelé registrují svoje zařízení, zobrazí se jim seznam nakonfigurovaných kategorií. Potom, co zvolí kategorii a dokončí registraci, se jejich zařízení přidá do skupiny zařízení Intune nebo do skupiny zabezpečení Active Directory, která odpovídá zvolené kategorii.

### Viz taky
[Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Oct16_HO2-->


