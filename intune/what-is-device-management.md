---
title: Správa zařízení v Microsoft 365
description: Součástí Microsoft 365 Enterprise je Microsoft Intune. Podívejte se, jak Intune poskytuje správu mobilních zařízení a správy mobilních aplikací pro vaši organizaci. Běžné scénáře a použití Intune k nasazení služeb Microsoft 365 ve vašem prostředí.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/12/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5614f0657175658c1a8442d650e16c8550c1ac1
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043837"
---
# <a name="what-is-device-management"></a>Co je správa zařízení? 

Hlavní úlohou každého správce je ochrana a zabezpečení prostředků a dat příslušné organizace. Tato úloha je *správy zařízení*. Uživatelé mají velký počet zařízení, kde se otevřete a sdílet osobní soubory, navštivte weby a instalovat aplikace a hry. Tyto stejné uživatele jsou také zaměstnancům a studentům. Chtějí používat svá zařízení pro přístup k pracovní a školní prostředky, jako jsou e-mailu a OneNote. Správa zařízení umožňuje organizacím chránit a zabezpečit svoje prostředky a data. 

Použití zprostředkovatele správy zařízení, organizace zajistit, že jenom oprávnění lidé a zařízení získat přístup k vlastnické informace. Podobně uživatelé zařízení může být na usnadnění přístupu k pracovním datům ze svého telefonu, protože jejich zařízení vyhovět nárokům na zabezpečení organizace, které znají. Jako zástupci organizace si možná kladete otázku: **Jaký produkt máme k ochraně našich prostředků použít?**

Odpověď je [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Intune nabízí správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). K hlavním úlohám řešení MDM nebo MAM patří:

- Podpora různých mobilního prostředí a bezpečně spravovat zařízení iOS, Android, Windows a macOS.
- Zajistěte, aby zařízení a aplikace jsou kompatibilní s požadavky na zabezpečení vaší organizace.
- Vytvoření zásady, které pomůžou zabezpečit data organizace ve firemních a vlastních zařízeních.
- Použití jediného unifikovaného mobilního řešení k vynucení těchto zásad a usnadnění správy zařízení, aplikací, uživatelů a skupin

Intune je součástí Microsoft 365 a integruje se s Azure Active Directory (Azure AD). Azure AD pomáhá řídit, kdo má přístup a k čemu má přístup.

## <a name="hello-intune"></a>Seznámení s Intune
Řada organizací, například Microsoft, používá Intune k zabezpečení vlastnických dat, ke kterým uživatelé přistupují ze svých firemních a osobních mobilních zařízení. Intune obsahuje zásady Konfigurace zařízení a aplikací, zásady aktualizace softwaru a stav instalace (grafy, tabulky a sestavy) můžete zabezpečit a monitorovat přístup k datům.

Je běžné, že lidé mají několik zařízení, která používají různé platformy. Zaměstnanec může například pro práci používat Surface Pro a pro soukromé účely mobilní zařízení s Androidem. A je běžné, že tato osoba z obou uvedených zařízení přistupuje k prostředkům organizace, jako jsou například Microsoft Outlook a SharePoint.

Pomocí Intune můžete spravovat více zařízení pro každou osobu a různé platformy, které běží na jednotlivých zařízeních, například iOS, macOS, Android a Windows. Intune odděluje zásady a nastavení podle platformy zařízení. Takže je snadné správy a zobrazit zařízení pro konkrétní platformu.

