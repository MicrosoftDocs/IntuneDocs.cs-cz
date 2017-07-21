---
title: "Přidání uživatelů a udělení oprávnění"
description: "Synchronizujte místní uživatele s Azure AD a udělte správci oprávnění ke správě předplatného Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Přidání uživatelů a udělení oprávnění pro správu v Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

V tomto tématu najdou správci informace o tom, jak můžou do Intune přidat uživatele a jaká oprávnění pro správu jsou ve službě Intune k dispozici.

Jako správce můžete uživatele přidat přímo nebo je synchronizovat z místní služby Active Directory. Po přidání můžou uživatelé zaregistrovat zařízení a přistupovat k prostředkům společnosti. Můžete také uživatelům udělit další oprávnění včetně oprávnění *globálního správce* a *správce služeb*.

## <a name="add-users-to-intune"></a>Přidání uživatelů do Intune
Můžete ručně přidat uživatele k předplatnému Intune prostřednictvím [Portálu služeb Office 365](https://www.office.com/signin) nebo [portálu Azure Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Správce může upravovat uživatelské účty a přiřazovat licence Intune. Licence můžete přiřazovat z portálu Office 365 i z portálu Intune Azure. Pokud potřebujete další informace k používání Portálu služeb Office 365, podívejte se na téma [Individuální nebo hromadné přidávání uživatelů na Portál služeb Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Přidání uživatelů Intune v Centru pro správu Office 365
1. Přihlaste se na [Portál služeb Office 365](https://www.office.com/signin).
2. V nabídce Office 365 vyberte **Správce**.
3. V Centru pro správu vyberte **Přidat uživatele**.

  ![Snímek obrazovky Správce Office 365](media/office-add-user.png)

4. Uveďte následující údaje o uživateli:
  - **Jméno**
  - **Příjmení**
  - **Zobrazované jméno** – zobrazuje se na portálu Intune
  - **Uživatelské jméno** – hlavní uživatelské jméno na portálu Intune
  - **Umístění**
  - **Kontaktní informace** (nepovinné)
  - **Heslo** – automaticky vygenerované nebo vytvořené

     ![Snímek obrazovky Správce Office 365](media/office-add-user-details.png)

5. Přiřaďte uživatelskou licenci pro Intune. Vyberte možnost **Licence na produkty** a vyberte licenci na produkt.
6. Zvolte **Přidat** a vytvořte tak nového uživatele.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Přidávání uživatelů Intune na portálu Azure Intune
1. Přihlaste se na [Azure Portal](https://portal.azure.com). a přejděte na **Monitorování a správa** > **Intune**. Můžete také *vyhledat prostředky* pro **Intune**.
2. Vyberte možnost **Uživatelé**.
3. V Centru pro správu vyberte **Přidat uživatele**.
  ![Snímek obrazovky Správce Office 365](media/intune-add-user.png)
4. Uveďte následující údaje o uživateli:
  - **Název**
  - **Uživatelské jméno** – nové jméno na portálu Azure Active Directory ![Snímek obrazovky Správce Office 365](media/intune-add-user-info.png) Pokračujte výběrem **OK**.
5. Volitelně můžete zadat následující vlastnosti uživatele:
  - **Profil** – údaje týkající se práce včetně **pracovní pozice** a **oddělení**
  -  **Skupiny** – vyberte skupiny, které chcete pro uživatele přidat
  - **Role adresáře** – uživateli můžete udělit oprávnění správce pro Intune

  Vyberte **Vytvořit** a přidejte tak nového uživatele do Intune.
6. Vyberte **Profil** a potom pro nového uživatele vyberte **Místo využívání**. Místo využívání je nutné zadat, abyste mohli přiřadit novému uživateli licenci Intune. Pokračujte možností **Uložit**.
    ![Snímek obrazovky Správce Office 365](media/intune-add-user-loc.png)
7. Vyberte **Licence**. Potom zvolte **Přiřadit** a přiřaďte tomuto uživateli licenci Intune. Licence Intune je nutná pro registraci zařízení a přístup k prostředkům společnosti. Vyberte **Produkty**, zvolte typ licence, **Vybrat** a potom **Přiřadit**.

## <a name="grant-admin-permissions"></a>Udělení oprávnění správce

Až budete mít k předplatnému Intune přidané další uživatele, doporučujeme, abyste několika uživatelům přidělili oprávnění správce:
-   [Globální správce](#tenant-administrator): K přiřazení tohoto typu správce použijte Portál služeb Office 365. Globální správce může spravovat předplatné včetně fakturace, cloudového úložiště a správy uživatelů, kteří můžou používat Intune.
-   [Vlastní správce nebo správce s omezením](#service-administrator): K přiřazení tohoto typu správce použijte Office 365 nebo Intune v konzole Azure. Správce bude mít na starosti každodenní úkoly, jako je správa zařízení a počítačů, nasazování zásad a aplikací nebo spouštění sestav.

![Obrázek přiřazení rolí na Portálu služeb Office 365](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>Typy správců

Přiřazení jednoho nebo více oprávnění správce uživatelům. Tato oprávnění definují, v jakém rozsahu můžou uživatelé provádět správu a úlohy. Oprávnění správce jsou obvyklá v rámci různých cloudových služeb Microsoftu, i když některé služby nemusí některá oprávnění podporovat. Intune používá následující oprávnění správce:

- **Globální správce** – (Office 365 a Intune) má přístup ke všem funkcím pro správu v Intune. Ve výchozím nastavení se globálním správcem stane uživatel, který se k Intune zaregistruje. Globální správci jsou jediní správci, kteří můžou přiřazovat další role správců. V organizaci můžete mít více než jednoho globálního správce. Jako osvědčený postup doporučujeme, aby tuto roli mělo jenom pár lidí ve vaší společnosti, aby se minimalizovala rizika, která by mohla ohrozit vaši firmu.
- **Správce fakturace** – (Office 365 a Intune) může nakupovat, spravovat předplatná, spravovat lístky podpory a sledovat stav služeb.
- **Správce hesel** – (Office 365 a Intune) může resetovat hesla, spravovat žádosti o služby a sledovat stav služeb. Správci hesel můžou resetovat hesla jenom uživatelům.
- **Správce služeb** – (Office 365) předkládá žádosti o podporu u Microsoftu a může si zobrazit řídicí panel služeb a centrum zpráv. Má oprávnění „jenom pro zobrazení“ s výjimkou zakládání lístků podpory a jejich čtení.
- **Správce správy uživatelů** – (Office 365 a Intune) může resetovat hesla, sledovat stav služeb, přidávat a odstraňovat uživatelské účty a spravovat žádosti o služby. Správce správy uživatelů nemůže odstranit globálního správce, vytvářet další role správců ani resetovat hesla jiných správců.

Ve výchozím nastavení je účet, který se používá k vytvoření vašeho předplatného Microsoft Intune, účet globálního správce. Nedoporučujeme používat účet globálního správce k provádění každodenních úloh. Správce nepotřebuje pro přístup ke konzole Intune pro správu licenci k Intune. Další informace najdete v části týkající se tenanta Azure AD v článku [Co je adresář Azure AD](http://technet.microsoft.com/library/jj573650.aspx).

Abyste měli přístup na Portál služeb Office 365, musí být u vašeho účtu nastavená možnost **Přihlášení povoleno**. Na portálu Intune v možnosti **Profil** nastavte u možnosti **Zablokovat přihlášení** hodnotu **Ne** a povolte tak přístup. Tento stav je něco jiného než vlastnictví licence k předplatnému. Ve výchozím nastavení jsou všechny uživatelské účty nastavené na **Povoleno**. Uživatelé bez oprávnění správce můžou použít portál Office 365 k resetování hesel k Intune.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizace služby Active Directory a přidání uživatelů do Intune
Můžete nakonfigurovat synchronizaci adresářů, aby se importovaly uživatelské účty z vaší místní služby Active Directory do Microsoft Azure Active Directory (Azure AD), což zahrnuje uživatele Intune. Když máte místní službu Active Directory připojenou ke všem vašim službám založeným na Azure Active Directory, správa identity uživatele se tím zjednodušuje. Můžete taky nakonfigurovat funkce jednotného přihlašování, aby se prostředí ověřování pro vaše uživatele zjednodušilo a zpřehlednilo. Propojením stejného [tenanta Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) s více službami se uživatelské účty, které jste předtím synchronizovali, stanou dostupnými pro všechny cloudové služby.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Synchronizace místních uživatelů s Azure AD
Jediný nástroj potřebný k synchronizaci uživatelských účtů s Azure AD je [Průvodce Azure AD Connectem](https://www.microsoft.com/download/details.aspx?id=47594). Průvodce Azure AD Connectem je nástroj, který vás zjednodušeně provede připojením místní infrastruktury identit ke cloudu.  Vyberte topologii a potřeby (jeden nebo více adresářů, synchronizaci hesel nebo federaci). Průvodce nasadí a nakonfiguruje všechny komponenty potřebné ke zprovoznění a spuštění vašeho připojení. Včetně služeb synchronizace, Active Directory Federation Services (AD FS) a modulu Azure AD PowerShell.

> [!TIP]
> Azure AD Connect zahrnuje funkce dřív vydané jako Dirsync a Azure AD Sync. Další informace o [integraci adresáře](http://technet.microsoft.com/library/jj573653.aspx). Informace o synchronizaci uživatelských účtů z místního adresáře do Azure AD najdete v tématu [Podobnosti mezi službou Active Directory a Azure AD](http://technet.microsoft.com/library/dn518177.aspx).