---
title: Vytvoření profilů certifikátů v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak používat Simple Certificate Enrollment Protocol (SCEP) nebo certifikáty PKCS (Public Key Cryptography Standards) a profily certifikátů s Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ea2d51b82f0f47ee4bfabc94c2e971e4cb666d4
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801749"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Použití certifikátů pro ověřování v Microsoft Intune

Pomocí certifikátů s Intune můžete ověřovat uživatele s aplikacemi a podnikovými prostředky prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů. Když k ověření těchto připojení použijete certifikáty, koncoví uživatelé nebudou muset zadávat uživatelská jména a hesla, což by mohlo mít bez potíží přístup. Certifikáty se taky používají k podepisování a šifrování e-mailů pomocí S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Podporované certifikáty a využití v Intune

| Typ              | Ověřování | Podepisování S/MIME | Šifrování S/MIME  |
|--|--|--|--|
| Importovaný certifikát PKCS (Public Key Cryptography Standards) |  | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png)|
| PKCS#12 (nebo PFX)    | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |  |
| Protokol SCEP (Simple Certificate Enrollment Protocol)  | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | |

K nasazení těchto certifikátů vytvoříte a přiřadíte profily certifikátů k zařízením.  

Každý profil každého jednotlivého certifikátu, který vytvoříte, podporuje jednu platformu. Pokud například používáte certifikáty PKCS, vytvoříte profil certifikátu PKCS pro Android a samostatný profil certifikátu PKCS pro iOS. Pokud pro tyto dvě platformy používáte také certifikáty SCEP, vytvoříte profil certifikátu SCEP pro Android a druhý pro iOS.

