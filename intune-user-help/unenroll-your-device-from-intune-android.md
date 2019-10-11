---
title: Postup odebrání zařízení s Androidem z Intune | Microsoft Docs
description: Odebrání zařízení s Androidem z Portál společnosti Intune
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
ms.openlocfilehash: 8f2e9313cf2a4d639096f783b895596fc2535649
ms.sourcegitcommit: 884654da8e72a63bfaea6b5def6c7891b065f251
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163549"
---
# <a name="unenroll-your-android-device-from-management"></a>Zrušit registraci zařízení s Androidem ze správy  

Odeberte zaregistrované zařízení se systémem Android, aby už není spravované vaší organizací. Tento článek popisuje, jak odebrat zařízení z aplikace Portál společnosti. Po odebrání zařízení:  

* Zařízení ztratí přístup k chráněným datům a prostředkům vaší organizace.
* Zařízení se už nezobrazuje v Portál společnosti.
* Nemůžete instalovat aplikace z Portál společnosti.
* Již neplatí všechna nastavení, která byla v zařízení změněna od jeho přidání (například zakázání fotoaparátu nebo vyžadování určité délky hesla).  

> [!NOTE]
> Z aplikace Microsoft Intune nemůžete zrušit registraci zařízení vlastněných společností nebo ho z ní odebrat. Zařízení bylo zaregistrováno během počátečního nastavení zařízení a musí být zaregistrováno pro přístup k prostředkům vaší organizace.  

1. V Portál společnosti v pravém horním rohu klepněte na tři svislé tečky. Otevře se nabídka akce.

   ![Snímek obrazovky aplikace pro Android Portál společnosti s nabídkou akce otevřenou v pravém horním rohu. Nová možnost odebrat portál společnosti je k dispozici jako třetí možnost pod položkou "můj profil" a "nastavení" a výše "podmínky", "nápovědu a zpětná vazba" a "o".](./media/android_remove_cp_menu_action_after_1705.png)

2. Klepněte na **odebrat portál společnosti**.  

3. Zobrazí se zpráva s informacemi o tom, co se stane, když zrušíte registraci zařízení. Klepnutím na **OK** potvrďte, že chcete zařízení odebrat z portál společnosti.

   ![Snímek obrazovky s potvrzením, který je k dispozici po výběru možnosti "odebrat portál společnosti" v nabídce Akce.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Odebrat data shromážděná aplikací Portál společnosti  

Pokud chcete odebrat všechna data, která aplikace Portál společnosti pro Android ukládá na vaše zařízení:

- Vymažte data aplikace klepnutím na **aplikace** > **[*název aplikace*]**  > **Vymazat data**.
- Odstraňte následující složku: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Odinstalace aplikace Portál společnosti

Portál společnosti je aplikace pro správu zařízení. Nedá se odinstalovat, dokud zrušíte registraci zařízení od jeho správy. Až to bude hotové, klepněte na ikonu aplikace Portál společnosti a podržte ji, dokud se nezobrazí možnost **odinstalovat**. Klepnutím na **odinstalovat** odeberte aplikaci ze svého zařízení.  

Případně klepněte na **nastavení** > **aplikace** > **portál společnosti** **odinstalaci** > .  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Odebrání aplikace Portál společnosti jako správce zařízení

Jako poslední možnost můžete aplikaci odinstalovat ze zařízení jako správce zařízení.  

Pokud máte zařízení vlastněné společností, může vaše organizace vyžadovat, aby na zařízení Portál společnosti. Pokud ho odinstalujete, může dojít ke ztrátě přístupu k chráněným prostředkům společnosti, jako je e-mail, aplikace, Wi-Fi nebo VPN, až do opětovné instalace aplikace. Další informace o instalaci, aktualizaci nebo odebrání požadovaných aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](/intune/apps/apps-add#apps-that-are-added-automatically-by-intune).

Tady je postup, jak zakázat Portál společnosti jako správce zařízení. Skutečné názvy jednotlivých nastavení se můžou v zařízení s Androidem lišit.  

**Možnost 1**:  

1. Vyberte **nastavení** > **zabezpečení** > **Další nastavení zabezpečení** > **Správci zařízení**.  
2. Zrušte zaškrtnutí **portál společnosti** výběru.  

**Možnost 2**:

1. Vyberte **nastavení** > **zamykací obrazovka a zabezpečení** > **Další nastavení zabezpečení** > **aplikace pro správu zařízení**.
2. Zrušte zaškrtnutí **portál společnosti** výběru.

Ještě potřebujete pomáhat? Obraťte se na firemní podporu. Kontaktní informace najdete na [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
