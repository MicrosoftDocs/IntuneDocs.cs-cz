---
title: Výjimky zásad přenosu dat pro aplikace
titleSuffix: Microsoft Intune
description: Vytvořte výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1910334093a416933912c9cdeedac85e36d66e92
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Vytvoření výjimek zásad přenosu dat ve správě mobilních aplikací Intune (MAM)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce můžete vytvořit výjimky zásad přenosu dat ve správě mobilních aplikací Intune (MAM). Pomocí výjimky lze konkrétně vybrat nespravované aplikace, které budou moct přenášet data do spravovaných aplikací a ze spravovaných aplikací. Nespravované aplikace, které jste zahrnuli do seznamu výjimek, musí být důvěryhodné pro oddělení IT. 

>[!WARNING] 
> Za provádění změn v zásadách výjimek přenosu dat nesete zodpovědnost. Nespravované aplikace (aplikace, které nejsou spravované pomocí Intune), které přidáte do těchto zásad, budou mít přístup k datům chráněným pomocí spravovaných aplikací. Takový přístup k chráněným datům může mít za následek porušení zabezpečení dat. Výjimky přenosu dat přidávejte jenom pro aplikace, které vaše organizace musí používat, ale které nepodporují zásady ochrany aplikací Intune. Kromě toho přidávejte výjimky jenom pro aplikace, které nepovažujete za rizikové z hlediska úniku dat.

Tato funkce se použije, když vytvoříte zásady ochrany aplikací Intune pro přenos dat s nastavením **jenom na spravované aplikace**. Pokud zásady přenosu dat nastavíte **jenom na spravované aplikace**, bude kromě vytvořených výjimek přenos dat i nadále omezený jenom na aplikace, které se spravují přes Intune. Tato omezení můžete vytvořit pomocí protokolů (iOS) nebo balíčků (Android).

Tuto funkci můžete nakonfigurovat tak, aby v zásadách ochrany aplikací v Intune MAM povolovala výjimky pro **omezení přenosu dat**. Tyto zásady se vyžadují jenom v případě, že chcete povolit přenos dat do aplikace, která nepodporuje zásady ochrany aplikací Intune. Tyto zásady umožňují aplikacím spravovaným pomocí Intune a s přenosem dat nastaveným **jenom na spravované aplikace** vyvolávat nespravované aplikace na základě protokolu URL (iOS) nebo názvu balíčku (Android). Intune přidává důležité nativní aplikace do výchozího seznamu výjimek. 

## <a name="ios-data-transfer-exceptions"></a>Výjimky přenosu dat pro iOS
U zásad cílících na iOS můžete nakonfigurovat výjimky přenosu dat pomocí protokolu URL. Pokud chcete přidat výjimku, vyhledejte informace o podporovaných protokolech URL v dokumentaci od vývojáře příslušné aplikace. Další informace o výjimkách přenosu dat pro iOS najdete v tématu [Nastavení zásad ochrany aplikací pro iOS – výjimky přenosu dat](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Výjimky přenosu dat pro Android
U zásad cílících na Android můžete nakonfigurovat výjimky přenosu dat pomocí názvu balíčku aplikace. Název balíčku aplikace můžete vyhledat na stránce obchodu **Google Play** pro aplikaci, pro kterou chcete přidat výjimku. Další informace o výjimkách přenosu dat pro Android najdete v tématu [Nastavení zásad ochrany aplikací pro Android – výjimky přenosu dat](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> ID balíčku aplikace najdete tak, že na tuto aplikaci přejdete v obchodě Google Play. ID balíčku je součástí adresy URL stránky aplikace. Třeba aplikace Microsoft Word má ID balíčku **com.microsoft.office.word**.

### <a name="example"></a>Příklad
Po přidání balíčku **Webex** jako výjimky k zásadám přenosu dat MAM se budou moct odkazy Webex v e-mailové zprávě spravovaného Outlooku otevírat přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezený.

- Příklad **Webex** pro iOS: Pokud chcete určit výjimku pro aplikaci **Webex**, aby ji mohly vyvolávat spravované aplikace Intune, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>wbx</code>.

- Příklad **Webex** pro Android: Pokud chcete určit výjimku pro aplikaci **Webex**, aby ji mohly vyvolávat spravované aplikace Intune, je nutné přidat výjimku přenosu dat pro tento řetězec: <code>com.cisco.webex.meetings</code>. 

## <a name="next-steps"></a>Další kroky

- [Vytvoření a nasazení zásad ochrany aplikací](app-protection-policies.md)
- [Nastavení zásad ochrany aplikací pro iOS – výjimky přenosu dat](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Nastavení zásad ochrany aplikací pro Android – výjimky přenosu dat](app-protection-policy-settings-android.md#data-transfer-exemptions)
