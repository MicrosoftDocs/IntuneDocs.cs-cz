---
title: Jak získat podporu pro Microsoft Intune
titleSuffix: Microsoft Intune
description: Získejte online podporu a podporu po telefonu pro placené i zkušební předplatné Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c4d40d3f15fe23511f3f15f7c13181a0fa72f6b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731834"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Jak získat podporu pro Microsoft Intune  

[!INCLUDE [azure_portal](../../intune-classic/includes/note-for-both-portals.md)]  
  
Microsoft poskytuje pro Microsoft Intune globální technickou a předprodejní podporu a podporu k fakturaci a správě předplatného. Podpora je k dispozici online i po telefonu pro placené i zkušební předplatné. Online technická podpora je k dispozici v angličtině a japonštině. V dalších jazycích je k dispozici podpora po telefonu a online podpora k fakturaci.

Jako správce Intune můžete použít možnost **pomoc a podpora** k zavedení lístku online podpory pro Intune z Azure Portal. Pokud chcete vytvořit a spravovat incident podpory, musí mít váš účet roli Azure Active Directory (Azure AD), která zahrnuje *akci* **Microsoft. Office 365. supportTickets/Tickets/Manage**. Informace o rolích a oprávněních služby Azure AD, které jsou nutné k vytvoření lístku podpory, najdete v tématu [role správců v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).  

>[!IMPORTANT]  
> Pokud potřebujete technickou podporu k produktům třetích stran, které fungují s Intune (jako je Saaswedo, Cisco nebo Lookout), obraťte se nejdřív na dodavatele konkrétního produktu. Než otevřete žádost o podporu Intune, zkontrolujte, jestli máte produkt správně nakonfigurovaný.
>
> Informace o řešení potíží souvisejících s Microsoft Intune najdete v dokumentaci k Intune v části týkající se [řešení potíží](help-desk-operators.md).

## <a name="known-issues-for-creating-support-incidents"></a>Známé problémy pro vytváření incidentů podpory  

Pokud má váš účet požadovaná oprávnění, ale nepodaří se mu úspěšně získat přístup k nápovědě a podpoře nebo vytvořit nebo spravovat incident podpory, přečtěte si následující známé problémy a řešení:  
- Zastaralý token uživatele pro váš účet. Pokud chcete tento problém vyřešit, odhlaste se od všech aktivních relací konzoly, přihlaste se znovu a potom se pokuste vytvořit nebo spravovat incident podpory. 
- Několik aktivních relací. Pokud jste se přihlásili s více než jedním uživatelem nebo relací, odhlaste se všechny kromě jedné konzoly. Pak se při jedné aktivní relaci pokusí vytvořit nebo spravovat incident podpory.

Další akce, které mohou být nezbytné k vyřešení problémů s přístupem:
- Vymažte všechny soubory cookie pro aktivní relaci prohlížeče a potom zkuste vytvořit nebo spravovat incident podpory.
- Pomocí relace procházení InPrivate se přihlaste k Intune a zkuste vytvořit nebo spravovat incident podpory.  

