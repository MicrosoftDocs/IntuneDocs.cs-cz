---
title: Ověření nastavení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak otestovat, že je vaše zásady ochrany aplikací nastavené a funguje správně v Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 760ff85bc31cf66e66a3bf98f7da22d5ce48eee0
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292233"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>Jak ověřit nastavení zásad ochrany aplikací v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Prověřte, jestli jsou vaše zásady ochrany aplikací správně nastavené a jestli fungují. Tento návod se vztahuje k zásadám ochrany aplikací na portálu Azure Portal.

## <a name="checking-for-symptoms"></a>Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože ochrana aplikací je nástroj na ochranu dat. Pokud dojde k potížím s konfigurací ochrany aplikací, uživatel bude mít neomezený přístup, jak by měli bez ochrany aplikací, a nebude ví, že se vyskytl problém. Z tohoto důvodu doporučujeme, abyste že měli ověřit konfiguraci ochrany aplikací pomocí pilotní nasazení zásad ochrany aplikací s malou skupinou uživatelů, kteří mohou omezení ochrany aplikací cíleně vyzkoušet.

## <a name="what-to-check"></a>Co zkontrolovat

Pokud testování odhalí chování zásady ochrany vaší aplikace nefunguje podle očekávání, zkontrolujte tyto položky:

- Mají uživatelé licenci k ochraně aplikací?
- Mají uživatelé licenci k O365?
- Je stav všech uživatelů aplikace ochrany aplikací podle očekávání. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

### <a name="user-app-protection-status"></a>Stav uživatele ochrany aplikací
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Vyberte **klientské aplikace** >  **stav ochrany aplikace**a pak vyberte **přiřazení uživatelé** dlaždici. 
4. Na **vytváření sestav aplikace** stránce **vybrat uživatele** zobrazíte seznam uživatelů a skupin. 
5. Vyhledejte a vyberte uživatele ze seznamu a pak zvolte **vybrat uživatele**. V horní části **vytváření sestav aplikace** podokně, zobrazí se, zda má uživatel licenci k ochraně aplikací. Uvidíte také, jestli má uživatel licenci k O365 a jaký je stav aplikace pro všechny uživatele zařízení.

## <a name="what-to-do"></a>Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel nemá licenci k ochraně aplikací, přiřaďte [licence Intune](licenses.md) uživateli.
- Pokud uživatel nemá licenci k O365, získejte [licence](licenses.md) pro daného uživatele.
- Pokud je aplikace uživatele uvedená jako **není zaregistrováno**, zkontrolujte, jestli jste správně nakonfigurovali [zásady ochrany aplikací](app-protection-policies-validate.md) pro tuto aplikaci.
- Ujistěte se, že platí tyto podmínky přes všechny uživatele, u kterých chcete [zásady ochrany aplikací](app-protection-policies-monitor.md) použít.

## <a name="see-also"></a>Viz také:

- [Co jsou zásady ochrany aplikací Intune?](app-protection-policies.md)
- [Licence, které zahrnují Intune](licenses.md)
- [Přiřazení licencí uživatelům, aby mohli zaregistrovat zařízení v Intune](licenses-assign.md)
- [Jak ověřit nastavení zásad ochrany aplikací](app-protection-policies-validate.md)
- [Jak monitorovat zásady ochrany aplikací](app-protection-policies-monitor.md)

