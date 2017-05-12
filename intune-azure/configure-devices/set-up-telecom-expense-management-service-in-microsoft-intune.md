---
title: "Nastavení služby TEM (Telecom Expense Management)"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Nakonfigurujte službu TEM Saaswedo pro integraci s Intune."
keywords: Saaswedo
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: e0f40d21412e261d31a0a492c260a6097d4dd007
ms.contentlocale: cs-cz
ms.lasthandoff: 05/10/2017

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Nastavení služby TEM (Telecom Expense Management) v Intune Azure Preview
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune umožňuje spravovat výdaje za telekomunikační služby vzniklé v závislosti na používání dat na mobilních zařízeních vlastněných firmou. Pokud chcete aktivovat tuto funkci, obsahuje Intune integrované řešení pro správu výdajů na telekomunikaci Datalert od externího vývojáře softwaru Saaswedo. Datalert je software pro správu výdajů na telekomunikaci v reálném čase, který umožňuje spravovat využití telekomunikačních dat a předejít tak finančně nákladnému a neočekávanému nadlimitnímu využití dat a roamingu u zařízení spravovaných pomocí Intune.

Integrace Intune s Datalertem umožňuje centrálně nastavit, monitorovat a vynutit limity využití roamingu a domácích dat pomocí automatických výstrah, které se zobrazí, když limity překročí definované prahové hodnoty. Službu můžete nakonfigurovat tak, aby se použily různé akce u jednotlivců nebo skupin koncových uživatelů, včetně zákazu roamingu v případě, že uživatelé překročí stanovenou prahovou hodnotu. Sestavy využití a monitorování dat jsou dostupné v konzole pro správu Datalertu.

V následujícím schématu můžete vidět, jak se Intune integruje s řešením Datalert.

  ![Schéma integrace Intune a Datalertu](../media/tem-datalert-intune-solution-diagram.png)

Než budete moct začít používat službu Datalert s Intune, musíte nakonfigurovat nastavení v konzole Datalert a v Intune. Pro službu Datalert a pro Intune musí být připojení zapnuté. Pokud je připojení povolené ve službě Datalert, ale v Intune ne, Intune komunikaci přijme, ale ignoruje ji.

## <a name="supported-platforms"></a>Podporované platformy

- Samsung Knox
- iOS 8.0 a novější

## <a name="prerequisites"></a>Požadavky

- Předplatné Microsoft Intune a přístup k portálu Azure Portal, který je aktuálně ve veřejné verzi preview.
- Předplatné služby TEM (Telecom Expense Management) Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Seznam poskytovatelů služby TEM (Telecom Expense Management)

Intune aktuálně spolupracuje s následujícími poskytovateli služby TEM (Telecom Expense Management):

