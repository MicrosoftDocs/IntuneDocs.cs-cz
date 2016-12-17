---
title: "Registrace 30denní bezplatné zkušební verze Microsoft Intune | Microsoft Docs"
description: "Registrace a nastavení 30denního bezplatného testování Microsoft Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: a65ead23e62870647245120d1663706fc46810ac


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registrace bezplatné zkušební verze Microsoft Intune
Tento článek vás provede procesem registrace zkušební verze Intune a pomůže vám ve zkušební verzi nastavit uživatele, abyste mohli postupovat podle příručky pro testování a vyzkoušet si, jak se v Intune spravují mobilní zařízení. <!---or app data when devices are not enrolled in Intune.--->

## <a name="assumptions"></a>Předpoklady
Tento článek o registraci a příručka pro testování předpokládají, že zkušební verzi používáte jenom pro účely vyhodnocení a poté, co se přihlásíte k odběru, plánujete použít čisté prostředí.

Abychom vám usnadnili použití zkušební verze, nastavíme velmi jednoduché prostředí, které bude používat jenom Intune a které předpokládá, že toto bude jedinou metodou správy zařízení (označovanou jako autorita pro správu mobilních zařízení). V příručce vás však budeme odkazovat na podrobnější technické informace pro případ, že se budete chtít dovědět více.

Ve zkušební verzi můžete provádět vše, co je možné i v placené verzi. Jediným rozdílem je omezení zkušební verze na 100 uživatelských účtů.

## <a name="sign-up-for-your-trial"></a>Zaregistrování zkušební verze
Přejděte na stránku [registrace Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) a vyplňte formulář pro registraci zkušebního předplatného.

Pokud máte pracovní nebo školní účet a chcete ho použít pro zkušební verzi Intune, postupujte místo toho podle [těchto pokynů pro přihlášení](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). V tomto článku a příručce pro testování se však předpokládá, že takový účet nepoužíváte.

> [!TIP]
> Pokud se většina pracovníků IT oddělení a uživatelů nachází v jiném národním prostředí než vy, můžete u vaší zkušební verze nastavit toto národní prostředí za účelem testování výkonu.

### <a name="post-sign-up-considerations"></a>Aspekty ke zvážení po registraci
Když se zaregistrujete ke zkušební verzi, přijde vám na e-mailovou adresu, kterou jste zadali při registraci, e-mailová zpráva s informacemi o vašem účtu. Ta potvrzuje, že je vaše zkušební verze aktivní.

Po dokončení procesu registrace budete přesměrováni na stránku, na které můžete přidat uživatele a přiřadit jim licence pomocí Centra pro správu Office 365. Při příštím přihlášení do Intune budete automaticky přesměrováni do konzoly pro správu Intune.

