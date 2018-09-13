---
title: Konfigurace nastavení ochrany identit v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte profil zařízení, se kterým můžete v Intune nastavit funkci Windows Hello pro firmy na zařízeních s Windows 10
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7012479023ece83ef475431c5cefe150ab2ef342
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43317991"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Konfigurace nastavení ochrany identit v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profily ochrany identit řídí způsob zřizování a konfigurace funkce Windows Hello pro firmy na spravovaných zařízeních s Windows 10. Po vytvoření tohoto profilu můžete konfigurovat:  
* Dostupnost funkce Windows Hello pro firmy pro zařízení a uživatele
* Požadavky na PIN kód zařízení
* Gesta, která uživatelé mohou nebo nemohou používat k přihlašování k zařízením  

 Profil ochrany identit můžete přiřadit vybraným skupinám uživatelů nebo zařízení, případně všem uživatelům a zařízením. Skupiny obdrží profil při ohlášení se v Intune.    

Pomocí pokynů v tomto článku vytvořte profil ochrany identit. Potom ho [přiřaďte](device-profile-assign.md) skupinám uživatelů a zařízení.

Tato funkce je dostupná pro zařízení s následujícími systémy:  
- Windows 10 a novější
- Windows Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Vytvoření profilu zařízení s nastavením ochrany identit

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **Název** a **Popis** profilu ochrany identit.
5. V rozevíracím seznamu **Platforma** vyberte **Windows 10 a novější**. Windows Hello pro firmy se podporuje jen na zařízeních s Windows 10 a novějšími.
6. V rozevíracím seznamu **Typ profilu** zvolte **Identity Protection**.
7. V podokně Windows Hello pro firmy zvolte jednu z těchto možností konfigurace:
    * Zakázáno Toto nastavení vyberte, pokud Windows Hello pro firmy nechcete používat. Všechna ostatní nastavení na obrazovce jsou nedostupná.
    * Povoleno. Toto nastavení vyberte, pokud chcete konfigurovat nastavení Windows Hello pro firmy.  

8. Pokud jste v předchozím kroku vybrali **Povoleno**, nakonfigurujte požadovaná nastavení, která se použijí pro cílená zaregistrovaná zařízení a uživatele s Windows 10 a Windows 10 Mobile.

> [!NOTE]
> Pokud profily ochrany identit přiřazujete jen uživatelům, kontext zařízení nastaví výchozí hodnotu **Nenakonfigurováno**.  

   - **Minimální délka PIN kódu**/**Maximální délka PIN kódu**. Konfiguruje zařízení, aby k zajištění bezpečného přihlášení vyžadovala minimální a maximální délky kódu PIN. Výchozí délka kódu PIN je 6 znaků, ale můžete vynutit minimální délku 4 znaky. Maximální délka kódu PIN je 127 znaků.  

   - **Malá písmena v PIN kódu**/**Velká písmena v PIN kódu**/**Speciální znaky v PIN kódu**. Silnější kódy PIN můžete vynutit tím, že se v nich bude vyžadovat použití velkých a malých písmen a speciálních znaků. Vybírejte z těchto možností:

     - **Povolené**. Uživatelé můžou tyto typy znaků ve svých kódech PIN použít, ale není to povinné.

     - **Požadované**. Uživatelé musí ve svém kódu PIN použít aspoň jeden z těchto typů znaků. Běžnou praxí třeba je vyžadovat použití nejméně jednoho velkého písmena, jednoho malého písmena a jednoho speciálního znaku.

     - **Není povolené** (výchozí). Uživatelé nesmí tyto typy znaků ve svém kódu PIN používat. (Toto chování se také používá, když není nastavení nakonfigurované.)<br>Mezi speciální znaky patří: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Doba platnosti kódu PIN (dny)**. Je dobrým zvykem zadat pro kód PIN dobu platnosti, po jejímž uplynutí ho uživatel musí změnit. Výchozí hodnota je 41 dnů.

   - **Pamatovat si historii kódů PIN**. Pomocí tohoto nastavení můžete zabránit opakovanému použití předchozích kódů PIN. Ve výchozím nastavení se nesmí znovu použít posledních 5 kódů PIN.  
   - **Povolit obnovení PIN kódu**: Umožňuje uživateli změnit PIN kód pomocí služby obnovení ve Windows Hello pro firmy. 
       - **Povolit**. Cloudová služba zašifruje tajný kód pro obnovení PIN kódu, který se uloží v zařízení. Uživatel si může PIN kód v případě potřeby změnit.  
       - **Nenakonfigurováno** (výchozí). Tajný kód pro obnovení PIN kódu se nevytvoří ani neuloží. Pokud uživatel PIN kód zapomene, může nový získat jedině odstraněním původního kódu a vytvořením dalšího. Uživatel se také musí znovu zaregistrovat ve všech službách, k nimž měl pomocí původního PIN kódu přístup.  
   
   - **Použít čip TPM (Trusted Platform Module)**. Čip TPM poskytuje další úroveň zabezpečení dat. Vyberte jednu z těchto hodnot:  
     - **Povolit**. Windows Hello pro firmy můžou zřídit jenom zařízení s přístupným čipem TPM.
     - **Není nakonfigurováno**. Windows Hello pro firmy mohou zřídit všechna zařízení, a to i bez využitelného čipu TPM. Zařízení nejdříve zkusí TPM, a když nebude k dispozici, mohou použít softwarové šifrování.  

   - **Povolit biometrické ověřování**. Jako alternativu ke kódu PIN pro Windows Hello pro firmy umožňuje biometrické ověřování, například rozpoznávání obličeje nebo otisků prstů. Uživatelé ale stejně musí nakonfigurovat pracovní kód PIN pro případ, že se biometrické ověření nepovede. Vybírejte z těchto možností:

     - **Povolit**. Windows Hello pro firmy umožňuje biometrické ověřování.
     - **Nenakonfigurováno** (výchozí). Windows Hello pro firmy neumožňuje biometrické ověřování (pro všechny typy účtů).

   - **Použít vylepšenou ochranu proti falšování identity, pokud je dostupná**. Konfiguruje, jestli se v zařízení použijí funkce ochrany proti falšování identity Windows Hello, pokud je zařízení podporuje (třeba rozpoznání fotografie tváře místo skutečné tváře).
       - **Povolit**. Windows vyžaduje, aby všichni uživatelé používali pro funkce rozpoznávání obličeje ochranu proti falšování, pokud je podporovaná.  
       - **Nenakonfigurováno** (výchozí). Windows respektuje konfiguraci proti falšování nastavenou na zařízení.

   - **Certifikát pro místní prostředky** 
       - **Povolit**. Umožňuje funkci Windows Hello pro firmy používat k ověřování místních prostředků certifikáty.
       - **Nenakonfigurováno** (výchozí). Brání funkci Windows Hello pro firmy používat k ověřování místních prostředků certifikáty.  
9. Kliknutím na **OK** uložte profil.  

Profil se vytvoří a zobrazí v seznamu **Konfigurace zařízení – Profily**. Pokud chcete pokračovat a přiřadit tento profil ke skupinám, přečtěte si téma [Přiřazení profilů uživatelů a zařízení v Microsoft Intune](device-profile-assign.md).  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
