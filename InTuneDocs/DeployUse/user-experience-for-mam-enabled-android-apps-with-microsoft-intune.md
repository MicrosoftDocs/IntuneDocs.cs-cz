---
title: "Aplikace pro Android se zásadami MAM | Microsoft Intune"
description: "Toto téma popisuje, co máte očekávat, když je vaše aplikace spravovaná pomocí zásad správy mobilních aplikací."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Co očekávat, když ke správě své aplikace pro Android používáte zásady MAM
Toto téma popisuje činnost uživatele aplikací se zásadami MAM. Zásady správy mobilních aplikací (MAM) se použijí jenom v případě, že se aplikace používají k práci: třeba pro přístup k aplikacím pomocí pracovního účtu nebo pro přístup k souborům uloženým v umístění OneDrive pro danou společnost.
##  Přístup k aplikacím

Všechny aplikace přidružené k zásadám MAM na zařízeních se systémem Android vyžadují aplikaci Portál společnosti.

U zařízení nezaregistrovaných v Intune je potřeba nainstalovat aplikaci Portál společnosti. Před použitím aplikací spravovaných pomocí zásad MAM ale uživatel nemusí aplikaci Portál společnosti spouštět ani se do ní přihlašovat.
Aplikace Portál společnosti představuje pro Intune možnost sdílení dat v zabezpečeném umístění, a proto se tato aplikace vyžaduje, i když zařízení není zaregistrované v Intune.


##  Použití aplikací s podporou víc identit

Zásady MAM se použijí jenom při použití aplikace k práci, takže v závislosti na kontextu (pracovní nebo osobní účely) se může chování aplikací lišit.

U aplikací podporujících více identit Intune použije zásady MAM jenom v případě, že koncový uživatel používá danou aplikaci k práci.  Koncovému uživateli se například při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN.  U **aplikace Outlook** se koncovému uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** k tomu dojde, když koncový uživatel použije pracovní účet.  U aplikací Microsoft **Word**, **PowerPoint* a **Excel** k tomu dojde, když koncový uživatel přistupuje k dokumentům uloženým v umístění OneDrive pro firmy pro danou společnost.
##  Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad MAM jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale zásady ovlivňují jenom prvního uživatele, který získá zásady MAM.

  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** druhý uživatelský účet neblokují, ale na tento druhý uživatelský účet nemají zásady MAM vliv.

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.


* Pokud zařízení obsahuje před nasazením zásad MAM víc uživatelských účtů, bude zásadami MAM služby Intune spravovaný ten účet, do kterého se zásady MAM nasadí dřív.


Přečtěte si níže uvedený ukázkový scénář, abyste lépe pochopili, jak se pracuje s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech, **společnosti X** a **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad MAM. **Společnost X** nasadí zásady MAM **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady MAM, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby byl účet přidružený ke společnosti Y spravovaný pomocí zásad MAM, musíte odebrat uživatelský účet přidružený ke společnosti X.
### Přidání druhého účtu
####  Android
Pokud používáte zařízení s Androidem, může se zobrazit zpráva o blokování s pokyny k odstranění existujícího účtu a přidání nového účtu.  Když chcete odebrat existující účet, přejděte na **Nastavení &gt; Obecné &gt; Správce aplikací &gt; Portál společnosti a vyberte Vymazat data**.

![Snímek obrazovky s chybovou zprávou a pokyny k odebrání účtu](../media/AppManagement/Android_SwitchUser.png)

##  Zobrazení souborů médií pomocí aplikace Azure Information Protection (dříve označované jako aplikaci pro sdílení obsahu Rights Management)
Pokud chcete na zařízení se systémem Android zobrazit podnikové audiovizuální a obrázkové soubory nebo soubory PDF, použijte [aplikaci Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Tuto aplikaci si můžete stáhnout z obchodu Google Play.  

Podporovány jsou následující typy souborů:

* **Zvuk:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozšířené AAC+), AAC ELD (rozšířené AAC s malým zpožděním), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Obrázky:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumenty:** PDF, PPDF

------------
|**pfile**|**text**|
|----|----|
|Pfile je obecný „obálkový“ formát pro chráněné soubory, který zapouzdřuje šifrovaný obsah a licence služby Azure Information Protection. Lze jej použít pro ochranu libovolného typu souboru.|Textové soubory včetně souborů XML, CSV atd. lze otevřít pro zobrazení v aplikaci, i když jsou chráněny. Typy souborů: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## Další kroky
[Co očekávat, když ke správě své aplikace pro iOS používáte zásady MAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### Viz taky
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


