---
title: "Vytvoření profilu VPN aplikace pro Android pomocí připojení Pulse Secure"
description: "Pro zařízení s Androidem spravovaná pomocí Intune můžete vytvořit profil VPN pro aplikaci."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5dd8b1318acc035ed3fee410eea7ac5d08065844
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a>Použití vlastních zásad pro vytvoření profilu sítě VPN pro aplikaci pro zařízení se systémem Android

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pro zařízení s Androidem verze 5.0 a novější spravovaná pomocí Intune můžete vytvořit profil VPN pro jednotlivé aplikace. Nejdříve vytvoříte profil VPN, který používá typ připojení Pulse Secure nebo Citrix. Potom vytvoříte vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím. 

Po nasazení zásad pro skupiny zařízení nebo uživatelů Android by uživatelé měli spustit VPN Pulse Secure nebo Citrix. Připojení pak umožní provoz jenom z určených aplikací, které budou moct používat otevřené připojení VPN.

> [!NOTE]
>
> Pro tento profil se podporují jenom připojení Pulse Secure a Citrix.


### <a name="step-1-create-a-vpn-profile"></a>Krok 1: Vytvoření profilu sítě VPN

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** > **Přidat zásadu**.
2. Vyberte šablonu pro novou zásadu. Rozbalte **Android** a potom zvolte **Profil VPN (Android 4 a novější)**.
3. V šabloně v části **typ připojení** zvolte **Pulse Secure** nebo **Citrix**.
4. Dokončete profil VPN a uložte ho. Další podrobnosti o profilech VPN najdete v tématu [Připojení VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).

> [!NOTE]
>
> Poznamenejte si **název připojení VPN (zobrazený uživatelům)**. Tuto hodnotu jste zadali při vytvoření profilu VPN. Budete ji potřebovat v dalším kroku. Příklad: **profil_VPN_pro_moje_aplikace**.

### <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2: Vytvoření vlastní zásady konfigurace

   1. V konzole správce Intune zvolte **Zásady** > **Přidat zásadu** > **Android** > **Vlastní konfigurace** > **Vytvořit zásadu**.
   2. Zadejte název pro tuto zásadu.
   3. V části **Nastavení OMA-URI** zvolte **Přidat**.
   4. Zadejte název nastavení.
   5. Jako **Datový typ** určete **String** (Řetězec).
   6. Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/PackageList**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/PackageList**.
   7.   Do pole **Hodnota** zadejte seznam balíčků (oddělených středníkem), které mají být k tomuto profilu přidružené. Pokud třeba chcete, aby připojení VPN používal Excel a prohlížeč Google Chrome, zadejte **com.microsoft.office.excel;com.android.chrome**.

![Příklad vlastní zásady VPN pro aplikaci pro Android](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)
  Pomocí hodnoty *BLACKLIST* můžete určit, že jde o seznam aplikací, pro které **není povoleno** použít připojení VPN. Ostatní aplikace se budou připojovat prostřednictvím VPN.
Další možností je určit pomocí hodnoty **WHITELIST** aplikace, které *jediné* budou moci připojení VPN používat. Aplikace, které nejsou v seznamu, se nebudou připojovat prostřednictvím VPN.
  1.    V nastavení **OMA-URI** zvolte **Přidat**.
  2.    Zadejte název nastavení.
  3.    Jako **Datový typ** určete **String** (Řetězec).
  4.    Pro **OMA-URI** použijte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/Mode**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/Mode**.
  5.    Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.



### <a name="step-3-deploy-both-policies"></a>Krok 3: Nasazení obou zásad

*Obě* zásady musíte nasadit *stejným* skupinám Intune.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.
2.  V dialogovém okně **Spravovat nasazení** :
    -   **Pokud chcete zásadu nasadit**, vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a pak vyberte **Přidat** > **OK**.
    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady**, zvolte **Zrušit**.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru **Řídicí panel** zobrazí shrnutí stavu.
