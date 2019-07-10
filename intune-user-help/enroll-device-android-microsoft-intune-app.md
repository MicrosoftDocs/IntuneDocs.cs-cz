---
title: Registrace podnikového zařízení ve službě Microsoft Intune App | Microsoft Docs
description: Popisuje registraci firemního zařízení s Androidem v Intune.
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
ms.openlocfilehash: b23323766e91e31c48aec6a51dfae971c3a333e8
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735759"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Registrace podnikového zařízení pomocí aplikace Microsoft Intune

Zaregistrujte svoje zařízení s Androidem vlastněné společností, abyste získali zabezpečený přístup k firemnímu e-mailu, aplikacím a dalším datům, která vaše organizace zpřístupní. Aplikace Microsoft Intune podporuje zařízení vlastněná společností se systémem Android 6,0 a novějším. Během registrace se automaticky nainstaluje do nových zařízení a zařízení pro obnovení továrního nastavení. 

Existují čtyři způsoby, jak se zaregistrovat. Vaše organizace by vám měla sdělit, kterou možnost použít.
 
* Bezkontaktní komunikace (NFC)  
* Podpisový  
* Kód QR   
* Google Zero Touch  

## <a name="enroll-device"></a>Registrace zařízení 
Provedením těchto kroků nastavíte a zaregistrujete své zařízení.  

> [!NOTE]
> Verze Androidu nebo výrobce zařízení můžou vyžadovat, abyste dokončili další kroky, na které se tento postup nezabývá. Barvy a text, který vidíte na snímcích obrazovky, se může zobrazit i jinak na vašem zařízení.  

