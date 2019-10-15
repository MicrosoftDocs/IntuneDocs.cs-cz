---
title: Správa zařízení v Microsoft 365
description: Microsoft 365 Enterprise obsahuje Microsoft Intune. Podívejte se, jak Intune zajišťuje správu mobilních zařízení a správu mobilních aplikací pro vaši organizaci. Čtení běžných scénářů a použití Intune k nasazení Microsoft 365 ve vašem prostředí.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/14/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93d8107d235d9f13af487bba4cbf6a71fc92eeab
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314545"
---
# <a name="device-management-overview"></a>Přehled správy zařízení

Klíčovou úlohou libovolného správce je ochrana a zabezpečení prostředků a dat organizace. Tato úloha je *Správa zařízení*. Uživatelé mají mnoho zařízení, kde otevřou a sdílejí osobní soubory, navštíví weby a instalují aplikace a hry. Tito uživatelé jsou také zaměstnanci a studenti. Chtějí používat svoje zařízení pro přístup k pracovním a školním prostředkům, jako je e-mail a OneNote.

Správa zařízení umožňuje organizacím chránit a zabezpečovat své prostředky a data a z různých zařízení.

Díky poskytovateli správy zařízení může organizace zajistit, aby přístup k proprietárním informacím měli jenom oprávnění lidé a zařízení. Podobně se uživatelé zařízení můžou rozpracovat na práci s pracovními daty z telefonu, protože ví, že jejich zařízení splňuje požadavky organizace na zabezpečení. Jako organizace se můžete zeptat, **co by mělo používat k ochraně našich prostředků?**

Odpověď je [Microsoft Intune](what-is-intune.md). Intune nabízí správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). Mezi klíčové úlohy libovolného řešení MDM nebo MAM patří:

- Podporují nejrůznější mobilní prostředí a bezpečně spravují zařízení s iOS, Androidem, Windows a macOS.
- Ujistěte se, že zařízení a aplikace vyhovují požadavkům na zabezpečení vaší organizace.
- Vytvořte zásady, které pomůžou zabezpečit data vaší organizace v bezpečí na zařízeních vlastněných organizací a osobním zařízením.
- Pomocí jediného sjednoceného mobilního řešení vyvynuťte tyto zásady a pomůžou vám spravovat zařízení, aplikace, uživatele a skupiny.
- Chraňte své firemní informace tím, že vám pomohou řídit způsob, jakým vaše zaměstnanci přistupují k datům a sdílí je.

Intune je součástí Microsoft Azure, Microsoft 365 a integruje se s Azure Active Directory (Azure AD). Azure AD pomáhá řídit, kdo má přístup a k čemu mají přístup.

## <a name="microsoft-intune"></a>Microsoft Intune

Mnoho organizací, jako je Microsoft, používá Intune k zabezpečení vlastních dat, ke kterým uživatelé přistupují z vlastních mobilních zařízení, která vlastní společnost. Intune zahrnuje zásady konfigurace zařízení a aplikací, zásady aktualizace softwaru a stavy instalace (grafy, tabulky a sestavy), které vám pomůžou zabezpečit a monitorovat přístup k datům.

Pro lidi je běžné, že mají několik zařízení, která používají různé platformy. Zaměstnanec může například použít Surface for Work a mobilní zařízení s Androidem v jejich osobním životě. A je běžné, že osoba má přístup k prostředkům organizace, jako je například Microsoft Outlook a SharePoint, z těchto více zařízení.

S Intune můžete spravovat víc zařízení na osobu a na různých platformách, které se na jednotlivých zařízeních spouštějí, včetně iOS, macOS, Androidu a Windows. Intune odděluje zásady a nastavení podle platformy zařízení. Proto je snadné spravovat a zobrazovat zařízení konkrétní platformy.

**[Běžnými scénáři](common-scenarios.md)** je skvělý prostředek, který vám umožní zjistit, jak Intune odpovídá na časté otázky při práci s mobilními zařízeními. Scénáře najdete v těchto scénářích:  

- Ochrana e-mailu s místním Exchangem
- Bezpečné a bezpečné získání přístupu k Office 365
- Použití osobních zařízení pro přístup k prostředkům organizace

Další informace o Intune najdete v tématu [co je Intune](what-is-intune.md).

## <a name="integration-with-secure-and-protect-services"></a>Integrace se službami zabezpečení a ochrany

Klíčovou úlohou řešení pro správu zařízení je poskytnutí zabezpečení a ochrany. Intune nabízí skvělou úlohu integrace s dalšími službami, aby bylo možné tuto úlohu dosáhnout. Například:

