---
title: "Nastavení e-mailu v Intune pro zařízení s Androidem | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 29a4346a04470192553ad2d4f0962a2a21d637ec
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-android-devices-in-microsoft-intune"></a>Nastavení e-mailového profilu pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba user1@contoso.com, nebo **Hlavní název uživatele**, třeba uživatel1 nebo user1@contoso.com.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.

## <a name="security-settings"></a>Nastavení zabezpečení

- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME** – Odchozí e-maily se budou posílat s využitím šifrování S/MIME.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.

## <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace** – Vyberte plán, podle kterého budou zařízení synchronizovat data z Exchange serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala hned po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

## <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci** – Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
    - **Kontakty**
    - **Kalendář**
    - **Úkoly**
