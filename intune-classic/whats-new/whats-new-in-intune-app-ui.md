---
title: "Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele | Dokumentace Microsoftu"
description: "Zjistěte, co se změnilo v uživatelském rozhraní aplikací, které fungují s Intune na zařízeních pro koncové uživatele."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 629a091c1016186700a95bf76b9feed9ef0adb79
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele
Zjistěte, jaké jsme v uživatelském rozhraní aplikací udělali změny, které koncoví uživatelé uvidí v této verzi Microsoft Intune. Pomůže vám to při komunikaci s uživateli a aktualizaci vlastní dokumentace, kterou jste vytvořili za účelem podpory vašeho nasazení. Můžete také zjistit, jak lépe řešit problémy uživatelů, když požádají helpdesk o podporu pomocí Portálu společnosti.

## <a name="coming-soon-in-the-ui"></a>Již brzy v uživatelském rozhraní
Zde najdete plánované aktualizace našeho uživatelského rozhraní, které vylepší uživatelské prostředí.

> [!Note]
> Upozorňujeme, že následující obrázky mohou být náhledy a avizovaný produkt se od prezentovaných verzí může lišit.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Vylepšené přihlašování k aplikacím Portál společnosti na všech platformách <!--User Story 1132123-->

Avizujeme změnu, kterou uvedeme během několika nadcházejících měsíců a která vylepší přihlašování k aplikacím Portál společnosti Intune v systémech Android, iOS a Windows. Nové uživatelské prostředí se automaticky zobrazí na všech platformách pro aplikaci Portál společnosti, až Azure AD tuto změnu provede. Kromě toho se teď uživatelé můžou k Portálu společnosti přihlašovat z jiného zařízení pomocí vygenerovaného kódu na jedno použití. To se hodí hlavně v případech, kdy se uživatelé potřebují přihlásit bez přihlašovacích údajů.  

Níže můžete vidět předchozí způsob přihlašování, nový způsob přihlašování pomocí přihlašovacích údajů a nový způsobu přihlašování z jiného zařízení.

__Předchozí způsob přihlašování__

![Přihlašovací stránka Portálu společnosti s ikonou osoby před grafickým znázorněním webu. Pod tím je tlačítko „Přihlásit se“. Odkaz dole vede na informace Microsoftu o ochraně osobních údajů a souborech cookie.](./media/cp_ios_aad_signin_before_1704_001.png)

![Po klepnutí na Přihlásit se uživatel zadá své přihlašovací údaje na této stránce, která požádá o uživatelův e-mail a heslo a současně nabídne způsoby, jak vyřešit problémy s heslem.](./media/cp_ios_aad_signin_before_1704_002.png)

![Po zadání hesla aplikace Portál společnosti zobrazí pruh načítání a přihlásí se.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nový způsob přihlašování__

![Přihlašovací stránka Portálu společnosti s ikonou osoby před grafickým znázorněním webu. Pod tím je tlačítko „Přihlásit se“. Odkaz dole vede na informace Microsoftu o ochraně osobních údajů a souborech cookie.](./media/cp_ios_aad_signin_after_1704_001.png)

![Uživatel je vyzván, aby zadal jenom e-mailovou adresu místo zadání e-mailu a hesla na stejné obrazovce.](./media/cp_ios_aad_signin_after_1704_002.png)

![Po přijetí e-mailové adresy je uživatel vyzván k zadání hesla.](./media/cp_ios_aad_signin_after_1704_003.png)

![Po absolvování procesu ověřování aplikace Portál společnosti zobrazí pruh načítání a přihlásí se.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nový způsob přihlášení při přihlašování z jiného zařízení__

![Přihlašovací stránka Portálu společnosti s ikonou osoby před grafickým znázorněním webu. Pod tím je tlačítko „Přihlásit se“. Odkaz dole vede na informace Microsoftu o ochraně osobních údajů a souborech cookie.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Klepněte na odkaz __Přihlásit z jiného zařízení__.

![Zobrazí se pokyny, abyste ze svého pracovního počítače přešli na stránku aka.ms/devicelogin s jedinečným přístupovým kódem a pak kód použili k přihlášení.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Spusťte prohlížeč a přejděte na [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Obrázek uživatelova prohlížeče na pracovním počítači místo aplikace Portál společnosti. Zobrazená stránka „Přihlášení na zařízení“ uživatele vyzve k zadání kódu, který dostal v aplikaci Portál společnosti.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Zadejte kód, který se vám zobrazil v aplikaci Portál společnosti. Když vyberete __Pokračovat__, budete moct provést ověření pomocí libovolné metody, kterou vaše společnost podporuje, například pomocí čipové karty.

![Uživatel zadal svůj jedinečný kód do pole a web „Přihlášení na zařízení“ požádal o potvrzení, že je Portál společnosti Intune správnou aplikací, která má získat ověření pro přihlášení.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Potvrzovací stránka, která uvádí, že se uživatel na svém zařízení přihlásil k aplikaci Portál společnosti a že tuto stránku může zavřít.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

Aplikace Portál společnosti se začne přihlašovat.

![Po absolvování procesu ověřování aplikace Portál společnosti zobrazí pruh načítání a přihlásí se.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="april-2017"></a>Duben 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nové ikony pro Managed Browser a Portál společnosti <!--918433, 918431-->

Managed Browser dostal aktualizované ikony pro verze aplikace pro Android i iOS. Nová ikona bude obsahovat aktualizovaný odznak Intune, aby byla konzistentnější s ostatními aplikacemi v Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Portál společnosti také dostal aktualizované ikony pro verze aplikace pro Android, iOS i Windows, aby byly konzistentnější s ostatními aplikacemi v EM+S. Tyto ikony se budou postupně vydávat pro všechny platformy od dubna do konce května.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Ukazatel průběhu přihlášení v Portálu společnosti pro Android <!--953374-->

Aktualizace aplikace Portál společnosti pro Android zobrazuje indikátor průběhu přihlášení, když uživatel aplikaci spustí nebo pokračuje v jejím používání. Než uživatel získá přístup k aplikaci, indikátor postupně zobrazuje nové stavy od „Připojování...“ přes „Přihlašování...“ po „Kontrolují se požadavky na zabezpečení...“.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune-classic/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Vylepšený stav instalace aplikace pro aplikaci Portál společnosti ve Windows 10 <!--676495-->
Na stránce podrobností aplikace v aplikaci Portál společnosti ve Windows 10 se teď zobrazuje indikátor průběhu instalace. To platí pro moderní aplikace na zařízeních s Windows 10 Anniversary Update a novějšími verzemi.

__Před__
  ![Obrázek předchozí verze načítací obrazovky, na které se jako stav zobrazovalo jen oznámení o tom, že probíhá instalace.](./media/cp_win10_install_status_before_1704.png)

__Po__
  ![Obrázek aktualizované verze načítací obrazovky, na které se teď zobrazuje indikátor průběhu instalace.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Únor 2017

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
            <img src="/intune-classic/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
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
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune/whats-new)
* [Co je nového – archiv](whats-new-archive.md)

