---
title: Nastavení přístupu zařízení s iOSem k prostředkům společnosti | Microsoft Docs
description: Popisuje, jak začít spravovat zařízení s iOSem pomocí Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490638"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Nastavení přístupu zařízení s iOSem k prostředkům společnosti  

Zaregistrujte si zařízení s iOSem pomocí aplikace Portál společnosti v Intune a získejte zabezpečený přístup k e-mailům, souborům a aplikacím vaší organizace.

Předtím, než se dá dostat specifická vlastní data z podnikových a osobních zařízení, je nutné nechte si spravovat zařízení. Poté, co se stane zařízení spravovaným, vaše organizace na zařízení prostřednictvím poskytovatele management (MDM) mobilních zařízení, jako je například Intune přiřaďte zásady a aplikace. 

Pokud chcete na zařízení udržovat přístup k pracovním nebo školním datům, je nutné nakonfigurovat ho tak, aby odpovídalo upřednostňovaným nastavením vaší organizace. Tento článek popisuje, jak používat portál společnosti k registraci můžete zařízení a zachovat nastavení požadavky vaší organizace. 

> [!NOTE]
> Pokud jste se pokusili přistoupit k podnikovému e-mailu v aplikaci Pošta a zobrazila se vám výzva ke správě vašeho zařízení, jste na správném místě. Podle pokynů uvedených níže získáte přístup ke svému e-mailu a dalším prostředkům společnosti na zařízení s iOSem.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Co čekat od aplikace Portál společnosti  

### <a name="security"></a>Zabezpečení  
Při počátečním nastavení vás aplikace požádá, abyste se ve vaší organizaci ověřili. Potom vás informuje o všech nastaveních, která musíte aktualizovat. Organizace si například často určují požadavky na minimální a maximální délku hesla, které musíte splnit.     

### <a name="protection"></a>Protection  
Po registraci zařízení bude aplikace Portál společnosti i nadále kontrolovat, že je chráněno. Pokud si například nainstalujete aplikaci z nedůvěryhodného zdroje, upozorní vás a dokonce vám může i odvolat přístup k firemním datům. Takovouto zásadu je běžné v organizacích a často je potřeba odinstalovat nedůvěryhodné aplikace předtím, než jste znovu získali přístup.  

### <a name="setting-notifications"></a>Nastavení oznámení  
Pokud po registraci vaše organizace vynucuje nový požadavek na zabezpečení (například vícefaktorové ověřování), aplikace Portál společnosti vás o něm informuje. Budete tak mít možnost si nastavení upravit, abyste se zařízením mohli dále pracovat.  

