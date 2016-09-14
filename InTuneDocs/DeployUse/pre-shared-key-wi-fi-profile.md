---
title: "Wi-Fi pomocí PSK | Microsoft Intune"
description: "Použijte vlastní konfiguraci k vytvoření profilu sítě Wi-Fi s předsdíleným klíčem."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf8da72092a2380e73cfbed2a693831706b40d23
ms.openlocfilehash: c005a1b38289580b1543e0e62cbb4cd00cb22c47



---
# Vytvoření profilu Wi-Fi s předsdíleným klíčem
Zde je postup používání **Vlastní konfigurace** služby Intune k vytvoření profilu sítě Wi-Fi s předsdíleným klíčem. Toto téma obsahuje také příklad vytvoření profilu Wi-Fi založeného na protokolu EAP.

> [!NOTE]
-   Pokud je to pro vás snadnější, můžete zkopírovat kód z počítače připojeného k této síti, jak je popsáno níže.
- Pro Android máte také možnost použít nástroj [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/), který poskytuje Johnathon Biersack.
-   Přidáním dalších nastavení OMA-URI můžete přidat více sítí a klíčů.
-  Pro iOS nastavte profil nástrojem Apple Configurator na stanici Mac. Alternativně můžete použít nástroj [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/), který poskytuje Johnathon Biersack.


1.  Pokud chcete vytvořit profil sítě Wi-Fi s předsdíleným klíčem pro Android nebo Windows, případně profil Wi-Fi založený na protokolu EAP, zvolte při vytváření zásady možnost **Vlastní konfigurace** pro platformu zařízení, namísto profilu Wi-Fi.

2.  Zadejte název a popis.
3.  Přidejte nové nastavení OMA-URI:

   a.   Zadejte název pro toto nastavení sítě Wi-Fi.

   b.   Zadejte popis nastavení OMA-URI nebo pole ponechte prázdné.

   c.   **Datový typ:** Nastavte na Řetězec (XML).

   d.   **OMA-URI:**

    - **Pro Android:** ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Pro Windows:** ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Nezapomeňte použít tečku na začátku.

    SSID je identifikátor SSID, pro který vytváříte zásadu. Příklad:
    `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e. **Hodnota pole**: Sem vkládáte svůj kód XML. Tady je příklad. Každá hodnota by měla být přizpůsobena nastavení sítě. Nějaké pokyny najdete v sekci komentáře ke kódu.
4. Zvolte **OK** a uložení. Poté zásadu nasaďte.

    > [!NOTE]
Tuto zásadu lze nasadit pouze do skupin uživatelů.

Pro každé zařízení, které se příště vrátí se změnami, se použijí zásady a vytvoří se pro ně profil Wi-Fi. Zařízení se bude moct připojit k síti automaticky.
## Profil Wi-Fi pro Android nebo Windows

Zde je příklad kódu XML pro profil Wi-Fi pro Android nebo Windows:

    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
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
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>

## Profil Wi-Fi založený na protokolu EAP
Zde je příklad kódu XML pro profil Wi-Fi založený na protokolu EAP:

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

## Vytvoření souboru XML z existujícího připojení Wi-Fi
Můžete také vytvořit soubor XML z existujícího připojení Wi-Fi:
1. Na počítači, který je připojený k bezdrátové síti nebo se k ní nedávno připojil, otevřete následující složku: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Nejvhodnější je použít počítač, který je připojený k co nejmenšímu počtu bezdrátových sítí, protože budete muset prohledávat každý profil, abyste našli ten správný.
3.     Prohledejte soubory XML a najděte ten se správným názvem.
4.     Po vyhledání správného souboru XML zkopírujte kód XML a vložte ho do pole Data na stránce nastavení OMA-URI.

## Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit**, vyberte jednu nebo několik skupin, do kterých chcete zásady nasadit, a potom vyberte **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – zvolte **Zrušit**.

Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

### Viz taky
[Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


