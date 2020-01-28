---
title: Vyřazení zámku aktivace v iOSu přes Intune
titleSuffix: Microsoft Intune
description: Přečtěte si, jak se dá přes Intune vyřadit zámek aktivace v iOSu, aby bylo možné přistupovat k uzamčeným zařízením.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c3847890a4871b784764a5beca46f6776d52d3f
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2020
ms.locfileid: "76761277"
---
# <a name="disable-activation-lock-on-supervised-ios-devices-with-intune"></a>Zakázání Zámek aktivace na zařízeních s iOS pod dohledem v Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune vám může pomoci spravovat zámek aktivace v iOSu – funkci aplikace Najít iPhone pro zařízení s iOSem 8.0 a novějším. Zámek aktivace je automaticky zapnutý, když uživatel na zařízení otevře aplikaci Najít iPhone. Když je tato funkce povolená, musí se zadat Apple ID a heslo uživatele, aby bylo možné:

- Vypnout aplikaci Můj iPhone
- Vymazat zařízení
- Znovu aktivovat zařízení

## <a name="how-activation-lock-affects-you"></a>Jaký vliv má funkce Zámek aktivace na práci se zařízením

Funkce Zámek aktivace sice pomáhá zabezpečit zařízení se systémem iOS a zvyšuje šance na obnovení zařízení v případě, že dojde k jeho ztrátě nebo odcizení, ale pro vás, jakožto správce IT, může představovat určité problémy. Například:

- Uživatel si na zařízení nastaví zámek aktivace. Tento uživatel pak společnost opustí a zařízení vrátí. Bez Apple ID a hesla uživatele neexistuje způsob, jak zařízení znovu aktivovat.
- Potřebujete sestavu všech zařízení, která mají povolený zámek aktivace.
- Při obnovování zařízení v organizaci chcete některá zařízení přiřadit jinému oddělení. Můžete to provést jedině se zařízeními, ve kterých není zámek aktivace povolený.

Aby bylo možné tyto problémy vyřešit, společnost Apple zavedla Zámek aktivace zakázat v iOS 7,1. Disable Zámek aktivace umožňuje odebrat Zámek aktivace ze zařízení pod dohledem bez Apple ID a hesla uživatele. Dozorovaná zařízení mohou generovat kód pro vyřazení zámku aktivace, který je uložený na aktivačním serveru společnosti Apple.

>[!TIP]
>Režim Pod dohledem pro zařízení s iOSem vám umožňuje pomocí Apple Configuratoru zařízení zamknout a omezit tak jeho funkčnost jenom na konkrétní firemní účely. Režim dohledu se používá jenom u zařízení v majetku podniků.

Další informace o zámku aktivace najdete na [webu společnosti Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak Intune pomáhá se správou zámku aktivace
Intune může požádat o stav zámku aktivace u dozorovaných zařízení, na kterých běží iOS 8.0 a novější. V případě zařízení pod dohledem může Intune získat kód pro zákaz Zámek aktivace a přímo ho vydat do zařízení. Pokud bylo zařízení vymazáno, můžete k němu získat přístup přímo tak, že uživatelské jméno necháte prázdné a jako heslo zadáte tento kód.

**Správy zámku aktivace pomocí Intune přináší firmám následující výhody:**

- Uživatel získá výhody zabezpečení aplikace Najít iPhone.
- Dokážete zajistit, aby uživatel mohl zařízení používat ke své práci, a zároveň budete vědět, že když bude nutné zařízení použít k jinému účelu, budete ho moct vyřadit nebo odemknout.

## <a name="before-you-start"></a>Než začnete
Než budete moct Zámek aktivace na zařízeních zakázat, je potřeba, abyste je povolili pomocí následujících pokynů:

1. Nakonfigurujte profil omezení zařízení Intune pro iOS pomocí informací uvedených v [postupu pro konfiguraci nastavení omezení zařízení](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. V [nastavení omezení pro zařízení s iOS](../configuration/device-restrictions-ios.md) v části **Obecné** povolte možnost **Zámek aktivace**.
3. Uložte profil a [přiřaďte ho](../configuration/device-profile-assign.md) k zařízením, na kterých chcete spravovat zámek aktivace zakázat.


## <a name="how-to-use-disable-activation-lock"></a>Jak používat Disable Zámek aktivace

>[!IMPORTANT]
>Když Zámek aktivace v zařízení zakážete, je při spuštění aplikace Najít iPhone automaticky použita nová Zámek aktivace. Z tohoto důvodu **byste měli mít před provedením tohoto postupu zařízení fyzicky u sebe**.

Akce **zakázat zámek aktivace** vzdáleného zařízení v Intune odebere zámek aktivace ze zařízení s iOS bez nutnosti Apple ID a hesla uživatele. Když Zámek aktivace zakážete, zařízení se znovu zapne Zámek aktivace při spuštění aplikace Najít iPhone. Zakažte Zámek aktivace jenom v případě, že máte fyzický přístup k zařízení.

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. V okně **Intune** vyberte **Zařízení**.
4. V okně **Zařízení** vyberte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, vyberte vzdálenou akci **zakázat zámek aktivace** zařízení.
6. Přejděte do hardwarové části zařízení a v části **Podmíněný přístup** zkopírujte hodnotu **Kód pro překonání zámku aktivace**.

    >[!NOTE]
    >Před vymazáním zařízení si kód zkopírujte. Když nastavení zařízení obnovíte před zkopírováním kódu, kód se z Azure odebere.

7. Přejděte do okna zařízení **Přehled** a pak vyberte **Vymazat**.
8. Jakmile se zařízení obnoví, zobrazí se výzva k zadání *Apple ID* a *hesla*. Pole *ID* nechte prázdné a jako *heslo* zadejte **kód pro překonání zámku**. Tímto se účet odebere ze zařízení. 


## <a name="next-steps"></a>Další kroky

Stav požadavku na odemčení můžete zkontrolovat na stránce podrobností pro dané zařízení v úloze **Spravovat zařízení**.