Další informace o registraci najdete v tématu s informacemi o tom, [co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Registrace zařízení s Iosem   

> [!IMPORTANT]
> Snímky obrazovky v této části ukazují možnosti pro zařízení s Iosem verze 12,1 a starší. Kde je to možné, jsme zahrnuli pokyny specifické pro verzi iOS 12.2 a novější. Pokud si všimnete, že vaše prostředí se liší od na snímcích obrazovky je znázorněno, prosím použijte 12.2 pokyny.      

Přejděte do obchodu s aplikacemi stáhnout a nainstalovat [aplikace portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) do vašeho zařízení. Během registrace budete také potřebovat připojení Wi-Fi a přístup do prohlížeče Safari. 

Pokud pozastavíte na více než několik minut, během registrace, může aplikace zavření nebo ukončení instalace. Pokud k tomu dojde, otevřete aplikaci portál společnosti a zkuste to znovu.  

1. Otevřete portál společnosti a přihlaste se pomocí svého pracovního nebo školního účtu. 

    ![Příklad snímek obrazovky aplikace portál společnosti přihlásit.](./media/ios-01-cp-enroll-1903.PNG)  

2. Po zobrazení výzvy k přijímání oznámení na portál společnosti, klepněte na **povolit.** Portál společnosti používá oznámení vás upozorní, pokud je například potřeba aktualizovat nastavení zařízení. 

    ![Příklad snímek domovské stránky portálu společnosti, řádku "Oznámení".](./media/ios-04-cp-enroll-1903.PNG)  

3. Na **nastavení přístupu** obrazovky, vyberte **začít.**  

     ![Příklad – snímek obrazovky portálu společnosti, obrazovky "Nastavení přístupu".](./media/ios-05-cp-enroll-1903.PNG)  

4. Přečtěte si seznam informací o zařízení vaší organizaci uvidí a neuvidí. [Další podrobnosti o tomto tématu](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) může se vyhledat přes **Další** odkaz. Až budete hotovi, klepněte na **pokračovat**.  

    ![Příklad snímek obrazovky aplikace portál společnosti "Co organizaci uvidí", pomocí tlačítka pro pokračování.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. **Co se chystá?** obrazovky obsahuje souhrn zbývající kroky. Tyto kroky může lišit v závislosti na vaší verzi iOS. 
    * **iOS 12.2 a novější**: prostředí může vyžadovat, místo abyste:  

        a. **Povolit stažení profilu správy**: Váš prohlížeč bude otevřít na webu portál společnosti a vyzve, abyste toto stahování povolili. Stahování se uloží v aplikaci nastavení.  

        b. **Otevřete aplikaci nastavení a instalovat profil**: Budete muset přejít do nastavení aplikace a nainstalovali profil správy.  

        c. **Vraťte se do aplikace portál společnosti**: Budete se muset vrátit do aplikace portál společnosti pro dokončení instalace.  

    Až budete připraveni stáhnout profil pro správu, klepněte na **pokračovat**.  

6. Safari se otevře web portál společnosti. Po zobrazení výzvy ke stažení konfiguračního profilu, klepněte na **povolit**.  
    * **iOS 12.2 a novější**: Počkejte profil, který chcete dokončení stahování v prohlížeči Safari nebo klepněte na **provádí**. Otevřete **nastavení** aplikace na vašem zařízení.  

    > [!IMPORTANT]
    > Je třeba přejít **nastavení** aplikace a instalaci tohoto profilu do 8 minut od stáhnout. Pokud to neuděláte, profil, který se odeberou a bude nutné restartovat registrace. 

7. V **nastavení** aplikace, klepněte na **instalovat profil stažen** > **nainstalovat**. Pokud **instalovat profil stažen** nebude nezobrazí jako možnost, přejděte na **Obecné** > **profily**. Pokud stále nevidíte profilu, budete muset znovu stáhnout.  

    ![Ukázkovém snímku obrazovky v aplikaci nastavení, nastavení instalace profilu stáhli s red Odznáček udávající nedávno staženým profilem.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. Pokud se zobrazí výzva, zadejte heslo zařízení. Potom klepněte na **nainstalovat**.      

9. Na další obrazovce je standardní systém upozornění pro správu zařízení. Další informace o co vaše organizace uvidí a neuvidí na vašem zařízení, najdete v příslušné [článek dokumentace Intune](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Chcete-li pokračovat v instalaci, klepněte na **nainstalovat**. Pokud budete vyzváni k důvěřování vzdálené správě, klepněte na **důvěryhodnosti**.  

    ![Příklad snímek obrazovky nastavení aplikace, obrazovka upozornění standardního systému pro správu mobilních zařízení a kořenový certifikát.](./media/ios-15-cp-enroll-1903.PNG)  

10. Po dokončení instalace, klepněte na **provádí**. Pokud chcete ověřit, že profil byl nainstalován, přejděte na **Správa zařízení a profily** nastavení. Profil uvedený v seznamu byste měli vidět **Správa mobilních zařízení**.   

    ![Příklad snímek obrazovky nastavení aplikace, Správa profilů a zařízení nastavení zobrazující profil pro správu.](./media/ios-00-cp-enroll-1903.PNG)  


11. Vraťte se **portál společnosti** aplikace. Portál společnosti se začne synchronizovat, a nastavit vaše zařízení. Portál společnosti vyzve aktualizovat další nastavení zařízení. Pokud ano, klepněte na **pokračovat**.

    ![Příklad – snímek obrazovky portálu společnosti, "Nastavení přístupu" obrazovka s žlutém trojúhelníku vedle nastavení požadavek.](./media/ios-12-cp-enroll-1903.PNG)  

12. Budete vědět, že tento instalační program je dokončen, pokud všechny položky v seznamu zobrazit zeleném kroužku. Klepněte na **Hotovo**.  
    
    ![Ukázkovém snímku obrazovky z portálu společnosti, "všechno je nastavené!" obrazovka zobrazující všechny zelené kruzích.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Pokud vaše organizace monitoruje omezení hlasu a dat nebo vám poskytne zařízení vlastněná společností, můžete mít několik kroků k dokončení. Pokud budete vyzváni k instalaci **Datalert** aplikace, najdete v článku [registraci zařízení do služby telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). Pokud vaše organizace je součástí programu registrace zařízení společnosti Apple, přečtěte si [způsobu registrace zařízení ve vlastnictví společnosti](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Další postup  
Najdete aplikace, které vám pomohou při práci nebo školu. Přečtěte si [jak aplikací jsou k dispozici](use-managed-apps-on-your-device-ios.md) vám prostřednictvím portálu společnosti.  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
