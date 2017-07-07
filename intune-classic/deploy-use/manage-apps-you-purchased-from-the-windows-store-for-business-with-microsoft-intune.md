---
title: "Správa aplikací z Windows Store pro firmy"
description: "Pokud chcete spravovat a nasazovat hromadně zakoupené aplikace z konzoly Intune, připojte Microsoft Intune k Windows Storu pro firmy."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 888d825fb9955e97b49e54a0c36ab882055076d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Správa aplikací koupených ve Windows Storu pro firmy v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Windows Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svoji organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete spravovat hromadně zakoupené aplikace pomocí konzoly Intune. Například:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole pro správu Intune a můžete je nasadit stejně jako všechny ostatní aplikace.
* V konzole pro správu Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatečný počet licencí, Intune blokuje nasazení a instalaci aplikací.

## <a name="before-you-start"></a>Než začnete
Než začnete synchronizovat a nasazovat aplikace z Windows Storu pro firmy, přečtěte si následující informace:
* Musíte nakonfigurovat Intune jako autoritu správy mobilních zařízení pro svoji organizaci. Další informace viz článek [Předpoklady pro registraci zařízení do Microsoft Intune](prerequisites-for-enrollment.md).
* Musíte mít zaregistrovaný účet ve Windows Storu pro firmy.
* Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
* Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Windows Storem pro firmy.
* Intune synchronizuje jenom aplikace s online licencemi, které jste zakoupili ve Windows Storu pro firmy.
* Pokud chcete použít tuto funkci, zařízení musí být připojená k doméně služby Active Directory nebo k síti na pracovišti.
* Zaregistrovaná zařízení musí používat verzi 1511 Windows 10.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Přidružení účtu ve Windows Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte **Microsoft Intune**.

> [!NOTE]
> Pokud k nasazování aplikací pro Windows Store pro firmy používáte více než jeden nástroj pro správu, mohli jste k Windows Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## <a name="configure-synchronization"></a>Konfigurace synchronizace

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**.
2. V pracovním prostoru **Správa** rozbalte **Správa mobilních zařízení** > **Windows** a pak zvolte **Store pro firmy**.
3. Na stránce **Windows Store pro firmy** postupujte takto:
 * Pokud jste to ještě neudělali, klikněte na odkaz pro registraci ve Windows Storu pro firmy.
 * Až se zaregistrujete, zvolte **Konfigurovat synchronizaci**.
4. V dialogu **Konfigurovat synchronizaci aplikací s Windows Storem pro firmy** vyberte **Povolit synchronizaci s Windows Storem pro firmy**.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se mají aplikace z Windows Storu pro firmy zobrazovat v konzole Intune. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Klikněte na **OK**.

## <a name="synchronize-apps"></a>Synchronizace aplikací

1. Na stránce **Windows Store pro firmy** zvolte **Synchronizovat nyní**. Aplikace zakoupené ve Storu se sesynchronizují s Intune.
2. V pracovním prostoru **Aplikace** zvolte **Aplikace** > **Multilicenční aplikace**. Zobrazí se aplikace, které můžete nasadit, a vy můžete ověřit, jestli se zakoupené aplikace správně naimportovaly. Aplikace v tomto uzlu se zobrazují s celkovým počtem licencí, které vlastníte, a počtem dostupných licencí.
Můžete například zakoupit aplikaci Portál společnosti (s online licencí) z Windows Store pro firmy, synchronizovat ji do konzoly Intune a pak ji nasadit jako požadovanou aplikaci do požadovaných zařízení s Windows 10. 


## <a name="deploy-apps"></a>Nasazení aplikací

Aplikace ze Storu se nasazují stejně jako všechny ostatní aplikace v Intune. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Když nasadíte aplikaci z Windows Storu pro firmy, každý uživatel, který si ji nainstaluje, využije jednu licenci. Když využijete všechny dostupné licence nasazené aplikace, už nebudete moct nasadit žádné další kopie. Musíte provést některý z těchto kroků:
* Odinstalovat aplikaci z některých zařízení.
* Snížit rozsah aktuálního nasazení tak, aby jeho cílem byli jenom uživatelé, pro které máte dostatek licencí.
* Zakoupit ve Windows Storu pro firmy další kopie příslušné aplikace.

> [!Important]
> Nasazené aplikace jsou dostupné jenom pro uživatele, který zařízení původně zaregistroval. Ostatní uživatelé k nim nemají přístup.


### <a name="see-also"></a>Související témata
[Přidávání aplikací pro mobilní zařízení do Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)
