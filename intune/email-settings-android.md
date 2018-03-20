---
title: "Nastavení e-mailu v Microsoft Intune pro zařízení s Androidem a s Androidem for Work"
titleSuffix: 
description: "Přečtěte si informace o nastaveních Microsoft Intune, která můžete použít ke konfiguraci nastavení e-mailu na zařízeních se systémem Android a Android for Work."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f989f9fafa4766ab71843c9dddef2bf3e18c5134
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Nastavení e-mailového profilu v Microsoft Intune pro zařízení s Androidem a Androidem for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení e-mailového profilu, které můžete konfigurovat pro zařízení s Androidem.

Jako správce Intune můžete vytvořit a přiřadit nastavení e-mailu pro následující zařízení s Androidem:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Nastavení e-mailu pro Android Samsung Knox Standard
- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Tento název je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba user1@contoso.com, nebo **Hlavní název uživatele**, třeba uživatel1 nebo user1@contoso.com.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
    - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="security-settings"></a>Nastavení zabezpečení

- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME** – Odchozí e-maily se budou posílat s využitím šifrování S/MIME.
    - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace** – Vyberte plán, podle kterého zařízení synchronizují data z Exchange Serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

### <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci** – Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
    - **Kontakty**
    - **Kalendář**
    - **Úkoly**

## <a name="android-for-work-email-settings"></a>Nastavení e-mailu pro Android for Work

- **E-mailová aplikace** – Vyberte **Gmail** nebo **Nine Work**.
- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Atribut uživatelského jména z AAD** – Tento název je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba user1@contoso.com, nebo **Hlavní název uživatele**, třeba uživatel1 nebo user1@contoso.com.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete jako e-mailovou adresu nebo **uživatelské jméno** používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
    - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Typ obsahu k synchronizaci** (jenom Nine Work) – Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
    - **Kontakty**
    - **Kalendář**
    - **Úkoly**
