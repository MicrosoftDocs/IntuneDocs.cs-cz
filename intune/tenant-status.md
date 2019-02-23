---
title: Stránka stavu Tenanta Microsoft Intune
titleSuffix: Microsoft Intune
description: Na stránce Stav Tenanta Intune můžete zobrazit podrobnosti o důležité tenantovi aniž byste museli opustit portál Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/23/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28a2ef36de4e664668875d2c9a099a573f5cfeba
ms.sourcegitcommit: 68ff00ec0f848f9476740691ed1004144684317e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56667348"
---
# <a name="intune-tenant-status-page"></a>Stránka stavu Tenanta Intune
Na stránce Stav Tenanta je centrála, kde můžete zobrazit aktuální a důležité podrobnosti o vašem tenantovi. Podrobnosti zahrnují dostupnost licencí a použití, stav konektoru a důležité komunikace o službě Intune.  

Chcete-li zobrazit řídicí panel, na Azure portal přejděte do **Intune > Stav Tenanta**.  Stav tenanta se zobrazí v části **Nápověda a podpora skupiny**.  

Na stránce je rozdělen na čtyři oblasti:

## <a name="tenant-details"></a>Podrobnosti o tenantovi
Podrobnosti o tenantovi poskytují informace na přehled o vašem tenantovi. Zobrazit podrobnosti, jako je název vašeho klienta a umístění, vaše autorita MDM a vaše číslo verze služby klientům. Číslo verze služby je odkaz, který otevře *co je nového v Intune* článku na webu Microsoft docs. V *novinky*, si můžete přečíst o nejnovějších funkcích a aktualizacích služby Intune.  

Tato část také obsahuje základní informace o dostupných licencí a kolik jsou přiřazené k uživatelům. Licence pro zařízení se nezobrazují.

## <a name="connector-status"></a>Stav konektoru
Stav konektoru je komplexní umístění Kontrola stavu všech dostupných konektorů pro Intune.  

Konektory jsou:
- **Připojení, které nakonfigurujete pro externí služby**. Například *programu Apple Volume Purchase Program* služby nebo *Windows Autopilot* služby.  Stav pro tento typ konektoru je založen na čas poslední úspěšné synchronizace.
- **Certifikáty nebo přihlašovací údaje, které jsou potřebné pro připojení k externím nespravovaná služba**, třeba *Apple Push Notification Services* certifikáty (APNS). Stav pro tento typ konektoru je založená na časové razítko vypršení platnosti certifikátu nebo přihlašovací údaje.  

Ve výchozím zobrazení zobrazí až o pěti konektory. Můžete vybrat **všechny konektory** rozbalte tohoto seznamu zobrazíte všechny dostupné konektory, včetně konektorů, které nebyly nakonfigurovány pro použití.  

Není v pořádku konektory se vždycky zobrazí v horní části seznamu. Dále jsou konektory spolu s varováními a seznamem konektorů, v pořádku. Zobrazí poslední konektorů, které jste dosud neprovedli konfiguraci.

Když je více než jeden konektor libovolného typu, je stav souhrn pro všechny tyto stejné konektory. Nejméně v pořádku stav všech jeden konektor slouží jako stav pro skupinu.  

**Stav konektoru:**
- **Není v pořádku:**
    - Vypršela platnost certifikátu nebo přihlašovacích údajů
    - Poslední synchronizace proběhla před nejméně tři dny
- **Upozornění:**
    - Certifikát nebo přihlašovací údaje vyprší do 7 dnů
    - Poslední synchronizace proběhla před víc než jeden den
- **V pořádku:**
    - Certifikát nebo přihlašovací údaje, aby platnost během příštích sedm dnů
    - Poslední synchronizace proběhla před méně než jeden den  

Když vyberete konektor v seznamu, zobrazí na portálu stránky portálu, který je relevantní pro vytvoření nebo konfigurace tohoto konektoru.  Například, když vyberete **datum vypršení platnosti VPP** konektor, **tokeny programu hromadných nákupů pro iOS** stránce otevře, kde najdete další podrobnosti o tento konektor. Můžete pak vytvořit novou konfiguraci nebo upravit a opravte problémy s již existující.  

## <a name="intune-service-health"></a>Stav služby Intune  
Můžete zobrazit podrobnosti pro aktivní incidenty a upozornění od společnosti bez nutnosti přejít na řídicí panel s stavu služby Microsoft 365 nebo Centrum zpráv, umístěny v Centru pro správu služeb Microsoft 365 na https://portal.office.com. Jsou zobrazeny pouze incidenty, pokud bylo zaznamenáno dopad ovlivnit vašeho tenanta.  

Když vyberete incident, podrobnosti o incidentu zobrazí přímo na stránce Stav Tenanta. Chcete-li zobrazit minulé poradci a incidentů, vyberte **zobrazit dřívější poradci pro incidenty**. Otevře se Centrum pro správu služeb Microsoft 365 a pak můžete zobrazit poradci a incidenty za posledních 30 dnů pro vašeho tenanta.  

Chcete-li zobrazit informace o *stav služby Intune*, musí mít váš účet **globálního správce** nebo **Správce služeb** role v Azure Active Directory nebo Portál pro správu Office. Pokud chcete přiřadit oprávnění, přihlaste se k [centra pro správu služeb Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) s oprávněními globálního správce. Vyberte **uživatele > aktivní uživatelé**a pak vyberte účet, který vyžaduje přístup. Vyberte **upravit** rolí, vyberte *Správce služeb* nebo *globálního správce*a potom **Uložit** úpravy přiřazení oprávnění.  

Pouze můžete nastavit předvolby komunikace pro stav služby Intune prostřednictvím centra pro správu Microsoftu 365.

## <a name="intune-news"></a>Novinky v Intune  
Zobrazit informační komunikaci od týmu služby Intune bez nutnosti přejít na Centrum zpráv Office. Komunikace zahrnout zprávy o změnách, které nedávno došlo ve službě Intune nebo které jsou na cestě pro vašeho tenanta.  

Ve výchozím zobrazení posledních 10 aktivní zprávy. Chcete-li zobrazit starším zprávám, vyberte **zobrazit dřívější zprávy** otevřít *Centrum zpráv* v portálu System center pro správu služeb Microsoft 365.  

Chcete-li zobrazit informace o Intune zprávy, musí mít váš účet **globálního správce** nebo **Správce služeb** role v Azure Active Directory, nebo **Čtenář Centra zpráv** rolí na portálu správy Office.  Pokud chcete přiřadit toto oprávnění, přihlaste se k [centra pro správu služeb Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) s oprávněními správce. Vyberte **uživatele > aktivní uživatelé**a pak vyberte účet, který vyžaduje přístup. Vyberte **upravit** pro *role*vyberte *týmy komunikace správce*a potom **Uložit** úpravy přiřazení oprávnění.  

Pouze můžete nastavit předvolby komunikace pro Intune příspěvky prostřednictvím centra pro správu Microsoftu 365.
