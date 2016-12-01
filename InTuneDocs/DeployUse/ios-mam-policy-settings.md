---
title: "Nastavení zásad MAM pro iOS | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad správy mobilních aplikací pro zařízení s iOS."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eb9cc86646e08b85148a273cee3c0f2b7b6a6efb
ms.openlocfilehash: 913008568226621de4824c5bac287e8a65dc6533


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Nastavení zásad správy mobilních aplikací pro iOS
Nastavení zásad popsané v tomto tématu se dá [nakonfigurovat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pro zásady správy mobilních aplikací (MAM) v okně **Nastavení** na portálu Azure Portal.

Existují dvě kategorie nastavení zásad:nastavení přemístění dat a nastavení přístupu. Výrazem *aplikace spravované podle zásad* se v tomto tématu označují aplikace, které mají nakonfigurované zásady MAM.

##  <a name="data-relocation-settings"></a>Nastavení přemístění dat

- **Zakázat zálohování dat v iTunes a na iCloudu**: Pokud chcete zakázat zálohování firemních dat z aplikací spravovaných podle zásad, zvolte **Ano**, a pokud je chcete povolit, zvolte **Ne**.

  Výchozí hodnota = **Ano**

- **Povolit aplikaci posílat data do jiných aplikací**: Výběrem jedné z možností určete aplikace, které můžou přijímat data z aplikací spravovaných podle zásad:
  - **Aplikace spravované podle zásad**: Povoluje přenos jenom do aplikací se zásadami MAM.
  - **Všechny aplikace**: Povoluje přenos do všech aplikací.
  - **Žádné**: Nepovoluje přenos dat do žádné aplikace, včetně ostatních aplikací spravovaných podle zásad.

  Pokud nastavíte tuto možnost na hodnotu **Aplikace spravované podle zásad** nebo **Žádné**, bude blokovaná funkce iOS 9, která umožňuje vyhledávání Spotlight dat v rámci aplikací.

  >[!NOTE]
  >Toto nastavení neřídí použití funkce „Otevřít v“ na mobilních zařízeních. Informace ke správě funkce Otevřít v najdete v tématu [Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Výchozí hodnota = **Aplikace spravované podle zásad**

- **Povolit aplikaci přijímat data z jiných aplikací**: Zadejte aplikace, které můžou přenášet data do aplikací spravovaných podle zásad:
  -  **Aplikace spravované podle zásad**: Povoluje přenos dat jenom z ostatních aplikací spravovaných podle zásad.
  -  **Všechny aplikace**: Povoluje přenos dat ze všech aplikací.
  -  **Žádné**: Nepovoluje přenos dat ze žádné aplikace.

  Výchozí hodnota = **Všechny aplikace**

- **Zakázat možnost Uložit jako**: Výběrem **Ano** zakážete použití možnosti Uložit jako ve všech aplikacích, které používají tuto zásadu. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**.

  Výchozí hodnota = **Ano**

- **Omezit operace vyjmutí, kopírování a vložení s jinými aplikacemi**: Určete, kdy se mají omezit akce vyjmutí, kopírování a vkládání. Vybírejte z těchto možností:
  -   **Blokované**: Nepovoluje akce vyjmutí, kopírování a vložení mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace spravované podle zásad**: Povoluje akce vyjmutí, kopírování a vložení jenom mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace s vložením spravované podle zásad**: Povoluje vyjmutí a kopírování dat mezi aplikacemi spravovanými podle zásad. Umožňuje vložit do této aplikace data vyjmutá nebo zkopírovaná z jakékoliv jiné aplikace.
  - **Libovolná aplikace**: Akce vyjmutí, kopírování a vložení mezi aplikacemi nejsou nijak omezené.

  Výchozí hodnota = **Aplikace s vložením spravované podle zásad**

- **Omezit webový obsah tak, aby se spouštěl v Managed Browseru**: Když je toto nastavení povolené, jakékoli odkazy v aplikaci se otevřou v Managed Browseru.

  Pro zařízení, která nejsou zaregistrovaná v Intune, se webové odkazy v aplikacích spravovaných podle zásad můžou otevřít jenom v aplikaci Managed Browser.

  Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Výchozí hodnota = **Ano**

- **Šifrovat data aplikace**: Pro aplikace, které jsou přidružené k zásadě Intune MAM, jsou uložená data zašifrovaná šifrováním na úrovni zařízení poskytovaným operačním systémem. Když se vyžaduje PIN, data se zašifrují podle nastavení v zásadách MAM. Jak uvádí dokumentace Apple, [moduly používané v iOS 7 mají certifikaci FIPS 140-2](http://support.apple.com/en-us/HT202739).

  V nastavení zásad můžete zadat hodnoty šifrování PIN. Tyto hodnoty určují, kdy se data zašifrují. Možnosti:
  -   **Když je zařízení zamknuté:** Všechna data aplikace přidružená k této zásadě jsou při uzamčení zařízení zašifrovaná.
  -   **Když je zařízení zamknuté (kromě otevřených souborů):** Všechna data aplikace přidružená k této zásadě jsou při uzamčení zařízení zašifrovaná, kromě dat v souborech, které jsou v aplikaci aktuálně otevřené.
  -   **Po restartování zařízení:** Všechna data aplikace přidružená k této zásadě jsou při restartování zařízení zašifrovaná až do doby, než se zařízení poprvé odemkne.
  -   **Použít nastavení zařízení:** Data aplikace se zašifrují podle výchozího nastavení v zařízení.
  Pokud povolíte toto nastavení, musí si uživatel nastavit kód PIN a používat ho pro přístup k zařízení.  Pokud není kód PIN nastavený, aplikace se neotevře a uživateli se místo toho zobrazí zpráva s informacemi o tom, že jeho společnost vyžaduje, aby pro přístup k této aplikaci nejdřív povolil kód PIN zařízení.

  Výchozí hodnota = Možnost šifrování není vybraná.
- **Zakázat synchronizaci kontaktů:** Pokud chcete zabránit synchronizaci kontaktních informací do nativní aplikace adresáře na zařízení, zvolte **Ano**. Pokud vyberete **Ne**, aplikace uloží kontaktní informace do nativní aplikace adresáře na zařízení.

  Když k odebrání firemních dat použijete selektivní vymazání, dojde k odebrání kontaktů přímo synchronizovaných z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook.

  Výchozí hodnota = **Ano**

- **Zakázat tisk:** Zvolením možnosti **Ano** zakážete tisk firemních dat z aplikací, které jsou přidružené k zásadám MAM.

    Výchozí hodnota = **Ano**

##  <a name="access-settings"></a>Nastavení přístupu

- **Vyžadovat pro přístup kód PIN**: Pokud chcete k použití aplikací spravovaných podle zásad vyžadovat kód PIN, vyberte **Ano**. Uživatel se vyzve k jeho nastavení při prvním spuštění aplikace v pracovním kontextu.

  Výchozí hodnota = **Ano**
    -  **Povolit jednoduchý kód PIN:** Určete, jestli můžou uživatelé používat jednoduchý kód PIN, jako je 1234 nebo 1111. Výchozí hodnota = **Ano**
    - **Délka kódu PIN**: Zadejte minimální počet číslic v kódu PIN. Výchozí hodnota = **4**
    - **Počet pokusů, než se musí PIN kód resetovat**: Zadejte počet možných pokusů o zadání kódu PIN, než uživatel musí PIN resetovat. Pro toto nastavení neexistuje výchozí hodnota.

- **Vyžadovat otisk prstu místo kódu PIN (iOS 8.0+)**: Pokud pro přístup k aplikaci místo kódu PIN požadujete otisk prstu, zvolte **Ano**.
V zařízeních s iOSem můžete uživatelům povolit, aby se místo kódu PIN identifikovali otiskem prstu na zařízení s iOSem. Když se uživatel pokusí otevřít tuto aplikaci ze svého pracovního účtu, zobrazí se výzva k zadání otisku prstu a uživatel nemusí zadávat kód PIN.

  Výchozí hodnota = **Ano**
- **Vyžadovat pro přístup podnikové přihlašovací údaje**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete podnikové přihlašovací údaje, vyberte **Ano**. Pokud nastavíte **Ano**, přepíše se tím požadavek na PIN nebo Touch ID. Uživatel se vyzve k zadání podnikových přihlašovacích údajů.

  Výchozí hodnota = **Ne**
- **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**: Pokud chcete blokovat spouštění aplikací na zařízeních s jailbreakem nebo rootem, vyberte **Ano**. Uživatel bude moct i dál používat zařízení pro své osobní účely, ale při práci bude muset používat jiné zařízení.

  Výchozí hodnota = **Ano**
- **Znovu zkontrolovat požadavky na přístup po (minuty)**
  -   **Časový limit:** Určete čas (v minutách), než se znovu zkontrolují požadavky na přístup k aplikaci.
  -   **Období odkladu pro offline režim**: Pokud je zařízení offline, určete časové období (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci.

  Výchozí hodnoty = časový limit **30** minut a období odkladu pro offline režim **720** minut
- **Doba v offline režimu (ve dnech) před vymazáním dat**: Můžete vybrat, že se firemní data vymažou, když je zařízení po určitou dobu offline. Zadejte počet dnů, po který zařízení může být offline, než se z něj odeberou firemní data.

  >[!TIP]
  >Zadáním hodnoty **0** toto nastavení vypnete.

  Výchozí hodnota = **90** dní



<!--HONumber=Oct16_HO5-->


