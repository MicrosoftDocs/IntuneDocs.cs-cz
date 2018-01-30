---
title: "Volba způsobu registrace zařízení s Windows v Intune"
titlesuffix: Azure portal
description: "Přečtěte si, jak nastavit registraci zařízení s Windows v Microsoft Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f36e579282f7aeaec74c3e80d866e52dfa508d3d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-ios-devices-in-intune"></a>Registrace zařízení s iOSem v Intune

Intune umožňuje správu mobilních zařízení (MDM) u iPadů a iPhonů, aby mohli jejich uživatelé získat přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete povolit registraci zařízení s iOSem. Můžete uživatelům povolit registraci osobních zařízení, která se označuje jako registrace BYOD (přineste si vlastní zařízení). Můžete povolit také registraci zařízení vlastněných firmou.

## <a name="prerequisites-for-ios-enrollment"></a>Předpoklady pro registraci zařízení s iOSem
Před povolením zařízení s iOSem proveďte následující kroky:
- [Nastavení Intune](setup-steps.md) – tento postup slouží k nastavení infrastruktury Intune. Registrace zařízení vyžaduje zejména [nastavení autority MDM](mdm-authority-set.md).
- [Získání certifikátu Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) – Apple vyžaduje k povolení správy zařízení s iOSem a macOS certifikát.

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení uživatelských licencí si uživatelé budou moct stáhnout aplikaci Portál společnosti pro iOS z App Storu a podle pokynů v aplikaci si zařízení zaregistrovat.

## <a name="company-owned-ios-devices"></a>Zařízení s iOSem patřící společnosti
U organizací, které svým uživatelům zařízení pořizují, Intune podporuje následující způsoby registrace zařízení s iOSem patřící společnosti:

- Program registrace zařízení (DEP) společnosti Apple
- Apple School Manager
- Registrace Průvodce nastavením s Apple Configuratorem
- Přímá registrace pomocí Apple Configuratoru

Zařízení s iOSem, která patří společnosti, můžete také zaregistrovat pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Program DEP (Device Enrollment Program)
Organizace můžou nakupovat zařízení s iOSem prostřednictvím Programu registrace zařízení (DEP) společnosti Apple. Program DEP umožňuje vzdáleně (bezdrátově) nasadit registrační profil, který umožní správu těchto zařízení. Přečtěte si další informace o [Programu registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager je program nákupu a registrace zařízení pro školy. Stejně jako u programu DEP máte možnost nasadit profil pro registraci zařízení pro účely správy. Další informace o [Apple School Manageru](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Zařízení s iOSem můžete zaregistrovat pomocí nástroje Apple Configurator spuštěného na počítači Mac. Zařízení připravíte tak, že je připojíte přes USB a nainstalujete registrační profil. Zařízení můžete pomocí Apple Configuratoru registrovat dvěma způsoby:
- Registrace pomocí Pomocníka s nastavením – obnoví tovární nastavení zařízení a připraví ho ke spuštění Pomocníka s nastavením a nainstaluje zásady společnosti pro nového uživatele zařízení.
- Přímá registrace – neobnoví tovární nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tato metoda je vhodná pro zařízení bez přidružení uživatele.

Přečtěte si další informace o [registraci pomocí Apple Configuratoru](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Použití služby Portálu společnosti v zařízeních zaregistrovaných pomocí Programu registrace zařízení nebo nástroje Apple Configurator

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé obdrží zařízení, musí provést určitý počet dodatečných kroků, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

Přidružení uživatele je nezbytné pro podporu následujících funkcí:
  - Aplikace MAM (správa mobilních aplikací)
  - Podmíněný přístup k e-mailu a firemním datům
  - Aplikace Portál společnosti

**Postup registrace zařízení s iOSem vlastněných společností s přidružením uživatele**
1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. Během nastavování se uživateli zobrazí výzva k zadání přihlašovacích údajů. Uživatel musí použít přihlašovací údaje (tj. jedinečné osobní jméno nebo hlavní název uživatele) přidružené k jeho předplatnému Intune.

2. Během nastavování se uživateli zobrazí výzva k zadání Apple ID. Aby mohlo zařízení nainstalovat aplikaci Portál společnosti, musí uživatel zadat Apple ID. Po dokončení nastavení můžou ID zadat i z nabídky nastavení iOS.

3. Po dokončení nastavení musí zařízení s iOSem nainstalovat aplikaci Portál společnosti z App Storu.

4. Uživatel se teď může přihlásit ke službě Portál společnosti pomocí hlavního názvu uživatele, který použil při nastavování zařízení.

5. Po přihlášení se uživateli zobrazí výzva k registraci zařízení. Prvním krokem je identifikace zařízení. Aplikace zobrazí seznam zařízení s iOS, která jsou už ve společnosti registrovaná a mají přiřazený účet Intune uživatele. Uživatel by měl vybrat odpovídající zařízení.

  Pokud zařízení ještě není ve společnosti zaregistrované, uživatel by měl vybrat **Nové zařízení** a pokračovat standardním postupem registrace.

6. Na další obrazovce musí uživatel potvrdit sériové číslo nového zařízení. Uživatel může klepnout na odkaz pro **potvrzení sériového čísla** a spustit tak pokyny pro aplikaci Nastavení, která sériové číslo ověří. Potom musí uživatel zadat poslední čtyři znaky sériového čísla do aplikace Portál společnosti.

  Tento krok ověřuje, jestli se jedná o firemní zařízení zaregistrované v Intune. Pokud sériové číslo zařízení neodpovídá, znamená to, že došlo k výběru nesprávného zařízení. Uživatel se musí vrátit na předchozí obrazovku a vybrat jiné zařízení.

7. Po ověření sériového čísla aplikace Portál společnosti přesměruje uživatele na web Portál společnosti, kde registraci dokončí. Potom web uživatele vyzve, aby se vrátil do aplikace.

8. Registrace je u konce. Uživatel teď může zařízení používat s úplnou sadou funkcí.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>O firemních spravovaných zařízeních bez přidružení uživatele

Zařízení nakonfigurovaná bez přidružení uživatele nepodporují aplikaci Portál společnosti a ta by se na ně neměla instalovat. Portál společnosti je určený pro uživatele, kteří mají firemní přihlašovací údaje a potřebují přístup k podnikovým prostředkům podle svých potřeb (třeba k e-mailu). Zařízení zaregistrovaná bez přidružení uživatele nejsou určená k tomu, aby se k nim přihlašoval jeden vyhrazený uživatel. Typickými případy použití zařízení zaregistrovaných bez přidružení uživatele jsou zařízení veřejných terminálů, pokladny nebo sdílená zařízení.

Pokud je požadováno přidružení uživatele, před registrací zařízení zkontrolujte, jestli je u registračního profilu daného zařízení vybraná možnost **Přidružení uživatele**. Pokud chcete stav přidružení zařízení změnit, musíte zařízení nejdřív vyřadit a potom ho znovu zaregistrovat.

