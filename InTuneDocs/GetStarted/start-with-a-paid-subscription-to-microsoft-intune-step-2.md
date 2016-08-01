---
title: "Konfigurace vlastního názvu domény | Microsoft Intune"
description: "Popisuje postup přidání názvu vlastní domény pro vaše předplatné Intune."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: f18afc5487fe20ba4a13d938dad78fa6087128d7


---


# Konfigurace vlastního názvu domény

Standardně Intune používá název domény **<domain>.onmicrosoft.com**, který byl vytvořený při prvním přihlášení k službě. Pokud má vaše organizace vlastní doménu, můžete instanci Intune nakonfigurovat tak, aby místo názvu domény poskytnutého s vaším předplatným používala tuto doménu.

Než vytvoříte nové uživatelské účty nebo synchronizujete účty z místní služby Active Directory, důrazně doporučujeme, abyste se rozhodli, jestli chcete používat jenom doménu .onmicrosoft.com, nebo jestli chcete přidat jeden nebo víc názvů vlastních domén. Konfigurace vlastní domény před přidáním uživatelů může zjednodušit správu identit uživatelů ve vašem předplatném, protože se uživatelé budou moct přihlašovat pomocí přihlašovacích údajů, které používají pro přístup k jiným prostředkům domény.

Když se přihlásíte k odběru cloudové služby od Microsoftu, stane se instance této služby [tenantem služby Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), která bude vašim cloudovým službám poskytovat identitu a adresářové služby. Vzhledem k tomu, že postup konfigurace Intune pro používání vlastního názvu domény vaší organizace je stejný jako u jiných tenantů Azure AD, můžete použít informace a postupy uvedené v tématu [Přidání domény](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Další informace o používání vlastní domény s cloudovou službou od Microsoftu najdete v tématu věnovaném [koncepčnímu přehled vlastních názvů domén v Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Další kroky
Gratulujeme! Právě jste dokončili krok 2 *úvodní příručky Intune*.

>[!div class="step-by-step"]

>[&larr; **Přihlášení k Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Přidání uživatelů do Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO3-->


