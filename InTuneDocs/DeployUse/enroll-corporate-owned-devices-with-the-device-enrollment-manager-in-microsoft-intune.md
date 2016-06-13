---
# required metadata

title: Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Přihlášení firemních zařízení pomocí manažera registrace zařízení v Microsoft Intune
Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *manažera registrace zařízení* je speciální účet Intune s oprávněním přihlásit víc než pět zařízení. Manažerovi nebo vedoucímu obchodu třeba můžete přidělit uživatelský účet manažera registrace zařízení, který mu pomůže s následujícím:

-   Registrace zařízení v Intune

-   Přihlášení k firemnímu portálu pro získání podnikových aplikací

-   Instalace a odinstalace softwaru

-   Konfigurace přístupu k datům společnosti


**Příklady situací se správcem registrace zařízení:** Restaurace chce pro své číšníky pořídit tablety POS a monitory na objednávky pro pracovníky kuchyně. Zaměstnanci nikdy nepotřebují přístup k podnikovým datům ani se nemusí přihlašovat jako uživatelé. Správce Intune vytvoří účet manažera registrace zařízení a zaregistruje zařízení vlastněná společností pomocí tohoto účtu. Správce taky může manažerovi registrace zařízení udělit pověření manažera restaurace, které mu umožňuje registrovat a spravovat zařízení.

Správce nebo manažer může do zařízení restaurace nasadit aplikace specifické pro role. Správce taky může vybrat zařízení v konzole služby Intune a vyřadit ho ze správy mobilních zařízení pomocí konzoly pro správu.

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení (DEM) mají následující omezení:
  - Neexistuje konkrétní uživatel, takže všechna zařízení jsou „bez uživatele“. Proto není přístup k e-mailu nebo datům společnosti, i když například síť VPN může stále poskytovat aplikace pro zařízení s přístupem k datům.
  - Neexistuje podmíněný přístup, protože se jedná o scénáře pro uživatele.
  - Zařízení nejde resetovat z portálu společnosti.
  - Nejsou k dispozici aplikace v rámci programu Apple Volume Purchase Program (VPP), protože jsou pro správu aplikací vyžadována Apple ID na uživatele.
  - Nelze také provést registraci pomocí Apple Configuratoru nebo programu Apple Device Enrollment Program (zařízení s iOS).

> [!NOTE]
> Uživatelské účty manažera registrace zařízení s víc než 20 registrovanými zařízeními můžou mít problém při používání aplikace portálu společnosti. Pokud chcete nasadit aplikace společnosti na zařízení spravovaná manažerem registrace zařízení, nasaďte aplikace portálu společnosti jako **požadovanou instalaci** pro uživatelský účet manažera registrace zařízení.
> Aby se zvýšil výkon, při zobrazení aplikace Portál společnosti na zařízení DEM se zobrazí pouze místní zařízení, a to jen v případě, že bylo zaregistrováno pomocí aplikace Portál společnosti. Vzdálenou správu jiných zařízení DEM lze provést jenom v konzole Intune.

## Vytvoření účtů správce registrace zařízení
Účty manažera registrace zařízení jsou uživatelské účty s oprávněním registrovat velká množství zařízení vlastněných společností. Manažeři registrace zařízení můžou být jenom uživatelé v konzole Intune.

#### Přidání správce registrace zařízení do služby Intune

1.  Přejděte na [portál účtů Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) a přihlaste se k účtu správce.

2.  Klikněte na **Přidat uživatele**.

3.  Ověřte, že je uvedený uživatelský účet, který bude manažer registrace zařízení. Pokud ne, přidejte uživatele kliknutím na **Nový** a dokončením procesu přidání uživatele. Každý uživatel, který službu používá, potřebuje licenci předplatného a *manažer registrace zařízení* nemůže být správce Intune. Určete, jestli před používáním této funkce budete muset přidat další licence.

4.  Přihlaste se ke [konzole pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

5.  V navigačním podokně klikněte na **Správce**, přejděte na **Správa správců** a vyberte **Manažer registrace zařízení**. Otevře se stránka manažera registrace zařízení.

6.  Klikněte na **Přidat...**. Otevře se dialog **Přidat manažera registrace zařízení** .

7.  Zadejte **ID uživatele** účtu Intune a klikněte na **OK**. Manažer registrace zařízení nemůže být správce služby Intune.

8.  Manažer registrace zařízení teď může registrovat mobilní zařízení stejným postupem, jaký používá koncový uživatel ve scénáři BYOD na podnikovém portálu.

## Odstranění manažera registrace zařízení ze služby Intune

1.  Přihlaste se na [portál pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

2.  V navigačním podokně klikněte na **Správce** , přejděte na **Správa správců** a vyberte **Manažer registrace zařízení**. Otevře se stránka manažera registrace zařízení.

3.  Vyberte **uživatele** – manažera registrace zařízení, kterého chcete odstranit, a klikněte na **Odstranit**. Uživatel se neodstraní ze služby Intune a zařízení, která spravuje, zůstanou v Intune zaregistrovaná. Odstranění manažera registrace zabrání tomuto uživateli registrovat v Intune víc zařízení.

4.  Kliknutím na **Ano** potvrďte, že chcete odstranit manažera registrace zařízení.

Odstranění manažera registrace zařízení nemá vliv na zaregistrovaná zařízení. Po odstranění manažera registrace zařízení:

-   Nejsou ovlivněná žádná zaregistrovaná zařízení.

-   Zaregistrovaná zařízení jsou dál plně spravovaná.

-   Přihlašovací údaje účtu manažera registrace zařízení jsou dál platné pro přihlašování na podnikový portál pro přístup k aplikacím

-   Přihlašovací údaje účtu manažera registrace zařízení dál nejde používat k mazání nebo vyřazování zařízení

-   Vztah odstraněného účtu manažera registrace zařízení k zaregistrovaným zařízením trvá, ale nebudou se registrovat žádná další zařízení.


<!--HONumber=May16_HO3-->


