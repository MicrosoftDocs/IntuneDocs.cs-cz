---
title: nastavení funkce zařízení s macOS v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazovat všechna nastavení konfigurace zařízení s macOS k tiskárnám v Microsoft Intune. Viz také kroky k získání IP adresy, cestu a nastavení portu serveru AirPrint ve vaší síti. Pomocí těchto nastavení v profilu konfigurace zařízení můžete nakonfigurovat zařízení s macOS, abyste mohli používat servery AirPrint ve vaší síti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4973dc5038ecfe9a8e909df1a1db3feceb30979b
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565328"
---
# <a name="macos-device-feature-settings-in-intune"></a>nastavení funkce zařízení s macOS v Intune

Intune obsahuje některé předdefinované nastavení, které povolí macOS uživatelům tisknout do tiskárny s Airprintem ve vaší síti. Tento článek uvádí tato nastavení a popisuje, co dělá jednotlivých nastavení. Jsou také uvedené kroky k získání IP adresy, cesta a port AirPrint tiskárny, které používají aplikaci terminál (emulátor).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení s macOS](device-features-configure.md).

## <a name="airprint-settings"></a>Nastavení AirPrint

1. V **nastavení**vyberte **AirPrint**. Zadejte následující vlastnosti AirPrint serveru:

    - **IP adresa**: Zadejte adresu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu pomocí příkazu ping tiskáren v aplikaci terminál. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
    - **Cesta**: Zadejte cestu k tiskárně. Cesta je obvykle `ipp/print` pro tiskárny ve vaší síti. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
    - **Port**: Zadejte naslouchající port cíle AirPrint. Pokud tuto vlastnost nezadáte, AirPrint použije výchozí port. K dispozici v Iosu 11.0 a novějších.
    - **TLS**: Zvolte **povolit** k zabezpečení připojení AirPrint pomocí zabezpečení TLS (Transport Layer). K dispozici v Iosu 11.0 a novějších.

2. Vyberte **Přidat**. AirPrint server se přidá do seznamu. Můžete přidat více serverů AirPrint.

    Můžete také **Import** soubor oddělených čárkou (.csv), který obsahuje seznam tiskárny s Airprintem. Po přidání tiskárny s Airprintem v Intune, můžete také **exportovat** tohoto seznamu.

3. Až budete hotovi, vyberte **OK** k uložení seznamu.

## <a name="get-the-ip-address-and-path"></a>Získat IP adresu a cestu

Přidání serverů AirPrinter, potřebujete IP adresu z tiskárny, cestu prostředku a port. Následující kroky ukazují, jak získat tyto informace.

1. Na Macu, který je připojený ke stejné místní síti (stejná podsíť) jako tiskárny s Airprintem, otevřete **terminálu** (z **/aplikace/Utility**).
2. V aplikaci terminál, zadejte `ippfind`, a vyberte možnost enter.

    Poznámka: informace o tiskárně. Například může vrátit podobně jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`, a vyberte možnost enter.

   Poznamenejte si IP adresu. Například může vrátit podobně jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adres a prostředků cestu. V tomto příkladu je IP adresa `10.50.25.21`, a cesta prostředku je `/ipp/port1`.

## <a name="next-steps"></a>Další postup

- Zobrazit všechna nastavení [iOS](ios-device-features-settings.md) zařízení.
- Tento profil přiřadit ke skupinám; Zobrazit [přiřazení profilů zařízení](device-profile-assign.md).
