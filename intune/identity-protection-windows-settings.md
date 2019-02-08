---
title: Windows Hello pro firmy nastavení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech PIN kód, biometrické a ochranu proti falšování identity nastavení v profilu ochrany identit, použití a konfigurace Windows Hello pro firmy na zařízeních s Windows 10 v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bbdb56770c154a482ad004f1f3f980809424caf
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848504"
---
# <a name="windows-10-and-newer-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Nastavení Windows 10 (a novější) zařízení chcete povolit Windows Hello pro firmy v Intune

Tento článek uvádí a popisuje ve Windows Hello pro firmy nastavení můžete řídit na zařízeních s Windows 10 v Intune. Jako součást řešení správy mobilních zařízení použijte toto nastavení použít PIN kód nebo otisk prstu k přihlášení a další.

Jako správce Intune můžete vytvořit a přiřadit tato nastavení pro Windows 10 a novější zařízení.

Další informace o Windows Hello pro firmy profily v Intune, najdete v článku [konfigurovat identity protection](identity-protection-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy

- **Konfigurovat Windows Hello pro firmy**: Chcete-li použít tuto funkci a nakonfigurujete jeho nastavení, zvolte **povolit**.
- **Minimální délka PIN kódu**: Zadejte minimální délku PIN kódu, které chcete povolit v zařízeních. Výchozí délka kódu PIN je 6 znaků. Minimální délka kódu PIN je čtyři (4) znaky.
- **Maximální délka PIN kódu**: Zadejte maximální délku PIN kódu, které chcete povolit v zařízeních. Výchozí délka kódu PIN je šest (6) znaků. Maximální délka kódu PIN je 127 znaků.  
- **Malá písmena v PIN kódu**: Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat malá písmena. Možnosti:

  - **Není povoleno** (výchozí): Zablokuje uživatelům možnost používat malá písmena v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
  - **Povolené**: Povolit uživatelům používat malá písmena v PIN KÓDECH, ale to není nutné.
  - **Vyžaduje**: Uživatelé musí obsahovat aspoň jedno malé písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

- **Velká písmena v PIN kódu**: Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat velká písmena. Možnosti:

  - **Není povoleno** (výchozí): Zablokuje uživatelům možnost používat velká písmena v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
  - **Povolené**: Povolit uživatelům používat velká písmena v PIN KÓDECH, ale to není nutné.
  - **Vyžaduje**: Uživatelé musí obsahovat aspoň jedno velké písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

- **Speciální znaky v PIN kódu**: Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat speciální znaky. Možnosti:

  - **Není povoleno** (výchozí): Zablokuje uživatelům možnost používat speciální znaky v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
    Mezi speciální znaky patří: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Povolené**: Povolit uživatelům používat velká písmena v PIN KÓDECH, ale to není nutné.
  - **Vyžaduje**: Uživatelé musí obsahovat aspoň jedno velké písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

- **Doba platnosti kódu PIN (dny)**: Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí hodnota je 41 dnů.

- **Pamatovat si historii kódů PIN**: Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. Ve výchozím nastavení nelze znovu použít posledních 5 kódů PIN.  
- **Povolit obnovení kódu PIN**: Umožňuje uživatelům změnit si PIN kód s využitím ve Windows Hello pro firmy obnovení služby.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Použít Trusted Platform Module (TPM)**: Čip TPM poskytuje další úroveň zabezpečení dat. Vyberte jednu z těchto hodnot:  
  - **Povolit**: Windows Hello pro firmy můžou zřídit jenom zařízení s přístupným čipem TPM.
  - **Není nakonfigurováno**: Windows Hello pro firmy mohou zřídit všechna zařízení, a to i bez využitelného čipu TPM. Zařízení nejdříve zkusí TPM, a když nebude k dispozici, mohou použít softwarové šifrování.  

- **Povolit biometrické ověřování**: Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:

  - **Povolit**: Windows Hello pro firmy umožňuje biometrické ověřování.
  - **Není nakonfigurováno** (výchozí): Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).

- **Používat rozšířenou ochranu proti falšování identity, pokud je k dispozici**: Zvolte, pokud ochranu proti falšování identity Windows Hello se v zařízení použijí funkce, které ho podporují. Například zjistit fotografie tváře místo skutečné tváře.

  - **Povolit**: Windows vyžaduje, aby všichni uživatelé používali pro funkce rozpoznávání obličeje ochranu proti falšování, pokud je podporovaná.  
  - **Není nakonfigurováno** (výchozí): Windows respektuje konfiguraci proti falšování nastavenou na zařízení.

- **Certifikát pro místní prostředky**: 

  - **Povolit**: Umožňuje funkci Windows Hello pro firmy používat k ověřování místních prostředků certifikáty.
  - **Není nakonfigurováno** (výchozí): Brání funkci Windows Hello pro firmy používat k ověřování místních prostředků certifikáty.  

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
