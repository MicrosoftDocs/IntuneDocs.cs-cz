---
# required metadata

title: Zrušení registrace zařízení v Intune, pokud odmítnete podmínky použití | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Zrušení registrace zařízení v Intune, pokud odmítnete podmínky použití

Nejlepší způsob, jak zrušit registraci zařízení s Androidem, je přijmout podmínky použití, přihlásit se do aplikace Portál společnosti a potom zrušit registraci zařízení pomocí [těchto pokynů](unenroll-your-device-from-intune-android.md). Pokud ale při pokusu o přihlášení k aplikaci Portál společnosti odmítnete podmínky použití, budete se vám bránit při budoucích pokusech v přihlášení k aplikaci Portál společnosti, takže ke zrušení registrace musíte použít tyto pokyny alternativního postupu.

Když odinstalujete aplikaci Portál společnosti, zrušíte tím taky registraci vašeho zařízení ve službě Intune. To znamená, že zařízení už nebude mít přístup k prostředkům společnosti.  Další informace o tom, co se stane, pokud zrušíte registraci, najdete v tématu [Co se stane, když zrušíte registraci zařízení v Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)..

Než odinstalujete aplikaci Portál společnosti, musíte přejít na nastavení **Správci zařízení** a vypnout **Portál společnosti**. Přesný postup se může mírně lišit v závislosti na tom, jako zařízení se systémem Android používáte.

Postup zrušení registrace zařízení v Intune pomocí aplikace Portál společnosti:

1.  Přejděte na **Nastavení** &gt; **Zabezpečení &amp; Zamykací obrazovka** &gt; **Správci zařízení**..

    Provedením tohoto kroku okamžitě zrušíte registraci zařízení.

2.  Zaškrtněte políčko vedle položky **Portál společnosti** nebo tuto položku vypněte..

    Teď můžete aplikaci Portál společnosti odinstalovat.


### Související témata
[Použití zařízení Android s Intune](using-your-android-device-with-intune.md)

<!--HONumber=May16_HO1-->

