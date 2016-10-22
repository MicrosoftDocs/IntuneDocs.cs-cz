---
title: "Poznámky k verzi Microsoft Intune | Microsoft Intune"
description: "Poznámky k verzi Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f1147e5fe766bc4642439c4ad23b2fdfbf74bb03
ms.openlocfilehash: da476088435d6ef8bd58ecad1b221254a30858cc


---

# Poznámky k verzi Microsoft Intune
Microsoft Intune je integrované cloudové řešení pro správu klientů, které poskytuje nástroje, sestavy a licence k upgradu na nejnovější verzi Windows. Pomáhá také udržovat vaše počítače v aktualizovaném a zabezpečeném stavu. Kromě toho Intune umožňuje spravovat mobilní zařízení v síti, a to buď prostřednictvím protokolu Exchange ActiveSync, nebo přímo přes Intune. Následující poznámky k verzi popisují důležité informace a známé problémy v Microsoft Intune.


## Po implementaci podmíněného přístupu pro Exchange Online nemůžou uživatelé systému Android odesílat e-maily

**Problém:** Uživatelé, kteří na svých zařízeních používají Samsung Android 5.1.1 a novější, nemůžou odesílat e-maily, pokud je nastavený podmíněný přístup pro Exchange Online. Samsung potvrzuje, že tento problém je v integrovaném e-mailovém klientovi v Androidu 5.1.1 a novějším, a pracuje na opravě.

**Alternativní řešení 1:** Poraďte uživatelům, aby používali aplikaci Outlook pro Android.

**Alternativní řešení 2:** Následujícím postupem umožněte dotčeným uživatelům odesílat e-maily:

1. Dejte každého dotčeného uživatele do skupiny zabezpečení v sekci „Vyloučené skupiny“ v zásadě podmíněného přístupu pro Exchange Online.
2. Umožněte uživateli dočasnou synchronizaci e-mailu v integrovaném e-mailovém klientovi.
3. Odeberte dotčeného uživatele z vyloučené skupiny a ověřte si, že teď může odesílat e-maily.

Microsoft bude se společností Samsung dál úzce spolupracovat na opravě nebo dalších alternativních řešeních.



## Změna profilů přístupu k prostředkům mezi skupinami pro iOS a Android může selhat
**Problém:** Při změně profilů přístupu k prostředkům e-mailu nebo protokolu SCEP (Simple Certificate Enrollment Protocol) mezi skupinami může dojít ke konfliktu a selhání profilů. Předpokládejme, že máte existující e-mailový profil odkazující na místní server Exchange cílený na skupinu A. Pak vytvoříte nový e-mailový profil odkazující na Exchange Online cílený na skupinu B. Když přesunete uživatele ze skupiny A do skupiny B, zachovají si zařízení e-mailový profil místního serveru Exchange a pokusí se nainstalovat e-mailový profil Exchange Online cílený na skupinu B.

V tu chvíli nastane některá z těchto situací: 
* Pokud jsou e-mailové profily A a B stejné, zařízení e-mailový profil B odmítne, protože e-mailový profil B už obsahuje e-mailový profil A.
* Pokud se e-mailový profil A liší od e-mailového profilu B, jak je uvedeno v příkladu výše, bude mít zařízení dva e-mailové profily.

> [!NOTE]
> K rozlišení jednoho e-mailového profilu od druhého se používá název hostitele a atribut používaný pro uživatelské jméno.

V obou případech nebyl ze zařízení odebrán profil přístupu k prostředkům (e-mailový profil), aby se zabránilo neúmyslnému odebrání přístupu uživatele k e-mailu nebo certifikátu SCEP klienta.

**Alternativní řešení:** Žádné.

## Při registraci zařízení s Windows 8.1, které se musí ověřit vůči proxy serveru, proces registrace bez zjevné příčiny selže
**Problém:** Když registrujete zařízení s Windows 8.1, které se musí během procesu registrace ověřit na proxy serveru, tak v případě, že toto zařízení nemá v mezipaměti uložené přihlašovací údaje proxy serveru, registrace selže. Pokud přihlašovací údaje k proxy serveru nejsou uložené v mezipaměti zařízení, musí proces registrace čekat, až tyto přihlašovací údaje uživatel zadá. Výzva k zadání přihlašovacích údajů k proxy serveru se ale během procesu registrace nezobrazí. Ve výsledku se proces registrace nemůže ověřit vůči proxy serveru. Uživateli není na toto selhání nijak upozorněný.

**Alternativní řešení:** U zařízení s Windows 8.1, která se musí registrovat v síti vyžadující použití ověřeného proxy serveru, nastavte a uložte přihlašovací údaje k proxy serveru ještě před registrací zařízení. Nastavení a uložení přihlašovacích údajů na zařízení s Windows 8.1:

1.  Na zařízení s Windows 8.1 otevřete Internet Explorer.
2.  Když se zobrazí výzva k zadání přihlašovacích údajů k proxy serveru, zadejte přihlašovací údaje a pak zvolte možnost **Zapamatovat přihlašovací údaje**.
3.  Registrace zařízení

## Zařízení se systémem Windows Phone 8.1 nejde zaregistrovat do Microsoft Intune, pokud je ve službě AD FS povolené ověřování zařízení.
**Problém:** Registrace zařízení s Windows Phone 8.1 selže, pokud je volitelné nastavení pro ověřování zařízení povolené v rámci globální zásady ověřování ve službě AD FS (Active Directory Federated Services).

**Alternativní řešení:** Zakažte ověřování zařízení na serveru služby AD FS zrušením zaškrtnutí políčka **Povolit ověřování zařízení** v nastavení **Upravit globální zásady ověřování**. Další informace najdete v tématu [Konfigurace zásad ověřování](http://technet.microsoft.com/library/dn486781.aspx).


## Nástroj Microsoft Intune App Wrapping Tool pro Android nemá žádnou integrovanou možnost odinstalace.
**Problém**: Nástroj **Microsoft App Wrapping Tool pro Android** nemá vestavěnou funkci odinstalace.

**Alternativní řešení:** Přejděte do umístění, kam jste nástroj nainstalovali, a adresář odstraňte. Výchozí instalační umístění: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Další informace o nástroji App Wrapping Tool najdete v tématu [Příprava správy aplikací pro Android pomocí nástroje App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## Vzdálená pomoc není dostupná na počítačích se systémem Windows 8 nebo Windows 8.1.
**Problém:** V této verzi není na počítačích se systémem Windows 8 nebo Windows 8.1 dostupná funkce Vzdálená pomoc.

**Alternativní řešení:** Žádné.

## Oznámení výstrah pro příjemce, kteří jsou přidaní automaticky, nemusí fungovat
**Problém:** Pokud jsou příjemci k oznámení výstrah přidaní automaticky, nemusí oznámení vždycky dostat.

**Alternativní řešení:** Pokud chcete mít jistotu, že příjemci dostanou oznámení, měli byste tyto příjemce k oznámením výstrah přidat ručně.

## Podpora jazyků na webu Azure Portal
Azure Portal podporuje tyto jazyky: čínština (zjednodušená), čínština (tradiční), čeština, holandština, angličtina, němčina, maďarština, italština, japonština, portugalština (Brazílie), portugalština (Portugalsko), ruština, španělština, angličtina, francouzština, korejština, polština, švédština, turečtina.

Konzola pro správu Intune a mobilní prostředí pro uživatele podporují kromě všech jazyků podporovaných webem Azure Portal také dánštinu, řečtinu, finštinu, norštinu a rumunštinu.



<!--HONumber=Oct16_HO2-->


