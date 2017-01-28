---
title: "Přidání uživatelů a udělení oprávnění | Dokumentace Microsoftu"
description: "Synchronizace místních uživatelů s Azure AD a udělení správci oprávnění ke správě předplatného Intune"
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
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: 02b6dd389c94d2b31bd96b2095ae48b685084370


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Přidání uživatelů a udělení oprávnění pro správu v Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Jako správce můžete uživatele přidat přímo nebo je synchronizovat z místní služby Active Directory. Po přidání můžou uživatelé zaregistrovat zařízení a přistupovat k prostředkům společnosti. Můžete také uživatelům udělit další oprávnění včetně oprávnění *správce tenanta*, *správce služeb* a *správce registrace zařízení*.

Toto téma vám pomůže s těmito aktivitami:

- [Přidání uživatelů do Intune](#add-users-to-intune)
- [Udělení dalších oprávnění Intune](#grant-intune-permissions) včetně:
  - [Správce tenanta](#tenant-administrator)
  - [Správce služeb](#service-administrator)
  - [Správci registrace zařízení](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Přidání uživatelů do Intune
Můžete ručně přidat uživatele k předplatnému Intune prostřednictvím [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). Těm se automaticky nepřidělí licence k Intune. Místo toho musí správce klienta Intune později uživatelský účet upravit a licenci uživateli přiřadit ručně z portálu Office služeb 365. Pokyny najdete v článku o [Individuální nebo hromadné přidávání uživatelů do Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizace služby Active Directory a přidání uživatelů do Intune
Můžete nakonfigurovat synchronizaci adresářů, aby se importovaly uživatelské účty z vaší místní služby Active Directory do Microsoft Azure Active Directory (Azure AD), což zahrnuje uživatele Intune. Když máte místní službu Active Directory připojenou ke všem vašim službám založeným na Azure Active Directory, správa identity uživatele se tím zjednodušuje. Můžete taky nakonfigurovat funkce jednotného přihlašování, aby se prostředí ověřování pro vaše uživatele zjednodušilo a zpřehlednilo. Propojením stejného [tenanta Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) s více službami se uživatelské účty, které jste předtím synchronizovali, stanou dostupnými pro všechny cloudové služby.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Synchronizace místních uživatelů s Azure AD
Jediný nástroj potřebný k synchronizaci uživatelských účtů s Azure AD je [Průvodce Azure AD Connectem](https://www.microsoft.com/download/details.aspx?id=47594). Průvodce Azure AD Connectem je nástroj, který vás zjednodušeně provede připojením místní infrastruktury identit ke cloudu.  Zvolte svoji topologii a potřeby (jeden nebo víc adresářů, synchronizaci hesel nebo federaci) a průvodce nasadí a nakonfiguruje všechny komponenty potřebné ke zprovoznění vašeho připojení. Včetně služeb synchronizace, Active Directory Federation Services (AD FS) a modulu Azure AD PowerShell.

> [!TIP]
> Azure AD Connect zahrnuje funkce dřív vydané jako Dirsync a Azure AD Sync. Další informace o [integraci adresáře](http://technet.microsoft.com/library/jj573653.aspx). Informace o výhodách synchronizace uživatelských účtů z místního adresáře do Azure AD najdete v tématu [Podobnosti mezi službou Active Directory a Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Udělení oprávnění Intune

Až budete mít k předplatnému Intune přidané další uživatele, doporučujeme, abyste několika uživatelským účtům udělili oprávnění správce. Ke správě Intune můžete uživatelům udělit tři typy oprávnění Intune:
-   **Správce tenanta**: K přiřazení tohoto typu správce použijte portál Office 365. Správce bude moct spravovat vaše předplatné včetně fakturace, cloudového úložiště a správy uživatelů, kteří můžou používat Intune.
-   **Správce služeb**: K přiřazení tohoto typu správce použijte konzolu pro správce Microsoft Intune. Správce bude mít na starosti každodenní úkoly, jako je správa zařízení a počítačů, nasazování zásad a aplikací nebo spouštění sestav.
-   **Správce registrace zařízení**: K přiřazení tohoto typu správce použijte konzolu pro správce Microsoft Intune. Správce bude mít na starosti každodenní úkoly, jako je správa zařízení a počítačů, nasazování zásad a aplikací nebo spouštění sestav.


### <a name="tenant-administrator"></a>Správce klienta


Správcům klientů se přiřazuje jedna role správce, která definuje obor správy pro daného uživatele a úlohy, které můžou spravovat. Role správců jsou obvyklé v rámci různých cloudových služeb Microsoftu, i když některé služby nemusí podporovat některé role. Intune používá tyhle role:
- **Globální správce** – Má přístup ke všem funkcím pro správu v Intune. Ve výchozím nastavení se globálním správcem stane uživatel, který se k Intune zaregistruje. Globální správci jsou jediní správci, kteří můžou přiřazovat další role správců. V organizaci můžete mít více než jednoho globálního správce. Jako osvědčený postup doporučujeme, aby tuto roli mělo jenom pár lidí ve vaší společnosti kvůli omezení rizika pro společnost.
- **Správce fakturace** – Může dělat nákupy, spravovat předplatná, spravovat lístky podpory a sledovat stav služeb.
- **Správce hesel** – Může resetovat hesla, spravovat žádosti o služby a sledovat stav služeb. Správci hesel můžou resetovat hesla jenom uživatelům.
- **Správce podpory služeb** – Zakládá žádosti o podporu u Microsoftu a může si zobrazit řídicí panel služeb a centrum zpráv. Má oprávnění „jenom pro zobrazení“ s výjimkou zakládání lístků podpory a jejich čtení.
- **Správce správy uživatelů** – Může resetovat hesla, sledovat stav služeb, přidávat a odstraňovat uživatelské účty a spravovat žádosti o služby. Správce správy uživatelů nemůže odstranit globálního správce, vytvářet další role správců ani resetovat hesla správců fakturace, globálních správců a správců služeb.

Ve výchozím nastavení je účet, který umožňuje vytvořit vaše předplatné Microsoft Intune, účtem správce tenanta s rolí globálního správce. Jako správce tenanta můžete pomocí konzoly pro správu Intune spravovat předplatné pro Intune a přiřazovat správce tenanta z [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). Pro přístup k portálu a přiřazení prvního správce služeb použijte správce tenanta s rolí globální správy. Pro každodenní úlohy se nedoporučuje používat správce klienta. Správce tenanta nepotřebuje pro přístup ke konzole pro správu Intune licenci k Intune. Správce klienta je běžným pojmem mezi cloudovými službami Microsoftu. Když si pořídíte předplatné Intune, bude vaše služba tenantem Azure AD. Další informace najdete v části týkající se tenanta Azure AD v článku [Co je adresář Azure AD](http://technet.microsoft.com/library/jj573650.aspx).

Jako správce tenanta můžete používat [portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) ke správě svého předplatného, včetně těchto úloh (pokud je umožňuje vaše role správce):

- Správa uživatelských účtů a konfigurace synchronizace adresářů z místní služby Active Directory
- Správa skupin uživatelů nazývaných skupiny zabezpečení
- Přiřazení licencí pro Intune uživatelům
- Konfigurace názvu domény pro vaše předplatné používaného při přihlašování uživatelů (např. contoso.com)
- Správa fakturace a nákupů včetně licencí a prostoru úložiště v cloudu
- Vyhledání odkazů pro zobrazení stavu služby Intune

Abyste měli přístup k portálu Office 365, musí mít váš účet stav přihlášení **Povoleno**. Tento stav je něco jiného než vlastnictví licence k předplatnému. Ve výchozím nastavení jsou všechny uživatelské účty nastavené na **Povoleno**. Uživatelé bez oprávnění správce můžou použít portál Office 365 k resetování hesel k Intune.

### <a name="service-administrator"></a>Správce služeb

Ve výchozím nastavení Intune nepřiřazuje správce služeb. Místo toho musíte k přiřazení prvního správce služeb pro vaše předplatné použít správce klienta s rolí globálního správce. Jako správce služeb můžete použít [konzolu pro správu Intune](https://manage.microsoft.com/) ke správě každodenních úloh pro Intune. Správce služeb přiřazujete z konzoly správce. Pro přístup ke konzole pro správu musí mít správce služeb licenci pro Intune.

Správcům služeb se přiřazuje jedno z těchto oprávnění:
- **Úplný přístup**: Má neomezený přístup do všech oblastí konzoly pro správu Intune, může přidávat a spravovat dalších správce služeb
- **Přístup jen pro čtení**: Má oprávnění ke čtení pro všechny oblasti konzoly pro správu Intune, nemůže měnit data, ale může spouštět sestavy
- **Helpdesk – uzel Skupiny**: Umožňuje správci služeb provádět jenom úlohy související se scénáři helpdesku, viz[Přizpůsobení zobrazení konzoly Intune podle rolí administrátora](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Jako správce služeb můžete tento portál využívat ke správě každodenních operací včetně:

- Vytváření a správa zásad pro počítače a mobilní zařízení
- Nahrávání a nasazování aktualizací softwaru a aplikací
- Správa služby Endpoint Protection na počítačích
- Zobrazení stavu zařízení a spouštění sestav

### <a name="device-enrollment-managers"></a>Správci registrace zařízení

Správci registrace zařízení jsou standardní uživatelské účty, které mají další oprávnění registrovat víc uživatelských zařízení. Ve výchozím nastavení může každý uživatel Intune zaregistrovat až patnáct zařízení. Jako správce můžete uživatelskému účtu poskytnout oprávnění správce registrace zařízení. Takový účet může registrovat velká množství zařízení vlastněných společností. To se hodí, když je možné zařízení dočasně přiřadit uživatelům nebo používat v celoobrazovkovém režimu, který nevyžaduje přiřazení uživatele k zařízení. Další informace najdete v článku [Správce registrace zařízení](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Nastavení domény**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Správa licencí Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Jan17_HO2-->


