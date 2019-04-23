---
title: Registrace firemních zařízení pomocí aplikace pro Microsoft Intune | Dokumentace Microsoftu
description: Popisuje, jak zaregistrovat firemní zařízení s Androidem v Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cf384bfcc0782226e363a6527ea47c4140f7faa
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61499643"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Registrace firemních zařízení pomocí aplikace pro Microsoft Intune

Registrace firemních zařízení s Androidem získat zabezpečený přístup k firemnímu e-mailu, aplikacím a další data, která vaší organizaci je k dispozici. Aplikace pro Microsoft Intune podporuje zařízení vlastněných společností s Androidem 6.0 a novějším. To se automaticky nainstaluje na nový a obnovení továrního nastavení zařízení během registrace. 

Existují čtyři způsoby, jak zaregistrovat. Vaše organizace by měly umožňují vědět, kterou možnost použít.
 
* Bezkontaktní komunikace (NFC)  
* Podpisový  
* Kód QR   
* Automatizované Google  

Než začnete s registrací, ujistěte se, že budete vědět o možnosti, kterou budete muset použít tak, že můžete provést příslušné kroky.  

## <a name="enroll-device"></a>Registrace zařízení 
Dokončete tyto kroky pro nastavení a registrace zařízení.  

> [!NOTE]
> S Androidem výrobce zařízení nebo verzi může vyžadovat, abyste mohli provést další kroky, které nejsou zahrnuty v tomto postupu. Barvy a text, který se zobrazí na snímcích obrazovky se může zobrazit i jiné na vašem zařízení.  

