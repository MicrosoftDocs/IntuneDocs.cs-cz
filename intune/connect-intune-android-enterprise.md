---
title: Propojení účtu Intune s účtem Androidu Enterprise
titlesuffix: Microsoft Intune
description: Zjistěte, jak propojit účet Intune s účtem Androidu Enterprise.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0152d0cb7af418b500c1ac5991f2356bd2e19965
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909078"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Propojení účtu Intune s účtem Androidu Enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kvůli podpoře zařízení s pracovním profilem Androidu a zařízení s Androidem v beznabídkovém režimu musíte účet tenanta Intune propojit s účtem Androidu Enterprise. 

> [!NOTE]
> Protože dochází k interakci mezi doménami Google a Microsoft, může tento krok vyžadovat úpravu nastavení prohlížeče.  Zkontrolujte, jestli jsou portal.azure.com a play.google.com ve vašem prohlížeči ve stejné zóně zabezpečení.

1. Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](mdm-authority-set.md) na **Microsoft Intune**.
2. Přihlaste se k [Intune na Azure Portalu](https://aka.ms/intuneportal) a zvolte **Registrace zařízení** > **Registrace Androidu** > **Spravovaný obchod Google Play**.  Pokud používáte vlastní roli správce Intune, vyžaduje přístup k tomuto nastavení oprávnění ke čtení a aktualizaci na úrovni organizace.
   
   ![Obrazovka registrace Androidu Enterprise](./media/android-work-bind.png)

3. Volbou možnosti **Souhlasím** udělte Microsoftu oprávnění k [odesílání informací o uživatelích a zařízeních do Googlu](data-intune-sends-to-google.md). 
   
4. Volbou možnosti **Pokud se chcete hned připojit, spusťte Google** otevřete web spravovaného obchodu Google Play. Web se otevře v prohlížeči na nové kartě.
  
5. Na přihlašovací stránce Googlu zadejte účet Google, který bude přidružený ke všem úlohám správy Androidu Enterprise v tomto tenantovi. Jedná se o účet Google, který správci IT ve vaší společnosti sdílejí a používají ke správě a publikování aplikací v konzole Google Play. Můžete použít existující účet Google, nebo vytvořte nový. Zvolený účet nesmí být přidružený k doméně G-Suite.
    
    > [!Note]
    > Pokud používáte prohlížeč Microsoft Edge, kliknutím na **Přihlásit se** v pravém horním rohu se přihlaste ke svému účtu Google.

6. Do pole **Název organizace** zadejte název vaší společnosti. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit **Microsoft Intune**.

7. Vyjádřete souhlas se smlouvou pro Android a zvolte **Potvrdit**. Vaše žádost bude zpracována.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Odpojení účtu pro správu Androidu Enterprise

Registraci a správu Androidu Enterprise můžete vypnout. Při zvolení příkazu **Odpojit** v konzole pro správu Intune se z registrace odeberou všechna zaregistrovaná zařízení s pracovním profilem Androidu a zařízení v beznabídkovém režimu. Zároveň se odebere vztah mezi účtem Androidu Enterprise a Intune.

1. Jako správce Intune vyberte na portálu [Azure Portal](https://portal.azure.com) možnost **Všechny služby** > **Monitorování a správa** > **Intune**.
2. Zvolte **Registrace zařízení** > **Registrace Androidu** > **Spravovaný obchod Google Play** > **Odpojit**.
3. Volbou možnosti **Ano** odpojte a zrušte registraci všech zařízení s Androidem Enterprise z Intune.

## <a name="next-steps"></a>Další kroky

Po připojení k účtu Androidu Enterprise můžete [nastavit zařízení s pracovním profilem Androidu](android-work-profile-enroll.md) a [nastavit zařízení s Androidem v beznabídkovém režimu](android-kiosk-enroll.md).