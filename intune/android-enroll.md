---
title: Registrace zařízení s Androidem v Intune
titlesuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 79a1a03f74db8e44dc3ee4d6575e193ce7841e24
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2018
ms.locfileid: "53031887"
---
# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete spravovat následující zařízení s Androidem:
- Zařízení s Androidem včetně zařízení Samsung Knox Standard
- Zařízení s Androidem Enterprise včetně [zařízení s pracovním profilem Androidu](#enable-enrollment-of-android-for-work-devices) a zařízení s Androidem v beznabídkovém režimu

U zařízení, která používají Samsung Knox Standard, se podporuje správa více uživatelů pomocí Intune. To znamená, že uživatelé se můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení je centrálně spravované bez ohledu na to, jestli se používá. Když se uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

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

Android Enterprise je sada funkcí a služeb pro zařízení s Androidem, které oddělují osobní aplikace a data od pracovního profilu obsahujícího pracovní aplikace a data. K zařízením s Androidem Enterprise patří zařízení s pracovním profilem a zařízení v beznabídkovém režimu. 

Před nastavením registrace zařízení s Androidem Enterprise musíte napřed [propojit Android Enterprise s Intune](connect-intune-android-enterprise.md). Po dokončení tohoto kroku můžete:

[Nastavit registraci pracovního profilu Androidu](android-work-profile-enroll.md)
[Nastavit registraci Androidu v beznabídkovém režimu](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Prostředí koncového uživatele při registraci zařízení se zabezpečením Samsung Knox
Při registraci zařízení se zabezpečením Samsung Know je třeba mít na paměti následující:
-   I když žádné zásady nevyžadují kód PIN, musí mít zařízení alespoň čtyřciferný kód PIN, aby se mohlo zaregistrovat. Pokud zařízení nemá kód PIN, uživateli se zobrazí výzva, aby ho vytvořil.
-   Pro certifikáty WPJ (Workplace Join) neexistuje žádná interakce uživatele.
-   Uživateli se zobrazí výzva s informacemi o registraci služby a o tom, co aplikace může dělat.
-   Uživateli se zobrazí výzva s informacemi o registraci zabezpečení Knox.
-   Pokud se vynucují zásady šifrování, musí uživatelé nastavit šestiznakové složité heslo jako heslo k zařízení.
-   Pro přístup k prostředkům společnosti se nezobrazují žádné další výzvy k instalaci certifikátů nabízených službou.
- Některá starší zařízení se zabezpečením Knox zobrazí výzvu k instalaci dalších certifikátů, které slouží pro přístup k prostředkům společnosti.
- Pokud se zařízení Samsung Mini nepodaří nainstalovat WPJ a zobrazí se chyba, že **certifikát se nenašel** nebo že **není možné zařízení zaregistrovat**, nainstalujte nejnovější aktualizace firmwaru Samsung.
