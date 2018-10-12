---
title: Podmíněný přístup s Microsoft Intune
titlesuffix: ''
description: Přečtěte si, jak se podmíněný přístup Intune běžně používá pro podmíněný přístup podle zařízení a aplikace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: db63d79a81de03a459a910a23fb9f999f33f0251
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231646"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Jaké jsou běžné způsoby používání podmíněného přístupu s Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Existují dva typy podmíněného přístupu s Intune: podmíněný přístup podle zařízení a podle aplikace. K zavedení dodržování předpisů podmíněného přístupu ve vaší organizaci musíte nakonfigurovat související zásady dodržování předpisů. Podmíněný přístup se běžně používá k provádění akcí, jako je povolení nebo blokování přístupu k místnímu Exchangi, řízení přístupu k síti nebo integraci s řešením Mobile Threat Defense.

Níže uvedené informace objasňují, jak se používají možnosti dodržování předpisů mobilními *zařízeními* Intune a možnosti správy mobilních *aplikací* (MAM) Intune. 

> [!NOTE]
> Podmíněný přístup je funkce Azure Active Directory, která je zahrnutá v licenci pro Azure Active Directory Premium. Intune tuto funkci vylepšuje tím, že do řešení přidává dodržování předpisů pro mobilní zařízení a správu mobilních aplikací.

## <a name="device-based-conditional-access"></a>Podmíněný přístup podle zařízení

Intune a Azure Active Directory spolupracují a zajišťují, aby přístup k e-mailu, službám Office 365, aplikacím softwaru jako služby (SaaS) a [místním aplikacím](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) měla jen spravovaná zařízení dodržující předpisy. Navíc můžete v Azure Active Directory nastavit zásadu, aby přístup ke službám Office 365 měly jen počítače, které jsou připojené k doméně, nebo mobilní zařízení, která jsou zaregistrovaná v Intune.

Intune poskytuje schopnosti zásad dodržování předpisů pro zařízení, které vyhodnocují stav dodržování předpisů ze strany zařízení. Stav dodržování předpisů se oznamuje službě Azure Active Directory, která ho využívá k vynucení zásady podmíněného přístupu vytvořené v Azure Active Directory, když se uživatel pokusí získat přístup k firemním prostředkům.

