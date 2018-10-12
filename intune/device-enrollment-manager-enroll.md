---
title: Registrace zařízení pomocí účtu správce registrace zařízení
titlesuffix: Microsoft Intune
description: Naučte se používat účet správce registrace zařízení k registraci zařízení v Intune. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e0d8d6aba74a37d1c07fa8445aa98adf5943be2
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141605"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Registrace zařízení pomocí účtu správce registrace zařízení

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *správce registrace zařízení* (DEM – Device Enrollment Manager) je speciální uživatelský účet, který může zaregistrovat až 1 000 zařízení. Do účtu DEM můžete přidat existující uživatele a udělit jim tak speciální možnosti DEM. Každé zaregistrované zařízení používá jednu licenci. Zařízení zaregistrovaná pomocí účtu správce registrace zařízení doporučujeme používat jako sdílená zařízení, nikoli jako osobní zařízení („BYOD“).  

Abyste mohli uživatele přidat jako správce registrace zařízení, musí tito uživatelé existovat na portálu [Azure Portal](https://portal.azure.com). Z důvodu optimálního zabezpečení by uživatel DEM neměl být současně i správcem Intune.

>[!NOTE]
>Metodu registrace pomocí správce registrace zařízení (DEM) nejde použít s těmito dalšími metodami registrace: [Apple Configurator s Pomocníkem s nastavením](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator s přímou registrací](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) nebo [Program registrace zařízení (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Příklad scénáře využití správce registrace zařízení

Restaurace chce pro své číšníky pořídit padesát tabletů POS a monitory na objednávky pro pracovníky kuchyně. Zaměstnanci nikdy nepotřebují přístup k datům společnosti a nepotřebují se přihlašovat jako uživatelé. Správce Intune vytvoří nový účet správce registrace zařízení pro nadřízeného restaurace.  Tento účet je oddělený od primárního účtu nadřízeného a používá se jen k registraci sdílených zařízení v Intune. Nadřízený nyní může zaregistrovat padesát zařízení pomocí přihlašovacích údajů DEM.

Správci registrace zařízení můžou být jen uživatelé na portálu [Azure Portal](https://portal.azure.com). Správce registrace zařízení nemůže být správcem služby Intune.

Uživatel DEM může:

-   Zaregistrovat v Intune až 1 000 zařízení
-   Přihlásit se k webu Portál společnosti a získat firemní aplikace
-   Konfigurovat přístup k datům společnosti tak, že na tablety nasadí aplikace specifické pro jednotlivé role

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Omezení zařízení zaregistrovaných pomocí účtu DEM

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení mají následující omezení:

  - Není možný přístup pro konkrétní uživatele. Zařízení nemají přiřazeného uživatele, takže ze zařízení není možný přístup k e-mailu nebo firemním datům. Konfigurace VPN však mohou aplikacím zařízení stále poskytovat přístup k datům.
  - Uživatel DEM nemůže přes Portál společnosti zrušit registraci zařízení zaregistrovaného pomocí účtu DEM. Správce Intune může registraci zrušit.
  - V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.
  - Uživatelé nemůžou používat aplikace v rámci programu Apple VPP (Volume Purchase Program) s využitím uživatelských licencí, protože ke správě těchto aplikací jsou vyžadovaná Apple ID jednotlivých uživatelů.
  - (Pouze iOS) Pokud pomocí DEM zaregistrujete zařízení s iOSem, nemůžete k registraci zařízení využít Apple Configurator, Program registrace zařízení Apple (DEP) ani Apple School Manager (ASM). To znamená, že nemůžete zařízení dát do režimu dohledu, takže nebudete mít přístup k některým možnostem konfigurace.
  - (Pouze Android) Počet zařízení s pracovním profilem Androidu, která lze zaregistrovat pomocí jednoho účtu DEM, je omezený. Pro každý účet DEM je možné zaregistrovat až 10 zařízení s pracovním profilem Androidu. Toto omezení se nevztahuje na registrace starších verzí Androidu.
  - Zařízení můžou instalovat aplikace VPP, pokud mají licence na zařízení.
  - K používání DEM se nevyžaduje licence zařízení Intune. Další informace o [uživatelských licencích a licencích na zařízení](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Firemní aplikace můžete nasadit na zařízení, která spravuje správce registrace zařízení. Nasaďte aplikaci Portál společnosti jako **požadovanou instalaci** do uživatelského účtu správce registrace zařízení.
> Kvůli zvýšení výkonu se při zobrazení aplikace Portál společnosti v zařízení správce registrace zařízení zobrazuje pouze místní zařízení. Vzdálenou správu jiných zařízení správce registrace zařízení lze provádět jenom v konzole pro správu Intune.


## <a name="add-a-device-enrollment-manager"></a>Přidání správce registrace zařízení

1.  V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Správci registrace zařízení**.

2.  Vyberte **Přidat**.

3.  V okně **Přidat uživatele** zadejte hlavní název uživatele (UPN) pro uživatele DEM a vyberte **Přidat**. Uživatel DEM se přidá do seznamu uživatelů DEM.

## <a name="permissions-for-dem"></a>Oprávnění pro DEM

Role globálního správce nebo správce služby Intune v Azure AD je potřeba
- k provádění úloh souvisejících s registrací DEM na Portálu pro správu,
- k zobrazení všech uživatelů DEM, bez ohledu na oprávnění RBAC, která jsou uvedená a dostupná v rámci vlastní role uživatele.

Uživatel, který nemá přiřazenou roli globálního správce nebo správce služby Intune, ale který má oprávnění ke čtení pro roli Správci registrace zařízení, může zobrazit jenom uživatele DEM, které vytvořil. Podpora role RBAC pro tyto funkce bude oznámena v budoucnu.


## <a name="remove-a-device-enrollment-manager"></a>Odebrání správce registrace zařízení

Po odebrání správce registrace zařízení nastane tento stav:

-   Zaregistrovaná zařízení nejsou nijak ovlivněná a jsou dál plně spravovaná.
-   Přihlašovací údaje odebraného účtu DEM jsou stále platné.
-   Odebraný DEM nemůže stále vymazávat nebo vyřazovat zařízení.
-   Odebraný DEM může registrovat počet zařízení jenom do limitu pro konkrétního uživatele, který nakonfiguroval správce Intune.

**Odebrání správce registrace zařízení**

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** a potom zvolte **Správci registrace zařízení**.
2. V okně **Správci registrace zařízení** vyberte uživatele DEM a pak vyberte **Odstranit**.

