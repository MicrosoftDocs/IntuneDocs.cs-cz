---
title: Jak získat podporu pro Microsoft Intune
titleSuffix: Microsoft Intune
description: Získejte online podporu a podporu po telefonu pro placené i zkušební předplatné Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: srik
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5aca7dbae7a74af399bcbf21aec1dd9dd2d1e851
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390749"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Jak získat podporu pro Microsoft Intune

Microsoft poskytuje pro Microsoft Intune globální technickou a předprodejní podporu a podporu k fakturaci a správě předplatného. Podpora je k dispozici online i po telefonu pro placené i zkušební předplatné. Online technická podpora je k dispozici v angličtině a japonštině. V dalších jazycích je k dispozici podpora po telefonu a online podpora k fakturaci.

Jako správce Intune můžete použít možnost **pomoc a podpora** k zavedení lístku online podpory pro Intune z Azure Portal. Pokud chcete vytvořit a spravovat incident podpory, musí mít váš účet roli Azure Active Directory (Azure AD), která zahrnuje *akci* **Microsoft. Office 365. supportTickets**. Informace o rolích a oprávněních služby Azure AD, které jsou nutné k vytvoření lístku podpory, najdete v tématu [role správců v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

>[!IMPORTANT]
> Pokud potřebujete technickou podporu k produktům třetích stran, které fungují s Intune (jako je Saaswedo, Cisco nebo Lookout), obraťte se nejdřív na dodavatele konkrétního produktu. Než otevřete žádost o podporu Intune, zkontrolujte, jestli máte produkt správně nakonfigurovaný.
>
> Informace o řešení potíží souvisejících s Microsoft Intune najdete v dokumentaci k Intune v části týkající se [řešení potíží](help-desk-operators.md).


## <a name="help-and-support-experience"></a>Prostředí pro pomoc a podporu

Pomoc a podpora pro Intune je k dispozici v [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431) a ze všech oken (nebo stránek) v Intune v Azure Portal.

Prostředí pro *nápovědu a podporu* se podobá prostředí, které se zobrazuje v [centru pro správu Microsoft 365](https://admin.microsoft.com/), a nahrazuje předchozí nápovědu a *podporu*, která zůstává na místě pro ostatní služby v Azure.

> [!TIP]
> Od 18. listopadu 2019 se aktualizovaly a zjednodušilo prostředí v konzole pro získání pomoci a podpory pro klienty. Pokud toto nové prostředí zatím není k dispozici, bude brzy.

### <a name="options-to-access-help-and-support"></a>Možnosti pro přístup k nápovědě a podpoře

Při použití nově vytvořeného tenanta pro Intune je možné, že se nepovede otevřít *pomoc a podpora* a vrátí se následující zpráva:

- *Došlo k neznámému problému. Aktualizujte prosím stránku, ale pokud potíže potrvají, vytvořte si prosím případ prostřednictvím [centra pro správu M365](https://admin.microsoft.com) a Projděte si informace o zadaném ID relace.*

Podrobnosti o chybě zahrnují *ID relace*, podrobnosti *rozšíření* a další. 
 
K tomuto problému dochází, když jste svůj nový účet tenanta ještě neověřili prostřednictvím **centra pro správu M365** na https://admin.microsoft.comnebo na **portálu Office 365** na https://portal.office.com. Pokud chcete tento problém vyřešit, vyberte odkaz pro *Centrum pro správu M365* ve zprávě nebo navštivte https://portal.office.coma přihlaste se. Po ověření v obou lokalitách bude k dispozici *pomoc a podpora* služby Intune.


**Přístup k nápovědě a podpoře**:

- **V Azure Portal**

  - Vyberte možnost **pomoc a podpora** z jakéhokoli okna nebo stránky Intune.

  > [!NOTE]  
  > Pokud je vaše instance Intune hostovaná v privátním cloudu pro státní správu, označovaná také jako svrchovaná Cloud, jako je Azure Government, přečtěte si část [Podpora služby Intune pro privátní cloud pro státní](#intune-support-for-private-cloud-for-government)správu dále v tomto článku. Prostředí pro správu *a podporu* Intune nebude k dispozici v privátním cloudu pro státní správu až do příštího roku.

- **Z centra pro správu Microsoft Endpoint Manageru**
  - Po výběru oblasti funkcí pro Intune vyberte možnost **nápovědu a podpora**.
  - Z libovolného uzlu v centru pro správu Microsoft Endpoint Manageru vyberte **?** v pravém horním rohu portálu a pak pomocí rozevírací nabídky vyberte službu, se kterou chcete získat informace. **?** ikona v centru pro správu Microsoft Endpoint Manager podporuje několik služeb a musíte vybrat konkrétní službu, pro kterou chcete pomoc.  

    ![Výběr služby](./media/get-support/select-a-service.png)

    Po výběru služby uvidíte stránku *pomoc a podpora* pro tuto službu, kde můžete zadat podrobnosti pro [hledání řešení](#find-solutions) pro konkrétní problém.

    Pokud výsledky hledání nevypadají podle očekávání pro vaši službu, zkontrolujte, zda byla vybrána správná služba. Výběr služby se zobrazí hned po *pomoci a podpoře*.  Pokud není vybraná správná služba, klikněte na *Vybrat službu* , kterou chcete vrátit do rozevíracího seznamu pro výběr služby.

    ![Potvrzení služby](./media/get-support/confirm-your-service-selection.png)

###  <a name="the-support-experience"></a>Prostředí podpory

  Po otevření okna pro pomoc a podporu se na portálu zobrazí okno **Potřebuji pomoc?** :

  ![Zobrazit okno potřeby s potřebam](./media/get-support/need-help.png)

  V levém horním rohu jsou tři ikony, které můžete vybrat pro otevření různých podoken v okně *Potřebuji Help?* . Podokno zobrazené v podokně je označeno podtržením.

  Zákazníci se smlouvou o podpoře **Premier** nebo **Unified** mají [Další možnosti](#premier-and-unified-support-customers) pro podporu a v nápisu *potřebujete pomoc?* který se podobá následujícímu obrázku: ![Premier banner](./media/get-support/premier-banner.png)

  *Potřebujete tuto podporu?* Otevře se podokno *najít řešení* . Pokud ale máte aktivní případ podpory, otevře se okno v podokně *žádosti o služby* , kde můžete zobrazit podrobnosti o aktivních a uzavřených případech podpory.

#### <a name="find-solutions"></a>Najít řešení

![Vyberte podokno najít řešení.](./media/get-support/find-solutions.png)

V podokně *najít řešení* zadejte několik podrobností o problému v zadaném textovém poli. V závislosti na textu, který zadáte k problému, se v podokně naplní přehledy, které jsou potenciálními shodami. Získáte také odkazy na Doporučené články, které vám mohou při řešení tohoto problému.

Když se pro popsáné podrobnosti najde silná shoda, tipy pro řešení potíží se můžou v okně *Potřebuji* považovat za nápovědu?

Můžete například zadat **chyby synchronizace hesel**. Výsledky zahrnují pokyny k odstraňování potíží přímo v podokně a odkazy na Doporučené články z naší knihovny dokumentace.

![Zobrazit přehledy řešení potíží](./media/get-support/troubleshooting-insights.png)

#### <a name="contact-support"></a>Kontaktujte podporu

![Vyberte podokno podpora kontaktů.](./media/get-support/contact-support.png)

V podokně *Podpora kontaktů* můžete odeslat žádost o pomoc. Toto podokno je k dispozici, jakmile v podokně *najít řešení* zadáte některá základní klíčová slova.

Při žádosti o pomoc uveďte popis problému s co největším množstvím podrobností.  Po potvrzení telefonního kontaktu a e-mailových kontaktních informací vyberte metodu kontaktu, které dáváte přednost. V okně se zobrazí doba odezvy pro každou metodu kontaktu, která vám poskytne očekávanou dobu, kdy se bude kontaktovat. Před odesláním žádosti připojte soubory, jako jsou protokoly nebo snímky obrazovky, které můžou pomůžou vyplnit podrobnosti o problému.

![Kontaktujte formulář podpory](./media/get-support/contact-support-form.png)

Jakmile vyplníte požadované informace, vyberte **Kontaktní osoba** pro odeslání žádosti.

#### <a name="service-requests"></a>Žádosti o služby

![Vyberte podokno žádosti o služby.](./media/get-support/service-requests.png)

V podokně *žádosti o služby* se zobrazí vaše historie případu. Aktivní případy jsou v horní části seznamu s uzavřenými problémy, které jsou k dispozici také pro kontrolu.

![Zobrazení seznamu žádostí o služby](./media/get-support/service-requests-pane.png)

Pokud máte aktivní číslo případu podpory, můžete ho sem zadat, pokud chcete přejít k tomuto problému, nebo můžete vybrat libovolný incident ze seznamu aktivních a uzavřených incidentů a zobrazit další informace.

Po zobrazení podrobností pro incident vyberte šipku vlevo, která se zobrazí v horní části okna žádosti o služby hned nad ikonami pro tři ikony, které *potřebujete nápovědu?* ikona podokna. Šipka zpět vrátí zobrazení na seznam incidentů podpory, které jste otevřeli.

#### <a name="premier-and-unified-support-customers"></a>Zákazníci s plánem Premier a Unified support

Jako zákazník se smlouvou o podpoře **Premier** nebo **Unified** můžete určit závažnost problému a naplánovat zpětné volání podpory pro určitý čas a den. Tyto možnosti jsou k dispozici, když otevřete nebo odešlete nový problém a upravíte aktivní případ podpory.

**Závažnost** – možnosti určení závažnosti problému závisí na vaší smlouvě o podpoře:

- *Premier*: závažnost a, B nebo C
- *Unified*: kritická nebo nekritická

Výběrem závažnosti **a** nebo **kritického** problému omezíte případ podpory pro telefonickou podporu, což vám poskytne nejrychlejší možnost získat podporu.

**Plán zpětného volání** – na určité datum a čas můžete požádat o zpětné volání.

## <a name="azure-help--support-experience"></a>Prostředí Azure Help a podpora

Pokud se vaše předplatné nepoužívá v privátním cloudu pro státní správu, nebudete už moct získat pomoc s Intune.
Pokud vaše instance Intune neběží na privátním cloudu pro státní správu, navigace prostřednictvím Azure *help + support* vás přesměruje na *nápovědu a podporu* služby Intune, kde můžete vytvářet a spravovat incidenty podpory:

Když použijete levé navigační podokno, získáte **pomoc a podporu**, nebo použijte **?** Chcete-li otevřít podokno pro *pomoc* a pak vybrat možnost **help + podpora**, otevřete stránku Azure *help + support* . 


Na této stránce vyberte **+ Nová žádost o podporu** a otevřete tak kartu *základy* na stránce *pomoc a podpora a nová žádost o podporu* .

![Pomoc a podpora](./media/get-support/help-plus-support.png)

Na této stránce:

- Jako *typ problému*vyberte **technický**.
- V případě *služby*vyberte **Microsoft Intune**.

  Pak se zobrazí odkaz, který vás přesměruje na [stránku pomoci a podpory pro Intune](https://aka.ms/intunehelpsupport).
  
  ![Nová žádost o podporu](./media/get-support/new-request.png)


## <a name="intune-support-for-private-cloud-for-government"></a>Podpora pro privátní cloud pro státní správu v Intune

Když se vaše předplatné Intune hostuje v privátním cloudu pro vládu, který se taky označuje jako svrchovaný Cloud, jako je Azure Government, ještě nemáte přístup k novější nápovědě a podpoře pro Intune.  Místo toho použijte následující informace, které najdete v části získání podpory pro Intune.

### <a name="create-an-online-support-ticket"></a>Vytvoření lístku online podpory

>[!IMPORTANT]
> Když *pomoc a podpora* přechází do nového systému, který ještě není k dispozici pro veřejný cloud pro státní správu, při vytváření incidentu podpory tento portál identifikuje případ podpory, který používá identifikační číslo s 15 číslicemi. Při vytvoření případu se 15 číslicemi se vytvoří zrcadlový svazek tohoto případu pro použití v podpora Microsoftu. Tento zrcadlový případ se vytvoří v novém systému podpory, používá 8bitové ID případu a používá služby podpory ke sledování všech pracovních a komunikačních incidentů podpory. Krátce po vytvoření případu s 15 číslicemi obdržíte e-mail, který identifikuje 8bitového případu podpory, který se používá pro služby podpory.
>
> Podporují osobní práci a komunikují z případu podpory s 8 číslicemi a používají se jenom 8 číslic, které slouží k protokolování komunikací a sledování průběhu incidentu. Proto obdržíte e-mailem aktualizace z tohoto případu podpory s 8 číslicemi, který bude sloužit jako záznam o pracovní skladbě. K incidentu podpory na 15 číslici se nezaznamenávají žádné podrobnosti. Po ukončení podpory a velikosti případu podpory se 8 číslicemi se tento stav projeví v případě podpory 15 číslic, kterou si můžete prohlédnout na webu Azure Portal.  Pro případ podpory 15 číslic by se neměly očekávat žádné jiné aktualizace ani změny stavu.
>
> V případě přechodů mezi nástroji podpory, které jsou v průběhu tohoto roku dokončeny, se prostředí podpory Intune hostované v cloudu pro státní správu bude podobat výchozím nastavením *pomoci a podpory* , které je aktuálně dostupné pro předplatná Intune hostovaná ve veřejném cloudu.

1. Přihlaste se na portálu Azure Portal (<https://portal.azure.us>) pomocí svých přihlašovacích údajů správce Intune, vyberte ikonu **?** v pravém horním rohu portálu a pak vyberte možnost **Nápověda a podpora**, kterou přejdete na stránku [nápovědy a podpory Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

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

2. Na stránce **pomoc a podpora** můžete zobrazit seznam **posledních žádostí o podporu**.

   > [!IMPORTANT]  
   > Privátní cloud pro zákazníky státní správy může zobrazit jenom číslo případu podpory na 15 číslicích a stav incidentu. Všechna případná komunikace a sledování práce nebo upozornění se odesílají e-mailem a odkazují na 8bitové číslo případu podpory, které se vytvoří jako zrcadlo případu podpory otevřeného v konzole Intune.

## <a name="additional-resources"></a>Další materiály a zdroje informací  

- [Podpora správy fakturace a předplatného](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Multilicence](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Řešení potíží s Intune](help-desk-operators.md)