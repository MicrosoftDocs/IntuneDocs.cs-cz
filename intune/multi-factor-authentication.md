---
title: "Vícefaktorové ověřování pro registraci zařízení v Intune"
titleSuffix: Intune on Azure
description: "Jak vyžadovat vícefaktorové ověřování ve službě Azure AD pro registraci zařízení"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 4789f94d06f61219dea3faa64a4ed0c59afcd56b
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/12/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Vícefaktorové ověřování pro registraci zařízení v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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
>Pro registraci v Microsoft Intune nekonfigurujte **pravidla přístupu na základě zařízení**.

1. Přihlaste se pomocí svých přihlašovacích údajů na [Microsoft Azure Portal](https://portal.azure.com).
2. Na tomto portálu zvolte **Azure Active Directory**.
2. Ve službě **Azure Active Directory** zvolte **Spravovat** > **Podnikové aplikace**.
3. V okně **Podnikové aplikace** zvolte **Spravovat** > **Všechny aplikace**. Uvidíte seznam všech aplikací Azure, které spravujete.
3. V tomto seznamu zvolte **Registrace v Microsoft Intune**.
4. V okně **Registrace v Microsoft Intune** zvolte **Zabezpečení** > **Podmíněný přístup**.
5. Zvolte **Nové zásady**.
6. V **nové zásadě** zadejte popisný název této zásady.
7. V části **Přiřazení** zvolte **Uživatelé a skupiny**.
8. V okně **Uživatelé a skupiny** zvolte uživatele nebo skupiny, které tuto zásadu dostanou, a pak zvolte **Hotovo**.
9. V části **Přiřazení** zvolte **Cloudové aplikace**.
10. Na kartě **Zahrnout** okna **Cloudové aplikace** zvolte **Vybrat aplikace**, pak zvolte **Vybrat** > **Registrace v Microsoft Intune** a nakonec zvolte **Hotovo**.
11. V části **Přiřazení** zvolte **Podmínky**.
12. V okně **Podmínky** nemusíte pro vícefaktorové ověřování konfigurovat žádná nastavení.
13. V části **Ovládací prvky přístupu** zvolte **Udělení**.
14. V okně **Udělení** zvolte **Udělit přístup** a pak vyberte **Vyžadovat vícefaktorové ověřování**.
    Nevybírejte **Vyžadovat, aby zařízení bylo označené jako vyhovující**, protože dokud není zařízení zaregistrované, nelze vyhodnotit, nakolik vyhovuje.
15. Zvolte **Vybrat**.
16. V **nové zásadě** zvolte **Povolit zásadu** > **Zapnuto** a pak zvolte **Vytvořit**.



## <a name="next-steps"></a>Další kroky

Když koncoví uživatelé registrují svá zařízení, musí se teď ověřit druhou formou identifikace, jako je PIN kód, telefon nebo biometrika.