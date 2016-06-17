---
# required metadata

title: Účty pro správu, weby a oprávnění v Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Účty pro správu, weby a oprávnění v Microsoft Intune

Před nastavením Microsoft Intune si přečtěte toto téma a další požadavky uvedené v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)..

Chcete-li spravovat Intune, budete používat:
- Dva typy účtů správce
- Uživatelské účty s dalšími oprávněními
- Dvě webové konzoly/portály pro správu k udělení přístupu vašim správcům k obsahu, který by měli spravovat.

V dalších částech najdete popis těchto účtů a portálů.

## Účty správce a uživatelské účty se zvláštními oprávněními

Dále jsou uvedené účty a oprávnění, které budete používat pro Intune.

### Správce klienta
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správcům klientů se přiřazuje jedna role správce, která definuje obor správy pro daného uživatele a úlohy, které můžou spravovat.<br /><br />Role správců jsou obvyklé v rámci různých cloudových služeb Microsoftu, i když některé služby nemusí podporovat některé role.<br /><br /> Microsoft Intune používá následující role:<br /><br />– Globální správce<br />– Správce fakturace<br />– Správce hesel<br />– Správce podpory služeb<br />– Správce správy uživatelů|Ve výchozím nastavení je účet, který umožňuje vytvořit vaše předplatné Microsoft Intune, účtem správce tenanta s rolí globálního správce.<br /></br>  Jako správce tenanta můžete použít [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] ke správě předplatného pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a přiřazení správce tenantů z [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Abyste mohli přiřadit svého prvního správce služby, použijte správce klienta s rolí globální správy pro přístup k [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Pro každodenní úlohy se nedoporučuje používat správce klienta. Správce tenanta nevyžaduje licenci pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], abyste měli přístup k [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Správce klienta je běžným pojmem mezi cloudovými službami Microsoftu. Když se přihlásíte k odběru [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], bude vaše služba tenantem Microsoft Azure AD. Přečtěte si část tenanta Azure AD v tématu [Co je adresář Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).|


### Správce služeb
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správcům služeb se přiřazuje jedno z těchto oprávnění:<br /><br />**Úplný přístup:** Uděluje přístup do všech oblastí [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] bez omezení. Můžete taky přidat a spravovat další správce služeb.<br /><br />**Přístup jen pro čtení:** Uděluje oprávnění ke čtení pro všechny oblasti [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Správce služby jen pro čtení nemůže měnit data, ale může spouštět sestavy.<br /><br />**Helpdesk – uzel Skupiny:** Udělí oprávnění, která správci služby umožní provádět jenom sadu úloh běžně spojovaných se scénáři technické podpory. Informace o této sadě oprávnění najdete v tématu [Přizpůsobení zobrazení konzoly Intune podle rolí administrátora](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)..|Ve výchozím nastavení [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nepřiřazuje správce služeb. Místo toho musíte k přiřazení prvního správce služeb pro vaše předplatné použít správce klienta s rolí globálního správce. </br></br> Jako správce služeb můžete použít [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] ke správě každodenních úloh pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Správce služeb přiřazujete z konzoly správce. Dřív, než bude možné z účtu získat přístup ke konzole pro správu, musí mít správce služeb licenci pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].|



### Správci registrace zařízení
|Úrovně oprávnění|Další informace|
|--------------------------|-------------------------|
|Správci registrace zařízení jsou standardní uživatelské účty, které mají další oprávnění registrovat víc než pět zařízení.|Ve výchozím nastavení může každý uživatel [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] zaregistrovat až pět zařízení. Uživatelskému účtu ale můžete udělit oprávnění správce registrace zařízení a pak z tohoto účtu zaregistrovat velké skupiny zařízení vlastněných společností. To se hodí, když je možné zařízení dočasně přiřadit uživatelům nebo používat v celoobrazovkovém režimu, který nevyžaduje přiřazení uživatele k zařízení.|


## Weby pro správu pro Intune
 Různé úlohy správy vyžadují, abyste použili jeden z následujících webů pro správu, ke kterým můžete přistupovat pomocí [podporovaného webového prohlížeče](supported-web-browsers.md)..

- [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konzola pro správu Microsoft Intune](https://admin.manage.microsoft.com/)

### [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Jako správce tenanta můžete používat tento portál ke správě svého předplatného**, včetně těchto úloh (pokud je umožňuje vaše role správce):

- Správa uživatelských účtů pro předplatné a konfigurace synchronizace adresářů z místní služby Active Directory.
- Správa skupin uživatelů, které se nazývají skupiny zabezpečení.
- Přiřazení licencí, které chcete použít pro uživatele [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Konfigurace názvu domény, který používáte se svým předplatným. Název domény definuje účet, ke kterému se uživatelé přihlašují.
- Správa údajů o fakturaci a nákupech ohledně vašeho předplatného, včetně počtu licencí, které máte, nebo velikosti úložiště cloudu, které můžete použít.
- Hledání odkazů pro zobrazení stavu služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Jako správce tenanta se můžete přihlásit k portálu Office 365 a spravovat předplatné i v případě, že váš účet nemá přiřazenou licenci k používání [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Všichni uživatelé, kteří mají licenci pro Intune, ale nejsou správci, můžou na tomto portálu obnovit své heslo účtu a upravovat svůj profil.
- Abyste měli přístup k portálu Office 365, musí mít váš účet stav přihlášení **Povoleno**. Tento stav je něco jiného než vlastnictví licence k předplatnému. Ve výchozím nastavení jsou všechny uživatelské účty nastavené na **Povoleno**..


### [Konzola pro správu Microsoft Intune](https://admin.manage.microsoft.com/)

**Jako správce služby můžete tento portál využívat ke správě každodenních operací** včetně:

- Nastavení zásad pro počítače a mobilní zařízení.
- Nahrání a nasazení softwaru, třeba aktualizací softwaru a aplikací.
- Správa služby Endpoint Protection [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na počítačích.
- Zobrazení stavu zařízení a spouštění sestav.
- Přihlaste se k tomuto portálu. Abyste se mohli přihlásit k tomuto portálu, musíte mít buď oprávnění správce služeb, nebo být správcem tenanta s rolí globálního správce.


K tomuto portálu se můžou přihlásit jen uživatelé, kteří mají oprávnění správce služeb nebo jsou správcem tenanta s rolí globálního správce. Abyste získali přístup ke konzole pro správu, musí mít váš účet licenci k používání [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a stav přihlášení nastavený na **Povoleno**..

Přečtěte si další informace o [přidávání uživatelů k vašemu předplatnému](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) a [přiřazování licencí pro vaše předplatné](start-with-a-paid-subscription-to-microsoft-intune-step-4.md)..

 ### Související témata
 [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


