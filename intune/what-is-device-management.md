---
title: Správa zařízení v Microsoft 365
description: Součástí Microsoft 365 Enterprise je Microsoft Intune. Zjistěte, jak Intune poskytuje správu mobilních zařízení a správu mobilních aplikací pro organizaci, včetně běžných scénářů a použití Intune k nasazení Microsoft 365 ve vašem prostředí.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/29/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea24101600c7a0e485440f50fc043c14bd840968
ms.sourcegitcommit: 8e6f4acb592dbe5de63aa7642ee9487288740714
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2019
ms.locfileid: "58646484"
---
# <a name="what-is-device-management"></a>Co je správa zařízení? 

Hlavní úlohou každého správce je ochrana a zabezpečení prostředků a dat příslušné organizace. Tato úloha je *správy zařízení*. Uživatelé mají mnoho zařízení, na kterých otevírají a sdílejí osobní soubory, navštěvují weby a instalují aplikace a hry. Titíž uživatelé jsou také zaměstnanci a studenti a chtějí pomocí svých zařízení přistupovat k pracovním a školním prostředkům, jako jsou e-mail a OneNote. Správa zařízení umožňuje organizacím chránit a zabezpečit svoje prostředky a data. 

Pomocí poskytovatele správy zařízení můžou organizace zajistit, aby přístup k vlastnickým informacím měli jenom autorizovaní jednotlivci a zařízení. Obdobně také uživatelé zařízení můžou být při přístupu k pracovním datům ze svého telefonu klidní, protože vědí, že jejich zařízení splňuje požadavky organizace na zabezpečení. Jako zástupci organizace si možná kladete otázku: **Jaký produkt máme k ochraně našich prostředků použít?**

Odpovědí může být [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Intune nabízí správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). K hlavním úlohám řešení MDM nebo MAM patří:

- Podpora různých mobilních prostředí – bezpečná správa zařízení se systémy iOS, Android, Windows a macOS
- Zajištění, aby zařízení a aplikace splňovaly požadavky organizace na zabezpečení
- Vytvoření zásad, které pomůžou udržovat data organizace na firemních a osobních zařízeních v bezpečí
- Použití jediného unifikovaného mobilního řešení k vynucení těchto zásad a usnadnění správy zařízení, aplikací, uživatelů a skupin

Intune je součástí Microsoft 365 a integruje se s Azure Active Directory (Azure AD). Azure AD pomáhá řídit, kdo má přístup a k čemu má přístup.

## <a name="hello-intune"></a>Seznámení s Intune
Řada organizací, například Microsoft, používá Intune k zabezpečení vlastnických dat, ke kterým uživatelé přistupují ze svých firemních a osobních mobilních zařízení. Intune obsahuje funkce, které vám pomůžou zabezpečit a monitorovat přístup k datům, například zásady konfigurace zařízení a aplikací, zásady aktualizace softwaru a stavy instalace (a také grafy, tabulky a sestavy).

Je běžné, že lidé mají několik zařízení, která používají různé platformy. Zaměstnanec může například pro práci používat Surface Pro a pro soukromé účely mobilní zařízení s Androidem. A je běžné, že tato osoba z obou uvedených zařízení přistupuje k prostředkům organizace, jako jsou například Microsoft Outlook a SharePoint.

Pomocí Intune můžete spravovat více zařízení pro každou osobu a různé platformy, které běží na jednotlivých zařízeních, například iOS, macOS, Android a Windows. Intune odděluje zásady a nastavení podle platformy zařízení, takže lze snadno spravovat a zobrazit zařízení s určitou platformou.

