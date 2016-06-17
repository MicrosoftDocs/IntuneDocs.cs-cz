---
# required metadata

title: Synchronizace služby Active Directory a přidání uživatelů do Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Synchronizace služby Active Directory a přidání uživatelů do Intune
Můžete nakonfigurovat synchronizaci adresářů, aby se importovaly uživatelské účty z vaší místní služby Active Directory do Microsoft Azure Active Directory (Azure AD). Když máte místní službu Active Directory připojenou ke všem vašim službám založeným na Azure Active Directory, správa identity uživatele se tím zjednodušuje. Můžete taky nakonfigurovat funkce jednotného přihlašování, aby se prostředí ověřování pro vaše uživatele zjednodušilo a zpřehlednilo.

Aby to bylo ještě jednodušší, při použití stejného [tenanta Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) jsou uživatelské účty, které jste dříve synchronizovali, dostupné všem cloudovým službám, které sdílejí stejné předplatné tenanta Azure AD.

## Synchronizace místních uživatelů s Azure AD
Jediný nástroj potřebný k synchronizaci uživatelských účtů s Azure AD je [Průvodce Azure AD Connectem](https://www.microsoft.com/download/details.aspx?id=47594). Průvodce Azure AD Connectem je nástroj, který vás zjednodušeně provede připojením místní infrastruktury identit ke cloudu.  Zvolte svoji topologii a potřeby (jeden nebo víc adresářů, synchronizaci hesel nebo federaci) a průvodce nasadí a nakonfiguruje všechny komponenty potřebné ke zprovoznění vašeho připojení. Včetně služeb synchronizace, Active Directory Federation Services (AD FS) a modulu Azure AD PowerShell.

> [!TIP]
> Azure AD Connect zahrnuje funkce dřív vydané jako Dirsync a Azure AD Sync. Další informace o [integraci adresáře](http://technet.microsoft.com/library/jj573653.aspx). Informace o výhodách synchronizace uživatelských účtů z místního adresáře do Azure AD najdete v tématu [Podobnosti mezi službou Active Directory a Azure AD](http://technet.microsoft.com/library/dn518177.aspx)..

## Udělení oprávnění správce
Až budete mít k předplatnému Intune přidané další uživatele, doporučujeme, abyste několika uživatelským účtům udělili [přihlašovací údaje správce](administrative-accounts-websites-perms.md). Konzola, kterou použijete k přiřazení přihlašovacích údajů správce, závisí na typu správce, kterého chcete přiřadit:

-   **Správce tenanta**: K přiřazení tohoto typu správce použijte **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]**. Správce bude mít na starosti správu předplatného, včetně fakturace, správu cloudového úložiště a uživatelů, kteří můžou používat [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Správce služeb**: K přiřazení tohoto typu správce použijte **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]**. Správce bude mít na starosti každodenní úkoly, jako je správa mobilních zařízení a počítačů, nasazování zásad a softwaru nebo spouštění sestav.


### Další kroky
Gratulujeme! Právě jste dokončili krok 3 *úvodní příručky Intune*.

>[!div class="step-by-step"]

>[&larr; **Nastavení domény**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Správa licencí Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  


<!--HONumber=May16_HO1-->


