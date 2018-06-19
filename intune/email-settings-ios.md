---
title: Nastavení e-mailu pro zařízení s iOSem v Microsoft Intune
titleSuffix: ''
description: Přečtěte si informace o nastaveních Microsoft Intune, která můžete použít ke konfiguraci nastavení e-mailu na zařízeních s iOSem.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe791dce88878fdbde7c62e59452a53ac08ef06b
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190481"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>Nastavení e-mailového profilu v Microsoft Intune pro zařízení s iOSem 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení e-mailového profilu, které můžete konfigurovat pro zařízení se systémem iOS.

## <a name="email-settings"></a>Nastavení e-mailu

- **E-mailový server** – Název hostitele vašeho Exchange serveru.
- **Název účtu** – Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.
- **Atribut uživatelského jména z AAD** – Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba **user1@contoso.com**, nebo **Hlavní název uživatele**, třeba **uživatel1** nebo **user1@contoso.com**.
- **Atribut e-mailové adresy z AAD** – Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**. Pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování** – Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty** (**Poznámka**: vícefaktorové ověřování není podporováno).
    - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL** – Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME** – Odchozí e-maily se budou posílat s podpisovým certifikátem S/MIME.
    - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu PKCS, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **Počet e-mailů k synchronizaci** – Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesunování zpráv na jiné e-mailové účty** – Tato možnost povolí uživatelům přesunovat e-mailové zprávy mezi různými účty, které si na svých zařízeních nakonfigurovali.
- **Umožnit posílání e-mailů z aplikací třetích stran** – Můžete povolit uživateli, aby tento profil vybral jako výchozí účet pro posílání e-mailů, a povolit aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například k připojování souborů k e-mailům.
- **Synchronizovat naposledy použité e-mailové adresy** – Tato funkce povolí uživatelům synchronizovat se serverem seznam e-mailových adres, které se na zařízení naposledy používaly.
