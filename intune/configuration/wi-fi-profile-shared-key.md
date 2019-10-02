---
title: Vytvoření profilu Wi-Fi s předsdíleným klíčem – Microsoft Intune – Azure | Microsoft Docs
description: Pokud chcete v Microsoft Intune vytvořit profil Wi-Fi s předsdíleným klíčem, použijte vlastní profil a získáte ukázkový kód XML pro profily Wi-Fi založené na Androidu, Windows a protokolu EAP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 175be4d51b034745ce6fab050f68be277f1d4858
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730426"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key---intune"></a>Vytvoření profilu Wi-Fi s předsdíleným klíčem pomocí vlastního profilu zařízení – Intune
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Předsdílené klíče (PSK) se obvykle používají k ověřování uživatelů v sítích Wi-Fi nebo bezdrátových sítích LAN. V Intune můžete vytvořit profil Wi-Fi s využitím předsdíleného klíče. Pokud chcete vytvořit profil, použijte funkci **vlastních profilů zařízení** v Intune. Tento článek také obsahuje několik příkladů vytvoření profilu Wi-Fi založeného na protokolu EAP.

> [!IMPORTANT]
>- Při použití předsdíleného klíče ve Windows 10 se v Intune zobrazí chyba odstranění problému. Když k ní dojde, profil Wi-Fi se správně přiřadí k zařízení a profil bude fungovat podle očekávání.
>- Pokud exportujete profil Wi-Fi s předsdíleným klíčem, ověřte si, že je soubor chráněný. Klíč má formát prostého textu, takže jeho ochranu zajišťujete vy.

## <a name="before-you-begin"></a>Před zahájením

- Může být pro vás snadnější zkopírovat kód z počítače připojeného k síti, jak je popsáno dále v tomto článku.
- Přidáním dalších nastavení OMA-URI můžete přidat více sítí a klíčů.
- Pro iOS nastavte profil nástrojem Apple Configurator na stanici Mac.
- PSK vyžaduje řetězec 64 číslic v šestnáctkovém formátu nebo heslo o délce 8 až 63 tisknutelných znaků ASCII. Některé znaky, například hvězdička (*), nejsou podporovány.

## <a name="create-a-custom-profile"></a>Vytvoření vlastního profilu
Můžete vytvořit vlastní profil s předsdíleným klíčem pro profil Wi-Fi založený na Androidu, Windows nebo protokolu EAP. Pokud chcete vytvořit profil na portálu Azure Portal, projděte si část [Vytvoření vlastního nastavení zařízení](custom-settings-configure.md). Při vytvoření profilu zařízení zvolte jako platformu zařízení možnost **Vlastní**. Nevybírejte profil Wi-Fi. Když vyberete možnost Vlastní, nezapomeňte provést toto: 

