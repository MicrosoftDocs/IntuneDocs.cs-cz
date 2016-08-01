---
title: "Nastavení zásad MAM pro iOS | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad správy mobilních aplikací pro zařízení s iOS."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 09bf7d1343580f7688671bf94d83f40f0a3405c5
ms.openlocfilehash: e0db92b6ecf7a552589ea805f6507ca59e6554b1


---

#  Nastavení zásad správy mobilních aplikací pro iOS
Níže popsané nastavení zásad MAM se dá [nakonfigurovat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) v okně **Nastavení** na portálu Azure.

Existují dvě kategorie nastavení zásad – přemístění dat a přístup:

##  Nastavení přemístění dat
Výrazem **aplikace spravované podle zásad** se označují aplikace, které mají nakonfigurované zásady MAM.

- **Zakázat zálohování dat v iTunes a na iCloudu**: Pokud chcete zakázat zálohování firemních dat z aplikací spravovaných podle zásad, vyberte **Ano**, a pokud je chcete povolit, vyberte **Ne**.

  **Výchozí hodnota = Ano**

- **Povolit aplikaci posílat data do jiných aplikací**: Výběrem jedné z možností určete aplikace, které můžou přijímat data z aplikací spravovaných podle zásad:
  - **Aplikace spravované podle zásad**: Povoluje přenos jenom do aplikací se zásadami MAM.
  - **Všechny aplikace**: Povoluje přenos do všech aplikací.
  - **Žádné**: Nepovoluje přenos dat do žádné aplikace, včetně ostatních aplikací spravovaných podle zásad.

  Pokud nastavíte tuto možnost na hodnotu **Aplikace spravované podle zásad** nebo **Žádné**, bude blokovaná funkce iOS 9, která umožňuje vyhledávání Spotlight dat v rámci aplikací.

  **Toto nastavení neřídí použití funkce Otevřít v na mobilních zařízeních. Informace ke správě funkce Otevřít v najdete [zde](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)**.

  **Výchozí hodnota = Aplikace spravované podle zásad**

- **Povolit aplikaci přijímat data z jiných aplikací**: Zadejte aplikace, které můžou přenášet data do aplikací spravovaných podle zásad:
  -  **Aplikace spravované podle zásad**: Povoluje přenos dat jenom z ostatních aplikací spravovaných podle zásad.
  -  **Všechny aplikace**: Povoluje přenos dat ze všech aplikací.
  -  **Žádné**: Nepovoluje přenos dat ze žádné aplikace.

  **Výchozí hodnota = Všechny aplikace**

- **Zakázat možnost Uložit jako**: Výběrem **Ano** zakážete použití možnosti Uložit jako ve všech aplikacích, které používají tuto zásadu. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**.

  **Výchozí hodnota = Ano**

- **Omezit operace vyjmutí, kopírování a vložení s jinými aplikacemi**: Určete, kdy se mají omezit operace vyjmutí, kopírování a vkládání. Vybírejte z těchto možností:
  -   **Blokované**: Nepovoluje operace vyjmutí, kopírování a vložení mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace spravované podle zásad**: Povoluje operace vyjmutí, kopírování a vložení jenom mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace s vložením spravované podle zásad**: Povoluje vyjmutí a kopírování dat mezi aplikacemi spravovanými podle zásad. Umožňuje vložit do této aplikace data vyjmutá nebo zkopírovaná z jakékoliv jiné aplikace.
  - **Libovolná aplikace**: Operace vyjmutí, kopírování a vložení mezi aplikacemi nejsou nijak omezené.

  **Výchozí hodnota = Aplikace s vložením spravované podle zásad**

