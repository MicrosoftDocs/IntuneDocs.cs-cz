---
title: "Předpoklady zásad MAM | Dokumentace Microsoftu"
description: "Toto téma popisuje předpoklady pro nastavení uživatelů před vytvořením zásad správy mobilních aplikací."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 71ebb310699cf80310b33be1b665a968ac102bde
ms.lasthandoff: 04/24/2017


---

# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Příprava na konfiguraci zásad ochrany aplikací na portálu Azure Portal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V tomto tématu jsou popsané předpoklady a kroky, které je potřeba provést **před tím**, než na portálu Azure Portal budete moct vytvářet zásady ochrany aplikací.

Pokud chcete zjistit, jak můžou zásady ochrany aplikací Intune chránit podniková data, podívejte se na článek o [ochraně dat a aplikací pomocí zásad ochrany aplikací](protect-apps-and-data-with-microsoft-intune.md).

## <a name="what-is-the-azure-portal"></a>Co je Azure Portal?

Azure Portal je nová konzola pro správu, kterou je možné používat k vytváření zásad ochrany aplikací. Podporuje následující scénáře MAM:
- Zařízení, která jsou zaregistrovaná v Intune
- Zařízení spravovaná jiným řešením Správa mobilních zařízení (MDM)
- Zařízení, která nejsou spravovaná žádným řešením MDM (BYOD)

V současnosti můžete konfigurovat zásady ochrany aplikací jak v **konzole pro správu Intune**, tak na **portálu Azure Portal**.  Vezměte v úvahu tyto informace:

* Zásady vytvořené na **portálu Azure Portal** jsou podporované ve **všech scénářích MAM** uvedených před nimi. **Konzola pro správu Intune** podporuje jen vytváření zásad pro **zařízení zaregistrovaná a spravovaná ve službě Intune**.

* V konzole pro správu Intune se nemusí zobrazovat všechna nastavení zásad ochrany aplikací, protože **nová nastavení** můžou být přidaná jen na **portál Azure Portal**.

* Pokud vytvoříte zásady ochrany aplikací na **obou** místech, tedy jak v konzole pro správu Intune, tak na portálu Azure Portal, **použijí se pro aplikace zásady z portálu Azure Portal a také budou nasazeny u uživatelů**.
    * Zásady ochrany aplikací vytvořené v konzole pro správu Intune se nedají importovat do portálu Azure Portal.  Zásady ochrany aplikací je potřeba znovu vytvořit na portálu Azure Portal.


* Ostatní **funkce pro správu aplikací**, jako je nasazení aplikací a zásady konfigurace aplikací, jsou v současnosti k dispozici jen v **konzole pro správu Intune**.


Pokud s portálem Azure Portal teprve začínáte, přečtěte si článek [Portál Azure Portal pro zásady ochrany aplikací Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md), kde najdete základní informace o používání tohoto portálu.

Pokyny k vytvoření zásad ochrany aplikací v konzole pro správu Intune najdete v tématu o [konfiguraci a nasazení zásad ochrany aplikací v konzole Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Podporované platformy
- iOS 8.1 nebo novější
- Android 4 nebo novější
- Windows 10

>[!NOTE]
>Počínaje verzí 1703 se můžou zásady ochrany aplikací pro zařízení s Windows 10 definovat v MAM bez registračního scénáře. Podrobnosti najdete v tématu věnovanému [ochraně podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Podporované aplikace
* **Aplikace Microsoftu:** Tyto aplikace mají integrovanou sadu Intune App SDK a před použitím zásad ochrany aplikací nevyžadují žádné další zpracování.
Úplný seznam podporovaných aplikací Microsoftu najdete v [galerii mobilních aplikací Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) na stránce aplikací pro Microsoft Intune od partnerů. Pokud na aplikaci kliknete, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.

* **Obchodní aplikace vaší organizace:** Před použitím zásad ochrany aplikací musíte tyto aplikace připravit tak, aby obsahovaly sadu Intune App SDK.

  * Pokud máte zařízení spravovaná pomocí Intune, projděte si téma [Rozhodnutí o způsobu přípravy aplikací na správu MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

  * Pokud máte zařízení, která nejsou spravovaná (třeba zařízení vlastněná zaměstnanci) nebo se k jejich správě používá jiné řešení pro správu mobilních zařízení, přečtěte si téma [Ochrana obchodních aplikací a dat na zařízeních, která nejsou zaregistrovaná v Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Požadavky

-   **Předplatné služby Microsoft Intune**. K získání aplikací se zásadami ochrany aplikací uživatelé potřebují licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
Pokud ke správě svých zařízení používáte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], již předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] máte. Pokud jste si zakoupili licenci Enterprise Mobility Suite (EMS), předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] už také máte. Pokud službu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] teprve zkoušíte, abyste se seznámili s funkcemi MAM, můžete na [webové stránce Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/) získat zkušební účet.

    Pokud chcete ověřit, jestli máte předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na portálu Office na stránku **Fakturace**.  Pokud předplatné máte, měla by být služba [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] označená jako **Aktivní**.

-   **Předplatné Office 365**, které je potřeba v těchto případech:

  - Chcete použít zásady ochrany aplikací pro aplikace s podporou více identit.

  - Chcete vytvořit pracovní účty SharePoint Online a Exchange Online. Místní Exchange a místní SharePoint se nepodporují.

-   **Nastavení Online Skypu pro firmy pro moderní ověřování**. Další informace najdete v tématu [Povolení moderního ověřování](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) pro vytváření uživatelů. Azure AD ověří uživatele, když otevřou aplikaci a zadají svoje pracovní přihlašovací údaje.

    > [!NOTE]
    > Skupiny uživatelů musí být nastavené v Azure AD. Skupiny uživatelů v Intune nejdou použít k nasazení zásad ochrany aplikací na portálu Azure Portal.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Vytvoření uživatelů a přiřazení licencí Microsoft Intune

1.  Přihlaste se na [portál Office](https://portal.office.com) pomocí svých přihlašovacích údajů správce.

2.  Přidejte uživatele podle popisu **kroků k dokončení 30denní zkušební verze Intune** v [Příručce pro testování Intune](https://docs.microsoft.com/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) a pak přiřaďte licence Intune. Pokud chcete, aby uživatel měl přístup na portály Office, Azure AD a Azure, přiřaďte mu roli **Globální správce**.

5.  Zásady ochrany aplikací se nasazují pro skupiny uživatelů ve službě Azure Active Directory. Pokud chcete vytvářet skupiny uživatelů pro zásady ochrany aplikací, vytvořte skupinu uživatelů podle popisu v části **Vytvoření skupiny uživatelů** v článku [Vytvoření skupiny pro uspořádání uživatelů a zařízení pro testovací předplatné](https://docs.microsoft.com/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Přiřazení rolí uživatelům, kteří nejsou globálními správci

Globální správci mají přístup k [portálu Azure Portal](https://portal.azure.com).  Pokud chcete, aby uživatelé, kteří nejsou globálními správci, mohli konfigurovat zásady a plnit další úkoly při správě mobilních aplikací, podívejte se na článek [Použití přiřazení rolí ke správě přístupu k prostředkům předplatného Azure](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/).

## <a name="next-steps"></a>Další kroky
[Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