1. Zadejte název a popis profilu.
2. Přidejte nové nastavení OMA-URI s následujícími vlastnostmi: 

   a. Zadejte název pro toto nastavení sítě Wi-Fi.

   b. (Volitelné) Zadejte popis nastavení OMA-URI nebo pole ponechte prázdné.

   c. Nastavte **Datový typ** na **String**.

   d. **OMA-URI:**

   - **Pro Android**: ./Vendor/MSFT/WiFi/Profile/SSID/Settings
   - **Pro Windows**: ./Vendor/MSFT/WiFi/Profile/SSID/WlanXml

     > [!NOTE]
     > Nezapomeňte použít tečku na začátku.

     SSID je identifikátor SSID, pro který vytváříte zásadu. Pokud má například síť Wi-Fi název `Hotspot-1`, zadejte `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

   e. **Hodnota pole**: Sem vkládáte svůj kód XML. Podívejte se na příklady v tomto článku. Aktualizujte jednotlivé hodnoty tak, aby odpovídaly nastavení vaší sítě. Nějaké pokyny najdete v sekci komentáře ke kódu.
3. Vyberte **OK**, zásadu uložte a pak přiřaďte.

    > [!NOTE]
    > Tuto zásadu je možné přiřadit pouze skupinám uživatelů.

Pro každé zařízení, které se příště vrátí se změnami, se použijí zásady a vytvoří se pro ně profil Wi-Fi. Zařízení se potom připojí k síti automaticky.

## <a name="android-or-windows-wi-fi-profile-example"></a>Příklad profilu Wi-Fi pro Android nebo Windows

Následující příklad zahrnuje kód XML pro profil Wi-Fi pro Android nebo Windows: Příklad uvádíme proto, abychom ukázali správný formát a poskytli více podrobností. Je to jenom příklad a není myšlen jako doporučená konfigurace pro vaše prostředí.

### <a name="important-considerations"></a>Důležité informace

- `<protected>false</protected>` je třeba nastavit na hodnotu **nepravda**. Nastavení hodnoty **pravda** by mohlo způsobit, že zařízení by očekávalo šifrované heslo, následně by se ho pokoušelo dešifrovat a to by vedlo k selhání připojení.

- `<hex>53534944</hex>`má být nastaveno na šestnáctkovou hodnotu `<name><SSID of wifi profile></name>`. Zařízení s Windows 10 můžou vracet falešnou chybu `x87D1FDE8 Remediation failed`, ale zařízení pořád obsahuje profil.

- XML má speciální znaky, například `&` (ampersand). Použití speciálních znaků může zabránit tomu, aby XML fungovalo podle očekávání. 

### <a name="example"></a>Příklad

``` xml
<!--
<hex>53534944</hex> = The hexadecimal value of <name><SSID of wifi profile></name>
<Name of wifi profile> = Name of profile shown to users. It could be <name>Your Company's Network</name>.
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped. It could be <name>Your Company's Network</name>.
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network, such as AES.
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Plain text of the password to connect to the network
-->

<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile-example"></a>Příklad profilu Wi-Fi založeného na protokolu EAP
Následující příklad obsahuje kód XML pro profil Wi-Fi založený na protokolu EAP: Příklad uvádíme proto, abychom ukázali správný formát a poskytli více podrobností. Je to jenom příklad a není myšlen jako doporučená konfigurace pro vaše prostředí.


```xml
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Vytvoření souboru XML z existujícího připojení Wi-Fi

Můžete také vytvořit soubor XML z existujícího připojení Wi-Fi. V počítači se systémem Windows použijte následující postup:

1. Vytvořte místní složku pro exportované profily W-Fi, například c:\WiFi.
2. Otevřete příkazový řádek jako správce (klikněte pravým tlačítkem `cmd` @ no__t-1**Spustit jako správce**).
3. Spusťte `netsh wlan show profiles`. Zobrazí se názvy všech profilů.
4. Spusťte `netsh wlan export profile name="YourProfileName" folder=c:\Wifi`. Tento příkaz vytvoří soubor s názvem `Wi-Fi-YourProfileName.xml` v c:\Wifi.

    - Pokud exportujete profil Wi-Fi, který obsahuje předsdílený klíč, přidejte do příkazu `key=clear`:
  
      `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

      `key=clear` exportuje klíč do prostého textu, který je požadován pro úspěšné použití profilu.

Až budete mít soubor XML, zkopírujte a vložte syntax XML do nastavení OMA-URI > **datový typ**. [Vytvoření vlastního profilu](#create-a-custom-profile) (v tomto článku) obsahuje seznam kroků.

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` zahrnuje také všechny profily ve formátu XML.

## <a name="best-practices"></a>Osvědčené postupy

- Než profil Wi-Fi s předsdíleným klíčem nasadíte, ověřte, jestli se zařízení může přímo připojit ke koncovému bodu.

- Při střídání klíčů (hesla nebo hesla) očekává prostoje a naplánujte nasazení. Zvažte zavedení nových profilů Wi-Fi mimo pracovní dobu. Také upozorněte uživatele, že může být ovlivněno připojení.

- Pokud chcete zajistit hladký přechod, ujistěte se, že je zařízení koncového uživatele alternativním připojením k Internetu. Koncový uživatel například může přejít zpátky na Host WiFi (nebo na jinou síť Wi-Fi) nebo mít mobilní připojení ke komunikaci s Intune. Toto připojení navíc mu umožní i nadále přijímat aktualizace zásad, když dojde k aktualizaci firemního profilu Wi-Fi na zařízení.
