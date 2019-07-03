---
title: Odebrání zařízení s Androidem z Intune | Microsoft Docs
description: Odebrání zařízení s Androidem z portálu společnosti Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: b68ea31a6c5d902e66c0eda8127e0f68383910f8
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529124"
---
# <a name="unenroll-your-android-device-from-management"></a>Zrušení správy registrovaného zařízení s Androidem  

Pokud organizace nechce zaregistrované zařízení s Androidem dále spravovat, může ho odebrat. V tomto článku je popsané, jak zařízení odebrat z aplikace Portál společnosti. Po odebrání zařízení:  

* Zařízení ztratí přístup k chráněným datům a prostředkům organizace.
* Zařízení se přestane zobrazovat na Portálu společnosti.
* Z Portálu společnosti nebude možné instalovat aplikace.
* Už nebudou platit nastavení, která se v zařízení změnila od jeho přidání (třeba zakázání fotoaparátu/kamery nebo vyžadování určité délky hesla).  

> [!NOTE]
> Nelze zrušit registraci nebo odebrat zařízení vlastněných společností z aplikace pro Microsoft Intune. Zařízení bylo zaregistrováno během počátečního nastavování zařízení a musí být zaregistrovaná pro přístup k prostředkům vaší organizace.  

1. Na Portálu společnosti přejděte do pravého horního rohu a klepněte na tři svislé tečky. Otevře se nabídka akcí.

   ![Snímek obrazovky aplikace portál společnosti pro Android, se v pravém horním rohu otevřenou nabídkou akcí. Nová možnost Odebrat Portál společnosti je k dispozici jako třetí pod možnostmi Můj profil a Nastavení a nad možnostmi Podmínky, Nápověda a váš názor a O produktu.](./media/android_remove_cp_menu_action_after_1705.png)

2. Klepněte na **Odebrat Portál společnosti**.  

3. Zobrazí se zpráva s informacemi o tom, co se stane, když zrušíte registraci zařízení. Pokud chcete potvrdit, že chcete zařízení z Portálu společnosti odebrat, klepněte na **OK**.

   ![Snímek obrazovky k dispozici po výběru nové možnosti "Odebrat portál společnosti" z nabídky akce potvrzení.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Odebrání dat shromažďovaných aplikací portál společnosti  

Postup odebrání všech dat, která do zařízení uložila aplikace Portál společnosti pro Android:

- Vymazat data aplikací tím, že klepnete na **aplikací** >  **[*název aplikace*]**  > **vymazat data**.
- Odstraňte následující složku: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Odinstalace aplikace Portál společnosti  
Portál společnosti je aplikace pro správu zařízení. Nelze odinstalovat, dokud se zrušení registrace zařízení od jeho správu. Jakmile registraci zrušíte, klepněte na ikonu aplikace Portál společnosti a podržte ji, dokud se nezobrazí **Odinstalovat**. Klepněte na **Odinstalovat** a aplikaci ze zařízení odeberte.  

Alternativně klepněte na **nastavení** > **aplikace** > **portál společnosti** > **odinstalovat**.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Odebrat aplikaci portál společnosti jako správce zařízení  
Jako poslední možnost můžete odinstalovat aplikaci z vašeho zařízení jako správce zařízení.  

Pokud máte zařízení ve vlastnictví společnosti, organizace může požadovat, aby portál společnosti na vašem zařízení za všech okolností. Pokud provádíte odinstalaci, možná ztratíte přístup k chráněné firemním prostředkům, jako je e-mail, aplikace, Wi-Fi nebo VPN, dokud je znovu nainstalovat aplikaci. Další informace o instalaci aktualizace nebo odebrání požadované aplikace, najdete v článku [do Microsoft Intune přidat aplikace](https://docs.microsoft.com/intune/apps-add#apps-that-are-added-automatically-by-intune).  

Tady je postup, chcete-li zakázat portálu společnosti jako správce zařízení. Názvy jednotlivých nastavení se může lišit na zařízení s Androidem.  

**Možnost 1**:  
1. Vyberte **nastavení** > **zabezpečení** > **nastavení dalšího ověření zabezpečení** > **Správci zařízení** .  
2. Zrušte **portál společnosti** výběru.  

**Možnost 2**:  
1. Vyberte **nastavení** > **zamykací obrazovka a zabezpečení** > **další nastavení zabezpečení** > **Správce zařízení aplikace**.  
2. Zrušte **portál společnosti** výběru.    

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
