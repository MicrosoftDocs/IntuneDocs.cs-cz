---
title: "Konfigurace a správa certifikátů PKCS pomocí Intune"
titleSuffix: Intune on Azure
description: "Vytvářejte a přiřazujte certifikáty PKCS pomocí Intune."
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a51d260718e0d0c3984966fab69e202b854c1847
ms.sourcegitcommit: b2467a653ffd36c2248a30b69cb88e3dc7cca2ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Konfigurace a správa certifikátů PKCS pomocí Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>požadavky

Pokud chcete používat certifikáty PKCS společně s Intune, musíte mít následující infrastrukturu:

* Musíte mít nakonfigurovanou službu Active Directory Domain Services (AD DS).
 
  Pokud potřebujete další informace o tom, jak nainstalovat a nakonfigurovat službu AD DS, najdete je v článku [Návrh a plánování a služby AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Musíte mít nakonfigurovanou existující certifikační autoritu (CA) organizace.

  Pokud potřebujete další informace o tom, jak nainstalovat a nakonfigurovat službu AD CS (Active Directory Certificate Services), najdete je v článku [Podrobný průvodce službou AD CS (Active Directory Certificate Services)](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune vyžaduje, abyste službu AD CS spustili pomocí certifikační autority (CA) organizace, nikoli pomocí samostatné certifikační autority.

* Musíte mít klienta, který má připojení k certifikační autoritě organizace.
* Je třeba mít vyexportovanou kopii kořenového certifikátu z vaší certifikační autority organizace.
* Je nutné stáhnout Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) z portálu Intune.
* Musíte mít k dispozici Windows Server pro hostování nástroje Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Export kořenového certifikátu z certifikační autority organizace

Pro ověření pomocí sítě VPN, WiFi nebo jiných prostředků musíte mít certifikát z kořenové nebo zprostředkující certifikační autority v každém zařízení. Následující kroky popisují, jak získat požadovaný certifikát z certifikační autority organizace.

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete příkazový řádek jako správce.
3. Exportujte certifikát kořenové certifikační autority do umístění, kam budete mít později přístup.

   Příklad:

4.  Po dokončení průvodce klikněte před jeho zavřením na **Spustit uživatelské rozhraní konektoru Certificate Connector**.

   `certutil -ca.cert certnew.cer`

   Další informace najdete v tématu [Úkoly programu CertUtil pro správu certifikátů](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Konfigurace šablon certifikátů v certifikační autoritě

1. Přihlaste se do certifikační autority organizace pomocí účtu, který má oprávnění správce.
2. Otevřete konzolu **Certifikační autorita**.
3. Pravým tlačítkem klikněte na **Šablony certifikátů** a pak klikněte na **Spravovat**.
4. Vyhledejte šablonu certifikátu **Uživatel**, klikněte pravým tlačítkem myši a vyberte možnost **Vytvořit duplikát šablony**. Otevře se okno **Vlastnosti nové šablony**.
5. Na kartě **Kompatibilita**:
   * Nastavte pole **Certifikační autorita** na **Windows Server 2008 R2**.
   * Nastavte pole **Příjemce certifikátu** na **Windows 7 / Server 2008 R2**.
6. Na kartě **Obecné**:
   * Nastavte **Zobrazovaný název šablony** na něco smysluplného pro vás.

   > [!WARNING]
   > **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*. Poznamenejte si název šablony pro pozdější použití.

7. Na kartě **Vyřízení žádosti** zaškrtněte políčko **Umožnit export privátního klíče**.
8. Na kartě **Kryptografie** potvrďte, že je **Minimální velikost klíče** nastavená na hodnotu 2048.
9. Na kartě **Název subjektu** zvolte přepínač **Dodán v žádosti**.
10. Na kartě **Rozšíření** zkontrolujte, jestli jsou v rozšíření **Zásady použití** položky Šifrování systému souborů, Zabezpečení e-mailu a Ověření klienta.
    
      > [!IMPORTANT]
      > V případě šablon certifikátů pro iOS a macOS na kartě **Rozšíření** upravte **použití klíče** a ujistěte se, že není vybraná možnost **Podpis je důkazem původu** .

11. Na kartě **Zabezpečení** přidejte účet počítače pro server, na který instalujete Microsoft Intune Certificate Connector.
    * Pro tento účet povolte oprávnění **Číst** a **Zaregistrovat**.
12. Klikněte na tlačítko **Použít** a pak kliknutím na tlačítko **OK** uložíte šablonu certifikátu.
13. Zavřete **konzolu šablon certifikátů**.
14. V konzole **Certifikační autorita** klikněte pravým tlačítkem myši na **Šablony certifikátů**, klikněte na **Nová** a potom klikněte na **Vystavovaná šablona certifikátu**.
    * Vyberte šablonu, kterou jste vytvořili v předchozích krocích, a klikněte na tlačítko **OK**.
15. Aby server spravoval certifikáty jménem zařízení a uživatelů zaregistrovaných v Intune, postupujte takto:

    a. Klikněte pravým tlačítkem na certifikační autoritu a potom vyberte **Vlastnosti**.

    b. Na kartě Zabezpečení přidejte účet počítače pro server, na kterém běží Microsoft Intune Certificate Connector.
      * Udělte oprávnění účtu počítače, která povolují **Vydávat a spravovat certifikáty** a **Vyžádat certifikáty**.
16. Odhlaste se z certifikační autority organizace.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Stažení, instalace a konfigurace nástroje Microsoft Intune Certificate Connector

![ConnectorDownload][ConnectorDownload]

1. Na portálu Azure Portal vyberte **Další služby** > **Monitorování + správa** > **Intune**.
2. V okně **Intune** zvolte **Konfigurace zařízení**. 
3. V okně **Konfigurace zařízení** vyberte **Certifikační autorita**. 
4. Klikněte na **Přidat** a vyberte **Stáhnout konektor**. Uložte stažený soubor do umístění, kam máte přístup ze serveru, na který ho budete instalovat. 
5.  Přihlaste se k serveru, na který chcete nainstalovat Microsoft Intune Certificate Connector.
6.  Spusťte instalační program a přijměte výchozí umístění. Konektor se nainstaluje do C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.
    1. Na stránce možností instalačního programu zvolte **Distribuce PFX** a klikněte na tlačítko **Další**.
    2. Klikněte na tlačítko **Nainstalovat** a počkejte na dokončení instalace.
    3. Na stránce Dokončení zaškrtněte políčko pro **spuštění Intune Connectoru** a klikněte na tlačítko **Dokončit**.
7.  Otevře se okno NDES Connector na kartě **Zápis**. Pokud chcete povolit připojení k Intune, klikněte na **Přihlásit se** a zadejte účet s oprávněním správce.
8.  Na kartě **Upřesnit** můžete nechat vybraný přepínač **Použít účet SYSTEM tohoto počítače (výchozí)**.
9.  Klikněte na tlačítko **Použít** pak **Zavřít**.
10. Nyní se vraťte na portál Azure Portal. V části **Intune** > **Konfigurace zařízení** > **Certifikační autorita** byste po několika minutách měli vidět zelené zaškrtnutí a slovo **Aktivní** v části **Stav připojení**. Toto potvrzení vás informuje o tom, že server konektoru komunikuje s Intune.


## <a name="create-a-device-configuration-profile"></a>Vytvoření profilu konfigurace zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte do **Intune**, **Konfigurace zařízení**, **Profily** a klikněte na **Vytvořit profil**.

   ![NavigateIntune][NavigateIntune]

3. Vyplňte následující informace:
   * Zadejte **Název** profilu.
   * Volitelně můžete nastavit popis.
   * Zadejte **Platformu**, na kterou se má profil nasadit.
   * Nastavte **Typ profilu** na **Důvěryhodný certifikát**.
4. Přejděte na **Nastavení** a zadejte soubor .cer kořenového certifikátu CA, který jste předtím vyexportovali.

   > [!NOTE]
   > V závislosti na platformě, kterou jste zvolili v **kroku 3**, můžete nebo nemusíte mít možnost vybrat **cílové úložiště** certifikátu.

   ![ProfileSettings][ProfileSettings]

5. Kliknutím na tlačítko **OK** a pak na **Vytvořit** profil uložíte.
6. Pokud chcete přiřadit nový profil jednomu nebo více zařízením, viz [Přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu PKCS

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Přejděte do **Intune**, **Konfigurace zařízení**, **Profily** a klikněte na **Vytvořit profil**.
3. Vyplňte následující informace:
   * Zadejte **Název** profilu.
   * Volitelně můžete nastavit popis.
   * Zadejte **Platformu**, na kterou se má profil nasadit.
   * Nastavte **Typ profilu** na **Certifikát PKCS**.
4. Přejděte na **Nastavení** a zadejte následující informace:
   * **Prahová hodnota obnovení (%)** – doporučuje se 20 %.
   * **Období platnosti certifikátu** – pokud jste nezměnili šablonu certifikátu, má být tato možnost nastavená na jeden rok.
   * **Certifikační autorita** – tato možnost je interní plně kvalifikovaný název domény (FQDN) vaší certifikační autority organizace.
   * **Název certifikační autority** – tato možnost je název vaší certifikační autority organizace a může být jiný než předchozí položka.
   * **Název šablony certifikátu** – tato možnost je název šablony, kterou jste vytvořili dříve. Pamatujte, že **Název šablony** je ve výchozím nastavení stejný jako **Zobrazovaný název šablony**, pouze *bez mezer*.
   * **Formát názvu subjektu** – tuto možnost nastavte na **Běžný název**, pokud není potřeba jiný.
   * **Alternativní název subjektu** – tuto možnost nastavte na **Hlavní název uživatele (UPN)**, pokud není potřeba jiný.
   * **Rozšířené použití klíče** – pokud jste v kroku 10 v předchozí části **Konfigurace šablon certifikátů v certifikační autoritě** použili výchozí nastavení, přidejte následující **předdefinované hodnoty** z oblasti výběru:
      * **Libovolný účel**
      * **Ověřování klientů**
      * **Zabezpečený e-mail**
   * **Kořenový certifikát** – (pro profily Android) tato možnost je soubor .cer exportovaný v kroku 3 v předchozí části [Export kořenového certifikátu z certifikační autority organizace](#export-the-root-certificate-from-the-enterprise-ca).

5. Kliknutím na tlačítko **OK** a pak na **Vytvořit** profil uložíte.
6. Pokud chcete přiřadit nový profil jednomu nebo více zařízením, viz článek [Přiřazení profilů zařízení v Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Přechod do Intune na webu Azure Portal a vytvoření nového profilu důvěryhodného certifikátu"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Vytvoření profilu a nahrání důvěryhodného certifikátu"
[ConnectorDownload]: ./media/certificates-download-connector.png "Stažení konektoru certifikátu z portálu Azure Portal"  
