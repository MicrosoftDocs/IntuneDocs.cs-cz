---
title: "Omezení přístupu k SharePointu Online | Dokumentace Microsoftu"
description: "Chraňte a řiďte přístup k podnikovým datům na SharePointu Online pomocí podmíněného přístupu."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 6b900f2bf41ea84088f8453f59b71136e013a884


---

# <a name="restrict-access-to-sharepoint-online-with-microsoft-intune"></a>Omezení přístupu ke službě SharePoint Online pomocí Microsoft Intune
Pro řízení přístupu k souborům umístěným v SharePointu Online použijte podmíněný přístup [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].
Podmíněný přístup má dvě součásti:
- Zásady dodržování předpisů zařízení, které zařízení musí dodržovat, aby mohlo být považované za vyhovující
- Zásady podmíněného přístupu, kde můžete určit podmínky, které zařízení musí splňovat pro přístup ke službě
Další informace o tom, jak podmíněný přístup funguje, najdete v tématu o [omezení přístupu k e-mailu, O365 a dalším službám](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Nasadíte zásady dodržování předpisů a podmíněného přístupu pro uživatele. Dodržování zásad se kontroluje u každého zařízení, které uživatel používá pro přístup ke službám.

Když se uživatel na svém zařízení pokusí připojit k souboru pomocí podporované aplikace, jako je třeba OneDrive, dojde k následujícímu vyhodnocení:

![Diagram zobrazující průběh rozhodování, jestli má zařízení povolený přístup k SharePointu, nebo je zablokované](../media/ConditionalAccess8-6.png)


**Dřív** než nakonfigurujete zásady podmíněného přístupu pro SharePoint Online, musíte:
- Mít předplatné **SharePointu Online** a uživatelé musí mít licenci pro SharePoint Online.
- Mít **předplatné Enterprise Mobility + Security (EMS)** nebo **předplatné Azure Active Directory (Azure AD) Premium** a uživatelé musí mít licenci pro EMS nebo Azure AD. Další informace najdete na [stránce s cenami služby Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) nebo na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


  Pro připojení k požadovaným souborům zařízení musí být:
-   **Zaregistrované** ve službě [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nebo se musí jednat o počítač připojený k doméně

-   **Zaregistrované** v Azure Active Directory (k tomu automaticky dojde při registraci zařízení ve službě [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).


-   **V souladu** s veškerými nasazenými zásadami dodržování předpisů služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]

Stav zařízení je uložený ve službě Azure Active Directory, která uděluje nebo blokuje přístup k souborům na základě podmínek, které zadáte.

Pokud není některá podmínka splněná, zobrazí se uživateli při přihlášení jedna z následujících zpráv:

-   Pokud zařízení není zaregistrované v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nebo v Azure Active Directory, zobrazí se zpráva s pokyny pro instalaci aplikace Portál společnosti a registraci.

-   Pokud zařízení není kompatibilní, zobrazí se zpráva, která uživatele přesměruje na web Portál společnosti [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] , kde najde informace o problému a jeho řešení.

**Podmíněný přístup se nevztahuje na externí sdílení**. Informace o tom, jak zabránit externímu sdílení ve vašem tenantovi nebo kolekci webů, najdete v tématu [Správa externích sdílení pro prostředí SharePointu Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US).

>[!NOTE]
>Pokud povolíte podmíněný přístup pro SharePoint Online, doporučujeme zakázat doménu v seznamu, jak je popsané v tématu [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/en-us/library/dn917451.aspx).  

## <a name="support-for-mobile-devices"></a>Podpora mobilních zařízení
Podporované systémy:
- iOS 8.0 a novější
- Android 4.0 nebo novější, Samsung Knox Standard 4.0 nebo novější
- Windows Phone 8.1 nebo novější

Můžete omezit přístup k SharePointu Online, když k němu zařízení s **iOSem** a **Androidem** přistupují z prohlížeče. Přístup je povolený jenom z podporovaných prohlížečů na vyhovujících zařízeních:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS a Android 5.0 nebo novější)

**Nepodporované prohlížeče jsou zablokované**.

## <a name="support-for-pcs"></a>Podpora počítačů
Podporované systémy:
- Windows 8.1 nebo novější (když jsou počítače zaregistrované v Intune)
- Windows 7.0, Windows 8.1 nebo Windows 10 (když jsou počítače připojené k doméně)
> [!NOTE]
>Pokud chcete použít podmíněný přístup u počítačů s Windows 10, musíte je aktualizovat na verzi Windows 10 Anniversary Update.

  - U počítačů připojených k doméně musíte nastavit [automatickou registraci](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) v Azure Active Directory. Pro zákazníky Intune a Office 365 je služba Azure AD Device Registration Service aktivovaná automaticky. Zákazníci, kteří už mají nasazenou službu ADFS Device Registration Service, registrovaná zařízení ve svojí místní službě Active Directory neuvidí.

  - Pokud je zásada nastavená tak, aby vyžadovala připojení k doméně, a počítač k doméně připojený není, zobrazí se zpráva, aby uživatel kontaktoval správce IT.

  - Pokud je zásada nastavená tak, aby vyžadovala připojení k doméně nebo splňování předpisů, a počítač ani jeden z těchto požadavků nesplňuje, zobrazí se zpráva s pokyny, jak nainstalovat aplikaci Portál společnosti a provést registraci.
  >[!NOTE]
  >Podmíněný přístup není podporovaný na počítačích, ve kterých běží klient Intune pro počítače.

[Musí být povolené moderní ověřování Office 365](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) a musí být nainstalované všechny nejnovější aktualizace Office.

Moderní ověřování poskytuje klientům Office 2013 Windows přihlašování založené na ADAL (Active Directory Authentication Library) a umožňuje lepší zabezpečení, jako je **vícefaktorové ověřování** a **ověřování prostřednictvím certifikátu**.


## <a name="configure-conditional-access-for-sharepoint-online"></a>Konfigurace podmíněného přístupu pro SharePoint Online

### <a name="step-1-configure-active-directory-security-groups"></a>Krok 1: Konfigurace skupin zabezpečení služby Active Directory
Než začnete, nakonfigurujte pro skupiny zabezpečení služby Azure Active Directory zásadu podmíněného přístupu. Tyto skupiny můžete nakonfigurovat v **Centru pro správu Office 365**nebo na **Portálu účtů Intune**. Tyto skupiny se použijí k zahrnutí nebo vyloučení uživatelů ze zásad. Pokud na uživatele cílí zásada, musí každé jím používané zařízení zásadu splňovat, aby mělo přístup k prostředkům.

V rámci zásad SharePointu Online můžete zadat dva typy skupin:

-   **Cílové skupiny**: Obsahují skupiny uživatelů, pro které zásady platí.

-   **Vyloučené skupiny**: Obsahují skupiny uživatelů, kteří jsou ze zásady vyloučení.

Pokud je uživatel v obou skupinách, bude ze zásad vyloučený.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Krok 2: Konfigurace a nasazení zásad dodržování předpisů
Pokud jste to ještě neudělali, vytvořte zásadu dodržování předpisů a nasaďte ji pro uživatele, na které cílí zásada SharePointu Online.

> [!NOTE]
> Zásady dodržování předpisů se nasadí do skupin [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a zásady podmíněného přístupu cílí na skupiny zabezpečení služby Azure Active Directory.

Podrobnosti o konfiguraci zásad dodržování předpisů najdete v tématu o [vytvoření zásad dodržování předpisů](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> Pokud jste zásady dodržování předpisů nenasadili, jsou zařízení považována za zařízení vyhovující zásadám dodržování předpisů.

Až budete připravení, pokračujte **Krokem 3**.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>Krok 3: Konfigurace zásad SharePointu Online
V dalším kroku nakonfigurujte zásadu, která bude vyžadovat, aby měla k SharePointu Online přístup jenom spravovaná zařízení, která jsou v souladu s předpisy. Tato zásada je uložená v Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> Můžete také vytvořit zásady podmíněného přístupu pro zařízení s Intune v konzole pro správu Azure AD (zásady se v Azure AD označují jako **zásady podmíněného přístupu na základě zařízení**). Kromě toho můžete vytvořit další zásady podmíněného přístupu, třeba vícefaktorové ověřování. Také můžete nastavit zásady podmíněného přístupu pro podnikové aplikace třetích stran, které Azure AD podporuje, například Salesforce nebo Box. Další informace najdete v tématu [Jak ve službě Azure Active Directory nastavit zásady podmíněného přístupu založené na zařízení a získat tak kontrolu přístupu do aplikací napojených na službu Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** > **Podmíněný přístup** > **Zásady pro SharePoint Online**.
![Snímek stránky zásad SharePointu Online](../media/mdm-ca-spo-policy-configuration.png)

2.  Vyberte **Zapnout zásady podmíněného přístupu pro SharePoint Online**.

3.  V části **Přístup k aplikaci** můžete použít zásady podmíněného přístupu na:

    -   **Všechny platformy**

        To vyžaduje, aby každé zařízení používané pro přístup k **SharePointu Online** bylo registrované v Intune a dodržovalo tyto zásady. Všechny klientské aplikace používající **moderní ověřování** podléhají zásadám podmíněného přístupu. Pokud Intune příslušnou platformu aktuálně nepodporuje, přístup k **SharePointu Online** je zablokovaný.

        Výběr volby **Všechny platformy** způsobí, že Azure Active Directory tyto zásady uplatní na všechny požadavky na ověření bez ohledu na platformu, která je ohlášena klientskou aplikací. Všechny platformy musí být zaregistrované a vyhovující s těmito výjimkami:
        *   Zařízení s Windows, která musejí být zaregistrovaná a vyhovující, připojená k doméně s místním Active Directory nebo obojí
        * Nepodporované platformy jako Mac. Aplikace používající moderní ověřování pocházející z těchto platforem jsou ale i nadále zablokované.

    -   **Specifické platformy**

         Zásady podmíněného přístupu platí pro každou klientskou aplikaci, která na určených platformách zařízení používá moderní ověřování.

     Počítače s Windows musí být připojené k doméně nebo zaregistrované v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a v souladu s předpisy. Můžete nastavit následující požadavky:

     -   **Zařízení musí být připojené k doméně nebo splňovat předpisy.** Tuto možnost vyberte, pokud chcete vyžadovat, že počítače musejí být připojené k doméně nebo splňovat zásady nastavené v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Pokud počítač některý z těchto požadavků nesplňuje, zobrazí se uživateli výzva registraci zařízení v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Zařízení musí být připojené k doméně.** Tuto možnost vyberte, pokud chcete, aby počítače musely být pro přístup k Exchangi Online připojené k doméně. Pokud počítač není připojený k doméně, je přístup k e-mailu blokovaný a uživateli se zobrazí výzva, aby se obrátil na správce IT.

     -   **Zařízení musí splňovat předpisy.** Tuto možnost vyberte, pokud chcete, aby počítače musely být zaregistrované v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a splňovat předpisy. Pokud počítač není zaregistrovaný, zobrazí se zpráva s pokyny, jak registraci provést.

4.   V části **Přístup z prohlížeče** pro SharePoint Online a OneDrive pro firmy můžete zvolit povolení přístupu k Exchangi Online jen prostřednictvím podporovaných prohlížečů: Safari (iOS) a Chrome (Android). Přístup z jiných prohlížečů je blokovaný. Omezení platformy, která jste vybrali pro přístup z aplikace pro OneDrive, budou použitá i zde.

  V zařízeních s **Androidem** musí uživatelé povolit přístup z prohlížeče. K tomu musí uživatel v zaregistrovaném zařízení zvolit možnost **Povolit přístup z prohlížeče** následujícím způsobem:
  1.    Otevřete aplikaci **Portál společnosti**.
  2.    Přejděte na stránku **Nastavení** prostřednictvím tlačítka se třemi tečkami (...) nebo hardwarového tlačítka nabídky.
  3.    Stiskněte tlačítko **Povolit přístup z prohlížeče**.
  4.    V prohlížeči Chrome se odhlaste z Office 365 a znovu spusťte Chrome.

  V platformách **iOS** a **Android** kvůli identifikaci zařízení použitého pro přístup ke službě vydá Azure Active Directory pro příslušné zařízení certifikát TLS (Transport Layer Security). Zařízení zobrazí certifikát s výzvou pro uživatele, aby vybral certifikát, jak je vidět na následujících snímcích obrazovky. Před tím, než bude moct používat prohlížeč, musí uživatel certifikát vybrat.

  **iOS**

  ![Snímek obrazovky s výzvou k výběru certifikátu na iPadu](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![Snímek obrazovky s výzvou k výběru certifikátu v zařízení s Androidem](../media/mdm-browser-ca-android-cert-prompt.png)
5.  V části **Cílové skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se zásady vztahují. Můžete cílit na všechny uživatele nebo vybranou skupinu uživatelů.

6.  V případě potřeby v části **Vyloučené skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se tyto zásady nevztahují.

7.  Po dokončení vyberte **Uložit**.

Zásady podmíněného přístupu nemusíte nasazovat, projeví se okamžitě.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>Krok 4: Sledování dodržování předpisů a zásad podmíněného přístupu
V pracovním prostoru **Skupiny** se můžete podívat na stav svých zařízení.

Vyberte libovolnou skupinu mobilních zařízení. Pak na kartě **Zařízení** zvolte jeden z následujících **Filtrů**:

-   **Zařízení nezaregistrovaná v AAD**: Tato zařízení mají přístup k SharePointu Online zablokovaný.

-   **Zařízení nevyhovující předpisům**: Tato zařízení mají přístup k SharePointu Online zablokovaný.

-   **Zařízení zaregistrovaná v AAD a vyhovující předpisům**: Tato zařízení mají k SharePointu Online přístup.

### <a name="see-also"></a>Související témata
[Omezení přístupu k e-mailu a službám O365 pomocí Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


