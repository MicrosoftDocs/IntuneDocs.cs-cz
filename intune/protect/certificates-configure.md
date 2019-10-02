---
title: Vytvoření profilů certifikátů v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil certifikátu pro zařízení pomocí konfigurace prostředí certifikátu SCEP nebo PKCS, exportujte veřejný certifikát, vytvořte profil na portálu Azure a pak přiřaďte SCEP nebo PKCS k profilům certifikátů v Microsoft Intune na portálu Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2019
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
ms.openlocfilehash: 74b920deeb5255f6f938f0c8b07eaab6d765e68e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729882"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Použití certifikátů pro ověřování v Microsoft Intune  

Pomocí certifikátů s Intune můžete ověřovat uživatele s aplikacemi a podnikovými prostředky prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů. Pokud používáte certifikáty k ověřování těchto připojení, koncoví uživatelé nebudou muset zadávat uživatelská jména a hesla, což pomáhá zajistit bezproblémové přístupu. Certifikáty se taky používají k podepisování a šifrování e-mailů pomocí S/MIME.

Intune podporuje následující typy certifikátů:  

- Protokol SCEP (Simple Certificate Enrollment Protocol)  
- PKCS#12 (nebo PFX)  
- Importované certifikáty PKCS

K nasazení těchto certifikátů vytvoříte a přiřadíte profily certifikátů k zařízením.  

Každý profil každého jednotlivého certifikátu, který vytvoříte, podporuje jednu platformu. Pokud například používáte certifikáty PKCS, vytvoříte profil certifikátu PKCS pro Android a samostatný profil certifikátu PKCS pro iOS. Pokud pro tyto dvě platformy používáte také certifikáty SCEP, vytvoříte profil certifikátu SCEP pro Android a druhý pro iOS.  

