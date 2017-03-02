---
title: "Ruční synchronizace zařízení s Windows | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 4b5f0129d6824a51c36662a1cc7ef4e8a2de9e20
ms.openlocfilehash: ff5a4313337c89da00cb87e0f4dd6c8dcc233361
ms.lasthandoff: 02/18/2017


---

# <a name="sync-your-windows-device-manually"></a>Ruční synchronizace zařízení s Windows

Někdy může instalace aplikace na zařízení s Windows trvat déle, než byste předpokládali. V takovém případě můžete zkusit provést ruční synchronizaci zařízení s Windows. Synchronizace může instalaci urychlit.

> [!Note]
> Pokud jste v síti s nižší rychlostí nebo s vyšším počtem zařízení, která stahují obsah ve stejnou dobu, může instalace aplikací chvíli trvat.

Synchronizovat ručně se dají verze Windows uvedené dále. Pokud vaše zařízení používá jinou verzi Windows, nebude bohužel možné ruční synchronizaci spustit.

* [Synchronizace stolního počítače s Windows 10](#windows-10-desktop)
* [Synchronizace Windows 10 Mobile](#windows-10-mobile)
* [Synchronizace Windows Phone 8.1](#windows-phone-81)

## <a name="windows-10-desktop"></a>Stolní počítač s Windows 10
Je více verzí Windows 10, a proto existují dvě sady postupů. Pokud chcete zjistit, jaké kroky použít, podívejte se na snímky obrazovky a postupujte podle pokynů, které odpovídají tomu, co vidíte na svém zařízení.

1. Zvolte tlačítko **Start** a pak zvolte **Nastavení**.

    ![Tlačítko Start](./media/win10pc-sync-1-start-button.png)

2. Na stránce **Nastavení** zvolte **Účty**.

    ![Volba možnosti Účty na obrazovce Nastavení](./media/win10pc-sync-2-settings-accounts.png)

3. Podívejte se na další dvě obrazovky a najděte tu, která vypadá stejně jako to, co vidíte ve svém zařízení. Použijte postup odpovídající této obrazovce.

    Pokud se zobrazí tato obrazovka s informací „Přístup do práce nebo do školy“, postupujte podle pokynů v části [Postup, pokud se zobrazí Přístup do práce nebo do školy](#steps-to-follow-if-you-see-access-work-or-school).

    ![Postup synchronizace, pokud se zobrazí Přístup do práce nebo do školy](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Pokud se zobrazí tato obrazovka s informací „Přístup do práce“, postupujte podle pokynů v části [Postup, pokud se zobrazí Přístup do práce](#steps-to-follow-if-you-see-your-account).

    ![Volba účtu typu Přístup do práce](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>Postup, pokud se zobrazí Přístup do práce nebo do školy

1. Na stránce **Účty** zvolte **Přístup do práce nebo do školy**.

    ![Volba Přístup do práce nebo do školy](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Zvolte svůj pracovní nebo školní účet. V závislosti na nastavení provedeném správcem IT se mohou zobrazit dva účty, které se podobají účtům v následujícím příkladu. Jeden účet má u sebe aktovku a druhý logo Microsoftu.

    - Pokud vidíte účet s aktovkou, vyberte ho a podívejte se, že je pod ním tlačítko **Informace**.
    - Pokud vidíte jen účet s logem Microsoftu, vyberte ho a podívejte se, že je pod ním tlačítko **Informace**.

    ![Volba názvu účtu vedle aktovky nebo loga Microsoftu](./media/win10pc-rs1-sync-info-button.png)

3. Zvolte tlačítko **Informace**. Otevře se dialogové okno, které vypadá podobně jako v následujícím příkladu.

    ![Volba názvu účtu vedle aktovky nebo loga Microsoftu](./media/win10pc-rs1-sync-button.png)

4. Zvolte tlačítko **Synchronizovat**. Zařízení se bude synchronizovat s Intune.

### <a name="steps-to-follow-if-you-see-work-access"></a>Postup, pokud se zobrazí Přístup do práce

1. Na stránce **Účty** zvolte **Přístup do práce**.

    ![Volba účtu typu Přístup do práce](./media/win10pc-sync-3-work-access.png)

2. V části **Zaregistrovat se ve správě zařízení** zvolte název své firmy.

    ![Volba názvu firmy pro správu zařízení](./media/win10pc-sync-4-tap-com-name.png)

3. Zvolte tlačítko **Synchronizovat**.

    ![Volba tlačítka Synchronizovat](./media/win10pc-sync-5-tap-sync.png)

   Tlačítko bude zašedlé, dokud synchronizace neskončí.

   ## <a name="windows-10-mobile"></a>Windows 10 Mobile
   Chcete-li ručně synchronizovat mobilní zařízení s Windows 10 pro urychlení pomalé instalace aplikací:

   1. Přejděte na **Všechny aplikace** > **Nastavení** > **Účty**.

       ![Volba možnosti Účty na obrazovce Nastavení](./media/win10m-sync-1-settings-accounts.png)

   2. Zvolte **Přístup do práce**.

       ![Volba účtu typu Přístup do práce](./media/win10m-sync-2-work-access.png)

   3. V části **Zaregistrovat se ve správě zařízení** zvolte název své firmy.

       ![Volba názvu firmy pro správu zařízení](./media/win10m-sync-3-tap-comp-name.png)

   4. Zvolte ikonu **Synchronizovat**.

       ![Volba ikony Synchronizovat](./media/win10m-sync-4-tap-sync.png)

       V horní části obrazovky se zobrazí zpráva, že „probíhá synchronizace účtu“. Tlačítko **Synchronizovat** je zašedlé, dokud neskončí synchronizace vašeho zařízení.

## <a name="windows-phone-81"></a>Windows Phone 8.1
Chcete-li provést ruční synchronizaci mobilního zařízení s Windows 8.1 pro urychlení pomalé instalace aplikací:

1. Přejděte na **Všechny aplikace** > **Nastavení** > **Pracoviště**.

    ![Seznam nastavení](./media/wp81-1-sync-settings-workplace.png)

2. Zvolte název své firmy.

    ![Volba názvu firmy pro účet pracoviště](./media/wp81-2-sync-tap-compname.png)

3. Zvolte ikonu **Synchronizovat**.

    ![Volba ikony Synchronizovat](./media/wp81-3-sync-tap-sync-button.png)

   V horní části obrazovky bude až do skončení synchronizace zařízení zobrazená zpráva, že „probíhá synchronizace účtu“.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

