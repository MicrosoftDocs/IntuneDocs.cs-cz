---
title: "Registrace zařízení s iOSem vlastněných společností | Dokumentace Microsoftu"
description: "Registrace zařízení s iOSem vlastněných společností pomocí Programu registrace zařízení Apple (DEP) nebo nástroje Apple Configurator"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2ed76d2905042f299022f1625ce7215c6834ad3f
ms.openlocfilehash: 7fcb910dfc566cdf7112a48558cda375ea1c39a8
ms.lasthandoff: 02/21/2017


---

# <a name="enroll-corporate-owned-ios-devices-in-microsoft-intune"></a>Registrace zařízení s iOSem vlastněných společností v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune podporuje registraci firemních zařízení s iOSem prostřednictvím Programu registrace zařízení Apple nebo pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) na počítači Mac.

**Předpoklad:** [Certifikát Apple Push Notification Service](set-up-ios-and-mac-management-with-microsoft-intune.md)

Při registraci zařízení s iOSem registrovaných podnikem můžete použít jeden ze tří způsobů:

- Apple Configurator s použitím pomocníka nastavením (Setup Assistant) nebo přímé registrace
- Program registrace zařízení
- Aplikace Portál společnosti

>[!NOTE]
>Způsoby registrace Apple Configurator a Program registrace zařízení nejdou použít u metody [registrace zařízení pomocí správce registrace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

Ve výchozím nastavení se můžou zaregistrovat v Intune všechna zařízení s iOSem. Pokud chcete zablokovat možnost registrace u osobních zařízení nebo zařízení vlastněných podnikem, přihlaste se pomocí přihlašovacích údajů správce na [portál pro správu Microsoft Intune](http://manage.microsoft.com). Zvolte možnost **správy** > **Správa mobilního zařízení** > **Pravidla registrace** a zrušte zaškrtnutí příslušných políček.

## <a name="use-apple-configurator"></a>Použití nástroje Apple Configurator

Zařízení s iOSem můžete registrovat exportováním podnikového registračního profilu a následným připojením těchto mobilních zařízení k počítači Mac, na které běží nástroj Apple Configurator. Apple Configurator podporuje dva způsoby registrace:

- **Registrace pomocí Pomocníka s nastavením:** Obnoví tovární nastavení a připraví zařízení k nastavení jeho novým uživatelem. Tato metoda vyžaduje, aby správce pomocí USB připojil zařízení s iOSem k počítači Mac, na kterém je spuštěný nástroj [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), a předkonfiguroval registraci. Zařízení se pak doručí jejich uživatelům, kteří spustí proces Pomocníka s nastavením. Tento proces v zařízení nakonfiguruje pracovní nebo školní přihlašovací údaje a dokončí proces registrace. Další informace najdete v článku [Registrace zařízení s iOSem pomocí nástroje Apple Configurator a Pomocníka s nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md).

- **Přímá registrace**: Vytvoří soubor kompatibilní s nástrojem Apple Configurator, který můžete použít při přípravě zařízení. Zaregistrovanému zařízení není obnoveno tovární nastavení, nemá ale žádného přiřazeného uživatele. Tato metoda vyžaduje, aby správce pomocí USB připojil zařízení s iOSem k počítači Mac, na kterém je spuštěný nástroj [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), a zaregistroval zařízení. Další informace najdete v článku [Registrace zařízení s iOSem pomocí přímé registrace nástroje Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md).

## <a name="use-the-device-enrollment-program-dep"></a>Použití Programu registrace zařízení (DEP)
DEP nasazuje registrační profil bezdrátově do zařízení, která jste prostřednictvím tohoto programu nakoupili. Když uživatel na zařízení spustí Pomocníka s nastavením, zařízení se zaregistruje do Intune. Další informace najdete v článku [Registrace zařízení s iOSem pomocí Programu registrace zařízení](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Použití služby Portálu společnosti v zařízeních zaregistrovaných pomocí Programu registrace zařízení nebo nástroje Apple Configurator

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé obdrží zařízení, musí provést určitý počet dodatečných kroků, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

Přidružení uživatele je nezbytné pro podporu následujících funkcí:
  - Aplikace MAM (správa mobilních aplikací)
  -    Podmíněný přístup k e-mailu a firemním datům
  -    Aplikace Portál společnosti

**Postup registrace zařízení s iOSem vlastněných společností s přidružením uživatele**
1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. Během nastavování se uživateli zobrazí výzva k zadání přihlašovacích údajů. Uživatel musí použít přihlašovací údaje (tj. jedinečné osobní jméno nebo hlavní název uživatele) přidružené k jeho předplatnému Intune.

2. Během nastavování se uživateli zobrazí výzva k zadání Apple ID. Aby mohlo zařízení nainstalovat aplikaci Portál společnosti, musí uživatel zadat Apple ID. Po dokončení nastavení můžou ID zadat i z nabídky nastavení iOSu.

3. Po dokončení nastavení musí zařízení s iOSem nainstalovat aplikaci Portál společnosti z App Storu.

4. Uživatel se teď může přihlásit ke službě Portál společnosti pomocí hlavního názvu uživatele, který použil při nastavování zařízení.

5. Po přihlášení se uživateli zobrazí výzva k registraci zařízení. Prvním krokem je identifikace zařízení. Aplikace zobrazí seznam zařízení s iOSem, která jsou už ve společnosti registrovaná a mají přiřazený účet Intune uživatele. Uživatel by měl vybrat odpovídající zařízení.

  Pokud zařízení ještě není ve společnosti zaregistrované, uživatel by měl vybrat **Nové zařízení** a pokračovat standardním postupem registrace.

6. Na další obrazovce musí uživatel potvrdit sériové číslo nového zařízení. Uživatel může klepnout na odkaz **Potvrdit sériové číslo**. Tím se spustí aplikace Nastavení, která sériové číslo ověří. Potom musí uživatel zadat poslední čtyři znaky sériového čísla do aplikace Portál společnosti.

  Tento krok ověřuje, jestli se jedná o firemní zařízení zaregistrované v Intune. Pokud sériové číslo zařízení neodpovídá, znamená to, že došlo k výběru nesprávného zařízení. Uživatel se musí vrátit na předchozí obrazovku a vybrat jiné zařízení.

7. Po ověření sériového čísla aplikace Portál společnosti přesměruje uživatele na web Portál společnosti, kde registraci dokončí. Potom web uživatele vyzve, aby se vrátil do aplikace.

8. Registrace je u konce. Uživatel teď může zařízení používat s úplnou sadou funkcí.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>O firemních spravovaných zařízeních bez přidružení uživatele

Zařízení nakonfigurovaná bez přidružení uživatele nepodporují aplikaci Portál společnosti a ta by se na ně neměla instalovat. Portál společnosti je určený pro uživatele, kteří mají firemní přihlašovací údaje a potřebují přístup k podnikovým prostředkům podle svých potřeb (třeba k e-mailu). Zařízení zaregistrovaná bez přidružení uživatele nejsou určená k tomu, aby se k nim přihlašoval jeden vyhrazený uživatel. Typickými případy použití zařízení zaregistrovaných bez přidružení uživatele jsou zařízení veřejných terminálů, pokladny nebo sdílená zařízení.

Pokud je požadováno přidružení uživatele, před registrací zařízení zkontrolujte, jestli je u registračního profilu daného zařízení vybraná možnost **Přidružení uživatele**. Pokud chcete stav přidružení zařízení změnit, musíte zařízení nejdřív vyřadit a potom ho znovu zaregistrovat.



### <a name="see-also"></a>Viz taky
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)