[Služba TEM Datalert od Saaswedo](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Nasazení integrovaného řešení Intune a Datalert

Než začnete, musíte mít Intune a předplatné služby TEM Datalert.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Krok 1: Připojte službu Datalert k Microsoft Intune

1. S přihlašovacími údaji správce se přihlaste na konzolu správy Datalert.

2. V konzole pro správu Datalert přejděte na kartu **Settings** (Nastavení) a pak na možnost **MDM configuration** (Konfigurace MDM).

3. Vyberte **Unblock** (Zrušit blokování), abyste na stránce mohli zadat nastavení.

4. U položky **Server MDM** zvolte **Microsoft Intune**.

5. Pro **Azure AD domain** (Doména Azure), zadejte svoje ID tenanta Azure a pak vyberte tlačítko **Connection** (Připojení).

    Když vyberete možnost **Připojení**, služba Datalert zkontroluje v Intune, že dosud neexistuje žádné připojení Datalert v Intune. Po několika sekundách se otevře přihlašovací stránka Microsoft a po ní ověření Azure pro Datalert.

6. Na ověřovací stránce Microsoft vyberte **Přijmout**. Budete přesměrováni na stránku Datalert s poděkováním, která se po pár sekundách zavře. Datalert ověří připojení a zobrazí zelenou značku zaškrtnutí vedle seznamu ověřených položek. Pokud se ověření nezdaří, zobrazí se zpráva zvýrazněná červeně. Pokud k tomu dojde, obraťte se na podporu Datalertu se žádostí o pomoc.

    Na následujícím snímku obrazovky vidíte zelené značky zaškrtnutí, které označují úspěšné připojení.

  ![Stránka Datalert zobrazující úspěšné připojení](../media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Krok 2: Zkontrolujte v Intune, že je aktivní funkce správy výdajů na telekomunikaci

Po dokončení kroku 1 výše by se mělo automaticky povolit připojení a na portálu Azure Portal by se měl zobrazit stav připojení **Aktivní**. V tomto postupu vidíte, jak zkontrolovat stav **Aktivní**.

1. Přihlaste se k portálu Azure Portal.

2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.

3. V okně **Intune** zvolte **Konfigurace zařízení**.

4. V okně **Konfigurace zařízení** zvolte **Nastavení** > **Služba TEM (Telecom Expense Management)**.

   V horní části stránky se podívejte, jestli je stav připojení **Aktivní**.

  ![Azure Portal se zobrazeným aktivním stavem připojení Datalertu](../media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Krok 3: Nasazení aplikace Datalert na podniková zaregistrovaná zařízení

Aby se shromažďovaly informace jenom o použití dat na linkách vlastněných firmou, je potřeba vytvořit v Intune kategorie zařízení a potom aplikaci Datalert zacílit jenom na podnikové telefony. Postupujte podle pokynů v následujících oddílech.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Definování kategorií zařízení a skupin zařízení namapovaných do kategorií

V závislosti na potřebách organizace budete muset vytvořit alespoň dvě kategorie zařízení (například podniková a osobní) a pro každou kategorii vytvořit dynamické skupiny zařízení. Podle potřeby pro svoji organizaci můžete vytvořit více kategorií.

Tyto kategorie se budou zobrazovat uživatelům při registraci. Podle toho, kterou kategorii uživatelé zvolí, se registrované zařízení přesune do příslušné skupiny zařízení. Postup vytvoření kategorií zařízení najdete v tématu [Mapování zařízení na skupiny](../enroll-devices/how-to-use-device-group-mapping.md).

  ![Snímek obrazovky okna Přidat zásadu](../media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Vytvoření aplikace Datalert v Intune

Podle následujících pokynů vytvořte v Intune aplikaci Datalert pro jednotlivé platformy. Jako příklad v tomto postupu použijeme iOS.

1. V okně **Intune** na portálu Azure Portal zvolte **Spravovat aplikace**.

2. V okně **Spravovat aplikace** zvolte **Spravovat** > **aplikace**.

3. Vyberte **Přidat**, abyste mohli přidat aplikaci.

4. Vyberte typ aplikace. Pro iOS vyberete například **iOS Store App**.

5. V části **Hledat v App Storu** vyhledejte aplikaci Datalert tak, že zadáte v okně hledání **Datalert**.

6. Vyberte aplikaci **Datalert** a **OK**.

  ![Snímek obrazovky okna Přidat zásadu](../media/tem-select-app-from-apple-app-store.png)

7. Pomocí zbývajících kroků v postupu vytvořte aplikaci pro iOS.

  ![Snímek obrazovky okna Přidat zásadu](../media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Přiřazení aplikace Datalert ke skupině firemních zařízení

1. Vyberte aplikaci Datalert pro iOS, kterou jste vytvořili v předchozím kroku.

2. V okně **Aplikace** přejděte na **Správa** > **Přiřazení**.

3. Zvolte **Vybrat skupiny** a postupujte podle pokynů pro výběr skupiny firemních zařízení.

4. Vyberte, jestli chcete, aby byla instalace aplikace pro skupinu povinná nebo volitelná. Na následujícím snímku obrazovky s příkladem vidíte povinnou instalaci, což znamená, že uživatelé musí po registraci svých zařízení aplikaci Datalert nainstalovat.

  ![Snímek obrazovky okna Přidat zásadu](../media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Krok 4: Přidejte do konzoly Datalert placené firemní telefonní linky

Teď máte služby Intune a Datalert nakonfigurované tak, aby spolu komunikovaly. Teď musíte přidat placené firemní telefonní linky ke konzole Datalert a definovat prahové hodnoty a akce pro veškerá porušení použití mobilních nebo roamingových služeb. Placené firemní telefonní linky můžete ke konzole Datalert přidat buď ručně, nebo je nechat přidat automaticky po registraci zařízení v Intune.

Pokud chcete nastavit tyto položky, přejděte na [stránku nastavení služby Datalert pro Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup) a postupujte podle pokynů v průvodci instalací na kartě **Nastavení**.

  ![Snímek obrazovky okna Přidat zásadu](../media/tem-add-phone-lines-to-datalert-console.png)


Služba Datalert je nyní aktivní. Spustí monitorování využití dat a zakáže mobilní a roamingová data u zařízení, která překročí nakonfigurované limity využití.

## <a name="client-enrollment-experience"></a>Možnosti registrace klienta
Při registraci klienta se zobrazí tyto možnosti:
-    [Registrace zařízení s iOSem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-    [Registrace zařízení s Androidem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Vypnutí služby Datalert

Zakázání služby Datalert na portálu Azure Portal bude mít za následek toto:

- Všechny akce, které jsou u zařízení použité (z důvodu překročení limitů využití), se zruší.
- Uživatelům se už nebude blokovat přístup k datům a roaming.
- Intune bude stále přijímat signály ze služby, ale bude je ignorovat.

**Vypnutí služby**

1. V okně **Služba TEM (Telecom Expense Management)** na portálu Azure Portal vyberte **Zakázat**.

2. Vyberte **Uložit**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Zobrazení sestav využití dat a roamingu

Vytváření seznam využití dat je momentálně dostupné jenom v konzole pro správu služby Datalert od Saaswedo.

Pokyny k instalaci aplikace Datalert pro koncové uživatele přidáme zanedlouho.

