---
title: "Nastavení e-mailu v Intune pro zařízení s iOSem | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 186630903a606842406ff1d76115c1fa7d1c962e
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení e-mailového profilu pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba **user1@contoso.com**, nebo **Hlavní název uživatele**, třeba **uživatel1** nebo **user1@contoso.com**.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME** – Odchozí e-maily se budou posílat s využitím šifrování S/MIME.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesunování zpráv na jiné e-mailové účty** – Tato možnost povolí uživatelům přesunovat e-mailové zprávy mezi různými účty, které si na svých zařízeních nakonfigurovali.
- **Umožnit posílání e-mailů z aplikací třetích stran** – Můžete povolit uživateli, aby tento profil vybral jako výchozí účet pro posílání e-mailů, a povolit aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například k připojování souborů k e-mailům.
- **Synchronizovat naposledy použité e-mailové adresy** – Tato funkce povolí uživatelům synchronizovat se serverem seznam e-mailových adres, které se na zařízení naposledy používaly.

