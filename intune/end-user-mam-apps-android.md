---
title: "Aplikace pro Android se zásadami ochrany aplikací"
description: "Toto téma popisuje, co můžete očekávat, když ke správě aplikace používáte zásady ochrany aplikací."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e9dc17cda485be244e05409bca69672edb87969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Toto téma popisuje uživatelské prostředí u aplikací se zásadami ochrany aplikací. Zásady ochrany aplikací se použijí jen v případě, že se aplikace používají v pracovním kontextu, například když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo používá soubory, které jsou uložené na firemním OneDrivu.
##  <a name="access-apps"></a>Přístup k aplikacím

Všechny aplikace přidružené k zásadám ochrany aplikací na zařízeních s Androidem vyžadují aplikaci Portál společnosti.

U zařízení nezaregistrovaných v Intune je potřeba nainstalovat aplikaci Portál společnosti. Před použitím aplikací spravovaných zásadami ochrany aplikací ale uživatel nemusí aplikaci Portál společnosti spouštět ani se do ní přihlašovat.

Aplikace Portál společnosti představuje způsob, jak může Intune sdílet data v zabezpečeném umístění. Aplikace Portál společnosti se proto vyžaduje pro všechny aplikace, které jsou přidružené k zásadám ochrany aplikací, i když zařízení není zaregistrované v Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Zásady ochrany aplikací se používají jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu. U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

##  <a name="manage-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací jen na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný. Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.

  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** neblokují druhý uživatelský účet, ale na tento druhý uživatelský účet nemají zásady ochrany aplikací vliv.

  * U aplikací **OneDrive** a **Outlook** můžete používat jenom jeden pracovní účet.  U těchto aplikací nejde přidat více pracovních účtů.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.


* Pokud zařízení obsahuje před nasazením zásad ochrany aplikací několik uživatelských účtů, bude zásadami ochrany aplikací služby Intune spravován ten účet, u kterého se zásady ochrany aplikací nasadí dřív.


Přečtěte si následující ukázkový scénář, abyste lépe pochopili, jak se pracuje s více uživatelskými účty.

Uživatel A pracuje ve dvou společnostech – ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby byl účet přidružený ke společnosti Y spravován pomocí zásad ochrany aplikací, musíte odebrat uživatelský účet přidružený ke společnosti X.
### <a name="add-a-second-account"></a>Přidání druhého účtu
####  <a name="android"></a>Android
Pokud používáte zařízení s Androidem, může se zobrazit zpráva o blokování s pokyny k odebrání existujícího účtu a přidání nového účtu.  Když chcete odebrat existující účet, přejděte na **Nastavení &gt;Obecné &gt; Správce aplikací &gt;Portál společnosti**. Pak zvolte **Vymazat data**.

![Snímek obrazovky s chybovou zprávou a pokyny k odebrání účtu](./media/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Zobrazení souborů médií pomocí aplikace Azure Information Protection
Pokud chcete na zařízení s Androidem zobrazit podnikové audiovizuální a obrázkové soubory nebo soubory PDF, použijte [aplikaci Azure Information Protection](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (dříve známou jako aplikace sdílení Rights Management).

Tuto aplikaci si můžete stáhnout z obchodu Google Play.  

Podporované jsou následující typy souborů:

* **Zvuk:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (rozšířené AAC+), AAC ELD (rozšířené AAC s malým zpožděním), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Obrázky:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Dokumenty:** PDF, PPDF


|**pfile**|**text**|
|----|----|
|Pfile je obecný „obálkový“ formát pro chráněné soubory, který zapouzdřuje šifrovaný obsah a licence Azure Information Protection. Dá se použít pro ochranu libovolného typu souboru.|Textové soubory včetně souborů XML, CSV a dalších jde otvírat pro zobrazení v aplikaci, i když jsou chráněné. Typy souborů: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|

## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](end-user-mam-apps-ios.md)