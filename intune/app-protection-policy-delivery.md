---
title: Doručování zásad ochrany aplikací Undertastand a časování
titleSuffix: Microsoft Intune
description: Přečtěte si jiné nasazení systému windows pro zásady ochrany aplikací pochopit, když by se měla zobrazit změny na vašich zařízeních koncových uživatelů.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef83366b54ef92bb6fb4fe5cea87838d371c1677
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043854"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Vysvětlení zásad ochrany aplikací doručování časování

Přečtěte si jiné nasazení systému windows pro zásady ochrany aplikací, abyste pochopili, když změny by se měla zobrazit na zařízeních koncových uživatelů.

## <a name="delivery-timing-summary"></a>Souhrn časování doručování

Doručování zásad ochrany aplikací závisí na stavu licence a registrace služby Intune pro vaše uživatele.  

|    Stav uživatele    |    Chování ochrany aplikace     |    Interval opakování (viz poznámky)    |    Proč k tomu dochází?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Tenant Nezprovoznilo.    |    Vyčkat, než intervalu příštího opakování.  Ochrana aplikací není aktivní uživatele.    |    24 hodin    |    Nastane, pokud jste nenastavili vašeho tenanta Intune.    |
|    Není licencovaný uživatel     |    Vyčkat, než intervalu příštího opakování.  Ochrana aplikací není aktivní uživatele.     |    12 hodin – ale na zařízeních s Androidem tento interval vyžaduje sadu Intune APP SDK verze 5.6.0 nebo novější. Jinak zařízení Andriod. interval je 24 hodin.   |    Nastane, pokud uživatel ještě licenci pro Intune.    |
|    Uživatel není přiřazený zásady ochrany aplikací    |    Vyčkat, než intervalu příštího opakování.  Ochrana aplikací není aktivní uživatele.    |    12 hodin        |    Nastane, pokud jste ještě nepřiřadili nastavení aplikace uživatele.    |
|    Uživatel úspěšně zaregistrovaný v Intune mam    |    Podle nastavení zásad se použije ochrana aplikací.    Aktualizace se provádí na základě na interval opakování    |    Služba Intune definovány v závislosti na zatížení uživatele.    Obvykle 30 minut.     |    Nastane, pokud uživatel úspěšně zaregistrovala ve službě Intune MAM konfigurace.    |

> [!NOTE]
> Může vyžadovat využití aplikací, které aktivní pravděpodobnější, což znamená, že je aplikace spuštěná a používají se intervaly opakování.  Pokud interval opakování je 24 hodin a uživatel čeká 48 hodin aplikaci spustit, bude opakovat akci ochrany aplikace klient 48 hodin.

## <a name="handling-network-connectivity-issues"></a>Zpracování problémy se síťovým připojením

Pokud se registrace uživatele nezdaří kvůli problémům se síťovým připojením interval akcelerované opakování se používá.  Ochranu aplikací bude klient opakovat pokus intervalech stále déle, dokud nedosáhne interval 60 minut nebo vytvoří úspěšné připojení.  Klient pak bude opakovat každých 60 minut, dokud vytvoří úspěšné připojení. Klient pak vrátí interval standardní opakování na základě stavu uživatele.

## <a name="next-steps"></a>Další postup

[Přiřazení licencí uživatelům, aby mohli zaregistrovat zařízení v Intune](licenses-assign.md)

