---
title: Nastavení stránky stavu registrace
titleSuffix: Microsoft Intune
description: Pozdravte uživatele, kteří registrují zařízení s Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08d76d6b76ee7838633435ae095c171e0a3cdf8e
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236488"
---
# <a name="set-up-an-enrollment-status-page"></a>Nastavení stránky stavu registrace
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Během nastavování zařízení se na stránce stavu registrace zobrazují informace o instalaci na zařízení. V okamžiku, kdy uživatel dokončí první přihlášení k zařízení po registraci, nemusí být některé aplikace, profily a certifikáty ještě nainstalovány. Stránka stavu registrace může uživatelům pomoci porozumět stavu jejich zařízení při nastavování. Můžete vytvořit více profilů stránky stavu registrace a použít je u různých skupin. Profily můžete nastavit tak, aby:
- Zobrazovaly průběh instalace.
- Blokovaly používání, než se instalace dokončí.
- Určovaly, co může uživatel udělat, pokud se instalace zařízení nezdaří.

Můžete také nastavit pořadí jednotlivých profilů podle priority, abyste ošetřili konfliktní přiřazení profilů stejného uživatele nebo zařízení.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Zapnutí výchozí stránky stavu registrace pro všechny uživatele

Pokud chcete zapnout stránku stavu registrace, postupujte podle následujících kroků.
 
1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Stránka stavu registrace (Preview)**.
2. V okně **Stránka stavu registrace** zvolte **Výchozí** > **Nastavení**.
3. U možnosti **Zobrazit průběh instalace aplikací a profilů** zvolte **Ano**.
4. Zvolte další nastavení, která chcete zapnout, a potom zvolte **Uložit**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Vytvoření profilu stránky stavu registrace a jeho přiřazení skupině

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Stránka stavu registrace (Preview)** > **Vytvořit profil**.
2. Zadejte **Název** a **Popis**.
3. Zvolte **Vytvořit**.
4. Nový profil vyberte v seznamu **Stránka stavu registrace**.
5. Vyberte **Přiřazení** > **Vybrat skupiny** > vyberte skupiny, které mají tento profil používat > **Vybrat** > **Uložit**.
6. Vyberte **Nastavení** > vyberte nastavení, která chcete pro tento profil použít > **Uložit**.

## <a name="set-the-enrollment-status-page-priority"></a>Nastavení priority stránky stavu registrace

Zařízení nebo uživatel mohou být členy více skupin a mohou mít více profilů stránky stavu registrace. Pro každý profil můžete nastavit prioritu, abyste konfliktům tohoto typu předešli. Pokud má někdo více profilů stránky stavu registrace, použije se pouze profil s nejvyšší prioritou.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Stránka stavu registrace (Preview)**.
2. Najeďte myší na profil v seznamu.
3. Pomocí tří svislých teček přetáhněte profil na požadované místo v seznamu.


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
- Profily připojení
    - Profily VPN nebo Wi-Fi přiřazené ke skupině **Všechna zařízení** nebo ke skupině zařízení, jejímž členem je zařízení, které se registruje. Platí pouze pro zařízení Autopilot.
- Profily certifikátů přiřazené ke skupině **Všechna zařízení** nebo ke skupině zařízení, jejímž členem je zařízení, které se registruje. Platí pouze pro zařízení Autopilot.

### <a name="account-setup"></a>Nastavení účtu
U nastavení účtu stránka stavu registrace sleduje následující položky:
- Zásady zabezpečení
    - Jeden poskytovatel konfiguračních služeb pro všechny registrace
    - Skuteční poskytovatelé konfiguračních služeb nakonfigurovaných službou Intune se zde nesledují.
- Aplikace
    - Počet obchodních aplikací Instalační služby MSI na jednoho uživatele, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je
    - Počet obchodních aplikací Instalační služby MSI na jeden počítač, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je
    - Obchodní aplikace pro Store, online aplikace pro Store a offline aplikace pro Store přiřazené jakékoli z následujících možností:
        - Všechna zařízení
        - Všichni uživatelé
        - Skupina uživatelů, ve které je uživatel registrující zařízení členem, s kontextem instalace nastaveným na Uživatel
- Profily připojení
    - Profily VPN a Wi-Fi, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je
- Certifikáty
    - Profily certifikátů, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je

## <a name="next-steps"></a>Další kroky
Po nastavení stránek registrace zařízení s Windows se naučte spravovat zařízení s Windows. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](https://docs.microsoft.com/intune/device-management).