## <a name="keeping-the-admin-center-and-the-intune-administration-console-straight"></a>Přehled používání Centra pro správu a konzoly pro správu Intune
Existují dva portály, které budete používat pro Intune: Centrum pro správu Office 365 ([portal.office.com](https://portal.office.com)) a konzola pro správu Intune ([manage.microsoft.com](https://manage.microsoft.com)).

Obvykle budete používat konzolu pro správu Intune, kterou vidíte dole. To je web, na kterém se nastavují a spravují skupiny, zásady, zařízení a aplikace.

![Obrázek konzoly pro správu Intune](./media/sign-up/intune-admin-console.png)

Přidávat a spravovat uživatele a pracovat s dalšími aspekty vašeho účtu včetně fakturace a podpory ale budete pomocí Centra pro správu Office 365, které vidíte dole.

![Obrázek Centra pro správu Office 365](./media/sign-up/office-admin-center.png)

Z Centra pro správu Office 365 můžete přejít do Konzoly správce Intune. Odkazy na centra pro správu se nachází pod poslední položkou v levém navigačním podokně. Pokud zvolíte **Intune**, otevře se v nové záložce Konzola správce Intune.

![Obrázek odkazu na konzolu pro správu Intune](./media/sign-up/link-to-intune.png)

Pokud chcete z Intune přejít zpátky do Centra pro správu Office 365, zvolte **Přidat uživatele** na stránce Přehled skupin.

![Obrázek odkazu zpět na Centrum pro správu Office 365](./media/sign-up/task-add-users.png)

## <a name="add-users"></a>Přidávání uživatelů
Než přejdete z Centra pro správu Office 365 do Intune, je třeba přidat uživatele ke zkušebnímu účtu.

V Centru pro správu Office 365 můžete přidávat uživatele jednotlivě nebo hromadně načtením souboru .csv. Při nastavení vaší zkušební verze použijeme obě možnosti. V produkčním prostředí budete však pravděpodobně chtít využít uživatelské účty služby Azure Active Directory. O této možnosti se můžete dozvědět více v [Příručce Začínáme](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) a v části [Další kroky](#Next-steps) v tomto článku.

### <a name="add-an-individual-user"></a>Přidání jednotlivého uživatele
1. Zvolte některou z možností přidání uživatele a otevřete formulář, který umožňuje vytvořit uživatele. Požadované jsou jenom položky s hvězdičkou (\*).
![Obrázek možností tlačítka pro přidání uživatelů](./media/sign-up/add-user.png)


2.  Když přidáte uživatele, odešlete mu v posledním kroku e-mail s dočasným heslem Intune. Pro účely vyhodnocení použijte svoji vlastní pracovní e-mailovou adresu, aby vám přišly přihlašovací údaje a mohli jste si prohlédnout e-mail, který budou dostávat vaši uživatelé. Potom můžete tyto identity uživatelů použít k registraci testovacích zařízení.<br/>

 ![Obrázek posledního kroku přidání uživatele](./media/sign-up/new-user-2.png)

3. Pokud chcete vytvořenému uživateli přiřadit roli správce, můžete tuto roli upravit v Centru pro správu Office 365, kde ze seznamu uživatelů vyberete uživatelské jméno tohoto uživatele a pak zvolíte možnost **Upravit** v řádku Role. Zobrazí se seznam rolí uživatelů, které můžete vybrat a přiřadit tomuto uživateli.

 ![Obrázek možností rolí uživatele](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Import více uživatelů
1. V seznamu **Další** najdete průvodce pro import více uživatelů.

 ![Obrázek možnosti přidat více uživatelů](./media/sign-up/add-multiple-users.png)

2. Pokud chcete pomoci se správným nastavením souboru .csv, můžete si stáhnou šablonu, do které přidáte data uživatelů. Stáhněte si soubor .csv se záhlavími a ukázkovými informacemi o uživatelích, ve kterém uvidíte, jaká data jsou potřeba pro jednotlivá pole.

 ![Obrázek prvního kroku v průvodci hromadnou registrací](./media/sign-up/bulk-enroll-step-1.png)


3. Jakmile vytvoříte a uložíte svůj soubor .csv, zvolte **Procházet** a tento soubor vyberte. Ověřte výběr a zvolte **Další**. Uživatelé se načtou a přidají do vašeho seznamu aktivních uživatelů.

Nyní přejděte do Konzoly správce Intune, kde můžete začít spravovat své uživatele a jejich zařízení a aplikace.

> [!NOTE]
> Uživatelé se v Intune nezobrazí, dokud si nezaregistrují zařízení, které má být spravováno.

## <a name="next-steps"></a>Další kroky
Scénář hodnocení: [Hodnocení správy mobilních zařízení v Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

Přečtěte si další informace o používání uživatelských účtů služby Azure Active Directory v Intune:
- [Požadavky na identity](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Požadavky na synchronizaci adresáře](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Požadavky na vícefaktorové ověřování](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Přečtěte si další informace o používání [Intune s nástrojem System Center Configuration Manager.](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)



<!--HONumber=Dec16_HO2-->


