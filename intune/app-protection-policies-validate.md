---
title: Ověření nastavení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak otestovat, jestli jsou vaše zásady ochrany aplikací správně nastavené a jestli fungují.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cac03f35cdec3c1a4815559abc83108bd27d3472
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231111"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Ověření nastavení zásad ochrany aplikací

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Prověřte, jestli jsou vaše zásady ochrany aplikací správně nastavené a jestli fungují. Tento návod se vztahuje k zásadám ochrany aplikací na portálu Azure Portal.

### <a name="checking-for-symptoms"></a>Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože ochrana aplikací je nástroj na ochranu dat. Pokud je s konfigurací ochrany aplikací nějaký problém, uživatelé mají stejně neomezený přístup jako bez ochrany aplikací a o potížích nevědí. Proto doporučujeme, abyste konfiguraci ochrany aplikací prověřili s malou skupinou uživatelů, kteří můžou omezení ochrany aplikací cíleně vyzkoušet.


### <a name="what-to-check"></a>Co zkontrolovat

Pokud testování odhalí, že zásady ochrany aplikací nepřinášejí očekávané výsledky, doporučujeme zkontrolovat tyto položky:

- Mají uživatelé licenci k ochraně aplikací?
- Mají uživatelé licenci k O365?
- Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

#### <a name="user-app-protection-status"></a>Stav uživatele ochrany aplikací
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
1. Zvolte **Spravovat aplikace** > **Monitorovat** >  **Stav ochrany aplikace** > **Přiřazení uživatelé**.

2. Zvolte uživatele v seznamu nebo ho vyhledejte a vyberte a pak zvolte **Vybrat uživatele**. V horní části sloupce **Vytváření sestav aplikace** uvidíte, jestli má uživatel licenci k ochraně aplikací. Také uvidíte, jestli má licenci k O365 a jaký je stav aplikace na všech jeho zařízeních.



### <a name="what-to-do"></a>Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel licenci k ochraně aplikací nemá, přiřaďte mu licenci k Intune.
- Pokud uživatel nemá licenci k O365, získejte ji pro něj.
- Pokud je aplikace uživatele uvedená se stavem **Není zaregistrováno**, zkontrolujte, jestli jste pro tuto aplikaci správně nakonfigurovali zásady ochrany aplikací.
- Dejte pozor, aby se uvedené nastavení použilo pro všechny uživatele, u kterých chcete zásady ochrany aplikací uplatnit.

### <a name="see-also"></a>Viz taky

[Co jsou zásady ochrany aplikací Intune?](app-protection-policies.md)
