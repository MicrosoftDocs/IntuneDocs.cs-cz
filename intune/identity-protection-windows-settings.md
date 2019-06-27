---
title: Windows Hello pro firmy nastavení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech PIN kód, biometrické a ochranu proti falšování identity nastavení v profilu ochrany identit, použití a konfigurace Windows Hello pro firmy na zařízeních s Windows 10 v Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 1cbf45fc337cbe7d7a45081a3b9e05002ca126d8
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402926"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Nastavení zařízení Windows 10 a povolit Windows Hello pro firmy v Intune

Tento článek uvádí a popisuje ve Windows Hello pro firmy nastavení můžete řídit na zařízeních s Windows 10 v Intune. Jako správce Intune můžete nakonfigurovat a přiřadit tato nastavení pro zařízení s Windows 10 jako součást řešení správy mobilních zařízení. 

Můžete najít další informace o těchto nastaveních [konfigurovat Windows Hello pro firmy zásady nastavení](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings), v dokumentaci Windows Hello.


Další informace o Windows Hello pro firmy profily v Intune, najdete v článku [konfigurovat identity protection](identity-protection-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy
- **Konfigurovat Windows Hello pro firmy**:
  - **Není nakonfigurováno** – vyberte toto nastavení, pokud nechcete, aby chcete Intune používat pro ovládací prvek Windows Hello pro firmy nastavení. Veškerá stávající nastavení Windows Hello pro firmy v zařízeních s Windows 10 se nezmění. Žádná ostatní nastavení v podokně nejsou dostupná.

  - **Zakázané** – Pokud už nechcete používat Windows Hello pro firmy, vyberte toto nastavení. Všechna ostatní nastavení na obrazovce jsou nedostupná.
  - **Povolené** – vyberte toto nastavení, pokud chcete, nakonfigurujete Windows Hello pro firmy.  
  
  **Výchozí**: Není nakonfigurováno

  Pokud je nastavena na *povoleno*, jsou dostupná následující nastavení:

    - **Minimální délka PIN kódu**  
     Zadejte minimální délku PIN kódu pro zařízení, abychom zabezpečené přihlašování. Výchozí nastavení pro zařízení Windows jsou šest znaků, ale toto nastavení můžete vynutit minimálně 4 až 127 znaků. 
  
      **Výchozí**: *Není nakonfigurováno*

    - **Maximální délka PIN kódu**  
    Zadejte maximální délku PIN kódu pro zařízení, abychom zabezpečené přihlašování. Výchozí nastavení pro zařízení Windows jsou šest znaků, ale toto nastavení můžete vynutit minimálně 4 až 127 znaků.  

      **Výchozí**: *Není nakonfigurováno*  

    - **Malá písmena v PIN kódu**  
      Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat malá písmena. Možnosti:

      - **Není povoleno** – zablokuje uživatelům možnost používat malá písmena v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
      - **Povolené** – uživatelům povolit používání malých písmen v PIN KÓDECH, ale to není nutné.
      - **Vyžaduje** – uživatelé musí obsahovat aspoň jedno malé písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

    - **Velká písmena v PIN kódu**  
    Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat velká písmena. Možnosti:

      - **Není povoleno** – zablokuje uživatelům možnost používat velká písmena v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
      - **Povolené** – uživatelům povolit používání velkých písmen v PIN KÓDECH, ale to není nutné.
      - **Vyžaduje** – uživatelé musí obsahovat aspoň jedno velké písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

    - **Speciální znaky v PIN kódu**  
    Můžete vynutit silnější kódy PIN tím, že koncoví uživatelé vyžaduje obsahovat speciální znaky. Mezi speciální znaky patří: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  
 
      Možnosti:
      - **Není povoleno** – zablokuje uživatelům možnost používat speciální znaky v PIN KÓDECH. K tomuto chování dochází i když toto nastavení není nakonfigurované.
      - **Povolené** – uživatelům povolit používání velkých písmen v PIN KÓDECH, ale to není nutné.
      - **Vyžaduje** – uživatelé musí obsahovat aspoň jedno velké písmeno v PIN KÓDECH. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

      **Výchozí**: Není povoleno

  - **Doba platnosti kódu PIN (dny)**  
      Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí nastavení zařízení Windows je 41 dnů.

    **Výchozí**: Nenakonfigurováno

  - **Pamatovat si historii kódů PIN**  
    Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. Windows výchozí zařízení pro zabránění opětovné použití posledních pět kódů PIN.  

    **Výchozí**: Nenakonfigurováno  

  - **Povolit obnovení kódu PIN**   
    Umožňuje uživateli používat ve Windows Hello pro firmy obnovení služby. 
    
    - **Povolené** – kód PIN pro obnovení tajný klíč uložený na zařízení a uživatel může změnit kód PIN, v případě potřeby.  
    - **Zakázané** -tajný kód pro obnovení není vytvořen nebo uložené.

    **Výchozí**: Není nakonfigurováno

  - **Použít Trusted Platform Module (TPM)**    
    Čip TPM poskytuje další úroveň zabezpečení dat.  

    - **Povolené** – pouze pro zařízení s přístupným čipem TPM můžete zřídit Windows Hello pro firmy.
    - **Není nakonfigurováno** – zařízení se nejdřív pokusí použít čip TPM. Pokud není dostupný, můžou použít softwarové šifrování.
    
    **Výchozí**: Není nakonfigurováno

  - **Povolit biometrické ověřování**  
     Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:

    - **Povolit** – Windows Hello pro firmy umožňuje biometrické ověřování.
    - **Není nakonfigurováno** – Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).

    **Výchozí**: Není nakonfigurováno

  - **Používat rozšířenou ochranu proti falšování identity, pokud je k dispozici**  
    Konfiguruje, jestli se v zařízení použijí funkce ochrany proti falšování identity Windows Hello, pokud je zařízení podporuje (třeba rozpoznání fotografie tváře místo skutečné tváře).  
    - **Povolit** – Windows vyžaduje všichni uživatelé používali ochranu proti falšování identity pro funkce rozpoznávání obličeje, který je podporováno.
    - **Není nakonfigurováno** – Windows respektuje ochranu proti falšování identity konfigurace v zařízení.

    **Výchozí**: Není nakonfigurováno

  - **Certifikát pro místní prostředky**  

    - **Povolit** – umožňuje Windows Hello pro firmy používat certifikáty k ověřování k prostředkům na pracovišti.
    - **Není nakonfigurováno** – brání Windows Hello pro firmy používat certifikáty k ověřování k prostředkům na pracovišti. Místo toho použijte výchozí chování zařízení *ověřovací key důvěryhodnosti v místním*. Další informace najdete v tématu [uživatelský certifikát pro ověřování v místním](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) v dokumentaci Windows Hello.  

  **Výchozí**: Není nakonfigurováno

- **Použití klíčů zabezpečení pro přihlášení**  
  Toto nastavení je dostupné pro zařízení se systémem Windows 10 verze 1903 nebo novější. Použijte ho ke správě podporu pro použití klíčů zabezpečení Windows Hello pro přihlášení.  

  - **Povolené** – uživatelé můžou používat klíč zabezpečení Windows Hello, jak přihlašovací údaje pro počítače s cílem touto zásadou. 
  - **Zakázané** – zabezpečení klíče jsou zakázané a uživatelé nemůžou používat k přihlášení do počítačů.   

  **Výchozí**: Není nakonfigurováno

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
