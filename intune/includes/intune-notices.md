---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: c4a17abdb518daba30fbdf339090f7e24c8c26d5
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412157"
---
Tato oznámení poskytují důležité informace, které vám pomohou připravit se na budoucí změny Intune a funkce. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizovat na nejnovější verzi aplikace portál společnosti pro Android <!--4536963-->
Intune pravidelně vydává aktualizace s Androidem aplikaci portál společnosti. V listopadu 2018 jsme vydali aktualizací aplikace portál společnosti, který součástí back-end přepínač přípravy na Googlu změnu z jejich stávajících oznámení platformy na Google Firebase Cloud Messaging (FCM). Když Google co vyřadí stávající oznámení platformy a přesune se do FCM, koncoví uživatelé budou muset aktualizovali svoje aplikace firemního portálu do alespoň z listopadu 2018 vydání pro pokračovat v komunikaci s obchodu Google play.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Naše telemetrie označuje, že máte zařízení s verzí starší než 5.0.4269.0 portál společnosti. Pokud tato verze nebo novější z aplikace portál společnosti není nainstalovaná, IT pro zařízení iniciované akce, jako je vymazání, resetovat heslo, dostupné a požadované aplikace se nainstaluje a zápis certifikátu nemusí fungovat podle očekávání. Pokud jsou vaše zařízení zaregistrovaná v Intune MDM, pak se zobrazí verze portálu společnosti a uživatele tak, že přejdete do klientské aplikace – zjištěné aplikace. Výběr starší verze aplikace portál společnosti vám umožní zobrazit, které koncoví uživatelé měli zařízení, která neprovedli aktualizaci portálu společnosti.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zeptejte se, že koncoví uživatelé zařízení s Androidem, které neprovedli aktualizaci na aktualizovat portál společnosti přes Google play. Informujte pracovníky helpdesku, v případě, že uživatel není uchovávat automatické aktualizace aplikace portál společnosti. Podívejte se na odkaz Další informace pro platformu FCM další na Googlu a změnit.

#### <a name="additional-information"></a>Další informace
https://firebase.google.com/docs/cloud-messaging/
