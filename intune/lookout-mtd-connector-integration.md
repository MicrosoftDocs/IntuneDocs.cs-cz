---
title: Nastavení integrace služby Lookout s Microsoft Intune
titleSuffix: Microsoft Intune
description: Přečtěte si o integraci Intune se službou Lookout Mobile Endpoint Security jako řešení Mobile Threat Defense, k řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be2e9371288961d0afdf7ad6e8cfec8f734087f6
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529870"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Nastavení integrace služby Lookout Mobile Endpoint Security se službou Intune
V prostředí, které splňuje [požadavky](lookout-mobile-threat-defense-connector.md#prerequisites), můžete integrovat Lookout Mobile Endpoint Security se službou Intune. Informace v tomto článku se dozvíte v nastavení integrace a konfigurace důležitých nastavení ve službě Lookout pro použití s Intune.  

> [!IMPORTANT]
> Existujícího tenanta Lookout Mobile Endpoint Security, který ještě není přidružený k vašemu tenantovi Azure AD, nejde použít k integraci s Azure AD a Intune. Pokud chcete vytvořit nového tenanta Lookout Mobile Endpoint Security, obraťte se na podporu Lookoutu. Pomocí tohoto nového tenanta můžete připojit uživatele Azure AD.

## <a name="collect-azure-ad-information"></a>Shromáždění informací z Azure AD  
Integrované služby Lookout s Intune můžete přidružit k váš tenant Lookout Mobility Endpoint Security vaše předplatné Azure Active Directory (AD).

Aby vaše předplatné integrace Lookout Mobile Endpoint Security se službou Intune, zadejte následující informace pro podporu služby Lookout (enterprisesupport@lookout.com):  

- **ID adresáře tenanta Azure AD**  

- **ID objektu skupiny Azure AD** skupiny pomocí **úplné** přístup ke konzole Lookout Mobile Endpoint Security (MES).  
  Vytvořte tuto skupinu uživatelů ve službě Azure AD obsahující uživatele, kteří mají *úplný přístup* k přihlášení **konzole Lookout**. Uživatelé musí být členy této skupiny nebo volitelné *omezený přístup* skupiny, pro přihlášení ke konzole Lookout. 

- **ID objektu skupiny Azure AD** skupiny pomocí **s omezeným přístupem** přístup ke konzole Lookout MES *(volitelnou skupinu)* . 
  Vytvoření této skupiny volitelné uživatelů ve službě Azure AD obsahující uživatele, kteří by neměly mít přístup k týkajícím se konfigurace a registrace některým modulům konzoly Lookout. Místo toho tito uživatelé mají přístup jen pro čtení k **zásady zabezpečení** konzoly Lookout. Uživatelé musí být členy této volitelné skupinu nebo požadované *úplný přístup* skupiny, pro přihlášení ke konzole Lookout.

 > [!TIP] 
 > Další podrobnosti o oprávněních najdete v [tomto článku](https://personal.support.lookout.com/hc/articles/114094105653) na webu Lookout.

### <a name="collect-information-from-azure-ad"></a>Shromažďování informací ze služby Azure AD 

1. Přihlaste se k [webu Azure portal](https://portal.azure.com) pomocí účtu globálního správce.

2. Přejděte na **Azure Active Directory** > **vlastnosti** a vyhledejte vaši **ID adresáře**. Použití *kopírování* tlačítko pro kopírování ID adresáře a uložte ho do textového souboru.

   ![Vlastnosti služby Azure AD](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Dále vyhledejte ID skupiny Azure AD pro účty, které používáte k Azure AD uživatelům udělit přístup ke konzole Lookout. Jedna skupina je pro *úplný přístup*a druhé skupiny pro *omezený přístup* je volitelný. Chcete-li získat *ID objektu*, pro každý účet:  
   1. Přejděte na **Azure Active Directory** > **skupiny** otevřít *skupiny – všechny skupiny* podokně.  

   2. Vyberte skupinu, kterou jste vytvořili pro *úplný přístup* otevřete jeho *přehled* podokně.  

   3. Použití *kopírování* tlačítko pro kopírování ID objektu a uložte ho do textového souboru.  

   4. Opakujte proces pro *omezený přístup* skupiny, pokud použijete tuto skupinu.  

      ![ID objektu skupiny Azure AD](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Až tyto informace shromáždíte, kontaktujte podporu služby Lookout (e-mail: enterprisesupport@lookout.com). Podpora lookout bude pracovat s váš primární kontakt na základě poskytnutých vaše předplatné a vytvořit váš účet Lookout Enterprise, pomocí informací, které zadáte.  

## <a name="configure-your-lookout-subscription"></a>Konfigurace předplatného služby Lookout  
Jakmile vám podpora Lookout vytvoří účet Lookout Enterprise, podpora služby Lookout odešle e-mail na adresu primárního kontaktu vaší firmy s odkazem na adresu url přihlášení: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>Počáteční přihlášení  
První přihlášení ke konzole Lookout MES zobrazí stránka pro odsouhlasení podmínek (https://aad.lookout.com/les?action=consent). Azure AD globálního správce právě přihlášení a **přijmout**. Následné přihlášení nevyžaduje, aby uživatel už tato úroveň oprávnění Azure AD. 

 Zobrazí se stránka pro vyjádření souhlasu. Vyberte možnost **přijmout** a dokončete registraci. 
   ![snímek obrazovky s první přihlašovací stránku konzoly Lookout](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Při přijetí a vyjádření souhlasu budete přesměrováni do konzoly Lookout.

Po dokončení počáteční přihlášení a vyjádření souhlasu uživatele, který přihlásit z https://aad.lookout.com přesměrováni do konzoly MES. Pokud ještě nebyl udělen souhlas, výsledkem všech pokusů o přihlášení chybný Chyba přihlášení.

### <a name="configure-the-intune-connector"></a>Konfigurace konektoru Intune  
Následující postup předpokládá, že jste předtím vytvořili skupinu uživatelů ve službě Azure AD pro účely testování nasazení aplikace Lookout. Osvědčeným postupem je začít s malou skupinou uživatelů a Povolit správcům Lookoutu a Intune a seznamte se s integrací produktu. Po jejich jste se seznámili, můžete registraci rozšířit na další skupiny uživatelů.

1. Přihlaste se k [konzole Lookout MES](https://aad.lookout.com) a přejděte na **systému** > **konektory**a pak vyberte **konektoru přidat**.  Vyberte **Intune**.

   ![Obrázek konzoly Lookout s Intune možností na kartě konektory](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. Na *Microsoft Intune* vyberte **nastavení připojení** a zadejte **frekvenci prezenčního signálu** během několika minut. 

   ![Obrázek kartu Nastavení připojení nakonfigurovaná frekvence prezenčního signálu](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. Vyberte **Správa registrace**a pro **použijte následující skupiny zabezpečení Azure AD k identifikaci zařízení, která by měla být zaregistrované v Lookout for Work**, zadejte *název skupiny*skupiny Azure AD pomocí služby Lookout, a potom vyberte **uložit změny**.

    ![snímek obrazovky zobrazující stránku registrace konektoru Intune](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **O skupinách použijete**:
   - Jako osvědčený postup spusťte pomocí skupiny zabezpečení služby Azure AD, který obsahuje malý počet uživatelů k testování aplikací Lookout integration.
   - **Název skupiny** rozlišuje velká a jak je znázorněno **vlastnosti** skupiny zabezpečení na webu Azure Portal.  
   - U vámi určených pro skupin **Správa registrace** definovat sadu uživatelů, jejichž zařízení se zaregistrují službu lookout. Pokud je uživatel ve skupině pro registraci, jejich zařízení ve službě Azure AD se zaregistrují a nich možné aktivovat Lookout MES. Uživatel otevře poprvé *Lookout for Work* aplikace na podporovaných zařízeních, zobrazí výzva k její aktivaci.

4. Vyberte **synchronizace stavu** a zajištění toho, aby *stav zařízení* a *hrozeb stav* jsou nastaveny na **na**.  Jsou potřeba pro integraci Lookout a Intune fungovala správně.  

5. Vyberte **Správa chyb**, zadejte e-mailovou adresu, která by měla přijímat zprávy o chybách a pak vyberte **uložit změny**.
 
   ![snímek obrazovky zobrazující stránku správy chyb konektoru Intune](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Vyberte **vytvořit konektor** na kompletní konfigurace konektoru. Později až budete s výsledky spokojení, můžete rozšířit registraci na další skupiny uživatelů.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Konfigurace Intune pro používání Lookout Mobile Threat Defense zprostředkovatele
Po dokončení konfigurace aplikace Lookout MES, musíte vytvořit připojení ke službě Lookout v Intune.  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Přejděte na **dodržování předpisů zařízením** > **Mobile Threat Defense** a vyberte **přidat**.

3. Na *konektoru přidat* podokně, použijte rozevírací seznam a vyberte **Lookout for Work**.  

4. Vyberte **Vytvořit**. Po spojnice vytvoří v kontaktu s Lookout MES *nastavení konektoru* budou k dispozici.

5. Nastavte **povolit synchronizaci aplikací pro zařízení se systémem iOS** k **na**. 

6. Vyberte **Uložit** a dokončete tak konfiguraci.  Intune a Lookout MES jsou teď integrované a připravené k použití.


## <a name="additional-settings-in-the-lookout-mes-console"></a>Další nastavení v konzole Lookout MES
Tady jsou další nastavení, která můžete nakonfigurovat v konzole Lookout MES.  

### <a name="configure-enrollment-settings"></a>Konfigurace nastavení registrace
V konzole Lookout MES vyberte **systému** > **spravovat registrace** > **nastavení registrace**.  

- Pro **stav Odpojeno**, zadejte počet dní, než se zařízení s nepřipojené je označená jako odpojená.  

  Odpojená zařízení se považují za nevyhovující a přístup k firemním aplikacím se jim zablokuje na základě zásad podmíněného přístupu Intune. Můžete zadat hodnotu mezi 1 a 90 dny.

  ![Nastavení registrace služby lookout v modulu systému](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>Konfigurace e-mailových oznámení
Pokud chcete dostávat e-mailová upozornění na hrozby, přihlaste se k [konzole Lookout MES](https://aad.lookout.com) pomocí uživatelského účtu, který má dostávat oznámení.  

- Přejděte na **Předvolby** a nastavte oznámení budete dostávat na **ON**a potom **Uložit** změny.  

- Pokud už nechcete dostávat e-mailová oznámení, nastavte u nich hodnotu **OFF** a uložte provedené změny.

  ![snímek obrazovky stránku předvoleb se zobrazeným uživatelským účtem](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)



## <a name="configure-threat-classifications"></a>Konfigurace klasifikace hrozeb  
Lookout Mobile Endpoint Security klasifikuje mobilní hrozby podle různých typů. Klasifikace hrozeb služby Lookout mít k nim má přiřazené výchozí úrovně rizika. Úrovně rizik lze změnit kdykoli tak, aby odpovídaly požadavkům vaší společnosti.

Informace o úrovni klasifikace hrozeb a Správa úrovně rizika spojená s nimi, naleznete v tématu [odkaz před internetovými útoky Lookout](https://enterprise.support.lookout.com/hc/articles/360011812974).

>[!IMPORTANT]
> Úrovně rizik jsou důležitou součástí Mobile Endpoint Security, protože integrace s Intune vypočítává dodržování předpisů zařízením podle těchto úrovní rizik za běhu.  
> 
> Správce Intune nastaví v zásadách pravidlo, které určí, že zařízení nesplňuje předpisy, pokud pro něj existuje aktivní hrozba minimálně **vysoké**, **střední** nebo**nízké** úrovně. Zásady klasifikace hrozeb ve službě Lookout Mobile Endpoint Security přímo řídí výpočet dodržování předpisů zařízením v Intune.  

## <a name="monitor-enrollment"></a>Sledování registrace
Po dokončení instalace aplikace Lookout Mobile Endpoint Security spustí k dotazování služby Azure AD pro zařízení, která odpovídají určeným skupinám pro registraci.  Informace o registrovaných zařízeních najdete na webu **zařízení** v konzole Lookout MES.  
- Počáteční stav u zařízení se *čekající*.  
- Stav zařízení se aktualizuje po *Lookout for Work* aplikace je nainstalovaná, otevře a aktivuje na zařízení.

Podrobnosti o tom, jak *Lookout for Work* aplikace nasazená na zařízení, najdete v článku [přidat aplikace Lookout for work pomocí Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Další postup

[Nastavení aplikací Lookout](mtd-apps-ios-app-configuration-policy-add-assign.md)
