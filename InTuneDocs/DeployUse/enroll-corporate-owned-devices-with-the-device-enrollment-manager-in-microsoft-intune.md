---
title: "Registrace pomocí správce registrace zařízení | Microsoft Intune"
description: "Účet správce registrace zařízení (DEM) umožňuje spravovat velké počty sdílených mobilních zařízení vlastněných společností z jediného uživatelského účtu."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 51e5f248c5e8759d5992918a99e1f114e2614142


---


# <a name="enroll-corporateowned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune
Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet *správce registrace zařízení* je speciální účet Intune, který může registrovat až 1000 zařízení. Zařízení zaregistrovaná pomocí účtu správce registrace zařízení doporučujeme používat jako sdílená zařízení, nikoli jako osobní zařízení („BYOD“). Uživatelé například nebudou moci používat „nativní“ e-mailové aplikace.

Uživatelský účet správce registrace zařízení můžete například přiřadit manažerovi nebo vedoucímu obchodu, aby mohli provádět následující:

-   Zaregistrovat zařízení v Intune.

-   Přihlásit se k webu Portál společnosti a získat firemní aplikace.

-   Instalovat a odinstalovat software.

-   Konfigurovat přístup k datům společnosti.


**Scénáře situací se správcem registrace zařízení:** Restaurace chce pro své číšníky pořídit tablety pro zadávání objednávek u stolů a pro pracovníky kuchyně monitory pro zobrazení objednávek. Zaměstnanci nikdy nepotřebují přístup k datům společnosti a nepotřebují se přihlašovat jako uživatelé. Správce Intune vytvoří účet správce registrace zařízení a pomocí tohoto účtu zaregistruje zařízení vlastněná společností. Správce taky může přihlašovací údaje správce registrace zařízení dát manažerovi restaurace, což mu umožní registrovat a spravovat zařízení.

Správce nebo manažer může do zařízení restaurace nasadit aplikace pro konkrétní role. Správce taky může vybrat určité zařízení v konzole služby Intune a vyřadit ho ze správy mobilních zařízení pomocí konzoly pro správu.

Zařízení zaregistrovaná pomocí účtu správce registrace zařízení mají následující omezení:
  - Neexistuje žádný konkrétní uživatel zařízení – proto neexistuje ani žádný přístup k e-mailům nebo datům společnosti. Sítě VPN však mohou aplikacím zařízení stále poskytovat přístup k datům.
  - Není možný podmíněný přístup, protože u podmíněného přístupu se jedná o scénáře pro konkrétní uživatele.
  - Zařízení nejde resetovat ze služby Portál společnosti.
  - V aplikaci nebo na webu Portál společnosti se zobrazí jenom místní zařízení.
  - Nemůžou používat aplikace v rámci programu Apple VPP (Volume Purchase Program), protože ke správě těchto aplikací jsou vyžadovaná Apple ID jednotlivých uživatelů.
  - (iOS) Nedají se taky zaregistrovat přes Apple Configurator ani Apple Device Enrollment Program (DEP), ale zařízení spravovaná programem DEP nebo Apple Configuratorem se dají zaregistrovat bez přidružení uživatele.

> [!NOTE]
> Pokud chcete nasadit aplikace společnosti na zařízení spravovaná správcem registrace zařízení, nasaďte aplikaci Portál společnosti jako **požadovanou instalaci** na uživatelský účet správce registrace zařízení.
> Kvůli zvýšení výkonu se při zobrazení aplikace Portál společnosti v zařízení správce registrace zařízení zobrazuje pouze místní zařízení. Vzdálenou správu jiných zařízení správce registrace zařízení lze provádět jenom v konzole správce Intune.

## <a name="create-device-enrollment-manager-accounts"></a>Vytvoření účtů správce registrace zařízení
Účty správce registrace zařízení jsou uživatelské účty s oprávněním registrovat velká množství zařízení vlastněných společností. Správci registrace zařízení můžou být jenom uživatelé v konzole Intune.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Přidání správce registrace zařízení do služby Intune

1.  Přejděte na [portál účtů Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=698854) a přihlaste se k účtu správce.

2.  Zvolte **Přidat uživatele**.

3.  Ověřte, že je uvedený uživatelský účet, který bude správcem registrace zařízení. Pokud není, přidejte uživatele zvolením možnosti **Nový** a potom dokončením procesu **Přidat uživatele**. Každý uživatel, který přistupuje k službě, musí mít předplacenou licenci. Správce registrace zařízení nemůže být správcem služby Intune. Před použitím této funkce zkontrolujte, jestli nepotřebujete přidat další licence.

4.  Přihlaste se ke [konzole pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

5.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka **Správci registrace zařízení**.

6.  Zvolte **Přidat**. Otevře se dialog **Přidat správce registrace zařízení** .

7.  Zadejte **ID uživatele** účtu Intune a zvolte **OK**. Správce registrace zařízení nemůže být správcem služby Intune.

8.  Správce registrace zařízení teď může registrovat mobilní zařízení stejným postupem, jaký používá koncový uživatel ve scénáři BYOD na webu Portál společnosti.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Odstranění správce registrace zařízení ze služby Intune

1.  Přihlaste se na [portál pro správu Microsoft Intune](http://manage.microsoft.com) pomocí přihlašovacích údajů správce.

2.  V navigačním podokně zvolte **Správce**, přejděte do části **Správa správců** a vyberte **Správce registrace zařízení**. Otevře se stránka **Správci registrace zařízení**.

3.  V poli **Uživatel** vyberte uživatele správce registrace zařízení, kterého chcete odstranit, a pak zvolte **Odstranit**. Uživatel se tím neodstraní ze služby Intune a zařízení, která spravuje, zůstanou v Intune dále zaregistrovaná. Odstranění správce registrace zabrání tomuto uživateli registrovat v Intune víc zařízení.

4.  Výběrem **Ano** potvrďte, že chcete správce registrace zařízení odstranit.

Odstranění správce registrace zařízení nemá vliv na zaregistrovaná zařízení. Po odstranění správce registrace zařízení:

-   Nejsou ovlivněná žádná zaregistrovaná zařízení.

-   Zaregistrovaná zařízení jsou dál plně spravovaná.

-   Přihlašovací údaje účtu správce registrace zařízení jsou dál platné pro přihlašování na Portál společnosti za účelem přístupu k aplikacím.

-   Přihlašovací údaje účtu správce registrace zařízení dál nejde používat k mazání nebo vyřazování zařízení.

-   Vztah odstraněného účtu správce registrace zařízení k zaregistrovaným zařízením trvá, ale nejde registrovat žádná další zařízení.



<!--HONumber=Nov16_HO1-->


