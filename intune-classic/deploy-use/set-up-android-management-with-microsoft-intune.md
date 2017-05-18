---
title: "Nastavení správy systému Android | Dokumentace Microsoftu"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení se systémy Android a KNOX Standard v Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 4042a22ecfbab7970ea4b3dab8ee6a82b0da5f78
ms.lasthandoff: 04/24/2017


---

# <a name="set-up-android-device-management"></a>Nastavení správy zařízení s Androidem

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Správce Intune může na Portálu společnosti povolit správu zařízení s Androidem, včetně zařízení se sadou Samsung Knox Standard. Uživatelé pak mohou k registraci svých zařízení použít aplikaci Portál společnosti, která je k dispozici v obchodě Google Play.

Zařízení s Androidem se standardně můžou registrovat do Intune. Pokud chcete u zařízení s Androidem zablokovat možnost registrace, přihlaste se pomocí přihlašovacích údajů správce na [portál pro správu Microsoft Intune](https://manage.microsoft.com). Zvolte **Správce** > **Správa mobilního zařízení** > **Pravidla registrace** a potom zrušte zaškrtnutí políčka **Povolit zařízení s Androidem**.

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Povolení registrace zařízení s Androidem**<br>
    K povolení registrace mobilních zařízení s Androidem nejsou potřeba žádné další konfigurace v konzole Intune.

3.  **Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Androidem v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.

    Informace o dalších úlohách koncových uživatelů najdete v článcích:
  - [Materiály o prostředí Microsoft Intune pro koncové uživatele](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Pokyny pro koncové uživatele zařízení s Androidem](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat Portál společnosti z čínských marketplace aplikací. Aplikace Portál společnosti pro Android bude dostupná ke stažení v těchto obchodech:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Ke komunikaci se službou Microsoft Intune používá aplikace Portál společnosti pro Android služby Google Play. Vzhledem k tomu, že služby Google Play ještě nejsou v Číně dostupné, může provádění kterékoli z následujících úloh trvat až 8 hodin. 

|Konzola správce Intune| Aplikace Portál společnosti Intune pro Android |Web Portál společnosti Intune|   
|---|---|---|
|Úplné vymazání| Odebrání vzdáleného zařízení| Odebrání zařízení (místní a vzdálené)|
|selektivní vymazání| Resetování zařízení| Resetování zařízení|
|Nasazení nových nebo aktualizovaných aplikací| Instalace dostupných obchodních aplikací| Resetování hesla zařízení|
|Vzdálené uzamčení|||
|Resetování hesla|||

### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)

