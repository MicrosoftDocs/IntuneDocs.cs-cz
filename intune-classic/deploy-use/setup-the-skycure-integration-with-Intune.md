---
title: "Nastavení integrace služby Skycure se službou Intune"
description: "Nastavení integrace služby Skycure se službou Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93722f66-7641-4a3f-b1fb-3a0a58a36675
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d5a59f34a5dacdc2e1a0d5c6601b4ede1a908e4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Nastavení integrace služby Skycure se službou Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete mít možnosti jednotného přihlašování, musíte aplikace Skycure přidat do služby Azure AD.

## <a name="before-you-begin"></a>Před zahájením

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Použití účtu služby Azure AD k integraci služeb Intune a Skycure

-   Než spustíte základní nastavení služby Skycure, ujistěte se, že máte účet Azure AD v [konzole pro správu Skycure](https://aad.skycure.com) správně nastavený.

### <a name="full-integration-vs-read-only"></a>Srovnání úplné integrace a integrace jen pro čtení

Služba Skycure podporuje dva způsoby integrace se službou Intune:

-   **Integrace jen pro čtení (základní nastavení):** Vytvoří pouze inventář zařízení z adresáře služby Azure Active Directory a naplní ho do konzoly Skycure.
<br>
    -   Pokud nejsou políčka **Report the health and risk of devices to Intune** (Hlásit stav a riziko zařízení službě Intune) a **Also report security incidents to Intune** (Hlásit službě Intune také bezpečnostní incidenty) v konzole pro správu Skycure zaškrtnutá, znamená to, že integrace je jen pro čtení, a proto se ve službě Intune nikdy nezmění stav zařízení (vyhovující nebo nevyhovující).
<br></br>
-   **Úplná integrace:** Umožňuje službě Skycure odesílat podrobnosti o rizikových a bezpečnostních incidentech do služby Intune, která vytváří obousměrnou komunikaci mezi oběma cloudovými službami.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Jak se aplikace Skycure používají se službami Azure AD a Intune?

-   **Aplikace pro iOS:** Umožňuje koncovým uživatelům přihlásit se do služby Azure AD pomocí aplikace pro iOS.

-   **Aplikace pro Android:** Umožňuje koncovým uživatelům přihlásit se do služby Azure AD pomocí aplikace pro Android.

-   **Aplikace pro správu:** Toto je aplikace Skycure pro více klientů služby Azure AD, která umožňuje komunikaci typu služba-služba se službou Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Postup nastavení integrace jen pro čtení mezi službami Intune a Skycure

> [!IMPORTANT]
> Přihlašovacími údaji správce služby Skycure je e-mail, který musí patřit platnému uživateli služby Azure Active Directory, jinak se přihlášení nezdaří. Služba Skycure k ověření správce používá jednotné přihlašování (SSO) služby Azure Active Directory.

1.  Přejděte do [konzoly pro správu Skycure](https://aad.skycure.com).

2.  Zadejte své **přihlašovací údaje správce Skycure** a potom klikněte na **Continue** (Pokračovat).

3.  Přejděte na **Settings** (Nastavení) a v části **Intune Integration** (Integrace služby Intune) vyberte **Basic Setup** (Základní nastavení).

4.  Klikněte na popisek **iOS App** (Aplikace pro iOS), na kterém je napsáno **Add to Active Directory** (Přidat do služby Active Directory).

    ![Aplikace pro iOS v konzole pro správu Skycure](../media/mtp/skycure-setup-1.png)

5.  Otevře se přihlašovací stránka. Zadejte své přihlašovací údaje do služby Intune a klikněte na **Accept** (Přijmout).

    ![Výzva k přihlášení aplikace pro iOS do služby Intune](../media/mtp/skycure-setup-2.png)

6.  Jakmile je aplikace ve službě Azure AD přidaná, uvidíte v konzole pro správu Skycure ukazatel, že se aplikace do služby Azure AD úspěšně přidala.

    ![Dokončení přidání aplikace pro iOS](../media/mtp/skycure-setup-3.png)

> [!NOTE]
> Stejný postup zopakujte pro aplikaci **Skycure pro Android** a **aplikaci pro správu**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Přidání skupiny zabezpečení služby Azure AD do služby Skycure

Je potřeba přidat skupinu zabezpečení služby Azure AD, která obsahuje všechna zařízení se službou Skycure.

1.  Zadejte a vyberte všechny skupiny zabezpečení se zařízeními, na kterých běží služba Skycure, a potom klikněte na **Apply changes** (Použít změny).

    ![Konfigurace skupiny zabezpečení v konzole pro správu Skycure](../media/mtp/skycure-setup-4.png)

Služba Skycure sesynchronizuje zařízení, na kterých běží její služba ochrany před mobilními hrozbami se skupinami zabezpečení služby Azure AD.

![Dokončení konfigurace skupiny zabezpečení v konzole pro správu Skycure](../media/mtp/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Nastavení úplné integrace mezi službami Intune a Skycure

1.  Přejděte do [konzoly pro správu Skycure](https://aad.skycure.com).

2.  Zadejte své **přihlašovací údaje správce Skycure** a potom klikněte na **Continue** (Pokračovat).

3.  Přejděte na **Settings** (Nastavení) a v části **Intune Integration** (Integrace služby Intune) vyberte **Full Integration** (Úplná integrace).

4.  Zaškrtněte tato nastavení:

    a.  Report the health and risk of device to Intune (Hlásit stav a riziko zařízení službě Intune)

    b.  Also report security incidents to Intune (Hlásit službě Intune také bezpečnostní incidenty)

5.  Klikněte na **Apply changes** (Použít změny).

    ![Dokončení úplné integrace služby Skycure](../media/mtp/skycure-setup-6.png)

## <a name="next-steps"></a>Další kroky

[Povolení ochrany před mobilními hrozbami Skycure ve službě Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)
