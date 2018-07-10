---
title: Používání certifikátů PKCS s Microsoft Intune – Azure | Micrososft Docs
description: Přidání nebo vytvoření certifikátů PKCS (Public Key Cryptography Standards) v Microsoft Intune, včetně návodu na export kořenového certifikátu, konfigurace šablony certifikátu, stažení a instalace Microsoft Intune Certificate Connectoru (NDES), vytvoření konfiguračního profilu zařízení, vytvoření profilu certifikátu PKCS v Azure a vaší certifikační autority.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b3bfe76173eff76a3175952bef5c6e23ad5e429
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271537"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Konfigurace a používání certifikátů PKCS pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certifikáty slouží k ověření a zabezpečení přístupu k firemním prostředkům, jako je síť VPN nebo Wi-Fi. Tento článek ukazuje, jak exportovat certifikát PKCS a pak ho přidat do profilu Intune. 

## <a name="requirements"></a>požadavky

Pokud chcete používat certifikáty PKCS společně s Intune, musíte mít následující infrastrukturu:

- **Doména služby Active Directory:** Všechny servery uvedené v této části musí být připojené k doméně Active Directory.

  Další informace o instalaci a konfiguraci AD DS najdete v článku [Návrh a plánování služby AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Certifikační autorita** (CA): Certifikační autorita (CA) organizace.

  Další informace o tom, jak nainstalovat a nakonfigurovat AD CS (Active Directory Certificate Services), najdete v [podrobném průvodci službou AD CS](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune vyžaduje, abyste službu AD CS spustili pomocí certifikační autority (CA) organizace, nikoli pomocí samostatné certifikační autority.

- **Klient:** Pro připojení k certifikační autoritě organizace.

- **Kořenový certifikát:** Exportovaná kopie kořenového certifikátu od certifikační autority organizace.

- **Microsoft Intune Certificate Connector**: Instalační program **Certificate Connectoru** (**NDESConnectorSetup.exe**) si můžete stáhnout z webu Azure Portal. 

  Certificate Connector pro NDES také podporuje režim FIPS (Federal Information Processing Standard). Režim FIPS není povinný, ale pokud ho aktivujete, můžete vydávat a odvolávat certifikáty.

- **Windows Server:** Hostuje Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

Pokud chcete k ověření použít síť VPN, Wi-Fi nebo jiné prostředky, potřebujete na každém zařízení certifikát kořenové nebo zprostředkující certifikační autority. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

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

  - Nastavte pole **Certifikační autorita** na **Windows Server 2008 R2**.
  - Nastavte pole **Příjemce certifikátu** na **Windows 7 / Server 2008 R2**.

5. Na kartě **Obecné** nastavte **Zobrazovaný název šablony**. Použijte popisný název.

   > [!WARNING]
   > **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*. Poznamenejte si název šablony, budete ho potřebovat později.

6. Ve **Vyřízení žádosti** vyberte **Umožnit export soukromého klíče**.
7. V **Kryptografii** zkontrolujte, že je **Minimální velikost klíče** nastavená na hodnotu 2048.
8. V **Názvu subjektu** zvolte **Dodat v žádosti**.
9. V **Rozšíření** zkontrolujte, jestli jsou v rozšíření **Zásady použití** položky Šifrování systému souborů, Zabezpečení e-mailu a Ověření klienta.

    > [!IMPORTANT]
    > V případě šablon certifikátů pro iOS přejděte na kartu **Rozšíření**, aktualizujte **Použití klíče** a zkontrolujte, že není vybraná možnost **Podpis je důkazem původu**.

10. V **Zabezpečení** přidejte účet počítače pro server, na který instalujete Microsoft Intune Certificate Connector. Pro tento účet povolte oprávnění **Číst** a **Zaregistrovat**.
11. Klikněte na **Použít** a pak kliknutím na **OK** uložte šablonu certifikátu.
12. Zavřete **konzolu šablon certifikátů**.
13. V konzole **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů**, klikněte na **Nová** a potom klikněte na **Vystavovaná šablona certifikátu**. Zvolte šablonu, kterou jste vytvořili v předchozích krocích, a vyberte **OK**.
14. Aby server spravoval certifikáty jménem zařízení a uživatelů zaregistrovaných v Intune, postupujte takto:

    1. Klikněte pravým tlačítkem na certifikační autoritu a potom vyberte **Vlastnosti**.
    2. Na kartě Zabezpečení přidejte účet počítače pro server, na kterém běží Microsoft Intune Certificate Connector. Udělte oprávnění účtu počítače, která povolují **Vydávat a spravovat certifikáty** a **Vyžádat certifikáty**.

15. Odhlaste se z certifikační autority organizace.

## <a name="download-install-and-configure-the-certificate-connector"></a>Stažení, instalace a konfigurace Certificate Connectoru

![ConnectorDownload][ConnectorDownload]

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** a potom **Certifikační autorita**.
4. Vyberte **Přidat** a **Stáhnout soubor konektoru**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který ho budete instalovat.
5. Po dokončení stahování se přihlaste k serveru. Další kroky:

    1. Zkontrolujte, že je nainstalované rozhraní .NET 4.5 Framework, protože ho vyžaduje NDES Certificate Connector. Rozhraní .NET 4.5 Framework je automaticky součástí Windows Serveru 2012 R2 a novějších verzí.
    2. Spusťte instalační program (NDESConnectorSetup.exe) a potvrďte výchozí umístění. Konektor se nainstaluje do `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`. V možnostech instalačního programu vyberte **distribuci PFX**. Pokračujte až do konce instalace.

6. NDES Connector otevře kartu **registrace**. Pokud chcete povolit připojení k Intune, **přihlaste se** a zadejte účet s globálním oprávněním správce.
7. Na kartě **Upřesnit** nechte vybranou možnost **Použít účet SYSTEM tohoto počítače (výchozí)**.
8. Vyberte **Použít** a pak **Zavřít**.
9. Přejděte zpět na portál Azure Portal (**Intune** > **Konfigurace zařízení** > **Certifikační autorita**). Po chvíli se zobrazí zelené zaškrtnutí a **Stav připojení** bude **Aktivní**. Váš server konektoru teď může komunikovat s Intune.

> [!NOTE]
> NDES Certificate Connector podporuje také protokol TLS 1.2. Pokud server s nainstalovaným NDES Certificate Connectorem podporuje TLS 1.2, použije se TLS 1.2. Pokud server nepodporuje TLS 1.2, použije se TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

## <a name="create-a-device-configuration-profile"></a>Vytvoření profilu konfigurace zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.

   ![NavigateIntune][NavigateIntune]

3. Zadejte tyto vlastnosti:

  - Zadejte **Název** profilu.
  - Volitelně můžete nastavit popis.
  - Zadejte **Platformu**, na kterou se má profil nasadit.
  - Nastavte **Typ profilu** na **Důvěryhodný certifikát**.

4. Přejděte na **Nastavení** a zadejte soubor .cer kořenového certifikátu CA, který jste předtím vyexportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 3**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

   ![ProfileSettings][ProfileSettings]

5. Výběrem **OK** a pak **Vytvořit** profil uložíte.
6. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

  - Zadejte **Název** profilu.
  - Volitelně můžete nastavit popis.
  - Zadejte **Platformu**, na kterou se má profil nasadit.
  - Nastavte **Typ profilu** na **Certifikát PKCS**.

4. Přejděte na **Nastavení** a zadejte tyto vlastnosti:

  - **Prahová hodnota obnovení (%)** – doporučuje se 20 %.
  - **Období platnosti certifikátu** – pokud jste nezměnili šablonu certifikátu, může být tato možnost nastavená na jeden rok.
  - **Certifikační autorita** – zobrazuje interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.
  - **Název certifikační autority** – uvádí název vaší certifikační autority organizace a může být jiný než předchozí položka.
  - **Název šablony certifikátu** – název šablony, kterou jste dříve vytvořili. Pamatujte, že **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*.
  - **Formát názvu subjektu** – tuto možnost nastavte na **Běžný název**, pokud není potřeba jiný.
  - **Alternativní název subjektu** – tuto možnost nastavte na **Hlavní název uživatele (UPN)**, pokud není potřeba jiný.
  - **Rozšířené použití klíče** – pokud jste v kroku 10 v části [Konfigurace šablon certifikátů v certifikační autoritě](#configure-certificate-templates-on-the-certification-authority) (v tomto článku) použili výchozí nastavení, přidejte následující **předdefinované hodnoty** z výběru:
    - **Libovolný účel**
    - **Ověřování klientů**
    - **Zabezpečený e-mail**
  - **Kořenový certifikát** – (pro profily Android) uvádí soubor .cer exportovaný v kroku 3 v části [Export kořenového certifikátu z certifikační autority organizace](#export-the-root-certificate-from-the-enterprise-ca) (v tomto článku).

5. Výběrem **OK** a pak **Vytvořit** profil uložíte.
6. Informace o přiřazení nového profilu jednomu nebo více zařízením najdete v článku o [přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="next-steps"></a>Další kroky
[Použití certifikátů SCEP](certificates-scep-configure.md) nebo [vydání certifikátů PKCS z webové služby správce infrastruktury veřejných klíčů Symantec](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Přechod do Intune na webu Azure Portal a vytvoření nového profilu důvěryhodného certifikátu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Vytvoření profilu a nahrání důvěryhodného certifikátu"
[ConnectorDownload]: ./media/certificates-download-connector.png "Stažení konektoru certifikátu z portálu Azure Portal"  