Pokud se vám předchozí alternativní řešení nepovede, jděte do [centra pro správu Microsoft 365](https://admin.microsoft.com) a z něj vytvořte lístek podpory. V současnosti pracujeme na opravě, která bude k dispozici v pozdní léta.  

## <a name="help-and-support-experience"></a>Prostředí pro pomoc a podporu  

Pomoc a podpora pro Intune je k dispozici na [portálu pro správu zařízení Microsoft 365](https://devicemanagement.microsoft.com) a ze všech oken (nebo stránek) v rámci služby Intune v Azure Portal. 

![Okna Intune](./media/get-support/intune-blades.png)


Prostředí pro *nápovědu a podporu* se podobá prostředí, které se zobrazuje v [centru pro správu Microsoft 365](https://admin.microsoft.com/), a nahrazuje předchozí nápovědu a *podporu*, která zůstává na místě pro ostatní služby v Azure. 

Chcete-li získat přístup k nápovědě a podpoře, použijte následující možnosti:  
- **Řídicí panel správy zařízení:**
  - Po výběru oblasti funkcí pro Intune vyberte možnost **nápovědu a podpora**.
  - Z libovolného uzlu na portálu pro správu zařízení vyberte **?** v pravém horním rohu portálu a pak pomocí rozevírací nabídky vyberte službu, se kterou chcete získat informace. **?** ikona na portálu pro správu zařízení podporuje několik služeb a musíte vybrat konkrétní službu, pro kterou chcete pomoc.  

    ![Výběr služby](./media/get-support/select-a-service.png)

    Po výběru služby uvidíte stránku *pomoc a podpora* pro tuto službu, kde pak můžete [zadat podrobnosti](#specify-details-about-an-issue) o konkrétním problému, se kterým chcete pomoc.  

    Pokud výsledky hledání nevypadají podle očekávání pro vaši službu, zkontrolujte, zda byla vybrána správná služba. Výběr služby se zobrazí hned po *pomoci a podpoře*.  Pokud není vybraná správná služba, klikněte na *Vybrat službu* , kterou chcete vrátit do rozevíracího seznamu pro výběr služby.   

    ![Potvrzení služby](./media/get-support/confirm-your-service-selection.png) 


- **V Azure Portal:**
  - Vybrat **pomoc a podporu** z jakéhokoli okna nebo stránky Intune

  Pokud v Azure Portal vyberete možnost **?** pomocí ikony v pravém horním rohu nebo **nápovědy a podpory** v levém navigačním podokně otevřete *nápovědu a podporu* pro Azure. V *nápovědě a podpoře*Azure nemůžete incident podpory Intune otevřít přímo, ale můžete se dostat na stránku *Nápověda a podpora* Intune, a to provedením následujících akcí: 
  1. Vyberte novou žádost o podporu.
  2. Jako typ problému zadejte Technical.
  3. V případě služby zadejte Microsoft Intune.
  4. Vyberte stránku pro pomoc a podporu Intune.

> [!NOTE]  
> Pokud je vaše instance Intune hostovaná ve službě COMPUTE COMPUTE Cloud (RSZ), označovaná také jako svrchovaná Cloud, jako je Azure Government, přečtěte si téma Podpora Intune pro státní výpočetní Cloud, dále v tomto článku. V části RSZ až do konce tohoto roku nebude k dispozici *pomoc a podpora* Intune. 


Když otevřete okno pro *pomoc a podporu*, na portálu se zobrazí zobrazení, které závisí na tom, jestli máte incidenty aktivní podpory a když máte Premier Support, některé další prvky a možnosti:
- **Neexistují žádné aktivní incidenty podpory**: na stránce **Potřebuji pomoc** se zobrazí stránka s informacemi o tom, jak je vidět na následujícím obrázku na řídicím panelu Správa zařízení.  
- **Incidenty aktivní podpory**: uvidíte stránku [lístky podpory](#view-support-cases) , která zobrazuje seznam aktivních incidentů.  
- **Smlouva Premier Support**: vaše zkušenosti jsou stejné jako první dvě možnosti, i když se vám podíváme na tyto další prvky, které potřebujete? Page 
  - Když nadpis stránky potřebuje popřípadě **?** , zobrazí se nápis Premier Support:  
    banner podpory ![Premier @ no__t-1
  - V části **získat podporu** na stránce můžete nastavit počáteční úroveň **závažnosti** při vytváření žádosti o službu telefonicky.


![Řídicí panel správy zařízení a potřebuji podporu? Page](./media/get-support/help-support-dashboard.png)

V tomto zobrazení můžete:

1. [Zadat podrobnosti](#specify-details-about-an-issue) o konkrétním problému, se kterým potřebujete pomoct.  
2. [Zobrazit kontextovou nápovědu](#view-context-sensitive-help) a související řešení založená na podrobnostech, které zadáte.  
3. [Získat podporu](#get-support), ať už e-mailovou nebo telefonickou.  
4. [Zobrazit případy podpory](#view-support-cases), které jste dříve otevřeli pomocí tohoto nového pracovního postupu.  

### <a name="specify-details-about-an-issue"></a>Zadání podrobností o problému 

Když otevřete pomoc a podporu z umístění, které je podporováno novým prostředím, otevře se stránka **Potřebuji pomoc?** . Na této stránce můžete zadat podrobnosti o problému. Po zadání podrobností vám konzola nabídne běžné dotazy na základě použitých klíčových slov. Vyberte nabízenou volbu nebo dokončete vlastní popis problému. Pokud zadáte vlastní popis, vyberte **Získat nápovědu** a dotaz odešlete. Po odeslání dotazu konzola vrátí kontextově závislé informace, které mohou přispět k vyřešení problému.

Tady jsou příklady dotazů, které můžete odeslat:
  
- *Nemohu obnovit zařízení s iOSem*  
- *Nejde vytvořit zásady podmíněného přístupu.*  

![Zadání problému na stránce Potřebujete pomoct?](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>Získání kontextové nápovědy 

Po výběru některé z nabízených možností nebo odeslání vlastního dotazu se v části **Zobrazit řešení** zobrazí kontextové výsledky. Ty zahrnují jak samoobslužné pokyny specifické pro Intune, tak i další výsledky vrácené z webového vyhledávání na základě kritérií dotazu.  
![Zobrazení výsledků](./media/get-support/view-results.png)

### <a name="get-support"></a>Získání podpory 

Pokud vám doprovodné materiály nebo webové doprovodné materiály nepomohly problém vyřešit, použijte konzolu nástroje k otevření problému s e-mailem nebo telefonickou podporou.  
Na stránce **Potřebujete pomoct?** vyberte možnost, kterou chcete použít.  

  > [!NOTE] 
  > E-mailové požadavky na podporu nejsou pro všechny klienty k dispozici.  

- U e-mailové žádosti zadejte e-mailovou adresu a volitelně také přidejte přílohy. Výběrem možnosti **Odeslat** otevřete žádost. 

  ![E-mailová žádost](./media/get-support/email-support.png)
  
- U telefonické žádosti zadejte telefonní číslo. Můžete také přidat e-mailovou adresu a přílohy. Žádost odešlete výběrem možnosti Zavolejte mi.  



   ![Telefonická žádost](./media/get-support/phone-support.png)

**Podpora Premier**:  
Pokud máte smlouvu Premier Support, máte stejné možnosti pro vytvoření incidentu podpory telefonu. Můžete také zadat **závažnost** pro zpětné volání podpory a zvolit vytvoření lístku podpory na základě nejdůležitější smlouvy.  

![Možnosti podpory Premier](./media/get-support/premier-phone-support-options.png)


### <a name="view-support-cases"></a>Zobrazení případů podpory  

Výběrem tlačítka historie zobrazíte incidenty podpory, které jste vytvořili.  

![Zobrazení případů podpory](./media/get-support/view-support-tickets.png)

- V tomto pracovním postupu se zobrazí pouze případy podpory, které jste otevřeli pomocí nového pracovního postupu. Pokud je chcete zobrazit, použijte zobrazení pro pomoc a podporu v konzole pro správu zařízení nebo v okně Intune v Azure Portal. Tyto případy jsou označeny osmimístnými čísly. Na tyto případy se také můžete podívat v centru pro správu Microsoft 365.  

- Případy, kdy jste otevřeli, když nepoužíváte pomoc a prostředí podpory Intune, se nezmění. Pokud je chcete zobrazit, je nutné použít zobrazení pro pomoc a podporu, které není součástí prostředí Intune nebo řídicího panelu správy zařízení. Tyto případy jsou označeny čísly, která začínají **117** nebo **118** a mají 15 číslic. K jejich zobrazení:

    1. Přihlaste se k Azure (<https://portal.azure.com>) pomocí svých přihlašovacích údajů správce Intune, vyberte ikonu *?* v pravém horním rohu portálu a pak vyberte možnost *Nápověda a podpora*, kterou přejdete na stránku [nápovědy a podpory Azure](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

    2. Na stránce **Nápověda a podpora** se zobrazí seznam **Nedávné žádosti o podporu**. Výběrem žádostí o podporu lze zobrazit další podrobnosti.
 

## <a name="azure-help--support-experience"></a>Prostředí Azure Help a podpora 

Když použijete levé navigační podokno, získáte **pomoc a podporu**, nebo použijte **?** v pravém horním rohu Azure Portal otevřete okno nápovědy a podpory pro Azure, které se liší od nápovědy a možností podpory pro Intune.  

Od dubna 2019 nemůžete získat pomoc s Intune a nebudete mít přístup ke službě Azure *help + support* , pokud vaše předplatné neplatí pro službu COMPUTE COMPUTE Cloud (RSZ).  

Pokud vaše instance Intune neběží na RSZ, navigace prostřednictvím Azure *help + support* vás přesměruje na *pomoc a možnosti podpory* Intune, abyste mohli vytvářet a spravovat incidenty podpory.  


## <a name="intune-support-for-government-compute-cloud"></a>Podpora Intune pro Cloud COMPUTE COMPUTE  

Když se vaše předplatné Intune hostuje v rámci služby COMPUTE COMPUTE Cloud (RSZ), která se také označuje jako svrchovaná Cloud, jako je Azure Government, ještě nemáte přístup k novější nápovědě a podpoře pro Intune.  Místo toho použijte následující informace, které najdete v části získání podpory pro Intune. 


### <a name="create-an-online-support-ticket"></a>Vytvoření lístku online podpory 

>[!IMPORTANT]    
> Když *pomoc a podpora* přechází do nového systému, který pro RSZ ještě není dostupný, při vytváření incidentu podpory tento portál identifikuje případ podpory, který používá identifikační číslo s 15 číslicemi. Při vytvoření případu se 15 číslicemi se vytvoří zrcadlový svazek tohoto případu pro použití v podpora Microsoftu. Tento zrcadlový případ se vytvoří v novém systému podpory, používá 8bitové ID případu a používá služby podpory ke sledování všech pracovních a komunikačních incidentů podpory. Krátce po vytvoření případu s 15 číslicemi obdržíte e-mail, který identifikuje 8bitového případu podpory, který se používá pro služby podpory.  
> 
> Podporují osobní práci a komunikují z případu podpory s 8 číslicemi a používají se jenom 8 číslic, které slouží k protokolování komunikací a sledování průběhu incidentu. Proto obdržíte e-mailem aktualizace z tohoto případu podpory s 8 číslicemi, který bude sloužit jako záznam o pracovní skladbě. K incidentu podpory na 15 číslici se nezaznamenávají žádné podrobnosti. Po ukončení podpory a velikosti případu podpory se 8 číslicemi se tento stav projeví v případě podpory 15 číslic, kterou si můžete prohlédnout na webu Azure Portal.  Pro případ podpory 15 číslic by se neměly očekávat žádné jiné aktualizace ani změny stavu.  
> 
> Když se přechody mezi nástroji podpory dokončí později než tento rok, bude se podpora služby Intune hostovaná v cloudu pro státní správu podobat výchozí *nápovědě a podpoře* , která je aktuálně dostupná pro předplatná Intune hostovaná na veřejný cloud.  


1. Přihlaste se na portálu Azure Portal (<https://portal.azure.com>) pomocí svých přihlašovacích údajů správce Intune, vyberte ikonu **?** v pravém horním rohu portálu a pak vyberte možnost **Nápověda a podpora**, kterou přejdete na stránku [nápovědy a podpory Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

   ![Obrázek odkazu na otazník pomocí zvýrazněného odkazu Nápověda a podpora](./media/get-support/azure-get-support.png)

2. Na stránce **pomoc a podpora** Azure vyberte **Nová žádost o podporu**.

   ![Obrázek odkazu na nové žádosti o podporu zvýrazněný na stránce pomoc a podpora](./media/get-support/azure-support-ticket-link.png)

3. Na kartě **základy** pro většinu problémů technické podpory Intune vyberte tyto možnosti:
   - **Typ problému**: **Technický**
   - **Předplatné**: <*vaše předplatné*>
   - **Služba**: **Microsoft Intune**
   - **Typ problému**: z rozevírací nabídky vyberte typ problému.
   - **Typ problému**: z rozevírací nabídky vyberte podtyp problému.
   - **Předmět**: stručně popište problém, se kterým chcete pomáhat.

   ![Obrázek karty základy na stránce pomoc a podpora – nová žádost o podporu](./media/get-support/help-new-support-case-basics.png)

   Klikněte na tlačítko **Další: řešení** pro pokračování.
4. Na kartě **řešení** si přečtěte doporučený postup, který vám může pomáhat vyřešit váš problém bez podání lístku. Pokud stále chcete vytvořit žádost o podporu po prohlédnutí kroků, klikněte na **Další: podrobnosti**.

   ![Obrázek karty řešení na stránce pomoc a podpora – nová žádost o podporu](./media/get-support/help-new-support-case-solutions.png)
5. Na kartě **Podrobnosti** vyplňte podrobnosti o vašem problému, způsob podpory, vaše kontaktní informace a klikněte na **Další: zkontrolovat + vytvořit**.

   ![Obrázek karty Podrobnosti na stránce pomoc a podpora – nová žádost o podporu](./media/get-support/help-new-support-case-details.png)
6. Zkontrolujte informace, ověřte, že je správná, a pak zvolte **vytvořit** a odešlete žádost o podporu.

   ![Obrázek karty revize + vytvořit na nové stránce žádosti o podporu](./media/get-support/help-new-support-case-create.png)

>[!IMPORTANT]
>Pokud máte otázky fakturace nebo předplatného, můžete otevřít případ a získat podporu prostřednictvím [centra pro správu Microsoft 365](https://admin.microsoft.com/Support/SupportEntry.aspx).

### <a name="view-support-requests"></a>Zobrazení žádostí o podporu  

Žádosti o podporu můžete zobrazit v rámci Azure Portal. K dispozici jsou však omezené informace.  Zobrazení incidentů: 

1. Přihlaste se k Azure (<https://portal.azure.com>) pomocí svých přihlašovacích údajů správce Intune, vyberte ikonu **?** v pravém horním rohu portálu a pak vyberte možnost **Nápověda a podpora**, kterou přejdete na stránku [nápovědy a podpory Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

2. Na stránce **pomoc a podpora** si můžete prohlédnout seznam **posledních žádostí o podporu**.

   > [!IMPORTANT]  
   > Zákazníci s výpočetními úřady pro státní správu můžou zobrazit jenom číslo případu podpory na 15 číslicích a stav incidentu. Všechna případná komunikace a sledování práce nebo upozornění se odesílají e-mailem a odkazují na 8bitové číslo případu podpory, které se vytvoří jako zrcadlo případu podpory otevřeného v konzole Intune.   

## <a name="additional-resources"></a>Další materiály a zdroje informací  

- [Podpora správy fakturace a předplatného](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Multilicence](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Řešení potíží s Intune](help-desk-operators.md)
