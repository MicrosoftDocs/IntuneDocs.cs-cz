---
# required metadata

title: Volba způsobu registrace mobilních zařízení | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Volba způsobu registrace mobilních zařízení

Registrace mobilních zařízení je proces, který zajišťuje správu smartphonů, tabletů a počítačů přes Microsoft Intune. Z pozice správce musíte určit, jak nejlépe provést registraci zařízení, podle těchto kritérií:

 -  Vlastnictví (osobní zařízení vs. zařízení patřící společnosti)
 -  Využívání (sdílené vs. osobní)
 -  Platforma (iOS, Android, Windows Phone, počítač s Windows, počítač Mac)

Nejvhodnější způsob registrace zařízení, která spravujete, vám pomůžou s odpověďmi na následující otázky.

## Přinášejí si zaměstnanci vlastní zařízení nebo používání zařízení, které jim dala vaše organizace?

  **Zařízení ve vlastnictví uživatelé:** V takovém případě jde o registraci typu Přineste si vlastní zařízení (BYOD – Bring Your Own Device). Uživatelé si můžou na zařízení nainstalovat aplikaci Portál společnosti Intune a pak zařízení zaregistrovat, aby měli přístup k prostředkům společnosti (například k e-mailům, podnikovým aplikacím, datům společnosti a podpoře).  
  > [!div class="button"]   [Registrace BYOD >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **Zařízení vlastněná společností:** Zařízení vlastněná společností (COD – Company-Owned Devices) je možné do Intune registrovat několika různými způsoby v závislosti na potřebách organizace a typech spravovaných zařízení. Další otázka...

## Jak se zařízení ve vlastnictví společnosti využívají? Jsou sdílená nebo je využívá vždycky jenom jeden konkrétní uživatel?

**Sdílená zařízení vlastněná společností:** Tato zařízení nemají jenom jednoho konkrétního uživatele a obvykle nejsou nakonfigurovaná pro přístup k e-mailu. O taková zařízení jde například v případě zařízení sloužících jako veřejný terminál nebo v případě zařízení, která si uživatelé vždy pouze vypůjčí na konkrétní úkol. Doporučené metody registrace závisí na platformě zařízení.

  - **Zařízení s Windows a Androidem:** *Správce registrace zařízení* je účet Intune, pomocí kterého je možné registrovat mnoho sdílených zařízení prostřednictvím aplikace Portál společnosti.
  > [!div class="button"]   [Správce registrace zařízení >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Zařízení s iOS:** Sdílená zařízení s iOS je možné spravovat třemi způsoby.  **Jak zaregistrujete svoje sdílená zařízení s iOS?**

    - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se s ním.
    > [!div class="button"]     [Registrace DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.

    > [!div class="button"]     [Registrace pomocí Pomocníka s nastavením >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) nebo [Přímá registrace >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **Žádná z výše uvedených možností:** Pokud nemůžete nebo nechcete použít metody registrace DEP nebo Apple Configurator společnosti Apple, použijte Správce registrace zařízení služby Intune.
    > [!div class="button"]     [Registrace pomocí Správce registrace zařízení >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Konkrétní uživatelé:** Zařízení vlastněná společností, která dostali k užívání konkrétní uživatelé, je třeba sledovat jako majetek společnosti a současně je potřeba uživatelům umožnit využívat je jako osobní zařízení pro přístup k e-mailům a datům. Doporučené metody registrace závisí na platformě zařízení.

  - **Zařízení s Windows a Androidem:** Naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností můžete zařízení označit v Intune jako zařízení ve vlastnictví společnosti. Uživatelé si pak můžou zaregistrovat svá zařízení jako osobní zařízení nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům.
  > [!div class="button"]   [Označení číslem IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **Zařízení s iOS:** Sdílená zařízení s iOS je možné spravovat třemi způsoby.  **Jak zaregistrujete svoje sdílená zařízení s iOS?**

    - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a na základě něj se zaregistruje.
    > [!div class="button"]     [Registrace DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.

    Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.
    Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.
    > [!div class="button"][Registrace pomocí Pomocníka s nastavením >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][Přímá registrace zařízení s iOS](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Žádná z výše uvedených možností:** Pokud nemůžete nebo nechcete použít metody registrace DEP nebo Apple Configurator společnosti Apple, můžete naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností zařízení označit v Intune jako zařízení ve vlastnictví společnosti. Uživatelé si pak můžou zaregistrovat svá zařízení jako osobní zařízení nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům. > [!div class="button"][Označení zařízení pomocí kódů IMEI](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO1-->