1. Zapněte nové zařízení nebo zařízení pro obnovení do továrního nastavení.  
2. Na **uvítací** obrazovce vyberte svůj jazyk.   Pokud jste dostali pokyn k registraci pomocí kódu QR nebo NFC, postupujte podle níže uvedeného kroku, který odpovídá metodě.  
     * NFC: Klepněte na zařízení, které podporuje NFC, aby se připojilo k síti vaší organizace. Postupujte podle pokynů na obrazovce. Až se dostanete na obrazovku s podmínkami služby Chrome, pokračujte krokem 5.  

     * Kód QR: Proveďte kroky v části [registrace kódu QR](#qr-code-enrollment).  

     Pokud jste se dostali k používání jiné metody, pokračujte krokem 3.    

1. Připojte se k Wi-Fi a klepněte na **Další**. Použijte krok, který odpovídá metodě registrace. 

    * Klíčové Až se dostanete na přihlašovací obrazovku Google, proveďte kroky v části [registrace tokenu](#token-enrollment).    
    * Google Zero Touch: Po připojení k Wi-Fi bude vaše zařízení rozpoznatelné vaší organizací. Pokračujte krokem 4 a postupujte podle pokynů na obrazovce, dokud nebude instalace dokončena.    
 
       ![Příklad obrázku obrazovky s podmínkami pro Google, který vidíte, pokud používáte Google Zero Touch, zvýrazňování tlačítka přijmout & pokračovat.](./media/google-zero-touch-intune-app-01.png)   
   
4. Zkontrolujte výrazy Google. Pak klepněte na **přijmout &AMP; pokračovat**.  

      ![Příklad obrázku obrazovky podmínek Google, zvýrazňování tlačítka přijmout & pokračování](./media/fully-managed-intune-app-04.png)   

6. Kontrola podmínek služby v Chrome. Pak klepněte na **přijmout &AMP; pokračovat**.  

   ![Příklad obrázku obrazovky s podmínkami služby Chrome, zvýraznění tlačítko přijmout & pokračovat](./media/fully-managed-intune-app-06.png)   

7. Na obrazovkách přihlášení se přihlaste pomocí svého pracovního nebo školního účtu.   

    a. Zadejte svůj e-mail a klepněte na **Další**.      
    b. Zadejte heslo a klepněte na **Přihlásit se**.  

8. V závislosti na požadavcích vaší organizace se může zobrazit výzva k aktualizaci nastavení, jako je třeba zámek nebo šifrování obrazovky. Pokud se zobrazí tyto výzvy, klepněte na **nastavit** a postupujte podle pokynů na obrazovce.  

   ![Příklad obrázku nastavení obrazovky pro práci s telefonem, tlačítko zvýraznění sady](./media/fully-managed-intune-app-10.png)   

9. Pokud chcete na zařízení nainstalovat pracovní aplikace, klepněte na **nainstalovat**. Po dokončení instalace klepněte na **Další**.  

   ![Příklad obrázku nastavení obrazovky pro práci s telefonem, zvýraznění tlačítka pro instalaci](./media/fully-managed-intune-app-11.png)   

10. Jakmile se zobrazí zpráva, že je zařízení připravené, klepněte na **Hotovo**. 

11. Přejít do vašich aplikací a otevřít aplikaci Microsoft Intune. Vyberte **Přihlásit se**. 

12. Na obrazovce pro **přístup k instalaci** se zobrazí seznam úkolů, které čekají na vyřízení. Klepněte na **pokračovat**.  

       ![Příklad obrázku Microsoft Intune aplikace, nastavení obrazovky přístupu a zobrazení nevyřízených úkolů.](./media/fully-managed-intune-app-14.png)   

13. Až se registrace zařízení dokončí, klepněte na **pokračovat**. Microsoft Intune vás může zobrazit výzva k aktualizaci dalších nastavení zařízení.   

       ![Příklad obrázku Microsoft Intune aplikace, aktualizace obrazovky nastavení zařízení](./media/fully-managed-intune-app-15-2.png)   

14. Instalace je dokončena, když všechny položky v seznamu zobrazí zelený kroužek. Teď máte přístup k prostředkům společnosti.  

       ![Příklad obrázku Microsoft Intune aplikace, nastavení obrazovky přístupu a zobrazení dokončených úkolů](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>Zápis kódu QR  
V této části provedete kontrolu kódu QR poskytovaného vaší společností.  Až budete hotovi, přesměrujeme vás zpátky na kroky registrace zařízení.     
  
1. Na **úvodní** obrazovce klepněte pětkrát na obrazovku a spusťte nastavení kódu QR.  

   ![Příklad obrázku úvodní obrazovky instalace zařízení, zvýraznění pokynů pro klepnutí na obrazovku](./media/qr-code-intune-app-01.png)  

2. Připojte se k Wi-Fi podle pokynů na obrazovce.  
3. Pokud zařízení nemá skener kódu QR, obrazovky instalačního programu zobrazí průběh instalace skeneru. Počkejte na dokončení instalace.  
4. Po zobrazení výzvy Naskenujte kód QR v registračním profilu, který vám vaše organizace poskytla.  
5. Vraťte se k [registraci zařízení](#enroll-device), krok 4 pro pokračování v instalaci.  

## <a name="token-enrollment"></a>Zápis tokenu  
V této části zadáte svůj token poskytovaný společností. Až budete hotovi, přesměrujeme vás zpátky na kroky registrace zařízení.  

1. Do přihlašovací obrazovky Google v poli **e-mail nebo telefon** zadejte **AFW # Setup**. Klepněte na **Další**. 

   ![Příklad obrázku přihlašovací obrazovky Google, který ukazuje, že se do pole zadává nastavení "AFW #".](./media/token-intune-app-01.png)   

2. Vyberte **nainstalovat** pro aplikaci **zásad zařízení** s Androidem. Pokračujte v instalaci. V závislosti na vašem zařízení možná budete muset zkontrolovat a přijmout další podmínky.    

3. Na obrazovce **zaregistrovat toto zařízení** vyberte **Další**.  

   ![Příklad obrázku registrace obrazovky zařízení Zobrazuje ilustraci kódu QR; zvýrazní tlačítko Další.](./media/token-intune-app-02.png)  

4. Vyberte **zadat kód**.

   ![Příklad snímku aktivního skeneru kódu QR Zvýrazní tlačítko pro zadání kódu.](./media/token-intune-app-03.png)  

5. Na obrazovce **Kontrola nebo zadání kódu** zadejte kód, který vám vaše organizace poskytla.  Pak klikněte na tlačítko **Další**.  

   ![Příklad obrázku skenování nebo zadání kódu obrazovky, zvýraznění tlačítka Další](./media/token-intune-app-04.png)  

6. Vraťte se k [registraci zařízení](#enroll-device), krok 4 pro pokračování v instalaci.  



## <a name="next-steps"></a>Další postup   
Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.  
