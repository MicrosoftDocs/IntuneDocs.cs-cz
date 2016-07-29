---
title: "VPN pro aplikaci pro Android pomocí Pulse Secure | Microsoft Intune"
description: "Pro zařízení s Androidem spravovaná pomocí Intune můžete vytvořit profil VPN pro aplikaci."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: d6d929b83b967cc4efdc84ecc3262c5c1f509351


---

# Použití vlastních zásad pro vytvoření profilu sítě VPN pro aplikaci pro zařízení se systémem Android

Pro zařízení s Androidem spravovaná pomocí Intune můžete vytvořit profil VPN pro aplikaci. Nejdřív vytvoříte profil VPN, který používá typ připojení Pulse Secure, a potom vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím. Po nasazení těchto zásad do skupin uživatelů nebo zařízení s Androidem, otevření jedné ze zadaných aplikací na těchto zařízeních způsobí, že se pro tuto aplikaci otevře připojení VPN.

### Krok 1: Vytvoření profilu sítě VPN

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** > **Přidat zásadu**.
2. Vyberte šablonu pro novou zásadu. Rozbalte **Android** a potom zvolte **Profil VPN (Android 4 a novější)**.

3. V šabloně v části **typ připojení** zvolte **Pulse Secure**.
4. Dokončete profil VPN a uložte ho. Další podrobnosti o profilech VPN najdete v tématu [Připojení VPN](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Poznamenejte si název profilu sítě VPN, abyste ho mohli použít v dalším kroku. Příklad: **profil_VPN_pro_moje_aplikace**.

### Krok 2: Vytvoření vlastní zásady konfigurace

   1. V konzole správce Intune vyberte **Zásady** -> **Přidat zásadu** -> **Android** -> **Vlastní konfigurace** -> **Vytvořit zásadu**.
   2. Zadejte název pro tuto zásadu.
   3. V části **Nastavení OMA-URI** klikněte na **Přidat**.
   4. Zadejte název nastavení.
   5. Jako **Datový typ** zadejte **String**.
   6. Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/PackageList**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/PackageList**.
   7.   Do pole **Hodnota** zadejte seznam balíčků (oddělených středníkem), které by měly být k tomuto profilu přidružené.  Pokud třeba chcete, aby připojení VPN používal Excel a prohlížeč Google Chrome, zadejte **com.microsoft.office.excel;com.android.chrome**.


   ![Příklad vlastní zásady VPN pro aplikaci pro Android](..\media\android_per_app_vpn_oma_uri.png)
#### Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)
Pomocí hodnoty *BLACKLIST* můžete určit, že se seznamu aplikací **nepovolí** použít připojení VPN.  Ostatní aplikace se budou připojovat prostřednictvím VPN.

Další možností je určit pomocí hodnoty *WHITELIST*, že připojení VPN budou moci používat **jenom** zadané aplikace.


1.  V části Nastavení OMA-URI klikněte na **Přidat**.
2.  Zadejte název nastavení.
3.  Jako **Datový typ** zadejte **String**.
4.  Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/Mode**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/Mode**.
5.  Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.



### Krok 3: Nasazení obou zásad

*Obě* zásady musíte nasadit *stejným* skupinám Intune.

   1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a pak klikněte na **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a pak klikněte na **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.



<!--HONumber=Jul16_HO4-->


