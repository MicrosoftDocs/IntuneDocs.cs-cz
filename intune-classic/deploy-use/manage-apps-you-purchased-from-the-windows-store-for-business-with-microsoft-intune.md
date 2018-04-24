---
title: Správa aplikací pro Microsoft Store pro firmy
description: Pokud chcete spravovat a nasazovat hromadně zakoupené aplikace z konzoly Intune, připojte Microsoft Intune k Microsoft Storu pro firmy.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/02/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b32f9c6be910156c26b446b7bf70a7975b4afaff
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Správa aplikací zakoupených v Microsoft Storu pro firmy v Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

[Microsoft Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svou organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete spravovat hromadně zakoupené aplikace pomocí konzoly Intune. Příklad:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole pro správu Intune a můžete je nasadit stejně jako všechny ostatní aplikace.
* V konzole pro správu Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatečný počet licencí, Intune blokuje nasazení a instalaci aplikací.

## <a name="before-you-start"></a>Než začnete
Než začnete synchronizovat a nasazovat aplikace z Microsoft Storu pro firmy, přečtěte si následující informace:
* Musíte nakonfigurovat Intune jako autoritu správy mobilních zařízení pro svoji organizaci. Další informace viz článek [Předpoklady pro registraci zařízení do Microsoft Intune](prerequisites-for-enrollment.md).
* Musíte mít zaregistrovaný účet v Microsoft Storu pro firmy.
* Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
* Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Microsoft Storem pro firmy.
* Intune synchronizuje jenom aplikace s online licencemi, které jste zakoupili v Microsoft Storu pro firmy.
* Pokud chcete použít tuto funkci, zařízení musí být připojená k doméně služby Active Directory nebo k síti na pracovišti.
* Zaregistrovaná zařízení musí používat verzi 1511 Windows 10.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Přidružení účtu v Microsoft Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte **Microsoft Intune**.

> [!NOTE]
> Pokud k nasazování aplikací pro Microsoft Store pro firmy používáte více nástrojů pro správu, mohli jste k Microsoft Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## <a name="configure-synchronization"></a>Konfigurace synchronizace

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**.
2. V pracovním prostoru **Správa** rozbalte **Správa mobilních zařízení** > **Windows** a pak zvolte **Store pro firmy**.
3. Na stránce **Microsoft Store pro firmy** postupujte takto:
   * Pokud jste to ještě neudělali, klikněte na odkaz pro registraci v Microsoft Storu pro firmy.
   * Až se zaregistrujete, zvolte **Konfigurovat synchronizaci**.
4. V dialogovém okně **Konfigurovat synchronizaci aplikací s Microsoft Storem pro firmy** vyberte **Povolit synchronizaci s Microsoft Storem pro firmy**.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se mají aplikace z Microsoft Storu pro firmy zobrazovat v konzole Intune. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Klikněte na **OK**.

## <a name="synchronize-apps"></a>Synchronizace aplikací

1. Na stránce **Microsoft Store pro firmy** zvolte **Synchronizovat nyní**. Aplikace zakoupené ve Storu se synchronizují s Intune.
2. V pracovním prostoru **Aplikace** zvolte **Aplikace** > **Multilicenční aplikace**. Zobrazí se aplikace, které můžete nasadit, a vy můžete ověřit, jestli se zakoupené aplikace správně naimportovaly. Aplikace v tomto uzlu se zobrazují s celkovým počtem licencí, které vlastníte, a počtem dostupných licencí.
Můžete například zakoupit aplikaci Portál společnosti (s online licencí) z Microsoft Storu pro firmy, synchronizovat ji do konzoly Intune a pak ji nasadit jako požadovanou aplikaci do požadovaných zařízení s Windows 10. 


## <a name="deploy-apps"></a>Nasazení aplikací

Aplikace ze Storu se nasazují stejně jako všechny ostatní aplikace v Intune. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Když nasadíte aplikaci z Microsoft Storu pro firmy, využije licenci každý uživatel, který si ji nainstaluje. Když využijete všechny dostupné licence nasazené aplikace, už nebudete moct nasadit žádné další kopie. Musíte provést některý z těchto kroků:
* Odinstalovat aplikaci z některých zařízení.
* Snížit rozsah aktuálního nasazení tak, aby jeho cílem byli jenom uživatelé, pro které máte dostatek licencí.
* Zakoupit v Microsoft Storu pro firmy další kopie příslušné aplikace.

> [!Important]
> Nasazené aplikace jsou dostupné jenom pro uživatele, který zařízení původně zaregistroval. Ostatní uživatelé k nim nemají přístup.


### <a name="see-also"></a>Viz taky
[Přidávání aplikací pro mobilní zařízení do Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)