- **Omezit webový obsah tak, aby se spouštěl v Managed Browser**: Když je toto nastavení povolené, jakékoli odkazy v aplikaci se otevřou v Managed Browseru.

  Pro zařízení, která nejsou zaregistrovaná v Intune, se webové odkazy v aplikacích spravovaných podle zásad otevřou jenom v aplikaci Managed Browser s využitím zásad správy mobilních aplikací.

  Pokud ke správě zařízení používáte Intune, přečtěte si téma věnované [správě přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Výchozí hodnota = Ano**

- **Šifrovat data aplikace**: Pro aplikace, které jsou přidružené k zásadám správy mobilních aplikací [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], jsou uložená data zašifrovaná pomocí šifrování na úrovni zařízení poskytované operačním systémem. Když se vyžaduje PIN, data se zašifrují podle nastavení v zásadách správy mobilních aplikací. Jak uvádí dokumentace Apple, [moduly používané v iOS 7 mají certifikaci FIPS 140-2](http://support.apple.com/en-us/HT202739).

  V nastavení zásad můžete zadat hodnoty šifrování PIN.  Tyto hodnoty určují, kdy se data zašifrují. Možnosti:
  - **Když je zařízení zamknuté:** Všechna data aplikace přidružená k této zásadě jsou při uzamčení zařízení zašifrovaná.
  -   **Když je zařízení zamknuté (kromě otevřených souborů):** Všechna data aplikace přidružená k této zásadě jsou při uzamčení zařízení zašifrovaná, kromě dat v souborech, které jsou v aplikaci aktuálně otevřené.
  -   **Po restartování zařízení:** Všechna data aplikace přidružená k této zásadě jsou při restartování zařízení zašifrovaná až do doby, než se zařízení poprvé odemkne.
  -   **Použít nastavení zařízení:** Data aplikace se zašifrují podle výchozího nastavení v zařízení.
  Pokud povolíte toto nastavení, musí si koncový uživatel nastavit kód PIN a používat ho pro přístup k zařízení.  Pokud není kód PIN pro přístup k zařízení nastavený, aplikace se nespustí a koncovému uživateli se místo toho zobrazí zpráva s informacemi o tom, že jeho společnost vyžaduje, aby pro přístup k dané aplikaci nejprve povolil kód PIN zařízení.

  **Výchozí hodnota – Možnost šifrování není vybraná.**
- **Zakázat synchronizaci kontaktů:** Pokud chcete zabránit synchronizaci kontaktních informací do nativní aplikace adresáře na zařízení, zvolte **Ano**. Pokud vyberete **Ne**, aplikace uloží kontaktní informace do nativní aplikace adresáře na zařízení.

  Když k odebrání firemních dat použijete selektivní vymazání, dojde k odebrání kontaktů přímo synchronizovaných z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace **Microsoft Outlook**.

  **Výchozí hodnota = Ano**
##  Nastavení zásad přístupu pro iOS
Výrazem **aplikace spravované podle zásad** se označují aplikace, které mají nakonfigurované zásady MAM.
- **Vyžadovat pro přístup kód PIN**: Pokud chcete k použití aplikací spravovaných podle zásad vyžadovat kód PIN, vyberte **Ano**. Uživatel se vyzve k jeho nastavení při prvním spuštění aplikace v pracovním kontextu.

  **Výchozí hodnota = Ano**
    -  **Povolit jednoduchý kód PIN:** Určete, jestli se uživatelům povoluje použití jednoduchého kódu PIN, jako je 1234 nebo 1111. **Výchozí hodnota = Ano**
    - **Délka kódu PIN**: Zadejte minimální počet číslic v kódu PIN. **Výchozí hodnota = 4**
    - **Počet pokusů, než se musí PIN kód resetovat**: Zadejte počet možných pokusů o zadání kódu PIN, než uživatel musí PIN resetovat.
  **Pro toto nastavení neexistuje výchozí hodnota.**

  - **Vyžadovat otisk prstu místo kódu PIN (iOS 8.0+)**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete otisk prstu, vyberte **Ano**.
V zařízeních s iOS můžete uživatelům povolit, aby se místo číselného kódu PIN identifikovali pomocí otisku prstu na zařízení iOS. Když se koncový uživatel pokusí o přístup k této aplikaci pomocí svého pracovního účtu, vyzve se k zadání otisku prstu a nemusí zadávat číselný PIN.

    **Výchozí hodnota = Ano**
- **Vyžadovat pro přístup podnikové přihlašovací údaje**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete podnikové přihlašovací údaje, vyberte **Ano**. **Pokud nastavíte Ano, přepíše se tím požadavek na PIN nebo Touch ID.** Uživatel se vyzve k zadání podnikových přihlašovacích údajů.

  **Výchozí hodnota = Ne**
- **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**: Pokud chcete blokovat spouštění aplikací na zařízeních s jailbreakem nebo rootem, vyberte **Ano**. Uživatel bude moct i dál používat zařízení pro své osobní účely, ale při práci bude muset používat jiné zařízení.

  **Výchozí hodnota = Ano**
- **Znova zkontrolovat požadavky pro přístup za (min.)**|-   **Časový limit:** Určuje čas (v minutách), než se znovu zkontrolují požadavky na přístup k aplikaci.
  -   **Období odkladu pro offline režim**: Pokud je zařízení offline, určete časové období (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci.

  **Výchozí hodnota = časový limit 30 minut a období odkladu pro offline režim 720 minut**
  - **Doba v offline režimu (ve dnech) před vymazáním dat**: Můžete vybrat, že se firemní data vymažou, když je zařízení po určitou dobu offline.  Zadejte počet dnů, po který zařízení může být offline, než se z něj odeberou firemní data. **Zadáním hodnoty 0 toto nastavení vypnete.**

  **Výchozí hodnota = 90 dní**



<!--HONumber=Jul16_HO3-->


