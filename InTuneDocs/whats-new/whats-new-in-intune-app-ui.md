---
title: "Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele | Dokumentace Microsoftu"
description: "Zjistěte, co se změnilo v uživatelském rozhraní aplikací, které fungují s Intune na zařízeních pro koncové uživatele."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0a39abc7f19f4c2c8074de66a9cd5df9cef78ed5
ms.openlocfilehash: 81761af5ab5aebe6abb44ff43a7df5a337d38fc7
ms.lasthandoff: 04/13/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele
Zjistěte, jaké jsme v uživatelském rozhraní aplikací udělali změny, které koncoví uživatelé uvidí v této verzi Microsoft Intune. Pomůže vám to při komunikaci s uživateli a aktualizaci vlastní dokumentace, kterou jste vytvořili za účelem podpory vašeho nasazení. Můžete také zjistit, jak lépe řešit problémy uživatelů, když požádají helpdesk o podporu pomocí Portálu společnosti.

> [!Note]
> Upozorňujeme, že následující obrázky jsou náhledy a oznámený produkt se od prezentovaných verzí může lišit.

## <a name="whats-coming-in-intune-app-ui"></a>Co připravujeme v uživatelském rozhraní aplikace Intune

### <a name="april-2017"></a>Duben 2017

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nové ikony pro Managed Browser a Portál společnosti <!--918433, 918431-->

Managed Browser dostal aktualizované ikony pro verze aplikace pro Android i iOS. Nová ikona bude obsahovat aktualizovaný odznáček Intune, aby byla konzistentnější s ostatními aplikacemi v Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Portál společnosti také dostal aktualizované ikony pro verze aplikace pro Android, iOS i Windows, aby byly konzistentnější s ostatními aplikacemi v EM+S. Tyto ikony se budou postupně vydávat pro všechny platformy od dubna do konce května.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Ukazatel průběhu přihlášení v Portálu společnosti pro Android <!--953374-->

Aktualizace aplikace Portál společnosti pro Android zobrazuje indikátor průběhu přihlášení, když uživatel aplikaci spustí nebo pokračuje v jejím používání. Než uživatel získá přístup k aplikaci, indikátor postupně zobrazuje nové stavy od „Připojování...“ přes „Přihlašování...“ po „Kontrolují se požadavky na zabezpečení...“.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

## <a name="whats-been-announced-for-ui-updates-for-end-user-apps"></a>Co je ohlášené ohledně aktualizací uživatelského rozhraní pro aplikace pro koncové uživatele

### <a name="february-2017"></a>Únor 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622, announced 1702-->
Od března bude aplikace Portál společnosti pro Android odpovídat [specifikacím Material Design](https://material.io/guidelines/material-design/introduction.html) a získá tak modernější vzhled a chování. Toto vylepšené uživatelské prostředí zahrnuje:

* __Barvy__: Záhlaví karet můžou mít barvy podle vaší vlastní palety barev.

![Nalevo je obrázek aplikace Portál společnosti pro Android před aktualizací. Napravo je obrázek aplikace Portál společnosti pro Android po aktualizaci. Na obou obrázcích je karta Zařízení jako vybraná karta ze tří dostupných karet Aplikace, Zařízení a Kontaktovat oddělení IT.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Rozhraní__: Jsou aktualizovaná tlačítka __Vybrané aplikace__ a __Všechny aplikace__ na kartě __Aplikace__. Tlačítko __Hledat__ je teď plovoucí tlačítko akce.

![Nalevo je obrázek aplikace Portál společnosti pro Android před aktualizací. Napravo je obrázek aplikace Portál společnosti pro Android po aktualizaci. Na obou obrázcích je karta Aplikace jako vybraná karta ze tří dostupných karet Aplikace, Zařízení a Kontaktovat oddělení IT.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigace__: V části Všechny aplikace se teď zobrazují karty __Doporučené__, __Vše__ a __Kategorie__, které zjednodušují navigaci. __Kontaktovat oddělení IT__ je teď jednodušší a s vylepšenou čitelností.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Leden 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernizace webu Portál společnosti <!--753980, announced 1701-->
Od února bude web Portál společnosti podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma, dynamické ilustrace a „hamburgerovou“ nabídku ![Obrázek hamburgerové nabídky, která je teď přidaná v levém horním rohu webu Portál společnosti](./media/CP_hamburger_menu.png) , která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace.

![Vlevo je obrázek současné verze webu Portál společnosti s předchozí verzí zobrazení Aplikace, Moje zařízení, Doporučené a Kategorie. Vpravo je obrázek aktualizované verze webu Portál společnosti s novým karuselem aplikací, seznamem Nedávno publikované aplikace a aktualizovaným zobrazením Kategorie.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co je nového – archiv](whats-new-archive.md)

