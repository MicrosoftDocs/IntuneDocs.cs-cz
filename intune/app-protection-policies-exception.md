---
title: Výjimky zásad přenosu dat pro aplikace
titleSuffix: Microsoft Intune
description: Vytvořte výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM).
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b860b68bbf8940a89533159885f471f5337ca0e8
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2018
ms.locfileid: "34216135"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Vytvoření výjimek zásad přenosu dat ve správě mobilních aplikací Intune (MAM)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce můžete vytvořit výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM). Pomocí výjimky lze konkrétně vybrat nespravované aplikace, které budou moct přenášet data do spravovaných aplikací a ze spravovaných aplikací. Nespravované aplikace, které jste zahrnuli do seznamu výjimek, musí být důvěryhodné pro oddělení IT. 

>[!WARNING] 
> Za provádění změn v zásadách výjimek přenosu dat nesete zodpovědnost. Nespravované aplikace (aplikace, které nejsou spravované pomocí Intune), které přidáte do těchto zásad, budou mít přístup k datům chráněným pomocí spravovaných aplikací. Takový přístup k chráněným datům může mít za následek porušení zabezpečení dat. Výjimky přenosu dat přidávejte jenom pro aplikace, které vaše organizace musí používat, ale které nepodporují zásady ochrany aplikací Intune. Kromě toho přidávejte výjimky jenom pro aplikace, které nepovažujete za rizikové z hlediska úniku dat.

Pokud v rámci zásad Intune Application Protection nastavíte **Povolit aplikaci posílat data do jiných aplikací** na **Aplikace spravované podle zásad**, znamená to, že aplikace může přenášet data pouze do aplikací spravovaných Intune. Pokud chcete povolit přenos dat do konkrétních aplikací, které nepodporují zásady Intune APP, můžete vytvořit výjimky z těchto zásad pomocí možnosti **Vyberte aplikace, které se mají vyloučit**. Výjimky umožňují, aby aplikace spravované Intune vyvolaly nespravované aplikace založené na protokolu URL (iOS) nebo názvu balíčku (Android). Intune přidává ve výchozím nastavení důležité nativní aplikace do seznamu výjimek. 

> [!NOTE]
> Změna nebo přidání aplikací do výjimek zásad přenosu dat nemá vliv na jiné zásady ochrany aplikací, jako jsou omezení vyjmutí, kopírování a vložení. 

## <a name="ios-data-transfer-exceptions"></a>Výjimky přenosu dat pro iOS
U zásad cílících na iOS můžete nakonfigurovat výjimky přenosu dat pomocí protokolu URL. Pokud chcete přidat výjimku, vyhledejte informace o podporovaných protokolech URL v dokumentaci od vývojáře příslušné aplikace. Další informace o výjimkách přenosu dat pro iOS najdete v tématu [Nastavení zásad ochrany aplikací pro iOS – výjimky přenosu dat](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Výjimky přenosu dat pro Android
U zásad cílících na Android můžete nakonfigurovat výjimky přenosu dat pomocí názvu balíčku aplikace. Název balíčku aplikace můžete vyhledat na stránce obchodu **Google Play** pro aplikaci, pro kterou chcete přidat výjimku. Další informace o výjimkách přenosu dat pro Android najdete v tématu [Nastavení zásad ochrany aplikací pro Android – výjimky přenosu dat](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

### <a name="example"></a>Příklad
Po přidání balíčku **Webex** jako výjimky k zásadám přenosu dat MAM se budou moct odkazy Webex v e-mailové zprávě spravovaného Outlooku otevírat přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezený.

- Příklad **Webex** pro iOS: Pokud chcete určit výjimku pro aplikaci **Webex**, aby ji mohly vyvolávat spravované aplikace Intune, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>wbx</code>.
    
 - Příklad **Maps** pro iOS: Pokud chcete určit výjimku pro nativní aplikaci **Maps**, aby ji mohly vyvolávat spravované aplikace Intune, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>maps</code>.

- Příklad **Webex** pro Android: Pokud chcete určit výjimku pro aplikaci **Webex**, aby ji mohly vyvolávat spravované aplikace Intune, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>com.cisco.webex.meetings</code>.
    
- Příklad **SMS** pro Android: Pokud chcete určit výjimku pro nativní aplikaci **SMS**, aby ji mohly vyvolávat spravované aplikace Intune napříč různými aplikacemi pro zasílání zpráv a zařízeními Android, je nutné přidat výjimku přenosu dat pro následující řetězce: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Další kroky

- [Vytvoření a nasazení zásad ochrany aplikací](app-protection-policies.md)
- [Nastavení zásad ochrany aplikací pro iOS – výjimky přenosu dat](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Nastavení zásad ochrany aplikací pro Android – výjimky přenosu dat](app-protection-policy-settings-android.md#data-transfer-exemptions)
