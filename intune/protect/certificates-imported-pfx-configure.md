---
title: Použití importovaných certifikátů PFX v Microsoft Intune – Azure | Microsoft Docs
description: Používejte importované certifikáty PKCS (Public Key Cryptography Standards) s Microsoft Intune, včetně importu certifikátů, konfigurace šablony certifikátu, instalace Intune Imported Certificate Connectoru a vytvoření importovaného souboru PKCS. Profil certifikátu.
keywords: ''
author: ralms
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d54c58523fdb44080b6c4210d639f9ad0ce476e2
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801549"
---
# <a name="configure-and-use-imported-pkcs-certificates-with-intune"></a>Konfigurace a používání importovaných certifikátů PKCS pomocí Intune

Microsoft Intune podporuje použití importovaných certifikátů PKCS (Public Key párové), které se běžně používají pro šifrování S/MIME s e-mailovými profily. Některé e-mailové profily v Intune podporují možnost Povolit S/MIME, kde můžete definovat podpisový certifikát S/MIME a certifikát šifrování S/MIME.

Šifrování s/MIME je náročné, protože e-mail je zašifrovaný pomocí konkrétního certifikátu. Musíte mít privátní klíč certifikátu, který šifruje e-mail na zařízení, ve kterém tento e-mail čtete, aby ho bylo možné dešifrovat. Šifrovací certifikáty se pravidelně obnovují, což znamená, že pro všechna vaše zařízení budete možná potřebovat historii šifrování, aby bylo možné číst starší e-maily.  Vzhledem k tomu, že je potřeba použít stejný certifikát pro všechna zařízení, není možné pro tento účel použít profily certifikátů [SCEP](certificates-scep-configure.md) nebo [PKCS](certficates-pfx-configure.md) , protože tyto mechanismy pro doručování certifikátů poskytují jedinečné certifikáty pro každé zařízení.

Další informace o použití S/MIME s Intune získáte [pomocí s/MIME k šifrování e-mailu](certificates-s-mime-encryption-sign.md).

## <a name="requirements"></a>požadavky

K používání importovaných certifikátů PKCS s Intune budete potřebovat následující infrastrukturu:

- **Konektor certifikátu PFX pro Microsoft Intune**:

  Každý tenant Intune podporuje jednu instanci tohoto konektoru. Tento konektor můžete nainstalovat na stejný server jako instanci konektoru Microsoft Intune Certificate Connector.

  Tento konektor zpracovává požadavky na soubory PFX importované do Intune pro šifrování e-mailu S/MIME pro konkrétního uživatele.

  Tento konektor se může automaticky aktualizovat, jakmile budou k dispozici nové verze. Chcete-li použít možnost aktualizace, je nutné zajistit, aby byly brány firewall otevřené, aby konektor mohl kontaktovat **AutoUpdate.msappproxy.NET** na portu **443**.

  Další informace o všech síťových koncových bodech, ke kterým konektor přistupuje, najdete v tématu [požadavky na konfiguraci sítě Intune a šířku pásma](../fundamentals/network-bandwidth-use.md).

- **Windows Server**:  
  K hostování konektoru certifikátů PFX pro Microsoft Intune používáte Windows Server.  Konektor slouží ke zpracování požadavků na certifikáty importované do Intune.

  Intune podporuje instalaci *Microsoft Intune Certificate Connector* na stejném serveru jako *konektor certifikátu PFX pro Microsoft Intune*.

  Pro podporu konektoru musí na serveru běžet rozhraní .NET 4,6 nebo vyšší. Pokud není rozhraní .NET 4,6 nainstalované při spuštění instalace konektoru, instalace konektoru se automaticky nainstaluje.

