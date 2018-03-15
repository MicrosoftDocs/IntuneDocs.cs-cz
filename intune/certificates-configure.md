---
title: "Vytvoření profilů certifikátů v Microsoft Intune – Azure | Microsoft Docs"
description: "Přidejte nebo vytvořte profil certifikátu pro zařízení pomocí konfigurace prostředí certifikátu SCEP nebo PKCS, exportujte veřejný certifikát, vytvořte profil na portálu Azure a pak přiřaďte SCEP nebo PKCS k profilům certifikátů v Microsoft Intune na portálu Azure Portal."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b9d181c4a6e490018c88214a2ed91c90327f2526
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Konfigurace profilu certifikátu pro zařízení v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Když uživatelům poskytnete přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, můžete tato připojení ověřovat pomocí certifikátů. Když používáte certifikáty, nemusíte zadávat uživatelské jméno a heslo pro ověření připojení. 

Pomocí Intune můžete přiřadit tyto certifikáty k zařízením, která spravujete. Intune podporuje přiřazování a správu těchto typů certifikátů:

- Protokol SCEP (Simple Certificate Enrollment Protocol)
- PKCS#12 (nebo PFX)

Každý z těchto typů certifikátů má vlastní požadované součásti a požadavky na infrastrukturu.

## <a name="overview"></a>Přehled

1. Zajistěte, abyste měli připravenou správnou infrastrukturu certifikátů. Můžete použít [certifikáty SCEP](certificates-scep-configure.md) a [certifikáty PKCS](certficates-pfx-configure.md).

2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. K tomuto účelu vytvořte a přiřaďte **profil důvěryhodného certifikátu**. Po přiřazení tohoto profilu budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu musíte vytvořit samostatný profil. Profily důvěryhodného certifikátu jsou dostupné pro tyto platformy:

    - iOS 8.0 a novější
    - macOS 10.9 a novější
    - Android 4.0 a novější
    - Android for Work
    - Windows 8.1 a vyšší
    - Windows Phone 8.1 nebo novější
    - Windows 10 a novější

3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu. Pro zařízení s následujícími platformami můžete vytvořit a přiřadit profil certifikátu **PKCS** nebo **SCEP**:

   - iOS 8.0 a novější
   - Android 4.0 a novější
   - Android for Work
   - Windows 10 (Desktop a Mobile) a novější

   Profil certifikátu **SCEP** můžete použít jenom pro zařízení s těmito platformami:

   - macOS 10.9 a novější
   - Windows Phone 8.1 nebo novější

Pro každou platformu zařízení je nutné vytvořit samostatný profil. Při vytváření profil přidružíte k profilu důvěryhodného kořenového certifikátu, který jste vytvořili dříve.

### <a name="further-considerations"></a>Další pravidla

- Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
- Pokud používáte profily SCEP, nakonfigurujte server služby zápisu síťových zařízení.
- Bez ohledu na to, jestli plánujete používat profily SCEP nebo PKCS, si stáhněte a nakonfigurujte Microsoft Intune Certificate Connector.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Krok 1: Konfigurace infrastruktury certifikátu

Potřebujete-li nápovědu ke konfiguraci infrastruktury jednotlivých typů profilů certifikátů, přečtěte si tato témata:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Krok 2: Export certifikátu důvěryhodné kořenové certifikační autority

Exportujte certifikát důvěryhodné kořenové certifikační autority jako veřejný certifikát (.cer) z vydávající certifikační autority nebo z jakéhokoli zařízení, které důvěřuje vaší vydávající certifikační autoritě. Privátní klíč (.pfx) neexportujte.

Tento certifikát naimportujete při nastavování profilu důvěryhodného certifikátu.

## <a name="step-3-create-trusted-certificate-profiles"></a>Krok 3: Vytvoření profilů důvěryhodných certifikátů
Před vytvořením profilu certifikátu SCEP nebo PKCS je potřeba vytvořit profil důvěryhodného certifikátu. Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo PKCS pro každou platformu zařízení. Postup vytvoření důvěryhodných certifikátů je pro jednotlivé platformy zařízení podobný.

1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.
2. V **Microsoft Intune** vyberte **Konfigurace zařízení** a pak **Profily**. Pak vyberte **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu důvěryhodného certifikátu.
4. U možnosti **Platforma** vyberte platformu zařízení pro tento důvěryhodný certifikát: 

    - **Androidemem**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

5. Jako **typ profilu** vyberte **Důvěryhodný certifikát**. Vyhledejte dříve uložený certifikát (*CertificateName*.cer) (krok 2).

    Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:  

    - **Úložiště počítačových certifikátů – kořenové**
    - **Úložiště počítačových certifikátů – zprostředkující**
    - **Úložiště uživatelských certifikátů – zprostředkující**

6. Kliknutím na **OK** uložte změny a vyberte **Vytvořit** a uložte tak nový profil.

Profil se vytvoří a zobrazí se v seznamu. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

Na zařízeních s Androidem se může zobrazit zpráva, že třetí strana nainstalovala důvěryhodný certifikát.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Krok 4: Vytvoření profilů certifikátů SCEP nebo PKCS

Potřebujete-li nápovědu ke konfiguraci a přiřazení jednotlivých typů profilů certifikátů, přečtěte si tato témata:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)

Po vytvoření profilu důvěryhodného certifikátu vytvořte profily certifikátů SCEP nebo PKCS pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP zadejte profil důvěryhodného certifikátu pro stejnou platformu. Oba profily certifikátů se tak propojí, ale přesto musíte každý profil přiřadit samostatně.

## <a name="next-steps"></a>Další kroky
Obecné informace o tom, jak přiřadit profily zařízení, najdete v tématu [Jak přiřadit profily zařízení](device-profile-assign.md).