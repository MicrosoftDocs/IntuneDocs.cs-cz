---
title: Registrace zařízení s Androidem v Intune
titlesuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 3d86afec4e501533ab0048e866969a5bf73c2c57
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2019
ms.locfileid: "54387053"
---
# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete spravovat následující zařízení s Androidem:
- Zařízení s Androidem včetně zařízení Samsung Knox Standard
- Zařízení s androidem enterprise, včetně:
    - **Zařízení s pracovním profilem**: Osobní zařízení udělit oprávnění pro přístup k podnikovým datům. Správci mohou spravovat pracovní účty, aplikace a data. Ze zařízení osobní data se ukládají odděleně od pracovní data a správci nad kterými nemáte kontrolu osobní nastavení nebo data. 
    - **Vyhrazená zařízení s androidem**: Zařízení vlastněná společností, jeden používá, například digitálních materiálů, lístku podpory tisku nebo řízení zásob. Správci omezí použití zařízení na omezenou sadu aplikací a webových odkazů. Uživatelé zároveň nemůžou na tomto zařízení přidávat jiné aplikace ani provádět jiné akce.
    - **Plně spravovaná zařízení s androidem**: Zařízení vlastněné společností, jeden uživatel používá výhradně pro pracovní a ne osobní použití. Správci můžou spravovat celé zařízení a vynucovat ovládací prvky zásad, není k dispozici pro pracovní profily. 

## <a name="prerequisite"></a>Požadavek

Při přípravě na správu mobilních zařízení musíte nastavit autoritu pro správu mobilních zařízení (MDM) na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.

## <a name="set-up-android-enrollment"></a>Nastavení registrace zařízení s Androidem

Standardně je služba Intune nastavená tak, aby umožňovala registraci zařízení používajících Android a Samsung Knox Standard. Po splnění tohoto předpokladu musí správci pouze [sdělit uživatelům, jak mají svá zařízení zaregistrovat](/intune-user-help/enroll-your-device-in-intune-android).

Po registraci můžete začít se správou zařízení uživatelů v Intune včetně [přiřazení zásad dodržování předpisů](compliance-policy-create-android.md), [správy aplikací](app-management.md) a dalších úloh.

Informace o dalších uživatelských úkolech najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení Android s Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Pokud chcete blokovat registraci zařízení s Androidem nebo blokovat jenom zařízení s Androidem v osobním vlastnictví, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="set-up-android-enterprise-enrollment"></a>Nastavení registrace Androidu Enterprise

Android Enterprise je sada funkcí a služeb pro zařízení s Androidem, které oddělují osobní aplikace a data od pracovního profilu obsahujícího pracovní aplikace a data. Zařízení s androidem enterprise zahrnují pracovní profil zařízení, plně spravovaná zařízení a vyhrazená zařízení. 

- [Nastavení registrace Android pracovní profil](android-work-profile-enroll.md)
- [Nastavení registrace zařízení s Androidem vyhrazené](android-kiosk-enroll.md)
- [Nastavení Androidu plně spravovat registrace](android-fully-managed-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Prostředí koncového uživatele při registraci zařízení se zabezpečením Samsung Knox

Zařízení Samsung Knox Standard jsou podporována správa více uživatelů pomocí Intune. To znamená, že uživatelé se můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení je centrálně spravované bez ohledu na to, jestli se používá. Když se uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Když se uživatelé registrují veškerá data aplikace se vymaže.

Při registraci zařízení se zabezpečením Samsung Know je třeba mít na paměti následující:
-   I když žádné zásady nevyžadují kód PIN, musí mít zařízení alespoň čtyřciferný kód PIN, aby se mohlo zaregistrovat. Pokud zařízení nemá kód PIN, uživateli se zobrazí výzva, aby ho vytvořil.
-   Pro certifikáty WPJ (Workplace Join) neexistuje žádná interakce uživatele.
-   Uživateli se zobrazí výzva s informacemi o registraci služby a o tom, co aplikace může dělat.
-   Uživateli se zobrazí výzva s informacemi o registraci zabezpečení Knox.
-   Pokud se vynucují zásady šifrování, musí uživatelé nastavit šestiznakové složité heslo jako heslo k zařízení.
-   Pro přístup k prostředkům společnosti se nezobrazují žádné další výzvy k instalaci certifikátů nabízených službou.
- Některá starší zařízení se zabezpečením Knox zobrazí výzvu k instalaci dalších certifikátů, které slouží pro přístup k prostředkům společnosti.
- Pokud se zařízení Samsung Mini nepodaří nainstalovat WPJ a zobrazí se chyba, že **certifikát se nenašel** nebo že **není možné zařízení zaregistrovat**, nainstalujte nejnovější aktualizace firmwaru Samsung.

## <a name="next-steps"></a>Další postup

- [Nastavení registrace Android pracovní profil](android-work-profile-enroll.md)
- [Nastavení registrace zařízení s Androidem vyhrazené](android-kiosk-enroll.md)
- [Nastavení Androidu plně spravovat registrace](android-fully-managed-enroll.md)
