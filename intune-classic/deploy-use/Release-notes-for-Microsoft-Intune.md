---
title: "Poznámky k verzi Microsoft Intune | Dokumentace Microsoftu"
description: "Poznámky k verzi Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2c7563ba79819a59740ba81c078c5540d0792ee5
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="release-notes-for-microsoft-intune"></a>Poznámky k verzi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune je integrované cloudové řešení pro správu klientů, které poskytuje nástroje, sestavy a licence k upgradu na nejnovější verzi Windows. Pomáhá také udržovat vaše počítače v aktualizovaném a zabezpečeném stavu. Kromě toho Intune umožňuje spravovat mobilní zařízení v síti, a to buď prostřednictvím protokolu Exchange ActiveSync, nebo přímo přes Intune. Následující poznámky k verzi popisují důležité informace a známé problémy v Microsoft Intune.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>Změna profilů přístupu k prostředkům mezi skupinami pro iOS a Android může selhat
**Problém:** Při změně profilů přístupu k prostředkům e-mailu nebo protokolu SCEP (Simple Certificate Enrollment Protocol) mezi skupinami může dojít ke konfliktu a selhání profilů. Předpokládejme, že máte existující e-mailový profil odkazující na místní server Exchange cílený na skupinu A. Pak vytvoříte nový e-mailový profil odkazující na Exchange Online cílený na skupinu B. Když přesunete uživatele ze skupiny A do skupiny B, zachovají si zařízení e-mailový profil místního serveru Exchange a pokusí se nainstalovat e-mailový profil Exchange Online cílený na skupinu B.

V tu chvíli nastane některá z těchto situací: 
* Pokud jsou e-mailové profily A a B stejné, zařízení e-mailový profil B odmítne, protože e-mailový profil B už obsahuje e-mailový profil A.
* Pokud se e-mailový profil A liší od e-mailového profilu B, jak je uvedeno v příkladu výše, bude mít zařízení dva e-mailové profily.

> [!NOTE]
> K rozlišení jednoho e-mailového profilu od druhého se používá název hostitele a atribut používaný pro uživatelské jméno.

V obou případech nebyl ze zařízení odebrán profil přístupu k prostředkům (e-mailový profil), aby se zabránilo neúmyslnému odebrání přístupu uživatele k e-mailu nebo certifikátu SCEP klienta.

**Alternativní řešení:** Žádné.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Při registraci zařízení s Windows 8.1, které se musí ověřit vůči proxy serveru, proces registrace bez zjevné příčiny selže
**Problém:** Když registrujete zařízení s Windows 8.1, které se musí během procesu registrace ověřit na proxy serveru, tak v případě, že toto zařízení nemá v mezipaměti uložené přihlašovací údaje proxy serveru, registrace selže. Pokud přihlašovací údaje k proxy serveru nejsou uložené v mezipaměti zařízení, musí proces registrace čekat, až tyto přihlašovací údaje uživatel zadá. Výzva k zadání přihlašovacích údajů k proxy serveru se ale během procesu registrace nezobrazí. Ve výsledku se proces registrace nemůže ověřit vůči proxy serveru. Uživateli není na toto selhání nijak upozorněný.

**Alternativní řešení:** U zařízení s Windows 8.1, která se musí registrovat v síti vyžadující použití ověřeného proxy serveru, nastavte a uložte přihlašovací údaje k proxy serveru ještě před registrací zařízení. Nastavení a uložení přihlašovacích údajů na zařízení s Windows 8.1:

1.  Na zařízení s Windows 8.1 otevřete Internet Explorer.
2.  Když se zobrazí výzva k zadání přihlašovacích údajů k proxy serveru, zadejte přihlašovací údaje a pak zvolte možnost **Zapamatovat přihlašovací údaje**.
3.  Registrace zařízení

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>Zařízení se systémem Windows Phone 8.1 nejde zaregistrovat do Microsoft Intune, pokud je ve službě AD FS povolené ověřování zařízení.
**Problém:** Registrace zařízení s Windows Phone 8.1 selže, pokud je volitelné nastavení pro ověřování zařízení povolené v rámci globální zásady ověřování ve službě AD FS (Active Directory Federated Services).

**Alternativní řešení:** Zakažte ověřování zařízení na serveru služby AD FS zrušením zaškrtnutí políčka **Povolit ověřování zařízení** v nastavení **Upravit globální zásady ověřování**. Další informace najdete v tématu [Konfigurace zásad ověřování](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>Nástroj Microsoft Intune App Wrapping Tool pro Android nemá žádnou integrovanou možnost odinstalace.
**Problém**: Nástroj **Microsoft App Wrapping Tool pro Android** nemá vestavěnou funkci odinstalace.

**Alternativní řešení:** Přejděte do umístění, kam jste nástroj nainstalovali, a adresář odstraňte. Výchozí umístění instalace: **C:\Program Files /intune-classic/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Vzdálená pomoc není dostupná na počítačích se systémem Windows 8 nebo Windows 8.1.
**Problém:** V této verzi není na počítačích se systémem Windows 8 nebo Windows 8.1 dostupná funkce Vzdálená pomoc.

**Alternativní řešení:** Žádné.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Oznámení výstrah pro příjemce, kteří jsou přidaní automaticky, nemusí fungovat
**Problém:** Pokud jsou příjemci k oznámení výstrah přidaní automaticky, nemusí oznámení vždycky dostat.

**Alternativní řešení:** Pokud chcete mít jistotu, že příjemci dostanou oznámení, měli byste tyto příjemce k oznámením výstrah přidat ručně.

## <a name="language-support-in-the-azure-portal"></a>Podpora jazyků na webu Azure Portal
Azure Portal podporuje tyto jazyky: čínština (zjednodušená), čínština (tradiční), čeština, holandština, angličtina, němčina, maďarština, italština, japonština, portugalština (Brazílie), portugalština (Portugalsko), ruština, španělština, angličtina, francouzština, korejština, polština, švédština, turečtina.

Konzola pro správu Intune a mobilní prostředí pro uživatele podporují kromě všech jazyků podporovaných webem Azure Portal také dánštinu, řečtinu, finštinu, norštinu a rumunštinu.

