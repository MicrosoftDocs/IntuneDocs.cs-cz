---
title: Podepisování a šifrování e-mailu pomocí S/MIME – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zjistěte, jak používat digitální certifikáty e-mailu v Microsoft Intune k podepisování a šifrování e-mailů v zařízeních. Tyto certifikáty S/MIME se nazývají a konfigurují pomocí profilů konfigurace zařízení. Podepisování a šifrování certifikáty PKCS nebo privátní certifikáty a použití konektoru pro import certifikátů.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 0339be98bf045d280912bf88e88b5ba544b0a1f4
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203123"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Přehled S/MIME k podepisování a šifrování e-mailu v Intune

E-mailovým certifikátům, označované také jako certifikát S/MIME poskytnout dodatečné zabezpečení e-mailovou komunikaci pomocí šifrování a dešifrování. Microsoft Intune můžete použít certifikáty S/MIME k podepisování a šifrování e-mailů do mobilních zařízení s následujícími platformami:

- Android
- iOS
- macOS
- Windows 10 a novější
- Windows Phone

Na zařízeních s iOSem můžete vytvořit e-mailový profil spravovaný pomocí Intune, který používá S/MIME a certifikáty k podepisování a šifrování příchozích a odchozích e-mailů. Ostatní platformy mohou, ale nemusí, S/MIME podporovat. Pokud je podporovaná, nainstalujte certifikáty, které používají S/MIME podepisování a šifrování. Koncový uživatel potom umožňuje S/MIME ve svých aplikacích e-mailu.

Další informace o podepisování S/MIME e-mailů a šifrování se serverem Exchange najdete v tématu [S/MIME pro zprávu podepisování a šifrování](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

Tento článek obsahuje základní informace o použití k podepisování a šifrování e-mailů v zařízeních certifikáty S/MIME.

## <a name="signing-certificates"></a>Podpisové certifikáty

Certifikáty používané k podepisování umožňují e-mailové aplikaci klienta bezpečně komunikovat s e-mailovým serverem.

Pokud chcete použít podpisové certifikáty, vytvořte šablonu ve vaší certifikační autoritě (CA), který se zaměřuje na podepisování. V článku o [konfiguraci šablony certifikátu serveru](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) najdete postup k vytvoření šablon certifikátu v certifikační autoritě Microsoft Active Directory.

Podpisové certifikáty v Intune používají certifikáty PKCS. [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md) popisuje, jak certifikát PKCS v prostředí Intune nasadit a používat. K těmto krokům patří:

- Stažení a instalace nástroje Microsoft Intune Certificate Connector, který podporuje žádosti o certifikát PKCS.
- Vytvoření profilu důvěryhodných kořenových certifikátů pro vaše zařízení. Tento krok zahrnuje použití důvěryhodných kořenových a zprostředkujících certifikátů ve vaší certifikační autoritě a následné nasazení tohoto profilu do zařízení.
- Vytvoření profilu certifikátu PKCS pomocí šablony certifikátu, kterou jste vytvořili. Tento profil bude zařízením vystavovat podpisové certifikáty a nasadí do nich profil certifikátu PKCS.

Podpisový certifikát můžete také importovat konkrétnímu uživateli. Podpisový certifikát je nasazený na jakémkoli zařízení, která uživatel zaregistruje. Pokud chcete certifikáty importovat do Intune, použijte [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access). Pokud chcete nasadit certifikát PKCS, který jste importovali do Intune k podepisování e-mailů, postupujte podle kroků v článku [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md). K těmto krokům patří:

- Stažení a instalace konektoru certifikátu PFX pro Microsoft Intune. Tento konektor dodává importované certifikáty PKCS zařízením.
- Import podpisových certifikátů e-mailu S/MIME do Intune.
- Vytvoření importovaného profilu certifikátu PKCS. Tento profil dodává importované certifikáty PKCS odpovídajícím zařízením uživatele.

## <a name="encryption-certificates"></a>Certifikáty šifrování

Certifikáty používané k šifrování potvrzují, že šifrovaný e-mail bude moct dešifrovat pouze zamýšlený příjemce. Šifrování S/MIME je další vrstvou zabezpečení, kterou můžete u e-mailové komunikace použít.

Když odesíláte šifrovaný e-mail jinému uživateli, získá se veřejný klíč certifikátu šifrování tohoto uživatele a odeslaný e-mail se zašifruje. Příjemce e-mail dešifruje pomocí privátního klíče na svém zařízení. Uživatelé mohou k šifrování e-mailů používat historii certifikátů. Aby bylo možné e-mail úspěšně dešifrovat, musí se každý z těchto certifikátů nasadit do všech zařízení konkrétního uživatele.

Certifikáty šifrování e-mailu se doporučuje nevytvářet v Intune. Přestože Intune vystavování certifikátů PKCS, které podporují šifrování, umožňuje, vytváří pro každé zařízení jedinečný certifikát. Jedinečné certifikáty pro každé zařízení nejsou u šifrování pomocí S/MIME, u kterého by se certifikát šifrování měl sdílet mezi všemi zařízeními uživatele, vhodné.

Pokud chcete certifikáty S/MIME nasadit pomocí Intune, musíte všechny certifikáty šifrování uživatele importovat do Intune. Intune pak nasadí všech těchto certifikátů na všech zařízeních, která uživatel zaregistruje. Pokud chcete certifikáty importovat do Intune, použijte [rutiny PowerShellu, které jsou k dispozici na GitHubu](https://github.com/Microsoft/Intune-Resource-Access).

Pokud chcete nasadit certifikát PKCS, který jste importovali do Intune k šifrování e-mailů, postupujte podle kroků v článku [Konfigurace a používání certifikátů PKCS pomocí Intune](certficates-pfx-configure.md). K těmto krokům patří:

- Stažení a instalace konektoru certifikátu PFX pro Microsoft Intune. Tento konektor dodává importované certifikáty PKCS zařízením.
- Import certifikátů šifrování e-mailu S/MIME do Intune.
- Vytvoření importovaného profilu certifikátu PKCS. Tento profil dodává importované certifikáty PKCS odpovídajícím zařízením uživatele.

 > [!NOTE]
 > Intune importované certifikáty šifrování S/MIME odstraní, když se odeberou firemní data nebo když se uživatelé vyřadí ze správy. U certifikační autority se však certifikáty neodvolají.

## <a name="smime-email-profiles"></a>E-mailové profily S/MIME

Jakmile profily podpisových a šifrovacích certifikátů S/MIME vytvoříte, můžete je [povolit v nativní e-mailové aplikaci pro iOS](email-settings-ios.md).

## <a name="next-steps"></a>Další postup

- [Používání certifikátů SCEP](certificates-scep-configure.md)
- [Používání certifikátů PKCS](certficates-pfx-configure.md)
- [Použití partnerský server certifikační Autority](certificate-authority-add-scep-overview.md)
- [Vydávání certifikátů PKCS od společnosti Symantec PKI manager webové služby](certificates-symantec-configure.md)
