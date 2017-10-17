---
title: "Konfigurace služby Skycure pro použití jednotného přihlašování služby Azure Active Directory"
description: "Konfigurace služby Skycure pro použití jednotného přihlašování služby Azure Active Directory (SSO)"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b89f9acded5cfd45b2716ce16aeedfd95e0af94e
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Konfigurace služby Skycure pro použití jednotného přihlašování služby Azure Active Directory (SSO)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Jednotné přihlašování služby Azure AD se používá, když službu Intune integrujete se službou Skycure. Toto jsou hlavní výhody:

-   **Správci** můžou používat stejné přihlašovací údaje a nemusí je zadávat znovu pokaždé, když se přihlašují nebo odhlašují z portálů Microsoft (služby Intune a Azure) a konzoly pro správu Skycure.

-   **Koncoví uživatelé** můžou použít stejné přihlašovací údaje služby Azure AD a nemusí je zadávat znovu pokaždé, když se přihlašují nebo odhlašují z aplikací služby Skycure.

Níže je uvedený postup, jak službu Skycure integrovat s jednotným přihlašováním služby Azure Active Directory (SSO).

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Postup získání ID tenanta služby Azure Active Directory

Je potřeba získat ID tenanta služby Azure AD.

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Na **řídicím panelu** zvolte **Azure Active Directory**.

![Řídicí panel služby Azure AD](../media/mtp/skycure-sso-1.png)

1.  Otevře se okno **Azure Active Directory**, ve kterém zvolte **Vlastnosti**.

![Okno Vlastnosti služby Azure AD](../media/mtp/skycure-sso-2.png)

1.  V okně **Vlastnosti služby Azure Active Directory** klikněte na ikonu **kopírování** v části **ID adresáře tenanta**.

> Zkopírovanou hodnotu ID adresáře vložte do textového souboru, abyste ji mohli použít později. Hodnotu ID adresáře budete později potřebovat při integraci služby Skycure se službou Intune.

![Řídicí panel služby Azure AD](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Povolení komunikace mezi službou Skycure a službou Azure Active Directory

1.  Zadejte do prohlížeče níže uvedenou adresu URL. Část **DIRECTORY_ID** nahraďte hodnotou ID tenanta služby Azure Active Directory, kterou jste si předtím zkopírovali do textového souboru.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Přihlaste se pomocí přihlašovacích údajů služby Azure Active Directory. Pokračujte kliknutím na **Přijmout**.

![Přihlašovací stránka Azure AD](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Vytvoření skupiny zabezpečení služby Azure AD pro službu Skycure (volitelné)

Máte možnost vytvořit vyhrazenou skupinu zabezpečení pro uživatele používající službu Skycure (např. Uživatelé služby Skycure). Ta potom může být užitečná při analýze činností služby Skycure prostřednictvím sestav.

-   Další informace získáte v článku týkajícím se [vytvoření skupiny a přidání členů ve službě Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Můžete také použít existující skupinu zabezpečení služby Azure AD.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Konfigurace účtu Azure AD pro integraci služby Intune se službou Skycure

1.  Do [konzoly pro správu Skycure](https://aad.skycure.com/) zadejte ID tenanta služby Azure Active Directory, které jste si předtím uložili do textového souboru.

![Pole pro ID tenanta služby Azure AD v konzole pro správu Skycure](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> Služba Skycure dotazem na službu Azure AD ověří, zda ID tenanta služby Azure Active Directory existuje, a jakmile ho najde, správce může přejít na další krok, kterým je Základní nastavení.

## <a name="next-steps"></a>Další kroky

[Stažení zásad konfigurace aplikace Skycure pro iOS](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)
