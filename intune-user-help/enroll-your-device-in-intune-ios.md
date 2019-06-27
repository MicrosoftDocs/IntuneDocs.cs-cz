---
title: Nastavení přístupu zařízení s iOSem k prostředkům společnosti | Microsoft Docs
description: Popisuje, jak začít spravovat zařízení s iOSem pomocí Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
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
ms.openlocfilehash: 4c8dfdea552d035c036828bfd2e6695cc5e4cb7b
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402766"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Nastavení přístupu zařízení s iOSem k prostředkům společnosti  

Zaregistrujte si zařízení s iOSem pomocí aplikace Portál společnosti v Intune a získejte zabezpečený přístup k e-mailům, souborům a aplikacím vaší organizace.

Po registraci vašeho zařízení, stane se *spravované*. Vaše organizace můžete přiřadit zásady a aplikace na zařízení prostřednictvím poskytovatele management (MDM) mobilních zařízení, jako je například Intune.  

Pokud chcete zachovat přístup k práci nebo škole informace z vašeho zařízení, budete muset nakonfigurovat zařízení tak, aby odpovídaly nastavení vaší organizace. Tento článek popisuje, jak používat portál společnosti k registraci můžete zařízení a zachovat nastavení požadavky vaší organizace.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Pokud jste se pokusili přistoupit k podnikovému e-mailu v aplikaci Pošta a zobrazila se vám výzva ke správě vašeho zařízení, jste na správném místě. Podle pokynů uvedených níže získáte přístup ke svému e-mailu a dalším prostředkům společnosti na zařízení s iOSem.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Co čekat od aplikace Portál společnosti  

### <a name="security"></a>Zabezpečení  
Při počátečním nastavení vás aplikace požádá, abyste se ve vaší organizaci ověřili. Potom vás informuje o všech nastaveních, která musíte aktualizovat. Organizace si například často určují požadavky na minimální a maximální délku hesla, které musíte splnit.

### <a name="protection"></a>Protection  
Po registraci zařízení bude aplikace Portál společnosti i nadále kontrolovat, že je chráněno. Pokud si například nainstalujete aplikaci z nedůvěryhodného zdroje, upozorní vás a dokonce vám může i odvolat přístup k firemním datům. Tento typ zásad je běžné v organizacích a často je potřeba odinstalovat nedůvěryhodné aplikace předtím, než jste znovu získali přístup.  

### <a name="setting-notifications"></a>Nastavení oznámení  
Pokud po registraci vaše organizace vynucuje nový požadavek na zabezpečení (například vícefaktorové ověřování), aplikace Portál společnosti vás o něm informuje. Budete tak mít možnost si nastavení upravit, abyste se zařízením mohli dále pracovat.  

