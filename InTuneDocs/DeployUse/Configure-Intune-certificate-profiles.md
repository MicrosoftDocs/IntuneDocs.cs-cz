---
# required metadata

title: Konfigurace profilů certifikátů | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurace profilů certifikátů Intune
Po konfiguraci infrastruktury a certifikátů, jak je popsáno v tématu [Konfigurace infrastruktury certifikátu](configure-certificate-infrastructure.md), můžete konfigurovat profily certifikátů:

**Úloha 1** – export certifikátu důvěryhodné kořenové certifikační autority
**Úloha 2** – vytvoření profilů certifikátů důvěryhodné certifikační autority
**Úloha 3** – jedna z následujících akcí:

Vytvoření profilů certifikátů SCEP

Vytvoření profilů certifikátů .PFX

### Úloha 1 – export důvěryhodného kořenového certifikátu
Exportujte certifikát důvěryhodné kořenové certifikační autority jako soubor **.cer** z vydávající certifikační autority nebo jakéhokoli zařízení, které vaší vydávající certifikační agentuře důvěřuje. Privátní klíč neexportujete.

Tento certifikát budete importovat při konfiguraci profilu důvěryhodného certifikátu.

### Úloha 2 – vytvoření profilů důvěryhodných certifikátů
Před vytvořením profilu certifikátu SCEP nebo. PFX musíte vytvořit **Profil důvěryhodného certifikátu**. Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo.PFS pro každou platformu mobilních zařízení.

##### Vytvoření profilu důvěryhodného certifikátu

1.  Otevřete [konzolu pro správu Intune](https://manage.microsoft.com) a klikněte na **Zásady** &gt; **Přidat zásadu**..

2.  Nakonfigurujte jeden z následujících typů zásad:

    **Android &gt; profil důvěryhodného certifikátu (Android 4 a novější)**

    **iOS &gt; Profil důvěryhodného certifikátu (iOS 7.1 a novější)**

    **Mac OS X &gt; Profil důvěryhodného certifikátu (Mac OS X 10.9 a novější)**

    **Windows &gt; Profil důvěryhodného certifikátu (Windows 8.1 a novější)**

    **Windows &gt; Profil důvěryhodného certifikátu (Windows Phone 8.1 a novější)**

    Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

3.  Poskytněte požadované informace pro konfiguraci nastavení profilu důvěryhodného certifikátu pro Android, iOS, Mac OS X, Windows 8.1 nebo Windows Phone 8.1. V nastavení **Soubor certifikátu** importujte certifikát důvěryhodné certifikační autority (**.cer**), který jste exportovali z vydávající certifikační autority. Nastavení **Cílové úložiště** se použije jen na zařízení se systémem Windows 8.1 a novějším a jen v případě, že má zařízení víc než jedno úložiště certifikátů.


4.  Po dokončení klikněte na **Uložit zásadu**..

Nové zásady se zobrazí v pracovním prostoru **Zásady** a můžete je teď nasadit.

### Úloha 3 – Vytvoření profilů certifikátů SCEP nebo .PFX
Po vytvoření profilu certifikátu důvěryhodné certifikační autority vytvořte profily certifikátů SCEP nebo .PFX pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP musíte zadat profil důvěryhodného certifikátu pro stejnou platformu. Tím se oba profily certifikátů propojí, ačkoliv každý profil musíte nasadit samostatně.

##### Vytvoření profilu certifikátu SCEP

1.  Otevřete [konzolu pro správu Intune](https://manage.microsoft.com), klikněte na **Zásady** &gt; **Přidat zásadu**..

2.  Nakonfigurujte jeden z následujících typů zásad:

    **Android &gt; Profil certifikátu SCEP (Android 4 a novější)**

    **iOS &gt; Profil certifikátu SCEP (iOS 7.1 a novější)**

    **Mac OS X &gt; Profil certifikátu SCEP (Mac OS X 10.9 a novější)**

    **Windows &gt; Profil certifikátu SCEP (Windows 8.1 a novější)**

    **Windows &gt; Profil certifikátu SCEP (Windows Phone 8.1 a novější)**

    Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

3.  Pokud chcete konfigurovat nastavení profilu certifikátu SCEP, postupujte podle pokynů na stránce konfigurace profilu.

4.  Po dokončení klikněte na **Uložit zásadu**..

Nové zásady se zobrazí v pracovním prostoru **Zásady** a můžete je teď nasadit.

##### Vytvoření profilu certifikátu .PFX

1.  Otevřete [konzolu pro správu Intune](https://manage.microsoft.com), klikněte na **Zásady** &gt; **Přidat zásadu**..

2.  Nakonfigurujte jeden z následujících typů zásad:



-   **Android &gt; Profil certifikátu .PFX (Android 4 a novější)**

    -   **Windows &gt; Profil certifikátu PKCS #12 (.PFX)  (Windows 10 a novější)**

    -   **Windows &gt; Profil certifikátu PKCS #12 (.PFX)  (Windows 10 a novější)**

    -    **iOS > Profil certifikátu PKCS #12 (.PFX) (iOS 7.1 a novější)**    

    Další informace: [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

3.  Zadejte požadované informace do formuláře zásad.

4.  Po dokončení klikněte na **Uložit zásadu**..

Nové zásady se zobrazí v pracovním prostoru **Zásady** a můžete je teď nasadit.

## Nasazení profilů certifikátů
Když nasadíte profily certifikátů, soubor certifikátu z profilu certifikátu důvěryhodné certifikační autority se nainstaluje do zařízení a zařízení použije profil certifikátu SCEP nebo .PFX k vytvoření žádosti o certifikát.

Profily certifikátů se nainstalují jenom na příslušná zařízení podle platformy, kterou použijete při vytváření profilu.

-   Profily certifikátů můžete nasadit na kolekce uživatelů nebo kolekce zařízení.

    > [!TIP]
    > Pokud chcete umožnit, aby se certifikáty do zařízení publikovaly rychle po zaregistrování zařízení, nasaďte profil certifikátu do skupiny uživatelů (ne skupiny zařízení). Pokud ho nasadíte do skupiny zařízení, musí proběhnout úplná registrace zařízení, než zařízení obdrží zásady.

-   Přestože se každý profil nasazuje samostatně, musí se nasadit jak profil důvěryhodného kořenového certifikátu i profil SCEP/.PFX, jinak se zásady certifikátu SCEP/.PFX nezdaří.

Profily certifikátů se nasazují stejným způsobem jako jiné zásady pro Intune.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom klikněte na **Spravovat nasazení**..

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a potom klikněte na **Přidat** &gt; **OK**..

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**..

Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.
###  Další kroky

Teď můžete používat certifikáty k usnadnění zabezpečení profilů e-mailu, Wi-Fi a VPN?

-  [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


