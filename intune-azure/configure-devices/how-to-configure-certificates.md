---
title: "Konfigurace certifikátů pomocí Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí Intune vytvářet a přiřazovat certifikáty, které vám pomůžou zabezpečit Wi-Fi, VPN a další připojení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a981b0253f56d66292ce77639faf4beba8832a9e
ms.openlocfilehash: 7d1d3c101aaa3832e36a0b9e9369fd1eeb0a6250
ms.lasthandoff: 04/19/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Konfigurace certifikátů v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Když uživatelům poskytnete přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, můžete tato připojení ověřovat pomocí certifikátů. Tím odpadne nutnost zadávat uživatelské jméno a heslo pro ověření připojení.

Pomocí Intune můžete přiřadit tyto certifikáty k zařízením, která spravujete. Intune podporuje přiřazování a správu těchto typů certifikátů:

- Protokol SCEP (Simple Certificate Enrollment Protocol)
- PKCS#12 (nebo PFX)

Každý z těchto typů certifikátů má vlastní požadované součásti a požadavky na infrastrukturu.

## <a name="general-workflow"></a>Obecný pracovní postup

1. Zajistěte, abyste měli připravenou správnou infrastrukturu certifikátů. Můžete použít [certifikáty SCEP](configure-certificate-infrastructure-for-scep.md) a [certifikáty PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. K tomuto účelu vytvořte a přiřaďte **profil důvěryhodného certifikátu**. Po přiřazení tohoto profilu budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu budete muset vytvořit samostatný profil. Profily důvěryhodného certifikátu jsou dostupné pro tyto platformy:
    - iOS 8.0 a novější
    - macOS 10.9 a novější
    - Android 4.0 a novější
    - Android for Work
    - Windows 8.1 a vyšší
    - Windows Phone 8.1 a novější
    - Windows 10 a novější
3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu. Pro zařízení s následujícími platformami můžete vytvořit a nasadit profil certifikátu **PKCS** nebo **SCEP**:
    - iOS 8.0 a novější
    - Android 4.0 a novější
    - Android for Work
    - Windows 10 (desktopové a mobilní) a novější

    Pro zařízení s následujícími platformami můžete použít jenom profil certifikátu SCEP:

-     macOS 10.9 a novější
-     Windows Phone 8.1 a novější

Pro každou platformu zařízení musíte vytvořit samostatný profil. Při vytváření profil přidružíte k profilu důvěryhodného kořenového certifikátu, který jste vytvořili dříve.

### <a name="further-considerations"></a>Další pravidla

- Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
- Pokud se na základě platforem zařízení rozhodnete použít profil SCEP (Simplified Certificate Enrollment Protocol), musíte taky nakonfigurovat server Služby zápisu síťových zařízení (NDES).
- Bez ohledu na to, jestli plánujete používat profily SCEP nebo PKCS, si musíte stáhnout a nakonfigurovat Microsoft Intune Certificate Connector.


## <a name="step-1--configure-your-certificate-infrastructure"></a>Krok 1: Konfigurace infrastruktury certifikátu

Potřebujete-li nápovědu ke konfiguraci infrastruktury jednotlivých typů profilů certifikátů, přečtěte si tato témata:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx)


## <a name="step-2---export-your-trusted-root-ca-certificate"></a>Krok 2: Export certifikátu důvěryhodné kořenové certifikační autority

Exportujte certifikát důvěryhodné kořenové certifikační autority jako soubor **.cer** z vydávající certifikační autority nebo z jakéhokoli zařízení, které vaší vydávající certifikační agentuře důvěřuje. Privátní klíč neexportujte.

Tento certifikát budete importovat při nastavování profilu důvěryhodného certifikátu.

## <a name="step-3-create-trusted-certificate-profiles"></a>Krok 3: Vytvoření profilů důvěryhodných certifikátů
Před vytvořením profilu certifikátu SCEP nebo PKCS musíte vytvořit profil důvěryhodného certifikátu. Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo PKCS pro každou platformu zařízení. Postup vytvoření důvěryhodných certifikátů je obdobný pro každou platformu zařízení.

### <a name="to-create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** profilu důvěryhodného certifikátu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento důvěryhodný certifikát. V současné době můžete pro nastavení certifikátů zvolit jednu z následujících platforem:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Důvěryhodný certifikát**.
7. Procházením vyhledejte certifikát, který jste si uložili v rámci úlohy 1, a pak klikněte na **OK**.
8. Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:
    - **Úložiště počítačových certifikátů – kořenové**
    - **Úložiště počítačových certifikátů – zprostředkující**
    - **Úložiště uživatelských certifikátů – zprostředkující**
8. Až to budete mít, zvolte **OK**, vraťte se do okna **Vytvořit profil** a zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).


> [!Note]
> Na zařízeních s Androidem se zobrazí oznámení o tom, že třetí strana nainstalovala důvěryhodný certifikát.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Krok 4: Vytvoření profilů certifikátů SCEP nebo PKCS

Potřebujete-li nápovědu ke konfiguraci a přiřazení jednotlivých typů profilů certifikátů, přečtěte si tato témata:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx)

Po vytvoření profilu důvěryhodného certifikátu vytvořte profily certifikátů SCEP nebo PKCS pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP musíte zadat profil důvěryhodného certifikátu pro stejnou platformu. Tím se oba profily certifikátů propojí, ale přesto musíte každý profil přiřadit samostatně.


## <a name="next-steps"></a>Další kroky
Obecné informace o tom, jak přiřadit profily zařízení, najdete v tématu [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).

