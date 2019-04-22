---
title: Nastavení stránky stavu registrace
titleSuffix: Microsoft Intune
description: Nastavte na stránce s pozdravem uživatelé, kteří registrují zařízení s Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d19be73472aed6b6ede1cfdc3d14007c5222c43
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896608"
---
# <a name="set-up-an-enrollment-status-page"></a>Nastavení stránky stavu registrace
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Během nastavování zařízení pomocí Intune stránka stavu registrace se zobrazí informace o instalaci na zařízení. V okamžiku, kdy uživatel dokončí první přihlášení k zařízení po registraci, nemusí být některé aplikace, profily a certifikáty ještě nainstalovány. Stránka stavu registrace může uživatelům pomoci porozumět stavu jejich zařízení při nastavování. Můžete vytvořit více profilů stránky stavu registrace a použít je u různých skupin. Profily můžete nastavit tak, aby:
- Zobrazovaly průběh instalace.
- Blokovaly používání, než se instalace dokončí.
- Určovaly, co může uživatel udělat, pokud se instalace zařízení nezdaří.

Můžete také nastavit pořadí priorit pro každý profil, aby se zohlednily konfliktních přiřazení profilů na stejné zařízení nebo uživatele.

> [!NOTE]
> Stránka stavu registrace se nezobrazí, pokud jen pro zařízení se v přiřazené skupině. Uživatel musí být v přiřazené skupině pro stránka stavu registrace se zobrazí.

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

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Blokovat přístup k zařízení, do konkrétní aplikace je nainstalována.

Můžete určit aplikace, které je potřeba nainstalovat předtím, než uživatel může přístup k ploše.

1. V Intune, zvolte **registrace zařízení** > **registrace Windows** > **stránka stavu registrace (Preview)**.
2. Zvolte profil > **nastavení**.
3. Zvolte **Ano** pro **zobrazit průběh instalace aplikaci a profilu**.
4. Zvolte **Ano** pro **zablokovat používání zařízení, dokud nebudou nainstalovány všechny aplikace a profily**.
5. Zvolte **vybrané** pro **zablokovat používání zařízení, dokud následující požadované aplikace jsou nainstalovány, pokud jsou přiřazeny k uživatele nebo zařízení**.
 6. Zvolte **vyberte aplikace** > vyberte aplikace > **vyberte** > **Uložit**.

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
    - Jeden poskytovatel konfiguračních služeb pro všechny registrace.
    - Skuteční poskytovatelé konfiguračních služeb nakonfigurovaných službou Intune se zde nesledují.
- Aplikace
    - Počet obchodních aplikací Instalační služby MSI na jednoho uživatele, které jsou přiřazeny ke všem zařízením, všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
    - Počet obchodních aplikací Instalační služby MSI na jeden počítač, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
    - Obchodní aplikace pro Store, online aplikace pro Store a offline aplikace pro Store přiřazené jakékoli z následujících možností:
        - Všechna zařízení
        - Všichni uživatelé
        - Skupina uživatelů, ve které je uživatel registrující zařízení členem, s kontextem instalace nastaveným na Uživatel.
- Profily připojení
    - Profily VPN a Wi-Fi, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.
- Certifikáty
    - Profily certifikátů, které jsou přiřazeny ke všem uživatelům nebo skupině uživatelů, jejímž členem uživatel provádějící registraci zařízení je.

## <a name="next-steps"></a>Další postup
Po nastavení stránek registrace zařízení s Windows se naučte spravovat zařízení s Windows. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](https://docs.microsoft.com/intune/device-management).