**[Typické scénáře](https://docs.microsoft.com/intune/common-scenarios)** jsou výborným zdrojem informací o tom, jak se v Intune řeší běžné situace při práci s mobilními zařízeními. Najdete zde scénáře pro tyto oblasti:  
- Ochrana e-mailu pomocí místního Exchange
- Bezpečný přístup k Office 365
- Použití osobních zařízení pro přístup k prostředkům organizace

## <a name="integration-with-secure-and-protect-services"></a>Integrace se službami zabezpečení a ochrany
Hlavní úlohou řešení správy zařízení je poskytování zabezpečení a ochrany. Intune k plnění této úlohy skvěle využívá integraci s dalšími službami. Příklad:

- **Microsoft 365** je hlavní komponentou pro zjednodušení běžných úloh IT. Pomocí centra pro správu Microsoft 365 můžete vytvářet uživatele, spravovat skupiny a získat přístup k dalším službám, jako jsou například Intune, Azure Active Directory a další. V Microsoft 365 můžete například vytvořit skupinu zařízení s iOSem. Potom pomocí Intune odešlete této skupině zařízení s iOSem zásady týkající se funkcí iOSu, jako jsou například přístup do App Storu, použití AirDropu, zálohování v iCloudu, použití webového filtru Apple a další.

- **Windows Defender** obsahuje mnoho funkcí zabezpečení, které usnadňují ochranu zařízení s Windows 10. Při společném použití Intune a programu Windows Defender můžete například: 

    - Povolit, aby [filtr SmartScreen v programu Windows Defender](https://docs.microsoft.com/intune/endpoint-protection-windows-10) hledal podezřelou aktivitu souborů a aplikací na mobilních zařízeních 
    - Použít [Rozšířenou ochranu před internetovými útoky v programu Windows Defender](https://docs.microsoft.com/intune/advanced-threat-protection) k tomu, aby zabraňovala porušením zabezpečení na mobilních zařízeních a pomáhala omezit dopad porušení zabezpečení zablokováním přístupu příslušného uživatele k podnikovým prostředkům

- **Podmíněný přístup** je funkce Azure Active Directory, která se dobře integruje s Intune. Pomocí [podmíněného přístupu](https://docs.microsoft.com/intune/conditional-access) můžete zajistit, aby přístup k e-mailu, SharePointu a jiným aplikacím měla jenom zařízení dodržující předpisy. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Výběr správného řešení pro správu zařízení

Existuje několik způsobů přístupu ke správě zařízení. U prvního způsobu můžete spravovat všechny aspekty zařízení pomocí všech funkcí, které jsou integrované do Intune. Tato možnost se nazývá **správa mobilních zařízení (MDM)**. Při použití tohoto způsobu si uživatelé „zaregistrují“ svoje zařízení a ke komunikaci s Intune používají certifikáty. Jako správce IT můžete distribuovat aplikace na zařízení, omezovat zařízení pro určitý operační systém, blokovat osobní zařízení a provádět další akce. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete také odebrat všechna data ze zařízení. 

U druhého způsobu spravujete aplikace na zařízeních. Tato možnost se nazývá **správa mobilních aplikací (MAM)**. Při použití tohoto způsobu můžou uživatelé přistupovat k prostředkům organizace pomocí svých osobních zařízení. Při otevření aplikace, jako je e-mail nebo SharePoint, se uživatelům zobrazí výzva k dalšímu ověření. Pokud dojde ke ztrátě nebo odcizení zařízení, můžete odebrat všechna data organizace ze zařízení. 

Můžete také použít společně kombinaci [MDM a MAM](https://docs.microsoft.com/intune/byod-technology-decisions).

Při nastavení Intune se také rozhodujete, jestli ke správě zařízení budete používat výhradně Azure Portal, nebo společně Intune a Microsoft 365. Přečtěte si, jak v Microsoft IT zvolili moderní přístup ke správě zařízení a jaké poznatky v tomto procesu získali, v případové studii Microsoft IT o [migraci správy mobilních zařízení do Intune na webu Azure Portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal). 

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
Až budete připraveni začít s řešením MDM nebo MAM a budete chtít provést různé kroky nastavení Intune, zaregistrovat zařízení a začít vytvářet zásady, přejděte k tématu [Správa mobilních zařízení pro Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure). 
