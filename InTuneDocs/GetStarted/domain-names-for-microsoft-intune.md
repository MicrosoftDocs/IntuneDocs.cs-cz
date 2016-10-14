---
title: "Názvy domén pro Microsoft Intune | Microsoft Intune"
description: "Přidání názvu domény pro Intune"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38159f6dbcae2eeb4dca47141e60eed12cd7f6ee
ms.openlocfilehash: abcf37e7ec3150b5a2fe4cda910631f83d4c510a


---



# Názvy vlastních domén s Microsoft Intune

Pokud si vaše organizace zaregistruje cloudovou službu Microsoftu, třeba Intune, získáte počáteční název domény, jejímž hostitelem je Azure Active Directory. Název může vypadat takhle: **vaše_doména.onmicrosoft.com**. V tomhle příkladu je **vaše_doména** název domény, který jste si zvolili při registraci, a **onmicrosoft.com** je přípona přiřazená účtům přidaným do vašeho předplatného.

Tento počáteční název domény nelze přejmenovat ani odebrat. Můžete však přidat, ověřit nebo odebrat své vlastní názvy domén, které chcete používat s Intune, což je užitečné, pokud chcete zachovat svou obchodní identitu.

## Přidání a ověření vlastní domény 

1. Přejděte na [portál pro správu Office 365](https://portal.office.com/Admin/Default.aspx) a přihlaste se k účtu správce.

2. V navigačním podokně zvolte **Nastavení** &gt; **Domény**.

3. Zvolte **Přidat doménu** a zadejte vlastní název domény.

4. Otevře se dialogové okno **Ověřit doménu** s hodnotami pro vytvoření záznamu TXT u poskytovatele hostingu DNS.
    - **Uživatelé GoDaddy:** Portál pro správu Office 365 vás přesměruje na přihlašovací stránku služby GoDaddy. Po zadání přihlašovacích údajů a přijetí smlouvy o oprávnění ke změně domény se záznam TXT vytvoří automaticky. Případně můžete [záznam TXT vytvořit](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Uživatelé Register.com:** Postupujte podle [podrobných pokynů](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) k vytvoření záznamu TXT.

    > [!TIP] 
    > Při provádění změn v rámci poskytovatele hostingu DNS ověřte, že jste vytvořili alias DNS (CNAME) pro [registraci zařízení s Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

Postup pro přidání a ověření vlastní domény může být případně [proveden v Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

V případě hybridního cloudu můžete po přidání vlastního názvu domény a ověření, že vaše organizace je jeho vlastníkem, pokračovat ve správě uživatelských účtů v místním Active Directory a pak je synchronizovat s Azure AD.

## Synchronizace místních uživatelů s Azure AD##

1. [Přidejte příponu UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) pro vaši vlastní doménu v místním Active Directory.
2. Nastavte novou příponu UPN pro místní uživatele, které chcete importovat.
3. Spusťte [synchronizaci Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) a proveďte integraci místních uživatelů s Azure AD.
4. Po úspěšné synchronizaci informací o uživatelských účtech můžete prostřednictvím [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) přiřadit licence Microsoft Intune.

### Související témata

[Informace o vaší počáteční doméně onmicrosoft.com v Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


