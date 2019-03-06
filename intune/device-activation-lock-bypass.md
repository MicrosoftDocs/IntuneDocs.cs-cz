---
title: Vyřazení zámku aktivace v iOSu přes Intune
titlesuffix: Microsoft Intune
description: Přečtěte si, jak se dá přes Intune vyřadit zámek aktivace v iOSu, aby bylo možné přistupovat k uzamčeným zařízením.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cb8967c82758bbf5749a2335f706d1e32e51010e
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397810"
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Vyřazení zámku aktivace přes Intune na zařízeních s iOSem, která jsou pod dohledem


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune vám může pomoci spravovat zámek aktivace v iOSu – funkci aplikace Najít iPhone pro zařízení s iOSem 8.0 a novějším. Zámek aktivace je automaticky zapnutý, když uživatel na zařízení otevře aplikaci Najít iPhone. Když je tato funkce povolená, musí se zadat Apple ID a heslo uživatele, aby bylo možné:

- Vypnout aplikaci Můj iPhone
- Vymazat zařízení
- Znovu aktivovat zařízení

## <a name="how-activation-lock-affects-you"></a>Jaký vliv má funkce Zámek aktivace na práci se zařízením

Funkce Zámek aktivace sice pomáhá zabezpečit zařízení se systémem iOS a zvyšuje šance na obnovení zařízení v případě, že dojde k jeho ztrátě nebo odcizení, ale pro vás, jakožto správce IT, může představovat určité problémy. Příklad:

- Uživatel si na zařízení nastaví zámek aktivace. Tento uživatel pak společnost opustí a zařízení vrátí. Bez Apple ID a hesla uživatele neexistuje způsob, jak zařízení znovu aktivovat.
- Potřebujete sestavu všech zařízení, která mají povolený zámek aktivace.
- Při obnovování zařízení v organizaci chcete některá zařízení přiřadit jinému oddělení. Můžete to provést jedině se zařízeními, ve kterých není zámek aktivace povolený.

Aby bylo možné tyto problémy vyřešit, společnost Apple vydala v iOSu 7.1 funkci vyřazení zámku aktivace. To vám umožní odebrat zámek aktivace ze zařízení pod dohledem i bez Apple ID a hesla uživatele. Dozorovaná zařízení mohou generovat kód pro vyřazení zámku aktivace, který je uložený na aktivačním serveru společnosti Apple.

>[!TIP]
>Režim Pod dohledem pro zařízení s iOSem vám umožňuje pomocí Apple Configuratoru zařízení zamknout a omezit tak jeho funkčnost jenom na konkrétní firemní účely. Režim dohledu se používá jenom u zařízení v majetku podniků.

Další informace o zámku aktivace najdete na [webu společnosti Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak Intune pomáhá se správou zámku aktivace
Intune může požádat o stav zámku aktivace u dozorovaných zařízení, na kterých běží iOS 8.0 a novější. Pouze pro dozorovaná zařízení může služba Intune získat kód pro vyřazení zámku aktivace a přímo ho předat zařízení. Pokud bylo zařízení vymazáno, můžete k němu získat přístup přímo tak, že uživatelské jméno necháte prázdné a jako heslo zadáte tento kód.

**Správy zámku aktivace pomocí Intune přináší firmám následující výhody:**

- Uživatel získá výhody zabezpečení aplikace Najít iPhone.
- Dokážete zajistit, aby uživatel mohl zařízení používat ke své práci, a zároveň budete vědět, že když bude nutné zařízení použít k jinému účelu, budete ho moct vyřadit nebo odemknout.

## <a name="before-you-start"></a>Než začnete
Než budete moct zámek aktivace na zařízeních vyřadit, musíte ho nejdřív povolit. Uděláte to takto:

1. Nakonfigurujte profil omezení zařízení Intune pro iOS pomocí informací uvedených v [postupu pro konfiguraci nastavení omezení zařízení](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. V [nastavení omezení pro zařízení s iOS](device-restrictions-ios.md) v části **Obecné** povolte možnost **Zámek aktivace**.
3. Profil uložte a [přiřaďte ho](device-profile-assign.md) k zařízením, na kterých chcete spravovat vyřazení zámku aktivace.


## <a name="how-to-use-activation-lock-bypass"></a>Jak používat vyřazení zámku aktivace

>[!IMPORTANT]
>Pokud je spuštěná aplikace Najít iPhone, při vyřazení zámku aktivace na zařízení se automaticky použije nový zámek aktivace. Z tohoto důvodu **byste měli mít před provedením tohoto postupu zařízení fyzicky u sebe**.

Akce Intune se vzdáleným zařízením **Vynechat zámek aktivace** odebere zámek aktivace ze zařízení s iOSem bez vyžadování Apple ID a hesla uživatele. Po vynechání zámku aktivace ho zařízení znovu zapne při spuštění aplikace Najít iPhone. Zámek aktivace vynechejte jenom v případě, že máte k zařízení fyzický přístup.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.
3. V okně **Intune** vyberte **Zařízení**.
4. V okně **Zařízení** vyberte **Všechna zařízení**.
5. Na seznamu zařízení, která spravujete, vyberte vzdálenou akci zařízení **Vynechat zámek aktivace**.
6. Přejděte do hardwarové části zařízení a v části **Podmíněný přístup** zkopírujte hodnotu **Kód pro překonání zámku aktivace**.

    >[!NOTE]
    >Před vymazáním zařízení si kód zkopírujte. Když nastavení zařízení obnovíte před zkopírováním kódu, kód se z Azure odebere.

7.  Přejděte do okna zařízení **Přehled** a pak vyberte **Vymazat**.
8.  Jakmile se zařízení obnoví, zobrazí se výzva k zadání *Apple ID* a *hesla*. Pole *ID* nechte prázdné a jako *heslo* zadejte **kód pro překonání zámku**. Tímto se účet odebere ze zařízení. 


## <a name="next-steps"></a>Další postup

Stav požadavku na odemčení můžete zkontrolovat na stránce podrobností pro dané zařízení v úloze **Spravovat zařízení**.
