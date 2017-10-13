---
title: "Vaše zařízení s Androidem je zřejmě šifrované"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 208cf6eb2d29ec5458d97d0a4481cec420acc281
ms.sourcegitcommit: 59811bf1183b3ef9c9e81eded634bd0d3124d0bb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Zdá se, že vaše zařízení s Androidem je zašifrované, ale Portál společnosti hlásí, že není

Když zařízení zašifrujete, zakódujete informace, které jsou na něm uložené, pomocí tajného klíče, který znáte jenom vy. Zabráníte tak v přístupu neoprávněným osobám. Mnoho organizací vyžaduje, aby uživatelé zašifrovali svoje zařízení s Androidem, než získají přístup k firemním souborům, e-mailu nebo datům.

## <a name="common-issues"></a>Běžné problémy

Novější verze Androidu, zejména počínaje verzí 7.0, vyžadují spouštěcí heslo, aby se zaručilo, že je zařízení plně zašifrované. Výrobci různých zařízení používají pro spouštěcí heslo různé popisy a umístění. Ve většině případů se toto nastavení označuje jako zabezpečené spuštění. 

## <a name="solutions"></a>Řešení

### <a name="add-a-startup-pin"></a>Přidání spouštěcího kódu PIN

Určitá zařízení s Androidem budou vyžadovat vytvoření spouštěcího PIN kódu, který zaručí, že je zařízení zabezpečené. Existuje mnoho verzí Androidu od mnoha různých výrobců. Můžete tento problém zkusit vyřešit tak, že v aplikaci nastavení najdete umístění k povolení této možnosti. Třeba na Samsungu Galaxy S7 můžete zabezpečené spuštění povolit tak, že přejdete do **Nastavení** > **Zamykací obrazovka a zabezpečení** > **Zabezpečené spuštění**.  

### <a name="downgrade-your-version-of-android"></a>Přechod na starší verzi Androidu

Pokud vaše zařízení umožňuje přechod na starší verzi produktu, tedy na verzi Android 6.0+, proveďte to. Pokud se pokusíte přejít na starší verzi produktu, může dojít ke ztrátě dat. Jinak doporučujeme, abyste se kvůli řešení tohoto problému obrátili na svou firemní podporu. Kontaktní údaje na firemní podporu najdete na [webu Portál společnosti](https://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Problémy konkrétních výrobců

Některá zařízení s Androidem verze 7.0 a novější šifrují data způsoby, které nejsou konzistentní s určitými standardy platformy Android. Tato zařízení můžou vypadat jako zašifrovaná, i když jsou zcela nová. Intune rozpozná, že metody šifrování u těchto zařízení můžou ohrozit informace na daném zařízení. Riziko představují především kyberzločinci, kteří mají k zařízení fyzický přístup.

> [!Note]
> Microsoft spolupracuje s výrobci na vyřešení problémů, na které narazíme při testování nebo které nám nahlásí uživatelé. Tento článek aktualizujeme vždy, když jsou k dispozici nové informace. 

## <a name="known-devices"></a>Známá zařízení

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Známá zařízení, u kterých se dá tento problém vyřešit jejich aktualizací

Pokud máte některé z následujících zařízení, můžete na tento problém narazit, pokud jste zařízení neaktualizovali na nejnovější verzi Androidu. Aktualizace těchto zařízení můžete nainstalovat tak, že přejdete do **Nastavení** > **Aktualizace**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Známá zařízení, u kterých se tento problém momentálně nedá vyřešit jejich aktualizací

Pro níže uvedená zařízení není možné tento problém vyřešit. Pro přístup k prostředkům společnosti budete možná muset použít jiná zařízení. 

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Chytré telefony Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
