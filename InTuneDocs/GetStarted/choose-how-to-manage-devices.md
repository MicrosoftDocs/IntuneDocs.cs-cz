---
title: "Volba způsobu správy zařízení | Microsoft Intune"
description: "Přečtěte si o různých způsobech, jakými můžete registrovat a spravovat zařízení."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: fccdf689868dbb181a171328fb7a8d186b9cb309


---

# <a name="choose-how-to-manage-devices"></a>Volba způsobu správy zařízení

Abyste mohli využívat mnoho funkcí, které služba Intune nabízí (například nasazení aplikaci nebo ovládání nastavení zařízení), musí být vaše zařízení *spravované*. Způsob správy zařízení záleží na tom, jaké možnosti služby Intune chcete používat.
Toto téma vám pomůže rozhodnout, která metoda nejlépe odpovídá vašim potřebám.

Pokud chcete spravovat zařízení se systémem iOS, Mac OS X, Android nebo Windows Phone, musíte je *zaregistrovat*.

U správy počítačů se systémem Windows máte dvě možnosti:

1. Zaregistrovat zařízení, **nebo**
2. nainstalovat *klientský software Intune*.

## <a name="decide-which-method-to-use"></a>Rozhodněte, kterou metodu použít
Použijte tento postup rozhodování k určení, jak budou vaše zařízení spravována.

![Postup rozhodování, jak budou vaše zařízení spravována.](./media/choose-manage-method.png)

Pokud chcete získat co nejvíce funkcí, zaregistrujte počítače s Windows. Klientský software Intune ale může vašim potřebám lépe odpovídat, pokud budou splněny tyto podmínky:

- Počítač používá systém Windows 7
- Chcete spravovat aktualizace softwaru systému Windows a využití licencí
- Ke správě malwaru chcete používat Endpoint Protection a bránu Windows Firewall
- Chcete uživatelům poskytovat vzdálenou pomoc přes software TeamViewer


Podrobné informace o možnostech, jaké vám každá z těchto metod propůjčuje, najdete v tématu [Možnosti správy mobilních zařízení](mobile-device-management-capabilities-in-microsoft-intune.md) a [Možnosti klientského softwaru Intune PC](windows-pc-management-capabilities-in-microsoft-intune.md).
Informace o zařízení a počítačích, které Intune podporuje, najdete v části [Podporovaná mobilní zařízení a počítače](/intune/get-started/supported-mobile-devices-and-computers)


## <a name="exchange-activesync-management"></a>Správa Exchange ActiveSync
Kromě registrace zařízení nebo instalace klientského softwaru Intune můžete zařízení spravovat i přes [protokol Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune). Tato metoda vyžaduje instalaci konektoru On-Premises Connector nebo použití integrovaného konektoru Service to Service Connector pro připojení k Exchange Serveru.
Toto je sice třetí možnost správy zařízení, ale ve srovnání s jinými metodami poskytuje jen omezené možnosti.


## <a name="next-steps"></a>Další kroky

- [Volba způsobu registrace mobilních zařízení](/intune/get-started/choose-how-to-enroll-devices1)
- [Správa počítačů s Windows pomocí klientského počítačového softwaru Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)



- [Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



<!--HONumber=Nov16_HO4-->