1. Zapněte nový nebo obnovení továrního nastavení zařízení.  
2. Na **uvítací** obrazovce vyberte svůj jazyk.   Pokud jste jste obdržely pokyn k registraci pomocí NFC a kód QR, postupujte podle následující krok, který odpovídá metodu.  
     * NFC: Klepněte na zařízení podporou NFC na programátorovi zařízení pro připojení k síti vaší organizace. Postupujte podle pokynů na obrazovce. Když obrazovka pro Chrome na podmínky služby, přejděte ke kroku 5.  

      * Kód QR: Proveďte kroky v [registrace kód QR](#qr-code-enrollment).  

      Pokud jste jste dostali pokyn použít jinou metodu, pokračujte krokem 3.    

1. Připojení k Wi-Fi a klepněte na **Další**. Postupujte podle kroku, který odpovídá způsobu registrace. 

    * token: Když se zobrazí na přihlašovací obrazovce Google, proveďte kroky v [Token pro zápis](#token-enrollment).    
    * Automatizované Google: Po připojení k Wi-Fi zařízení bude rozpoznán vaší organizací. Pokračujte krokem 4 a postupujte podle pokynů na obrazovce, dokud se instalace byla dokončena.    
 
       ![Příklad snímek obrazovky podmínky Google, který se zobrazí, pokud používáte Touch nula Google, zvýraznění tlačítko Přijmout a pokračovat.](./media/google-zero-touch-intune-app-01.png)   
   
4. Přečtěte podmínky společnosti Google. Potom klepněte na **přijmout a pokračovat**.  

      ![Příklad snímek obrazovky podmínek Google, zvýraznění tlačítko Přijmout a pokračovat.](./media/fully-managed-intune-app-04.png)   

6. Projděte si Chrome podmínky služby. Potom klepněte na **přijmout a pokračovat**.  

   ![Příklad snímek obrazovky smluvních podmínkách Chrome, zvýraznění tlačítko Přijmout a pokračovat.](./media/fully-managed-intune-app-06.png)   

7. Na přihlašovací obrazovky Přihlaste se pomocí svého pracovního nebo školního účtu.   

    a. Zadejte e-mailu a klepněte na **Další**.      
    b. Zadejte své heslo a klepněte na **přihlášení**.  

8. V závislosti na požadavcích vaší organizace vám může zobrazit výzva k aktualizaci nastavení, jako je například zámek obrazovky nebo šifrování. Pokud se zobrazí tyto výzvy, klepněte na **nastavit** a postupujte podle pokynů na obrazovce.  

   ![Obrázek příkladu sady nahoru obrazovce pracovní telefon, zvýraznění tlačítko nastavit.](./media/fully-managed-intune-app-10.png)   

9. Instalace pracovních aplikací na zařízení, klepněte na **nainstalovat**. Po dokončení instalace, klepněte na **Další**.  

   ![Obrázek příkladu sady nahoru obrazovce pracovní telefon, zvýraznění tlačítko nainstalovat.](./media/fully-managed-intune-app-11.png)   

10. Až se zobrazí zpráva, že vaše zařízení je připravené, klepněte na **HOTOVO**. 

11. Přejděte do své aplikace a otevřete aplikaci Microsoft Intune. Vyberte **přihlášení**. 

12. Na **nastavení přístupu** obrazovky, zobrazí se vám seznam čekající úlohy. Klepněte na **pokračovat**.  

       ![Obrázek příkladu aplikace pro Microsoft Intune, nastavení přístupu obrazovky čekající úlohy.](./media/fully-managed-intune-app-14.png)   

13. Po dokončení registrace zařízení klepněte na **pokračovat**. Microsoft Intune může zobrazit výzvu k aktualizaci další nastavení zařízení.   

       ![Obrázek příkladu aplikace pro Microsoft Intune, obrazovky nastavení aktualizace zařízení.](./media/fully-managed-intune-app-15-2.png)   

14. Instalace byla dokončena, když všechny položky v seznamu zobrazit zeleném kroužku. Můžete teď přístup k prostředkům společnosti.  

       ![Obrázek příkladu aplikace pro Microsoft Intune, nastavení přístupu k obrazovce znázorňující dokončení úlohy.](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>Zápis kódu QR  
V této části naskenujete kód QR poskytované společnosti.  Jakmile budete hotovi, vás přesměrujeme zpět na postup registrace zařízení.     
  
1. Na **úvodní** obrazovky, klepněte na obrazovku pětkrát na spuštění instalačního programu kód QR.  

   ![Příklad obrázek úvodní obrazovky nastavení zařízení, zvýraznění pokynů a klepněte na obrazovku.](./media/qr-code-intune-app-01.png)  

2. Postupujte podle pokynů na obrazovce pro připojení k Wi-Fi.  
3. Pokud zařízení nemá skener kódů QR, obrazovek instalačního programu se zobrazí průběh jako nainstalovaní skeneru. Počkejte na dokončení instalace.  
4. Po zobrazení výzvy, kontrolovat registrační profil kód QR, který vaše organizace zobrazila.  
5. Vraťte se na [zapsat zařízení](#enroll-device), krok 4 pro pokračování instalačního programu.  

## <a name="token-enrollment"></a>Token pro zápis  
V této části zadáte token poskytované společnosti. Jakmile budete hotovi, vás přesměrujeme zpět na postup registrace zařízení.  

1. Na přihlašovací obrazovku Google v **E-mail nebo telefon** zadejte **afw #setup**. Klepněte na **Další**. 

   ![Obrázek příkladu Google přihlašovací obrazovky, že je "afw #setup" zadali do pole.](./media/token-intune-app-01.png)   

2. Zvolte **nainstalovat** pro **zásad zařízení s Androidem** aplikace. Pokračujte v instalaci. V závislosti na vašem zařízení může být potřeba zkontrolovat a přijmout další podmínky.    

3. Na **zaregistrovat toto zařízení** obrazovky, vyberte **Další**.  

   ![Obrázek příkladu zapsat tuto obrazovku na zařízení. Zobrazí obrázek kódu QR; Zvýrazní tlačítko Další.](./media/token-intune-app-02.png)  

4. Vyberte **zadejte kód**.

   ![Příklad snímek active skener kódů QR. Zvýrazní tlačítko Enter kód.](./media/token-intune-app-03.png)  

5. Na **prohledávají nebo zadejte kód** obrazovky, zadejte kód, který vaše organizace zobrazila.  Pak klikněte na tlačítko **Další**.  

   ![Obrázek příkladu kontroly nebo zadejte kód obrazovky, zvýraznění tlačítko Další.](./media/token-intune-app-04.png)  

6. Vraťte se na [zapsat zařízení](#enroll-device), krok 4 pro pokračování instalačního programu.  



## <a name="next-steps"></a>Další postup   
Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.  
