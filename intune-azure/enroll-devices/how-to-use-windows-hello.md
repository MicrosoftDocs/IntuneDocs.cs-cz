---
title: "Použití Windows Hello pro firmy"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se vytvářet zásady pro řízení použití Windows Hello pro firmy na spravovaných zařízeních."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 541be8b8-8668-41be-afce-3f3e08c12191
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 1844cf87ae51c7d0832e3ba6315efde734ff56cc
ms.lasthandoff: 02/18/2017


---

# <a name="use-windows-hello-for-business"></a>Použití Windows Hello pro firmy


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune umožňuje integraci se službou Windows Hello pro firmy (dříve Microsoft Passport for Work). Je to alternativní metoda pro přihlašování pomocí účtu služby Active Directory nebo Azure Active Directory, která může nahradit hesla, čipové karty a virtuální čipové karty.

Hello pro firmy umožňuje používat k přihlášení *gesto uživatele* místo hesla. Gesto uživatele může být jednoduchý PIN kód, biometrické ověřování jako třeba Windows Hello nebo externí zařízení, jako je třeba čtečka otisků prstů.

Intune se s Hello pro firmy integruje dvěma způsoby:

-   Pomocí zásady Intune můžete řídit, která gesta uživatel může nebo nemůže používat k přihlášení.

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> V desktopových a mobilních verzích Windows 10 před Anniversary Update šlo nastavit dva různé kódy PIN, které se daly použít k ověření prostředků:
- **PIN zařízení** se používal k odemknutí zařízení a připojení k prostředkům cloudu.
- **Pracovní PIN** se používal pro přístup k prostředkům Azure AD na uživatelově osobním zařízení (BYOD).

>Anniversary Update sloučil tyhle dva kódy do jediného PIN zařízení.
Veškeré zásady konfigurace Intune, které mají nastaveno, že ovládají PIN zařízení, a také jakékoli nakonfigurované zásady Windows Hello pro firmy teď nastavují hodnotu tohoto nového kódu PIN.
Pokud jste o obou typů zásad nastavili, že ovládají kód PIN, použijí se na desktopových i mobilních zařízeních s Windows 10 zásady Windows Hello pro firmy.
Abyste předešli konfliktům mezi zásadami a zajistili, že zásady kódu PIN se budou aplikovat správně, aktualizujte zásady Windows Hello pro firmy, tak aby odpovídaly nastavení zásad konfigurace. Potom požádejte uživatele, aby si svá zařízení synchronizovali v aplikaci Portál společnosti.



## <a name="create-a-windows-hello-for-business-policy"></a>Vytvoření zásad pro službu Windows Hello pro firmy

1.  Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2.  V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Spravovat** > **Windows Hello pro firmy**.

3.  V okně, které se otevře, zvolte **výchozí** nastavení.

4.  V okně **Všichni uživatelé** klikněte na **Vlastnosti** a pak zadejte **název** a volitelně **popis** pro nastavení Windows Hello pro firmy.

5. V okně **Všichni uživatelé** klikněte na **Nastavení** a pak pro možnost **Konfigurovat Windows Hello pro firmy** zvolte jednu z těchto hodnot:

    - **Zakázáno**. Toto nastavení vyberte, pokud Windows Hello pro firmy nechcete používat. Všechna ostatní nastavení na obrazovce jsou nedostupná.
    - **Povoleno**. Toto nastavení vyberte, pokud chcete konfigurovat nastavení Windows Hello pro firmy.
    - **Není nakonfigurováno**. Toto nastavení vyberte, pokud k řízení nastavení Windows Hello pro firmy nechcete používat Intune. Veškerá stávající nastavení Windows Hello pro firmy v zařízeních s Windows 10 se nezmění. Všechna ostatní nastavení v okně jsou nedostupná.

6.  Pokud jste v předchozím kroku vybrali **Povoleno**, nakonfigurujte požadovaná nastavení, která se použijí pro všechna zaregistrovaná zařízení s Windows 10 a Windows 10 Mobile.

 - **Použít čip TPM (Trusted Platform Module)**. Čip TPM poskytuje další úroveň zabezpečení dat.<br>Vyberte jednu z těchto hodnot:

     - **Požadované** (výchozí). Windows Hello pro firmy můžou zřídit jenom zařízení s přístupným čipem TPM.
     - **Preferované**. Zařízení se nejdřív pokusí použít čip TPM. Pokud není dostupný, můžou použít softwarové šifrování.

 - **Vyžadovat minimální délku PIN kódu**/**Vyžadovat maximální délku PIN kódu**. Konfiguruje zařízení, aby k zajištění bezpečného přihlášení vyžadovala minimální a maximální délky kódu PIN. Výchozí délka kódu PIN je 6 znaků, ale můžete vynutit minimální délku 4 znaky. Maximální délka kódu PIN je 127 znaků.

 - **Vyžadovat v PIN kódu malá písmena**/**Vyžadovat v PIN kódu velká písmena**/**Vyžadovat v PIN kódu speciální znaky**. Silnější kódy PIN můžete vynutit tím, že se v nich bude vyžadovat použití velkých a malých písmen a speciálních znaků. Vybírejte z těchto možností:

     - **Povolené**. Uživatelé můžou tyto typy znaků ve svých kódech PIN použít, ale není to povinné.
    
     - **Požadované**. Uživatelé musí ve svém kódu PIN použít aspoň jeden z těchto typů znaků. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

     - **Není povolené** (výchozí). Uživatelé nesmí tyto typy znaků ve svém kódu PIN používat. (Toto chování se taky použije, když nastavení není nakonfigurované.)<br>Mezi speciální znaky patří: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

 - **Doba platnosti kódu PIN (dny)**. Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí hodnota je 41 dnů.

 - **Pamatovat si historii kódů PIN**. Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. Ve výchozím nastavení se nesmí znovu použít posledních 5 kódů PIN.

 - **Povolit biometrické ověřování**. Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:

     - **Ano**. Windows Hello pro firmy umožňuje biometrické ověřování.
     - **Ne**. Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).

 - **Použít vylepšenou ochranu proti falšování identity, pokud je dostupná**. Konfiguruje, jestli se v zařízení použijí funkce ochrany proti falšování identity Windows Hello, pokud je zařízení podporuje (třeba rozpoznání fotografie tváře místo skutečné tváře).<br>Pokud je nastavená hodnota **Ano**, Windows vyžaduje, aby všichni uživatelé používali pro funkce rozpoznávání obličeje ochranu proti falšování, pokud je podporovaná.

 - **Použít přihlášení telefonem**. Pokud je tato možnost nastavená na hodnotu **Ano**, uživatelé můžou použít vzdálenou službu Passport, která bude sloužit jako přenosné doprovodné zařízení pro ověřování stolního počítače. Stolní počítač musí být připojený ke službě Azure Active Directory a v doprovodném zařízení musí být nakonfigurovaný kód PIN služby Windows Hello pro firmy.


## <a name="further-information"></a>Další informace
Další informace o službě Microsoft Passport najdete v [příručce](https://technet.microsoft.com/library/mt589441.aspx) v dokumentaci k Windows 10.

