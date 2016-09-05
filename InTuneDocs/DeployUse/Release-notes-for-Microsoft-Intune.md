---
title: "Poznámky k verzi Microsoft Intune | Microsoft Intune"
description: "Poznámky k verzi Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: d4961042d3fbd1d6467fa784db5adef6ed5f7f1f


---

# Poznámky k verzi Microsoft Intune
Microsoft Intune je integrované cloudové řešení pro správu klienta, které poskytuje nástroje, sestavy a licence na upgrade na nejnovější verzi Windows a pomáhá udržovat počítač aktualizovaný a zabezpečený. Kromě toho Intune umožňuje spravovat mobilní zařízení v síti, a to buď prostřednictvím protokolu Exchange ActiveSync, nebo přímo přes Intune. Následující poznámky k verzi popisují důležité informace a známé problémy v Microsoft Intune.


## Po implementaci podmíněného přístupu pro Exchange Online nemůžou uživatelé systému Android odesílat e-maily

Uživatelé, kteří na svých zařízeních používají systém Samsung Android 5.1.1 a vyšší, nemůžou po konfiguraci podmíněného přístupu pro Exchange Online odesílat e-maily. Společnost Samsung přiznává, že se jedná o problém v jejím e-mailovém klientovi integrovaném v systému Android 5.1.1 a vyšším, a v současné době hledá opravu.

**Alternativní řešení 1:** Poraďte koncovým uživatelům, aby používali aplikaci Outlook pro Android.

**Alternativní řešení 2:** Pokud chcete dotyčným uživatelům umožnit odesílat e-maily, můžete provést následující kroky:

1. Umístěte dotyčného uživatele do skupiny zabezpečení v části „Vyloučené skupiny“ v zásadách podmíněného přístupu pro Exchange Online.
2. Povolte uživateli dočasnou synchronizaci e-mailu v integrovaném e-mailovém klientovi.
3. Odeberte dotyčného uživatele z vyloučené skupiny a ověřte si, že teď uživatel může odesílat e-maily.

Microsoft bude se společností Samsung dál úzce spolupracovat na opravě nebo dalších alternativních řešeních.



## Nemusí se podařit změna profilů přístupu k prostředkům mezi skupinami pro iOS a Android
**Problém:** Při změně profilů přístupu k prostředkům e-mailu nebo protokolu SCEP (Simple Certificate Enrollment Protocol) mezi skupinami může dojít ke konfliktu a selhání profilů. Budeme třeba předpokládat, že máte existující e-mailový profil odkazující na místní server Exchange cílený na skupinu A a potom vytvoříte nový e-mailový profil odkazující na Exchange Online cílený na skupinu B. Když přesunete uživatele ze skupiny A do skupiny B, zařízení si zachovají e-mailový profil místního serveru Exchange a pokusí se nainstalovat e-mailový profil Exchange Online cílený na skupinu B.

V tu chvíli nastane některá z těchto situací: 
* Pokud jsou e-mailové profily A a B stejné, zařízení e-mailový profil B odmítne, protože e-mailový profil B už obsahuje e-mailový profil A.
* Pokud se e-mailový profil A liší od e-mailového profilu B, jak je uvedeno v příkladu výše, zařízení bude mít dva e-mailové profily.

**Poznámka:** Při rozlišování jednoho e-mailového profilu od druhého se kontroluje název hostitele a atribut používaný pro uživatelské jméno.

V obou výše popsaných případech nedošlo k odebrání profilu přístupu k prostředkům (e-mailového profilu) ze zařízení, aby se zabránilo neúmyslnému odebrání přístupu uživatele k e-mailu nebo certifikátu SCEP klienta.

**Alternativní řešení:** Žádné.

