---
title: "Ruční synchronizace zařízení s Windows | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2d7630d71505fadc22ab135ff0c8988b314793ad
ms.openlocfilehash: e0f18e4e1077f7843b4f8d8ea6d9e485f715bc3c


---


# Ruční synchronizace zařízení s Windows
Pokud instalace aplikace trvá moc dlouho, můžete zkusit zařízení s Windows synchronizovat ručně. Ruční synchronizace může instalaci urychlit.

Jsou podporované jenom následující verze. Použijte pokyny odpovídající typu vašeho zařízení.

* [Windows 10 Mobile](#windows-10-mobile)
* [Stolní počítač s Windows 10](#windows-10-desktop)
* [Windows Phone 8.1](#windows-phone-8-1)


## Windows 10 Mobile
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

## Stolní počítač s Windows 10
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

### Postup, pokud se zobrazí Přístup do práce nebo do školy

1. Na stránce **Účty** zvolte **Přístup do práce nebo do školy**.

    ![Volba Přístup do práce nebo do školy](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Zvolte svůj pracovní nebo školní účet. V závislosti na nastavení provedeném správcem IT se mohou zobrazit dva účty, které se podobají účtům v následujícím příkladu. Jeden účet má u sebe aktovku a druhý logo Microsoftu. 

    - Pokud vidíte účet s aktovkou, vyberte ho a podívejte se, že je pod ním tlačítko **Informace**. 
    - Pokud vidíte jen účet s logem Microsoftu, vyberte ho a podívejte se, že je pod ním tlačítko **Informace**.

    ![Volba názvu účtu vedle aktovky nebo loga Microsoftu](./media/win10pc-rs1-sync-info-button.png)

3. Zvolte tlačítko **Informace**. Otevře se dialogové okno, které vypadá podobně jako v následujícím příkladu.

    ![Volba názvu účtu vedle aktovky nebo loga Microsoftu](./media/win10pc-rs1-sync-button.png)

4. Zvolte tlačítko **Synchronizovat**. Zařízení se bude synchronizovat s Intune.

### Postup, pokud se zobrazí Přístup do práce
    
1. Na stránce **Účty** zvolte **Přístup do práce**.

    ![Volba účtu typu Přístup do práce](./media/win10pc-sync-3-work-access.png)

2. V části **Zaregistrovat se ve správě zařízení** zvolte název své firmy.

    ![Volba názvu firmy pro správu zařízení](./media/win10pc-sync-4-tap-com-name.png)

3. Zvolte tlačítko **Synchronizovat**.

    ![Volba tlačítka Synchronizovat](./media/win10pc-sync-5-tap-sync.png)

   Tlačítko bude zašedlé, dokud synchronizace neskončí.

## Windows Phone 8.1
Chcete-li provést ruční synchronizaci mobilního zařízení s Windows 8.1 pro urychlení pomalé instalace aplikací:

1. Přejděte na **Všechny aplikace** > **Nastavení** > **Pracoviště**.

    ![Seznam nastavení](./media/wp81-1-sync-settings-workplace.png)

2. Zvolte název své firmy.

    ![Volba názvu firmy pro účet pracoviště](./media/wp81-2-sync-tap-compname.png)

3. Zvolte ikonu **Synchronizovat**.

    ![Volba ikony Synchronizovat](./media/wp81-3-sync-tap-sync-button.png)

   V horní části obrazovky bude až do skončení synchronizace zařízení zobrazená zpráva, že „probíhá synchronizace účtu“.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->


