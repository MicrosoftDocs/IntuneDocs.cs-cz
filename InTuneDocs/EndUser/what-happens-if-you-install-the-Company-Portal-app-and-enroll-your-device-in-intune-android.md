---
# required metadata

title: Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune? | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d22f5aea-7be4-419b-b51b-a522ca037b69

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune?

Když nainstalujete aplikaci Portál společnosti a potom v ní zaregistrujete své zařízení s Androidem v Intune, můžete v aplikaci Portál společnosti provádět tyto kroky:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání aplikací společnosti z Portálu společnosti

-   Automatická konfigurace e-mailového účtu vaší společnosti

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Když přidáte zařízení se systémem Android, udělujete správci IT oprávnění k přístupu k zařízení. Může provádět například následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat veškerá firemní data. Vaše osobní údaje a nastavení se při tom neodeberou.

-   Požadovat, abyste si v zařízení nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování zařízení nebo obnovení zařízení do výchozího továrního nastavení.

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Povolit nebo zakázat používání fotoaparátu/kamery v zařízení.

-   Vynutit šifrování všech dat v zařízení, včetně firemních a osobních údajů. Tím jsou data chráněna v případě ztráty nebo odcizení zařízení.

-   Po přidání vašeho zařízení na portál společnosti přibližně každých 8 hodin proběhnou tyto kroky:

    -   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil.

    -   Odeslání všech aktualizací inventáře hardwaru (tyto aktualizace neobsahují osobní informace).

    -   Odeslání všech aktualizací inventáře aplikací společnosti (tyto aktualizace neobsahují osobní informace).

### Související témata
[Použití zařízení Android s Intune](using-your-android-device-with-intune.md)

<!--HONumber=May16_HO1-->


