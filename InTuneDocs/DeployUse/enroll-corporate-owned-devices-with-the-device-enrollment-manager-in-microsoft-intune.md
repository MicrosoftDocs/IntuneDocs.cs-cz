---
title: "Registrace pomocí správce registrace zařízení | Microsoft Intune"
description: "Účet správce registrace zařízení (DEM) služby Microsoft Intune umožňuje spravovat velké počty sdílených mobilních zařízení vlastněných společností pomocí jediného uživatelského účtu."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 5c7eecf5b7801eca3d23dd0eee954203e9c9cb06


---


# Přihlášení firemních zařízení pomocí manažera registrace zařízení v Microsoft Intune
Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *správce registrace zařízení* je speciální účet Intune s oprávněním přihlásit až 1000 zařízení. Zařízení zaregistrovaná pomocí účtu správce registrace zařízení používejte jako sdílená zařízení, nikoli jako osobní zařízení („BYOD“). Uživatelé například nebudou moci používat „nativní“ e-mailové aplikace. Manažerovi nebo vedoucímu obchodu třeba můžete přidělit uživatelský účet manažera registrace zařízení, který mu pomůže s následujícím:

-   Registrace zařízení v Intune

-   Přihlášení k firemnímu portálu pro získání podnikových aplikací

-   Instalace a odinstalace softwaru

-   Konfigurace přístupu k datům společnosti


**Příklady situací se správcem registrace zařízení:** Restaurace chce pro své číšníky pořídit tablety POS a monitory na objednávky pro pracovníky kuchyně. Zaměstnanci nikdy nepotřebují přístup k podnikovým datům ani se nemusí přihlašovat jako uživatelé. Správce Intune vytvoří účet manažera registrace zařízení a zaregistruje zařízení vlastněná společností pomocí tohoto účtu. Správce taky může manažerovi registrace zařízení udělit pověření manažera restaurace, které mu umožňuje registrovat a spravovat zařízení.

Správce nebo manažer může do zařízení restaurace nasadit aplikace specifické pro role. Správce taky může vybrat zařízení v konzole služby Intune a vyřadit ho ze správy mobilních zařízení pomocí konzoly pro správu.

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení mají následující omezení:
  - Neexistuje konkrétní uživatel, takže všechna zařízení jsou „bez uživatele“. Proto není přístup k e-mailu nebo datům společnosti, i když například síť VPN může stále poskytovat aplikace pro zařízení s přístupem k datům.
  - Neexistuje podmíněný přístup, protože se jedná o scénáře pro uživatele.
  - Zařízení nejde resetovat z portálu společnosti.
  - V aplikaci nebo na webu Portál společnosti se zobrazí pouze místní zařízení.
  - Nejsou k dispozici aplikace v rámci programu Apple Volume Purchase Program (VPP), protože jsou pro správu aplikací vyžadována Apple ID na uživatele.
  - Nelze také provést registraci pomocí Apple Configuratoru nebo programu Apple Device Enrollment Program (zařízení s iOS).

> [!NOTE]
> Pokud chcete nasadit aplikace společnosti na zařízení spravovaná manažerem registrace zařízení, nasaďte aplikace portálu společnosti jako **požadovanou instalaci** pro uživatelský účet manažera registrace zařízení.
> Kvůli zvýšení výkonu se při zobrazení aplikace Portál společnosti v zařízení správce registrace zařízení zobrazuje pouze místní zařízení. Vzdálenou správu jiných zařízení správce registrace zařízení lze provádět jenom v konzole správce Intune.

## Vytvoření účtů správce registrace zařízení
Účty manažera registrace zařízení jsou uživatelské účty s oprávněním registrovat velká množství zařízení vlastněných společností. Manažeři registrace zařízení můžou být jenom uživatelé v konzole Intune.

#### Přidání správce registrace zařízení do služby Intune

1.  Přejděte na [portál účtů Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) a přihlaste se k účtu správce.

2.  Zvolte **Přidat uživatele**.

3.  Ověřte, že je uvedený uživatelský účet, který bude manažer registrace zařízení. Pokud ne, přidejte uživatele zvolením možnosti **Nový** a dokončením procesu přidání uživatele. Každý uživatel, který službu používá, potřebuje licenci předplatného a *manažer registrace zařízení* nemůže být správce Intune. Určete, jestli před používáním této funkce budete muset přidat další licence.

4.  Přihlaste se ke [konzole pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

5.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka manažera registrace zařízení.

6.  Zvolte **Přidat**. Otevře se dialog **Přidat manažera registrace zařízení** .

7.  Zadejte **ID uživatele** účtu Intune a zvolte **OK**. Manažer registrace zařízení nemůže být správce služby Intune.

8.  Manažer registrace zařízení teď může registrovat mobilní zařízení stejným postupem, jaký používá koncový uživatel ve scénáři BYOD na podnikovém portálu.

## Odstranění manažera registrace zařízení ze služby Intune

1.  Přihlaste se na [portál pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

2.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka manažera registrace zařízení.

3.  V poli **Uživatel** vyberte uživatele správce registrace zařízení, kterého chcete odstranit, a pak zvolte **Odstranit**. Uživatel se neodstraní ze služby Intune a zařízení, která spravuje, zůstanou v Intune zaregistrovaná. Odstranění manažera registrace zabrání tomuto uživateli registrovat v Intune víc zařízení.

4.  Zvolením **Ano** potvrďte, že chcete správce registrace zařízení odstranit.

Odstranění manažera registrace zařízení nemá vliv na zaregistrovaná zařízení. Po odstranění manažera registrace zařízení:

-   Nejsou ovlivněná žádná zaregistrovaná zařízení.

-   Zaregistrovaná zařízení jsou dál plně spravovaná.

-   Přihlašovací údaje účtu manažera registrace zařízení jsou dál platné pro přihlašování na podnikový portál pro přístup k aplikacím

-   Přihlašovací údaje účtu manažera registrace zařízení dál nejde používat k mazání nebo vyřazování zařízení

-   Vztah odstraněného účtu manažera registrace zařízení k zaregistrovaným zařízením trvá, ale nebudou se registrovat žádná další zařízení.



<!--HONumber=Jul16_HO3-->


