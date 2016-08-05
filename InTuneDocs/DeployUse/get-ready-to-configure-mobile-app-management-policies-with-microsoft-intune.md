---
title: "Příprava ke konfiguraci zásad MAM | Microsoft Intune"
description: "Toto téma popisuje požadavky a nastavení uživatelů, aby bylo možné vytvořit zásady správy mobilních aplikací."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 39af738fe83ec6ea2e963d857cc233332063c80b


---

# Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune
Toto téma popisuje, co je třeba provést před vytvořením zásad správy mobilních aplikací (MAM) na portálu Azure.

Na Portálu Azure najdete novou konzolu pro správu, kterou je možné používat pro vytváření zásad MAM. K vytváření zásad MAM doporučujeme použít tento portál. Portál Azure podporuje následující scénáře MAM:
- Zařízení, která jsou zaregistrovaná v Intune
- Zařízení spravovaná řešením MDM třetí strany
- Zařízení, která nejsou spravovaná žádným řešením MDM (BYOD)

Pokud s používáním portálu Azure teprve začínáte, přečtěte si téma [Portál Azure pro zásady MAM v Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md), které vám zajistí rychlý přehled.

>[!IMPORTANT]

> Pokud teď ke správě svých zařízení používáte konzolu pro správu Intune, můžete ji využít k vytváření zásad MAM podporujících aplikace pro zařízení zaregistrovaná v Intune. Doporučujeme ale použít portál Azure, a to i pro zařízení, která jsou zaregistrovaná v Intune. Pokyny k vytvoření zásady MAM pomocí konzoly pro správu služby Intune najdete v tématu [Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> V Konzole správce Intune nemusíte vidět všechna nastavení zásad MAM. Pokud vytváříte zásady MAM v konzole pro správu Intune i na portálu Azure, pro aplikace se použije a pro uživatele nasadí zásada na portálu Azure.
> Zásady MAM vytvořené v konzole pro správu Intune se nedají importovat do portálu Azure.  Zásady MAM je potřeba znovu vytvořit na portálu Azure.


##  Podporované platformy
- iOS 8.1 nebo novější

- Android 4 nebo novější

V současné době není dostupná podpora zařízení s Windows.
##  Podporované aplikace
* **Aplikace Microsoftu:** Tyto aplikace mají integrovanou sadu Intune App SDK a před použitím zásad MAM nevyžadují žádné další zpracování.
Úplný seznam podporovaných aplikací Microsoftu najdete v galerii mobilních aplikací Microsoft Intune na stránce [Partneři aplikací Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx). Pokud na aplikaci kliknete, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.
* **Obchodní aplikace vaší organizace:** Před použitím zásad MAM vyžadují, abyste aplikaci připravili tak, aby obsahovala sadu Intune App SDK.

  * Pokud máte zařízení spravovaná pomocí Intune, projděte si téma [Rozhodnutí o způsobu přípravy aplikací na správu MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Pokud máte zařízení, která nejsou spravovaná (třeba zařízení vlastněná zaměstnanci), nebo zařízení spravovaná externím řešením správy mobilních zařízení, projděte si téma [Ochrana obchodních aplikací a dat na zařízeních nezaregistrovaných v Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

*Před tím*, než můžete nakonfigurovat zásady MAM, budete potřebovat:

-   Předplatné Microsoft Intune.    K získání aplikací se zásadami MAM uživatelé potřebují licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   Předplatné Office 365, které je potřeba v těchto případech:
  - Chcete použít zásady MAM pro aplikace s podporou víc identit.
  - Chcete vytvořit pracovní účty SharePoint Online a Exchange Online. Místní Exchange a místní SharePoint se nepodporují.
-   Nastavení Online Skypu pro firmy pro moderní ověřování. Další informace najdete v tématu [Povolení moderního ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx.md).


- Azure Active Directory (Azure AD) pro vytváření uživatelů. Azure AD ověří uživatele, když otevřou aplikaci a zadají svoje pracovní přihlašovací údaje.

    > [!NOTE]
    > Pokud k nastavení uživatelů použijete konzolu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], uvědomte si, že se konfigurace zásad MAM přesouvá na portál Azure. Pokud chcete použít tento portál, musíte nastavit skupiny uživatelů Azure AD pomocí portálu Office 365.


## Vytvoření uživatelů a přiřazení licencí Microsoft Intune

1. Ujistěte se, že máte předplatné Intune. Pokud ke správě svých zařízení používáte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], již předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] máte.  Pokud jste si zakoupili licenci Enterprise Mobility Suite (EMS), předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] už také máte. Pokud službu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] teprve zkoušíte, abyste se seznámili s funkcemi MAM, můžete na [webové stránce Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) získat zkušební účet.

    Pokud chcete ověřit, jestli máte předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na portálu Office na stránku **Fakturace**.  Předplatné služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] by mělo být označené jako **Aktivní**.

