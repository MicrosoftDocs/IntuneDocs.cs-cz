---
title: "Podporovaná zařízení – Microsoft Intune"
description: "Seznam podporovaných platforem zařízení a prohlížečů pro správu zařízení přes Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b168cbf5282b4e016133d071c56c8abd54c2e23b
ms.sourcegitcommit: dc2595bec05206a826cd10cb834bf6043145c917
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/14/2017
---
# <a name="supported-devices-and-browsers"></a>Podporovaná zařízení a prohlížeče

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Tento článek je určený pro správce systému, kteří se v podniku starají o zařízení. Nápovědu k instalaci Intune do telefonu najdete v článku [Práce pomocí spravovaných zařízení](/intune-user-help/company-portal-frequently-asked-questions).

Než začnete s nastavováním Microsoft Intune, projděte si následující požadavky:

- [Podporovaná zařízení a počítače](#intune-supported-devices)
- [Seznam podporovaných webových prohlížečů k používání Intune](#intune-supported-web-browsers)

Měli byste se také seznámit s [využitím šířky pásma Intune](network-bandwidth-use.md) ([klasický portál](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Zařízení podporovaná pro Intune

Pomocí správy mobilních zařízení Intune můžete spravovat následující zařízení:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Podporovaná zařízení Samsung KNOX Standard

Během registrace MDM se aplikace Portál společnosti pokusí aktivovat Samsung KNOX jenom v případě, že je zařízení uvedené v [seznamu podporovaných zařízení KNOX](https://www.samsungknox.com/knox-supported-devices/knox-workspace). To pomáhá předejít chybám aktivace KNOX, které brání v registraci MDM. Zařízení, která nepodporují aktivaci Samsung KNOX, se zaregistrují jako standardní zařízení s Androidem. Některá čísla modelů zařízení Samsung mohou podporovat KNOX, některá nemusí. Než si zařízení Samsung koupíte a nasadíte, ověřte si u prodejce, zda je vaše zařízení kompatibilní se systémem KNOX.

Následující modely zařízení Samsung nepodporují KNOX a aplikace Portál společnosti pro Android je nezaregistruje jako nativní zařízení s Androidem:

| **Název zařízení** | **Číslo modelu zařízení** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110F |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Intune se nedá použít ke správě operačních systémů Windows Server.

### <a name="windows-pc-software-client"></a>Softwarový klient pro počítače s Windows

Jako alternativní metodu registrace jde na počítače s Windows nasadit a nainstalovat [softwarového klienta Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune). Tato funkce je dostupná jen při používání klasického portálu Intune. Softwarového klienta Intune můžete použít ke správě počítačů s Windows 7 a novějšími s výjimkou Windows 10 Home.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Podporované webové prohlížeče Intune

Různé úlohy správy vyžadují, abyste použili některý z následujících webů pro správu.

- [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

Portály podporují následující prohlížeče:
- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

### <a name="intune-classic-portal"></a>Klasický portál Intune

Funkce klasického Intune, jako je softwarový počítačový klient Intune a integrace partnerů MTD (Mobile Threat Defense), jsou dostupné jen na klasickém portálu Intune (https://manage.microsoft.com). Klasický portál Intune vyžaduje, aby prohlížeč podporoval Silverlight.

Konzolu Intune podporují následující prohlížeče vybavené technologií Silverlight:
- Internet Explorer 10 nebo novější
- Google Chrome (verze starší než verze 42)
- Mozilla Firefox se zapnutým doplňkem Silverlight [Další informace](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Klasický portál Intune nepodporuje Microsoft Edge ani mobilní prohlížeče, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

K tomuto portálu se můžou přihlásit jen uživatelé, kteří mají oprávnění správce služeb nebo jsou správcem tenanta s rolí globálního správce. Abyste získali přístup ke konzole pro správu, musí mít váš účet licenci k používání Intune a stav registrace **Povoleno**.
