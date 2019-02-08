---
title: Nastavení e-mailu pro Windows Phone 8.1 v Microsoft Intune
titleSuffix: ''
description: Přečtěte si o nastaveních Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1622595814d2ccdb180b7167d973d283781615bb
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841279"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-windows-phone-81"></a>Nastavení e-mailového profilu v Microsoft Intune pro zařízení s Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení e-mailového profilu, která můžete konfigurovat pro zařízení s Windows Phone 8.1.


- **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na klasickém portálu Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba **user1@contoso.com**, nebo **Hlavní název uživatele**, třeba **uživatel1** nebo **user1@contoso.com**.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.


## <a name="security-settings"></a>Nastavení zabezpečení

- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).



## <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace** – Vyberte plán, podle kterého zařízení synchronizují data z Exchange Serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala hned po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

## <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci** – Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
    - **Kontakty**
    - **Kalendář**
    - **Úkoly**
