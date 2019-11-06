---
title: Povolení konektoru ochrany před mobilními hrozbami pro neregistrovaná zařízení
titleSuffix: Microsoft Intune
description: Povolte pro neregistrovaná zařízení konektor ochrany před mobilními hrozbami v Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2744a27a733824bab9d920f4de0b49e951c1c34
ms.sourcegitcommit: a4c7339ec9ff5b1b846cb3cca887cf91b5cd4baa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627640"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Povolení konektoru ochrany před mobilními hrozbami v Intune pro neregistrovaná zařízení

Při instalaci ochrany před mobilními hrozbami (MTD) jste nakonfigurovali zásadu pro klasifikaci hrozeb v konzole partnerského serveru ochrany před mobilními hrozbami a v Intune jste vytvořili zásady ochrany aplikací. Pokud jste už konektor Intune nakonfigurovali v konzole pro partnery MTD, můžete teď povolit připojení MTD pro partnerské aplikace MTD.

> [!NOTE] 
> Tento článek se týká všech partnerů ochrany před mobilními hrozbami, které podporují zásady ochrany aplikací: lepší mobilní zařízení (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Nastavení** zvolte **Mobile Threat Defense**.

3. V podokně **Mobile Threat Defense** zvolte **Přidat**.

4. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Povolte možnosti přepínání podle požadavků vaší organizace. Viditelnost možností přepínání se bude lišit v závislosti na partnerovi MTD.

## <a name="mtd-toggle-options"></a>Možnosti přepínání MTD

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

**Nastavení zásad ochrany aplikací**
- **Připojit zařízení s Androidem verze 4,4 a novější pro *\<název partnera MTD >* pro vyhodnocení zásad ochrany aplikací**: když tuto možnost povolíte, zásady ochrany aplikací pomocí pravidla úrovně hrozby zařízení vyhodnotí zařízení, včetně data z tohoto konektoru.
- **Připojit zařízení s iOS verze 11 a vyšší, aby *\<MTD název partnera >* pro vyhodnocení zásad ochrany aplikací**: když tuto možnost povolíte, zásady ochrany aplikací pomocí pravidla úrovně hrozeb pro zařízení vyhodnotí zařízení, která budou zahrnovat data z Tento konektor.

**Společné sdílené nastavení**
- **Počet dnů, než partner přestane reagovat**: Počet dnů nečinnosti, než bude Intune kvůli ztrátě připojení považovat partnera za nereagujícího. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.

> [!NOTE] 
> Když povolíte připojení ochrany před mobilními hrozbami do Intune, vytvoří Intune v Azure Active Directory klasické zásady podmíněného přístupu. Každá aplikace MTD, kterou integrujete, včetně [ATP ATP](advanced-threat-protection.md) nebo kteréhokoli z našich dalších [partnerů MTD](mobile-threat-defense.md#mobile-threat-defense-partners), vytvoří nové zásady podmíněného přístupu v klasickém rozhraní. **Tyto zásady je možné ignorovat, ale neměly by být upravované, odstraňující ani zakázané.**
> 
> Klasické zásady podmíněného přístupu pro aplikace MTD: 
> - Používají Intune MTD k tomu, aby vyžadovaly, aby byla zařízení zaregistrovaná ve službě Azure AD, aby měla ID zařízení před komunikací s partnery MTD. IDENTIFIKÁTOR je povinný, aby zařízení a mohl úspěšně ohlásit svůj stav do Intune.  
> - Nemusíte mít žádný vliv na žádné jiné cloudové aplikace ani prostředky.  
> - Liší se od zásad podmíněného přístupu, které byste mohli vytvořit, abyste mohli lépe spravovat MTD nebo vyžadovat certifikační autoritu aplikace App Protection.
> - Ve výchozím nastavení nekomunikujete s dalšími zásadami podmíněného přístupu, které používáte pro vyhodnocení.  
>
> Pokud chcete zobrazit klasické zásady podmíněného přístupu, přejděte v [Azure](https://portal.azure.com/#home)na **Azure Active Directory** > **podmíněný přístup** > **Classic**.

## <a name="next-steps"></a>Další kroky

- [Vytvořte zásady ochrany aplikací ochrany před mobilními hrozbami (MTD) v Intune](~/protect/mtd-app-protection-policy.md).
