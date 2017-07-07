---
title: "Nastavení e-mailu pro Windows Phone 8.1 v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s Windows Phone 8.1."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4925ceb1be344a12270ee40519096a62b1f0c739
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Nastavení e-mailového profilu pro Windows Phone 8.1 v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


- **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba **user1@contoso.com**, nebo **Hlavní název uživatele**, třeba **uživatel1** nebo **user1@contoso.com**.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.


## <a name="security-settings"></a>Nastavení zabezpečení

- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).



## <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace** – Vyberte plán, podle kterého budou zařízení synchronizovat data z Exchange serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala hned po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

## <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci** – Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
    - **Kontakty**
    - **Kalendář**
    - **Úkoly**
