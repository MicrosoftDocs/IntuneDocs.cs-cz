---
title: Kurz – návod Intune na portálu Azure portal
titleSuffix: Microsoft Intune
description: V tomto kurzu se prohlédnete si Microsoft Intune, abyste lépe pochopit, jak provádět úlohy.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 01/31/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c733dbbf992ae10e14ba711b34e621d3f0fb3da8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395268"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Kurz: Návod služby Microsoft Intune na portálu Azure portal

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) obsahuje více než 100 služeb, abychom vám s širokou škálu cloud computingu scénáře a možnosti. Microsoft Intune je jednou z několika služeb dostupných v Azure. Intune vám pomůže zajistit, že zařízení, aplikace a data společnosti splňovat požadavky na zabezpečení vaší společnosti. Budete mít kontrolu sady, které je třeba zkontrolovat požadavky a co se stane, když tyto požadavky nejsou splněny. [Azure Portal](https://portal.azure.com) je místo, kde najdete službu Microsoft Intune. Princip funkce dostupné v Intune můžete provádět různé správy mobilních zařízení (MDM) a správu mobilních aplikací (MAM) úlohy.

V tomto kurzu provedete následující:
> [!div class="checklist"]
> * Tour Microsoft Intune
> * Konfigurace na webu Azure portal

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
Než budete nastavovat Microsoft Intune, projděte si následující požadavky:

   - [Podporované operační systémy a prohlížeče](supported-devices-browsers.md) 
   - [Požadavky týkající se konfigurace sítě a šířky pásma](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registrace bezplatné zkušební verze Microsoft Intune

Intune si můžete zdarma vyzkoušet. Zkušební doba je 30 dní. Pokud už máte svůj pracovní nebo školní účet, **přihlaste se** s jeho použitím a přidejte Intune k svému předplatnému. V opačném případě můžete [zaregistrovat Bezplatný zkušební účet](free-trial-sign-up.md) chcete Intune používat pro vaši organizaci.

> [!IMPORTANT]
> Když si zaregistrujete nový účet, nebude možné s ním kombinovat stávající pracovní nebo školní účet.

## <a name="tour-microsoft-intune"></a>Tour Microsoft Intune

Postupujte podle následujících kroků, abyste lépe pochopili Intune na portálu Azure portal. Až prohlídku dokončíte, budete mít lepší přehled některých hlavních oblastech služby Intune.

1. Otevřete prohlížeč a přihlaste se k [portál Intune](https://aka.ms/intuneportal). Pokud jste ještě do Intune, pomocí vašeho bezplatného zkušebního předplatného.

    ![Snímek obrazovky portálu Microsoft Intune](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Když v Azure otevřete Intune nebo jakoukoli jinou službu, objeví se v podokně. Některé z prvních úloh, můžete použít v Intune obsahují **zařízení**, **klientské aplikace**, **uživatelé**, a **skupiny**. Zatížení je jednoduše dílčí části služby. Při výběru úlohy se toto podokno otevře na celou stránku. Jiná podokna vysunou z pravé strany podokna při otevřít a zavřít zobrazit předchozí podokno. Podokno se také označuje jako okno. 

    Ve výchozím nastavení, když otevřete Intune uvidíte **přehled** podokně. V tomto podokně poskytuje celkový vizuální snímek stavu přiřazení a dodržování předpisů zařízení a také stav instalace aplikace.

2. Z [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** zobrazíte podrobnosti o zaregistrovaných zařízeních ve vašem tenantovi Intune. Pokud začínáte s nového tenanta Intune, nebudete mít všechna zaregistrovaná zařízení ještě. 

    ![Snímek obrazovky podokna registrace zařízení](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Intune umožňuje spravovat vaši pracovníci zařízení a aplikací, včetně způsobu jejich přístup k firemním datům. K používání této služby správy mobilních zařízení, musíte zařízení nejdřív zaregistrovaná v Intune. Když je zařízení zaregistrované, vystaví se mu certifikát MDM. Tento certifikát slouží ke komunikaci se službou Intune. 

    V Intune zaregistrovat zařízení zaměstnanců několika způsoby. Jednotlivé způsoby závisí na vlastnictví zařízení (osobní nebo firemní), typu zařízení (iOS, Windows, Android) a požadavcích na správu (resetování, spřažení, uzamčení). Ale předtím, než můžete povolit registraci zařízení, musíte vytvořit infrastruktury Intune. Registrace zařízení vyžaduje zejména [nastavení autority MDM](mdm-authority-set.md). Další informace o přípravě vašeho prostředí Intune (tenant) najdete v tématu [nastavenou službu Intune](setup-steps.md). Jakmile budete mít tenanta Intune připravená, můžete zařízení zaregistrovat. Další informace o registraci zařízení najdete v článku [Co je registrace zařízení?](device-enrollment.md)

3. Z [Intune](https://aka.ms/intuneportal)vyberte **dodržování předpisů zařízením** zobrazíte podrobnosti o dodržování předpisů pro zařízení spravovaná pomocí Intune. Zobrazí se podrobnosti podobně jako na následujícím obrázku.

    ![Snímek obrazovky podokna dodržování předpisů zařízení](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Požadavky na dodržování předpisů jsou v podstatě pravidla, jako je například vyžadování PIN kódu zařízení nebo šifrování zařízení. Zásady dodržování předpisů zařízeními definují pravidla a nastavení, která musí zařízení splňovat, aby bylo považováno za kompatibilní. Pokud chcete použít dodržování předpisů u zařízení, musíte mít:
    - Intune a předplatné Azure Active Directory (Azure AD) Premium
    - Zařízení se systémem na podporované platformě
    - Zařízení musí být zaregistrovaná v Intune
    - Zařízení, která jsou zaregistrovaná na jednoho uživatele nebo bez primárního uživatele.
    
    Další informace najdete v tématu [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

4. Z [Intune](https://aka.ms/intuneportal)vyberte **konfigurace zařízení** zobrazíte podrobnosti o profilech zařízení v Intune. 

    ![Snímek obrazovky podokna konfigurace zařízení](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Intune obsahuje nastavení a funkce, které můžete různým zařízením v organizaci povolit nebo zakázat. Tato nastavení a funkce se přidají do "konfiguračních profily". Můžete vytvořit profily pro různá zařízení a různé platformy, včetně iOS, Android a Windows. Potom můžete Intune použít profil pro zařízení ve vaší organizaci.   

    Další informace o konfiguraci zařízení najdete v tématu [nastavení funkcí v zařízeních pomocí profilů zařízení v Microsoft Intune](device-profiles.md).

5. Z [Intune](https://aka.ms/intuneportal)vyberte **zařízení** zobrazíte podrobnosti o Intune na tenanta zaregistrovaná zařízení. Pokud hodláte spustit novou zařazení Intune, nebudete mít všechna zaregistrovaná zařízení ještě. 

    ![Snímek obrazovky podokna registrace zařízení](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)
    
    **Zařízení** podokně poskytuje informace o vašem tenantovi uživatele registrovaná zařízení. Můžete kliknout na **všechna zařízení** zobrazíte seznam zařízení pro vašeho tenanta Intune. 

6. Z [Intune](https://aka.ms/intuneportal)vyberte **klientské aplikace** k zobrazení stavu instalace aplikace.

    ![Snímek obrazovky podokna klientské aplikace](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)
    
    Jako správce IT můžete Microsoft Intune použít ke správě klientských aplikací, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune. Intune nabízí celou řadu funkcí, které vám pomůžou zajistit, aby na požadovaných zařízeních byly potřebné aplikace. Další informace o přidávání a přiřazování aplikací najdete v tématu [do Microsoft Intune přidat aplikace](apps-add.md) a [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).

7. Z [Intune](https://aka.ms/intuneportal)vyberte **podmíněného přístupu** zobrazíte podrobné informace o zásadách přístupu.

    ![Snímek obrazovky podokna podmíněného přístupu](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Podmíněný přístup označuje způsoby, jimiž můžete řídit zařízení a aplikace, které se smí připojovat k vašemu e-mailu a firemním prostředkům. Prostudujte si podmíněný přístup podle zařízení a na základě aplikace a najdete běžné scénáře pro použití podmíněného přístupu s Intune, přečtěte si téma [co je podmíněný přístup?](conditional-access.md)

8. Z [Intune](https://aka.ms/intuneportal)vyberte **uživatelé** zobrazíte podrobnosti o uživatelích, které jste zahrnuli do Intune. Tito uživatelé se pracovníci vaší společnosti. 
 
    ![Snímek obrazovky podokna uživatelů](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Můžete přímo do Intune přidat uživatele nebo synchronizovat uživatele z vaší místní Active Directory. Po přidání můžou uživatelé zaregistrovat zařízení a přistupovat k prostředkům společnosti. Můžete také uživatelům udělit další oprávnění pro přístup k Intune. Další informace najdete v tématu [přidání uživatelů a udělení oprávnění pro správu Intune](users-add.md).

9. Z [Intune](https://aka.ms/intuneportal)vyberte **skupiny** zobrazíte podrobnosti o skupinách Azure Active Directory (Azure AD) v Intune. Jako správce Intune používat skupiny ke správě zařízení a uživatelů. 

    ![Snímek obrazovky podokna skupiny](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Například můžete nastavit zásady pro mnoho uživatelů nebo nasadit aplikace do skupiny zařízení. Další informace o skupinách najdete v tématu [přidat skupiny pro uspořádání uživatelů a zařízení](groups-add.md).

10. Z [Intune](https://aka.ms/intuneportal)vyberte **Nápověda a podpora** chcete požádat o pomoc. Jako správce IT, můžete použít **Nápověda a podpora** možnost vyhledávání a podívejte se na řešení, stejně jako soubor lístek online podpory pro Intune. 

    ![Snímek obrazovky podokna Nápověda a podpora](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Pokud chcete vytvořit lístek podpory, musí váš účet přiřazenou roli správce ve službě Azure Active Directory. Role správce zahrnují, **správce Intune**, **globálního správce**, a **Správce služeb**. Další informace najdete v tématu [jak získat podporu pro Microsoft Intune](get-support.md).

11. Z [Intune](https://aka.ms/intuneportal)vyberte **stav Tenanta** zobrazíte podrobnosti o vašem tenantovi Intune.

    ![Snímek obrazovky podokna stav Tenanta.](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Podrobnosti o stavu klienta zahrnují stav konektoru, stav služby Intune a Intune zpráv. Pokud jsou nějaké problémy s vaším tenanta nebo Intune samotného, najdete informace v **stav Tenanta** podokně. Další informace najdete v tématu [stav Tenanta Intune](tenant-status.md).

12. Z [Intune](https://aka.ms/intuneportal)vyberte **Poradce při potížích** kontaktovat zástupce na tipy k odstraňování problémů, žádosti o podporu nebo kontrole stavu služby Intune. Tyto informace je specifická vyberete uživatelů Intune.

    ![Snímek obrazovky podokna Poradce při potížích](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Další informace o odstraňování potíží v Intune najdete v tématu [použít portál pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Konfigurace na webu Azure portal

Azure umožňuje přizpůsobení a konfiguraci zobrazení na portálu.

### <a name="change-the-sidebar"></a>Změna bočního panelu

**Boční panel** na levé straně portálu Azure Portal zobrazuje seznam všech dostupných služeb Azure. Výchozí zobrazení tohoto kompletního seznamu se dá změnit, abyste neustále měli na očích služby, které jsou pro vás nejdůležitější. V níže uvedeném příkladu si přidáte službu Intune na začátek seznamu.

![Hledání služby Microsoft Intune v seznamu Další služby](./media/azure-add-intune1.png)

1. Na bočním panelu na levé straně stránky vyberte **Všechny služby**.
2. V poli filtru vyhledejte **Intune**.
3. Výběrem **hvězdičky** přidáte Intune na konec seznamu svých oblíbených služeb.
4. Najeďte na službu Intune myší. Vyberte a přetáhněte Intune pomocí **tří svislých teček** na pravé straně názvu služby.

### <a name="change-the-dashboard"></a>Změna řídicího panelu

Výchozí cílovou stránkou je **řídicí panel**. Na této stránce si dlaždice přizpůsobíte tak, aby zobrazovaly informace, které jsou pro vás nejdůležitější.

![Obrázek obecného nového řídicího panelu. Znázorňuje řídicí panel se všemi službami nalevo a hlavní řídicí panel uprostřed. Tlačítka pro změnu řídicího panelu se nacházejí nahoře společně s dlaždicemi, které nabízejí přístup ke všem prostředkům, výukovým kurzům, stavu služby a Azure Marketpace.](./media/azure-default-dashboard.png)

Pokud chcete současný řídicí panel změnit, vyberte tlačítko **Upravit řídicí panel**. Pokud výchozí řídicí panel nechcete změnit, můžete také vytvořit **Nový řídicí panel**. Vytvořením nového řídicího panelu získáte prázdný privátní řídicí panel s **galerií dlaždic**, který umožňuje přidání a uspořádání dlaždic. Dlaždice můžete najít podle **obecné** kategorie, **typu**, pomocí **hledání** a prostřednictvím **skupiny prostředků** nebo **značky**.

Přímo na řídicí panel přidáte dlaždice tak, že zvolíte jakékoli tlačítko se **třemi tečkami** a vyberete **Připnout na řídicí panel**.

![Detail oblasti Uživatelé a skupiny > Všechny skupiny v Intune, kde je v pravém horním rohu skupiny vidět možnost Připnout na řídicí panel](./media/azure-pin-to-dashboard.png)

Tato možnost bude užitečnější, až si do Intune přidáte další obsah, jako jsou skupiny a uživatelé.

## <a name="next-steps"></a>Další postup

Získejte rychle spuštěna v Microsoft Intune, projděte skrze rychlých startů Intune první nastavením bezplatného účtu Intune.

> [!div class="nextstepaction"]
> [Rychlý start: Bezplatné vyzkoušení Microsoft Intune](free-trial-sign-up.md)


