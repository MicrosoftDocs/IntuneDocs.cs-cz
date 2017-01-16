---
title: "Aplikace pro Android se zásadami MAM | Dokumentace Microsoftu"
description: "Toto téma popisuje, co máte očekávat, když je vaše aplikace spravovaná pomocí zásad správy mobilních aplikací."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Co očekávat, když ke správě své aplikace pro Android používáte zásady MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje činnost uživatele aplikací se zásadami správy mobilních aplikací (MAM). Zásady MAM se použijí jenom v případě, že se aplikace používají k práci: třeba když uživatel k aplikacím přistupuje pomocí pracovního účtu nebo přistupuje k souborům, které jsou uložené ve firemním umístění OneDrive.
##  <a name="access-apps"></a>Přístup k aplikacím

Všechny aplikace přidružené k zásadám MAM na zařízeních s Androidem vyžadují aplikaci Portál společnosti.

U zařízení nezaregistrovaných v Intune je potřeba nainstalovat aplikaci Portál společnosti. Před použitím aplikací spravovaných pomocí zásad MAM ale uživatel nemusí aplikaci Portál společnosti spouštět ani se do ní přihlašovat.

Aplikace Portál společnosti představuje způsob, jak může Intune sdílet data v zabezpečeném umístění. Aplikace Portál společnosti je proto požadovaná pro všechny aplikace, které jsou přidružené k zásadám MAM, i když zařízení není zaregistrované v Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Použití aplikací s podporou více identit

Zásady MAM se použijí jen v pracovním kontextu. Aplikace se proto můžou chovat odlišně podle toho, jestli je kontext pracovní nebo osobní.

Uživateli se třeba při přístupu k pracovním datům zobrazí výzva k zadání kódu PIN. U **aplikace Outlook** se uživateli zobrazí výzva k zadání kódu PIN při spouštění aplikace. U **aplikace OneDrive** se uživateli zobrazí výzva k zadání kódu PIN při zadání pracovního účtu. U aplikací Microsoft **Word**, **PowerPoint** a **Excel** se uživateli zobrazí výzva k zadání kódu PIN, když přistupuje k dokumentům uloženým v umístění OneDrive pro firmy.

##  <a name="manage-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad MAM jenom na jeden uživatelský účet v každém zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný. Ve všech případech ale zásady ovlivňují jenom prvního uživatele, který získá zásady MAM.

  * Aplikace **Microsoft Word**, **Excel** a **PowerPoint** druhý uživatelský účet neblokují, ale na tento druhý uživatelský účet nemají zásady MAM vliv.

  * U aplikací **OneDrive** a **Outlook** můžete používat jenom jeden pracovní účet.  U těchto aplikací nejde přidat více pracovních účtů.  Na zařízení ale můžete odebrat uživatele a přidat jiného uživatele.


* Pokud zařízení obsahuje před nasazením zásad MAM více uživatelských účtů, bude zásadami MAM služby Intune spravován ten účet, do kterého se zásady MAM nasadí dříve.


Přečtěte si následující ukázkový scénář, abyste lépe pochopili, jak se pracuje s více uživatelskými účty.

Uživatel A pracuje ve dvou společnostech – ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad MAM. **Společnost X** nasadí zásady MAM **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady MAM, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby byl účet přidružený ke společnosti Y spravován pomocí zásad MAM, musíte odebrat uživatelský účet přidružený ke společnosti X.
### <a name="add-a-second-account"></a>Přidání druhého účtu
####  <a name="android"></a>Android
Pokud používáte zařízení s Androidem, může se zobrazit zpráva o blokování s pokyny k odebrání existujícího účtu a přidání nového účtu.  Když chcete odebrat existující účet, přejděte na **Nastavení &gt;Obecné &gt; Správce aplikací &gt;Portál společnosti**. Pak zvolte **Vymazat data**.

![Snímek obrazovky s chybovou zprávou a pokyny k odebrání účtu](../media/AppManagement/Android_SwitchUser.png)

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
[Co očekávat, když ke správě své aplikace pro iOS používáte zásady MAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Související témata
[Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


