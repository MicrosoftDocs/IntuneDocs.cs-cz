---
title: "Nastavení e-mailu pro Windows Phone 8.1 v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
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
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c656f46c9dd19ffbefb499220c102c3471ff9c56
ms.lasthandoff: 02/18/2017


---

# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Nastavení e-mailového profilu pro Windows Phone 8.1 v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


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

