---
title: Integrace Windows Hello pro firmy s Microsoft Intune
titleSuffix: Microsoft Intune
description: Naučte se vytvářet zásady pro řízení použití Windows Hello pro firmy na spravovaných zařízeních.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 7ce6def40c6c0fff3a28f884c458220283979234
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465767"
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>Integrace Windows Hello pro firmy s Microsoft Intune  

Windows Hello pro firmy (dříve Microsoft Passport for Work) můžete integrovat s Microsoft Intune.

 Hello pro firmy je alternativní metoda pro přihlašování pomocí účtu služby Active Directory nebo Azure Active Directory, která může nahradit hesla, čipové karty a virtuální čipové karty. Umožňuje používat k přihlášení místo hesla *gesto uživatele*. A user gesture might be a PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.

Intune se s Hello pro firmy integruje dvěma způsoby:

- Vytvořením zásady Intune v části **Registrace zařízení**. Tato zásada cílí na celou organizaci (celého tenanta). Podporuje program Windows AutoPilot spouštěný při prvním zapnutí a použije se při registraci zařízení. 
- Vytvořením profilu ochrany identit v části **Konfigurace zařízení**. Tento profil cílí na přiřazené uživatele a zařízení a použije se při ohlášení. 

Pomocí tohoto článku můžete vytvořit výchozí zásadu pro službu Windows Hello pro firmy, která bude cílit na celou organizaci. Pokyny k vytváření profilů ochrany identit, které se použití u vybraných skupin uživatelů nebo zařízení, najdete v článku o [konfiguraci profilu ochrany identit](identity-protection-configure.md).  

<!--- - You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> V desktopových a mobilních verzích Windows 10 před Anniversary Update šlo nastavit dva různé kódy PIN, které se daly použít k ověření prostředků:
> - **PIN zařízení** se používal k odemknutí zařízení a připojení k prostředkům cloudu.
> - **Pracovní PIN** se používal pro přístup k prostředkům Azure AD na uživatelově osobním zařízení (BYOD).
> 
> Anniversary Update sloučil tyhle dva kódy do jediného PIN zařízení.
> Veškeré zásady konfigurace Intune, které mají nastaveno, že ovládají PIN zařízení, a také jakékoli nakonfigurované zásady Windows Hello pro firmy teď nastavují hodnotu tohoto nového kódu PIN.
> Pokud jste u obou typů zásad nastavili, že ovládají kód PIN, použijí se v zařízeních s desktopovými i mobilními verzemi Windows 10 zásady Windows Hello pro firmy.
> Abyste předešli konfliktům mezi zásadami a zajistili, že zásady kódu PIN se budou aplikovat správně, aktualizujte zásady Windows Hello pro firmy, tak aby odpovídaly nastavení zásad konfigurace. Potom požádejte uživatele, aby si svá zařízení synchronizovali v aplikaci Portál společnosti.



## <a name="create-a-windows-hello-for-business-policy"></a>Vytvoření zásad pro službu Windows Hello pro firmy

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431.

2. Go to **Devices** >  enrollment** > **Enroll devices** > **Windows enrollment** > **Windows Hello for Business**. The Windows Hello for Business pane opens.

3. Select from the following options for **Configure Windows Hello for Business**:

    - **Zakázáno**. Toto nastavení vyberte, pokud Windows Hello pro firmy nechcete používat. If disabled, users can't provision Windows Hello for Business except on Azure Active Directory joined mobile phones where provisioning may be required.
    - **Povoleno**. Toto nastavení vyberte, pokud chcete konfigurovat nastavení Windows Hello pro firmy.  When you select *Enabled*, additional settings for WIndows Hello become visible.
    - **Není nakonfigurováno**. Toto nastavení vyberte, pokud k řízení nastavení Windows Hello pro firmy nechcete používat Intune. Any existing Windows Hello for Business settings on Windows 10 devices isn't changed. Žádná ostatní nastavení v podokně nejsou dostupná.

4. Pokud jste v předchozím kroku vybrali **Povoleno**, nakonfigurujte požadovaná nastavení, která se použijí pro všechna zaregistrovaná zařízení s Windows 10 a Windows 10 Mobile. After  you configure these settings, select **Save**.

   - **Use a Trusted Platform Module (TPM)** :

     Čip TPM poskytuje další úroveň zabezpečení dat. Vyberte jednu z těchto hodnot:

     - **Požadované** (výchozí). Windows Hello pro firmy můžou zřídit jenom zařízení s přístupným čipem TPM.
     - **Preferované**. Zařízení se nejdřív pokusí použít čip TPM. If this option isn't available, they can use software encryption.

   - **Minimum PIN length** and **Maximum PIN length**:

     Konfiguruje zařízení, aby k zajištění bezpečného přihlášení vyžadovala minimální a maximální délky kódu PIN. Výchozí délka kódu PIN je 6 znaků, ale můžete vynutit minimální délku 4 znaky. Maximální délka kódu PIN je 127 znaků.

   - **Lowercase letters in PIN**, **Uppercase letters in PIN**, and **Special characters in PIN**.

     Silnější kódy PIN můžete vynutit tím, že se v nich bude vyžadovat použití velkých a malých písmen a speciálních znaků. For each, select from:

     - **Povolené**. Users can use the character type in their PIN, but it isn't mandatory.

     - **Požadované**. Uživatelé musí ve svém kódu PIN použít aspoň jeden z těchto typů znaků. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

     - **Není povolené** (výchozí). Uživatelé nesmí tyto typy znaků ve svém kódu PIN používat. (This is also the behavior if the setting isn't configured.)

       Mezi speciální znaky patří: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN expiration (days)** :

     Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí hodnota je 41 dnů.

   - **Remember PIN history**:

     Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. By default, the last 5 PINs can't be reused.

   - **Allow biometric authentication**:

     Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:

     - **Ano**. Windows Hello pro firmy umožňuje biometrické ověřování.
     - **Ne**. Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).

   - **Use enhanced anti-spoofing, when available**:

     Configures whether the anti-spoofing features of Windows Hello are used on devices that support it. For example, detecting a photograph of a face instead of a real face.

     When set to **Yes**, Windows requires all users to use anti-spoofing for facial features when that is supported.

   - **Allow phone sign-in**:

     Pokud je tato možnost nastavená na hodnotu **Ano**, uživatelé můžou použít vzdálenou službu Passport, která bude sloužit jako přenosné doprovodné zařízení pro ověřování stolního počítače. Stolní počítač musí být připojený ke službě Azure Active Directory a v doprovodném zařízení musí být nakonfigurovaný kód PIN služby Windows Hello pro firmy.

## <a name="windows-holographic-for-business-support"></a>Podpora Windows Holographic for Business

Windows Holographic for Business supports the following settings for Windows Hello for Business:

- Použít čip TPM (Trusted Platform Module)
- Minimální délka PIN kódu
- Maximální délka PIN kódu
- Malá písmena v PIN kódu
- Velká písmena v PIN kódu
- Speciální znaky v PIN kódu
- Vypršení platnosti PIN kódu (v dnech)
- Pamatovat si historii PIN kódů

## <a name="next-steps"></a>Další kroky

For more information about Windows Hello for Business, see [the guide](https://technet.microsoft.com/library/mt589441.aspx) in the Windows 10 documentation.