Zásady podmíněného přístupu na základě zařízení pro Exchange Online a další produkty Office 365 se konfigurují prostřednictvím portálu [Azure Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

-   Přečtěte si další informace o [podmíněném přístupu v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   Přečtěte si další informace o [dodržování předpisů zařízením v Intune](device-compliance.md).

-   Přečtěte si další informace o [ochraně e-mailu, Office 365 a dalších služeb pomocí podmíněného přístupu v Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

> [!NOTE]
> Pokud na zařízeních s Androidem povolíte přístup na základě zařízení pro Sharepoint Online, je nutné, aby uživatelé na zaregistrovaném zařízení povolili možnost **Povolit přístup z prohlížeče** následujícím způsobem:
> 1. Spusťte **aplikaci Portál společnosti**.
> 2. Přejděte na stránku **Nastavení** prostřednictvím tlačítka se třemi tečkami (...) nebo hardwarového tlačítka nabídky.
> 3. Stiskněte tlačítko **Povolit přístup z prohlížeče**. 
> 4. V prohlížeči Chrome se odhlaste z Office 365 a znovu spusťte Chrome.

### <a name="conditional-access-for-exchange-on-premises"></a>Podmíněný přístup pro místní Exchange

Pomocí podmíněného přístupu můžete na základě zásad dodržování předpisů a stavu registrace zařízení povolit nebo zablokovat přístup k **místnímu Exchangi**. Když zásady podmíněného přístupu použijete v kombinaci se zásadami dodržování předpisů zařízením, povolí se přístup k místnímu Exchangi jen zařízením dodržujícím předpisy.

V podmíněném přístupu můžete nakonfigurovat upřesňující nastavení pro podrobnější řízení, třeba:

-   Povolit nebo zakázat určité platformy

-   Okamžitě zablokovat zařízení, která nespravuje Intune

Při použití zásad dodržování předpisů zařízením a podmíněného přístupu se u všech zařízení používaných pro přístup k místnímu Exchangi kontroluje dodržování předpisů.

Pokud zařízení nesplňuje stanovené podmínky, je koncový uživatel proveden procesem jeho registrace a vyřešení problému, kvůli kterému zařízení nedodržuje předpisy.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Jak podmíněný přístup pro místní Exchange funguje

Konektor Intune Exchange si vyžádá všechny záznamy Exchange Active Sync (EAS), které existují na serveru Exchange, aby Intune mohl tyto záznamy EAS namapovat na záznamy zařízení Intune. Tyto záznamy jsou zařízení zaregistrovaná a rozpoznaná službou Intune. Tento proces povolí nebo zablokuje přístup k e-mailu.

Pokud je záznam EAS zcela nový a Intune o něm neví, vydá Intune rutinu, která zablokuje přístup k e-mailu. Tady jsou další podrobnosti o tom, jak tento proces funguje:

![Vývojový diagram místního Exchange s podmíněným přístupem](./media/ca-intune-common-ways-1.png)

1.  Uživatel se pokusí o přístup k podnikovému e-mailu, který je hostovaný na místním Exchangi 2010 SP1 nebo novějším.

2.  Pokud zařízení nespravuje Intune, bude mít zablokovaný přístup k e-mailu. Intune odešle oznámení o zablokování klientovi EAS.

3.  EAS obdrží oznámení o zablokování, přesune zařízení do karantény a odešle e-mail o karanténě s kroky k nápravě obsahující odkazy, aby uživatelé mohli svá zařízení zaregistrovat.

4.  Provede se proces připojení k pracovišti, který je prvním krokem k tomu, aby se zařízení spravovalo pomocí Intune.

5.  Zařízení se zaregistruje v Intune.

6.  Intune namapuje záznam EAS na záznam zařízení a uloží stav dodržování předpisů zařízením.

7.  ID klienta EAS se zaregistruje prostřednictvím procesu registrace zařízení Azure AD. Tím se vytvoří vztah mezi záznamem zařízení v Intune a ID klienta EAS.

8.  Registrace zařízení Azure AD uloží informace o stavu zařízení.

9.  Pokud uživatel splňuje zásady podmíněného přístupu, Intune prostřednictvím konektoru Intune Exchange vydá rutinu, která umožní synchronizaci poštovní schránky.

10. Server Exchange odešle oznámení klientovi EAS, aby uživatel získal přístup k e-mailu.

#### <a name="whats-the-intune-role"></a>Jaká je role Intune?

Intune vyhodnocuje a spravuje stav zařízení.

#### <a name="whats-the-exchange-server-role"></a>Jaká je role serveru Exchange?

Server Exchange poskytuje rozhraní API a infrastrukturu pro přesun zařízení do jeho karantény.

> [!IMPORTANT]
> Mějte na paměti, že uživatel, který zařízení používá, musí mít přiřazený profil dodržování předpisů, aby se dodržování předpisů zařízením vyhodnocovalo. Pokud uživatel nemá nasazené žádné zásady dodržování předpisů, považuje se zařízení za dodržující předpisy a žádná omezení přístupu se neuplatní.

### <a name="conditional-access-based-on-network-access-control"></a>Podmíněný přístup na základě řízení přístupu k síti

Intune je integrovaný s partnery jako Cisco ISE, Aruba Clear Pass a Citrix NetScaler k poskytování řízení přístupu na základě registrace v Intune a stavu dodržování předpisů zařízením.

Uživatelům se může při pokusu o přístup k podnikové síti Wi-Fi nebo prostředkům VPN přístup povolit nebo odepřít v závislosti na tom, jestli je zařízení spravované a splňuje zásady Intune ohledně dodržování předpisů zařízením.

-   Další informace o[integraci NAC s Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Podmíněný přístup na základě rizika zařízení

Intune ve spolupráci s dodavateli služeb Mobile Threat Defense poskytuje řešení zabezpečení pro zjišťování malwaru, trojských koňů a dalších hrozeb na mobilních zařízeních.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Jak funguje integrace Intune s ochranou před mobilními hrozbami

Když mají mobilní zařízení nainstalovaného agenta pro ochranu před mobilními hrozbami, může agent odesílat zprávy o stavu dodržování předpisů zpět do Intune a hlásit, jestli byla v samotném mobilním zařízení nalezena hrozba.

Integrace Intune a ochrany před mobilními hrozbami hraje roli při rozhodování podmíněného přístupu na základě rizika zařízení.

-   Přečtěte si další informace o [Intune Mobile Threat Defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).

### <a name="conditional-access-for-windows-pcs"></a>Podmíněný přístup pro počítače s Windows

Podmíněný přístup pro počítače poskytuje podobné možnosti jako pro mobilní zařízení. Nyní se seznámíme se způsoby použití podmíněného přístupu při správě počítačů s Intune.

#### <a name="corporate-owned"></a>Ve vlastnictví firmy

-   **Připojení k místní doméně AD:** Tuto možnost běžně používají organizace, kterým vyhovuje, jak už svoje počítače spravují prostřednictvím zásad skupiny AD nebo System Center Configuration Manageru.

-   **Připojení k doméně Azure AD a správa prostřednictvím Intune:** Tento scénář je typický pro výběr vlastního zařízení (CYOD: Choose Your Own Device) a scénáře přenosných počítačů, kdy jsou tato zařízení zřídka připojená k podnikové síti. Zařízení se připojí k Azure AD a zaregistruje v Intune, čímž se odeberou všechny závislosti na místním AD a řadičích domény. To se dá využít jako kritérium podmíněného přístupu při přístupu k podnikovým prostředkům.

-   **Připojení k doméně AD a System Center Configuration Manager:** Od aktuální větve System Center Configuration Manager poskytuje možnosti podmíněného přístupu, které můžou vyhodnocovat konkrétní kritéria dodržování předpisů, vedle toho, že je počítač připojený k doméně:

    -   Je počítač zašifrovaný?

    -   Je nainstalovaný malware? Je aktuální?

    -   Byl na zařízení proveden jailbreak nebo root?

#### <a name="bring-your-own-device-byod"></a>Přineste si vlastní zařízení (BYOD)

-   **Připojení k pracovišti a správa prostřednictvím Intune:** V tomto případě může uživatel připojit svoje osobní zařízení pro přístup k podnikovým prostředkům a službám. Můžete použít připojení k pracovišti a zaregistrovat zařízení v Intune pro přijímání zásad na úrovni zařízení, což je také další možnost pro vyhodnocování kritérií podmíněného přístupu.

## <a name="app-based-conditional-access"></a>Podmíněný přístup založený na aplikacích

Intune a Azure Active Directory společně zajišťují, aby přístup k podnikovému e-mailu nebo jiným službám Office 365 měly jenom spravované aplikace.

-   Přečtěte si další informace o [podmíněném přístupu založeném na aplikacích s Intune](app-based-conditional-access-intune.md).

## <a name="next-steps"></a>Další kroky

[Jak nakonfigurovat podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Jak nainstalovat místní konektor Exchange v Intune](https://docs.microsoft.com/intune/exchange-connector-install)

[Jak vytvořit zásadu podmíněného přístupu pro místní Exchange](conditional-access-exchange-create.md)
