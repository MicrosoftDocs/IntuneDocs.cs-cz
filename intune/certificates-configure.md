---
title: Vytvoření profilů certifikátů v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil certifikátu pro zařízení pomocí konfigurace prostředí certifikátu SCEP nebo PKCS, exportujte veřejný certifikát, vytvořte profil na portálu Azure a pak přiřaďte SCEP nebo PKCS k profilům certifikátů v Microsoft Intune na portálu Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f13b5b92ca442f4b5ae05d3567f8385288d92909
ms.sourcegitcommit: 6b5907046f920279bbda3ee6c93e98594624c05c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2019
ms.locfileid: "69582921"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Konfigurace profilu certifikátu pro zařízení v Microsoft Intune

Uživatelům umožníte přístup k podnikovým prostředkům prostřednictvím VPN, Wi-Fi nebo e-mailových profilů. Tato připojení můžete ověřovat pomocí certifikátů. Když používáte certifikáty, nemusí koncoví uživatelé při ověřování zadávat uživatelské jméno a heslo.

Pomocí Intune můžete přiřadit tyto certifikáty k zařízením, která spravujete. Intune podporuje přiřazování a správu těchto typů certifikátů:

- Protokol SCEP (Simple Certificate Enrollment Protocol)
- PKCS#12 (nebo PFX)

Každý z těchto typů certifikátů má vlastní požadované součásti a požadavky na infrastrukturu.


## <a name="overview"></a>Přehled

1. Zajistěte, abyste měli nainstalovanou správnou infrastrukturu certifikátů. Můžete použít [certifikáty SCEP](certificates-scep-configure.md) a [certifikáty PKCS](certficates-pfx-configure.md).

2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. Certifikát nainstalujete tak, že pro každé zařízení vytvoříte a přiřadíte **profil důvěryhodného certifikátu** . Po přiřazení tohoto profilu budou zařízení spravovaná přes Intune požadovat a přijímat kořenový certifikát. Pro každou platformu musíte vytvořit samostatný profil. Profily důvěryhodného certifikátu jsou dostupné pro tyto platformy:

    - iOS 8.0 a novější
    - macOS 10.11 a novější
    - Android 4.0 a novější
    - Android Enterprise  
    - Windows 8.1 a vyšší
    - Windows Phone 8.1 nebo novější
    - Windows 10 a novější

    > [!NOTE]  
    > V zařízeních se systémem *Android Enterprise pro vyhrazená zařízení*nejsou profily certifikátů podporovány.

3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu. Pro různé platformy jsou k dispozici následující typy profilů:  

   | Platforma     |Certifikát PKCS|Certifikát SCEP| Importovaný certifikát PKCS | 
   |--------------|----------------|----------------|-------------------|
   | Android                | Ano    | Ano    | Ano    |
   | Android Enterprise     | Ano    | Ano    | Ano    |
   | iOS                    | Ano    | Ano    | Ano    |
   | macOS                  |        | Ano    | Ano    |
   | Windows Phone 8.1      |        | Ano    | Ano    |
   | Windows 8.1 a vyšší  |        | Ano    |        |
   | Windows 10 a novější   | Ano    | Ano    | Ano    |

   Pro každou platformu zařízení je nutné vytvořit samostatný profil. Při vytváření profil přidružíte k profilu důvěryhodného kořenového certifikátu, který jste vytvořili dříve.

### <a name="further-considerations"></a>Další pravidla

- Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
- Pokud používáte profily SCEP, nakonfigurujte server služby zápisu síťových zařízení.
- Bez ohledu na to, jestli plánujete používat profily SCEP nebo PKCS, si stáhněte a nakonfigurujte Microsoft Intune Certificate Connector.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Krok 1: Konfigurace infrastruktury certifikátu

Nápovědu ke konfiguraci infrastruktury pro každý typ profilu certifikátu najdete v jednom z následujících článků:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Krok 2: Exportujte certifikát důvěryhodné kořenové certifikační autority.

Exportujte certifikát důvěryhodné kořenové certifikační autority jako veřejný certifikát (.cer) z vydávající certifikační autority nebo z jakéhokoli zařízení, které důvěřuje vaší vydávající certifikační autoritě. Neexportujte privátní klíč (. pfx).

Tento certifikát naimportujete při nastavování profilu důvěryhodného certifikátu.

## <a name="step-3-create-trusted-certificate-profiles"></a>Krok 3: Vytvoření profilů důvěryhodných certifikátů

Před vytvořením profilu certifikátu SCEP nebo PKCS je potřeba vytvořit profil důvěryhodného certifikátu. Potřebujete profil důvěryhodného certifikátu a profil SCEP nebo PKCS pro každou platformu zařízení. Postup vytvoření důvěryhodných certifikátů je pro jednotlivé platformy zařízení podobný.

1. V [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)vyberte **Konfigurace** > zařízení**Spravovat** > **profily** > **vytvořit profil**.
2. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název profilu. Své profily pojmenujte, abyste je později mohli snadno identifikovat. Dobrým názvem profilu je například **důvěryhodný profil certifikátu pro zařízení s Androidem Enterprise Owner** nebo **profil důvěryhodného certifikátu pro zařízení s iOS**.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu zařízení. Možnosti:

      - **Android**
      -  > **Jenom vlastníci zařízení** s Androidem Enterprise
      -  > **Jenom pracovní profil** Android Enterprise
      - **iOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 a novější**
      - **Windows 10 a novější**

    - **Typ profilu**: Vyberte **důvěryhodný certifikát**.

3. Vyhledejte certifikát, který jste uložili v [kroku 2: Exportujte certifikát](#step-2-export-your-trusted-root-ca-certificate)důvěryhodné kořenové certifikační autority a pak vyberte **OK**.
4. Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:

    - **Úložiště certifikátů počítače-kořen** SCEP
    - **Úložiště certifikátů počítače-zprostředkující** SCEP
    - **Úložiště certifikátů uživatele-zprostředkující** (PKCS, SCEP)

5. Až to budete mít, zvolte **OK**, vraťte se zpět do podokna **Vytvořit profil** a vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v seznamu. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

   >[!NOTE]
   > Na zařízeních s Androidem se může zobrazit zpráva, že třetí strana nainstalovala důvěryhodný certifikát.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Krok 4: Vytvoření profilů certifikátů SCEP nebo PKCS

Nápovědu ke konfiguraci a přiřazování jednotlivých typů profilů certifikátů najdete v jednom z následujících článků:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)

Po vytvoření profilu důvěryhodného certifikátu vytvořte profily certifikátů SCEP nebo PKCS pro každou platformu, kterou chcete použít. Při vytváření profilu certifikátu SCEP zadejte profil důvěryhodného certifikátu pro stejnou platformu. Oba profily certifikátů se tak propojí, ale přesto musíte každý profil přiřadit samostatně.

## <a name="next-steps"></a>Další postup

[Přiřazení profilů zařízení](device-profile-assign.md)  
[Podepisování a šifrování e-mailů pomocí S/MIME](certificates-s-mime-encryption-sign.md)  
[Používání certifikační autority třetí strany](certificate-authority-add-scep-overview.md)

## <a name="see-also"></a>Viz také:

[Řešení potíží s konfigurací NDES pro použití s Microsoft Intune profily certifikátů](https://support.microsoft.com/help/4459540)

[Řešení potíží s nasazením profilu certifikátu SCEP v Microsoft Intune](https://support.microsoft.com/help/4457481)
