---
title: "Aplikace pro Android se zásadami ochrany aplikací"
titlesuffix: Azure portal
description: "Toto téma popisuje, co můžete očekávat, když ke správě aplikace pro Android používáte zásady ochrany aplikací."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d6fce4a48245bc8ba7533380fa5a365d44705ee
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/08/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje uživatelské prostředí u aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jenom v případě, že se aplikace používají v pracovním kontextu: třeba pro přístup k aplikacím pomocí pracovního účtu nebo pro přístup k souborům uloženým v umístění OneDrivu pro danou společnost.
##  <a name="accessing-apps"></a>Přístup k aplikacím

Všechny aplikace přidružené k zásadám ochrany aplikací na zařízeních se systémem Android vyžadují aplikaci Portál společnosti.

U zařízení nezaregistrovaných v Intune je potřeba nainstalovat aplikaci Portál společnosti. Před použitím aplikací spravovaných pomocí zásad ochrany aplikací ale uživatel nemusí aplikaci Portál společnosti spouštět ani se do ní nemusí přihlašovat.
Aplikace Portál společnosti představuje pro Intune možnost sdílení dat v zabezpečeném umístění, a proto se tato aplikace vyžaduje, i když zařízení není zaregistrované v Intune.


##  <a name="using-apps-with-multi-identity-support"></a>Použití aplikací s podporou víc identit

Zásady ochrany aplikací se použijí jenom při použití aplikace v pracovním kontextu, takže v závislosti na kontextu (pracovní nebo osobní účely) se může chování aplikací lišit.

U aplikací podporujících více identit použije Intune zásady ochrany aplikací jenom v případě, že koncový uživatel používá danou aplikaci v pracovním kontextu.  Koncovému uživateli se například při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN.  U **aplikace Outlook** se koncovému uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** k tomu dojde, když koncový uživatel použije pracovní účet.  U aplikací Microsoft **Word**, **PowerPoint* a **Excel** k tomu dojde, když koncový uživatel přistupuje k dokumentům uloženým v umístění OneDrive pro firmy pro danou společnost.
##  <a name="managing-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.

  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** neblokují druhý uživatelský účet, ale na tento druhý uživatelský účet nemají zásady ochrany aplikací vliv.

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.


* Pokud zařízení obsahuje před nasazením zásad ochrany aplikací víc uživatelských účtů, budou zásady ochrany aplikací služby Intune spravovat ten účet, u kterého se zásady ochrany aplikací nasadí dřív.


Přečtěte si níže uvedený ukázkový scénář, abyste lépe pochopili, jak se pracuje s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech, **společnosti X** a **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musíte uživatelský účet přidružený ke společnosti X odebrat.
### <a name="adding-a-second-account"></a>Přidání druhého účtu
####  <a name="android"></a>Android
Pokud používáte zařízení s Androidem, může se zobrazit zpráva o blokování s pokyny k odstranění existujícího účtu a přidání nového účtu.  Když chcete odebrat existující účet, přejděte na **Nastavení &gt; Obecné &gt; Správce aplikací &gt; Portál společnosti a vyberte Vymazat data**.

![Snímek obrazovky s chybovou zprávou a pokyny k odebrání účtu](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Zobrazení souborů médií pomocí aplikace Azure Information Protection (dříve označované jako aplikaci pro sdílení obsahu Rights Management)
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
## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Související témata
[Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)
