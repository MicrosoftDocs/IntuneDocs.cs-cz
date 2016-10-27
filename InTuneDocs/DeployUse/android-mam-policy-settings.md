---
title: "Nastavení zásad MAM pro Android | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad správy mobilních aplikací pro zařízení s Androidem."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7313854dc9cee26412ed4759e570f0aecc5f156b
ms.openlocfilehash: e8b1ccca0c905ccdefd5c4a97b78561c6edb7908


---

# Nastavení zásad správy mobilních aplikací pro Android v Microsoft Intune
Níže popsané nastavení zásad MAM se dá [nakonfigurovat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) v okně **Nastavení** na portálu Azure.
Existují dvě kategorie nastavení zásad – přemístění dat a přístup:

##  Nastavení přemístění dat
Výrazem **aplikace spravované podle zásad** se označují aplikace, které mají nakonfigurované zásady MAM.
- **Zabránit zálohování dat v zařízeních s Androidem**: Pokud chcete zakázat zálohování firemních dat z aplikací spravovaných podle zásad, vyberte **Ano**, a pokud je chcete povolit, vyberte **Ne**.

  **Výchozí hodnota = Ano**
- **Povolit aplikaci posílat data do jiných aplikací**: Výběrem jedné z možností určete aplikace, které můžou přijímat firemní data z aplikací spravovaných podle zásad:
  -   **Aplikace spravované podle zásad**: Povoluje přenos jenom do aplikací se zásadou MAM.
  -   **Všechny aplikace**: Povoluje přenos do všech aplikací.
  -   **Žádné**: Nepovoluje přenos dat do žádné aplikace.

  **Výchozí hodnota = Aplikace spravované podle zásad**
- **Povolit aplikaci přijímat data z jiných aplikací**: Zadejte aplikace, které můžou přenášet data do aplikací spravovaných podle zásad:
  -   **Aplikace spravované podle zásad**: Povoluje přenos dat jenom z ostatních aplikací spravovaných podle zásad.
  -   **Všechny aplikace**: Povoluje přenos dat ze všech aplikací.
  -   **Žádné**: Nepovoluje přenos dat ze žádné aplikace.

      **Výchozí hodnota = Všechny aplikace**

-   **Zakázat možnost Uložit jako**: Výběrem **Ano** zakážete použití možnosti Uložit jako ve všech aplikacích, které používají tuto zásadu. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**.

  **Výchozí hodnota = Ano**
- **Omezit operace vyjmutí, kopírování a vložení s jinými aplikacemi**: Určete, kdy se mají omezit operace vyjmutí, kopírování a vkládání. Vybírejte z těchto možností:
  -   **Blokované**: Nepovoluje operace vyjmutí, kopírování a vložení mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace spravované podle zásad**: Povoluje operace vyjmutí, kopírování a vložení jenom mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace s vložením spravované podle zásad**: Povoluje vyjmutí a kopírování dat mezi aplikacemi spravovanými podle zásad. Umožňuje vložit do této aplikace data vyjmutá nebo zkopírovaná z jakékoliv jiné aplikace.
  -   **Libovolná aplikace**: Operace vyjmutí, kopírování a vložení mezi aplikacemi nejsou nijak omezené.

    **Výchozí hodnota = Aplikace s vložením spravované podle zásad**
