---
title: Nastavení služby TEM (Telecom Expense Management)
titleSuffix: Microsoft Intune
description: Integrujte službu správy telekomunikačních výdajů Saaswedo do Intune.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 031db83302dfef8b99fc83ab7975e233c3eeb799
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396858"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Nastavení služby TEM (Telecom Expense Management) v Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat výdaje za telekomunikační služby vzniklé v závislosti na používání dat na mobilních zařízeních vlastněných firmou. Pokud chcete tuto funkci aktivovat, má Intune integrované řešení [Datalert pro správu telekomunikačních výdajů](http://datalert.biz/get-started) od externího vývojáře softwaru Saaswedo. Datalert je software pro správu telekomunikačních výdajů v reálném čase, který umožňuje spravovat využití telekomunikačních dat. Pomůže vám vyhnout se nákladným a neočekávaným překročením limitů dat a roamingu u vašich zařízení spravovaných pomocí Intune.

Integrace Intune s Datalertem umožňuje centrálně nastavit, monitorovat a vynutit limity využití roamingu a domácích dat. Automatické výstrahy se zobrazí, když limity překročí definované prahové hodnoty. Službu můžete nakonfigurovat tak, aby se použily různé akce u jednotlivců nebo skupin koncových uživatelů (třeba zákaz roamingu při překročení prahové hodnoty). Sestavy využití a monitorování dat jsou dostupné v konzole pro správu Datalertu.

V následujícím schématu můžete vidět, jak se Intune integruje s řešením Datalert.

  ![Schéma integrace Intune a Datalertu](./media/tem-datalert-intune-solution-diagram.png)

Než budete moct začít používat službu Datalert s Intune, musíte nakonfigurovat nastavení v konzole Datalert a v Intune. Pro službu Datalert a pro Intune musí být připojení zapnuté. Pokud je připojení povolené ve službě Datalert, ale v Intune ne, Intune komunikaci přijme, ale ignoruje ji.

## <a name="supported-platforms"></a>Podporované platformy

- Samsung Knox
- iOS 8.0 a novější

## <a name="prerequisites"></a>Požadavky

- Předplatné Microsoft Intune a přístup na Azure Portal
- Předplatné služby TEM (Telecom Expense Management) Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Seznam poskytovatelů služby TEM (Telecom Expense Management)

Intune aktuálně spolupracuje s následujícími poskytovateli služby TEM (Telecom Expense Management):