## Při registraci zařízení se systémem Windows 8.1, které se musí ověřit na proxy serveru, proces registrace selže, aniž by se ukázala jakákoli příčina selhání.
**Problém:** Když registrujete zařízení s Windows 8.1, které se musí během procesu registrace ověřit na proxy serveru, tak v případě, že toto zařízení nemá v mezipaměti uložené přihlašovací údaje proxy serveru, registrace selže. Pokud přihlašovací údaje k proxy serveru nejsou uložené v mezipaměti zařízení, musí proces registrace čekat, až tyto přihlašovací údaje uživatel zadá. Výzva k zadání přihlašovacích údajů k proxy serveru se ale během procesu registrace nezobrazí. Výsledkem je, že proces registrace nemůže ověřit proxy server, ale uživateli se žádná informace o tomto selhání nezobrazí.

**Alternativní řešení:** U zařízení s Windows 8.1, která se musí registrovat v síti vyžadující použití ověřeného proxy serveru, nakonfigurujte a uložte přihlašovací údaje k proxy serveru ještě před jejich registrací. Konfigurace a uložení přihlašovacích údajů na zařízení s Windows 8.1:

1.  Na zařízení s Windows 8.1 otevřete **Internet Explorer**.

2.  Když se zobrazí výzva k zadání přihlašovacích údajů k proxy serveru, zadejte přihlašovací údaje a potom vyberte možnost **Zapamatovat pověření**.

3.  Registrace zařízení

## Zařízení se systémem Windows Phone 8.1 nejde zaregistrovat do Microsoft Intune, pokud je ve službě AD FS povolené ověřování zařízení.
**Problém:** Při registraci zařízení Windows Phone 8.1 registrace selže, pokud je povolené volitelné nastavení pro ověřování zařízení v rámci globální zásady ověřování ve službě Active Directory Federated Services (AD FS).

**Alternativní řešení:** Zakažte ověřování zařízení na serveru služby AD FS zrušením zaškrtnutí políčka **Povolit ověřování zařízení** v nastavení **Upravit globální zásady ověřování**. Další informace najdete v tématu [Konfigurace zásad ověřování](http://technet.microsoft.com/library/dn486781.aspx).


## Nástroj Microsoft Intune App Wrapping Tool pro Android nemá žádnou integrovanou možnost odinstalace.
**Problém**: Nástroj **Microsoft App Wrapping Tool pro Android** nemá vestavěnou funkci odinstalace.

**Alternativní řešení:** Přejděte do umístění, kam jste nástroj nainstalovali, a adresář odstraňte. Výchozí instalační umístění: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Další informace o nástroji App Wrapping Tool najdete v tématu [Příprava aplikací pro Android na správu mobilních aplikací nástrojem App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## Vzdálená pomoc není dostupná na počítačích se systémem Windows 8 nebo Windows 8.1.
**Problém:** V této verzi není na počítačích se systémem Windows 8 nebo Windows 8.1 dostupná funkce Vzdálená pomoc.

**Alternativní řešení:** Žádné.

## Oznámení výstrah pro příjemce, kteří jsou přidaní automaticky, nemusí fungovat.
**Problém:** Pokud je příjemce k oznámení výstrahy přidaný automaticky, nemusí vždycky dostat oznámení.

**Alternativní řešení:** Pokud chcete mít jistotu, že příjemci dostanou oznámení, měli byste tyto příjemce k oznámením výstrah přidat ručně.

## Podpora jazyků na portálu Azure Preview
Portál Azure Preview je založený na nové platformě a podporuje tyto jazyky: čínština (zjednodušená), čínština (tradiční), čeština, holandština, angličtina, němčina, maďarština, italština, japonština, portugalština (Brazílie), portugalština (Portugalsko), ruština, španělština, angličtina, francouzština, korejština, polština, švédština, turečtina.

Konzola pro správu Intune a mobilní prostředí pro koncové uživatele podporují kromě všech jazyků podporovaných portálem Azure Preview také dánštinu, řečtinu, finštinu, norštinu a rumunštinu.



<!--HONumber=Jul16_HO4-->