**Obecné pokyny**:  
- Pokud nemáte certifikační autoritu organizace (CA), musíte jednu z [našich podporovaných partnerů](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners)vytvořit nebo použít jeden z nich.
- Pokud používáte profily certifikátů SCEP pomocí služby Microsoft Active Directory Certificate Services, nakonfigurujete server služby zápisu síťových zařízení (NDES).
- Pokud používáte SCEP s některým z našich partnerů pro certifikační autoritu, budete ho muset [integrovat s Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Profily certifikátů SCEP a PKCS vyžadují, abyste si Microsoft Intune Certificate Connector stáhnout, nainstalovat a nakonfigurovat. 
- Importované certifikáty PCKS vyžadují stažení, instalaci a konfiguraci konektoru certifikátů PFX pro Microsoft Intune.
- Importované certifikáty PKCS vyžadují, abyste exportovali certifikáty od certifikační autority a importovali je do Microsoft Intune. Zobrazit [projekt prostředí PowerShell pro PFXImport](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)
- Aby zařízení používalo profily certifikátů SCEP, PCKS nebo PKCS, musí toto zařízení důvěřovat vaší kořenové certifikační autoritě. K nasazení certifikátu důvěryhodné kořenové certifikační autority do zařízení použijete *profil důvěryhodného certifikátu* .  

## <a name="supported-platforms-and-certificate-profiles"></a>Podporované platformy a profily certifikátů  
| Platforma              | Profil důvěryhodného certifikátu | Profil certifikátu PKCS | Profil certifikátu SCEP | Profil certifikátu importovaného PKCS  |
|--|--|--|--|---|
| Správce zařízení s Androidem | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png)|  ![Podporováno](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> – Vlastník zařízení   | ![Podporováno](./media/certificates-configure/green-check.png) |   |  |   |
| Android Enterprise <br> – Pracovní profil    | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |
| iOS                   | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |
| macOS                 | ![Podporováno](./media/certificates-configure/green-check.png) |   |![Podporováno](./media/certificates-configure/green-check.png)|![Podporováno](./media/certificates-configure/green-check.png)|
| Wvdows Phone 8.1     |![Podporováno](./media/certificates-configure/green-check.png)  |  | ![Podporováno](./media/certificates-configure/green-check.png)| ![Podporováno](./media/certificates-configure/green-check.png) |
| Windows 8.1 a vyšší |![Podporováno](./media/certificates-configure/green-check.png)  |  |![Podporováno](./media/certificates-configure/green-check.png) |   |
| Windows 10 a novější  | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) | ![Podporováno](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Exportujte certifikát důvěryhodné kořenové certifikační autority.  
Aby zařízení mohla používat importované certifikáty PKCS, SCEP a PKCS, musí důvěřovat vaší kořenové certifikační autoritě. Chcete-li vytvořit tento vztah důvěryhodnosti, exportujte certifikát důvěryhodné kořenové certifikační autority (CA) a také jakékoli zprostředkující nebo vydávající certifikáty certifikační autority jako veřejný certifikát (. cer). Tyto certifikáty můžete získat z vydávající certifikační autority nebo z jakéhokoli zařízení, které důvěřuje vydávající certifikační autoritě.  

Informace o exportu certifikátu najdete v dokumentaci k vaší certifikační autoritě. Veřejný certifikát budete muset exportovat jako soubor. cer.  Neexportujte privátní klíč, soubor. pfx.  

Tento soubor. cer budete používat při [vytváření profilů důvěryhodných certifikátů](#create-trusted-certificate-profiles) k nasazení tohoto certifikátu do zařízení.  

## <a name="create-trusted-certificate-profiles"></a>Vytvoření profilů důvěryhodných certifikátů  
Než budete moct vytvořit profil certifikátu SCEP, PKCS nebo PKCS, vytvořte profil důvěryhodného certifikátu. Nasazení profilu důvěryhodného certifikátu zajišťuje, aby každé zařízení rozpoznalo legitimitu vaší certifikační autority. Profily certifikátů SCEP přímo odkazují na profil důvěryhodného certifikátu. Profily certifikátů PKCS přímo neodkazují na profil důvěryhodného certifikátu, ale přímo odkazují na server, který je hostitelem vaší certifikační autority. Profily certifikátů PKCS importované přímo neodkazují na profil důvěryhodného certifikátu, ale můžou ho využít na zařízení. Nasazení profilu důvěryhodného certifikátu na zařízení zajistí, že se tento vztah důvěryhodnosti naváže. Když zařízení nedůvěřuje kořenové certifikační autoritě, zásada profilu certifikátu SCEP nebo PKCS se nezdaří.  

Vytvořte samostatný profil důvěryhodného certifikátu pro každou platformu zařízení, kterou chcete podporovat, stejně jako u profilů certifikátů SCEP, PCKS a PKCS.  


### <a name="to-create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu  

1. Přihlaste se k [portálu Intune](https://aka.ms/intuneportal).  
2. Vyberte **Konfigurace zařízení** > **Spravovat** > **Profily** > **Vytvořit profil**.  
3. Zadejte **název a popis** profilu důvěryhodného certifikátu.  
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení pro tento důvěryhodný certifikát.  
5. V rozevíracím seznamu **Typ profilu** zvolte **Důvěryhodný certifikát**.  
6. Vyhledejte soubor. CER certifikátu důvěryhodné kořenové certifikační autority, který jste exportovali pro použití s tímto profilem certifikátu, a pak vyberte **OK**.  
7. Jenom pro zařízení s Windows 8.1 a Windows 10 vyberte **cílové úložiště** pro důvěryhodný certifikát z těchto možností:  
   - **Úložiště počítačových certifikátů – kořenové**
   - **Úložiště počítačových certifikátů – zprostředkující**
   - **Úložiště uživatelských certifikátů – zprostředkující**
8. Až to budete mít, zvolte **OK**, vraťte se zpět do podokna **Vytvořit profil** a vyberte **Vytvořit**.
Profil se zobrazí v seznamu profilů v podokně *Konfigurace zařízení – zobrazení profily* s typem profilu **důvěryhodného certifikátu**.  Nezapomeňte tento profil přiřadit k zařízením, která budou používat certifikáty SCEP nebo PCKS. Pokud chcete přiřadit tento profil ke skupinám, přečtěte si téma [přiřazení profilů zařízení](../configuration/device-profile-assign.md).

> [!NOTE]  
> V zařízeních s Androidem se může zobrazit zpráva, že třetí strana nainstalovala důvěryhodný certifikát.  

## <a name="additional-resources"></a>Další materiály a zdroje informací  
- [Přiřazení profilů zařízení](../configuration/device-profile-assign.md)  
- [Podepisování a šifrování e-mailů pomocí S/MIME](certificates-s-mime-encryption-sign.md)  
- [Použití certifikační autority třetích stran](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Další kroky  
Po vytvoření a přiřazení profilů důvěryhodných certifikátů vytvořte profily certifikátů SCEP, PKCS a PKCS pro každou platformu, kterou chcete použít. Chcete-li pokračovat, přečtěte si následující články:  
- [Konfigurace infrastruktury pro podporu certifikátů SCEP pomocí Intune](certificates-scep-configure.md)  
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)  
- [Vytvoření importovaného profilu certifikátu PKCS](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  

