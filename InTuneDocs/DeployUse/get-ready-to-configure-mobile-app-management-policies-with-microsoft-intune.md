---
title: "Předpoklady zásad MAM | Microsoft Intune"
description: "Toto téma popisuje požadavky a nastavení uživatelů, aby bylo možné vytvořit zásady správy mobilních aplikací."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Příprava na konfiguraci zásad správy mobilních aplikací na portálu Azure Portal
V tomto tématu jsou popsané předpoklady a kroky, které je potřeba udělat **předtím**, než na portálu Azure Portal budete moct vytvářet zásady správy mobilních aplikací (MAM).

Pokud chcete zjistit, jak zásady MAM služby Intune chrání data společnosti, přečtěte si téma [Ochrana aplikačních dat pomocí zásad správy mobilních aplikací](protect-apps-and-data-with-microsoft-intune.md).

## Co je Azure Portal?
Azure Portal je nová konzola pro správu, která umožňuje vytvářet zásady MAM a podporuje následující scénáře MAM:
- **Zařízení, která jsou zaregistrovaná v Intune**
- **Zařízení spravovaná jiným řešením MDM**
- **Zařízení, která nejsou spravovaná žádným řešením MDM (BYOD)**


V současnosti můžete konfigurovat zásady MAM jak v **konzole pro správu Intune**, tak na **portálu Azure Portal**.  Vezměte v úvahu tyto informace:

* Zásady vytvořené na **portálu Azure Portal** jsou podporované ve **všech scénářích MAM** uvedených výše. **Konzola pro správu Intune** podporuje jen vytváření zásad pro **zařízení zaregistrovaná a spravovaná ve službě Intune**.
* V konzole pro správu Intune se nemusí zobrazovat všechna nastavení zásad MAM, protože **nová nastavení** mohla být přidána jen na **portál Azure Portal**.
* Pokud vytvoříte zásady MAM na **obou** místech, tzn. jak v konzole pro správu Intune, tak na portálu Azure Portal, **použijí se pro aplikace zásady na portálu Azure Portal, které také budou nasazeny u uživatelů**.
    * Zásady MAM vytvořené v konzole pro správu Intune se nedají importovat do portálu Azure.  Zásady MAM je potřeba znovu vytvořit na portálu Azure.
* Ostatní **funkce pro správu aplikací**, jako je nasazení aplikací a zásady konfigurace aplikací, jsou v současnosti k dispozici jenom v **konzole pro správu Intune**.


Pokud s portálem Azure Portal teprve začínáte, přečtěte si téma [Portál Azure pro zásady MAM v Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md), kde najdete základní informace o používání tohoto portálu.

Pokyny k vytvoření zásady MAM v konzole pro správu Intune najdete v tématu [Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Podporované platformy
- iOS 8.1 nebo novější

- Android 4 nebo novější

>[!NOTE]
>Zařízení s Windows tyto zásady správy mobilních aplikací nepodporují. Pokud zařízení s Windows 10 zaregistrujete do Intune, můžete použít sadu Windows Information Protection, která nabízí podobné funkce. Podrobnosti najdete v tématu věnovanému [ochraně podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Podporované aplikace
* **Aplikace Microsoftu:** Tyto aplikace mají integrovanou sadu Intune App SDK a před použitím zásad MAM nevyžadují žádné další zpracování.
Úplný seznam podporovaných aplikací Microsoftu najdete v [galerii mobilních aplikací Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) na stránce aplikací pro Microsoft Intune od partnerů. Pokud na aplikaci kliknete, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.
* **Obchodní aplikace vaší organizace:** Před použitím zásad MAM vyžadují, abyste aplikaci připravili tak, aby obsahovala sadu Intune App SDK.

  * Pokud máte zařízení spravovaná pomocí Intune, projděte si téma [Rozhodnutí o způsobu přípravy aplikací na správu MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Pokud máte zařízení, která nejsou spravovaná (třeba zařízení vlastněná zaměstnanci) nebo se k jejich správě používá jiné řešení pro správu mobilních zařízení, přečtěte si téma [Ochrana obchodních aplikací a dat na zařízeních nezaregistrovaných v Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Požadavky

-   Předplatné Microsoft Intune.    K získání aplikací se zásadami MAM uživatelé potřebují licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
Pokud ke správě svých zařízení používáte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], již předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] máte.  Pokud jste si zakoupili licenci Enterprise Mobility Suite (EMS), předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] už také máte. Pokud službu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] teprve zkoušíte, abyste se seznámili s funkcemi MAM, můžete na [webové stránce Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) získat zkušební účet.

    Pokud chcete ověřit, jestli máte předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na portálu Office na stránku **Fakturace**.  Předplatné služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] by mělo být označené jako **Aktivní**.

-   Předplatné Office 365, které je potřeba v těchto případech:
  - Chcete použít zásady MAM pro aplikace s podporou víc identit.
  - Chcete vytvořit pracovní účty SharePoint Online a Exchange Online. Místní Exchange a místní SharePoint se nepodporují.
-   Nastavení Online Skypu pro firmy pro moderní ověřování. Další informace najdete v tématu [Povolení moderního ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) pro vytváření uživatelů. Azure AD ověří uživatele, když otevřou aplikaci a zadají svoje pracovní přihlašovací údaje.

    > [!NOTE]
    > Skupiny uživatelů musí být nastaveny v Azure AD. Skupiny uživatelů v Intune nejdou použít k nasazení zásad MAM na portálu Azure Portal.

### Vytvoření uživatelů a přiřazení licencí Microsoft Intune

1.  Přihlaste se na [portál Office](http://portal.office.com) pomocí svých přihlašovacích údajů správce.

2.  Přidejte uživatele podle popisu v části **Přidání uživatelů** v [tomto](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) tématu a přiřaďte jim licence Intune. Pokud chcete, aby uživatel měl přístup na portály Office, Azure AD a Azure, přiřaďte mu roli **Globální správce**.

5.  Zásady MAM jsou nasazené pro skupiny uživatelů ve službě Azure Active Directory. Pokud chcete vytvářet skupiny uživatelů pro zásady MAM, vytvořte skupinu uživatelů podle popisu v části **Vytvoření skupiny uživatelů** v [tomto](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) tématu.

### Jiní než globální správci

Globální správci mají přístup k [portálu Azure](https://portal.azure.com).  Pokud chcete, aby uživatelé, kteří nejsou globálními správci, mohli konfigurovat zásady a plnit další úkoly při správě mobilních aplikací, můžete jim přiřadit roli přispěvatele. Podrobné pokyny najdete v tématu [Použití přiřazení rolí ke správě přístupu k prostředkům předplatného Azure](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

V následující tabulce najdete přehled rolí a oprávnění, které můžete přiřazovat správcům.

|||
|--|----|
|**Role**|**Oprávnění**|
|Globální správce (portál Office 365)|Přístup k portálu Office 365 a portálu Azure AD.<br /><br />Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Vlastník (portál Azure)|Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Přispěvatel (portál Azure)|Přístup k portálu Azure (může provádět jenom úkoly správy mobilních aplikací).|




## Další kroky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


