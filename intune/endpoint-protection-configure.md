---
title: Konfigurace nastavení ochrany koncových bodů v Microsoft Intune – Azure | Microsoft Docs
description: Nastavení ochrany koncových bodů určete při vytváření profilu zařízení s macOS nebo Windows 10 v Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: cbac3627a17fb28f7ec0bf06898038a6c6001ac8
ms.sourcegitcommit: f8bbd9bac2016a77f36461bec260f716e2155b4a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65733043"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Přidání nastavení ochrany koncových bodů v Intune

S Intune můžete použít profily konfigurace zařízení ke správě běžné funkce zabezpečení na zařízeních, včetně koncového bodu ochrany:
- Brána firewall 
- BitLocker
- Povolování a blokování aplikací  
- Program Windows Defender a šifrování

Můžete například vytvořit profil ochrany koncových bodů, který umožní uživatelům macOS instalovat aplikace jenom z Mac App Storu. Nebo můžete při spouštění aplikací na zařízeních s Windows 10 aktivovat filtr Windows SmartScreen.

Než vytvoříte profil, že podrobnosti, které můžete spravovat nastavení ochrany koncového bodu Intune pro každou podporovanou platformu najdete v následujících článcích: 
   - [Nastavení macOS](endpoint-protection-macos.md)
   - [Nastavení Windows 10](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení ochrany koncových bodů

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **Název** a **Popis** profilu ochrany koncových bodů.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
   - **macOS**
   - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Ochrana koncového bodu**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Další informace:
   - [Nastavení macOS](endpoint-protection-macos.md)
   - [Nastavení Windows 10](endpoint-protection-windows-10.md)  

8. Po konfiguraci příslušných nastavení, vyberte **vytvořit** na **vytvořit profil** stránky.

   Profil se vytvoří a zobrazí se na stránce se seznamem profilů. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Přidat vlastní pravidla brány Firewall pro zařízení s Windows 10  

Když konfigurujete jako součást profilu, který obsahuje pravidla pro ochranu koncového bodu pro Windows 10 firewallu v programu Windows Defender, můžete nakonfigurovat vlastní pravidla pro brány firewall. Vlastní pravidla umožňují rozšířit na předdefinované sady pravidel brány Firewall, které jsou podporované pro Windows 10.  

Při plánování pro profily pomocí vlastního pravidla brány Firewall, zvažte následující informace, které by mohly ovlivnit, jak budete chtít skupinu pravidel brány firewall v profilech:  
- Každý profil podporuje až 150 pravidla brány firewall. Pokud používáte víc než 150 pravidla, vytvořte další profily, každý je omezená na 150 pravidla.  
- Pro každý profil, pokud jedno pravidlo se nezdaří, všechna pravidla v tom, že došlo k profilu a žádná pravidla se použijí na zařízení.  
- Když pravidlo se nezdaří, všechna pravidla v profilu se ohlásí jako neúspěšný. Intune nemůže zjistit, které jednotlivých pravidel se nezdařilo. 

Pravidla brány Firewall, které Intune dokáže spravovat jsou podrobně popsány v Windows [poskytovatel konfiguračních služeb pro brány Firewall]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) (CSP). Projděte si seznam brány firewall na vlastní nastavení pro zařízení s Windows 10, které Intune podporuje, najdete v článku [vlastních pravidel brány Firewall](endpoint-protection-windows-10.md#custom-firewall-rules).   

#### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Přidání vlastních pravidel brány firewall na profil ochrany koncových bodů  

1. V Intune, přejděte na **konfigurace zařízení** > **profily** > **vytvořit profil**.  

2. Pro *platformy*vyberte **Windows 10 a novější**a potom *typ profilu* vyberte **Endpoint protection**.  

3. Vyberte **firewallu v programu Windows Defender** otevřete stránku konfigurace a potom *pravidla brány Firewall* vyberte **přidat** otevřít **vytvořit pravidlo**stránky.  

4. Zadejte nastavení pro pravidlo brány Firewall a pak vyberte **OK** ji uložit. Možnosti brány firewall k dispozici vlastní pravidla v dokumentaci najdete v tématu [vlastních pravidel brány Firewall](endpoint-protection-windows-10.md#custom-firewall-rules).  

5. Po uložení pravidla se zobrazí na *firewallu v programu Windows Defender* stránku v seznamu pravidel.  

6. Pokud chcete pravidlo upravit, vyberte pravidlo ze seznamu, otevřete **upravit pravidlo** stránky.  

7. Pokud chcete odstranit pravidlo z profilu, vyberte tři tečky **(...)**  pravidlo a pak vyberte **odstranit**.  

8. Chcete-li změnit pořadí, ve které zobrazení pravidla, vyberte *šipka nahoru, dolů šipkami* ikonu v horní části seznamu pravidlo.  





## <a name="next-steps"></a>Další postup  

Pokud chcete profil přiřadit ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).
