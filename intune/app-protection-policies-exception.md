---
title: Výjimky zásad přenosu dat pro aplikace
titleSuffix: Microsoft Intune
description: Vytvořte výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9f6ee3d1672c375071b061b4a551f609792deb9
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238247"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Vytvoření výjimek zásad přenosu dat ve správě mobilních aplikací Intune (MAM)

Jako správce můžete vytvořit výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM). Pomocí výjimky lze konkrétně vybrat nespravované aplikace, které budou moct přenášet data do spravovaných aplikací a ze spravovaných aplikací. Tým IT musí důvěřovat nespravovaných aplikacích, které zahrnete do seznamu výjimek. 

>[!WARNING] 
> Za provádění změn v zásadách výjimek přenosu dat nesete zodpovědnost. Nespravované aplikace (aplikace, které nejsou spravované pomocí Intune), které přidáte do těchto zásad, budou mít přístup k datům chráněným pomocí spravovaných aplikací. Takový přístup k chráněným datům může mít za následek porušení zabezpečení dat. Výjimky přenosu dat přidávejte jenom pro aplikace, které vaše organizace musí používat, ale které nepodporují zásady ochrany aplikací Intune. Kromě toho přidávejte výjimky jenom pro aplikace, které nepovažujete za rizikové z hlediska úniku dat.

V rámci Intune zásadami ochrany aplikací, nastavení **povolit aplikaci posílat data do jiných aplikací** k **aplikace spravované podle zásad** znamená, že aplikace můžou přenášet data jenom do aplikací spravovaných pomocí Intune. Pokud je potřeba povolit data přesunou do konkrétní aplikace, které nepodporují aplikace v Intune, můžete vytvořit výjimky pro tuto zásadu pomocí **vyberte aplikace, které se mají vyloučit**. Výjimky umožňují, aby aplikace spravované Intune vyvolaly nespravované aplikace založené na protokolu URL (iOS) nebo názvu balíčku (Android). Intune přidává ve výchozím nastavení důležité nativní aplikace do seznamu výjimek. 

> [!NOTE]
> Změna nebo přidání aplikací do výjimek zásad přenosu dat nemá vliv na jiné zásady ochrany aplikací, jako jsou omezení vyjmutí, kopírování a vložení. 

## <a name="ios-data-transfer-exceptions"></a>Výjimky přenosu dat pro iOS
U zásad cílících na iOS můžete nakonfigurovat výjimky přenosu dat pomocí protokolu URL. Pokud chcete přidat výjimku, vyhledejte informace o podporovaných protokolech URL v dokumentaci od vývojáře příslušné aplikace. Další informace o výjimkách přenosu dat pro iOS najdete v tématu [výjimky přenosu nastavení zásad ochrany aplikací iOS - Data](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> U aplikací jiných výrobců Microsoft nenabízí metodu ručního vyhledání protokolu adresy URL pro vytváření výjimek aplikací. 

## <a name="android-data-transfer-exceptions"></a>Výjimky přenosu dat pro Android
U zásad cílících na Android můžete nakonfigurovat výjimky přenosu dat pomocí názvu balíčku aplikace. Název balíčku aplikace můžete vyhledat na stránce obchodu **Google Play** pro aplikaci, pro kterou chcete přidat výjimku. Další informace o výjimkách přenosu dat pro Android najdete v tématu [výjimky přenosu nastavení zásad ochrany aplikací pro Android – Data](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

### <a name="example"></a>Příklad
Po přidání balíčku **Webex** jako výjimky k zásadám přenosu dat MAM se budou moct odkazy Webex v e-mailové zprávě spravovaného Outlooku otevírat přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezený.

- iOS **Webex** příkladu:   Které se mají vyloučit **Webex** aplikaci tak, že je povolené má být volána v Intune spravovaných aplikací, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>wbx</code>
    
 - iOS **mapy** příkladu:  Pokud chcete určit výjimku pro nativní **mapy** aplikaci tak, že je povolené má být volána v Intune spravovaných aplikací, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>maps</code>

- Android **Webex** příkladu:   Které se mají vyloučit **Webex** aplikaci tak, že je povolené má být volána v Intune spravovaných aplikací, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>com.cisco.webex.meetings</code>
    
- Android **SMS** příkladu:   Pokud chcete určit výjimku pro nativní **SMS** aplikaci tak, že je povolené má být volána v Intune spravovaných aplikací v různých aplikacích zasílání zpráv a zařízení s Androidem, je nutné přidat výjimku přenosu dat pro následující řetězce: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Další postup

- [Vytvoření a nasazení zásad ochrany aplikací](app-protection-policies.md)
- [Nastavení zásad ochrany aplikací pro iOS – výjimky přenosu dat](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Nastavení zásad ochrany aplikací pro Android – výjimky přenosu dat](app-protection-policy-settings-android.md#data-transfer-exemptions)
