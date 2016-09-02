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
ms.sourcegitcommit: a2464a9d2276319f75a3da7db70c2613152bed9b
ms.openlocfilehash: 177ed5f693b8f1ce16d96e1b3e729630d661475f


---

# Použití vlastních zásad pro vytvoření profilu sítě VPN pro aplikaci pro zařízení se systémem Android

Pro zařízení s Androidem spravovaná pomocí Intune můžete vytvořit profil VPN pro jednotlivé aplikace. Nejdřív vytvoříte profil VPN, který používá typ připojení Pulse Secure. Potom vytvoříte vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím. Po nasazení těchto zásad do skupin uživatelů nebo zařízení s Androidem způsobí otevření jedné ze zadaných aplikací, že se pro tuto aplikaci otevře spojení VPN.

> [!NOTE]
>
> Pro tento profil se podporuje jenom připojení Pulse Secure.


### Krok 1: Vytvoření profilu sítě VPN

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** > **Přidat zásadu**.
2. Vyberte šablonu pro novou zásadu. Rozbalte **Android** a potom zvolte **Profil VPN (Android 4 a novější)**.
3. V šabloně v části **typ připojení** zvolte **Pulse Secure**.
4. Dokončete profil VPN a uložte ho. Další podrobnosti o profilech VPN najdete v tématu [Připojení VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).

> [!NOTE]
>
> Poznamenejte si název profilu sítě VPN pro použití v dalším kroku. Například profil_VPN_pro_moje_aplikace.

### Krok 2: Vytvoření vlastní zásady konfigurace

   1. V konzole správce Intune zvolte **Zásady** > **Přidat zásadu** > **Android** > **Vlastní konfigurace** > **Vytvořit zásadu**.
   2. Zadejte název pro tuto zásadu.
   3. V části **Nastavení OMA-URI** zvolte **Přidat**.
   4. Zadejte název nastavení.
   5. Jako **Datový typ** určete **String** (Řetězec).
   6. Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/PackageList**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/PackageList**.
   7.   Do pole **Hodnota** zadejte seznam balíčků (oddělených středníkem), které mají být k tomuto profilu přidružené. Pokud třeba chcete, aby připojení VPN používal Excel a prohlížeč Google Chrome, zadejte **com.microsoft.office.excel;com.android.chrome**.


    ![Příklad vlastní zásady VPN pro aplikaci pro Android](..\media\android_per_app_vpn_oma_uri.png)

#### Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)
  Pomocí hodnoty *BLACKLIST* můžete určit, že jde o seznam aplikací, pro které **není povoleno** použít připojení VPN. Ostatní aplikace se budou připojovat prostřednictvím VPN.
Další možností je určit pomocí hodnoty **WHITELIST** aplikace, které *jediné* budou moci připojení VPN používat. Aplikace, které nejsou v seznamu, se nebudou připojovat prostřednictvím VPN.
  1.    V nastavení **OMA-URI** zvolte **Přidat**.
  2.    Zadejte název nastavení.
  3.    Jako **Datový typ** určete **String** (Řetězec).
  4.    Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/Mode**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/Mode**.
  5.    Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.



### Krok 3: Nasazení obou zásad

*Obě* zásady musíte nasadit *stejným* skupinám Intune.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.
2.  V dialogovém okně **Spravovat nasazení** :
    -   **Pokud chcete zásadu nasadit**, vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a pak vyberte **Přidat** > **OK**.
    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady**, zvolte **Zrušit**.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru **Řídicí panel** zobrazí shrnutí stavu.



<!--HONumber=Aug16_HO3-->