**[Typické scénáře](https://docs.microsoft.com/intune/common-scenarios)** jsou výborným zdrojem informací o tom, jak se v Intune řeší běžné situace při práci s mobilními zařízeními. Najdete zde scénáře pro tyto oblasti:  
- Ochrana e-mailu pomocí místního Exchange
- Bezpečný přístup k Office 365
- Použití osobních zařízení pro přístup k prostředkům organizace

## <a name="integration-with-secure-and-protect-services"></a>Integrace se službami zabezpečení a ochrany
Hlavní úlohou řešení správy zařízení je poskytování zabezpečení a ochrany. Intune k plnění této úlohy skvěle využívá integraci s dalšími službami. Příklad:

- **Microsoft 365** je hlavní komponentou pro zjednodušení běžných úloh IT. V Centru pro správu služeb Microsoft 365 vytvořte uživatele a spravovat skupiny. Získáte také přístup k dalším službám, jako je například Intune, Azure AD a provádění dalších akcí. 

  Například vytvořte skupinu zařízení s Iosem v Microsoft 365. Potom pomocí Intune odešlete této skupině zařízení s iOSem zásady týkající se funkcí iOSu, jako jsou například přístup do App Storu, použití AirDropu, zálohování v iCloudu, použití webového filtru Apple a další.

- **Windows Defender** obsahuje mnoho funkcí zabezpečení, které usnadňují ochranu zařízení s Windows 10. Při společném použití Intune a programu Windows Defender můžete například: 

    - Povolit, aby [filtr SmartScreen v programu Windows Defender](https://docs.microsoft.com/intune/endpoint-protection-windows-10) hledal podezřelou aktivitu souborů a aplikací na mobilních zařízeních 
    - Použití [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) k porušením zabezpečení na mobilních zařízeních. A pomáhají omezit dopad těchto porušení zabezpečení zákonné zodpovědnosti organizací blokováním uživatelů k podnikovým prostředkům.

- **Podmíněný přístup** je funkce služby Azure Active Directory a hezky integrované ve službě Intune. Pomocí [podmíněného přístupu](https://docs.microsoft.com/intune/conditional-access), ujistěte se, že pouze povolí zařízením dodržujícím předpisy přístup k e-mailu, SharePoint a jinými aplikacemi. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Výběr správného řešení pro správu zařízení

Existuje několik způsobů přístupu ke správě zařízení. Nejprve můžete spravovat různé aspekty zařízení díky funkcím, které jsou integrované do Intune. Tento přístup se nazývá **správu mobilních zařízení (MDM)**. Uživatelé "zaregistrovat" svá zařízení a komunikovat s Intune používat certifikáty. Jako IT správce, nainstalovat aplikace na zařízení, omezení zařízení pro konkrétní operační systém, blokování osobních zařízení a další. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete také odebrat všechna data ze zařízení. 

U druhého způsobu spravujete aplikace na zařízeních. Tento přístup se nazývá **správy mobilních aplikací (MAM)**. Uživatele můžete použít svoje osobní zařízení pro přístup k prostředkům organizace. Při otevření aplikace, jako je e-mail nebo SharePoint, se uživatelům zobrazí výzva k dalšímu ověření. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete odebrat všechna data organizace ze zařízení. 

Můžete také použít společně kombinaci [MDM a MAM](https://docs.microsoft.com/intune/byod-technology-decisions).

Při nastavení Intune se také rozhodujete, jestli ke správě zařízení budete používat výhradně Azure Portal, nebo společně Intune a Microsoft 365. [Migrace správy mobilních zařízení do Intune na portálu Azure portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) je případovou studii – Microsoft IT. V tomto případě studie, zjistěte, jak Microsoft IT zvolili takový přístup ke správě moderních zařízení a přečtěte si, co jste se naučili.

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>Zjednodušení úloh IT pomocí řídicího panelu Správa zařízení

[Řídicí panel Správa zařízení](https://devicemanagement.portal.azure.com/) je univerzálním nástrojem pro správu a provádění úloh pro vaše mobilní zařízení. Součástí tohoto řídicího panelu jsou služby, které se používají ke správě zařízení, například Intune a Azure Active Directory, a také ke správě klientských aplikací. 

Na řídicím panelu Správa zařízení je možné provádět tyto činnosti:

- [Registrovat zařízení](https://docs.microsoft.com/intune/device-enrollment)
- [Nastavení dodržování předpisů zařízením](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Správa zařízení](https://docs.microsoft.com/intune/device-management)
- [Správa aplikací](https://docs.microsoft.com/intune/app-management)  
- [E-knihy pro iOS](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Instalace konektoru On-Premises Connector](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Správa rolí](https://docs.microsoft.com/intune/role-based-access-control)  
- Správa aktualizací softwaru
  - [Správa aktualizací Windows 10](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [Správa aktualizací iOSu](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Správa uživatelů](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Správa skupin a členů](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Řešení potíží](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Další krok
Až budete připravení začít s řešením MDM a MAM, provede jiný postup k nastavení Intune, registrace zařízení a začněte vytvářet zásady. [Správa mobilních zařízení pro Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) skvělým zdrojem je také.
