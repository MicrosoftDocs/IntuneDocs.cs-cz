---
title: Vaše zařízení Android je zřejmě zašifrované | Microsoft Docs
description: Vyřešit stav šifrování v aplikaci portál společnosti a Microsoft Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8c35400f37ab4ddee275cf23f7a50f280322e3b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501574"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Zařízení zašifrovaná, ale aplikace Řekněme, že jinak

Pokud aplikace portál společnosti nebo aplikace pro Microsoft Intune říct, že vaše zařízení není zašifrované, ale jste si jisti, že se jedná, proveďte kroky v tomto článku.  

## <a name="add-a-startup-pin"></a>Přidání spouštěcího kódu PIN

Určitá zařízení s Androidem budou vyžadovat vytvoření spouštěcího PIN kódu, který zaručí, že je zařízení zabezpečené. Umístění tohoto nastavení bude ve vašem zařízení **nastavení** aplikace. Název a umístění nastavení může lišit. Třeba na Samsungu Galaxy S7 nastavení se nazývá **zabezpečené spuštění**. Chcete-li jej povolit a vytvořit heslo, přejděte na **nastavení** > **zamykací obrazovka a zabezpečení** > **zabezpečené spuštění**.  

## <a name="encrypt-the-entire-device"></a>Zašifrujte celé zařízení.

Tato část platí jenom pro aplikaci portál společnosti. Některá zařízení vám dají na výběr, jestli chcete zašifrovat celé zařízení, nebo jenom využité místo. Zvolte možnost zašifrování celého zařízení. Pokud jste se rozhodli šifrovat jenom využité místo:

1. [Odebrat toto zařízení z portálu společnosti](unenroll-your-device-from-intune-android.md).
2. Dešifrujte využité místo.  
3. Zašifrujte celé zařízení.  
4. Zařízení znovu zaregistrujte.  

## <a name="downgrade-your-version-of-android"></a>Přechod na starší verzi Androidu

Tato část platí jenom pro aplikaci portál společnosti. Pokud vaše zařízení nabízí možnost downgradovat na Android 6.0 a novější, proveďte to. Existuje riziko ztráty dat, pokud se pokusíte přejít na. Jinak doporučujeme, abyste se kvůli řešení tohoto problému obrátili na svou firemní podporu. Kontaktní informace na svou firemní podporu získat [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Problémy konkrétních výrobců

Některá zařízení s Androidem verze 7.0 nebo novější šifrují data způsoby, které nejsou konzistentní s určitými standardy platformy Android. Tato zařízení můžou vypadat jako zašifrovaná, i když jsou zcela nová. Intune rozpozná, že metody šifrování u těchto zařízení můžou ohrozit informace na daném zařízení. Riziko představují především kyberzločinci, kteří mají k zařízení fyzický přístup.

> [!Note]
> Microsoft spolupracuje s výrobci na vyřešení problémů, na které narazíme při testování nebo které nám nahlásí uživatelé. Tento článek aktualizujeme vždy, když jsou k dispozici nové informace. 

## <a name="update-known-devices"></a>Aktualizovat známá zařízení   

Pokud vaše zařízení jste neprovedli aktualizaci na nejnovější verzi Androidu, přejděte do svého zařízení **nastavení** aplikaci a vyberte **aktualizace**. Dokud je aktualizovat, se nemusí zobrazit tato zařízení kompatibilní.  

- Huawei Honor 8
- Huawei P9

## <a name="known-devices-that-always-appear-encrypted"></a>Známá zařízení, které se vždy zobrazují šifrované  
Následující zařízení bude vždy vypadat jako zašifrovaná a nelze použít pro přístup k prostředkům společnosti. Přístup k firemním prostředkům, musí používat jiné zařízení.  

- Huawei Mate 8
- Zařízení OPPO
- Zařízení vivo
- Chytré telefony Xiaomi mi  

## <a name="next-steps"></a>Další postup   
Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.  