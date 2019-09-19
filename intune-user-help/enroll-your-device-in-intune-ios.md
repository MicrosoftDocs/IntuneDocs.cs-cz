---
title: Nastavení přístupu zařízení s iOSem k prostředkům společnosti | Microsoft Docs
description: Popisuje, jak začít spravovat zařízení s iOSem pomocí Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f207f1f94d34e6aa1768bb5ae0f5179710839c71
ms.sourcegitcommit: 8934b1abec96e18cee15a77107d37551766f7666
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2019
ms.locfileid: "71099868"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Nastavení přístupu zařízení s iOSem k prostředkům společnosti  

Zaregistrujte si zařízení s iOSem pomocí aplikace Portál společnosti v Intune a získejte zabezpečený přístup k e-mailům, souborům a aplikacím vaší organizace.

Po registraci zařízení se bude *Spravovat*. Vaše organizace může k zařízení přiřadit zásady a aplikace prostřednictvím poskytovatele správy mobilních zařízení (MDM), jako je třeba Intune.  

> [!NOTE]
> Žádná data shromážděná naší službou neprodávají z jakéhokoli důvodu žádné třetí straně.  

Pokud chcete zachovat přístup k pracovním nebo školním informacím ze zařízení, budete muset nakonfigurovat zařízení tak, aby odpovídalo preferovanému nastavení vaší organizace. Tento článek popisuje, jak použít Portál společnosti k registraci zařízení a udržování požadavků na nastavení vaší organizace.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Pokud jste se pokusili přistoupit k podnikovému e-mailu v aplikaci Pošta a zobrazila se vám výzva ke správě vašeho zařízení, jste na správném místě. Podle pokynů uvedených níže získáte přístup ke svému e-mailu a dalším prostředkům společnosti na zařízení s iOSem.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Co čekat od aplikace Portál společnosti  

### <a name="security"></a>Zabezpečení  
Při počátečním nastavení vás aplikace požádá, abyste se ve vaší organizaci ověřili. Potom vás informuje o všech nastaveních, která musíte aktualizovat. Organizace si například často určují požadavky na minimální a maximální délku hesla, které musíte splnit.

### <a name="protection"></a>Protection  
Po registraci zařízení bude aplikace Portál společnosti i nadále kontrolovat, že je chráněno. Pokud si například nainstalujete aplikaci z nedůvěryhodného zdroje, upozorní vás a dokonce vám může i odvolat přístup k firemním datům. Tento druh zásad je v organizacích společný a často vyžaduje, abyste před tím, než budete moct znovu získat přístup, odinstalovali nedůvěryhodnou aplikaci.  

### <a name="setting-notifications"></a>Nastavení oznámení  
Pokud po registraci vaše organizace vynucuje nový požadavek na zabezpečení (například vícefaktorové ověřování), aplikace Portál společnosti vás o něm informuje. Budete tak mít možnost si nastavení upravit, abyste se zařízením mohli dále pracovat.  

