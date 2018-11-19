---
title: Ověření nastavení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak otestovat, jestli jsou vaše zásady ochrany aplikací správně nastavené a jestli fungují.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0a207d3e845e3983dfe6ce3abbb70fcbbe65cf
ms.sourcegitcommit: 4d5e811d451aeb6307e0f64818e182e471ae1ed4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2018
ms.locfileid: "51618969"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Ověření nastavení zásad ochrany aplikací

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Prověřte, jestli jsou vaše zásady ochrany aplikací správně nastavené a jestli fungují. Tento návod se vztahuje k zásadám ochrany aplikací na portálu Azure Portal.

### <a name="checking-for-symptoms"></a>Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože ochrana aplikací je nástroj na ochranu dat. Pokud dojde k nějakému problému s konfigurací ochrany aplikací uživatele má neomezený přístup, jako bez ochrany aplikací a nemusíte vědět, že se vyskytl problém. Z tohoto důvodu doporučujeme, abyste že měli ověřit konfiguraci ochrany aplikací pomocí pilotní nasazení zásad ochrany aplikací s malou skupinou uživatelů, kteří mohou omezení ochrany aplikací cíleně vyzkoušet.


### <a name="what-to-check"></a>Co zkontrolovat

Pokud testování odhalí chování zásady ochrany vaší aplikace není podle očekávání, zkontrolujte tyto položky:

- Mají uživatelé licenci k ochraně aplikací?
- Mají uživatelé licenci k O365?
- Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

#### <a name="user-app-protection-status"></a>Stav uživatele ochrany aplikací
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Vyberte **klientské aplikace** > **monitorování** >  **stav ochrany aplikace**a pak vyberte **přiřazení uživatelé**dlaždici. 
4. Na **vytváření sestav aplikace** stránce **vybrat uživatele** zobrazíte seznam uživatelů a skupin. 
5. Vyhledejte a vyberte uživatele ze seznamu a pak zvolte **vybrat uživatele**. V horní části **vytváření sestav aplikace** podokně, zobrazí se, zda má uživatel licenci k ochraně aplikací. Uvidíte také, jestli má uživatel licenci k O365 a jaký je stav aplikace pro všechny uživatele zařízení.



### <a name="what-to-do"></a>Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel nemá licenci k ochraně aplikací, přiřadíte licence Intune uživateli.
- Pokud uživatel nemá licenci k O365, získání licence pro uživatele.
- Pokud je aplikace uživatele uvedená se stavem **Není zaregistrováno**, zkontrolujte, jestli jste pro tuto aplikaci správně nakonfigurovali zásady ochrany aplikací.
- Ujistěte se, že platí tyto podmínky přes všechny uživatele, u kterých chcete použít zásady ochrany aplikací.

### <a name="see-also"></a>Viz také

[Co jsou zásady ochrany aplikací Intune?](app-protection-policies.md)
