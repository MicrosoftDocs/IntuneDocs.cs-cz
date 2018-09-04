---
title: Nasazení aplikací pro Windows 10 pomocí Intune
titlesuffix: ''
description: Získejte další informace o dostupných scénářích týkajících se aplikací pro Windows 10 v Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7508f2c2eca06ceacf203103ab2cad53abc39a65
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347428"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Nasazení aplikací pro Windows 10 pomocí Intune 

Microsoft Intune aktuálně na zařízeních s Windows 10 podporuje různé typy aplikací a scénářů nasazení. Po přidání aplikace do Intune ji můžete přiřadit uživatelům a zařízením. Následující informace poskytují další podrobnosti týkající se podporovaných scénářů pro Windows 10. Kromě toho také poskytují klíčové podrobnosti, které byste při nasazování aplikací do systému Windows neměli opomenout. 

Obchodní aplikace (LOB) a aplikace pro Microsoft Store pro firmy jsou na zařízeních s Windows 10 podporované.

> [!Note]
> Minimální potřebnou aktualizací Windows 10 pro nasazování aplikací v kontextu zařízení je [KB4100403 z 23. května 2018 (Číslo sestavení operačního systému 17134.81)](https://support.microsoft.com/en-us/help/4100403/windows-10-update-kb4100403).

## <a name="windows-10-line-of-business-apps"></a>Obchodní aplikace pro Windows 10

Obchodní aplikace pro Windows 10 jsou podepsané a nahrané v konzole správce Intune a mohou obsahovat jak moderní aplikace, jako jsou aplikace Univerzální platformy Windows (UWP) a balíčky aplikace systému Windows (AppX), tak i aplikace Win 32, jako jsou jednoduché soubory balíčku Microsoft Installer (MSI). Aktualizace obchodních aplikací se musí pokaždé ručně nahrát a nasadit správcem. Nasazené aktualizace se automaticky bez zásahu uživatele nainstalují na zařízení koncových uživatelů, kteří mají aplikaci nainstalovanou. Uživatel nemá nad aktualizacemi žádnou kontrolu. 

## <a name="microsoft-store-for-business-apps"></a>Aplikace pro Microsoft Store pro firmy

Aplikace pro Microsoft Store pro firmy jsou moderními aplikacemi, které můžete zakoupit na portálu pro správu Microsoft Storu pro firmy a které se potom synchronizují do Microsoft Intune pro správu. Tyto aplikace mohou mít **online licenci** nebo **offline licenci**. Aktualizace aplikací z Microsoft Storu pro firmy se spravují přímo v Microsoft Storu bez nutnosti zásahu správcem. Správce může použitím vlastního identifikátoru URI (Uniform Resource Identifier) zabránit aktualizacím konkrétních aplikací. Další informace najdete v tématu o [správě podnikových aplikací a zabránění jejich automatické aktualizace](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Koncový uživatel může na svém zařízení automatické aktualizace aplikací z Microsoft Storu pro firmy také zakázat. 

## <a name="installing-apps-on-windows-10-devices"></a>Instalace aplikací na zařízeních s Windows 10
V závislosti na typu aplikace můžete aplikace na zařízení s Windows 10 instalovat jedním ze dvou způsobů:

- **Kontext uživatele**: když se aplikace nasadí v kontextu uživatele, spravovaná aplikace se nainstaluje konkrétnímu uživateli na zařízení, jakmile se k němu přihlásí. Instalace aplikace úspěšné neproběhne, dokud se uživatel k zařízení nepřihlásí. 
    - V kontextu uživatele je možné nasadit moderní obchodní aplikace a aplikace pro Microsoft Store pro firmy (online i offline) s podporou záměru Povinné i K dispozici.
- **Kontext zařízení**: když se aplikace nasadí v kontextu zařízení, spravovaná aplikace se pomocí Intune nainstaluje do zařízení přímo.
    - V kontextu zařízení je možné nasadit jen moderní obchodní aplikace a online licencované aplikace pro Microsoft Store pro firmy s podporou pouze záměru Povinné.

> [!Note]
> Nasazení MSI prostřednictvím správy mobilních zařízení ještě není na zařízeních s Windows 10 podporované.

Když se aplikace nasadí v kontextu zařízení, instalace proběhne úspěšně pouze v případě, že zařízení kontext zařízení podporuje. Kromě toho nasazení v kontextu zařízení obsahuje následující podmínky:
- Pokud se aplikace nasadí v kontextu zařízení a cílí na uživatele, instalace se nezdaří a v konzole pro správu se zobrazí následující stav a chyba:
    - Stav: Neúspěšné.
    - Chyba: Instalace v kontextu zařízení nemůže cílit na uživatele.
- Pokud se aplikace nasadí v kontextu zařízení a cílí na zařízení, které kontext zařízení nepodporuje, instalace se nezdaří a v konzole pro správu se zobrazí následující stav a chyba:
    - Stav: Neúspěšné.
    - Chyba: Tato platforma nepodporuje instalaci v kontextu zařízení. 

> [!Note]
> Jakmile se přiřazení aplikace uloží pod konkrétním nasazením, není možné u daného přiřazení kontext změnit (s výjimkou moderních aplikací). V případě moderních aplikací můžete kontext změnit z kontextu uživatele na kontext zařízení. 

V případě, že u jednoho uživatele nebo zařízení dojde ke konfliktu mezi zásadami, určí se konečná zásada podle následujících priorit:
- Zásady kontextu zařízení mají vyšší prioritu než zásady kontextu uživatele. 
- Zásady instalace mají vyšší prioritu než zásady odinstalace.

Další informace o přiřazování aplikací pomocí Microsoft Intune najdete v tématech [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md) a [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md). Další informace o typech aplikací v Intune najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Další kroky

- Další informace o přiřazení aplikací ke skupinám najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).
- Další informace o sledování přiřazení aplikací najdete v článku o [monitorování aplikací](apps-monitor.md).
