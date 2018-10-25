---
title: Omezení zařízení pro pracovní profily Androidu v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s profily Androidu Enterprise můžete omezit některá nastavení včetně kopírování a vkládání, zobrazování oznámení, oprávnění aplikací, sdílení dat, délky hesla, neúspěšných přihlášení, odemykání pomocí otisku prstu, opakovaného použití hesel a povolení sdílení pracovních kontaktů přes Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6a633b73856b5f9f50ffe0b9993713b888b969b
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828138"
---
# <a name="work-device-restriction-settings-in-intune"></a>Nastavení omezení pracovních zařízení v Intune

Tento článek uvádí nastavení omezení zařízení v Microsoft Intune, která můžete nakonfigurovat pro zařízení s profilem Androidu Enterprise.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Nastavení pracovního profilu

### <a name="general-settings"></a>Obecná nastavení

- **Kopírování a vkládání mezi pracovními a osobními profily**: ovládá kopírování a vkládání mezi pracovními a osobními aplikacemi. Zvolením možnosti **Blokovat** zapnete blokování. Zvolením možnosti **Nenakonfigurováno** blokování vypnete.
- **Sdílení dat mezi pracovním a osobním profilem**: určuje, jestli aplikace v pracovním profilu můžou používat sdílení s aplikacemi v osobním profilu. Toto nastavení řídí akce sdílení v rámci aplikací, například možnost **Sdílet** v aplikaci prohlížeče Chrome. Toto nastavení se nevztahuje na chování schránky při kopírování/vkládání. Na rozdíl od [nastavení zásad ochrany aplikací](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) se nastavení omezení zařízení spravují na portálu Intune a k izolování spravovaných aplikací používají oddíl pracovního profilu Androidu. Vybírejte z těchto možností:
  - **Výchozí omezení sdílení**: jedná se o výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neblokuje sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: povoluje integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Povolit sdílení přes hranice**: umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení. Proto ho používejte opatrně.

- **Oznámení z pracovního profilu, když je zařízení zamknuté**: řídí, jestli aplikace v pracovním profilu můžou zobrazovat data v oznámeních, když je zařízení zamknuté.
- **Výchozí oprávnění aplikace**: umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Tyto zásady používejte k automatickému udělování oprávnění bez výzvy, automatickému odepření oprávnění bez výzvy nebo ponechání rozhodnutí na koncovém uživateli. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Zeptat se**
  - **Automaticky udělit**
  - **Automaticky odepřít**

    Zásady konfigurace aplikace můžete použít také k udělení oprávnění pro jednotlivé aplikace (**Klientské aplikace** > **Zásady konfigurace aplikací**).

- **Přidat nebo odebrat účty**

   Zabrání koncovým uživatelům ručně přidávat nebo odebírat účty v pracovním profilu.

   Když do pracovního profilu Androidu nasadíte například aplikaci Gmail, můžete zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v tomto pracovním profilu.

- **Sdílení kontaktů přes Bluetooth**: Povoluje přístup k pracovním kontaktům z jiného zařízení, například ze zařízení v autě, které je spárováno pomocí Bluetooth. Ve výchozím nastavení toto nastavení není nakonfigurováno a pracovní kontakty se nezobrazují. Vyberte **Povolit** a sdílení povolte, aby se zobrazily kontakty pracovního profilu. Toto nastavení platí pro zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších. Když toto nastavení povolíte, budou určitá zařízení Bluetooth ukládat pracovní kontakty do mezipaměti při prvním připojení. V případě jejího zakázání po počátečním zpárování/synchronizaci se pracovní kontakty ze zařízení Bluetooth nemusí odstranit.

- **Snímek obrazovky**: Blokuje snímek obrazovky v pracovním profilu zařízení. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa.

- **Zobrazit v osobním profilu ID volajícího pracovního kontaktu**: Pokud je povoleno (nenakonfigurováno), zobrazují se v osobním profilu podrobnosti o volajícím, pokud jde o pracovní kontakt. V případě blokování se číslo volajícího pracovního kontaktu v osobním profilu nezobrazuje. Platí pro operační systém Android 6.0 a novější verze.

- **Kamera**: Blokuje v pracovním profilu zařízení kameru. Nastavení nemá vliv na kameru v osobním profilu.

### <a name="work-profile-password"></a>Heslo pracovního profilu

- **Vyžadovat heslo pracovního profilu**: platí pro Android 7.0 a vyšší s aktivovaným pracovním profilem. Umožňuje definovat zásady hesla, které platí jenom pro aplikace v pracovním profilu. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich.
- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**16**.
- **Maximální doba neaktivity v minutách, než se pracovní profil zamkne**: umožňuje vybrat dobu, po které se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se pracovní profil ze zařízení vymaže.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: blokuje koncovému uživateli možnost používat skener otisků prstů zařízení k odemknutí zařízení.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti**: umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se také říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo pracovního profilu, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="device-password"></a>Heslo zařízení

- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**14**.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: umožňuje vybrat dobu, po které neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se ze zařízení vymažou veškerá data.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: blokuje koncovému uživateli možnost používat skener otisků prstů zařízení k odemknutí zařízení.
- **Smart Lock a jiní agenti pro určování důvěryhodnosti**: umožňuje řídit funkci Smart Lock na kompatibilních zařízeních. Tato funkce telefonů, které se také říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

## <a name="system-security"></a>Zabezpečení systému

- **Kontrola ohrožení aplikací**: vynutí zapnutí nastavení **Ověřovat aplikace** pro pracovní a osobní profily.

   > [!Note]
   > Toto nastavení funguje jenom u zařízení s Androidem O a vyšším.

## <a name="connectivity"></a>Připojení

- **Neustále aktivní připojení VPN**: výběrem možnosti **Povolit** nastavte klienta VPN tak, aby se automaticky připojoval a znovu připojoval k VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN. 

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: vyberte klienta VPN, který podporuje neustále aktivní připojení VPN. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: zadejte ID balíčku aplikace v obchodu Google Play. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

    > [!IMPORTANT]
    >  - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
    >  - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.

- **Režim uzamčení**: **Povolte**, abyste vynutili používání tunelu VPN veškerým síťovým provozem. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="next-step"></a>Další krok

[Přiřaďte profily](device-profile-assign.md) uživatelům a zařízením.
