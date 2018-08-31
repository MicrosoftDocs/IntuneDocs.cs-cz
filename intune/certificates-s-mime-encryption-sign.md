---
title: Podepisování a šifrování e-mailů pomocí S/MIME – Azure | Microsoft Docs
description: Certifikát S/MIME můžete použít nebo povolit k podepisování a šifrování e-mailů v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a31a43cfe45060891c30a7f159123a30b43173d
ms.sourcegitcommit: 488be75cbee88455b33c68a3ec2acb864d461bf8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "41910662"
---
# <a name="smime-email-signing-and-encryption-in-intune"></a>Podepisování a šifrování e-mailů pomocí S/MIME v Intune

> [!IMPORTANT]
> Funkci S/MIME popsanou v tomto článku právě vylepšujeme. V důsledku toho je tato funkce S/MIME z Intune odebraná. Až tuto funkci uvolníme k použití, tuto poznámku odstraníme.

Certifikát S/MIME poskytuje vaší e-mailové komunikaci díky šifrování a dešifrování další úroveň zabezpečení. Microsoft Intune může S/MIME použít k podepisování a šifrování e-mailů odeslaných do mobilních zařízení se systémy iOS, Windows, Windows Phone, Android a macOS.

Na zařízeních s iOSem můžete vytvořit e-mailový profil spravovaný pomocí Intune, který používá S/MIME a certifikáty k podepisování a šifrování příchozích a odchozích e-mailů. Ostatní platformy mohou, ale nemusí, S/MIME podporovat. Pokud S/MIME podporují, můžete na nich nainstalovat certifikáty používající podepisování a šifrování S/MIME. Koncový uživatel potom bude moct ve své e-mailové aplikaci S/MIME zapnout.

Další informace o podepisování a šifrování e-mailů pomocí S/MIME najdete v tématu o [podepisování a šifrování zpráv pomocí S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

## <a name="signing-certificates"></a>Podpisové certifikáty

Certifikáty používané k podepisování umožňují e-mailové aplikaci klienta bezpečně komunikovat s e-mailovým serverem.

Pokud chcete podpisové certifikáty používat, vytvořte ve své certifikační autoritě šablonu, která se zaměřuje na podepisování. V článku o [konfiguraci šablony certifikátu serveru](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) najdete postup k vytvoření šablon certifikátu v certifikační autoritě Microsoft Active Directory.

Podpisové certifikáty v Intune používají certifikáty PKCS. [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md) popisuje, jak certifikát PKCS v prostředí Intune nasadit a používat. K těmto krokům patří:

- Stažení a instalace nástroje Microsoft Intune Certificate Connector, který podporuje žádosti o certifikát PKCS.
- Vytvoření profilu důvěryhodných kořenových certifikátů pro vaše zařízení. Tento krok zahrnuje použití důvěryhodných kořenových a zprostředkujících certifikátů ve vaší certifikační autoritě a následné nasazení tohoto profilu do zařízení.
- Vytvoření profilu certifikátu PKCS pomocí šablony certifikátu, kterou jste vytvořili. Tento profil bude zařízením vystavovat podpisové certifikáty a nasadí do nich profil certifikátu PKCS.

Podpisový certifikát můžete také importovat konkrétnímu uživateli. Podpisový certifikát se potom nasadí na všechna zařízení, která uživatel zaregistruje. Pokud chcete certifikáty importovat do Intune, použijte [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access). Pokud chcete nasadit certifikát PKCS, který jste importovali do Intune k podepisování e-mailů, postupujte podle kroků v článku [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md). K těmto krokům patří:

- Stažení a instalace konektoru certifikátu PFX pro Microsoft Intune. Tento konektor dodává importované certifikáty PKCS zařízením.
- Import podpisových certifikátů e-mailu S/MIME do Intune.
- Vytvoření importovaného profilu certifikátu PKCS. Tento profil dodává importované certifikáty PKCS odpovídajícím zařízením uživatele.

## <a name="encryption-certificates"></a>Certifikáty šifrování

Certifikáty používané k šifrování potvrzují, že šifrovaný e-mail bude moct dešifrovat pouze zamýšlený příjemce. Šifrování S/MIME je další vrstvou zabezpečení, kterou můžete u e-mailové komunikace použít.

Když odesíláte šifrovaný e-mail jinému uživateli, získá se veřejný klíč certifikátu šifrování tohoto uživatele a odeslaný e-mail se zašifruje. Příjemce e-mail dešifruje pomocí privátního klíče na svém zařízení. Uživatelé mohou k šifrování e-mailů používat historii certifikátů. Aby bylo možné e-mail úspěšně dešifrovat, musí se každý z těchto certifikátů nasadit do všech zařízení konkrétního uživatele.

Certifikáty šifrování e-mailu se doporučuje nevytvářet v Intune. Přestože Intune vystavování certifikátů PKCS, které podporují šifrování, umožňuje, vytváří pro každé zařízení jedinečný certifikát. Jedinečné certifikáty pro každé zařízení nejsou u šifrování pomocí S/MIME, u kterého by se certifikát šifrování měl sdílet mezi všemi zařízeními uživatele, vhodné.

Pokud chcete certifikáty S/MIME nasadit pomocí Intune, musíte všechny certifikáty šifrování uživatele importovat do Intune. Intune potom všechny tyto certifikáty nasadí do jednotlivých zařízení, které uživatel zaregistruje. Pokud chcete certifikáty importovat do Intune, použijte [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access).

Pokud chcete nasadit certifikát PKCS, který jste importovali do Intune k šifrování e-mailů, postupujte podle kroků v článku [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md). K těmto krokům patří:

- Stažení a instalace konektoru certifikátu PFX pro Microsoft Intune. Tento konektor dodává importované certifikáty PKCS zařízením.
- Import certifikátů šifrování e-mailu S/MIME do Intune.
- Vytvoření importovaného profilu certifikátu PKCS. Tento profil dodává importované certifikáty PKCS odpovídajícím zařízením uživatele.

 > [!NOTE]
 > Intune importované certifikáty šifrování S/MIME odstraní, když se odeberou firemní data nebo když se uživatelé vyřadí ze správy. U certifikační autority se však certifikáty neodvolají.

## <a name="smime-email-profiles"></a>E-mailové profily S/MIME

Jakmile profily podpisových a šifrovacích certifikátů S/MIME vytvoříte, můžete je [povolit v nativní e-mailové aplikaci pro iOS](email-settings-ios.md).