**Obecné pokyny**:
- Pokud nemáte certifikační autoritu organizace (CA), musíte jednu z [našich podporovaných partnerů](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners)vytvořit nebo použít jeden z nich.
- Pokud používáte profily certifikátů SCEP pomocí služby Microsoft Active Directory Certificate Services, nakonfigurujete server služby zápisu síťových zařízení (NDES).
- Pokud používáte SCEP s některým z našich partnerů pro certifikační autoritu, budete ho muset [integrovat s Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Profily certifikátů SCEP a PKCS vyžadují, abyste si Microsoft Intune Certificate Connector stáhnout, nainstalovat a nakonfigurovat.
- Importované certifikáty PKCS vyžadují, abyste si stáhli, nainstalovali a nakonfigurovali konektor certifikátů PFX pro Microsoft Intune.
- Importované certifikáty PKCS vyžadují, abyste exportovali certifikáty od certifikační autority a importovali je do Microsoft Intune. Viz [projekt prostředí PowerShell pro PFXImport](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).
- Aby zařízení používalo profily certifikátů SCEP, PKCS nebo PKCS, musí toto zařízení důvěřovat vaší kořenové certifikační autoritě. K nasazení certifikátu důvěryhodné kořenové certifikační autority do zařízení použijete *profil důvěryhodného certifikátu* .

## <a name="supported-platforms-and-certificate-profiles"></a>Podporované platformy a profily certifikátů

| Platforma              | Profil důvěryhodného certifikátu | Profil certifikátu PKCS | Profil certifikátu SCEP | Profil certifikátu importovaného PKCS  |
|--|--|--|--|---|
| Správce zařízení s Androidem | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png)|  ![Podporováno](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> – Plně spravované (vlastník zařízení)   | ![Podporováno](./media/certificates-configure/green-check.png) |   | ![Podporováno](./media/certificates-configure/green-check.png) |   |
| Android Enterprise <br> -Vyhrazené (vlastník zařízení)   |  |   |  |   |
| Android Enterprise <br> – Pracovní profil    | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |
| iOS                   | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |
| macOS                 | ![Podporováno](./media/certificates-configure/green-check.png) |  ![Podporováno](./media/certificates-configure/green-check.png) |![Podporováno](./media/certificates-configure/green-check.png)|![Podporováno](./media/certificates-configure/green-check.png)|
| Wvdows Phone 8.1     |![Podporováno](./media/certificates-configure/green-check.png)  |  | ![Podporováno](./media/certificates-configure/green-check.png)| ![Podporováno](./media/certificates-configure/green-check.png) |
| Windows 8.1 a vyšší |![Podporováno](./media/certificates-configure/green-check.png)  |  |![Podporováno](./media/certificates-configure/green-check.png) |   |
| Windows 10 a novější  | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Exportujte certifikát důvěryhodné kořenové certifikační autority.

Aby zařízení mohla používat importované certifikáty PKCS, SCEP a PKCS, musí důvěřovat vaší kořenové certifikační autoritě. Chcete-li vytvořit vztah důvěryhodnosti, exportujte certifikát důvěryhodné kořenové certifikační autority (CA) a všechny zprostředkující nebo vydávající certifikáty certifikační autority jako veřejný certifikát (. cer). Tyto certifikáty můžete získat z vydávající certifikační autority nebo z jakéhokoli zařízení, které důvěřuje vydávající certifikační autoritě.

Informace o exportu certifikátu najdete v dokumentaci k vaší certifikační autoritě. Veřejný certifikát budete muset exportovat jako soubor. cer.  Neexportujte privátní klíč, soubor. pfx.

Tento soubor. cer budete používat při [vytváření profilů důvěryhodných certifikátů](#create-trusted-certificate-profiles) k nasazení tohoto certifikátu do zařízení.

## <a name="create-trusted-certificate-profiles"></a>Vytvoření profilů důvěryhodných certifikátů

Než budete moct vytvořit profil certifikátu SCEP, PKCS nebo PKCS, vytvořte profil důvěryhodného certifikátu. Nasazení profilu důvěryhodného certifikátu zajišťuje, aby každé zařízení rozpoznalo legitimitu vaší certifikační autority. Profily certifikátů SCEP přímo odkazují na profil důvěryhodného certifikátu. Profily certifikátů PKCS přímo neodkazují na profil důvěryhodného certifikátu, ale přímo odkazují na server, který je hostitelem vaší certifikační autority. Profily certifikátů PKCS importované přímo neodkazují na profil důvěryhodného certifikátu, ale můžou ho použít na zařízení. Nasazení profilu důvěryhodného certifikátu na zařízení zajistí, že se tento vztah důvěryhodnosti naváže. Když zařízení nedůvěřuje kořenové certifikační autoritě, zásada profilu certifikátu SCEP nebo PKCS se nezdaří.  

Vytvořte samostatný profil důvěryhodného certifikátu pro každou platformu zařízení, kterou chcete podporovat, stejně jako u profilů certifikátů SCEP, PKCS a PKCS.  


### <a name="to-create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu  

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.

   ![Přejděte na Intune a vytvořte nový profil důvěryhodného certifikátu.](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Zadejte následující vlastnosti:

   - Zadejte **Název** profilu.
   - Volitelně můžete nastavit **Popis** .
   - Zadejte **Platformu**, na kterou se má profil nasadit.
   - Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

4. Vyberte **Nastavení**a pak vyhledejte soubor. CER certifikátu důvěryhodné kořenové certifikační autority, který jste exportovali pro použití s tímto profilem certifikátu, a pak vyberte **OK**.

5. Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:  
   - **Úložiště počítačových certifikátů – kořenové**
   - **Úložiště počítačových certifikátů – zprostředkující**
   - **Úložiště uživatelských certifikátů – zprostředkující**

6. Až to budete mít, zvolte **OK**, vraťte se zpět do podokna **Vytvořit profil** a vyberte **Vytvořit**.

Profil se zobrazí v seznamu profilů v okně *zařízení – konfigurační profily* s typem profilu **důvěryhodného certifikátu**.  Nezapomeňte tento profil přiřadit k zařízením, která budou používat certifikáty SCEP nebo PKCS. Pokud chcete přiřadit tento profil ke skupinám, přečtěte si téma [přiřazení profilů zařízení](../configuration/device-profile-assign.md).

> [!NOTE]  
> V zařízeních s Androidem se může zobrazit zpráva, že třetí strana nainstalovala důvěryhodný certifikát.  

## <a name="additional-resources"></a>Další materiály a zdroje informací

- [Přiřazení profilů zařízení](../configuration/device-profile-assign.md)  
- [Podepisování a šifrování e-mailů pomocí S/MIME](certificates-s-mime-encryption-sign.md)  
- [Použití certifikační autority třetích stran](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Další kroky

Pro každou platformu, kterou chcete použít, vytvořte profily certifikátů importované pomocí protokolu SCEP, PKCS nebo PKCS. Chcete-li pokračovat, přečtěte si následující články:  
- [Konfigurace infrastruktury pro podporu certifikátů SCEP pomocí Intune](certificates-scep-configure.md)  
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)  
- [Vytvoření importovaného profilu certifikátu PKCS](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  
