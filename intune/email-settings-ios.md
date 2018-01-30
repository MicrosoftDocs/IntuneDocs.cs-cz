---
title: "Nastavení e-mailu pro zařízení s iOSem v Intune"
titleSuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete nakonfigurovat připojení e-mailu na zařízeních s iOSem."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7baec2990b9020e8125395b589fba7a965ba86ee
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení e-mailového profilu pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba **user1@contoso.com**, nebo **Hlavní název uživatele**, třeba **uživatel1** nebo **user1@contoso.com**.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME** – Odchozí e-maily se budou posílat s podpisovým certifikátem S/MIME.
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesunování zpráv na jiné e-mailové účty** – Tato možnost povolí uživatelům přesunovat e-mailové zprávy mezi různými účty, které si na svých zařízeních nakonfigurovali.
- **Umožnit posílání e-mailů z aplikací třetích stran** – Můžete povolit uživateli, aby tento profil vybral jako výchozí účet pro posílání e-mailů, a povolit aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například k připojování souborů k e-mailům.
- **Synchronizovat naposledy použité e-mailové adresy** – Tato funkce povolí uživatelům synchronizovat se serverem seznam e-mailových adres, které se na zařízení naposledy používaly.
