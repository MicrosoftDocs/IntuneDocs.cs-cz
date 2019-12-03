---
title: Nastavení služby pro správu telekomunikačních výdajů v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Integrujte Microsoft Intune se službou Saaswedo Telecom výdaje za sledování využití dat a nastavení prahových hodnot nebo omezení na zařízeních s Androidem a iOS.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 340659adfa3bbd40f98ccec9d8d44e952f7ec9b9
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059928"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Nastavení služby TEM (Telecom Expense Management) v Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Pomocí Intune můžete spravovat telekomunikační výdaje ze využívání dat na mobilních zařízeních vlastněných organizací. Intune se integruje se [správou telekomunikačních výdajů Datalert](http://datalert.biz/get-started)v Saaswedo. Datalert je řešení pro správu telekomunikačních výdajů v reálném čase, které spravuje využití telekomunikačních dat. Může vám to zabránit nákladným a neočekávaným datům a poplatkům za roaming pro vaše zařízení spravovaná pomocí Intune.

Integrace s Datalert může nastavovat, monitorovat a vymáhat limity využití roamingu a domácích dat. Když limity překročí definované prahové hodnoty, výstrahy se automaticky aktivují. Službu můžete také nakonfigurovat tak, aby se nakonfigurovali různé akce, jako je například zákaz roamingu nebo překročení prahové hodnoty jednotlivcům nebo skupinám. Konzola pro správu Datalert obsahuje sestavy, které zobrazují informace o využití a monitorování dat.

Následující obrázek ukazuje, jak se Intune integruje s Datalert:

  ![Schéma integrace Intune a Datalertu](./media/telecom-expenses-monitor/tem-datalert-intune-solution-diagram.png)

Pokud chcete používat službu Datalert s Intune, je k dispozici několik nastavení konfigurace v Datalert a Intune. V tomto článku se dozvíte, jak:

- Nakonfigurujte nastavení v konzole Datalert, aby se služba Datalert připojila k Intune.
- Ověřte, jestli je toto připojení aktivní a povolené v Intune.
- K přidání aplikace Datalert do zařízení použijte Intune.
- Vypněte službu Datalert a službu Intune (volitelné).

## <a name="supported-platforms"></a>Podporované platformy

