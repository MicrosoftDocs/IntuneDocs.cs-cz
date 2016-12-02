---
title: "Synchronizace služby Active Directory a přidání uživatelů do Intune | Microsoft Intune"
description: "Synchronizujte místní uživatele s Azure AD a udělte správci oprávnění ke správě předplatného Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizace služby Active Directory a přidání uživatelů do Intune
Můžete nakonfigurovat synchronizaci adresářů, aby se importovaly uživatelské účty z vaší místní služby Active Directory do Microsoft Azure Active Directory (Azure AD). Když máte místní službu Active Directory připojenou ke všem vašim službám založeným na Azure Active Directory, správa identity uživatele se tím zjednodušuje. Můžete taky nakonfigurovat funkce jednotného přihlašování, aby se prostředí ověřování pro vaše uživatele zjednodušilo a zpřehlednilo.

Aby to bylo ještě jednodušší, při použití stejného [tenanta Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) jsou uživatelské účty, které jste dříve synchronizovali, dostupné všem cloudovým službám, které sdílejí stejné předplatné tenanta Azure AD.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Synchronizace místních uživatelů s Azure AD
Jediný nástroj potřebný k synchronizaci uživatelských účtů s Azure AD je [Průvodce Azure AD Connectem](https://www.microsoft.com/download/details.aspx?id=47594). Průvodce Azure AD Connectem je nástroj, který vás zjednodušeně provede připojením místní infrastruktury identit ke cloudu.  Zvolte svoji topologii a potřeby (jeden nebo víc adresářů, synchronizaci hesel nebo federaci) a průvodce nasadí a nakonfiguruje všechny komponenty potřebné ke zprovoznění vašeho připojení. Včetně služeb synchronizace, Active Directory Federation Services (AD FS) a modulu Azure AD PowerShell.

> [!TIP]
> Azure AD Connect zahrnuje funkce dřív vydané jako Dirsync a Azure AD Sync. Další informace o [integraci adresáře](http://technet.microsoft.com/library/jj573653.aspx). Informace o výhodách synchronizace uživatelských účtů z místního adresáře do Azure AD najdete v tématu [Podobnosti mezi službou Active Directory a Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Udělení oprávnění správce

Chcete-li spravovat Intune, budete používat:
- Dva typy účtů správce
- Uživatelské účty s dalšími oprávněními
- Dvě webové konzoly/portály pro správu k udělení přístupu vašim správcům k obsahu, který by měli spravovat.

Až budete mít k předplatnému Intune přidané další uživatele, doporučujeme, abyste několika uživatelským účtům udělili přihlašovací údaje správce. Konzola, kterou použijete k přiřazení přihlašovacích údajů správce, závisí na typu správce, kterého chcete přiřadit:

-   **Správce tenanta**: K přiřazení tohoto typu správce použijte **portál účtu Microsoft Intune**. Správce bude mít na starosti správu vašeho předplatného, včetně fakturace, cloudového úložiště a správy uživatelů, kteří můžou používat Intune.

-   **Správce služeb**: K přiřazení tohoto typu správce použijte **konzolu pro správce Microsoft Intune**. Správce bude mít na starosti každodenní úkoly, jako je správa mobilních zařízení a počítačů, nasazování zásad a softwaru nebo spouštění sestav.

V dalších částech najdete popis těchto účtů a portálů.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Účty správce a uživatelské účty se zvláštními oprávněními

Níže jsou uvedené účty a oprávnění, které budete používat pro Intune.

### <a name="tenant-administrator"></a>Správce klienta
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správcům klientů se přiřazuje jedna role správce, která definuje obor správy pro daného uživatele a úlohy, které můžou spravovat.<br /><br />Role správců jsou obvyklé v rámci různých cloudových služeb Microsoftu, i když některé služby nemusí podporovat některé role.<br /><br /> Microsoft Intune používá následující role:<br /><br />– Globální správce<br />– Správce fakturace<br />– Správce hesel<br />– Správce podpory služeb<br />– Správce správy uživatelů|Ve výchozím nastavení je účet, který umožňuje vytvořit vaše předplatné Microsoft Intune, účtem správce tenanta s rolí globálního správce.<br /></br>  Jako správce tenanta můžete použít [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] ke správě předplatného pro Intune a přiřazení správců tenantů z [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Abyste mohli přiřadit svého prvního správce služby, použijte správce klienta s rolí globální správy pro přístup k [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Pro každodenní úlohy se nedoporučuje používat správce klienta. Správce tenanta nevyžaduje licenci, aby měla služba Intune přístup k [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Správce klienta je běžným pojmem mezi cloudovými službami Microsoftu. Když si pořídíte předplatné Intune, bude vaše služba tenantem Microsoft Azure AD. Přečtěte si část týkající se tenanta Azure AD v tématu [Co je adresář Azure AD](http://technet.microsoft.com/library/jj573650.aspx).|


### <a name="service-administrator"></a>Správce služeb
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správcům služeb se přiřazuje jedno z těchto oprávnění:<br /><br />**Úplný přístup:** Uděluje přístup do všech oblastí [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] bez omezení. Můžete taky přidat a spravovat další správce služeb.<br /><br />**Přístup jen pro čtení:** Uděluje oprávnění ke čtení pro všechny oblasti [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Správce služby jen pro čtení nemůže měnit data, ale může spouštět sestavy.<br /><br />**Helpdesk – uzel Skupiny:** Udělí oprávnění, která správci služby umožní provádět jenom sadu úloh běžně spojovaných se scénáři technické podpory. Informace o této sadě oprávnění najdete v tématu [Přizpůsobení zobrazení konzoly Intune podle rolí administrátora](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Ve výchozím nastavení Intune nepřiřazuje správce služeb. Místo toho musíte k přiřazení prvního správce služeb pro vaše předplatné použít správce klienta s rolí globálního správce. </br></br> Jako správce služeb můžete použít [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] ke správě každodenních úloh pro Intune.<br /><br />Správce služeb přiřazujete z konzoly správce. Než bude možné z účtu získat přístup ke konzole pro správu, musí mít správce služeb licenci pro Intune.|



### <a name="device-enrollment-managers"></a>Správci registrace zařízení
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správci registrace zařízení jsou standardní uživatelské účty, které mají další oprávnění registrovat víc než pět zařízení.|Ve výchozím nastavení může každý uživatel [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] zaregistrovat až pět zařízení. Uživatelskému účtu ale můžete udělit oprávnění správce registrace zařízení a pak z tohoto účtu zaregistrovat velké skupiny zařízení vlastněných společností. To se hodí, když je možné zařízení dočasně přiřadit uživatelům nebo používat v celoobrazovkovém režimu, který nevyžaduje přiřazení uživatele k zařízení.|




>[!div class="step-by-step"]

>[&larr; **Nastavení domény**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Správa licencí Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


