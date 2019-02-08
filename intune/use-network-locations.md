---
title: Vazba zařízení s Androidem na síťové umístění v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte a nakonfigurujte síťová umístění v Microsoft Intune pro zařízení s Androidem. Zařízení můžete na základě jejich síťového umístění označovat jako nevyhovující. Pokud se zařízení octne mimo síťové umístění, můžete zablokovat přístup k prostředkům společnosti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: da29f4fcdbd694b2817bf4eca953c37d2d3c6b0e
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848181"
---
# <a name="use-locations-network-fence-in-intune"></a>Použití funkce Umístění (ohraničení sítě) v Intune

Můžete chtít blokovat přístup k firemní síti v případě, že zařízení opustí umístění. Tuto možnost nabízí v Intune funkce **Umístění**. 

Můžete vytvořit zásady dodržování předpisů založené na síťovém umístění, které se také označují jako ohraničení sítě. Tyto zásady zajišťují, že pokud mají zařízení vyhovovat, musí být připojená k pracovní síti. Tyto zásady se dají používat se zásadami podmíněného přístupu, aby zařízení měla přístup k pracovním prostředkům *jenom* v případě, že jsou připojená k pracovní síti. Když není zařízení připojené k pracovní síti, stane se nevyhovujícím a ztratí přístup k pracovním prostředkům.

Vezměte v úvahu následující scénář:

Někteří zaměstnanci ve vašem výrobním závodě používají zařízení s Androidem. Zaměstnanci si odnášejí zařízení s Androidem mimo závod nebo továrnu. Abyste zabránili neoprávněnému přístupu, můžete:

1. Vytvořit umístění s rozsahem IPv4, které nazvete **Výrobní podlaží**.
2. Vytvořit zásady dodržování předpisů, který vyžadují, aby tato zařízení byla připojená k vaší firemní síti, a tyto zásady přiřadit.
3. Pokud se zařízení octne mimo výrobní závod, bude považované za nevyhovující a nebude mít přístup k firemním prostředkům.

Kromě toho můžete přidat [akce při nedodržení předpisů](#configure-the-actions-for-noncompliance). Jakmile bude zařízení zpět v místním prostředí a v síťovém umístění, získá znovu přístup k firemním prostředkům.

## <a name="prerequisites"></a>Požadavky

Vytvoření zásad dodržování předpisů založených na síťovém umístění:

- Vytvořte síťová umístění jako rozsahy sítě IPV4 pro server brány, server DHCP a/nebo server DNS, ke kterým se zařízení připojují.
- Vytvořte zásady dodržování předpisů používající tato umístění a definujte akci, která se má provést, když zařízení přestane být připojené k síťovému umístění.
- Používejte zařízení s Androidem verze 6.0 nebo novější s aktualizovanou aplikací Portál společnosti.

## <a name="create-a-location"></a>Vytvoření umístění

1. V Intune vyberte **Dodržování předpisů zařízením** > **Umístění** > **Vytvořit**.

2. Zadejte tyto vlastnosti:  

   - Povinný parametr. Zadejte **Název** umístění, například **Výrobní podlaží** nebo **Budova 44 – zabezpečená**.
   - Volitelné. Zadejte **rozsah IPv4** s notací CIDR (Classless Interdomain Routing), například `aaa.bbb.ccc.ddd/n`.
   - Volitelné. Zadejte adresu **brány IPv4**, například `aaa.bbb.ccc.ddd`.
   - Volitelné. Zadejte adresu **serveru DHCP IPv4**, například `aaa.bbb.ccc.ddd`.
   - Volitelné. Zadejte seznam adres **serverů DNS IPv4**. Toto nastavení používá **shodu podmnožin**. Pokud servery DNS IPv4 na zařízení jsou podmnožinami definovaných hodnot, zařízení je považované za zařízení UVNITŘ ohraničení. Každou adresu zadejte na samostatném řádku, například:  
     `aaa.bbb.ccc.ddd`  
     `aaa.bbb.ccc.ddd`
   - Volitelné. Zadejte seznam **přípon DNS**. Toto nastavení používá **shodu podmnožin**. Pokud přípony DNS na zařízení jsou podmnožinami definovaných hodnot, zařízení je považované za zařízení UVNITŘ ohraničení. Každou doménu zadejte na samostatném řádku, například:  
     `contoso.com`  
     `contoso.org`

3. **Uložte** provedené změny.

## <a name="create-the-location-compliance-policy"></a>Vytvoření zásad dodržování předpisů založených na síťovém umístění

Při vytváření zásad dodržování předpisů vyberte pro položku **Platforma** možnost **Android**. V seznamu **Umístění** můžete zvolit jedno nebo více síťových umístění, která jste přidali. Tato umístění jsou součástí ohraničení sítě, které vytváříte pro vaše zařízení.

Některé pokyny najdete v tématu o [vytvoření zásad dodržování předpisů založených na síťovém umístění](compliance-policy-create-android.md#locations).

## <a name="configure-the-actions-for-noncompliance"></a>Konfigurace akcí při nedodržení předpisů

Po vytvoření zásad dodržování předpisů platí pro zařízení výchozí akce při nedodržení předpisů. Můžete přidat další akce. Můžete třeba přidat akci, která odešle e-mail uživateli, když zařízení přestane být vyhovující z hlediska umístění.

Některé pokyny najdete v tématu o [přidání akcí při nedodržení předpisů](actions-for-noncompliance.md).

## <a name="company-portal-app"></a>Aplikace Portál společnosti

Když je zařízení připojené k vašim umístěním, zobrazuje se v aplikaci Portál společnosti jako vyhovující. Pokud není zařízení připojené k některému z vašich umístění, zobrazuje se jako nevyhovující.

## <a name="next-steps"></a>Další postup
[Monitorování zásad dodržování předpisů zařízením](compliance-policy-monitor.md)  
[Začínáme se zásadami dodržování předpisů](device-compliance-get-started.md)