2.  Přihlaste se na [portál Office](http://portal.office.com) pomocí svých přihlašovacích údajů správce.

3.  Pokud chcete přidat uživatele a přiřadit licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na stránku **Aktivní uživatelé**.

    ![Stránka Aktivní uživatelé na portálu Office](../media/AppManagement/OfficePortal_AddUsers.png)

    ![Stránka Upravit uživatele na portálu Office](../media/AppManagement/OfficePortal_AssignLicenses.png)

4.  Pokud chcete, aby uživatel měl přístup na portály Office, Azure AD a Azure, přiřaďte mu roli **Globální správce**.

    ![Stránka pro úpravu rolí uživatelů na portálu Office](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Zásady MAM jsou nasazené pro skupiny uživatelů ve službě Azure Active Directory. Pokud chcete vytvořit skupiny uživatelů pro zásady MAM, na portálu Office přejděte na stránku **Skupiny** a výběrem možnosti **Přidat skupinu** v horní nabídce vytvořte novou skupinu zabezpečení.  Zadejte název a popis a potom klikněte na **Vytvořit**. Do vytvořené skupiny můžete přidávat uživatele kliknutím na **Upravit členy**. Skupina zabezpečení je vytvořená ve službě Azure Active Directory.

    ![Stránka pro skupiny zabezpečení na portálu Office](../media/AppManagement/OfficePortal_CreateGroups.png)

V následující tabulce najdete přehled rolí a oprávnění, které můžete přiřazovat správcům.

|||
|--|----|
|**Role**|**Oprávnění**|
|Globální správce (portál Office 365)|Přístup k portálu Office 365 a portálu Azure AD.<br /><br />Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Vlastník (portál Azure)|Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Přispěvatel (portál Azure)|Přístup k portálu Azure (může provádět jenom úkoly správy mobilních aplikací).|

## Přiřazení role Přispěvatel uživateli

Globální správci mají přístup k [portálu Azure](https://portal.azure.com).  Pokud chcete, aby ostatní správci mohli konfigurovat zásady a provádět i další úkoly správy mobilních aplikací, můžete jim přiřadit roli přispěvatele:


1.  V okně **Nastavení** v části **Správa prostředků** klikněte na **Uživatelé**.

    ![Okno Uživatelé na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Kliknutím na **Přidat** otevřete okno **Přidat přístup** .

3.  Klikněte na **Vybrat roli**a potom klikněte na **Přispěvatel**.

    ![Okno Vybrat roli na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Klikněte na **Přidat uživatele** a požadovaného uživatele vyhledejte podle jména nebo e-mailové adresy. V tomto seznamu se zobrazí prvních 1000 uživatelů, které jste vytvořili ve službě Azure AD pomocí portálu Office. Kliknutím na **OK** v okně **Přidat přístup** uložíte a přiřadíte uživateli roli.

    ![Okno přidání uživatelů na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Pokud vyberete uživatele, který nemá přiřazenou licenci [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], nebude moci získat přístup k portálu.

## Další kroky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


