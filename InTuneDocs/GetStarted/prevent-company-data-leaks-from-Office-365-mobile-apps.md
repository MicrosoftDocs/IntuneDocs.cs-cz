---
title: "Prevence úniků firemních dat z mobilních aplikací Office 365 | Microsoft Intune"
description: "Intune můžete použít k zabezpečení dat organizace prostřednictvím zásad správy mobilních aplikací (MAM), které brání jejich úniku z mobilních aplikací Office 365 nebo z jiných obchodních aplikací (LOB)."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 10/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 84faafafb531f0f3599a2b0d81a4123c930852ec
ms.openlocfilehash: e9ed47a6ced12f800bb5e75bc73d5404a9d5cbc0


---

# Úvodní příručka: Prevence úniků firemních dat z mobilních aplikací Office 365
Microsoft Intune může přispět k zabezpečení dat vaší organizace pomocí zásad správy mobilních aplikací (MAM), které zvyšují ochranu proti únikům firemních dat z mobilních aplikací Office 365 nebo jiných obchodních aplikací (LOB). Zásady MAM v Intune je možné použít, aniž by si koncoví uživatelé museli svá zařízení zaregistrovat ve správě mobilních zařízení (MDM) Intune. Takže pokud se vyskytnou uživatelé, kteří si nebudou chtít svá mobilní zařízení (BYOD) s iOS nebo Androidem zaregistrovat do řešení Microsoft MDM (Intune, Configuration Manager nebo EAS), pokud chcete firemní data chránit bez správy zařízení koncových uživatelů nebo pokud už používáte jiné řešení než Microsoft MDM, pak vám Intune může pomoct zvýšit zabezpečení firemních dat.   

## Je tato úvodní příručka pro mě to pravé?
Chcete koncovým uživatelům umožnit přístup k datům aplikací Office 365 a obchodních aplikací na zařízeních s iOS a Androidem bez nutnosti jejich registrace v řešení správy mobilních zařízení (MDM), ale i tak si udržet kontrolu nad tím, co můžou nebo nemůžou s daty dělat, například jestli si je můžou zkopírovat do osobních aplikací?

Pokud ano, Microsoft Intune vám umožní nastavit zásady MAM pro mobilní aplikace Office 365 v iOS a Androidu, včetně omezení pro vyjmutí, kopírování a vkládání, deaktivace funkce Uložit jako, nastavení požadavků na kódy PIN a možnosti vzdáleně vymazat data chráněná přes MAM.  Tím se zajistí ochrana firemních dat, aniž by uživatelé museli zaregistrovat svá zařízení do řešení MDM a současně se zachová skvělé prostředí pro koncové uživatele s mobilními aplikacemi pro Office.

## Jak to udělám?
1.  Získejte základní povědomí o tom, [jak správa mobilních aplikací (MAM) v Intune funguje](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).
2.  Zjistěte, [co je třeba udělat před vytvořením zásad MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) na Portálu Azure.
3.  [Vytvořte a nasaďte zásady MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) pomocí Intune.

### Další informace:
- [Prostředí pro koncové uživatele](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) v aplikacích s aktivovanou správou mobilních aplikací (MAM)
- [Příprava obchodních aplikací pro MAM s Intune](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners" target="_blank"> Seznam partnerů nabízejících aplikace pro Microsoft Intune &rarr;</a> poskytování aplikací aktivovaných pro MAM

## Co dalšího mám udělat?
[Migrace z řešení MDM od jiného poskytovatele než Microsoftu do Microsoft Intune](/intune/deploy-use/migrate-to-intune)

[Registrace zařízení v MDM Intune](/intune/deploy-use/enroll-devices-in-microsoft-intune)



<!--HONumber=Oct16_HO3-->


