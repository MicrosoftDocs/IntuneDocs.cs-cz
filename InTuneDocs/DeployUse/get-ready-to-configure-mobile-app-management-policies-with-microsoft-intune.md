---
title: "Příprava před konfigurací zásad správy mobilních aplikací | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.sourcegitcommit: 6a989482e9c3c35c1f377e0b32bf04beb89e60a3
ms.openlocfilehash: da4020eb71432f9bccb52909272d027da64ee47c


---

# Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune
Toto téma popisuje, co je třeba provést před vytvořením zásad správy mobilních aplikací (MAM) na portálu Azure.

Portál Azure je nová konzola pro správu, která slouží k vytváření zásad MAM, a doporučujeme tento portál při vytváření zásad MAM používat. Portál Azure podporuje následující scénáře MAM:
- Zařízení zaregistrovaná v Intune
- Zařízení spravovaná řešením MDM třetí strany
- Zařízení, která nejsou spravována žádným řešením MDM (BYOD).

Pokud s používáním portálu Azure teprve začínáte, přečtěte si téma [Portál Azure pro zásady MAM v Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md), které vám zajistí rychlý přehled.

Pokud zatím ke správě zařízení používáte **konzolu pro správu Intune**, můžete pomocí **konzoly pro správu Intune** vytvářet zásady MAM podporující aplikace pro zařízení zaregistrovaná v Intune, ale i pro zařízení zaregistrovaná v Intune doporučujeme používat portál Azure. Pokyny pro vytvoření zásady MAM pomocí konzoly pro správu Intune najdete [tady](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

Zásady MAM vytvořené v konzole pro správu Intune nelze importovat do portálu Azure.  Zásady MAM je nutné znovu vytvořit na portálu Azure.

>[!IMPORTANT]
> V Konzole správce Intune nemusíte vidět všechna nastavení zásad MAM. Pokud vytváříte zásady MAM v konzole pro správu Intune i na portálu Azure, pro aplikace se použije a pro uživatele se nasadí zásada na portálu Azure.


##  Podporované platformy
- iOS 8.1 nebo novější

- Android 4 nebo novější

V současné době není dostupná podpora zařízení s Windows.
##  Podporované aplikace
* **Aplikace Microsoftu:** Tyto aplikace mají integrovanou sadu Intune App SDK a před použitím zásad MAM nevyžadují žádné další zpracování.
Úplný seznam podporovaných aplikací Microsoftu najdete v galerii mobilních aplikací Microsoft Intune na stránce [galerie mobilních aplikací pro Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx). Pokud na aplikaci kliknete, můžete zjistit podporované scénáře, platformy a to, jestli aplikace podporuje víc identit.
* Vaše interní sestavené **obchodní aplikace:** Před použitím zásad MAM vyžadují, abyste aplikaci připravili tak, aby obsahovala sadu Intune App SDK.

  * Pokud máte zařízení spravovaná pomocí Intune, projděte si téma [Rozhodnutí o způsobu přípravy aplikací na správu MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Pokud máte zařízení, která nejsou spravovaná jako zařízení vlastněná zaměstnanci, nebo zařízení spravovaná externím řešením správy mobilních zařízení, projděte si téma [Ochrana obchodních aplikací a dat na zařízeních nezaregistrovaných v Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

**Před tím**, než můžete nakonfigurovat zásady MAM, potřebujete toto:

-   **Předplatné Microsoft Intune**.    Koncoví uživatelé potřebují k získání aplikací se zásadami MAM licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   Předplatné **Office 365 (O365)**, které je potřeba v těchto případech:
  - Chcete použít zásady MAM pro aplikace s podporou víc identit.
  - Chcete vytvořit pracovní účty SharePoint Online a Exchange Online. Místní Exchange a místní SharePoint nejsou podporovány.
-    [Povolení moderního ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx.md) pro **Online Skype pro firmy**.


- **Azure Active Directory (Azure AD)** pro vytváření uživatelů. Služba Azure AD ověřuje uživatele při spuštění aplikace a zadání pracovních přihlašovacích údajů.

    > [!NOTE] Pokud nastavujete uživatele pomocí konzoly nástroje [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], uvědomte si, že konfigurace zásad MAM se od nynějška přesouvá na portál Azure. Pokud chcete používat tento portál, je potřeba nastavit skupiny uživatelů Azure AD pomocí portálu Office 365.


## Vytvoření uživatelů a přiřazení licencí Microsoft Intune

1. Potřebujete předplatné Intune: Pokud používáte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ke správě svých zařízení, předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] už máte.  Pokud jste si zakoupili licenci EMS, předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] už také máte. Pokud službu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] teprv zkoušíte, abyste se seznámili s funkcemi MAM, [tady](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) můžete získat zkušební účet.

    Pokud chcete ověřit, jestli máte předplatné [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na portálu Office na stránku Fakturace.  Předplatné služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] by mělo být označené jako **Aktivní**.

