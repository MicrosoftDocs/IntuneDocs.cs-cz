---
title: Nastavení Windows Hello pro firmy na zařízeních
description: Přečtěte si, jak Intune umožňuje integraci se službou Windows Hello pro firmy. Je to alternativní metoda pro přihlašování pomocí účtu služby Active Directory nebo Azure Active Directory, která může nahradit hesla, čipové karty a virtuální čipové karty.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 09/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b841bcf97ecb213f75575508362de0234bc8a2b9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="control-windows-hello-for-business-settings-on-devices-with-microsoft-intune"></a>Řízení nastavení Windows Hello pro firmy na zařízeních pomocí Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune umožňuje integraci se službou Windows Hello pro firmy (dříve Microsoft Passport for Work). Je to alternativní metoda pro přihlašování pomocí účtu služby Active Directory nebo Azure Active Directory, která může nahradit hesla, čipové karty a virtuální čipové karty.

Hello pro firmy umožňuje používat k přihlášení *gesto uživatele* místo hesla. Gesto uživatele může být jednoduchý PIN kód, biometrické ověřování jako třeba Windows Hello nebo externí zařízení, jako je třeba čtečka otisků prstů.

Intune se s Hello pro firmy integruje dvěma způsoby:

-   Pomocí zásady Intune můžete řídit, která gesta uživatel může nebo nemůže používat k přihlášení.

-   Ověřovací certifikáty můžete uložit ve zprostředkovateli úložiště klíčů (KSP) služby Windows Hello pro firmy. Další informace najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).

> [!IMPORTANT]
> V desktopových a mobilních verzích Windows 10 před Anniversary Update šlo nastavit dva různé kódy PIN, které se daly použít k ověření prostředků:
> - **PIN zařízení** se používal k odemknutí zařízení a připojení k prostředkům cloudu.
> - **Pracovní PIN** se používal pro přístup k prostředkům Azure AD na uživatelově osobním zařízení (BYOD).
> 
> Anniversary Update sloučil tyhle dva kódy do jediného PIN zařízení.
> Veškeré zásady konfigurace Intune, které mají nastaveno, že ovládají PIN zařízení, a také jakékoli nakonfigurované zásady Windows Hello pro firmy teď nastavují hodnotu tohoto nového kódu PIN.
> Pokud jste o obou typů zásad nastavili, že ovládají kód PIN, použijí se na desktopových i mobilních zařízeních s Windows 10 zásady Windows Hello pro firmy.
> Abyste předešli konfliktům mezi zásadami a zajistili, že zásady kódu PIN se budou aplikovat správně, aktualizujte zásady Windows Hello pro firmy, tak aby odpovídaly nastavení zásad konfigurace. Potom požádejte uživatele, aby si svá zařízení synchronizovali v aplikaci Portál společnosti.



## <a name="create-a-windows-hello-for-business-policy"></a>Vytvoření zásad pro službu Windows Hello pro firmy

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) Zvolte **Správce** &gt; **Správa mobilních zařízení** &gt; **Windows** &gt; **Windows Hello pro firmy**. Otevře se stránka Windows Hello pro firmy.

    ![Stránka Windows Hello pro firmy](../media/passport.png)

2.  Zvolte jedno z těchto nastavení:
    - **Zakázat Windows Hello pro firmy na registrovaných zařízeních**. Toto nastavení vyberte, pokud Windows Hello pro firmy nechcete používat. Všechna ostatní nastavení na obrazovce jsou nedostupná.
    - **Povolit Windows Hello pro firmy na registrovaných zařízeních**. Toto nastavení vyberte, pokud chcete konfigurovat nastavení Windows Hello pro firmy.
    - **Není nakonfigurováno**. Toto nastavení vyberte, pokud k řízení nastavení Windows Hello pro firmy nechcete používat Intune. Veškerá stávající nastavení Windows Hello pro firmy v zařízeních s Windows 10 se nezmění. Všechna ostatní nastavení na obrazovce jsou nedostupná.
3.  Pokud jste vybrali **Povolit Windows Hello pro firmy na registrovaných zařízeních**, nakonfigurujte požadovaná nastavení, která se použijí pro všechna zaregistrovaná zařízení s Windows 10 a Windows 10 Mobile.
4.  Po dokončení zvolte **Uložit**.


## <a name="settings-for-the-windows-hello-for-business-policy"></a>Nastavení zásad pro službu Windows Hello pro firmy

- **Použít čip TPM (Trusted Platform Module)**. Čip TPM poskytuje další úroveň zabezpečení dat.<br>Vyberte jednu z těchto hodnot:
    - **Požadované** (výchozí). Windows Hello pro firmy můžou zřídit jenom zařízení s přístupným čipem TPM.
    - **Preferované**. Zařízení se nejdřív pokusí použít čip TPM. Pokud není dostupný, můžou použít softwarové šifrování.
- **Vyžadovat minimální délku PIN kódu**/**Vyžadovat maximální délku PIN kódu**. Konfiguruje zařízení, aby k zajištění bezpečného přihlášení vyžadovala minimální a maximální délky kódu PIN. Výchozí délka kódu PIN je 6 znaků, ale můžete vynutit minimální délku 4 znaky. Maximální délka kódu PIN je 127 znaků.
- **Vyžadovat v PIN kódu malá písmena**/**Vyžadovat v PIN kódu velká písmena**/**Vyžadovat v PIN kódu speciální znaky**. Silnější kódy PIN můžete vynutit tím, že se v nich bude vyžadovat použití velkých a malých písmen a speciálních znaků. Vybírejte z těchto možností:
    - **Povolené**. Uživatelé můžou tyto typy znaků ve svých kódech PIN použít, ale není to povinné.
    - **Požadované**. Uživatelé musí ve svém kódu PIN použít aspoň jeden z těchto typů znaků. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.
    - **Není povolené** (výchozí). Uživatelé nesmí tyto typy znaků ve svém kódu PIN používat. (Toto chování se taky použije, když nastavení není nakonfigurované.)<br>Mezi speciální znaky patří: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Doba platnosti kódu PIN (dny)**. Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí hodnota je 41 dnů.
- **Pamatovat si historii kódů PIN**. Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. Ve výchozím nastavení se nesmí znovu použít posledních 5 kódů PIN.
- **Povolit biometrické ověřování**. Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:
    - **Ano**. Windows Hello pro firmy umožňuje biometrické ověřování.
    - **Ne**. Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).
- **Použít vylepšenou ochranu proti falšování identity, pokud je dostupná**. Konfiguruje, jestli se v zařízení použijí funkce ochrany proti falšování identity Windows Hello, pokud je zařízení podporuje (třeba rozpoznání fotografie tváře místo skutečné tváře).<br>Pokud je nastavená hodnota **Ano**, Windows vyžaduje, aby všichni uživatelé používali pro funkce rozpoznávání obličeje ochranu proti falšování, pokud je podporovaná.
- **Použít přihlášení telefonem**. Pokud je tato možnost nastavená na hodnotu **Ano**, uživatelé můžou použít vzdálenou službu Passport, která bude sloužit jako přenosné doprovodné zařízení pro ověřování stolního počítače. Stolní počítač musí být připojený ke službě Azure Active Directory a v doprovodném zařízení musí být nakonfigurovaný kód PIN služby Windows Hello pro firmy.

## <a name="further-information"></a>Další informace
Další informace o službě Microsoft Passport najdete v [příručce](https://technet.microsoft.com/library/mt589441.aspx) v dokumentaci k Windows 10.
