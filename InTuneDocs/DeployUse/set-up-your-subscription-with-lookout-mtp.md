---
title: "Nastavení předplatného pro Lookout MTP | Microsoft Intune"
description: "Toto téma obsahuje podrobné informace o tom, jak nakonfigurovat Lookout MTP."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Nastavení předplatného ochrany proti mobilním hrozbám Lookout
Aby podpora Lookout (enterprisesupport@lookout.com) mohla připravit vaše předplatné pro službu Lookout MTP, bude potřebovat následující informace o vašem účtu ve službě Azure Active Directory (Azure AD). 

* ID klienta Azure AD
* ID objektu skupiny Azure AD pro úplný přístup ke konzole Lookout MTP
* ID objektu skupiny Azure AD pro omezený přístup ke konzole Lookout MTP (volitelné)

V následující části se dozvíte, jak získat informace, které je třeba sdělit týmu podpory Lookout.  

## Získání informací o vašem účtu v Azure AD
### Získání ID klienta Azure AD
Přihlaste se k portálu pro správu Azure AD (https://manage.windowsazure.com) a vyberte své předplatné. 

![snímek obrazovky zobrazující stránku služby Azure AD, na které je název tenanta](../media/mtp/aad_tenant_name.png) Když vyberete název vašeho předplatného, bude výsledná adresa URL obsahovat ID předplatného.  Pokud máte problémy s nalezením ID vašeho předplatného, přečtěte si [článek od podpory společnosti Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US), který obsahuje další tipy.   
### Získání ID skupiny Azure AD
Konzola Lookout MTP podporuje dvě úrovně přístupu:  
* **Úplný přístup:** Správce Azure AD může vytvořit skupinu pro uživatele, kteří budou mít úplný přístup a volitelně mohou také vytvořit skupinu pro uživatele, kteří budou mít omezený přístup.  Ke **konzole Lookout MTP** se budou moct přihlásit jenom uživatelé z těchto skupin.
* **Omezený přístup:** K několika modulům konzoly Lookout MTP týkajícím se konfigurace a registrace nebude umožněn přístup vůbec a k modulu **Zásady zabezpečení** bude přístup jen pro čtení.  

Další podrobnosti o oprávněních najdete v [tomto článku](https://personal.support.lookout.com/hc/en-us/articles/114094105653) na webu Lookout.

**ID objektu skupiny** najdete na stránce vlastností skupiny v konzole pro správu Azure AD.

![snímek obrazovky zobrazující stránku vlastností se zvýrazněným polem s ID skupiny](../media/mtp/aad_group_object_id.png)

Jakmile tyto informace získáte, obraťte se na podporu Lookout (e-mail: enterprisesupport@lookout.com).

Podpora Lookout použije k registraci vašeho předplatného a vytvoření účtu Lookout MTP Enterprise váš primární kontakt na základě poskytnutých informací.


## Konfigurace předplatného pro Lookout MTP
### Krok 1: Nastavení MTP
Jakmile vám podpora Lookout vytvoří účet Lookout MTP Enterprise, budete se moct přihlásit ke konzole Lookout MTP.   Na adresu primárního kontaktu vaší firmy Lookout odešle e-mail s odkazem na přihlašovací stránku: https://aad.lookout.com/les?action=consent

Při prvním přihlášení ke konzole Lookout MTP musíte použít uživatelský účet, který má v Azure AD roli globálního správce, protože to Lookout MTP potřebuje pro registraci tenanta Azure AD.   Při dalším přihlašování už tato úroveň oprávnění ke službě Azure AD není třeba.  Při prvním přihlášení se zobrazí stránka pro odsouhlasení podmínek. Vyberte možnost **přijmout** a dokončete registraci.

![snímek obrazovky zobrazující přihlašovací stránku ke konzole Lookout MTP](../media/mtp/lookout_mtp_initial_login.png) Jakmile odsouhlasíte podmínky, budete přesměrováni do konzoly Lookout MTP. Při dalším přihlašování po počáteční registraci můžete používat tuto adresu URL: https://aad.lookout.com

Pokud se při přihlašování setkáte s problémy, přečtěte si [článek pro řešení potíží](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

Další kroky popisují úkoly, které je třeba udělat k dokončení nastavení služby Lookout MTP v rámci [konzoly Lookout MTP](https://aad.lookout.com).

### Krok 2: Konfigurace konektoru Intune

Přejděte v konzole Lookout MTP do modulu **Systém**, vyberte kartu **Konektory** a možnost **Intune**.

![snímek obrazovky zobrazující konzolu Lookout MTP s otevřenou kartou konektorů a zvýrazněnou možností Intune](../media/mtp/lookout_mtp_setup-intune-connector.png)

V nastavení připojení nakonfigurujte frekvenci prezenčního signálu v minutách.  Jakmile tento krok dokončíte, bude konektor Intune připravený.  

![snímek obrazovky zobrazující kartu nastavení připojení, na které je nakonfigurovaná frekvence prezenčního signálu](../media/mtp/lookout-mtp-connection-settings.png)

### Krok 3: Konfigurace skupin pro registraci
V nastavení **Správa registrace** definujte skupinu uživatelů, jejichž zařízení mají být zaregistrována ve službě Lookout.   Osvědčeným postupem je otestovat postup s malou skupinou uživatelů a seznámit se tak s tím, jak integrace funguje.  Jakmile budete spokojeni s výsledky testování, můžete registraci rozšířit na další skupiny uživatelů.

Se skupinami pro registraci začněte tak, že nejdříve definujte skupinu zabezpečení Azure AD, která bude obsahovat první skupinu uživatelů vhodnou k registraci do služby Lookout MTP. Jakmile skupinu v Azure AD vytvoříte, přejděte v konzole Lookout MTP do nastavení **Správa registrace** a přidejte **Zobrazované názvy** skupiny zabezpečení Azure AD pro registraci.

Pokud je uživatel ve skupině pro registraci, všechna jeho identifikovaná a podporovaná zařízení v Azure AD se zaregistrují a bude u nich možné aktivovat ochranu Lookout MTP.  Podporované zařízení se aktivuje ve chvíli, kdy se na něm poprvé otevře aplikace Lookout for Work.
![snímek obrazovky zobrazující stránku registrace konektoru Intune](../media/mtp/lookout-mtp-enrollment.png)

Osvědčeným postupem je ponechat interval vyhledávání nových zařízení na výchozí hodnotě 5 minut.

>[!IMPORTANT]
> U zobrazovaného názvu se rozlišují velká a malá písmena.  Použijte **Zobrazovaný název**, který se zobrazuje na stránce **Vlastnosti** skupiny zabezpečení na webu Azure Portal. Na obrázku níže si všimněte, že zobrazovaný název na stránce **Vlastnosti** skupiny zabezpečení je zapsaný podle konvence camelCase.  Nadpis se ale zobrazuje malými písmeny, proto ho do konzoly Lookout MTP nezadávejte.
>![snímek obrazovky zobrazující Azure Portal, službu Azure Active Directory a stránku vlastností](../media/mtp/aad-group-display-name.png)

Aktuální verze má následující omezení:  
* Není k dispozici žádné ověřování zobrazovaných názvů skupin.  Ujistěte se, že používáte hodnotu z pole **ZOBRAZOVANÝ NÁZEV** na webu Azure Portal pro skupinu zabezpečení Azure AD.
* Vytváření skupin v rámci skupin není aktuálně podporováno.  Zadané skupiny zabezpečení Azure AD by měly obsahovat pouze uživatele, ne vnořené skupiny.


### Krok 4: Konfigurace synchronizace stavu
V nastavení **Synchronizace stavu** určete typ dat odesílaných do Intune.  V současné době je nutné povolit stav zařízení i stav hrozby, aby integrace Lookout se službou Intune fungovala správně.  Ve výchozím nastavení jsou tyto možnosti povolené.
### Krok 5: Konfigurace informací o příjemci e-mailů se zprávami o chybách
V nastavení **Správa chyb** zadejte e-mailovou adresu příjemce, který má dostávat zprávy o chybách.

![snímek obrazovky zobrazující stránku správy chyb konektoru Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Krok 6: Konfigurace e-mailových oznámení
Pokud chcete dostávat e-mailová upozornění na hrozby, přihlaste se ke [konzole Lookout MTP](https://aad.lookout.com) pomocí uživatelského účtu, na kterém chcete přijímat oznámení.  Přejděte do modulu **Systém** a na kartě **Předvolby** vyberte požadovaná oznámení a nastavte u nich hodnotu **Zapnuto**. Uložte provedené změny.

![snímek obrazovky zobrazující stránku předvoleb se zobrazeným uživatelským účtem](../media/mtp/lookout-mtp-email-notifications.png) Pokud už určitá e-mailová oznámení dostávat nechcete, nastavte u nich hodnotu **Vypnuto** a provedené změny uložte.
### Krok 7: Konfigurace klasifikace hrozeb
Lookout MTP klasifikuje mobilní hrozby podle různých typů. [Klasifikace hrozeb služby Lookout MTP](http://personal.support.lookout.com/hc/en-us/articles/114094130693) k nim má přiřazené výchozí úrovně rizika. Ty lze kdykoli změnit tak, aby odpovídaly požadavkům vaší společnosti.

![snímek obrazovky zobrazující stránku zásad s hrozbami a klasifikací](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Úrovně rizik, které jsou zde zadané, jsou důležitou součástí ochrany MTP, protože integrace s Intune vypočítává míru dodržování předpisů u zařízení za běhu právě podle těchto úrovní rizik. Jinými slovy, správce Intune nastaví v zásadách pravidlo, které určí, že zařízení nesplňuje předpisy, pokud pro něj existuje aktivní hrozba minimálně nízké/střední/vysoké úrovně. Zásady klasifikace hrozeb v MTP přímo řídí výpočet dodržování předpisů zařízení v Intune.

## Sledování registrací
Po dokončení nastavení začne Lookout MTP posílat do služby Azure AD dotazy na zařízení, která odpovídají určeným skupinám pro registraci.  Informace o registrovaných zařízeních najdete v modulu Zařízení.  Počáteční stav u zařízení je čekající na vyřízení.  Stav zařízení se změní, jakmile se na zařízení nainstaluje, otevře a aktivuje aplikace Lookout for Work.  Podrobnosti o tom, jak aplikaci Lookout for Work přidat do zařízení, najdete v tématu o [konfiguraci a nasazení aplikace Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## Další kroky
[Povolení připojení Lookout MTP k Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->


