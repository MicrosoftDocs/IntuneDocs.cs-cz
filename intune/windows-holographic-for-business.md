---
title: Správa zařízení s Windows Holographic v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete plnit různé úkoly spojené se zařízeními se systémem Windows Holographic for Business, jako je konfigurace Portálu společnosti, vytvoření zásady dodržování předpisů, přizpůsobení nastavení OMA-URI, nasazení aplikací, zařazení zařízení do skupin, vytváření profilů, omezení zařízení, povolení aktualizací softwaru, nastavení podmínek a ujednání, konfigurace nastavení VPN a Wi-Fi a použití funkce Hello pro firmy.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41c1ea3bf12b83a0f09c8535275ffb58e5f46931
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Přizpůsobení zařízení s Windows Holographic v Intune

Microsoft Intune podporuje zařízení s Windows Holographic for Business, jako je například [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Pokud chcete v Microsoft Intune spravovat zařízení, na kterých běží Windows Holographic, musíte vytvořit profil Upgrade edice. Tento aktualizační profil upgraduje zařízení z Windows Holographic na Windows Holographic for Business. V případě zařízení Microsoft HoloLens můžete požadovanou licenci pro upgrade získat zakoupením edice Commercial Suite. Další informace najdete v tématu [Upgrade zařízení s Windows Holographic na Windows Holographic for Business](holographic-upgrade.md).

Ke správě a přizpůsobení zařízení s Windows Holographic for Business použijte úkoly popsané v tomto článku. Můžete například spravovat softwarové aktualizace, konfigurovat nastavení VPN a provádět další úkoly.

## <a name="company-portal"></a>Portál společnosti
**[Konfigurace aplikace Portál společnosti](company-portal-app.md)**

Součástí Intune je Portál společnosti, kde mají uživatelé přístup k firemním datům, registrují zařízení, instalují aplikace, mohou kontaktovat oddělení IT apod. Aplikaci Portál společnosti můžete přizpůsobit pro zařízení s Windows Holographic for Business.

## <a name="compliance-policy"></a>zásady dodržování předpisů
**[Vytvoření zásady dodržování předpisů pro zařízení](compliance-policy-create-windows.md)**

Zásady dodržování předpisů jsou pravidla a nastavení, která musí zařízení dodržovat, aby vyhovovala. Pomocí zásad podmíněného přístupu můžete nevyhovujícím zařízením zablokovat přístup k prostředkům společnosti. V Intune můžete vytvářet zásady dodržování předpisů, které povolí nebo zablokují přístup zařízením s Windows Holographic for Business. Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.

Další informace najdete v tématu **[Začínáme se zásadami dodržování předpisů](device-compliance-get-started.md)**.

## <a name="deploy-apps"></a>Nasazení aplikací
**[Přidání aplikací do Intune](apps-add.md)**

V Intune můžete do zařízení s Windows Holographic for Business přidat aplikace. Existují různé způsoby nasazování aplikací:

- [Přidání aplikací z Microsoft Storu](store-apps-windows.md)
- [Přidání vytvořených aplikací](lob-apps-windows.md)
- [Přiřazení aplikací skupinám](apps-deploy.md)

## <a name="device-categories-and-groups"></a>Kategorie a skupiny zařízení
**[Zařazení zařízení do skupin](device-group-mapping.md)**

V Intune můžete vytvářet kategorie zařízení, abyste podle nich mohli zařízení automaticky přidávat do skupin. Příklad: Prodej, Účetnictví, Lidské zdroje apod. Cílem je usnadnit správu zařízení s Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Konfigurační profily zařízení 
**[Začínáme s konfiguračními profily](device-profiles.md) a [vytvoření vlastního profilu](device-profile-create.md)**

Intune obsahuje nastavení a funkce, které můžete různým zařízením v organizaci povolit nebo zakázat. Tato nastavení a funkce se spravují pomocí profilů. Můžete třeba vytvořit profil, který povolí Cortanu nebo na zařízeních s Windows Holographic for Business používá filtr SmartScreen programu Windows Defender.

V profilech můžete k přizpůsobení některých nastavení, vytvoření omezení pro zařízení a konfiguraci sítí VPN a Wi-Fi použít OMA-URI.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Vlastní nastavení zařízení](custom-settings-windows-holographic.md)

Pokud chcete nakonfigurovat nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), můžete v Intune vytvořit vlastní profil. Nastavení OMA-URI se používá k ovládání různých funkcí zařízení s Windows Holographic for Business, jako je povolení VPN nebo kontrola aktualizací ve službě Microsoft Update.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Omezení zařízení](device-restrictions-windows-holographic.md)

Omezení zařízení umožňují ovládat různá nastavení a funkce zařízení, jako je povinné heslo, instalace aplikací z [Microsoft Storu](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), zapnutí technologie Bluetooth atd. Tato omezení se vytvářejí v profilu Intune. Profil můžete použít u více zařízení, na kterých běží Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Konfigurace VPN](vpn-settings-configure.md)

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. V Intune můžete vytvořit profil VPN, ve kterém budou mít zařízení s Windows Holographic for Business určité nastavení. Můžete třeba vytvořit profil VPN, kde budou mít všechna zařízení s Windows Holographic for Business typ připojení Citrix VPN.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Konfigurace Wi-Fi](wi-fi-settings-configure.md)

V Intune můžete také vytvořit profil Wi-Fi, kterým zařízením s Windows Holographic for Business přiřadíte nastavení bezdrátové sítě. Když zařízení přiřadíte profil Wi-Fi, získají koncoví uživatelé přístup k firemní síti bez konfigurace. Můžete třeba vytvořit síť Wi-Fi určenou jenom zařízením s Windows Holographic for Business.

## <a name="software-updates"></a>Aktualizace softwaru
**[Správa softwarových aktualizací](windows-update-for-business-configure.md)**

V Intune je funkce Aktualizační kanály zařízení s Windows 10. Tyto aktualizační kanály zahrnují skupinu nastavení, která určují, jak se budou aktualizace instalovat. Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat. Aktualizační kanál můžete použít pro více zařízení s Windows Holographic for Business.

## <a name="terms-and-conditions"></a>podmínky a ujednání
**[Nastavení podmínek a ujednání společnosti pro přístup uživatelů](terms-and-conditions-create.md)**

Před registrací zařízení a získáním přístupu k firemním aplikacím (včetně e-mailu) můžete vyžadovat, aby uživatelé přijali podmínky a ujednání společnosti. V Intune můžete definovat, jak se podmínky a ujednání zobrazí v aplikaci Portál společnosti, a také můžete tyto podmínky a ujednání přiřadit zařízením s Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy
**[Použití Windows Hello pro firmy](windows-hello.md)**

Hello pro firmy je alternativní přihlašovací metoda, která k nahrazení hesla, čipové karty nebo virtuální čipové karty používá účet Azure Active Directory. Hello pro firmy umožňuje zařízením s Windows Holographic for Business používat k přihlášení PIN o minimální délce, kterou sami určíte.
