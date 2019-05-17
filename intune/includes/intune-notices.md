---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732613"
---
Tato oznámení poskytují důležité informace, které vám pomohou připravit se na budoucí změny Intune a funkce. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Změnit v pracovním postupu registrace pomocí portálu společnosti Intune na zařízení se systémem iOS podnikové ověřování Pomocníka s nastavením <!-- 1927359 -->
Je chystanou změnou v pracovním postupu pro registraci zařízení s Iosem prostřednictvím jednoho z Apple podnikové způsoby registrace zařízení – Apple Configurator, obchodní ředitel společnosti Apple, Apple School Manager nebo Apple zařízení registrace programu (DEP), když pomocí instalačního programu Pomocník pro ověřování. Tato změna platí pouze pro zařízení zaregistrovaná s přidružením uživatele.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Při nasazení této změně, profily registrace v Intune na portálu Azure portal bude aktualizován tak, aby můžete určit, jak ověřovat zařízení, a pokud se zobrazí v aplikaci portál společnosti. Bude Vylepšený pracovní postup registrace zařízení s Iosem pomocí výše uvedených metod. 

- Při registraci nového zařízení a ověřování s pomocníkem s nastavením, je budete moci rozhodnout, zda chcete automaticky nasadit aplikaci portál společnosti. Koncoví uživatelé uvidí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace.  
- Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple je nutné provést akci, pokud chcete zapnout zásady podmíněného přístupu. Budete muset [Konfigurace zásady Konfigurace aplikací](https://aka.ms/enrollment_setup_assistant) s konkrétní xml tak, aby nabízel až do těchto zařízení aplikaci portál společnosti.  Pokud se rozhodnete tak, aby nabízel portálu společnosti tímto způsobem, koncovým uživatelům se zobrazí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace. 
- Po této změně nasazení, pokud jste nenasadili portál společnosti pomocí konfigurační profil aplikací uvedených výše, a pokud budete ke stažení koncovým uživatelům ukládat aplikace portál společnosti z aplikace, můžou zaregistrovat, ale zobrazí chybová zpráva. Nebudou moct používat aplikace pro podmíněný přístup. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Pokud máte v úmyslu používat upravenou pracovní postup, je vhodné pro aktualizace pokynů pro koncové uživatele k označení, že:

- Koncoví uživatelé nebudou moci zobrazit dvě obrazovky výše uvedené v postupem registrace. 
- Budete muset přihlásit do aplikace portál společnosti, když se automaticky nasadí a není si ho stáhnout z app storu. 

Můžete teď vytvořit zásady Konfigurace aplikací v případě potřeby během přípravy na tuto změnu. Při zavádění tohoto nového pracovního postupu se zobrazí aktualizovaná registrační profily z konzoly. Také jsme budete informovat o zavedení prostřednictvím Centra zpráv. Potom budete muset udělat tak, aby vaši koncoví uživatelé můžou prostřednictvím programu DEP zaregistrovat prostřednictvím pomocníka s nastavením a portál společnosti můžete použít pro podmíněný přístup.

#### <a name="additional-information"></a>Další informace 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizovat na nejnovější verzi aplikace portál společnosti pro Android <!--4536963-->
Intune pravidelně vydává aktualizace s Androidem aplikaci portál společnosti. V listopadu 2018 jsme vydali aktualizací aplikace portál společnosti, který součástí back-end přepínač přípravy na Googlu změnu z jejich stávajících oznámení platformy na Google Firebase Cloud Messaging (FCM). Když Google co vyřadí stávající oznámení platformy a přesune se do FCM, koncoví uživatelé budou muset aktualizovali svoje aplikace firemního portálu do alespoň z listopadu 2018 vydání pro pokračovat v komunikaci s obchodu Google play.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Naše telemetrie označuje, že máte zařízení s verzí starší než 5.0.4269.0 portál společnosti. Pokud tato verze nebo novější z aplikace portál společnosti není nainstalovaná, IT pro zařízení iniciované akce, jako je vymazání, resetovat heslo, dostupné a požadované aplikace se nainstaluje a zápis certifikátu nemusí fungovat podle očekávání. Pokud jsou vaše zařízení zaregistrovaná v Intune MDM, pak se zobrazí verze portálu společnosti a uživatele tak, že přejdete do klientské aplikace – zjištěné aplikace. Výběr starší verze aplikace portál společnosti vám umožní zobrazit, které koncoví uživatelé měli zařízení, která neprovedli aktualizaci portálu společnosti.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zeptejte se, že koncoví uživatelé zařízení s Androidem, které neprovedli aktualizaci na aktualizovat portál společnosti přes Google play. Informujte pracovníky helpdesku, v případě, že uživatel není uchovávat automatické aktualizace aplikace portál společnosti. Podívejte se na odkaz Další informace pro platformu FCM další na Googlu a změnit.

#### <a name="additional-information"></a>Další informace
https://firebase.google.com/docs/cloud-messaging/