-   **Omezit webový obsah tak, aby se spouštěl v Managed Browser**: Když je toto nastavení povolené, otevřou se jakékoli odkazy v aplikaci ve spravovaném prohlížeči.

  Pro zařízení, která nejsou zaregistrovaná v Intune, se webové odkazy v aplikacích spravovaných podle zásad otevřou jenom v aplikaci spravovaného prohlížeče, která používá zásadu správy mobilních aplikací.

  Pokud ke správě zařízení používáte Intune, přečtěte si téma věnované [správě přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Výchozí hodnota = Ano**
- **Šifrovat data aplikace**: Pokud chcete povolit šifrování, vyberte **Ano**. Když je toto nastavení povolené, pro aplikace, které jsou přidružené k zásadám správy mobilních aplikací, zajišťuje šifrování Microsoft. Data jsou mezi vstupně-výstupními operacemi souborů synchronně šifrovaná. Obsah v úložišti zařízení je zašifrovaný vždycky.
  >[!NOTE]
  >Metoda šifrování nemá certifikaci FIPS 140-2

  **Výchozí hodnota = Ano**

- **Zakázat synchronizaci kontaktů:** Pokud chcete zabránit synchronizaci kontaktních informací do nativní aplikace adresáře na zařízení, zvolte **Ano**. Pokud vyberete **Ne**, aplikace uloží kontaktní informace do nativní aplikace adresáře na zařízení.<br/>Když k odebrání firemních dat použijete selektivní vymazání, dojde k odebrání kontaktů přímo synchronizovaných z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace **Microsoft Outlook**.

  **Výchozí hodnota = Ano**
- **Zakázat tisk:** Zvolením možnosti **Ano** zakážete tisk firemních dat z aplikací, které jsou přidružené k zásadám MAM.

  **Výchozí hodnota = Ano**

##  Nastavení zásad přístupu pro Android
Výrazem **aplikace spravované podle zásad** se označují aplikace, které mají nakonfigurované zásady MAM.

- **Vyžadovat pro přístup kód PIN**: Pokud chcete k použití aplikací spravovaných podle zásad vyžadovat kód PIN, vyberte **Ano**. Uživatel se vyzve k jeho nastavení při prvním spuštění aplikace v pracovním kontextu.

 **Výchozí hodnota = Ano**

 -  **Povolit jednoduchý kód PIN:** Určete, jestli se uživatelům povoluje použití jednoduchého kódu PIN, jako je 1234 nebo 1111. **Výchozí hodnota = Ano**
 - **Délka kódu PIN**: Zadejte minimální počet číslic v kódu PIN. **Výchozí hodnota = 4**
 - **Počet pokusů, než se musí PIN kód resetovat**: Zadejte počet možných pokusů o zadání kódu PIN, než uživatel musí PIN resetovat. **Pro toto nastavení neexistuje výchozí hodnota.**
- **Vyžadovat pro přístup podnikové přihlašovací údaje**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete podnikové přihlašovací údaje, vyberte **Ano**.  Pokud nastavíte **Ano**, přepíše se tím požadavek na PIN nebo Touch ID.  Uživatel se vyzve k zadání podnikových přihlašovacích údajů.

  **Výchozí hodnota = Ne**
- **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**: Pokud chcete blokovat spouštění aplikací na zařízeních s jailbreakem nebo rootem, vyberte **Ano**. Uživatel bude moct i dál používat zařízení pro své osobní účely, ale při práci bude muset používat jiné zařízení.

  **Výchozí hodnota = Ano**
- **Znova zkontrolovat požadavky pro přístup za (min.)**-   **Časový limit:** Určuje čas (v minutách), než se znovu zkontrolují požadavky na přístup k aplikaci.
  -   **Období odkladu pro offline režim**: Pokud je zařízení offline, určete časové období (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci.

    **Výchozí hodnoty = časový limit 30 minut a období odkladu pro offline režim 720 minut**

-   **Doba v offline režimu (ve dnech) před vymazáním dat**: Můžete vybrat, že se firemní data vymažou, když je zařízení po určitou dobu offline.  Zadejte počet dnů, po který zařízení může být offline, než se z něj odeberou firemní data. **Tip:** Zadáním hodnoty 0 toto nastavení vypnete.

  **Výchozí hodnota = 90 dní**
- **Blokovat snímek obrazovky a Android Assistant (Android Marshmallow 6 nebo novější)**: Pokud chcete na zařízení zablokovat snímky obrazovky a funkci **Android Assistant** při použití této aplikace, vyberte **Ano**.



<!--HONumber=Oct16_HO2-->


