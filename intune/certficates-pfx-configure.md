---
title: Používání certifikátů PKCS s Microsoft Intune – Azure | Micrososft Docs
description: Přidání nebo vytvoření certifikátů PKCS (Public Key Cryptography Standards) pomocí Microsoft Intune včetně postupu, jak exportovat kořenový certifikát, nakonfigurovat šablonu certifikátu, stáhnout a nainstalovat Microsoft Intune Certificate Connector, vytvořit konfigurační profil zařízení, vytvořit profil certifikátu PKCS v Azure a vaší certifikační autoritě
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61a190be2b4685030438988dab0d0134a8fa9f9b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurace a používání certifikátů PKCS pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certifikáty slouží k ověření a zabezpečení přístupu k firemním prostředkům, jako je síť VPN nebo Wi-Fi. Tento článek ukazuje, jak exportovat certifikát PKCS a pak ho přidat do profilu Intune. 

## <a name="requirements"></a>požadavky

Pokud chcete používat certifikáty PKCS společně s Intune, musíte mít následující infrastrukturu:

* Musíte mít nakonfigurovanou službu Active Directory Domain Services (AD DS).
 
  Další informace o instalaci a konfiguraci AD DS najdete v článku [Návrh a plánování služby AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Musíte mít nakonfigurovanou existující certifikační autoritu (CA) organizace.

  Další informace o tom, jak nainstalovat a nakonfigurovat AD CS (Active Directory Certificate Services), najdete v [podrobném průvodci službou AD CS](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune vyžaduje, abyste službu AD CS spustili pomocí certifikační autority (CA) organizace, nikoli pomocí samostatné certifikační autority.

* Musíte mít klienta, který má připojení k certifikační autoritě organizace.
* Je třeba mít vyexportovanou kopii kořenového certifikátu z vaší certifikační autority organizace.
* Je nutné stáhnout Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) z portálu Intune.
* Musíte mít Windows Server pro hostování nástroje Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

Pro ověření pomocí sítě VPN, WiFi nebo jiných prostředků musíte mít v každém zařízení certifikát z kořenové nebo zprostředkující certifikační autority. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete příkazový řádek jako správce.
3. Exportujte certifikát kořenové certifikační autority (.cer) do umístění, kam budete mít později přístup.

   Příklad:

4. Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

   `certutil -ca.cert certnew.cer`

   Další informace najdete v tématu [Úkoly programu CertUtil pro správu certifikátů](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Konfigurace šablon certifikátů v certifikační autoritě

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete konzolu **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů** a vyberte **Spravovat**.
3. Vyhledejte šablonu certifikátu **Uživatel**, klikněte pravým tlačítkem myši a vyberte možnost **Vytvořit duplikát šablony**. Otevřou se **Vlastnosti nové šablony**.
4. Na kartě **Kompatibilita**: 
   * Nastavte pole **Certifikační autorita** na **Windows Server 2008 R2**.
   * Nastavte pole **Příjemce certifikátu** na **Windows 7 / Server 2008 R2**.
5. Na kartě **Obecné**:
   * Nastavte **Zobrazovaný název šablony** na něco smysluplného pro vás.

   > [!WARNING]
   > **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*. Poznamenejte si název šablony, budete ho potřebovat později.

6. Ve **Vyřízení žádosti** vyberte **Umožnit export soukromého klíče**.
7. V **Kryptografii** zkontrolujte, že je **Minimální velikost klíče** nastavená na hodnotu 2048.
8. V **Názvu subjektu** zvolte **Dodat v žádosti**.
9. V **Rozšíření** zkontrolujte, jestli jsou v rozšíření **Zásady použití** položky Šifrování systému souborů, Zabezpečení e-mailu a Ověření klienta.
    
      > [!IMPORTANT]
      > V případě šablon certifikátů pro iOS přejděte na kartu **Rozšíření**, aktualizujte **Použití klíče** a zkontrolujte, že není vybraná možnost **Podpis je důkazem původu**.

10. V **Zabezpečení** přidejte účet počítače pro server, na který instalujete Microsoft Intune Certificate Connector.
    * Pro tento účet povolte oprávnění **Číst** a **Zaregistrovat**.
11. Klikněte na **Použít** a pak kliknutím na **OK** uložte šablonu certifikátu.
12. Zavřete **konzolu šablon certifikátů**.
13. V konzole **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů**, klikněte na **Nová** a potom klikněte na **Vystavovaná šablona certifikátu**.
    * Vyberte šablonu, kterou jste vytvořili v předchozích krocích, a zvolte **OK**.
14. Aby server spravoval certifikáty jménem zařízení a uživatelů zaregistrovaných v Intune, postupujte takto:

    a. Klikněte pravým tlačítkem na certifikační autoritu a potom vyberte **Vlastnosti**.

    b. Na kartě Zabezpečení přidejte účet počítače pro server, na kterém běží Microsoft Intune Certificate Connector.
      * Udělte oprávnění účtu počítače, která povolují **Vydávat a spravovat certifikáty** a **Vyžádat certifikáty**.
15. Odhlaste se z certifikační autority organizace.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Stažení, instalace a konfigurace nástroje Microsoft Intune Certificate Connector

![ConnectorDownload][ConnectorDownload]

1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyfiltrujte **Intune**. Vyberte **Microsoft Intune** a pak vyberte **Konfigurace zařízení**. 
2. Vyberte **Certifikační autorita**, vyberte **Přidat**a pak **Stáhnout soubor konektoru**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který se bude instalovat. 
3. Přihlaste se k tomuto serveru a spusťte instalační program: 

    1. Přijměte výchozí umístění. Konektor se nainstaluje do `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`.
    2. V možnostech instalačního programu vyberte **Distribuce PFX** a vyberte **Další**.
    3. Klikněte na **Nainstalovat** a počkejte na dokončení instalace.
    4. Po dokončení zaškrtněte **Spustit konektor Intune** a pak zvolte **Dokončit**.

4. Mělo by se otevřít okno NDES Connector na kartě **Zápis**. Pokud chcete povolit připojení k Intune, vyberte **Přihlásit se** a zadejte účet s globálním oprávněním správce.
5. Na kartě **Upřesnit** nechte vybranou možnost **Použít účet SYSTEM tohoto počítače (výchozí)**.
6. Vyberte **Použít** a pak **Zavřít**.
7. Přejděte zpět na portál Azure Portal (**Intune** > **Konfigurace zařízení** > **Certifikační autorita**). Po několika minutách se zobrazí zelená značka zaškrtnutí a **Stav připojení** je **Aktivní**. Váš server konektoru teď může komunikovat s Intune.

## <a name="create-a-device-configuration-profile"></a>Vytvoření profilu konfigurace zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte do **Intune**, **Konfigurace zařízení**, **Profily** a vyberte **Vytvořit profil**.

   ![NavigateIntune][NavigateIntune]

3. Zadejte tyto vlastnosti:
   * Zadejte **Název** profilu.
   * Volitelně můžete nastavit popis.
   * Zadejte **Platformu**, na kterou se má profil nasadit.
   * Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

4. Přejděte na **Nastavení** a zadejte soubor .cer kořenového certifikátu CA, který jste předtím vyexportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 3**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

   ![ProfileSettings][ProfileSettings]

5. Výběrem **OK** a pak **Vytvořit** profil uložíte.
6. Pokud chcete přiřadit nový profil jednomu nebo více zařízením, přečtěte si článek [Přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte do **Intune**, **Konfigurace zařízení**, **Profily** a vyberte **Vytvořit profil**.
3. Zadejte tyto vlastnosti:
   * Zadejte **Název** profilu.
   * Volitelně můžete nastavit popis.
   * Zadejte **Platformu**, na kterou se má profil nasadit.
   * Nastavte **Typ profilu** na **Certifikát PKCS**.
4. Přejděte na **Nastavení** a zadejte tyto vlastnosti:
   * **Prahová hodnota obnovení (%)** – doporučuje se 20 %.
   * **Období platnosti certifikátu** – pokud jste nezměnili šablonu certifikátu, může být tato možnost nastavená na jeden rok.
   * **Certifikační autorita** – zobrazuje interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.
   * **Název certifikační autority** – uvádí název vaší certifikační autority organizace a může být jiný než předchozí položka.
   * **Název šablony certifikátu** – název šablony, kterou jste dříve vytvořili. Pamatujte, že **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*.
   * **Formát názvu subjektu** – tuto možnost nastavte na **Běžný název**, pokud není potřeba jiný.
   * **Alternativní název subjektu** – tuto možnost nastavte na **Hlavní název uživatele (UPN)**, pokud není potřeba jiný.
   * **Rozšířené použití klíče** – pokud jste v kroku 10 v části [Konfigurace šablon certifikátů v certifikační autoritě](#configure-certificate-templates-on-the-certification-authority) (v tomto článku) použili výchozí nastavení, přidejte následující **předdefinované hodnoty** z výběru:
      * **Libovolný účel**
      * **Ověřování klientů**
      * **Zabezpečený e-mail**
   * **Kořenový certifikát** – (pro profily Android) uvádí soubor .cer exportovaný v kroku 3 v části [Export kořenového certifikátu z certifikační autority organizace](#export-the-root-certificate-from-the-enterprise-ca) (v tomto článku).

5. Výběrem **OK** a pak **Vytvořit** profil uložíte.
6. Pokud chcete přiřadit nový profil jednomu nebo více zařízením, viz článek [Přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Přechod do Intune na webu Azure Portal a vytvoření nového profilu důvěryhodného certifikátu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Vytvoření profilu a nahrání důvěryhodného certifikátu"
[ConnectorDownload]: ./media/certificates-download-connector.png "Stažení konektoru certifikátu z portálu Azure Portal"  
