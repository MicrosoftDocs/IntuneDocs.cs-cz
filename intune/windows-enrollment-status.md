---
title: Nastavení stránky stavu registrace
titleSuffix: Microsoft Intune
description: Pozdravte uživatele, kteří registrují zařízení s Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-an-enrollment-status-page"></a>Nastavení stránky stavu registrace
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Během nastavování zařízení se na stránce stavu registrace zobrazují informace o stavu instalace na zařízení koncového uživatele. Některé aplikace, profily a certifikáty nemusí být v době registrace uživatele plně nainstalovány. Stránka stavu může uživatelům pomoci porozumět stavu jejich zařízení při registraci a po ní. Můžete zapnout stránku pro všechny uživatele, ale také zabránit uživatelům v používání zařízení, dokud se nenainstalují všechny přiřazené aplikace a profily.
 
Stránku stavu registrace zařízení zapnete pro všechny koncové uživatele následujícím postupem.
 
1.  V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Stránka stavu registrace (Preview)**.
2.  V okně **Stránka stavu registrace** zvolte **Výchozí** > **Nastavení**.
3.  U možnosti **Zobrazit průběh instalace aplikací a profilů** zvolte **Ano**.
4.  Zvolte další nastavení, která chcete zapnout, a potom zvolte **Uložit**.
 
## <a name="enrollment-status-page-tracking-information"></a>Informace o sledování na stránce stavu registrace

Stránka stavu sleduje informace o přípravě a nastavení zařízení a nastavení účtu.

### <a name="device-preparation"></a>Příprava zařízení

V případě přípravy zařízení stránka stavu registrace sleduje ověření identit klíčů čipu TPM (Trusted Platform Module) (pokud se používá), postup připojení služby Azure Active Directory a registraci v Intune.

### <a name="device-setup"></a>Nastavení zařízení

U nastavení zařízení stránka stavu registrace sleduje následující položky, pokud jsou přiřazeny ke všem zařízením:
- Zásady zabezpečení
    - Jeden poskytovatel konfiguračních služeb pro všechny registrace.
    - Skuteční poskytovatelé konfiguračních služeb nakonfigurovaných službou Intune se zde nesledují.
- Aplikace
    - Počet obchodních aplikací Instalační služby MSI na jeden počítač.
    - Obchodní aplikace pro Store s kontextem instalace = zařízení.
    - Offline aplikace pro Store a obchodní aplikace pro Store s kontextem instalace = zařízení.
- Profily připojení (VPN a Wi-Fi) se dosud nesledují, a proto bude vždy uveden údaj 0 z 0.
- Certifikáty se dosud nesledují, a proto bude vždy uveden údaj 0 z 0.

### <a name="account-setup"></a>Nastavení účtu
U nastavení účtu stránka stavu registrace sleduje následující položky:
- Zásady zabezpečení
    - Jeden poskytovatel konfiguračních služeb pro všechny registrace.
    - Skuteční poskytovatelé konfiguračních služeb nakonfigurovaných službou Intune se zde nesledují.
- Aplikace
    - Počet obchodních aplikací Instalační služby MSI na jednoho uživatele, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
    - Počet obchodních aplikací Instalační služby MSI na jeden počítač, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
    - Obchodní aplikace pro Store, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je, s kontextem instalace = uživatel.
    - Online aplikace pro Store, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je, s kontextem instalace = uživatel.
    - Offline aplikace pro Store, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je, s kontextem instalace = uživatel.
- Profily připojení
    - Profily VPN a Wi-Fi, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
- Certifikáty
    - Profily certifikátů, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.

## <a name="next-steps"></a>Další kroky
Po nastavení stránek registrace zařízení s Windows se naučte spravovat zařízení s Windows. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](https://docs.microsoft.com/intune/device-management).