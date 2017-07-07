---
title: "Konfigurace profilů certifikátů"
description: "Přečtěte si, jak vytvořit profil certifikátu Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aaf7bf3cb05708457c57070f4a300ece987421c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="configure-intune-certificate-profiles"></a>Konfigurace profilů certifikátů Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Po konfiguraci infrastruktury a certifikátů, jak je popsáno v tématu [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) nebo [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md), můžete vytvořit profily certifikátů. Postup je následující:

- **Úloha 1**: Export certifikátu důvěryhodné kořenové certifikační autority
- **Úloha 2**: Vytvoření profilů důvěryhodných certifikátů
- **Úloha 3**: Vytvoření jednoho ze dvou typů profilu:
  - Profily certifikátů SCEP
  - Profily certifikátů .PFX

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>**Úloha 1**: Export certifikátu důvěryhodné kořenové certifikační autority
Exportujte certifikát důvěryhodné kořenové certifikační autority jako soubor **.cer** z vydávající certifikační autority nebo z jakéhokoli zařízení, které vaší vydávající certifikační agentuře důvěřuje. Privátní klíč neexportujte.

Tento certifikát budete importovat při nastavování profilu důvěryhodného certifikátu.

## <a name="task-2-create-trusted-certificate-profiles"></a>**Úloha 2**: Vytvoření profilů důvěryhodných certifikátů
Profil důvěryhodného certifikátu je nutné vytvořit před vytvořením profilu certifikátu protokolu SCEP (Simple Certificate Enrollment Protocol) či standardu PKCS #12 (.PFX). Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo .PFX pro každou platformu mobilních zařízení.

### <a name="to-create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1.  V [konzole pro správu Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Přidat zásadu** a zvolte platformu zařízení. Pro tato zařízení můžete vytvořit profil důvěryhodného zařízení:

-  Android 4 nebo novější

-  Android for Work

-  iOS 7.1 nebo novější

-  Mac OS X 10.9 a novější

-  Windows 8.1 a vyšší

-  Windows Phone 8.1 nebo novější

2.  Přidejte zásadu **Profil důvěryhodného certifikátu**.

    Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Zadejte informace požadované pro konfiguraci nastavení profilu důvěryhodného certifikátu pro Android, iOS, Mac OS X, Windows 8.1 nebo Windows Phone 8.1.
4.  V nastavení **Soubor certifikátu** importujte certifikát důvěryhodné kořenové certifikační autority (soubor .cer), který jste exportovali z vydávající certifikační autority. Nastavení **Cílové úložiště** se použije jen na zařízení se systémem Windows 8.1 a novějším a jen v případě, že má zařízení víc než jedno úložiště certifikátů.

4.  Vyberte možnost **Uložit zásadu**.

Nová zásada se zobrazí v pracovním prostoru **Zásady**. Teď ji můžete nasadit.

> [!NOTE]
>
> Na zařízeních se systémem Android a Android for Work se zobrazí oznámení o tom, že třetí strana nainstalovala důvěryhodný certifikát.


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a>**Úloha 3**: Vytvoření profilů certifikátů SCEP nebo .PFX
Po vytvoření profilu certifikátu důvěryhodné certifikační autority vytvořte profily certifikátů SCEP nebo .PFX pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP musíte zadat profil důvěryhodného certifikátu pro stejnou platformu. Tím se oba profily certifikátů propojí, ale přesto musíte každý profil nasadit samostatně.

### <a name="to-create-an-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1.  V [konzole pro správu Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Přidat zásadu** a zvolte platformu zařízení.  Pro tato zařízení můžete vytvořit profil certifikátu SCEP:

-  Android 4 nebo novější

-  Android for Work

-  iOS 7.1 nebo novější

-  Mac OS X 10.9 a novější

-  Windows 8.1 a vyšší

-  Windows Phone 8.1 nebo novější

2.  Přidejte zásadu **Profil certifikátu SCEP**.

    Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Pokud chcete konfigurovat nastavení profilu certifikátu SCEP, postupujte podle pokynů na stránce konfigurace profilu.
    > [!NOTE]
    >
    > Pokud chcete zadat vlastní formát názvu subjektu (jenom profily iOS), v části **Formát názvu subjektu** vyberte **Vlastní**.
    >
    > Vlastní formát je aktuálně možné použít pro dvě proměnné, a to `Common Name (CN)` a `Email (E)`. Kombinací těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu, jako je třeba tenhle:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > V příkladu správce vytvořil formát názvu subjektu, který kromě proměnných `CN` a `E` používá řetězce pro hodnoty Organizační jednotka (OU), Organizace (O), Umístění (L), Oblast (S) a Země (C). Výčet podporovaných řetězců je uveden v popisu [funkce CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx).

4.  Vyberte možnost **Uložit zásadu**.

Nová zásada se zobrazí v pracovním prostoru **Zásady**. Teď ji můžete nasadit.

### <a name="to-create-a-pfx-certificate-profile"></a>Vytvoření profilu certifikátu .PFX

1.  V [konzole pro správu Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Přidat zásadu** a zvolte platformu zařízení. Certifikáty .PFX jsou podporované pro:
  - Android 4 nebo novější
  - Android for Work
  - Windows 10 a novější
  - Windows Phone 10 a novější
  - iOS 8.0 a novější    


2.  Přidejte zásadu **Profil certifikátu PFX**.
      Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Do formuláře zásad zadejte požadované informace.
4.  Vyberte možnost **Uložit zásadu**.

Nová zásada se zobrazí v pracovním prostoru **Zásady**. Teď ji můžete nasadit.

## <a name="deploy-certificate-profiles"></a>Nasazení profilů certifikátů
Při nasazení profilu certifikátu se soubor certifikátu z profilu důvěryhodné certifikační autority nainstaluje na zařízení. Zařízení profil certifikátu SCEP nebo .PFX použije k vytvoření vlastní žádosti o certifikát.

Profily certifikátů se nainstalují jenom na zařízení té platformy, kterou použijete při vytváření profilu.

-   Profily certifikátů můžete nasadit do kolekce uživatelů nebo do kolekce zařízení.

    > [!TIP]
    > Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, nasaďte profil certifikátu do skupinu uživatelů (ne zařízení). Pokud ho nasadíte do skupiny zařízení, budete je muset před obdržením zásad plně zaregistrovat.

-   I když se každý profil nasazuje samostatně, je třeba nasadit jak důvěryhodnou kořenovou certifikační autoritu, tak profil SCEP nebo .PFX. Jinak zásady certifikátu SCEP nebo .PFX nebudou fungovat.

Profily certifikátů nasaďte stejným způsobem jako jiné zásady pro Intune:

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.
2.  V dialogovém okně **Spravovat nasazení** :
    -   **Pokud chcete nasadit zásadu**, vyberte jednu nebo víc skupin, do kterých ji chcete nasadit, a klikněte na **Přidat**&gt;**OK**.
    -   **Pokud chcete dialogové okno zavřít bez nasazení**, klikněte na **Zrušit**.

Když vyberete nasazenou zásadu, v dolní části seznamu zásad se zobrazí další informace o nasazení.

### <a name="next-steps"></a>Další kroky

Dál zjistěte, jak pomocí certifikátů zabezpečit profily e-mailu, Wi-Fi a VPN.

-  [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md)
