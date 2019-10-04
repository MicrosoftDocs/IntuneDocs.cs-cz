---
title: Registrace zařízení s iOS v Intune
titleSuffix: Microsoft Intune
description: Nastavení registrace zařízení se systémem iOS v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c4f3424c0d9712affbbf8ba3929e825b62ce5864
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940315"
---
# <a name="enroll-ios-devices-in-intune"></a>Registrace zařízení s iOS v Intune

Intune umožňuje správu mobilních zařízení (MDM) pro iPady a iPhone, aby uživatelé měli zabezpečený přístup k firemním e-mailům, datům a aplikacím.

Jako správce Intune můžete nastavit registraci pro zařízení s iOS a iPadOS, abyste měli přístup k prostředkům společnosti. Uživatelům můžete umožnit registraci zařízení vlastněných osobně, označované jako registrace vlastního zařízení (BYOD). Můžete také nastavit registraci zařízení vlastněných společností.

## <a name="prerequisites-for-ios-enrollment"></a>Předpoklady pro registraci zařízení se systémem iOS

Předtím, než budete moci povolit zařízení se systémem iOS, proveďte následující kroky:

- Ujistěte [se, že vaše zařízení má nárok na registraci zařízení Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Nastavení Intune](../fundamentals/setup-steps.md) – tyto kroky nastavují infrastrukturu Intune. Konkrétně registrace zařízení vyžaduje, abyste [nastavili autoritu MDM](../fundamentals/mdm-authority-set.md).
- [Získání certifikátu Apple MDM push Certificate](apple-mdm-push-certificate-get.md) – Apple vyžaduje certifikát, který umožňuje správu zařízení s iOS a MacOS.

## <a name="user-owned-ios-and-ipados-devices-byod"></a>Zařízení s iOS a iPadOS vlastněná uživateli (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune, a to jako "Přineste si vlastní zařízení" nebo BYOD. Pro registraci uživatelů existují tři možnosti:
- Zásady ochrany aplikací poskytují nejsvětlejší možnosti BYOD a poskytují správu jenom na úrovni aplikace. Pokud ale chcete zařízení zabezpečit i pomocí šestého složeného kódu PIN, můžete tyto zásady použít spolu s zápisem uživatele.
- Registrace zařízení je to, co si můžete představit jako typické registraci BYOD. Poskytuje správcům široké spektrum možností správy.
- Registrace uživatele je efektivnější proces registrace, který poskytuje správcům podmnožinu možností správy zařízení. Tato funkce je aktuálně ve verzi Preview. 

Po dokončení požadavků a přiřazení uživatelských licencí si uživatelé můžou aplikaci Portál společnosti Intune stáhnout z App Storu a podle pokynů v aplikaci. Portál společnosti prohlášení o zásadách ochrany osobních údajů na zařízeních s iOS můžete přizpůsobit, jak je popsáno v [tématu přizpůsobení prohlášení o ochraně osobních údajů](../apps/company-portal-app.md#privacy-statement-customization)

## <a name="company-owned-ios-devices"></a>Zařízení s iOS vlastněná společností

Pro organizace, které kupují zařízení pro své uživatele, podporuje Intune následující metody registrace zařízení vlastněných společností iOS:

- Program Apple Program registrace zařízení (DEP)
- Apple School Manager
- Registrace Pomocníka s nastavením Apple Configuratoru
- Přímá registrace Apple Configuratoru

Zařízení s iOS vlastněná společností můžete také zaregistrovat pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) .

## <a name="device-enrollment-program"></a>Program registrace zařízení

