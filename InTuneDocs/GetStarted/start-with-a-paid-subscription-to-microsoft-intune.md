---
title: "Úvodní příručka služby Intune | Microsoft Intune"
description: "Požadavky a předpoklady k tomu, abyste se vaše předplatné Intune dalo začít používat"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 735889feb1c3234c0c063048601715a3f8aa4719


---


# Úvodní příručka služby Intune
Tato úvodní příručka vás provede postupem vytvoření placeného předplatného služby Microsoft Intune, abyste mohli rychle a snadno spravovat mobilní zařízení a počítače s Windows, které používá vaše organizace. Jednotlivé kroky můžete provádět v uvedeném pořadí, případně můžete některé z nich přeskočit, pokud nevyhovují vašemu prostředí nebo obchodním potřebám.

>[!NOTE]
>Tento článek se týká nastavení Intune jako samostatné služby. Pokud ke správě počítačů a serverů aktuálně používáte Microsoft System Center Configuration Manager, můžete [Configuration Manager rozšířit pro správu mobilních zařízení](https://technet.microsoft.com/library/jj884158.aspx). Můžete k tomu využít propojení Intune s Configuration Managerem v nasazení hybridní správy mobilních zařízení (MDM).

Řada kroků v této úvodní příručce se shoduje s kroky uvedenými v [Příručce pro testování Intune](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). Až dokončíte vyhodnocení a budete připravení zahájit správu mobilních zařízení, budete ale muset vyřešit několik dalších požadavků:

-   Synchronizace místních účtů služby Active Directory s Intune a Azure Active Directory

-   Aktualizace záznamů o veřejné doméně a službě DNS u vašeho registrátora domény

-   Přizpůsobení funkcí Intune pro provozní využití

>[!TIP]
>Pokud si koupíte nejmíň 150 licencí na Microsoft Intune v rámci opravňujícího plánu, můžete využít *benefit Centra FastTrack*. Jde o službu, kdy vám specialista Microsoftu pomůže připravit vaše prostředí na Intune. Další informace najdete v tématu [Popis výhod služby Microsoft Intune](https://technet.microsoft.com/library/mt228265.aspx).


## Před zahájením
Tuto příručku použijte v případě, že začínáte s placeným předplatným a jste připravení nasadit Intune a provést změny ve své stávající síťové infrastruktuře. Může jít o různé změny, od jednoduchého přidání nebo aktualizace interních a externích záznamů DNS až po synchronizaci stávajících uživatelských účtů služby Active Directory se službou Azure Active Directory. Ať už se rozhodnete využívat jakoukoli kombinaci funkcí správy mobilních zařízení Intune, musíte pečlivě naplánovat způsob, jakým bude Intune komunikovat s vašimi stávajícími síťovými součástmi a službami. Konkrétně byste měli zkontrolovat:

-   **Jak budete spravovat identitu uživatelů**: Ve většině středně velkých a velkých organizací se za nejlepší a nejpohodlnější způsob, jak spravovat identitu uživatelů v Intune, považuje připojení stávající adresářové služby k Intune přes Azure Active Directory. To platí především tehdy, pokud už používáte jiné cloudové služby Microsoft, jako je třeba Office 365 nebo Exchange Online. Synchronizace vašich stávajících uživatelských účtů pomocí služby [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) je rychlý a snadný způsob, jak připojit místní službu Active Directory k Azure Active Directory a nakonfigurovat ověření jednotného přihlašování pro vaše uživatele.

-   **Jaký to bude mít vliv na DNS**: Pokud chcete místo výchozí domény onmicrosoft.com, kterou dostanete při první registraci v Intune, používat vlastní název domény, budete potřebovat aktualizace některých veřejných záznamů DNS. Aktualizace záznamů DNS je nutná proto, aby mobilní zařízení dokázala službu Intune najít a aby služba správy předplatných správně spravovala všechna zařízení používaná vaší organizací.

## Co budete potřebovat
Jste připravení začít? Při zahájení placeného předplatného Intune budete potřebovat tyto položky:

### Zařízení s webovým prohlížečem s podporou technologie Silverlight
Potřebujete ho pro přístup ke konzole pro správu Intune, kterou budete používat ke správě zařízení, aplikací a zásad. Budete také potřebovat webový prohlížeč pro přístup k webovému Portálu společnosti Intune, když zrovna nebudete používat aplikaci Portál společnosti na mobilním zařízení. V zájmu usnadnění můžete použít „režim ochrany osobních údajů“ ve stejném prohlížeči, který používáte pro správu Intune (třeba v Internet Exploreru můžete kliknout na **Nástroje** &gt; **Procházení InPrivate**).

>[!TIP]
>Kvůli tomuto požadavku není přístup ke konzole pro správu Intune podporovaný v prohlížeči Microsoft Edge.


### Certifikáty pro mobilní zařízení
Pokud pomocí Intune spravujete zařízení s iOS nebo zařízení Windows Phone, budete potřebovat certifikáty a účty k načtení těchto certifikátů. Zařízení s Androidem žádné další certifikáty nepotřebují.

- Pro uživatele **Windows Phone 8.1**, kteří si aplikaci Portál společnosti nainstalují ze Storu, žádný certifikát potřeba není. Pro **Windows Phone 8.0** nebo v případě použití Intune k nasazení aplikace Portál společnosti na zařízení Windows Phone 8.1 se vyžaduje [certifikát pro podpis kódu Symantec](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do).

>[!NOTE]
>Tato úvodní příručka předpokládá, že uživatelé aplikaci Portál společnosti získají ze Storu na zařízení Windows Phone 8.1 nebo novějším. Informace o podpoře zařízení Windows Phone 8.0 najdete v tématu [Nastavení správy pro zařízení Windows Phone 8.0 v Microsoft Intune](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Pro **počítače s Windows** a **zařízení s Windows RT** se v případě registrace počítačů s Windows jako zařízení nebo [instalaci klienta Microsoft Intune pro počítače s Windows](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune) nepožadují žádné certifikáty.

- U zařízení se systémem **iOS** nebo **Mac OS X** budete muset požádat o certifikát služby Apple Push Notification od společnosti Apple, jak se popisuje v kroku 3 v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

## Další kroky
Je čas seznámit se s úvodní příručkou služby Intune!

>[!div class="step-by-step"]
[**Přihlášení k Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Aug16_HO4-->