2.  Přihlaste se na   [portál Office](http://portal.office.com) pomocí svých přihlašovacích údajů správce.

3.  Pokud chcete přidat uživatele a přiřadit licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], přejděte na stránku **Aktivní uživatelé**.

    ![Stránka Přidat uživatele portálu Office](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Pokud chcete, aby uživatel měl přístup na portály Office, Azure AD a Azure, přiřaďte mu **roli globálního správce**.

    ![Snímek obrazovky zobrazující stránku Aktivní uživatelé portálu Office ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Zásady MAM jsou nasazené pro skupiny uživatelů ve službě Azure Active Directory. Pokud chcete vytvořit skupiny uživatelů v souladu se zásadami MAM, přejděte na stránku **Skupiny** na **portálu Office** a kliknutím na ikonu **+** vytvořte novou skupinu zabezpečení.  Zadejte název a popis a klikněte na **Vytvořit**. Do vytvořené skupiny můžete přidávat uživatele kliknutím na volbu **Upravit členy** v nově vytvořené skupině zabezpečení. Skupina zabezpečení je vytvořená ve službě Azure Active Directory.

    ![Obrazovka stránky zobrazující výběr role Globální správce na stránce Upravit uživatelské role](../media/AppManagement/OfficePortal_CreateGroups.png)

V následující tabulce najdete přehled rolí a oprávnění, které můžete přiřazovat správcům.

|||
|--|----|
|**Role**|**Oprávnění**|
|Globální správce (portál O365)|Přístup k portálu O365 a portálu Azure AD<br /><br />Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Role Vlastník (portál Azure)|Přístup k portálu Azure (může provádět úkoly správy rolí i správy mobilních aplikací).|
|Role Přispěvatel (portál Azure)|Přístup k portálu Azure (může provádět jenom úkoly správy mobilních aplikací).|

## Přiřazení role Přispěvatel uživateli

**Globální správci** mají přístup k [portálu Azure](https://portal.azure.com).  Chcete-li, aby ostatní správci mohli konfigurovat zásady a provádět i další úkoly správy mobilních aplikací, můžete jim přiřadit **roli přispěvatele** podle pokynů níže:


1.  V okně **Nastavení** v části **Správa prostředků** klikněte na **Uživatelé**.

    ![Snímek obrazovky okna Uživatelé na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Kliknutím na **Přidat** otevřete okno **Přidat přístup** .

3.  Klikněte na **Vybrat roli**a poté na **role Přispěvatel**.

    ![Snímek obrazovky okna Vybrat roli na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Jakmile vyberete roli, klikněte na volbu **Přidat uživatele**a vyhledejte uživatele pomocí uživatelského jména nebo e-mailové adresy. V tomto seznamu se zobrazí prvních 1000 uživatelů, které jste vytvořili ve službě Azure AD pomocí portálu Office. Kliknutím na **OK** v okně **Přidat přístup** uložíte a přiřadíte uživateli roli.

    ![Snímek obrazovky okna Přidat uživatele na portálu Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT] Pokud vyberete uživatele, který nemá přiřazenou licenci [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], nebude moct získat přístup k portálu.

## Další kroky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


