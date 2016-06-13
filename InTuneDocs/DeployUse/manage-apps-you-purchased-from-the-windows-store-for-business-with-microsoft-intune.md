---
# required metadata

title: Správa aplikací koupených ve Windows Storu pro firmy | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Správa aplikací koupených ve Windows Storu pro firmy v Microsoft Intune
[Windows Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svoji organizaci, a to jednotlivě i hromadně. Pokud Store propojíte s Microsoft Intune, můžete spravovat hromadně zakoupené aplikace pomocí konzoly Intune. Příklad:
* Můžete synchronizovat seznam aplikací, které jste zakoupili ve Storu, s Intune.
* Aplikace, které jsou synchronizované, se zobrazí v konzole správce Intune a můžete je nasadit stejně jako všechny ostatní aplikace.
* V konzole správce Intune můžete sledovat, kolik licencí je dostupných a kolik se jich právě používá.
* Pokud není dostupný dostatek licencí, Intune blokuje nasazení a instalaci aplikací.

## Než začnete
Než začnete synchronizovat a nasazovat aplikace z Windows Storu pro firmy, přečtěte si následující informace:
* Musíte nakonfigurovat Intune jako autoritu správy mobilních zařízení pro svoji organizaci. Další informace najdete v tématu [Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md).
* Musíte mít zaregistrovaný účet ve Windows Storu pro firmy.
* Až přidružíte účet ve Windows Storu pro firmy k Intune, už nebude možné tento účet změnit.
* Aplikace zakoupené ze Storu se nedají do služby Intune přidat ručně ani z ní ručně odebrat. Dají se jenom synchronizovat s Windows Storem pro firmy.
* Intune synchronizuje jenom aplikace s online licencemi, které jste zakoupili ve Windows Storu pro firmy.
* Chcete-li použít tuto funkci, zařízení musí být připojená k doméně služby Active Directory nebo k síti na pracovišti.
* Zaregistrovaná zařízení musí používat verzi 1511 Windows 10.

## Přidružení účtu ve Windows Storu pro firmy k Intune
Než povolíte synchronizaci v konzole služby Intune, musíte svůj účet ve Storu nakonfigurovat tak, aby používal Intune jako nástroj pro správu:
1. Ujistěte se, že se do Storu pro firmy přihlašujete pomocí stejného účtu tenanta, který používáte k přihlášení do Intune.
2. Ve Storu pro firmy vyberte **Nastavení** > **Nástroje pro správu**.
3. Na stránce Nástroje pro správu vyberte **Přidat nástroj pro správu** a zvolte Microsoft Intune.

Teď můžete pokračovat a nastavit synchronizaci v konzole Intune.

## Konfigurace synchronizace

1. V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Správce**.
2. V pracovním prostoru **Správa** rozbalte položku **Správa mobilního zařízení** a potom klikněte na **Store pro firmy**.
3. Na stránce **Windows Store pro firmy** postupujte takto:
* Pokud jste to ještě neudělali, klikněte na odkaz pro registraci ve Windows Storu pro firmy.
* Až se zaregistrujete, klikněte na **Konfigurovat synchronizaci**.
4. V dialogu **Konfigurovat synchronizaci aplikací s Windows Storem pro firmy** vyberte **Povolit synchronizaci s Windows Storem pro firmy**.
5. V rozevíracím seznamu **Jazyk** vyberte jazyk, ve kterém se mají aplikace z Windows Storu pro firmy zobrazovat v konzole Intune. Bez ohledu na jazyk, ve kterém se budou zobrazovat, se nainstalují v jazyce koncového uživatele, pokud je dostupný.
6. Klikněte na **OK**.

## Synchronizace aplikací

1. Na stránce **Windows Store pro firmy** klikněte na **Synchronizovat nyní**. Aplikace zakoupené ve Storu se synchronizují s Intune.
2. V pracovním prostoru **Aplikace** klikněte na **Spravovaný software** > **Licencovaný software**. Zobrazí se dostupné aplikace a můžete ověřit, jestli se zakoupené aplikace správně importovaly.
Aplikace v tomto uzlu se zobrazují s celkovým počtem licencí, který vlastníte, a počtem dostupných licencí.

## Nasazení aplikací

Aplikace ze Storu se nasazují stejně jako všechny ostatní aplikace v Intune. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Když nasadíte aplikaci z Windows Storu pro firmy, každý uživatel, který si ji nainstaluje, využije jednu licenci. Když využijete všechny dostupné licence nasazené aplikace, už nebudete moct nasadit žádné další kopie a musíte provést některý z těchto kroků:
* Odinstalovat aplikaci z některých zařízení
* Snížit rozsah aktuálního nasazení tak, aby jeho cílem byli jenom uživatelé, pro které máte dostatek licencí
* Zakoupit ve Windows Storu pro firmy další kopie aplikace


### Související témata
[Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=May16_HO2-->


