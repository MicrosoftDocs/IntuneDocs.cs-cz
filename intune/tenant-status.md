---
title: Stránka stavu Tenanta Microsoft Intune
titleSuffix: Microsoft Intune
description: Na stránce Stav Tenanta Intune můžete zobrazit podrobnosti o důležité tenantovi aniž byste museli opustit portál Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98b3180bc90c7b54213781ddf8b6668918b22dd3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203794"
---
# <a name="intune-tenant-status-page"></a>Stránka stavu Tenanta Intune
Na stránce Stav Tenanta jako centrální rozbočovač pro aktuální informace o důležité podrobnosti o tenantovi, dostupnost licencí a použití, stav konektoru a důležité komunikace o službě Intune.  

Chcete-li zobrazit řídicí panel, na Azure portal přejděte do **Intune > Stav Tenanta**.  Stav tenanta se zobrazí v části **Nápověda a podpora skupiny**.  

Na stránce je rozdělen na čtyři oblasti:

## <a name="tenant-details"></a>Podrobnosti o tenantovi
Podrobnosti o tenantovi poskytují informace na přehled o vašem tenantovi. Zobrazit podrobnosti, jako je název vašeho klienta a umístění, vaše autorita MDM a vaše číslo verze služby klientům. Číslo verze služby je odkaz, který se otevře *co je nového v Intune* článku na webu docs Microsoftu, kde najdete informace o nejnovějších funkcích a aktualizací služby Intune.  

Tato část také obsahuje základní informace o dostupných licencí a kolik jsou přiřazené k uživatelům. Licence pro zařízení se nezobrazují.

## <a name="connector-status"></a>Stav konektoru
Stav konektoru je komplexní umístění Kontrola stavu všech dostupných konektorů pro Intune.  

Konektory jsou:
- **Připojení, které nakonfigurujete pro externí služby**. Například *programu Apple Volume Purchase Program* služby nebo *Windows Autopilot* služby.  Stav pro tento typ konektoru je založen na čas poslední úspěšné synchronizace.
- **Certifikáty nebo přihlašovací údaje, které jsou potřebné pro připojení k externím nespravovaná služba**, třeba *Apple Push Notification Services* certifikáty (APNS). Stav pro tento typ konektoru je založená na časové razítko vypršení platnosti certifikátu nebo přihlašovací údaje.  

Ve výchozím nastavení zobrazí se jenom pět konektory. Můžete vybrat **všechny konektory** rozbalte tohoto seznamu zobrazíte všechny dostupné konektory, včetně konektorů, které nebyly nakonfigurovány pro použití.  

Když je více než jeden konektor libovolného typu, je stav souhrn pro všechny tyto stejné konektory. Nejméně v pořádku stav všech jeden konektor slouží jako stav pro skupinu.  

Není v pořádku konektory se vždycky zobrazí v horní části seznamu. Dále jsou konektory spolu s varováními a seznamem konektorů, v pořádku. Zobrazí poslední konektorů, které jste dosud neprovedli konfiguraci.

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

Chcete-li zobrazit informace o Intune zprávy, musí mít váš účet **globálního správce** nebo **Správce služeb** role v Azure Active Directory, nebo přiřadit **Čtenář Centra zpráv**  rolí na portálu správy Office.  Pokud chcete přiřadit toto oprávnění, přihlaste se k [centra pro správu služeb Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) s oprávněními správce. Vyberte **uživatele > aktivní uživatelé**a pak vyberte účet, který vyžaduje přístup. Vyberte **upravit** pro *role*vyberte *týmy komunikace správce*a potom **Uložit** úpravy přiřazení oprávnění.  

Pouze můžete nastavit předvolby komunikace pro Intune příspěvky prostřednictvím centra pro správu Microsoftu 365.
