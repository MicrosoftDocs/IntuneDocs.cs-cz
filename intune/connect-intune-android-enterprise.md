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
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 421d9c56f959fe30d35c0c55ce34017a7a0ba5a6
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838254"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Propojení účtu Intune s účtem Androidu Enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pro podporu [pracovní profil Androidu](android-work-profile-enroll.md), [Android plně spravované](android-fully-managed-enroll.md), a [vyhrazená zařízení s Androidem](android-kiosk-enroll.md), musíte se připojit účtu tenanta Intune k Androidu enterprise účet.  

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

Registraci a správu Androidu Enterprise můžete vypnout. Pokud to chcete udělat, je nutné nejprve vyřadit z provozu všechna zaregistrovaná zařízení s pracovním profilem Androidu. Pak volbou příkazu **Odpojit** v konzole pro správu Intune odeberte z registrace všechna zaregistrovaná zařízení s pracovním profilem Androidu a zařízení v beznabídkovém režimu. Touto akcí se odebere také vztah mezi účtem Androidu Enterprise a Intune.

1. Jako správce Intune vyberte na portálu [Azure Portal](https://portal.azure.com) možnost **Všechny služby** > **Monitorování a správa** > **Intune**.
2. Zvolte **Registrace zařízení** > **Registrace Androidu** > **Spravovaný obchod Google Play** > **Odpojit**.
3. Volbou možnosti **Ano** odpojte a zrušte registraci všech zařízení s Androidem Enterprise z Intune.

## <a name="next-steps"></a>Další postup

Po připojení k účtu Androidu Enterprise můžete [nastavit zařízení s pracovním profilem Androidu](android-work-profile-enroll.md) a [nastavit zařízení s Androidem v beznabídkovém režimu](android-kiosk-enroll.md).
