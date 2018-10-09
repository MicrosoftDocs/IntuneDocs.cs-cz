---
title: Aplikace pro Android se zásadami ochrany aplikací
titlesuffix: Microsoft Intune
description: Zjistěte, co můžete očekávat od aplikace pro Android, která má zásady ochrany.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8c606f9b304f91e02ba977c801bd8de18682612
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231691"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zjistěte, co můžete očekávat od aplikací pro Android, které mají zásady ochrany aplikací. Zásady ochrany aplikací se použijí jenom v případě, že se aplikace používají k práci. Například při přístupu k aplikaci pomocí pracovního účtu nebo když zobrazujete soubory uložené na OneDrivu vaší společnosti.
##  <a name="accessing-apps"></a>Přístup k aplikacím

Všechny aplikace na zařízeních s Androidem, které mají zásady ochrany aplikací, vyžadují aplikaci Portál společnosti.

Nainstalujte aplikaci Portál společnosti na všechna zařízení, která nejsou zaregistrovaná v Intune. Uživatelé se nemusí přihlašovat k aplikaci Portál společnosti, aby mohli používat aplikace, které mají zásady ochrany aplikací.
Aplikace Portál společnosti umožňuje sdílet data v zabezpečeném umístění. Požaduje se tedy i pro neregistrovaná zařízení.


##  <a name="using-apps-with-multi-identity-support"></a>Použití aplikací s podporou víc identit

Zásady ochrany aplikací se projeví, jenom když se uživatel pokusí o přístup k pracovním datům.  Když chce uživatel použít aplikaci pro osobní účely, může se aplikace chovat jinak.

Některé aplikace podporují více identit. V takovém případě použije Intune zásady ochrany aplikací jenom při přístupu uživatele k pracovním datům.  Uživateli se například může zobrazit výzva k zadání kódu PIN.  V **aplikaci Outlook** se výzva zobrazí uživateli při spuštění. V **aplikaci OneDrive** se zobrazí výzva, když uživatel použije pracovní účet.  V aplikaci Microsoft **Word**, **PowerPoint** a **Excel** se zobrazí výzva, když uživatel zobrazuje dokumenty na OneDrivu.
##  <a name="managing-user-accounts-on-the-device"></a>Správa uživatelských účtů v zařízení

Intune podporuje nasazení zásad ochrany aplikací na jeden uživatelský účet v jednom zařízení.

* V závislosti na aplikaci, kterou používáte, může být druhý uživatel v zařízení blokovaný (ale nemusí). Ve všech případech ale mají tyto zásady vliv jenom na prvního uživatele, kterému se přiřadí zásady ochrany aplikací.

  * **Microsoft Word**, **Excel** a **PowerPoint** nebudou blokovat přístup k dalším uživatelským účtům. Na tyto uživatelské účty se ale nebudou vztahovat zásady ochrany aplikací.

  * U aplikací **OneDrive a Outlook** smíte používat jenom jeden pracovní účet.  Přidávání více pracovních účtů se v těchto aplikacích blokuje.  Můžete však ze zařízení odebrat uživatele a pak přidat jiného.


* Před nasazením zásad ochrany aplikací může mít zařízení několik existujících uživatelských účtů. V takovém případě spravují zásady ochrany aplikací Intune první účet, na který jsou nasazené zásady ochrany aplikací.


Přečtěte si následující ukázkový scénář, kde se dozvíte, jak Intune zachází s několika uživatelskými účty.

Uživatel A pracuje ve dvou společnostech: ve **společnosti X** a ve **společnosti Y**. Uživatel A má pro každou společnost pracovní účet a obě společnosti používají Intune k nasazení zásad ochrany aplikací. **Společnost X** nasadí zásady ochrany aplikací **dřív než** **společnost Y**. Účet přidružený ke **společnosti X** získá zásady ochrany aplikací, ale účet přidružený ke společnosti Y ne. Pokud chcete, aby uživatelský účet přidružený ke společnosti Y spravovaly zásady ochrany aplikací, musí uživatel A odebrat uživatelský účet společnosti X.
### <a name="adding-a-second-account"></a>Přidání druhého účtu
####  <a name="android"></a>Android
Může se zobrazit výzva k odebrání existujícího účtu a přidání nového.  Když chcete odebrat existující účet, přejděte na **Nastavení &gt;Obecné &gt; Správce aplikací &gt; Portál společnosti. Potom vyberte možnost pro vymazání dat.**

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

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>text</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pfile je obecný formát obálky pro chráněné soubory. Zapouzdřuje šifrovaný obsah a licence Azure Information Protection. Dá se použít pro ochranu libovolného typu souboru. | Textové soubory včetně souborů XML, CSV atd. lze otevřít pro zobrazení v aplikaci, i když jsou chráněny. Typy souborů: txt, ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>Další kroky
[Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Viz taky
[Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune](app-protection-policies.md)
