---
title: Konfigurace vlastního názvu domény
titlesuffix: Microsoft Intune
description: Přidání názvu vlastní domény do předplatného Microsoft Intune
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b9f81049e7bdfdfe2861d617dceb6036a55cecf
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31023525"
---
# <a name="configure-a-custom-domain-name"></a>Konfigurace vlastního názvu domény

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

V tomto tématu najdou správci informace o tom, jak vytvořit záznam DNS CNAME pro zjednodušení a přizpůsobení možností přihlašování v Microsoft Intune.

Pokud si vaše organizace zaregistruje cloudovou službu Microsoftu, třeba Intune, získáte počáteční název domény, jejímž hostitelem je Azure Active Directory (AD). Název může vypadat takto: **vaše_doména.onmicrosoft.com**. V tomto příkladu je **vaše_doména** název domény, který jste si zvolili při registraci. **onmicrosoft.com** je přípona přiřazená účtům přidaným do vašeho předplatného. Místo názvu domény, který získáte s předplatným, můžete pro přístup k Intune nakonfigurovat vlastní doménu vaší organizace.

Než vytvoříte uživatelské účty nebo synchronizujete místní službu Active Directory, důrazně doporučujeme, abyste se rozhodli, jestli chcete používat jenom doménu .onmicrosoft.com, nebo jestli chcete přidat jeden nebo více názvů vlastních domén. Pokud nastavíte vlastní doménu před přidáním uživatelů, správa uživatelů se zjednoduší. Uživatelé se budou moct přihlásit s přihlašovacími údaji, které používají pro přístup k jiným doménovým prostředkům.

Když se přihlásíte k odběru cloudové služby od Microsoftu, stane se instance této služby [tenantem služby Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), která bude vašim cloudovým službám poskytovat identitu a adresářové služby. Vzhledem k tomu, že postup konfigurace Intune pro používání vlastního názvu domény vaší organizace je stejný jako u jiných tenantů Azure AD, můžete použít informace a postupy uvedené v tématu [Přidání domény](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Další informace o vlastních doménách najdete v části [Přehled pojmů k vlastním názvům domén v Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Tento počáteční název domény onmicrosoft.com nelze přejmenovat ani odebrat. Aby bylo možné zachovat identitu firmy, můžete přidat, ověřit nebo odebrat vlastní názvy domén používané s Intune.

## <a name="to-add-and-verify-your-custom-domain"></a>Přidání a ověření vlastní domény

1. Přejděte na [portál pro správu Office 365](https://portal.office.com/Admin/Default.aspx) a přihlaste se k účtu správce.

2. V navigačním podokně zvolte **Nastavení** &gt; **Domény**.

3. Zvolte **Přidat doménu** a zadejte vlastní název domény. Vyberte **Další**.
   ![Snímek obrazovky z Centra Office 365, kde je vybraná možnost Nastavení > Domény a kde se přidává nový název domény](./media/domain-custom-add.png)
4. Otevře se dialogové okno **Ověřit doménu** s hodnotami pro vytvoření záznamu TXT u poskytovatele hostingu DNS.
    - **Uživatelé GoDaddy:** Portál pro správu Office 365 vás přesměruje na přihlašovací stránku služby GoDaddy. Po zadání přihlašovacích údajů a přijetí smlouvy o oprávnění ke změně domény se záznam TXT vytvoří automaticky. Případně můžete [záznam TXT vytvořit](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Uživatelé Register.com:** Postupujte podle [podrobných pokynů](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) k vytvoření záznamu TXT.

Postup pro přidání a ověření vlastní domény může být také [proveden v Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Další informace najdete v článku [Informace o vaší počáteční doméně onmicrosoft.com v Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A).