- Android 4,4 a novější zařízení, která podporují Knox (Samsung)

  [Verze Androidu, které podporují Knox](https://seap.samsung.com/faq/what-versions-android-support-knox-standard-and-knox-premium-sdks-0) (otevře web Samsung), uvádí podporované verze Knox.

- iOS 8.0 a novější

## <a name="prerequisites"></a>Požadované součásti

- Předplatné, které se má Microsoft Intune a přístup k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)
- Předplatné [Datalert](http://www.datalert.biz/) (otevře web Datalert)

## <a name="telecom-expense-management-providers"></a>Poskytovatelé pro správu telekomunikačních výdajů

Intune se integruje s následujícím poskytovatelem pro správu telekomunikačních výdajů:

- [Saaswedo Datalert, služba pro správu telekomunikačních výdajů](http://www.datalert.biz/) (otevře se web Datalert)

## <a name="deploy-the-intune-and-datalert-solution"></a>Nasazení řešení Intune a Datalert

### <a name="step-1-connect-the-datalert-service-to-intune"></a>Krok 1: připojení služby Datalert k Intune

1. Přihlaste se ke konzole pro správu Datalert s přihlašovacími údaji správce.

2. V konzole nástroje přejdete na kartu **nastavení** > **Konfigurace MDM**.

3. Vyberte **odblokovat**. **Odblokování** umožňuje změnit nebo aktualizovat nastavení na stránce.

4. V **Intune/Datalert připojení** > **Server MDM**vyberte **Microsoft Intune**.

5. V případě **domény Azure AD**zadejte ID tenanta Azure. Vyberte **připojení**.

    Když vyberete **připojení**, služba Datalert se vrátí s Intune. Potvrzuje, že nejsou k dispozici žádná existující připojení Datalert. Po chvíli se zobrazí přihlašovací stránka Microsoftu, za kterou následuje ověřování Azure Datalert.

6. Na ověřovací stránce Microsoft vyberte **Přijmout**.

    Budete přesměrováni na stránku Datalert s **poděkováním** , která se po chvíli zavře. Datalert ověří připojení a zobrazí zelenou značku zaškrtnutí u položek, které byly ověřeny. Pokud se ověření nepovede, zobrazí se zpráva červeně. Pokud chcete získat pomoc, obraťte se na podporu Datalert.

    Na následujícím obrázku jsou po úspěšném připojení zobrazeny zelené značky zaškrtnutí:

      ![Stránka Datalert zobrazující úspěšné připojení](./media/telecom-expenses-monitor/tem-datalert-connection.png)

7. V části **Datalert App/ADAL souhlasu**nastavte přepínač na **zapnuto**. Na ověřovací stránce Microsoft vyberte **Přijmout**.

    Budete přesměrováni na stránku Datalert s **poděkováním** , která se po chvíli zavře. Datalert ověří připojení a zobrazí zelenou značku zaškrtnutí u položek, které byly ověřeny. Pokud se ověření nepovede, zobrazí se zpráva červeně. Pokud chcete získat pomoc, obraťte se na podporu Datalert.

    Na následujícím obrázku jsou po úspěšném připojení zobrazeny zelené značky zaškrtnutí:

      ![Stránka Datalert zobrazující úspěšné připojení](./media/telecom-expenses-monitor/tem-datalert-adal-consent.png)

8. V části **Správa profilů MDM (volitelné)** nastavte přepínač na **zapnuto**. Toto nastavení umožňuje Datalert načíst dostupné profily v Intune, které vám pomůžou nastavit zásady. 

    Na ověřovací stránce Microsoft vyberte **Přijmout**.

    Budete přesměrováni na stránku Datalert s **poděkováním** , která se po chvíli zavře. Datalert ověří připojení a zobrazí zelenou značku zaškrtnutí u položek, které byly ověřeny. Pokud se ověření nepovede, zobrazí se zpráva červeně. Pokud chcete získat pomoc, obraťte se na podporu Datalert.

    Na následujícím obrázku jsou po úspěšném připojení zobrazeny zelené značky zaškrtnutí:

   ![Stránka Datalert zobrazující úspěšné připojení](./media/telecom-expenses-monitor/tem-datalert-mdm-profiles.png)

### <a name="step-2-confirm-telecom-expense-management-is-active-in-intune"></a>Krok 2: potvrďte, že je Správa telekomunikačních výdajů aktivní v Intune

Po dokončení kroku 1 se připojení automaticky povolí. V Intune se zobrazuje stav připojení **aktivní**. Pokud chcete potvrdit, že je stav aktivní, použijte následující postup:

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte možnost **Správa tenanta** > **konektory a tokeny** > **správu telekomunikačních výdajů**. Vyhledejte stav **aktivního** připojení:

   ![Stránka Intune zobrazující aktivní stav připojení Datalertu](./media/telecom-expenses-monitor/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-devices"></a>Krok 3: nasazení aplikace Datalert do zařízení

Pokud chcete potvrdit, že se bude shromažďovat využití dat jenom z řádků vlastněných organizací, nezapomeňte:

- Vytváření kategorií zařízení v Intune
- Cílit aplikaci Datalert jenom na telefony s organizací.

V této části jsou uvedeny tyto kroky.

#### <a name="create-device-categories-and-device-groups-mapped-to-your-categories"></a>Vytváření kategorií zařízení a skupin zařízení mapovaných na vaše kategorie

V závislosti na potřebách vaší organizace vytvořte aspoň dvě kategorie zařízení, například firemní a osobní. Pak pro každou kategorii vytvořte dynamické skupiny zařízení. Podle potřeby pro svoji organizaci můžete vytvořit více kategorií.

Informace o vytváření kategorií zařízení v Intune najdete v tématu [mapování zařízení na skupiny](../enrollment/device-group-mapping.md).

Tyto kategorie se uživatelům zobrazí během registrace ([registrace zařízení s Androidem](../enrollment/android-enroll.md)). V závislosti na tom, jakou kategorii uživatelé zvolí, se zaregistrované zařízení přesune do příslušné skupiny zařízení.

  ![Snímek obrazovky s podoknem Přidat zásadu](./media/telecom-expenses-monitor/tem-dynamic-membership-rules.png)

#### <a name="add-the-datalert-app-to-intune"></a>Přidání aplikace Datalert do Intune

V následujících krocích se přidá aplikace Datalert. V takovém případě se používá iOS. [Přidejte aplikace](../apps/apps-add.md) a [používejte značky oboru](../fundamentals/scope-tags.md) , které obsahují konkrétnější informace o těchto krocích.

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **aplikace** > **všechny aplikace** > **Přidat**.

2. Vyberte **Typ aplikace**. Například pro iOS vyberte **Store app-iOS**.

3. V **části Hledat v App Storu**zadejte **Datalert** a vyhledejte aplikaci Datalert.

4. Zvolte aplikaci **Datalert** > **Vyberte**:

   ![Přidání aplikace datalert z App Storu do klientských aplikací Intune](./media/telecom-expenses-monitor/tem-select-app-from-apple-app-store.png)

5. Zadejte jakékoli další vlastnosti, například informace o aplikaci a značky oboru:

   ![Zadejte vlastnosti aplikace, včetně názvu, popisu, výběru operačního systému a dalších nastavení aplikace v Intune.](./media/telecom-expenses-monitor/tem-steps-to-create-the-app.png)

6. Vyberte **OK** > **Přidat** a uložte provedené změny. V seznamu se zobrazí aplikace Datalert.

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Přiřazení aplikace Datalert ke skupině firemních zařízení

1. V části **aplikace** > **všechny aplikace**vyberte aplikaci Datalert, kterou jste přidali v předchozím kroku.

2. Vyberte **přiřazení** > **Přidat skupinu**. Vyberte způsob přiřazení aplikace. [Přiřazení aplikací do skupin v Intune](../apps/apps-deploy.md) obsahuje další podrobnosti o těchto nastaveních.

    V tomto postupu se rozhodnete nastavit, aby byla instalace aplikace povinná nebo volitelná pro skupinu. Následující příklad znázorňuje instalaci podle potřeby. V případě potřeby si uživatelé musí po registraci svého zařízení nainstalovat aplikaci Datalert.

   ![Snímek obrazovky s podoknem Přidat zásadu](./media/telecom-expenses-monitor/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-organization-phone-lines-to-the-datalert-console"></a>Krok 4: Přidání telefonních linek organizace do konzoly Datalert

Služby Intune a Datalert jsou teď nakonfigurované tak, aby vzájemně komunikovaly. Potom do konzoly Datalert přidejte své organizace placené telefonní linky. A zadejte prahové hodnoty a akce pro jakékoli narušení mobilního nebo roamingového použití. Do konzoly Datalert můžete ručně přidat firemní placené telefonní linky nebo je automaticky přidat po registraci zařízení v Intune.

Chcete-li nastavit tyto položky, přejít na [Datalert instalační program pro Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (otevře web Datalert). Na kartě **Nastavení** postupujte podle pokynů v Průvodci instalací nástroje.

  ![Snímek obrazovky s podoknem Přidat zásadu](./media/telecom-expenses-monitor/tem-add-phone-lines-to-datalert-console.png)

Služba Datalert je teď aktivní. Spustí monitorování využití dat a zakáže mobilní a roamingová data na zařízeních, která překračují nakonfigurovaná omezení využití.

## <a name="end-user-enrollment"></a>Registrace koncového uživatele

Pro činnost koncového uživatele mohou následující články pomáhat:

- [Registrace zařízení s iOSem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
- [Registrace zařízení s Androidem ve službě TEM (Telecom Expense Management)](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turn-off-the-datalert-service"></a>Vypnutí služby Datalert

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **Správa tenanta** > **konektory a tokeny** > **správu telekomunikačních výdajů**.
2. Nastavte **Povolit správu telekomunikačních výdajů a zablokujte mobilní nebo roamingová data na zařízeních, která přesahují kvóty využití, které nakonfigurujete** pro **zakázání**.
3. **Uložte** provedené změny.

> [!IMPORTANT]
> Pokud službu Datalert zakážete v Intune:
>
> - Všechny akce, které jsou aplikovány na zařízení z důvodu předchozích porušení limitů použití, jsou vráceny.
> - Uživatelům se už nebude blokovat přístup k datům a roaming.
> - Intune stále přijímá signály přicházející ze služby, ale tyto signály ignoruje.

## <a name="next-steps"></a>Další kroky

Vytváření sestav využití dat je dostupné v konzole pro správu Datalert v Saaswedo.