---
title: "Prevence úniků firemních dat z mobilních aplikací Office 365"
description: "Intune můžete použít k zabezpečení dat organizace prostřednictvím zásad správy mobilních aplikací (MAM), které brání jejich úniku z mobilních aplikací Office 365 nebo z jiných obchodních aplikací (LOB)."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 40356d01be1d436e2a7fc0598ebac0d25749a49a
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Úvodní příručka: Prevence úniků firemních dat z mobilních aplikací Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune může přispět k zabezpečení dat vaší organizace pomocí zásad správy mobilních aplikací (MAM), které zvyšují ochranu proti únikům firemních dat z mobilních aplikací Office 365 nebo jiných obchodních aplikací (LOB). Zásady MAM v Intune je možné použít, aniž by si koncoví uživatelé museli svá zařízení zaregistrovat ve správě mobilních zařízení (MDM) Intune. Takže pokud se vyskytnou uživatelé, kteří si nebudou chtít svá mobilní zařízení (BYOD) s iOSem nebo Androidem zaregistrovat do řešení Microsoft MDM (Intune, Configuration Manager nebo EAS), pokud chcete firemní data chránit bez správy zařízení koncových uživatelů nebo pokud už používáte jiné řešení než Microsoft MDM, pak vám Intune může pomoct zvýšit zabezpečení firemních dat.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Je tato úvodní příručka pro mě to pravé?
Chcete koncovým uživatelům umožnit přístup k datům aplikací Office 365 a obchodních aplikací na zařízeních s iOSem a Androidem bez nutnosti jejich registrace v řešení správy mobilních zařízení (MDM), ale i tak si udržet kontrolu nad tím, co můžou nebo nemůžou s daty dělat, například jestli si je můžou zkopírovat do osobních aplikací?

Pokud ano, Microsoft Intune vám umožní nastavit zásady MAM pro mobilní aplikace Office 365 v iOSu a Androidu, včetně omezení pro vyjmutí, kopírování a vkládání, deaktivace funkce Uložit jako, nastavení požadavků na kódy PIN a možnosti vzdáleně vymazat data chráněná přes MAM.  Tím se zajistí ochrana firemních dat, aniž by uživatelé museli zaregistrovat svá zařízení do řešení MDM a současně se zachová skvělé prostředí pro koncové uživatele s mobilními aplikacemi pro Office.

## <a name="how-do-i-do-it"></a>Jak to udělám?
1.  Získejte základní povědomí o tom, [jak správa mobilních aplikací (MAM) v Intune funguje](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.  Zjistěte, [co je třeba udělat před vytvořením zásad MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) na portálu Azure Portal.
3.  [Vytvořte a nasaďte zásady MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) pomocí Intune.

### <a name="additional-information"></a>Další informace:
- [Prostředí pro koncové uživatele](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) v aplikacích s aktivovanou správou mobilních aplikací (MAM)
- [Příprava obchodních aplikací pro MAM s Intune](/intune/apps-prepare-mobile-application-management)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank">Seznam partnerů nabízejících aplikace pro Microsoft Intune k &rarr;</a> poskytování aplikací aktivovaných pro MAM

## <a name="what-should-i-do-next"></a>Co dalšího mám udělat?
[Migrace z řešení MDM od jiného poskytovatele než Microsoftu do Microsoft Intune](/intune-classic/deploy-use/migrate-to-intune)

[Registrace zařízení v MDM Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
