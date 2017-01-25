---
title: "Nastavení správy systému Android | Dokumentace Microsoftu"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení se systémy Android a KNOX Standard v Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ddc03985ab8a4959a1d2c9a47e77f042ab9310
ms.openlocfilehash: 6b74c09c37970429d3eaa571db655854d592a2fe


---

# <a name="set-up-android-device-management"></a>Nastavení správy zařízení s Androidem

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Správce Intune může na Portálu společnosti povolit správu zařízení s Androidem, včetně zařízení se sadou Samsung Knox Standard. Uživatelé pak mohou k registraci svých zařízení použít aplikaci Portál společnosti, která je k dispozici v obchodě Google Play.

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Povolení registrace zařízení s Androidem**<br>
    K povolení registrace mobilních zařízení s Androidem nejsou potřeba žádné další konfigurace v konzole Intune.

3.  **Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Androidem v Intune](../enduser/enroll-your-device-in-intune-android.md). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.

    Informace o dalších úlohách koncových uživatelů najdete v článcích:
  - [Materiály o prostředí Microsoft Intune pro koncové uživatele](what-to-tell-your-end-users-about-using-microsoft-intune.md)
  - [Pokyny pro koncové uživatele zařízení s Androidem](../enduser/using-your-android-device-with-intune.md)

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



<!--HONumber=Jan17_HO1-->