Další informace o registraci najdete v tématu s informacemi o tom, [co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Registrace zařízení s iOS  

Pokud si chcete stáhnout a nainstalovat [aplikaci Portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) do svého zařízení, přejdete do obchodu App Store. Budete také muset udržovat připojení Wi-Fi a mít přístup k Safari během registrace. 

Pozastavení aplikace po dobu delší než několik minut může způsobit ukončení nebo ukončení instalace aplikace. Pokud k tomu dojde, otevřete aplikaci Portál společnosti a zkuste to znovu.  

1. Otevřete Portál společnosti a přihlaste se pomocí svého pracovního nebo školního účtu. 

    ![Ukázkový snímek obrazovky aplikace Portál společnosti, přihlášení](./media/ios-01-cp-enroll-1904.PNG)  

2. Po zobrazení výzvy k přijetí oznámení Portál společnosti klepněte na možnost **povolení.** Portál společnosti používá oznámení k upozornění, pokud například potřebujete aktualizovat nastavení zařízení. 

    ![Příklad obrazovky Portál společnosti domovské stránky s výzvou k zadání oznámení](./media/ios-02-cp-enroll-1904.PNG)  

3. Na obrazovce **nastavit přístup** vyberte **začít.**  

     ![Příklad obrazovky Portál společnosti a obrazovky "nastavit přístup".](./media/ios-03-cp-enroll-1904.PNG)  

4. Přečtěte si seznam informací o zařízení, které vaše organizace může a neuvidí. Pak klepněte na **pokračovat**.  

5. Přečtěte si pokyny na obrazovce **co dál?** Až budete připraveni stáhnout a nainstalovat profil pro správu, klepněte na **pokračovat**.  

 > [!IMPORTANT]
> Tyto další kroky a obrazovky se budou lišit v závislosti na verzi iOS. Postupujte podle kroků pro verzi iOS. 

6. Safari otevře web Portál společnosti na vašem zařízení. Po zobrazení výzvy ke stažení konfiguračního profilu klepněte na možnost **Povolení**. Pokud se nacházíte na zařízení se systémem:  
    * iOS 12,2 a novější: Po dokončení stahování klepněte na **Hotovo.** Pokračujte krokem 7 v tomto článku.
    * iOS 12,1 a starší: Budete automaticky přesměrováni do aplikace nastavení. Přejděte na krok 8 v tomto článku.  
 
    Pokud omylem klepnete na **Ignorovat**, aktualizujte stránku. Zobrazí se výzva k otevření aplikace Portál společnosti. Z aplikace můžete znovu klepnout na **Stáhnout**.

  > [!NOTE]
  > Je nutné nainstalovat profil pro správu, jak je popsáno v následujících krocích během 8 minut od stažení. Pokud to neuděláte, profil se odebere a bude nutné restartovat registraci.  

7. jenom iOS 12,2 a novější: Po zobrazení výzvy k otevření Portál společnosti klepněte na **otevřít**. Na obrazovce **Instalace profilu správy** se zobrazí seznam kroků pro instalaci profilu.

    ![Příklad obrazovky Portál společnosti, instalace profilu správy](./media/ios-07-cp-enroll-1904.PNG)  

8. Otevřete aplikaci nastavení a klepněte na **Stáhnout profil**.  

    Pokud se **profil stáhl** jako možnost, přejdete na **Obecné** > **profily**. Pokud profil stále nevidíte, možná ho budete muset stáhnout znovu.  

    ![Ukázkový snímek obrazovky aplikace nastavení, nastavení staženého profilu](./media/ios-1904-settings-badge.PNG)  

9. Klepněte na **Instalovat**.  
    
10. Zadejte heslo zařízení. Pak klepněte na **instalovat**.    

    ![Příklad snímku obrazovky aplikace nastavení, instalace obrazovky Profile se kurzorem na tlačítku * * instalovat * *.](./media/ios-10-cp-enroll-1904.PNG)  


11. Další obrazovka je standardní systémové upozornění pro správu zařízení. Pokud chcete pokračovat v instalaci, klepněte na **instalovat**. Pokud se zobrazí výzva k důvěřování vzdálené správě, klepněte na **důvěřovat**.  

    ![Příklad obrazovky nastavení aplikace, standardní systémová Varovná obrazovka pro kořenový certifikát a správu mobilních zařízení.](./media/ios-11-cp-enroll-1904.PNG)  

12. Po dokončení instalace klepněte na **Hotovo**. Pokud chcete ověřit, že se profil nainstaloval, klikněte na **profily & nastavení správy zařízení** . Měl by se zobrazit profil uvedený v části **Správa mobilních zařízení**.   

    ![Příklad obrazovky nastavení aplikace, profily & nastavení správy zařízení, zobrazení profilu správy.](./media/ios-12-cp-enroll-1904.PNG)  

13. Vraťte se do aplikace Portál společnosti. Portál společnosti se začne synchronizovat a nastavit vaše zařízení. Portál společnosti vás může zobrazit výzva k aktualizaci dalších nastavení zařízení. Pokud k tomu klepne, klepněte na **pokračovat**.  

    ![Příklad obrazovky Portál společnosti a obrazovky "nastavit přístup" se žlutým trojúhelníkem vedle nastavení požadavku.](./media/ios-13-cp-enroll-1904.PNG)  

14. Poznáte, že je instalace dokončena, když všechny položky v seznamu zobrazí zelený kroužek. Klepněte na **Hotovo**.   
    
    ![Ukázkový snímek obrazovky Portál společnosti, "všechno je nastavené!" obrazovky se zobrazením všech zelených kroužků.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Pokud vaše organizace sleduje omezení hlasu a dat nebo poskytuje zařízení vlastněná společností, může být potřeba provést několik dalších kroků. Pokud se zobrazí výzva k instalaci aplikace **Datalert** , přečtěte si téma [registrace zařízení ve správě telekomunikačních výdajů](enroll-your-device-with-telecom-expense-management-ios.md). Pokud je vaše organizace součástí Program registrace zařízení společnosti Apple, přečtěte si, [jak zaregistrovat zařízení vlastněné společností](enroll-your-device-dep-ios.md).  

## <a name="it-administrator-support"></a>Podpora správce IT  
Pokud jste správcem IT a máte potíže s registrací zařízení, přečtěte si téma řešení potíží s registrací [zařízení s iOS v Microsoft Intune](https://support.microsoft.com/en-us/help/4039809). V tomto článku jsou uvedené běžné chyby, jejich příčiny a kroky, jak je vyřešit.  

## <a name="next-steps"></a>Další kroky  
Najděte aplikace, které vám pomůžou při práci nebo ve škole. Seznamte se s tím, [jak jsou aplikace zpřístupněny](use-managed-apps-on-your-device-ios.md) prostřednictvím portál společnosti.  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
