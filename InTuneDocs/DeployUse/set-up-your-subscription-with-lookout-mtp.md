---
title: "Nastavení předplatného pro službu Lookout | Microsoft Intune"
description: "Toto téma obsahuje podrobné informace o způsobu konfigurace ochrany zařízení před internetovými útoky ve službě Lookout."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Nastavení předplatného ochrany zařízení před internetovými útoky ve službě Lookout
Aby mohla podpora Lookout ((enterprisesupport@lookout.com)) připravit vaše předplatné na službu ochrany před hrozbami pro zařízení služby Lookout, potřebuje následující informace o vašem předplatném Azure Active Directory (Azure AD). Váš tenant Lookout Mobility Endpoint Security se přidruží k předplatnému Azure AD, aby se Lookout mohl integrovat s Intune. 

* **ID klienta Azure AD**
* **ID objektu skupiny Azure AD** pro **úplný** přístup ke konzole Lookout
* **ID objektu skupiny Azure AD** pro **omezený** přístup ke konzole Lookout (volitelné)

> [!IMPORTANT]
> Existujícího tenanta Lookout Mobile Endpoint Security, který ještě není přidružený k vašemu tenantovi Azure AD, nejde použít k integraci s Azure AD a Intune. Pokud chcete vytvořit nového tenanta Lookout Mobile Endpoint Security, obraťte se na podporu Lookoutu. Pomocí tohoto nového tenanta můžete připojit uživatele Azure AD.

V následující části se dozvíte, jak získat informace, které je třeba sdělit týmu podpory Lookout.  

