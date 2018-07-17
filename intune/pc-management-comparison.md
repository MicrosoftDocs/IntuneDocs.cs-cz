---
title: Porovnání možností správy počítačů s Windows
titlesuffix: Microsoft Intune
description: Registrace zařízení s iOSem vlastněných společností pomocí Programu registrace zařízení Apple (DEP) nebo nástroje Apple Configurator
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 0643c9aaff2a795fa44a8ed6cac09cf143c4ce56
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310466"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Porovnání správy počítačů s Windows jako počítačů nebo jako mobilních zařízení

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Organizace mohou v Microsoft Intune spravovat počítače s Windows buď jako mobilní zařízení prostřednictvím správy mobilních zařízení (MDM), nebo jako počítače se softwarovým klientem Intune.  Microsoft zákazníkům doporučuje, aby pokud možno používali řešení pro správu MDM. Kvůli lepšímu pochopení rozdílů mezi těmito možnostmi vám nabízíme následující tabulku, která obě možnosti správy srovnává.

|**Funkce/scénář** |**Windows jako počítač**<br>softwarový klient Intune | **Windows jako mobilní zařízení**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Operační systémy** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Podpora portálu Intune** |[Konzola Silverlight](https://manage.microsoft.com)|[Azure Portal](https://portal.azure.com) |
|**Podmíněný přístup**|Není k dispozici|K dispozici <br>[Co je podmíněný přístup?](conditional-access.md)|
|**Hromadná registrace**|Není k dispozici|K dispozici <br>[Hromadná registrace zařízení s Windows](windows-bulk-enroll.md)|
|**Profily zařízení**|Není k dispozici|K dispozici <br>[Co jsou profily zařízení v Microsoft Intune?](device-profiles.md)|
|**Registrace bez agenta**|Není k dispozici |K dispozici<br>[Registrace zařízení s Windows](windows-enroll.md)|
|**Správa aktualizací softwaru**| Aktualizace Windows a aplikací od Microsoftu<br>[Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Microsoft Store pro firmy pro aktualizace Windows 10 a aktualizace aplikací od Microsoftu<br> [Konfigurace nastavení služby Windows Update pro firmy](windows-update-for-business-configure.md) |
|**Správa softwarových licencí**|K dispozici <br>[Správa licenčních smluv na software počítačů s Windows](manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Microsoft Store pro firmy (pouze aplikace .appx)<br>[Správa aplikací koupených z Microsoft Storu pro firmy](windows-store-for-business.md)|
|**Inventář**|K dispozici <br>[Zobrazení inventáře hardwaru a softwaru pro počítače s Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|K dispozici <br>[Jak monitorovat informace o aplikacích](apps-monitor.md)<br>[Co je správa zařízení?](device-management.md)|
|**Zásady brány Windows Firewall**|K dispozici <br>[Pomoc při ochraně počítačů s Windows pomocí zásad brány Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |K dispozici <br>[Firewall v programu Windows Defender](endpoint-protection-windows-10.md#windows-defender-firewall)|
|**Ochrana proti malwaru**|Funkce Endpoint Protection<br>[Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Windows Defender<br>[Povolení Windows Defenderu](advanced-threat-protection.md)|
|**Vzdálená pomoc** |TeamViewer<br>[Žádost o poskytnutí vzdálené pomoci na počítačích s Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Vzdálená správa zařízení s Intune pomocí TeamVieweru](device-profile-android-teamviewer.md) |
|**Nasazení aplikací** | Není k dispozici pro Microsoft Store pro firmy,<br>jenom .exe, .appx a vícesouborové .msi<br>[Přidání aplikací pro počítače s Windows, na kterých běží softwarový klient Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)|K dispozici pro aplikace z Microsoft Storu a pro podnikové aplikace<br>[Přidání aplikací pro Windows Store](store-apps-windows.md)<br>[Přidání obchodních aplikací (LOB) pro Windows](lob-apps-windows.md)|
|**Ochrana aplikací**|Není k dispozici|K dispozici <br>[Co jsou zásady ochrany aplikací?](app-protection-policy.md)|
|**Ověření stavu**|Není k dispozici|K dispozici|


### <a name="advantages-of-mdm-windows-pc-management"></a>Výhody správy počítačů s Windows v řešení MDM
Správa počítačů s Windows s využitím moderní správy mobilních zařízení přináší následující výhody:
- **Škálovatelnost** – řešení MDM je díky cloudové správě Intune škálovatelné. Softwarový klient Intune je omezený na 7000 počítačů.
- **Jednoduchost** – používá moderní funkce správy, které jsou součástí operačního systému, bez spoléhání se na staženého softwarového klienta.
- **Konzistence** – počítače s Windows se v organizaci spravují jako všechna ostatní mobilní zařízení. <!-- - **Cloud optimization** - -->