- **Microsoft 365** je klíčová komponenta pro zjednodušení běžných IT úloh. V centru pro správu Microsoft 365 vytváříte uživatele a spravujete skupiny. Získáte také přístup k dalším službám, jako je například Intune, Azure AD a další.

  Vytvořte například skupinu zařízení se systémem iOS v Microsoft 365. Pak použijte Intune k nabízení zásad do skupiny zařízení s iOS, které se zaměřují na funkce iOS, jako je například přístup k obchodu s aplikacemi, použití přetažení, zálohování na iCloud, použití webového filtru společnosti Apple a další.

- **Windows Defender** obsahuje mnoho funkcí zabezpečení, které vám pomůžou chránit zařízení s Windows 10. Například pomocí Intune a programu Windows Defender společně můžete:

  - Povolit [Filtr SmartScreen v programu Windows Defender](../protect/endpoint-protection-windows-10.md) a vyhledat podezřelé aktivity v souborech a aplikacích na mobilních zařízeních
  - Použití [rozšířené ochrany před internetovými útoky v programu Microsoft Defender (ATP)](../protect/advanced-threat-protection.md) k ochraně před narušením zabezpečení mobilních zařízení. A můžete tak omezit dopad porušení zabezpečení tím, že zablokujete uživatele z firemních prostředků.

- **Podmíněný přístup** je funkce Azure Active Directory a v Intune se v tomto případě integruje. Pomocí [podmíněného přístupu](../protect/conditional-access.md)zajistěte, aby přístup k e-mailu, SharePointu a dalším aplikacím umožňoval jenom vyhovující zařízení.

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Vyberte řešení pro správu zařízení, které je pro vás nejvhodnější.

Existuje několik způsobů, jak se připojit ke správě zařízení. Nejdřív můžete spravovat různé aspekty zařízení pomocí funkcí integrovaných do Intune. Tento přístup se nazývá **Správa mobilních zařízení (MDM)** . Uživatelé si zaregistrují svá zařízení a používají certifikáty ke komunikaci s Intune. Jako správce IT můžete nabízet aplikace na zařízeních, omezovat zařízení na konkrétní operační systém, blokovat osobní zařízení a další. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete také odebrat všechna data ze zařízení.

Ve druhém přístupu budete spravovat aplikace na zařízeních. Tento přístup se nazývá **Správa mobilních aplikací (MAM)** . Uživatelé můžou k přístupu k prostředkům organizace používat svoje osobní zařízení. Při otevírání aplikace, jako je e-mail nebo SharePoint, se uživatelům zobrazí výzva k dodatečnému ověření. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete ze zařízení odebrat všechna data organizace.

Můžete také použít kombinaci [MDM a mam](byod-technology-decisions.md) společně.

Při nastavování Intune se taky rozhodnete, že při správě zařízení budete pracovat výhradně v Azure Portal, nebo můžete pomocí Intune a Microsoft 365 společně spravovat zařízení. [Migrace správy mobilních zařízení do Intune v Azure Portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) je Případová studie Microsoftu. V takovém případě si prostudujte, jak Microsoft IT zvolí moderní přístup k správě zařízení, a přečtěte si získané lekce.

## <a name="simplify-it-tasks-using-the-device-management-admin-center"></a>Zjednodušení IT úloh pomocí centra pro správu správy zařízení

Centrum pro správu [správy zařízení](https://devicemanagement.microsoft.com/) je jedním z důvodů, jak spravovat a provádět úlohy pro vaše mobilní zařízení. Tento pracovní prostor zahrnuje služby používané pro správu zařízení, včetně Intune a Azure Active Directory, a také správu klientských aplikací.

V centru pro správu správy zařízení můžete:

- [Registrace zařízení](../enrollment/device-enrollment.md)
- [Nastavení dodržování předpisů zařízením](../protect/device-compliance-get-started.md)
- [Správa zařízení](../remote-actions/device-management.md)
- [Správa aplikací](../apps/app-management.md)  
- [e-knihy pro iOS](../apps/vpp-ebooks-ios.md)  
- [Nainstalovat konektor Exchange On-Premises Connector](../protect/exchange-connector-install.md)  
- [Správa rolí](role-based-access-control.md)  
- Spravovat aktualizace softwaru
  - [Správa aktualizací Windows 10](../protect/windows-update-for-business-configure.md)  
  - [Správa aktualizací pro iOS](../protect/software-updates-ios.md)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Správa uživatelů](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Správa skupin a členů](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Řešení problémů](help-desk-operators.md)

## <a name="next-steps"></a>Další kroky

Až budete připraveni začít s řešením MDM nebo MAM, Projděte si jednotlivé kroky k nastavení Intune, registraci zařízení a zahájení vytváření zásad. [Správa mobilních zařízení pro Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) je také skvělým prostředkem.