[Služba TEM Datalert od Saaswedo](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Nasazení integrovaného řešení Intune a Datalert

Než začnete, musíte mít Intune a předplatné služby TEM Datalert.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Krok 1: Připojte službu Datalert k Microsoft Intune

1. S přihlašovacími údaji správce se přihlaste na konzolu správy Datalert.

2. V konzole pro správu Datalert přejděte na kartu **Settings** (Nastavení) a pak na možnost **MDM configuration** (Konfigurace MDM).

3. Pokud chcete na stránce změnit nastavení, vyberte dole **Unblock** (Odblokovat).

4. V oddílu **Intune / Datalert Connection** (Připojení Intune/Datalert) vyberte jako **Server MDM** možnost **Microsoft Intune**.    

5. V poli **Azure AD domain** (Doména Azure AD) zadejte ID svého tenanta Azure a vyberte **Connection** (Připojení).

    Když vyberete **Connection** (Připojení), zkontroluje služba Datalert, jestli neexistuje nějaké starší připojení této služby k Intune. Po několika sekundách se otevře přihlašovací stránka Microsoft a po ní ověření Azure pro Datalert.

6. Na ověřovací stránce Microsoft vyberte **Přijmout**. Budete přesměrováni na stránku Datalert s **poděkováním**, která se po pár sekundách zavře. Datalert ověří připojení. Vedle ověřených připojení se v seznamu zobrazí zelené zaškrtnutí. Pokud se ověření nezdaří, zobrazí se červená zpráva a měli byste Datalert požádat o pomoc.

    Na následujícím snímku obrazovky vidíte zelené značky zaškrtnutí, které označují úspěšné připojení.

   ![Stránka Datalert zobrazující úspěšné připojení](./media/tem-datalert-connection.png)

7. V oddílu **Datalert App / ADAL Consent** (Souhlas s aplikací Datalert / ADAL) nastavte přepínač na **On** (Zapnuto). Na ověřovací stránce Microsoft vyberte **Přijmout**. Budete přesměrováni na stránku Datalert s **poděkováním**, která se po pár sekundách zavře. Datalert ověří připojení. Vedle ověřených připojení se v seznamu zobrazí zelené zaškrtnutí. Pokud se ověření nezdaří, zobrazí se červená zpráva a měli byste Datalert požádat o pomoc.    

    Na následujícím snímku obrazovky vidíte zelené značky zaškrtnutí, které označují úspěšné připojení.

   ![Stránka Datalert zobrazující úspěšné připojení](./media/tem-datalert-adal-consent.png)

8. V oddílu **MDM Profiles management (optional)** (Správa profilů MDM (volitelná)) nastavte přepínač do polohy **On** (Zapnuto), aby aplikace Datalert mohla číst profily, které jsou dostupné v Intune, a mohla vám pomoci s nastavením zásad. Na ověřovací stránce Microsoft vyberte **Přijmout**. Budete přesměrováni na stránku Datalert s **poděkováním**, která se po pár sekundách zavře. Datalert ověří připojení. Vedle ověřených připojení se v seznamu zobrazí zelené zaškrtnutí. Pokud se ověření nezdaří, zobrazí se červená zpráva a měli byste Datalert požádat o pomoc.    

    Na následujícím snímku obrazovky vidíte zelené značky zaškrtnutí, které označují úspěšné připojení.

   ![Stránka Datalert zobrazující úspěšné připojení](./media/tem-datalert-mdm-profiles.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Krok 2: Zkontrolujte, jestli funkce správy telekomunikačních výdajů je aktivní v Intune

Po dokončení kroku 1 výše by se mělo automaticky povolit připojení a na portálu Azure Portal by se měl zobrazit stav připojení **Aktivní**. V tomto postupu vidíte, jak zkontrolovat stav **Aktivní**.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).

2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.

3. V podokně **Intune** zvolte **Konfigurace zařízení**.

4. V podokně **Konfigurace zařízení** zvolte **Nastavení** > **Služba TEM (Telecom Expense Management)**.

   V horní části stránky se podívejte, jestli je stav připojení **Aktivní**.

   ![Stránka Intune zobrazující aktivní stav připojení Datalertu](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Krok 3: Nasazení aplikace Datalert na podniková zaregistrovaná zařízení

Aby se zajistilo, že se bude zjišťovat využití dat jenom z firemních linek, musíte udělat dvě věci:
- vytvořit kategorie zařízení v Intune
- zacílit aplikaci Datalert jenom na firemní telefony

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Definování kategorií zařízení a skupin zařízení namapovaných do kategorií

V závislosti na potřebách organizace vytvořte aspoň dvě kategorie zařízení (třeba Firemní a Osobní). Pak pro každou kategorii vytvořte dynamické skupiny zařízení. Podle potřeby pro svoji organizaci můžete vytvořit více kategorií.

Tyto kategorie se budou zobrazovat uživatelům při registraci. Podle toho, kterou kategorii uživatelé zvolí, se registrované zařízení přesune do příslušné skupiny zařízení. Postup vytvoření kategorií zařízení najdete v tématu [Mapování zařízení na skupiny](device-group-mapping.md).

  ![Snímek obrazovky s podoknem Přidat zásadu](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Vytvoření aplikace Datalert v Intune

Podle následujících pokynů vytvořte v Intune aplikaci Datalert pro jednotlivé platformy. Jako příklad v tomto postupu použijeme iOS.

1. V podokně **Intune** na portálu [Azure Portal](https://portal.azure.com) zvolte **Klientské aplikace**.

2. V podokně **Klientské aplikace** zvolte **Spravovat** > **Aplikace**.

3. Vyberte **Přidat**, abyste mohli přidat aplikaci.

4. Vyberte typ aplikace. Pro iOS vyberete například **iOS Store App**.

5. V části **Hledat v App Storu** vyhledejte aplikaci Datalert tak, že zadáte v okně hledání **Datalert**.

6. Vyberte aplikaci **Datalert** a **Vybrat**.

   ![Snímek obrazovky s podoknem Přidat zásadu](./media/tem-select-app-from-apple-app-store.png)

7. Pomocí zbývajících kroků v postupu vytvořte aplikaci pro iOS.

   ![Snímek obrazovky s podoknem Přidat zásadu](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Přiřazení aplikace Datalert ke skupině firemních zařízení

1. V podokně **Klientské aplikace – Aplikace** vyberte aplikaci Datalert pro iOS, kterou jste vytvořili v předchozím kroku.

2. V podokně **Aplikace** zvolte **Spravovat** > **Přiřazení**.

3. Zvolte **Přidat skupinu** a postupujte podle pokynů pro výběr skupiny firemních zařízení.

4. Vyberte, jestli chcete, aby byla instalace aplikace pro skupinu povinná nebo volitelná. Na následujícím snímku obrazovky s příkladem vidíte povinnou instalaci, což znamená, že uživatelé musí po registraci svých zařízení aplikaci Datalert nainstalovat.

   ![Snímek obrazovky s podoknem Přidat zásadu](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Krok 4: Přidat placené firemní telefonní linky ke konzole Datalert

Teď máte služby Intune a Datalert nakonfigurované tak, aby spolu komunikovaly. Teď musíte přidat placené firemní telefonní linky ke konzole Datalert a definovat prahové hodnoty a akce pro veškerá porušení použití mobilních nebo roamingových služeb. Placené firemní telefonní linky můžete ke konzole Datalert přidat ručně nebo je přidat automaticky po registraci zařízení v Intune.

Pokud chcete nastavit tyto položky, přejděte na [stránku nastavení služby Datalert pro Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup)) a postupujte podle pokynů v průvodci instalací na kartě **Nastavení**.

  ![Snímek obrazovky s podoknem Přidat zásadu](./media/tem-add-phone-lines-to-datalert-console.png)


Služba Datalert je nyní aktivní. Spustí monitorování využití dat a zakáže mobilní a roamingová data u zařízení, která překročí nakonfigurované limity využití.

## <a name="client-enrollment-experience"></a>Možnosti registrace klienta
K registraci klienta si můžete přečíst tato témata:
-   [Registrace zařízení s iOSem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Registrace zařízení s Androidem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Vypnutí služby Datalert

Zakázání služby Datalert na portálu Azure Portal bude mít za následek toto:

- Všechny akce, které jsou u zařízení použité (z důvodu překročení limitů využití), se zruší.
- Uživatelům se už nebude blokovat přístup k datům a roaming.
- Intune bude stále přijímat signály ze služby, ale bude je ignorovat.

**Vypnutí služby**

1. V podokně **Služba TEM (Telecom Expense Management)** na portálu Azure Portal vyberte **Zakázat**.

2. Vyberte **Uložit**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Zobrazení sestav využití dat a roamingu

Vytváření seznam využití dat je momentálně dostupné jenom v konzole pro správu služby Datalert od Saaswedo.

Pokyny k instalaci aplikace Datalert pro koncové uživatele přidáme zanedlouho.
