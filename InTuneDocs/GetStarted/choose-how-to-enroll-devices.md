---
title: "Volba způsobu registrace mobilních zařízení | Microsoft Intune"
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
ms.sourcegitcommit: 928b79530ac278f78356f8d1ef9f267077634b5b
ms.openlocfilehash: 00767d06fe0d7a10cba10d0dd428f99be0390866


---

# Volba způsobu registrace mobilních zařízení

Registrace mobilních zařízení je proces, který zajišťuje správu smartphonů, tabletů a počítačů přes Microsoft Intune. Z pozice správce musíte určit, jak nejlépe provést registraci zařízení, podle těchto kritérií:

 -  Vlastnictví (osobní zařízení vs. zařízení patřící společnosti)
 -  Využívání (sdílené vs. osobní)
 -  Platforma (iOS, Android, Windows Phone, počítač s Windows, počítač Mac)

Nejvhodnější způsob registrace zařízení, která spravujete, vám pomůžou s odpověďmi na následující otázky.

## **Přinášejí si zaměstnanci vlastní zařízení nebo používání zařízení, které jim dala vaše organizace?**

  **Zařízení ve vlastnictví uživatele** (používá se také označení registrace typu Přineste si vlastní zařízení (BYOD – Bring Your Own Device) umožňují uživatelům zaregistrovat zařízení, aby měli přístup k prostředkům společnosti, jako jsou e-mail, podnikové aplikace, data společnosti a podpora. **Zařízení vlastněná společností** (COD) poskytuje organizace svým zaměstnancům pro pracovní účely.
  > [!div class="button"]   [Registrace BYOD >](#byod-device-enrollment)   [Registrace COD >](cod-device-enrollment)

### Registrace zařízení BYOD

Registrace BYOD vyžaduje, aby si uživatelé na svoje zařízení nainstalovali aplikaci Portál společnosti služby Intune. Potom ji mohou spustit a zaregistrovat se zadáním pracovních nebo školních přihlašovacích údajů. Za předpokladu, že Intune pro tyto přihlašovací údaje najde licenci, zařízení se přidá do konzoly správce Intune a získá od služby Intune zásady, které umožňují přístup k firemním prostředkům.

**Vyberte typ zařízení:**

> [!div class="op_single_selector"]
- [Nastavení správy systému Android pomocí Microsoft Intune](..deploy-use/set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Nastavení správy pro zařízení Windows Phone v Microsoft Intune](..deploy-use/set-up-windows-phone-management-with-microsoft-intune.md)
- [Nastavení správy pro zařízení Windows v Microsoft Intune](..deploy-use/set-up-windows-device-management-with-microsoft-intune.md)


### Registrace zařízení COD

Zařízení ve vlastnictví společnosti mohou být zaregistrovaná pro vyhrazeného uživatele nebo sdílená.  **Sdílená zařízení** nemají jenom jednoho konkrétního uživatele a obvykle nejsou nakonfigurovaná pro přístup k e-mailu. O taková zařízení jde například v případě zařízení sloužících jako veřejný terminál nebo v případě zařízení, která si uživatelé vždy pouze vypůjčí na konkrétní úkol. Doporučené metody registrace závisí na platformě zařízení. **Vyhrazená zařízení** dostanou k užívání konkrétní uživatelé. Je třeba je sledovat jako majetek společnosti a současně uživatelům umožnit využívat je jako osobní zařízení pro přístup k e-mailům a datům. Doporučené metody registrace závisí na platformě zařízení.

## **Jak se zařízení ve vlastnictví společnosti využívají? Jsou sdílená nebo je využívá vždycky jenom jeden konkrétní uživatel?**

> [!div class="button"] [Sdílená >](#Shared-company-owned-devices)   [Vyhrazená >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Sdílená zařízení ve vlastnictví společnosti

Tato zařízení nemají jenom jednoho konkrétního uživatele a obvykle nejsou nakonfigurovaná pro přístup k e-mailu. O taková zařízení jde například v případě zařízení sloužících jako veřejný terminál nebo v případě zařízení, která si uživatelé vždy pouze vypůjčí na konkrétní úkol. Doporučené metody registrace závisí na platformě zařízení.

  - **Zařízení s Windows a Androidem:** *Správce registrace zařízení* je účet Intune, pomocí kterého je možné registrovat mnoho sdílených zařízení prostřednictvím aplikace Portál společnosti.
  > [!div class="button"]   [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Registrace sdílených zařízení s iOS

Preferovaná metoda registrace pro sdílená zařízení s iOS, která jsou ve vlastnictví společnosti, závisí na tom, jak tato zařízení kupujete a spravujete:

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se s ním.
  - **Apple Configurator na Macu (Mac):** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.
  - **Žádná z výše uvedených možností:** Pokud nemůžete nebo nechcete použít metody registrace DEP nebo Apple Configurator společnosti Apple, použijte Správce registrace zařízení služby Intune.

  **Zvolte:**
    > [!div class="button"]      [Registrace DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Přímá registrace >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

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



<!--HONumber=Jun16_HO2-->


