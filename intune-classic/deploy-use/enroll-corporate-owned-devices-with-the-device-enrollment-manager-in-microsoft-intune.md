---
title: "Registrace pomocí správce registrace zařízení"
description: "Účet správce registrace zařízení (DEM) umožňuje spravovat velké počty sdílených mobilních zařízení vlastněných společností z jediného uživatelského účtu."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095b89d1428d6b8f06143043d8bb6ed37fd8fa5b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *správce registrace zařízení* (DEM – Device Enrollment Manager) je speciální uživatelský účet, který může zaregistrovat až 1 000 zařízení. Do účtu DEM můžete přidat existující uživatele a udělit jim tak speciální možnosti DEM. Každé zaregistrované zařízení používá jednu licenci. Zařízení zaregistrovaná pomocí tohoto účtu doporučujeme používat jako sdílená zařízení (tedy bez přidružení uživatele), nikoli jako osobní zařízení („BYOD“).  

Abyste mohli uživatele přidat jako správce registrace zařízení, musí tito uživatelé existovat na portálu Azure Portal. Z důvodu optimálního zabezpečení by uživatel DEM neměl být současně i správcem Intune.

>[!NOTE]
>Metodu registrace DEM není možné použít s [Pomocníkem s nastavením v Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md), u [přímé registrace](ios-direct-enrollment-in-microsoft-intune.md) nebo u [metody registrace DEP](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Příklad scénáře využití správce registrace zařízení

Restaurace chce pro své číšníky pořídit padesát tabletů POS a monitory na objednávky pro pracovníky kuchyně. Zaměstnanci nikdy nepotřebují přístup k datům společnosti a nepotřebují se přihlašovat jako uživatelé. Správce Intune vytvoří účet správce registrace zařízení a přidá vedoucího restaurace k účtu DEM, čímž mu v podstatě dá nadřízené možnosti DEM. Nadřízený nyní může zaregistrovat padesát zařízení pomocí přihlašovacích údajů DEM.

Správci registrace zařízení můžou být jenom uživatelé v konzole Intune. Správce registrace zařízení nemůže být správcem služby Intune.

Uživatel DEM může:

-   Zaregistrovat v Intune až 1 000 zařízení
-   Použít aplikaci Portál společnosti k získání firemních aplikací
-   Konfigurovat přístup k datům společnosti tak, že na tablety nasadí aplikace specifické pro jednotlivé role

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Omezení zařízení zaregistrovaných pomocí účtu DEM

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení mají následující omezení:

  - Neexistuje žádný konkrétní uživatel zařízení. Z tohoto důvodu neexistuje ani žádný přístup k e-mailům nebo datům společnosti. Sítě VPN však mohou aplikacím zařízení stále poskytovat přístup k datům.

  - Není možný podmíněný přístup, protože u podmíněného přístupu se jedná o scénáře pro konkrétní uživatele.

  - Uživatel DEM nemůže přes Portál společnosti zrušit registraci zařízení zaregistrovaného pomocí účtu DEM. Tuto možnost má správce Intune, ale uživatel DEM nikoli.

  - V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.

  - Uživatelé nemůžou používat aplikace v rámci programu Apple VPP (Volume Purchase Program), protože ke správě těchto aplikací jsou vyžadovaná Apple ID jednotlivých uživatelů.

  - (Pouze iOS) Pokud pomocí DEM zaregistrujete zařízení s iOSem, nemůžete k registraci zařízení využít Apple Configurator ani Program registrace zařízení Apple (DEP).

> [!NOTE]
> Pokud chcete nasadit aplikace společnosti na zařízení spravovaná správcem registrace zařízení, nasaďte aplikaci Portál společnosti jako **požadovanou instalaci** na uživatelský účet správce registrace zařízení.
> Kvůli zvýšení výkonu se při zobrazení aplikace Portál společnosti v zařízení správce registrace zařízení zobrazuje pouze místní zařízení. Vzdálenou správu jiných zařízení správce registrace zařízení lze provádět jenom v konzole pro správu Intune.


## <a name="add-a-device-enrollment-manager"></a>Přidání správce registrace zařízení

1.  Zkontrolujte, že uživatel, kterého chcete přidat do účtu DEM, už existuje. Pokud potřebujete přidat uživatele, přihlaste se k [portálu služeb Office 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) a postupujte podle pokynů uvedených v tématu [Přidání uživatelů na portál služeb Office 365 jednotlivě nebo hromadně](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2.  Přihlaste se ke [konzole pro správu Microsoft Intune](https://manage.microsoft.com) pomocí přihlašovacích údajů správce.

3.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka **Správci registrace zařízení**.

4.  Zvolte **Přidat**. Otevře se dialog **Přidat správce registrace zařízení** .

5.  Zadejte **ID uživatele** účtu Intune a zvolte **OK**.

    Uživatel DEM teď může registrovat mobilní zařízení stejným postupem, jaký používá koncový uživatel ve scénáři BYOD na webu Portál společnosti. Koncový uživatel, který je správcem, může nainstalovat aplikaci Portál společnosti a zaregistrovat zařízení pomocí svých přihlašovacích údajů DEM až na 1000 zařízení. Postup registrace koncovým uživatelem pro jednotlivé platformy najdete v následujících tématech:

  - [Registrace zařízení s iOSem v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Registrace zařízení s macOS do Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Registrace zařízení s Androidem v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Odstranění správce registrace zařízení ze služby Intune

1.  Přihlaste se na [portál pro správu Microsoft Intune](https://manage.microsoft.com) pomocí přihlašovacích údajů správce.

2.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka **Správci registrace zařízení**.

3.  V poli **Uživatel** vyberte uživatele správce registrace zařízení, kterého chcete odstranit, a pak zvolte **Odstranit**. Uživatel se tím neodstraní ze služby Intune a zařízení, která spravuje, zůstanou v Intune dále zaregistrovaná. Odstranění správce registrace zabrání tomuto uživateli registrovat v Intune víc zařízení.

4.  Výběrem **Ano** potvrďte, že chcete správce registrace zařízení odstranit.

Odstranění správce registrace zařízení nemá vliv na zaregistrovaná zařízení. Po odstranění správce registrace zařízení:

-   Nejsou ovlivněná žádná zaregistrovaná zařízení.

-   Zaregistrovaná zařízení jsou dál plně spravovaná.

-   Přihlašovací údaje účtu správce registrace zařízení jsou dál platné pro přihlašování na Portál společnosti za účelem přístupu k aplikacím.

-   Přihlašovací údaje účtu správce registrace zařízení dál nejde používat k mazání nebo vyřazování zařízení.

-   Vztah odstraněného účtu správce registrace zařízení k zaregistrovaným zařízením trvá, ale nejde registrovat žádná další zařízení.
