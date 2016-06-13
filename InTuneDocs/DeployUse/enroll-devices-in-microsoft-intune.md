---
# required metadata

title: Registrace zařízení | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrace zařízení pro správu v Intune
Správa mobilních zařízení Microsoft Intune (MDM) využívá registraci pro zajištění správy zařízení a povolení přístupu k prostředkům. Způsob registrace zařízení závisí na jeho typu, vlastnictví a požadované úrovni správy. Scénáře pro zařízení vlastněná společností (COD) a Přineste si vlastní zařízení (BYOD) vyžadují proces registrace. Organizace, které využívají protokol Exchange ActiveSync, ať už místní, nebo hostovaný v cloudu, mohou povolit jednodušší správu bez požadavků na registraci. Pomocí klientského softwaru Intune je také možné spravovat počítače s Windows.

###  Podporované platformy zařízení

Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Povolení registrace zařízení  
 Registrace umožňuje uživatelům přistupovat k prostředkům společnosti z jejich osobních zařízení a správcům umožňuje zajistit, že tato zařízení dodržují zásady, které chrání prostředky společnosti. Toto je nejlepší způsob, jak pro Intune povolit scénáře Přineste si vlastní zařízení. Správce musí povolit registraci pomocí konzoly Intune. Může to vyžadovat vytvoření vztahu důvěryhodnosti se zařízením a přiřazení licencí uživatelům. Zařízení se pak zaregistruje, obvykle uživatelem, který zadá přihlašovací údaje svého pracovního nebo školního účtu. Potom zařízení obdrží zásady ze služby Intune a získá přístup k prostředkům.

[Příprava registrace zařízení v Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrace zařízení vlastněných společností
Zařízení vlastněná společností (COD) je možné spravovat pomocí konzoly Intune. Zařízení s iOS se mohou zaregistrovat přímo pomocí nástrojů poskytovaných společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

[Registrace zařízení vlastněných společností](manage-corporate-owned-devices.md)

## Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune využívá Exchange Connector ke komunikaci s protokolem EAS, ať už místním, nebo hostovaným v cloudu.



[Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Správa počítačů s Windows pomocí Intune  
Microsoft Intune můžete také využít ke správě počítačů se systémem Windows, a to pomocí klientského softwaru Intune pro počítače s Windows. Počítače spravované pomocí Intune mohou:

 - Vytvářet sestavy inventáře softwaru a hardwaru
 - Instalovat desktopové aplikace (například soubory .exe a .msi)
 - Nastavení brány firewall

Počítače spravované pomocí klientského softwaru Intune nejde selektivně vymazat nebo vyřadit. Nemohou také využívat řadu funkcí správy Intune, jako je třeba podmíněný přístup, nastavení připojení VPN a Wi-Fi nebo nasazení certifikátů a konfigurací e-mailu.

[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO4-->


