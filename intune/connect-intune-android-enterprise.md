---
title: Připojte si účet Intune ke svému účtu spravovaný obchod Google Play.
titleSuffix: Microsoft Intune
description: Zjistěte, jak připojit váš účet Intune ke svému účtu spravovaný obchod Google Play.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19efd0821deeac0e76c60ee67e6230da554391a0
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898009"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Připojte si účet Intune ke svému účtu spravovaný obchod Google Play

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pro podporu [pracovní profil Androidu Enterprise](android-work-profile-enroll.md), [Androidu Enterprise, plně spravované](android-fully-managed-enroll.md), a [vyhrazená zařízení s Androidem Enterprise](android-kiosk-enroll.md), je nutné se připojit vaším tenantem Intune účet pro váš účet spravovaný obchod Google Play.  

> [!NOTE]
> Protože dochází k interakci mezi doménami Google a Microsoft, může tento krok vyžadovat úpravu nastavení prohlížeče.  Zkontrolujte, jestli jsou portal.azure.com a play.google.com ve vašem prohlížeči ve stejné zóně zabezpečení.

1. Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](mdm-authority-set.md) na **Microsoft Intune**.
2. Přihlaste se k [Intune na Azure Portalu](https://aka.ms/intuneportal) a zvolte **Registrace zařízení** > **Registrace Androidu** > **Spravovaný obchod Google Play**.  Pokud používáte vlastní roli správce Intune, vyžaduje přístup k tomuto nastavení oprávnění ke čtení a aktualizaci na úrovni organizace.
   
   ![Obrazovka registrace Androidu Enterprise](./media/android-work-bind.png)

3. Volbou možnosti **Souhlasím** udělte Microsoftu oprávnění k [odesílání informací o uživatelích a zařízeních do Googlu](data-intune-sends-to-google.md). 
   
4. Volbou možnosti **Pokud se chcete hned připojit, spusťte Google** otevřete web spravovaného obchodu Google Play. Web se otevře v prohlížeči na nové kartě.
  
5. V Googlu přihlašovací stránka, zadejte účet Google, která bude spojená s všechny úlohy správy Androidu Enterprise pro tohoto tenanta. Jedná se o účet Google, který správci IT ve vaší společnosti sdílejí a používají ke správě a publikování aplikací v konzole Google Play. Můžete použít existující účet Google, nebo vytvořte nový. Zvolený účet nesmí být přidružený k doméně G-Suite.
    
    > [!Note]
    > Pokud používáte prohlížeč Microsoft Edge, kliknutím na **Přihlásit se** v pravém horním rohu se přihlaste ke svému účtu Google.

6. Do pole **Název organizace** zadejte název vaší společnosti. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit **Microsoft Intune**.

7. Vyjádřete souhlas se smlouvou pro Android a zvolte **Potvrdit**. Vaše žádost bude zpracována.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Odpojit účtu správce Android Enterprise

Můžete vypnout registraci Androidu Enterprise a správu. Chcete-li to provést, musíte nejprve vyřadit všechna zaregistrovaná zařízení s Androidem Enterprise pracovní profil. Potom kliknutím na možnost **odpojit** ve správě Intune konzoly odebrat všechna zaregistrovaná zařízení s Androidem Enterprise pracovním profilem a vyhrazené registrace zařízení. Tím také vztah mezi účtem spravovaný obchod Google Play a Intune.

1. Jako správce Intune vyberte na portálu [Azure Portal](https://portal.azure.com) možnost **Všechny služby** > **Monitorování a správa** > **Intune**.
2. Zvolte **Registrace zařízení** > **Registrace Androidu** > **Spravovaný obchod Google Play** > **Odpojit**.
3. Volbou možnosti **Ano** odpojte a zrušte registraci všech zařízení s Androidem Enterprise z Intune.

## <a name="next-steps"></a>Další postup

Po připojení k účtu spravovaný obchod Google Play, můžete [nastavit zařízení s Androidem Enterprise pracovním profilem](android-work-profile-enroll.md) a [nastavit zařízení s Androidem Enterprise vyhrazené](android-kiosk-enroll.md).