## <a name="get-your-azure-ad-information"></a>Získejte informace o vašem účtu v Azure AD
### <a name="azure-ad-tenant-id"></a>ID tenanta Azure AD
Přihlaste se k [portálu pro správu Azure AD](https://manage.windowsazure.com) a vyberte své předplatné. 

![snímek obrazovky zobrazující stránku služby Azure AD, na které je název tenanta](../media/mtp/aad_tenant_name.png) Když zvolíte název svého předplatného, bude výsledná adresa URL obsahovat jeho ID.  Pokud máte problémy s nalezením ID vašeho předplatného, přečtěte si [článek podpory společnosti Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US), který obsahuje tipy, jak toto ID najít.   
### <a name="azure-ad-group-id"></a>ID skupiny AD Azure
Konzola Lookout podporuje dvě úrovně přístupu:  
* **Úplný přístup:** Správce Azure AD může vytvořit skupinu pro uživatele, kteří budou mít úplný přístup, a volitelně může také vytvořit skupinu pro uživatele, kteří budou mít omezený přístup.  Ke **konzole Lookout** se budou moct přihlásit jenom uživatelé z těchto skupin.
* **Omezený přístup:** Uživatelé z této skupiny nemají přístup k některým modulům konzoly Lookout týkajícím se konfigurace a registrace a mají přístup jenom pro čtení k modulu **Zásady zabezpečení**.  

Další podrobnosti o oprávněních najdete v [tomto článku](https://personal.support.lookout.com/hc/en-us/articles/114094105653) na webu Lookout.

**ID objektu skupiny** najdete na stránce **Vlastnosti** dané skupiny v **konzole pro správu Azure AD**.

![snímek obrazovky zobrazující stránku vlastností se zvýrazněným polem s ID skupiny](../media/mtp/aad_group_object_id.png)

Jakmile tyto informace získáte, obraťte se na podporu Lookout (e-mail: enterprisesupport@lookout.com).

Podpora Lookout bude při zprovoznění vašeho předplatného a vytvoření účtu Lookout Enterprise používat váš primární kontakt (pro veškerou potřebnou komunikaci) na základě poskytnutých informací.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Nastavení předplatného ochrany zařízení před internetovými útoky ve službě Lookout
### <a name="step-1-set-up-your-device-threat-protection"></a>Krok 1: Nastavení ochrany zařízení před internetovými útoky
Jakmile vám podpora Lookout vytvoří účet Lookout Enterprise, budete se moct přihlásit ke konzole Lookout.   Na adresu primárního kontaktu vaší firmy Lookout odešle e-mail s odkazem na přihlašovací stránku: https://aad.lookout.com/les?action=consent

Při prvním přihlášení ke konzole Lookout musíte použít uživatelský účet, který má v Azure AD roli globálního správce. Služba Lookout tuto informaci potřebuje, aby mohla zaregistrovat tenanta Azure AD.   Při dalších přihlášeních už tato úroveň oprávnění ke službě Azure AD nebude třeba.  Při prvním přihlášení se zobrazí stránka pro odsouhlasení podmínek. Vyberte možnost **přijmout** a dokončete registraci.

![snímek obrazovky zobrazující přihlašovací stránku konzoly Lookout](../media/mtp/lookout_mtp_initial_login.png) Jakmile odsouhlasíte podmínky, budete přesměrováni do konzoly Lookout. Při dalších přihlášeních po počáteční registraci můžete používat tuto adresu URL: https://aad.lookout.com

Pokud se při přihlašování setkáte s problémy, přečtěte si [článek pro řešení potíží](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

Další kroky popisují úkoly, které musíte udělat, abyste dokončili nastavení služby Lookout v rámci [konzoly Lookout](https://aad.lookout.com).

### <a name="step-2-configure-the-intune-connector"></a>Krok 2: Konfigurace konektoru Intune

1.  V konzole Lookout zvolte v modulu **Systém** kartu **Konektory** a vyberte **Intune**.

  ![snímek obrazovky zobrazující konzolu Lookout s otevřenou kartou konektorů a zvýrazněnou možností Intune](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  V nastavení připojení nakonfigurujte frekvenci prezenčního signálu v minutách.  Váš konektor Intune je nyní připravený.  

  ![snímek obrazovky zobrazující kartu nastavení připojení, na které je nakonfigurovaná frekvence prezenčního signálu](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>Krok 3: Konfigurace skupin pro registraci
V nastavení **Správa registrace** definujte skupinu uživatelů, jejichž zařízení mají být zaregistrována ve službě Lookout. Osvědčeným postupem je otestovat postup s malou skupinou uživatelů a seznámit se tak s tím, jak integrace funguje.  Jakmile budete s výsledky testování spokojeni, můžete registraci rozšířit na další skupiny uživatelů.

Se skupinami pro registraci začněte tak, že nejdříve provedete definici skupiny zabezpečení Azure AD, která bude obsahovat první skupinu uživatelů vhodnou k registraci do ochrany zařízení před internetovými útoky ve službě Lookout. Po vytvoření skupiny v Azure AD přejděte v konzole Lookout do možnosti **Správa registrace** a přidejte **Zobrazované názvy** skupiny zabezpečení Azure AD pro registraci.

Když je uživatel ve skupině pro registraci, všechna jeho identifikovaná a podporovaná zařízení v Azure AD se zaregistrují a bude u nich možné aktivovat ochranu zařízení před internetovými útoky ve službě Lookout.  Podporované zařízení se aktivuje ve chvíli, kdy na něm poprvé spustíte aplikaci Lookout for Work.

![snímek obrazovky zobrazující stránku registrace konektoru Intune](../media/mtp/lookout-mtp-enrollment.png)

Osvědčeným postupem je ponechat výchozí nastavení (5 minut) intervalu vyhledávání nových zařízení.

>[!IMPORTANT]
> U zobrazovaného názvu se rozlišují velká a malá písmena.  Použijte **Zobrazovaný název**, který se zobrazuje na stránce **Vlastnosti** skupiny zabezpečení na webu Azure Portal. Na obrázku níže si všimněte, že zobrazovaný název na stránce **Vlastnosti** skupiny zabezpečení je zapsaný podle konvence camelCase.  Nadpis se však zobrazuje malými písmeny a neměl by se zadávat do konzoly Lookout.
>![snímek obrazovky portálu Azure Portal, služby Azure Active Directory a stránky vlastností](../media/mtp/aad-group-display-name.png)

Aktuální verze má následující omezení:  
* Žádné ověřování zobrazovaných názvů skupin není dostupné.  Ujistěte se, že používáte hodnotu z pole **ZOBRAZOVANÝ NÁZEV** na webu Azure Portal pro skupinu zabezpečení Azure AD.
* Vytváření skupin v rámci skupin není aktuálně podporováno.  Zadané skupiny zabezpečení Azure AD můžou obsahovat pouze uživatele, ne vnořené skupiny.


### <a name="step-4-configure-state-sync"></a>Krok 4: Konfigurace synchronizace stavu
V nastavení **Synchronizace stavu** určete typ dat odesílaných do Intune.  V současné době je nutné povolit stav zařízení i stav hrozby, aby integrace Lookout se službou Intune fungovala správně.  Ve výchozím nastavení jsou tyto možnosti povolené.
### <a name="step-5-configure-error-report-email-recipient-information"></a>Krok 5: Konfigurace informací o příjemci e-mailů se zprávami o chybách
V nastavení **Správa chyb** zadejte e-mailovou adresu příjemce, který má dostávat zprávy o chybách.

![snímek obrazovky zobrazující stránku správy chyb konektoru Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>Krok 6: Konfigurace nastavení registrace
V modulu **Systém** zadejte na stránce **Konektory** počet dnů, po jejichž uplynutí se zařízení bude považovat za odpojené.  Odpojená zařízení se považují za nevyhovující a bude jim zablokován přístup k firemním aplikacím na základě zásad podmíněného přístupu Intune. Můžete zadat hodnotu mezi 1 a 90 dny.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>Krok 7: Konfigurace e-mailových oznámení
Pokud chcete e-mailem dostávat upozornění na hrozby, přihlaste se ke [konzole Lookout](https://aad.lookout.com) pomocí uživatelského účtu, na kterém chcete oznámení přijímat. Přejděte na kartu **Předvolby** v modulu **Systém**, vyberte požadovaná oznámení a nastavte u nich hodnotu **Zapnuto**. Uložte provedené změny.

![snímek obrazovky zobrazující stránku předvoleb se zobrazeným uživatelským účtem](../media/mtp/lookout-mtp-email-notifications.png) Pokud už nechcete dostávat některá e-mailová oznámení, nastavte příslušná oznámení na **Vypnuto** a provedené změny uložte.
### <a name="step-8-configure-threat-classification"></a>Krok 8: Konfigurace klasifikace hrozeb
Ochrana zařízení před internetovými útoky ve službě Lookout klasifikuje mobilní hrozby podle různých typů. [Klasifikace hrozeb ve službě Lookout](http://personal.support.lookout.com/hc/en-us/articles/114094130693) k nim má přiřazené výchozí úrovně rizika. Ty lze kdykoli změnit tak, aby odpovídaly požadavkům vaší společnosti.

![snímek obrazovky zobrazující stránku zásad s hrozbami a klasifikací](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Úrovně rizik, které jsou tady zadané, jsou důležitou součástí ochrany zařízení před internetovými útoky, protože integrace s Intune vypočítává míru dodržování předpisů u zařízení za běhu právě podle těchto úrovní rizik. Správce Intune nastaví v zásadách pravidlo, které určí, že zařízení nesplňuje předpisy, pokud pro něj existuje aktivní hrozba minimálně nízké/střední/vysoké úrovně. Zásady klasifikace hrozeb v ochraně zařízení před internetovými útoky ve službě Lookout přímo řídí výpočet dodržování předpisů zařízením v Intune.

## <a name="watching-enrollment"></a>Sledování registrací
Po dokončení nastavení začne ochrana zařízení před internetovými útoky ve službě Lookout posílat do služby Azure AD dotazy na zařízení, která odpovídají určeným skupinám pro registraci.  Informace o registrovaných zařízeních najdete v modulu Zařízení.  Počáteční stav u zařízení je čekající na vyřízení.  Stav zařízení se změní, jakmile se na zařízení nainstaluje, otevře a aktivuje aplikace Lookout for Work.  Podrobnosti o tom, jak aplikaci Lookout for Work přidat do zařízení, najdete v tématu [Konfigurace a nasazení aplikace Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## <a name="next-steps"></a>Další kroky
[Povolení připojení Lookout MTP k Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


