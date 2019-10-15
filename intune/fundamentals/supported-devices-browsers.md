---
title: Operační systémy a prohlížeče podporované nástrojem Microsoft Intune
titleSuffix: ''
description: Seznam podporovaných platforem zařízení a prohlížečů pro správu zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d2777f2caabc24a457fc407b3e47facb1f6fc3c
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314602"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Podporované operační systémy a prohlížeče v Intune

Před nastavením Microsoft Intune zkontrolujte podporované operační systémy a prohlížeče.

Nápovědu k instalaci Intune na zařízení najdete v tématu [použití spravovaných zařízení k tomu, abyste mohli provádět práce](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) a [využití šířky pásma Intune](network-bandwidth-use.md).

Další informace o podpoře poskytovatele konfigurační služby najdete v referenčních informacích o [poskytovateli služby konfigurace](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="intune-supported-operating-systems"></a>Operační systémy podporované Intune

Můžete spravovat zařízení s následujícími operačními systémy:

[!INCLUDE [mdm-supported-devices](../../intune-classic/includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Podporovaná zařízení Samsung KNOX Standard

Aby se zabránilo chybám aktivace KNOX, které brání v registraci MDM, aplikace Portál společnosti se při registraci MDM pokusí aktivovat Samsung KNOX jenom v případě, že se zařízení objeví v [seznamu podporovaných zařízení Knox](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Zařízení, která nepodporují aktivaci Samsung KNOX, se registrují jako standardní zařízení s Androidem. Zařízení Samsung může mít několik modelů, které podporují KNOX, jiné ne. Před nákupem a nasazením zařízení Samsung ověřte kompatibilitu s vaším prodejcem zařízení.

> [!NOTE]
> Registrace zařízení Samsung KNOX může vyžadovat, abyste [povolili přístup k serverům Samsung](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers). 

Následující seznam modelů zařízení Samsung nepodporují Knox. Jsou zaregistrované jako nativní zařízení s Androidem v Portál společnosti aplikaci pro Android:

| **Název zařízení** | **Čísla modelů zařízení** |
| --- | --- |
| Galaxy značka | SM – G386T |
| Galaxy Core 2/Core 2 Duos | SM – G355H<br>SM – G355M |
| Galaxy Core Lite | SM – G3588V |
| Základní Galaxy základny | SM – G360H |
| Galaxy Core LTE | SM – G386F<br>SM – G386W |
| Galaxy Grand | GT – I9082L<br>GT – I9082<br>GT – I9080L |
| Galaxy Grand 3 | SM – G7200 |
| Galaxy Grand Neo | GT – I9060I |
| Edice Galaxy Grand Prvočísl Value | SM – G531H |
| Galaxy J max | SM – T285YD |
| Galaxy J1 | SM – J100H<br>SM – J100M<br>SM – J100ML |
| Galaxy J1 ACE | SM – J110F<br>SM – J110H |
| Galaxy J1 Mini | SM – J105M |
| Galaxy J2/J2 pro | SM – J200H<br>SM – J210F |
| Galaxy J3 | SM – J320F<br>SM – J320FN<br>SM – J320H<br>SM – J320M |
| Galaxy K přiblížení | SM – C115 |
| Galaxy světlo | SGH-T399N |
| Galaxy Poznámka 3 | SM – N9002<br>SM – N9009 |
| Galaxy Poznámka 7/Poznámka 7 Duos | SM – N930S<br>SM – N9300<br>SM – N930F<br>SM – N930T<br>SM – N9300<br>SM – N930F<br>SM – N930S<br>SM – N930T |
| Galaxy Poznámka 10,1 3G | SM – P602 |
| Galaxy S2 plus | GT – I9105P |
| Galaxy S3 Mini | SM – G730A<br>SM – G730V |
| Galaxy S3 Neo | GT – I9300<br>GT – I9300I |
| Galaxy S4 | SM – S975L |
| Galaxy S4 Neo | SM – G318ML |
| Galaxy S5 | SM – G9006W |
| Galaxy S6 Edge | 404SC |
| Karta Galaxy A 7.0 @ no__t-0 | SM – T280<br>SM – T285 |
| Galaxy Karta 3 7 @ no__t-0/Tab 3 Lite 7 @ no__t-1 | SM – T116<br>SM – T210<br>SM – T211 |
| Galaxy Karta 3 8.0 @ no__t-0 | SM – T311 |
| Galaxy Karta 3 10.1 @ no__t-0 | GT – P5200<br>GT – P5210<br>GT – P5220 |
| Galaxy trend 2 Lite | SM – G318H |
| Galaxy V plus | SM – G318HZ |
| Galaxy Young 2 Duos | SM – G130BU |


### <a name="windows-pc-software-client"></a>Klientský software pro počítače se systémem Windows

[Softwarový klient Intune](../manage-windows-pcs-with-microsoft-intune.md) se dá nasadit a nainstalovat na počítače s Windows jako alternativní metoda registrace. Tato funkce je k dispozici pouze pomocí klasického portálu Intune. Softwarového klienta Intune můžete použít ke správě počítačů s Windows 7 a novějšími s výjimkou Windows 10 Home Edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](../enrollment/device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Podporované webové prohlížeče Intune

Různé úlohy správy vyžadují, abyste použili jeden z následujících webů pro správu.

- [Centrum pro správu Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

Pro tyto portály se podporují následující prohlížeče:
- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, pouze Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)




### <a name="intune-classic-portal"></a>Klasický portál Intune

Klasický portál Intune se používá jenom ke správě zařízení zaregistrovaných pomocí klientského softwaru Intune pro počítače (https://manage.microsoft.com). Klasický portál Intune vyžaduje podporu prohlížeče Silverlight.

Konzolu Intune podporují následující prohlížeče Silverlight:
- Internet Explorer 10 nebo novější
- Google Chrome (verze starší než verze 42)
- Mozilla Firefox s povoleným programem Silverlight (verze starší než verze 56)

> [!Note]
> Microsoft Edge a mobilní prohlížeče nejsou podporované pro klasický portál Intune, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

K tomuto portálu se můžou přihlásit jenom uživatelé s oprávněními správce služeb nebo Správci klientů s rolí globálního správce. Aby bylo možné získat přístup ke konzole pro správu, musí mít váš účet licenci k používání Intune a stav přihlášení **povoleno**.
