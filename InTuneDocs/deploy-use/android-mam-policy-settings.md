---
title: "Nastavení zásad MAM pro Android | Microsoft Intune"
description: "Toto téma popisuje nastavení zásad správy mobilních aplikací pro zařízení s Androidem."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d0a1a2b3f4e5dbac8b333db3a5cc4bb32c0d61ef


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Nastavení zásad správy mobilních aplikací pro Android v Microsoft Intune
Nastavení zásad popsané v tomto tématu se dá [nakonfigurovat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pro zásady správy mobilních aplikací (MAM) v okně **Nastavení** na portálu Azure Portal.
Existují dvě kategorie nastavení zásad:nastavení přemístění dat a nastavení přístupu. Výrazem *aplikace spravované podle zásad* se v tomto tématu označují aplikace, které mají nakonfigurované zásady MAM.

##  <a name="data-relocation-settings"></a>Nastavení přemístění dat

- **Zabránit zálohování dat v zařízeních s Androidem**: Pokud chcete zakázat zálohování firemních dat z aplikací spravovaných podle zásad, vyberte **Ano**, a pokud je chcete povolit, vyberte **Ne**.

  Výchozí hodnota = **Ano**
- **Povolit aplikaci posílat data do jiných aplikací**: Zvolením jedné z možností určete typ aplikací, které můžou přijímat firemní data z aplikací spravovaných podle zásad:
  -   **Aplikace spravované podle zásad**: Povoluje přenos jenom do aplikací se zásadami MAM.
  -   **Všechny aplikace**: Povoluje přenos do všech aplikací.
  -   **Žádné**: Nepovoluje přenos dat do žádné aplikace.

 Výchozí hodnota = **Aplikace spravované podle zásad**
- **Povolit aplikaci přijímat data z jiných aplikací**: Zadejte, které aplikace můžou přenášet data do aplikací spravovaných podle zásad:
  -   **Aplikace spravované podle zásad**: Povoluje přenos dat jenom z ostatních aplikací spravovaných podle zásad.
  -   **Všechny aplikace**: Povoluje přenos dat ze všech aplikací.
  -   **Žádné**: Nepovoluje přenos dat ze žádné aplikace.

  Výchozí hodnota = **Všechny aplikace**

-   **Zakázat možnost Uložit jako**: Výběrem **Ano** zakážete použití možnosti Uložit jako ve všech aplikacích, které používají tuto zásadu. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**.

  Výchozí hodnota = **Ano**
- **Omezit operace vyjmutí, kopírování a vložení s jinými aplikacemi**: Určete, kdy se mají omezit akce vyjmutí, kopírování a vkládání. Vybírejte z těchto možností:
  -   **Blokované**: Nepovoluje akce vyjmutí, kopírování a vložení mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace spravované podle zásad**: Povoluje akce vyjmutí, kopírování a vložení jenom mezi aplikacemi spravovanými podle zásad.
  -   **Aplikace s vložením spravované podle zásad**: Povoluje vyjmutí a kopírování dat mezi aplikacemi spravovanými podle zásad. Umožňuje vložit do této aplikace data vyjmutá nebo zkopírovaná z jakékoliv jiné aplikace.
  -   **Libovolná aplikace**: Akce vyjmutí, kopírování a vložení mezi aplikacemi nejsou nijak omezené.

  Výchozí hodnota = **Aplikace s vložením spravované podle zásad**
-   **Omezit webový obsah tak, aby se spouštěl v Managed Browseru**: Když vyberete **ano**, všechny odkazy v aplikaci se otevřou v Managed Browseru.

  Na zařízeních, která nejsou zaregistrovaná v Intune, se odkazy v aplikacích spravovaných podle zásad můžou otevřít v Managed Browseru, jenom když použijete zásady MAM.

  Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Výchozí hodnota = **Ano**
- **Šifrovat data aplikace**: Pokud chcete povolit šifrování, vyberte **Ano**. Když je toto nastavení povolené, pak Microsoft zajišťuje šifrování pro aplikace, které jsou přidružené k zásadám MAM. Data jsou mezi vstupně-výstupními úlohami souborů synchronně šifrovaná. Obsah v úložišti zařízení je zašifrovaný vždycky.
  >[!NOTE]
  >Metoda šifrování nemá certifikaci FIPS 140-2.

  Výchozí hodnota = **Ano**

- **Zakázat synchronizaci kontaktů:** Pokud chcete zabránit synchronizaci kontaktních informací s nativní aplikací adresáře na zařízení, zvolte **Ano**. Pokud vyberete **Ne**, aplikace uloží kontaktní informace do nativní aplikace adresáře na zařízení.

  Když k odebrání firemních dat použijete selektivní vymazání, dojde k odebrání kontaktů přímo synchronizovaných mezi aplikací a nativním adresářem. Kontakty synchronizované mezi nativním adresářem a dalším externím zdrojem není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook.

  Výchozí hodnota = **Ano**
- **Zakázat tisk:** Zvolením možnosti **Ano** zakážete tisk firemních dat z aplikací, které jsou přidružené k zásadám MAM.

  Výchozí hodnota = **Ano**

##  <a name="access-settings"></a>Nastavení přístupu

- **Vyžadovat pro přístup kód PIN**: Pokud chcete k použití aplikací spravovaných podle zásad vyžadovat kód PIN, vyberte **Ano**. Uživatel se vyzve k jeho nastavení při prvním spuštění aplikace v pracovním kontextu.

 Výchozí hodnota = **Ano**

 -  **Povolit jednoduchý kód PIN:** Určete, jestli můžou uživatelé používat jednoduchý kód PIN, jako je 1234 nebo 1111. Výchozí hodnota = **Ano**
 - **Délka kódu PIN**: Zadejte minimální počet číslic v kódu PIN. Výchozí hodnota = **4**
 - **Počet pokusů, než se musí PIN kód resetovat**: Zadejte počet možných pokusů o zadání kódu PIN, než uživatel musí PIN resetovat. Pro toto nastavení neexistuje výchozí hodnota.
 - **Vyžadovat otisk prstu místo kódu PIN (Android 6.0+)**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete otisk prstu, vyberte **Ano**.
 Na zařízeních s Androidem můžete uživatelům povolit, aby se místo číselného kódu PIN identifikovali pomocí otisku prstu. Když se uživatel pokusí otevřít tuto aplikaci ze svého pracovního účtu, zobrazí se výzva k zadání otisku prstu a uživatel nemusí zadávat kód PIN.
 - **Vyžadovat pro přístup podnikové přihlašovací údaje**: Pokud pro přístup k aplikaci místo číselného kódu PIN požadujete podnikové přihlašovací údaje nebo otisk prstu, zvolte **Ano**. Pokud nastavíte **Ano**, toto nastavení přepíše požadavek na PIN nebo Touch ID. Uživatel se vyzve k zadání podnikových přihlašovacích údajů. Výchozí hodnota = **Ne**


- **Blokovat spouštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem**: Pokud chcete blokovat spouštění aplikací na zařízeních s jailbreakem nebo rootem, vyberte **Ano**. Uživatel může dál používat aplikace pro osobní účely, ale k práci musí používat jiné zařízení.

  Výchozí hodnota = **Ano**
- **Znovu zkontrolovat požadavky na přístup po (minuty)**
  -   **Časový limit:** Určete čas (v minutách), než se znovu zkontrolují požadavky na přístup k aplikaci.
  -   **Období odkladu pro offline režim**: Pokud je zařízení offline, určete časové období (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci.

  Výchozí hodnoty = časový limit **30** minut a období odkladu pro offline režim **720** minut

-   **Doba v offline režimu (ve dnech) před vymazáním dat**: Můžete vybrat, že se firemní data vymažou, když je zařízení po určitou dobu offline.  Zadejte počet dnů, po který zařízení může být offline, než se z něj odeberou firemní data.

    >[!TIP]
    >Zadáním hodnoty **0** toto nastavení vypnete.

  Výchozí hodnota = **90** dní
- **Blokovat snímek obrazovky a Android Assistant (Android Marshmallow 6 nebo novější)**: Pokud chcete na zařízení zablokovat snímky obrazovky a funkci **Android Assistant** při použití této aplikace, vyberte **Ano**.



<!--HONumber=Dec16_HO2-->


