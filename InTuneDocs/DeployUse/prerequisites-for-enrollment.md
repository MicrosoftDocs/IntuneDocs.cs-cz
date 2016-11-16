---
title: "Požadavky na registraci mobilních zařízení | Microsoft Intune"
description: "Nastavte požadavky správy mobilních zařízení a připravte registraci různých operačních systémů."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 391612c35a7665073ca8a5c629169e5be967ab59


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Požadavky na správu mobilních zařízení v Intune
Pokud chcete zaměstnancům povolit registraci mobilních zařízení s Intune, proveďte následující kroky. Stejné kroky je třeba podniknout i v případě správy zařízení ve vlastnictví společnosti.

|Kroky|Podrobnosti|  
|-----------|-------------|  
|**Krok 1:** [Povolení připojení](#step-1-enable-connections)|Zkontrolujte, zda máte nakonfigurovaný název domény a zda je připravena síťová komunikace|  
|**Krok 2:** [Nastavení autority pro správu mobilních zařízení (MDM)](#step-2-set-mdm-authority)|Autorita pro správu mobilních zařízení definuje služby přiřazené k vašim zařízením|
|**Krok 3:** [Vytvoření skupin](#step-3-create-groups)|Nakonfigurování uživatelského nastavení pro aplikaci Portál společnosti|  
|**Krok 4:** [Konfigurace Portálu společnosti](#step-4-configure-company-portal)|Nakonfigurování uživatelského nastavení pro aplikaci Portál společnosti|  
|**Krok 5:** [Přiřazení licencí uživatelům](#step-5-assign-user-licenses)|Přiřazení licencí Intune uživatelům, aby mohli zaregistrovat zařízení|
|**Krok 6:** [Povolení registrace](#step-6-enable-enrollment)|Povolte nastavení správy systému iOS a Windows, specifické pro platformu. U zařízení Android není žádná další konfigurace zapotřebí.|
|**Krok 7:** [Další kroky](#step-7-next-steps)|Povolte nastavení správy systému iOS a Windows, specifické pro platformu. U zařízení Android není žádná další konfigurace zapotřebí.|

Hledáte Intune s Configuration Managerem?
> [!div class="button"]
[Zobrazit dokumentaci k SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Krok 1: Povolení připojení

Ještě než povolíte registraci mobilních zařízení, zkontrolujte, zda jste provedli následující:
- [Kontrola požadovaných síťových adres URL a portů](../get-started/network-infrastructure-requirements-for-microsoft-intune)
- [Přidání a ověření názvu domény](../get-started/domain-names-for-microsoft-intune)

## <a name="step-2-set-mdm-authority"></a>Krok 2: Nastavení autority pro správu mobilních zařízení (MDM)
Autorita MDM definuje službu správy s oprávněním ke správě skupiny zařízení. Příklady možných autorit MDM zahrnují Intune samostatně a Configuration Manager s Intune. Pokud nastavíte Configuration Manager jako autoritu správy, ke správě mobilních zařízení nejde použít žádnou jinou službu.

>[!IMPORTANT]
> Důkladně zvažte, jestli chcete spravovat mobilní zařízení jenom pomocí Intune (online služba), nebo pomocí System Center Configuration Manageru s Intune (místní softwarové řešení ve spojení s online službou). Když nastavíte autoritu správy mobilních zařízení, už ji nemůžete změnit.



1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) zvolte **Správce** &gt; **Správa mobilních zařízení**.

2.  V seznamu **Úkoly** klikněte na **Nastavit autoritu pro správu mobilních zařízení**. Otevře se dialogové okno **nastavení autority pro správu mobilních zařízení** .

    ![Dialogové okno nastavení autority pro správu mobilních zařízení](../media/intune-mdm-authority.png)

3.  Intune požádá o potvrzení, že chcete Intune používat jako autoritu pro správu mobilních zařízení. Jestli chcete ke správě mobilních zařízení používat Microsoft Intune, zaškrtněte políčko a zvolte **Ano**.

## <a name="step-3-create-groups"></a>Krok 3: Vytvoření skupin

Když vytvoříte skupiny uživatelů a zařízení, zjednodušíte tím správu a zlepšíte cílení nasazených aplikací, zásad a prostředků společnosti. [Přečtěte si, jak vytvářet skupiny.](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups)

## <a name="step-4-configure-company-portal"></a>Krok 4: Konfigurace Portálu společnosti

Portál společnosti v Intune je místem, kde uživatelé přistupují k podnikovým datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.

> [!TIP]
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti.

Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Pro přizpůsobení se přihlaste do [konzoly správce Microsoft Intune](https://manage.microsoft.com) jako tenant nebo správce služby, zvolte **Správce** &gt; **Portál společnosti** a konfigurujte nastavení portálu společnosti.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Kontaktní informace společnosti a prohlášení o zásadách ochrany osobních údajů

Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Kontaktní informace a podrobnosti se uživatelům zobrazí na obrazovce Kontakt na IT v Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.

|Název pole|Maximální délka|Další informace|
    |----------|------------------------|----------------|
    |Název společnosti|40|Tento název se zobrazí v záhlaví okna Portálu společnosti. **Poznámka:**: povolené jsou jen alfanumerické znaky. Toto pole nepodporuje speciální znaky.|
    |Jméno kontaktní osoby oddělení IT|40|Tento název se zobrazí na stránce **Kontakt na IT**.|
    |Telefonní číslo oddělení IT|20|Toto kontaktní číslo se zobrazí na stránce **Kontakt na IT**.|
    |E-mailová adresa oddělení IT|40|Tato kontaktní adresa se zobrazí na stránce **Kontakt na IT**. Je potřeba zadat platnou e-mailovou adresu ve formátu **alias@domainname.com**.|
    |Další informace|120|Tyto informace se zobrazí na stránce **Kontakt na IT**.|
    |Adresa URL prohlášení o zásadách ochrany osobních údajů společnosti|79|Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Pole musí obsahovat platnou adresu URL ve formátu https://www.contoso.com.|

### <a name="support-contacts"></a>Kontaktní údaje podpory
Web podpory je zobrazen uživatelům v Portálu společnosti, aby jim umožnil přístup k online podpoře.

|Název pole|Maximální délka|Další informace|
    |----------|------------------------|----------------|
    |Adresa URL webu podpory|150|Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu https://www.contoso.com. Pokud adresu URL nezadáte, nezobrazí se na stránce **Kontakt na IT** v Portálu společnosti žádné informace o webu podpory.|
    |Název webu|40|Toto je popisný název, který se zobrazí pro adresu URL webu podpory. Pokud zadáte adresu URL webu podpory bez popisného názvu, zobrazí se na stránce **Kontakt na IT** v Portálu společnosti text **Přejít na web IT**.|


### <a name="company-branding-customization"></a>Přizpůsobení obchodní značky

Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.

|Název pole|Další informace|
    |----------|----------------|
    |Barva motivu|Vyberte barvu motivu, kterou chcete použít pro Portál společnosti.|
    |Zahrnout logo společnosti|Povolení této možnosti vám umožní nahrát vlastní logo společnosti, které se bude zobrazovat v Portálu společnosti. Můžete nahrát dvě loga – jedno, které se zobrazí, když bude pozadí Portálu společnosti bílé, a druhé, které se zobrazí, když se bude pro pozadí Portálu společnosti používat vybraná barva motivu. Loga musí být ve formátu .png nebo .jpg o maximálním rozlišení 400 × 100 pixelů a nesmí být větší než 750 kB.|
    |Volba pozadí pro aplikaci portálu společnosti|Toto nastavení má vliv jenom na pozadí aplikace Portál společnosti.|


Po uložení změn můžete pomocí odkazů uvedených v dolní části stránky **Portál společnosti** v konzole pro správu zobrazit web Portál společnosti. Tyto odkazy se nedají změnit. Když se uživatel přihlásí, tyto odkazy zobrazí vaše předplatná v Portálu společnosti.

## <a name="step-5-assign-user-licenses"></a>Krok 5: Přiřazení licencí uživatelům

**Portál pro správu Office 365** můžete použít k ručnímu přidání cloudových uživatelů a přiřazení licencí účtům cloudových uživatelů i účtům, které se synchronizovaly z místní služby Active Directory do Azure Active Directory (Azure AD). Můžete [synchronizovat místní uživatele s Azure AD](../get-started/domain-names-for-microsoft-intune#to-synchronize-on-premises-users-with-azure-ad.md).

1.  Přihlaste se na [portál pro správu Office 365](https://portal.office.com/Admin/Default.aspx) pomocí svých přihlašovacích údajů správce tenanta.

2.  Vyberte uživatelský účet, kterému chcete přiřadit uživatelskou licenci pro Intune, a ve vlastnostech tohoto uživatelského účtu zaškrtněte políčko **Microsoft Intune**.

3.  Uživatelský účet se teď přidá do skupiny uživatelů Microsoft Intune, která uděluje uživatelům oprávnění k používání služby a registraci zařízení do systému správy.

### <a name="to-synchronize-onpremises-users-with-azure-ad"></a>Synchronizace místních uživatelů s Azure AD

1. [Přidejte příponu UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) pro vaši vlastní doménu v místním Active Directory.
2. Nastavte novou příponu UPN pro místní uživatele, které chcete importovat.
3. Spusťte [synchronizaci Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) a proveďte integraci místních uživatelů s Azure AD.
4. Po úspěšné synchronizaci informací o uživatelských účtech můžete prostřednictvím [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) přiřadit licence Microsoft Intune.

## <a name="step-6-enable-enrollment"></a>Krok 6: Povolení registrace
Po nastavení autority správy mobilních zařízení musíte nastavit správu zařízení pro operační systémy, které vaše organizace hodlá podporovat. Kroky při nastavení správy zařízení se liší v závislosti na operačním systému. Operační systém Android například v konzole pro správu Intune nevyžaduje žádné akce. Operační systémy Windows a iOS naopak pro umožnění správy vyžadují vztah důvěryhodnosti mezi zařízením a Intune.

Nastavte správu pro následující platformy:
- [iOS a Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Stolní a přenosné počítače s Windows](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile a Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

Můžete také povolit [registraci zařízení vlastněných společností](manage-corporate-owned-devices).

## <a name="step-7-next-steps"></a>Krok 7: Další kroky

Po povolení registrace doporučujeme nastavit správu, aby vyhovovala potřebám vašeho podniku. Příklady možností správy:

- [Nasazení zásad, které spravují nastavení a funkce zařízení](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Povolení přístupu k prostředkům společnosti, jako je e-mail, Wi-Fi a VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Přidání aplikací](add-apps.md) a [nasazení aplikací](deploy-apps.md) do spravovaných zařízení
- [Vytvoření zásad dodržování předpisů pro zařízení](introduction-to-device-compliance-policies-in-microsoft-intune.md) a [omezení přístupu podle dodržování předpisů](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