Organizace můžou zařízení s iOS koupit prostřednictvím Program registrace zařízení (DEP) společnosti Apple. DEP umožňuje nasadit registrační profil přes Air, aby se zařízení mohla spravovat. Další informace najdete v tématu [program registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="user-enrollment"></a>Zápis uživatele
Registrace uživatele umožňuje správcům podmnožinu možností správy ve srovnání s jinými metodami registrace. Další informace najdete v tématech [podporované akce při registraci uživatelů, hesla a další možnosti](ios-user-enrollment-supported-actions.md) a [Nastavení registrace uživatele pro iOS a iPadOS](ios-user-enrollment.md).

## <a name="apple-school-manager"></a>Apple School Manager

Apple School Manager je program pro nákup a registraci zařízení pro školy. Podobně jako u programu DEP můžete nasadit profil pro registraci zařízení v rámci správy. Přečtěte si další informace o [Apple School Manageru](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configuratoru

Můžete zaregistrovat zařízení s iOS pomocí Apple Configuratoru spuštěného na počítači Mac. K přípravě zařízení je připojíte přes USB a nainstalujete registrační profil. Pomocí Apple Configuratoru můžete zaregistrovat zařízení dvěma způsoby:

- Registrace Pomocníka s nastavením – vymaže zařízení, připraví ho ke spuštění pomocníka s nastavením a nainstaluje zásady společnosti pro nového uživatele zařízení.
- Přímá registrace – nevymaže zařízení a zaregistruje zařízení s předdefinovanými zásadami. Tato metoda je určena pro zařízení bez přidružení uživatele.

Přečtěte si další informace o [registraci Apple Configuratoru](apple-configurator-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Použití Portál společnosti na zařízeních zaregistrovaných pomocí programu DEP nebo Apple Configuratoru

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti pro stahování aplikací a správu zařízení. Jakmile uživatelé dostanou svá zařízení, musí provést několik dalších kroků, aby dokončili Průvodce nastavením a nainstalovali aplikaci Portál společnosti.

Přidružení uživatele se vyžaduje pro podporu následujících akcí:

- Aplikace pro správu mobilních aplikací (MAM)
- Podmíněný přístup k e-mailu a datům společnosti
- Aplikace Portál společnosti

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Jak uživatelé registrují zařízení s iOS vlastněná společností s přidružením uživatele

1. Když uživatel zapne zařízení, zobrazí se výzva k dokončení pomocníka s nastavením.
2. Po dokončení instalace se uživatelům zobrazí výzva k zadání Apple ID. Aby bylo možné zařízení nainstalovat Portál společnosti, musí zadat Apple ID.
3. Zařízení se systémem iOS automaticky nainstaluje aplikaci Portál společnosti z App Storu.
4. Uživatelé by měli spustit aplikaci Portál společnosti a přihlásit se pomocí přihlašovacích údajů (jako je jedinečné osobní jméno nebo hlavní název uživatele (UPN)), které jsou přidružené k předplatnému v Intune.
5. Po přihlášení se registrace dokončí. Uživatelé teď můžou toto zařízení používat s úplnou sadou funkcí.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>O spravovaných zařízeních vlastněných společností bez přidružení uživatele

Zařízení nakonfigurovaná bez přidružení uživatele nepodporují Portál společnosti a nemají aplikaci nainstalovanou. Portál společnosti je navržený pro uživatele, kteří mají firemní přihlašovací údaje a vyžadují přístup k individuálním podnikovým prostředkům (třeba e-mailem). Zařízení zaregistrovaná bez přidružení uživatele nemají za cíl přihlašovat se vyhrazeným uživatelem. Pro zařízení, která jsou zaregistrovaná bez přidružení uživatele, jsou typické případy použití veřejného terminálu, zařízení v místě prodeje (POS) nebo sdílených nástrojů.

Pokud je potřeba přidružení uživatele, před registrací zařízení se ujistěte, že je pro registrační profil zařízení vybraná možnost **přidružení uživatele** . Pokud chcete změnit stav spřažení na zařízení, musíte zařízení vyřadit a znovu zaregistrovat.

## <a name="see-also"></a>Viz také:

[Řešení potíží s registrací zařízení s iOS v Microsoft Intune](https://support.microsoft.com/help/4039809)