- **Visual studio 2015 nebo novější** (volitelné): pomocí sady Visual Studio sestavíte modul PowerShellu pomocníka s rutinami pro import certifikátů PFX do Microsoft Intune. Pokud chcete získat pomocné rutiny PowerShellu, přečtěte si téma [projekt PFXImport PowerShellu v GitHubu](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="how-it-works"></a>Jak to funguje

Když použijete Intune k nasazení **importovaného certifikátu PFX** pro uživatele, jsou kromě zařízení k dispozici dvě komponenty:

- **Intune Service**: ukládá certifikáty PFX v zašifrovaném stavu a zpracovává nasazení certifikátu pro uživatelské zařízení.  Hesla, která chrání privátní klíče certifikátů, se šifrují předtím, než se nahrají pomocí modulu hardwarového zabezpečení (HSM) nebo kryptografie Windows. to zajistí, že Intune nebude mít přístup k privátnímu klíči kdykoli.

- **PFX Certificate Connector pro Microsoft Intune**: když zařízení požaduje certifikát PFX, který se importoval do Intune, pošle se do konektoru šifrované heslo, certifikát a veřejný klíč zařízení.  Konektor dešifruje heslo pomocí místního privátního klíče a pak před odesláním certifikátu zpátky do Intune znovu zašifruje heslo (a všechny plist profily, pokud používáte iOS) s klíčem zařízení.  Intune pak doručí certifikát do zařízení a zařízení bude schopné ho dešifrovat pomocí privátního klíče zařízení a nainstalovat certifikát.

## <a name="download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune"></a>Stažení, instalace a konfigurace konektoru certifikátů PFX pro Microsoft Intune

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte možnost **Správa tenanta** > **konektory a tokeny** > **konektory certifikátů** > **Přidat**.

   ![Konektor certifikátu PFX pro stažení Microsoft Intune](./media/certificates-imported-pfx-configure/download-imported-pfxconnector.png)

3. Postupujte podle pokynů ke stažení *Certificate Connectoru PFX pro Microsoft Intune* do umístění, které je přístupné ze serveru, na který budete konektor instalovat.

4. Po dokončení stahování se přihlaste k serveru a spusťte instalační program (PfxCertificateConnectorBootstrapper. exe).  
   - Když přijmete výchozí umístění instalace, konektor se nainstaluje do `Program Files\Microsoft Intune\PFXCertificateConnector`.
   - Služba konektoru běží pod místním systémovým účtem. Pokud je pro přístup k Internetu vyžadován proxy server, ověřte, že účet místní služby má přístup k nastavení proxy serveru.

5. Konektor certifikátu PFX pro Microsoft Intune se po instalaci otevře na kartě **Zápis**. Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce pro Azure nebo s oprávněním správce pro Intune.

   > [!WARNING]
   > Ve výchozím nastavení je **Konfigurace rozšířeného zabezpečení** Windows serveru IE nastavená na **zapnuto** , což může způsobit problémy s přihlášením k Office 365.

6. Okno zavřete.

7. V centru pro správu Microsoft Endpoint Manageru se vraťte do části **Správa tenanta** > **konektory a tokeny** > **konektory certifikátů**. Za chvíli se zobrazí zelená značka zaškrtnutí a aktualizuje se stav připojení. Server konektoru teď může komunikovat s Intune.

## <a name="import-pfx-certificates-to-intune"></a>Import certifikátů PFX do Intune

Pomocí [Microsoft Graph](https://docs.microsoft.com/graph) můžete importovat certifikáty PFX uživatelů do Intune. [PFXImport projekt prostředí PowerShell pomocníka na GitHubu](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) poskytuje rutiny pro snadné provádění operací.

Pokud dáváte přednost použití vlastního řešení pomocí grafu, použijte [typ prostředku userPFXCertificate](https://docs.microsoft.com/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta).

### <a name="build-pfximport-powershell-project-cmdlets"></a>Sestavit rutiny projektu PowerShellu pro PFXImport

Pokud chcete používat rutiny PowerShellu, sestavíte projekt sami pomocí sady Visual Studio. Tento proces je rovnou dopředný a i když ho může běžet na serveru, doporučujeme ho spustit na pracovní stanici.  

1. Přejděte do kořenového adresáře úložiště [Intune – přístup k prostředkům](https://github.com/microsoft/Intune-Resource-Access) na GitHubu a pak stáhněte nebo naklonujte úložiště pomocí Gitu do svého počítače.

   ![Tlačítko pro stažení GitHubu](./media/certificates-imported-pfx-configure/github-download.png)

2. Přejít na `.\Intune-Resource-Access-develop\src\PFXImportPowershell\` a otevřít projekt pomocí sady Visual Studio pomocí souboru **PFXImportPS. sln**.

3. V horní části se změňte z **ladění** na **release**.

4. Přejít na **sestavení** a vybrat **PFXImportPS sestavení**. Po chvíli se zobrazí potvrzení **úspěšného sestavení** se zobrazí v levém dolním rohu sady Visual Studio.

   ![Možnost sestavení sady Visual Studio](./media/certificates-imported-pfx-configure/vs-build-release.png)

5. Proces sestavení vytvoří novou složku s modulem PowerShell na `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release`.

   Tuto složku pro **vydání** použijete pro další kroky.

### <a name="create-the-encryption-public-key"></a>Vytvoření veřejného klíče šifrování

Naimportujete certifikáty PFX a jejich privátní klíče do Intune. Heslo chránící soukromý klíč je šifrované veřejným klíčem, který je uložený místně. Pro generování a ukládání párů veřejného a privátního klíče můžete použít kryptografii systému Windows, modul hardwarového zabezpečení nebo jiný typ kryptografie.  V závislosti na typu používané kryptografie se dá pár veřejného a privátního klíče exportovat ve formátu souboru pro účely zálohování.

Modul PowerShell poskytuje metody pro vytvoření klíče pomocí Kryptografie systému Windows. Pomocí jiných nástrojů můžete také vytvořit klíč.  

#### <a name="to-create-the-encryption-key-using-windows-cryptography"></a>Vytvoření šifrovacího klíče pomocí Kryptografie systému Windows

1. Zkopírujte složku pro *vydání* vytvořenou aplikací Visual Studio na server, na který jste nainstalovali **Certificate Connector PFX pro Microsoft Intune**. Tato složka obsahuje modul prostředí PowerShell.

2. Na serveru otevřete *PowerShell* jako správce a pak přejděte do složky pro *vydání* , která obsahuje modul prostředí PowerShell.

3. Pokud chcete modul naimportovat, spusťte `Import-Module .\IntunePfxImport.psd1` a importujte modul.

4. Dále spusťte `Add-IntuneKspKey "Microsoft Software Key Storage Provider" "PFXEncryptionKey"`

   > [!TIP]
   > Poskytovatele, kterého použijete, musí být vybrán znovu při importu certifikátů PFX. Můžete použít **poskytovatele úložiště klíčů od Microsoftu**, i když se podporuje použití jiného poskytovatele. Název klíče je také k dispozici jako příklad a můžete použít jiný název klíče podle vašeho výběru.

   Pokud plánujete importovat certifikát z pracovní stanice, můžete tento klíč exportovat do souboru pomocí následujícího příkazu: `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path to write to>"`

   Privátní klíč musí být importován na serveru, který je hostitelem konektoru certifikátů PFX pro Microsoft Intune, aby bylo možné úspěšně zpracovat importované certifikáty PFX.

#### <a name="to-use-a-hardware-security-module-hsm"></a>Použití modulu hardwarového zabezpečení (HSM)

K vygenerování a uložení páru veřejného a privátního klíče můžete použít modul hardwarového zabezpečení (HSM). Další informace najdete v dokumentaci poskytovatele HSM.

### <a name="import-pfx-certificates"></a>Importovat certifikáty PFX

Následující postup používá rutiny prostředí PowerShell jako příklad importu certifikátů PFX. V závislosti na vašich požadavcích můžete vybrat různé možnosti.

Vaše možnosti jsou:  
- Zamýšlený účel (skupiny certifikátů na základě značky):  
  - nepřiřazené
  - Šifrování smimeencryption
  - smimeSigning

- Schéma odsazení:  
  - výplně PKCS1
  - oaepSha1
  - oaepSha256
  - oaepSha384
  - oaepSha512

Vyberte poskytovatele úložiště klíčů, který odpovídá poskytovateli, který jste použili k vytvoření klíče.

#### <a name="to-import-the-pfx-certificate"></a>Import certifikátu PFX  

1. Exportujte certifikáty z jakékoli certifikační autority (CA) podle dokumentace od poskytovatele.  Pro službu Microsoft Active Directory Certificate Services můžete použít [Tento ukázkový skript](https://gallery.technet.microsoft.com/Export-CMPfxCertificatesFro-d55f687b).

2. Na serveru otevřete *PowerShell* jako správce a pak přejděte do složky pro *vydání* , která obsahuje modul prostředí PowerShell.

3. Pokud chcete modul naimportovat, spusťte `Import-Module .\IntunePfxImport.psd1`

4. Pokud chcete provést ověření v Intune Graph, spusťte `$authResult = Get-IntuneAuthenticationToken -AdminUserName "<Admin-UPN>"`

   > [!NOTE]
   > Vzhledem k tomu, že je ověřování spuštěno v grafu, je nutné zadat oprávnění k AppID. Pokud jste tento nástroj použili poprvé, vyžaduje se *globální správce* . Rutiny PowerShellu používají stejný AppID jako ten, který se používá při použití [ukázek PowerShellu pro Intune](https://github.com/microsoftgraph/powershell-intune-samples).

5. Převeďte heslo pro každý soubor PFX, který importujete, do zabezpečeného řetězce spuštěním `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force`.

6. Pokud chcete vytvořit objekt **UserPFXCertificate** , spusťte `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>"`

   Příklad: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption" "pkcs1"`

   > [!NOTE]
   > Když importujete certifikát z jiného systému, než je server, na kterém je konektor nainstalovaný, použijte následující příkaz, který zahrnuje cestu k souboru klíče: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

7. Import objektu **UserPFXCertificate** do Intune spuštěním `Import-IntuneUserPfxCertificate -AuthenticationResult $authResult -CertificateList $userPFXObject`

8. Pokud chcete ověřit, že se certifikát naimportoval, spusťte `Get-IntuneUserPfxCertificate -AuthenticationResult $authResult -UserList "<UserUPN>"`

Další informace o dalších dostupných příkazech najdete v souboru Readme v [projektu PFXImport PowerShellu na GitHubu](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Vytvoření importovaného profilu certifikátu PKCS

Po importování certifikátů do Intune vytvořte profil **importovaného certifikátu PKCS** a přiřaďte ho ke skupinám Azure Active Directory.

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfigurační profil** > **vytvořit profil**.

3. Zadejte následující vlastnosti:

   - Zadejte **Název** profilu.
   - Volitelně můžete nastavit popis.
   - Zadejte **Platformu**, na kterou se má profil nasadit.
   - Nastavte **Typ profilu** na **Importovaný certifikát PKCS**.

4. Vyberte **Nastavení**a zadejte následující vlastnosti:

   - **Zamýšlený účel**: Určete zamýšlený účel certifikátů, které jsou importované pro tento profil. Správci mohou importovat certifikáty s různými zamýšlenými účely (například podepisování S/MIME nebo šifrování S/MIME). Zamýšlený účel vybraný v profilu certifikátu odpovídá profilu certifikátu se správně importovanými certifikáty. Zamýšlený účel je značka pro seskupení importovaných certifikátů společně a nezaručuje, že certifikáty importované s touto značkou budou vyhovovat zamýšlenému účelu.  
   - **Období platnosti certifikátu**: Pokud se v šabloně certifikátu nezměnila doba platnosti, tato možnost je ve výchozím nastavení nastavená na jeden rok.
   - **Zprostředkovatel úložiště klíčů (KSP):** U systému Windows vyberte, kde na zařízení se mají klíče ukládat.

5. Vyberte **OK** > **Vytvořit** a profil uložte.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. [Přiřaďte](../configuration/device-profile-assign.md) nový profil zařízení.