Další informace o registraci najdete v tématu s informacemi o tom, [co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Registrace zařízení s Iosem  

Přejděte do obchodu s aplikacemi stáhnout a nainstalovat [aplikace portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) na vašem zařízení. Také budete muset udržovat připojení Wi-Fi a mají přístup do prohlížeče Safari během registrace. 

Přerušení na více než několik minut, během registrace může způsobit, že aplikace k zavření nebo ukončení instalace. Pokud k tomu dojde, otevřete aplikaci portál společnosti a zkuste to znovu.  

1. Otevřete portál společnosti a přihlaste se pomocí svého pracovního nebo školního účtu. 

    ![Příklad snímek obrazovky aplikace portál společnosti přihlásit.](./media/ios-01-cp-enroll-1904.PNG)  

2. Po zobrazení výzvy k přijímání oznámení na portál společnosti, klepněte na **povolit.** Portál společnosti používá oznámení vás upozorní, pokud je například potřeba aktualizovat nastavení zařízení. 

    ![Příklad snímek domovské stránky portálu společnosti, řádku "Oznámení".](./media/ios-02-cp-enroll-1904.PNG)  

3. Na **nastavení přístupu** obrazovky, vyberte **začít.**  

     ![Příklad – snímek obrazovky portálu společnosti, obrazovky "Nastavení přístupu".](./media/ios-03-cp-enroll-1904.PNG)  

4. Přečtěte si seznam informací o zařízení vaší organizaci uvidí a neuvidí. Potom klepněte na **pokračovat**.  

5. Přečtěte si pokyny na **co se chystá?** obrazovky. Až budete připraveni stáhnout a nainstalovat profil správy, klepněte na **pokračovat**.  

 > [!IMPORTANT]
> Tyto další kroky a obrazovky se bude lišit v závislosti na vaší verzi iOS. Postupujte podle kroků pro vaši verzi iOS. 

6. Safari se otevře web portál společnosti na vašem zařízení. Po zobrazení výzvy ke stažení konfiguračního profilu, klepněte na **povolit**. Pokud jste na zařízení se systémem:  
    * iOS 12.2 a novější: Po dokončení stahování klepněte **Hotovo.** Pokračujte krokem 7 v tomto článku.
    * iOS 12,1 a starší: Budete automaticky přesměrováni do nastavení aplikace. Přejděte ke kroku 8 v tomto článku.  
 
    Pokud omylem klepnete **Ignorovat**, aktualizujte stránku. Budete vyzváni, otevřete aplikaci portál společnosti. Z aplikace, můžete klepnout na **znovu stáhnout**.

  > [!NOTE]
  > Musíte si nainstalovat profil správy, jak je popsáno v dalších krocích do 8 minut od stáhnout. Pokud to neuděláte, profil, který se odeberou a bude nutné restartovat registrace.  

7. iOS 12.2 a vyšší: Po zobrazení výzvy k otevření portálu společnosti, klepněte na **otevřete**. **Instalaci profilu správy** obrazovky jsou uvedené kroky k instalaci profilu.

    ![Příklad – snímek obrazovky portálu společnosti, obrazovce nainstalovat profil správy.](./media/ios-07-cp-enroll-1904.PNG)  

8. Přejít do nastavení aplikace a klepněte na **profil stažen**.  

    Pokud **profil stažen** nebude nezobrazí jako možnost, přejděte na **Obecné** > **profily**. Pokud stále nevidíte profilu, budete muset znovu stáhnout.  

    ![Ukázkovém snímku obrazovky v aplikaci nastavení, profil stažen nastavení.](./media/ios-1904-settings-badge.PNG)  

9. Klepněte na **Instalovat**.  
    
10. Zadejte heslo zařízení. Potom klepněte na **nainstalovat**.    

    ![V aplikaci nastavení, instalaci profilu obrazovky, s kurzorem na snímku obrazovky s příkladem ** nainstalovat ** tlačítko.](./media/ios-10-cp-enroll-1904.PNG)  


11. Na další obrazovce je standardní systém upozornění pro správu zařízení. Chcete-li pokračovat v instalaci, klepněte na **nainstalovat**. Pokud se zobrazí výzva k důvěřování vzdálené správě, klepněte na **důvěryhodnosti**.  

    ![Příklad snímek obrazovky nastavení aplikace, obrazovka upozornění standardního systému pro správu mobilních zařízení a kořenový certifikát.](./media/ios-11-cp-enroll-1904.PNG)  

12. Po dokončení instalace, klepněte na **provádí**. Pokud chcete ověřit, že profil byl nainstalován, přejděte na **Správa zařízení a profily** nastavení. Profil uvedený v seznamu byste měli vidět **Správa mobilních zařízení**.   

    ![Příklad snímek obrazovky nastavení aplikace, Správa profilů a zařízení nastavení zobrazující profil pro správu.](./media/ios-12-cp-enroll-1904.PNG)  

13. Vraťte se do aplikace portál společnosti. Portál společnosti se začne synchronizovat, a nastavit vaše zařízení. Portál společnosti vyzve aktualizovat další nastavení zařízení. Pokud ano, klepněte na **pokračovat**.  

    ![Příklad – snímek obrazovky portálu společnosti, "Nastavení přístupu" obrazovka s žlutém trojúhelníku vedle nastavení požadavek.](./media/ios-13-cp-enroll-1904.PNG)  

14. Budete vědět, že tento instalační program je dokončen, pokud všechny položky v seznamu zobrazit zeleném kroužku. Klepněte na **Hotovo**.   
    
    ![Ukázkovém snímku obrazovky z portálu společnosti, "všechno je nastavené!" obrazovka zobrazující všechny zelené kruzích.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Pokud vaše organizace monitoruje omezení hlasu a dat nebo vám poskytne zařízení vlastněná společností, můžete mít několik kroků k dokončení. Pokud budete vyzváni k instalaci **Datalert** aplikace, najdete v článku [registraci zařízení do služby telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). Pokud vaše organizace je součástí programu registrace zařízení společnosti Apple, přečtěte si [způsobu registrace zařízení ve vlastnictví společnosti](enroll-your-device-dep-ios.md).  

## <a name="it-administrator-support"></a>Podpora pro správce IT  
Pokud jste správcem IT a spustit potíží při registraci zařízení, najdete v článku [řešení potíží s problémy registrace zařízení s Iosem v Microsoft Intune](https://support.microsoft.com/en-us/help/4039809). Tento článek uvádí běžné chyby, jejich příčiny a kroky k jejich řešení.  

## <a name="next-steps"></a>Další postup  
Najdete aplikace, které vám pomohou při práci nebo školu. Přečtěte si [jak aplikací jsou k dispozici](use-managed-apps-on-your-device-ios.md) vám prostřednictvím portálu společnosti.  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
