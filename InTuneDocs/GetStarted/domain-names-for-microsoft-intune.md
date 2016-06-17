---
# required metadata

title: Názvy domén pro Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Názvy domén pro Microsoft Intune

Před nastavením Microsoft Intune si přečtěte toto téma a další požadavky uvedené v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)..

Pokud si vaše organizace zaregistruje cloudovou službu Microsoftu, třeba Intune, získáte počáteční název domény, který může vypadat takhle: **contoso.onmicrosoft.com**. V tomhle příkladu je **contoso** název domény, který jste si zvolili při registraci, a **onmicrosoft.com** je přípona přiřazená účtům přidaným do vašeho předplatného. Po dokončení procesu registrace se tento název domény nedá změnit. Jako globální správce ale můžete přidat vlastní názvy domén pro vaši organizaci, které se mají použít se službou, nebo odebrat domény, které jste přidali dříve.

Pokud ve výchozím nastavení použijete doménu onmicrosoft, bude mít každý importovaný uživatel u svého hlavního názvu uživatele (UPN) příponu **onmicrosoft.com**.

Pokud chcete místo názvu domény, který vám byl přiřazen při registraci, použít název domény, který vlastníte, můžete ho přidat do Azure Active Directory. Jakmile doménu přidáte a ověří se, že jste jejím vlastníkem, můžete vytvořit účty a skupiny s názvem domény tak, že změníte záznamy prostředků DNS u svého poskytovatele hostingu DNS. Aby se zjednodušila správa uživatelských účtů, když chcete používat vlastní doménu, proveďte konfiguraci vlastního názvu domény ke svému předplatnému předtím, než začnete synchronizovat uživatele z místní služby Active Directory.

Konfigurace názvů domén a záznamy prostředků DNS pro Intune je stejná jako ostatní tenanty Azure Active Directory. Pokyny najdete v tématu [Přidání vlastního názvu domény k zjednodušení přihlašování pomocí Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### Související témata
[Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


