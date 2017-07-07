---
title: "Podporovaná zařízení – Microsoft Intune"
description: "Seznam podporovaných platforem zařízení a prohlížečů pro správu zařízení přes Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: df9c4c0a0a23740bf9df4c13e34b8752838aa99a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="supported-devices-and-browsers"></a>Podporovaná zařízení a prohlížeče

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Tento článek je určený pro správce systému, kteří se v podniku starají o zařízení. Nápovědu k instalaci Intune do telefonu najdete v článku [Práce pomocí spravovaných zařízení](/intune-user-help/company-portal-frequently-asked-questions).

Než začnete s nastavováním Microsoft Intune, projděte si následující požadavky:

- [Podporovaná zařízení a počítače](#intune-supported-devices)
- [Seznam podporovaných webových prohlížečů k používání Intune](#intune-supported-web-browsers)

Měli byste se také seznámit s [využitím šířky pásma Intune](network-bandwidth-use.md) ([klasická konzola](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Zařízení podporovaná pro Intune

Pomocí správy mobilních zařízení Intune můžete spravovat následující zařízení:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Intune se nedá použít ke správě operačních systémů Windows Server.

### <a name="windows-pc-software-client"></a>Softwarový klient pro počítače s Windows

Jako alternativní metodu registrace jde na počítače s Windows nasadit a nainstalovat [softwarového klienta Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune). Tato funkce je dostupná, jen když používáte klasickou konzolu Intune. Softwarového klienta Intune můžete použít ke správě počítačů s Windows 7 a novějšími s výjimkou Windows 10 Home.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Podporované webové prohlížeče Intune

Různé úlohy správy vyžadují, abyste použili některý z následujících webů pro správu.

- [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portál Intune](https://portal.azure.com/)

Portály podporují následující prohlížeče:
- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

### <a name="intune-classic-portal"></a>Klasický portál Intune

Funkce klasického portálu Intune, jako je softwarový počítačový klient Intune a integrace partnerů MTD (Mobile Threat Defense), jsou k dispozici jen na klasickém portálu Intune (https://manage.microsoft.com). Klasická konzola Intune vyžaduje prohlížeč s podporou technologie Silverlight.

Klasickou konzolu Intune podporují následující prohlížeče vybavené technologií Silverlight:
- Internet Explorer 10 nebo novější
- Google Chrome (verze starší než verze 42)
- Mozilla Firefox se zapnutým doplňkem Silverlight [Další informace](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Klasická konzola Intune nepodporuje Microsoft Edge ani mobilní prohlížeče, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).


K tomuto portálu se můžou přihlásit jen uživatelé, kteří mají oprávnění správce služeb nebo jsou správcem tenanta s rolí globálního správce. Abyste získali přístup ke konzole pro správu, musí mít váš účet licenci k používání Intune a stav registrace **Povoleno**.
