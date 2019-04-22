---
title: Vyžadování vícefaktorového ověřování pro registraci zařízení v Intune
titleSuffix: Microsoft Intune
description: Jak vyžadovat vícefaktorové ověřování ve službě Azure AD pro registraci zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf5611b3b9292222582d66cae39b4f751279dcec
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897676"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Vyžadování vícefaktorového ověřování pro registraci zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune dokáže používat vícefaktorové ověřování služby Azure Active Directory AD (AD) pro registraci zařízení a pomáhá tak zabezpečit firemní prostředky.

Vícefaktorové ověřování funguje tak, že vyžaduje jakékoliv dvě nebo více z následujících metod ověřování:

- Něco, co víte (obvykle heslo nebo PIN).
- Něco, co máte (důvěryhodné zařízení, které není lehké duplikovat, jako je telefon).
- Něco, co je vaše (biometrika, třeba otisk prstu)

Vícefaktorové ověřování se podporuje u zařízení se systémem iOS, Android, Windows 8.1 nebo novějším, Windows Phone 8.1 nebo novějším a Windows 10 Mobile nebo novějším.

Když je povolené, musí koncoví uživatelé při registraci zařízení zadat dvě formy přihlašovacích údajů.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurace služby Intune tak, aby při registraci zařízení vyžadovala vícefaktorové ověřování

K vynucení vícefaktorového ověřování při registraci zařízení slouží tento postup:

>[!Important]
>Abyste mohli implementovat tyto zásady, musí mít vaši uživatelé přiřazený plán Azure Active Directory Premium P1 nebo vyšší.

>[!Important]
>Pro registraci v Microsoft Intune nekonfigurujte **pravidla přístupu na základě zařízení**.

1. Přihlaste se pomocí svých přihlašovacích údajů na [Microsoft Azure Portal](https://portal.azure.com).
2. Na portálu přejděte na **Intune** a zvolte **podmíněného přístupu**. Uzlu podmíněný přístup k němu přistupovat z *Intune* je stejný uzel, protože k němu přistupovat z *Azure AD*.
4. Zvolte **Nové zásady**.
5. V **nové zásadě** zadejte popisný název této zásady.
6. V části **Přiřazení** zvolte **Uživatelé a skupiny**. 
7. V oblasti **Uživatelé a skupiny** zvolte **Vybrat uživatele nebo skupiny** a zaškrtněte políčko **Uživatelé a skupiny**. Pak vyberte uživatele a/nebo skupiny, které obdrží tyto zásady, a zvolte **Hotovo**.
8. V části **Přiřazení** zvolte **Cloudové aplikace**.
9. Na kartě **Zahrnout** okna **Cloudové aplikace** zvolte **Vybrat aplikace**, pak zvolte **Vybrat** > **Registrace v Microsoft Intune** a nakonec zvolte **Hotovo**.
10. V oddílu **Přiřazení** nemusíte pro **Podmínky** konfigurovat žádné nastavení vícefaktorového ověřování.
11. V části **Ovládací prvky přístupu** zvolte **Udělení**.
12. V okně **Udělení** zvolte **Udělit přístup** a pak vyberte **Vyžadovat vícefaktorové ověřování**. Nevybírejte **Vyžadovat, aby zařízení bylo označené jako vyhovující**, protože dokud není zařízení zaregistrované, nelze vyhodnotit, nakolik vyhovuje. Pak zvolte **Vybrat**.
13. V **nové zásadě** zvolte **Povolit zásadu** > **Zapnuto** a pak zvolte **Vytvořit**.



## <a name="next-steps"></a>Další postup

Když koncoví uživatelé registrují svá zařízení, musí se teď ověřit druhou formou identifikace, jako je PIN kód, telefon nebo biometrika.
