---
title: Nastavení integrace služby Lookout s Microsoft Intune
titlesuffix: ''
description: Přečtěte si o integraci Intune se službou Lookout Mobile Threat Defense za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8b1b7d9ef1a7dce0b5a139f3b8acb85ab7d11d4c
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a>Nastavení integrace ochrany před mobilními hrozbami Lookout s Intune

Při nastavování předplatného ochrany před mobilními hrozbami Lookout je potřeba provést tyto kroky:

| #        |Krok  |
| ------------- |:-------------|
| 1 | [Shromáždění informací z Azure AD](#collect-azure-ad-information) |
| 2 | [Konfigurace předplatného](#configure-your-subscription) |
| 3 | [Konfigurace skupin pro registraci](#configure-enrollment-groups) |
| 4 | [Konfigurace synchronizace stavu](#configure-state-sync) |
| 5 | [Konfigurace informací o příjemci e-mailů se zprávami o chybách](#configure-error-report-email-recipient-information) |
| 6 | [Konfigurace nastavení registrace](#configure-enrollment-settings) |
| 7 | [Konfigurace e-mailových oznámení](#configure-email-notifications) |
| 8 | [Konfigurace klasifikace hrozeb](#configure-threat-classification) |
| 9 | [Sledování registrací](#watching-enrollment) |

> [!IMPORTANT]
> Existujícího tenanta Lookout Mobile Endpoint Security, který ještě není přidružený k vašemu tenantovi Azure AD, nejde použít k integraci s Azure AD a Intune. Pokud chcete vytvořit nového tenanta Lookout Mobile Endpoint Security, obraťte se na podporu Lookoutu. Pomocí tohoto nového tenanta můžete připojit uživatele Azure AD.

## <a name="collect-azure-ad-information"></a>Shromáždění informací z Azure AD
Váš tenant Lookout Mobility Endpoint Security se přidruží k předplatnému Azure AD, aby se Lookout mohl integrovat s Intune. K tomu, aby bylo možné povolit předplatné ochrany před mobilními hrozbami Lookout, potřebuje podpora služby Lookout (enterprisesupport@lookout.com) následující informace:

* **ID klienta Azure AD**
* **ID objektu skupiny Azure AD** pro **úplný** přístup ke konzole Lookout
* **ID objektu skupiny Azure AD** pro **omezený** přístup ke konzole Lookout (volitelné)

V následujícím postupu se dozvíte, jak získat informace, které je třeba sdělit týmu podpory služby Lookout.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com) a vyberte své předplatné. 

2. Když vyberete název vašeho předplatného, výsledná adresa URL obsahuje ID předplatného.  Pokud máte problémy s nalezením ID vašeho předplatného, přečtěte si [článek podpory společnosti Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b), který obsahuje tipy, jak toto ID najít.

3. Najděte ID skupiny Azure AD. Konzola Lookout podporuje dvě úrovně přístupu:  
  * **Úplný přístup:** Správce Azure AD může vytvořit skupinu pro uživatele, kteří budou mít úplný přístup, a volitelně může také vytvořit skupinu pro uživatele, kteří budou mít omezený přístup.  Ke **konzole Lookout** se budou moct přihlásit jenom uživatelé z těchto skupin.
  * **Omezený přístup:** Uživatelé z této skupiny nemají přístup k některým modulům konzoly Lookout týkajícím se konfigurace a registrace a mají přístup jenom pro čtení k modulu **Zásady zabezpečení**.  

    > [!TIP] 
    > Další podrobnosti o oprávněních najdete v [tomto článku](https://personal.support.lookout.com/hc/articles/114094105653) na webu Lookout.

    > [!NOTE] 
    > **ID objektu skupiny** najdete na stránce **Vlastnosti** dané skupiny v **portálu pro správu Azure AD**.

4. Jakmile tyto informace získáte, obraťte se na podporu služby Lookout (e-mail: enterprisesupport@lookout.com). Podpora Lookout bude při zprovoznění vašeho předplatného a vytvoření účtu Lookout Enterprise používat váš primární kontakt (pro veškerou potřebnou komunikaci) na základě poskytnutých informací.

## <a name="configure-your-subscription"></a>Konfigurace předplatného

1. Poté, co podpora služby Lookout vytvoří váš účet Lookout Enterprise, se na adresu primárního kontaktu vaší firmy odešle e-mail ze služby Lookout s odkazem na přihlašovací stránku: https://aad.lookout.com/les?action=consent.

2.  Při prvním přihlášení ke konzole Lookout je nutné použít uživatelský účet, který má v Azure AD roli globálního správce, aby bylo možné zaregistrovat tenanta Azure AD. Při dalších přihlášeních se už tato úroveň oprávnění v Azure AD nevyžaduje. Zobrazí se stránka pro vyjádření souhlasu. Vyberte možnost **přijmout** a dokončete registraci. Po přijetí a vyjádření souhlasu budete přesměrováni na konzolu Lookout.

    ![snímek obrazovky stránky prvního přihlášení do konzoly Lookout](./media/lookout_mtp_initial_login.png)

3.  V [konzole Lookout](https://aad.lookout.com) zvolte v modulu **Systém** kartu **Konektory** a vyberte **Intune**.

    ![snímek obrazovky zobrazující konzolu Lookout s otevřenou kartou konektorů a zvýrazněnou možností Intune](./media/lookout_mtp_setup-intune-connector.png)

4.  Přejděte na **Konektory** > **Nastavení připojení** a určete **frekvenci prezenčního signálu** v minutách.

    ![snímek obrazovky zobrazující kartu nastavení připojení, na které je nakonfigurovaná frekvence prezenčního signálu](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Konfigurace skupin pro registraci
1. Osvědčeným postupem je vytvořit na [portálu pro správu Azure AD](https://manage.windowsazure.com) skupinu zabezpečení Azure AD, která obsahuje malý počet uživatelů a umožňuje otestovat integraci se službou Lookout.

    > [!NOTE] 
    > Všechna identifikovaná a podporovaná zařízení uživatelů ve skupině pro registraci v Azure AD, která Lookout podporuje a jsou zaregistrovaná v Intune, se zaregistrují a bude možné je aktivovat v konzole Lookout MTD.

2. V [konzole Lookout](https://aad.lookout.com) zvolte v modulu **Systém** kartu **Konektory** a vyberte **Správa registrace**, abyste mohli definovat sadu uživatelů, jejichž zařízení se mají ve službě Lookout zaregistrovat. Přidejte **zobrazovaný název** skupiny zabezpečení Azure AD pro registraci.

    ![snímek obrazovky zobrazující stránku registrace konektoru Intune](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > V **zobrazovaném názvu** se rozlišují velká a malá písmena, jak je vidět ve **vlastnostech** skupiny zabezpečení na webu Azure Portal. Na obrázku níže vidíte, že **zobrazovaný název** skupiny zabezpečení je ve stylu CamelCase, zatímco v nadpisu jsou všechna písmena malá. V konzole Lookout použijte pro **zobrazovaný název** stejnou velikost písmen jako u skupiny zabezpečení.
    >![snímek obrazovky portálu Azure Portal, služby Azure Active Directory a stránky vlastností](./media/aad-group-display-name.png)

    >[!NOTE] 
    >Osvědčeným postupem je ponechat výchozí nastavení (5 minut) intervalu vyhledávání nových zařízení. Stávající omezení: **služba Lookout nedokáže ověřit zobrazované názvy skupin** – zkontrolujte, že pole **ZOBRAZOVANÝ NÁZEV** na portálu Azure Portal přesně odpovídá skupině zabezpečení Azure AD. **Nepodporuje se vytváření vnořených skupin:** skupiny zabezpečení Azure AD, které se používají ve službě Lookout, musí obsahovat jenom uživatele. Nesmí obsahovat jiné skupiny.

3.  Po přidání skupiny se podporované zařízení aktivuje ve službě Lookout ve chvíli, kdy na něm uživatel znovu otevře aplikaci Lookout for Work.

4.  Až budete s výsledky spokojení, rozšiřte registraci na další skupiny uživatelů.

## <a name="configure-state-sync"></a>Konfigurace synchronizace stavu
V nastavení **Synchronizace stavu** určete typ dat odesílaných do Intune.  Aby integrace služeb Lookout a Intune fungovala správně, je nutné povolit stav zařízení i stav hrozby. Ve výchozím nastavení jsou tyto možnosti povolené.

## <a name="configure-error-report-email-recipient-information"></a>Konfigurace informací o příjemci e-mailů se zprávami o chybách
V nastavení **Správa chyb** zadejte e-mailovou adresu příjemce, který má dostávat zprávy o chybách.

![snímek obrazovky zobrazující stránku správy chyb konektoru Intune](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Konfigurace nastavení registrace
V modulu **Systém** zadejte na stránce **Konektory** počet dnů, po jejichž uplynutí se zařízení bude považovat za odpojené.  Odpojená zařízení se považují za nevyhovující a přístup k firemním aplikacím se jim zablokuje na základě zásad podmíněného přístupu Intune. Můžete zadat hodnotu mezi 1 a 90 dny.

![Nastavení registrace služby Lookout](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>Konfigurace e-mailových oznámení
Pokud chcete e-mailem dostávat upozornění na hrozby, přihlaste se ke [konzole Lookout](https://aad.lookout.com) pomocí uživatelského účtu, na kterém chcete oznámení přijímat. Přejděte na kartu **Předvolby** v modulu **Systém**, vyberte úrovně hrozeb, při kterých by se měla posílat oznámení, a nastavte u nich hodnotu **Zapnuto**. Uložte provedené změny.

![snímek obrazovky zobrazující stránku předvoleb se zobrazeným uživatelským účtem](./media/lookout-mtp-email-notifications.png) Pokud už nechcete dostávat některá e-mailová oznámení, nastavte příslušná oznámení na **Vypnuto** a provedené změny uložte.

### <a name="configure-threat-classification"></a>Konfigurace klasifikace hrozeb
Ochrana před mobilními hrozbami Lookout klasifikuje mobilní hrozby podle různých typů. [Klasifikace hrozeb ve službě Lookout](http://personal.support.lookout.com/hc/articles/114094130693) k nim má přiřazené výchozí úrovně rizika. Ty lze kdykoli změnit tak, aby odpovídaly požadavkům vaší společnosti.

![snímek obrazovky zobrazující stránku zásad s hrozbami a klasifikací](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Úrovně rizik jsou důležitou součástí ochrany před mobilními hrozbami, protože integrace se službou Intune vypočítává míru dodržování předpisů u zařízení za běhu právě podle těchto úrovní rizik. Správce Intune nastaví v zásadách pravidlo, které určí, že zařízení nesplňuje předpisy, pokud pro něj existuje aktivní hrozba minimálně **vysoké**, **střední** nebo**nízké** úrovně. Zásady klasifikace hrozeb v ochraně před mobilními hrozbami Lookout přímo řídí výpočet dodržování předpisů zařízením ve službě Intune.

## <a name="watching-enrollment"></a>Sledování registrací
Po dokončení nastavení začne ochrana před mobilními hrozbami Lookout posílat do služby Azure AD dotazy na zařízení, která odpovídají určeným skupinám pro registraci.  Informace o registrovaných zařízeních najdete v modulu Zařízení.  Počáteční stav u zařízení je čekající na vyřízení.  Stav zařízení se změní, jakmile se na zařízení nainstaluje, otevře a aktivuje aplikace Lookout for Work.  Podrobnosti o tom, jak aplikaci Lookout for Work přidat do zařízení, najdete v tématu [Přidání aplikací Lookout for Work pomocí Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Další kroky

[Nastavení aplikací Lookout](mtd-apps-ios-app-configuration-policy-add-assign.md)
