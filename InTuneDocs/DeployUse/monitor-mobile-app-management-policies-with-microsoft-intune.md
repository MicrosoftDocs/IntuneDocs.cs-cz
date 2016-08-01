---
title: "Monitorování zásad MAM s Microsoft Intune | Microsoft Intune"
description: "Podívejte se, kolik uživatelů má zásady, a přechodem k podrobnostem zjistěte další informace."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 644860abcd351d24f08d7a517a3a4b5f44824689
ms.openlocfilehash: 1d22d26c1a1c52dda4f9b01658d22f8de8187f0f


---

# Monitorování zásad správy mobilních aplikací s Microsoft Intune
Jakmile nakonfigurujete zásadu MAM a použijete ji pro uživatele, můžete na [portálu Azure](https://portal.azure.com) monitorovat stav dodržování předpisů. Portál Azure obsahuje informace o uživatelích ovlivněných zásadou, stav dodržování předpisů a veškeré problémy, se kterými se mohou vaši koncoví uživatelé setkat.
## Souhrnné zobrazení
Níže se dozvíte, jak můžete v okně **Správa mobilních aplikací Intune** zobrazit souhrn stavu dodržování předpisů:


![Dlaždice souhrnu okna Správa mobilních aplikací Intune](../media/mam-azure-portal-user-status-summary.png)

-   **UŽIVATELÉ:** Celkový počet uživatelů ve vaší společnosti, kteří používají aplikace přidružené k zásadě.

-   **SPRAVOVANÉ ZÁSADOU:** Počet uživatelů, kteří použili aspoň jednu z aplikací v pracovním kontextu.

-   **ŽÁDNÉ ZÁSADY:** Počet uživatelů, kteří používají aplikace přidružené k zásadě, ale nejsou cílem vaší zásady.  Zvažte přidání těchto uživatelů do vaší zásady.

- **Uživatelé označení příznakem:** Počet uživatelů, kteří mají problémy. Aktuálně jsou v části **Uživatelé označení příznakem** uvedení jenom uživatelé se zařízením s jailbreakem.


## Podrobné zobrazení
Můžete získat podrobné zobrazení souhrnu kliknutím na dlaždici **Stav uživatele** a dlaždici **Uživatelé označení příznakem**.

### Stav uživatele
Můžete vyhledat jednoho uživatele a podívat se na stav dodržování předpisů pro tohoto uživatele. Okno **Vytváření sestav aplikace** zobrazuje pro vybraného uživatele následující informace:
- Zařízení, která jsou přidružená k účtu uživatele
- Aplikace se zásadou MAM na zařízení
- Stav:

  **Zaregistrováno:** Znamená, že byla zásada nasazena uživateli a aplikace se aspoň jednou použila v pracovním kontextu.

  **Není zaregistrováno:** Znamená, že došlo k nasazení zásady pro uživatele, ale aplikace se od té doby nepoužila v pracovním kontextu.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva oznamující, že uživatel není cílem žádné zásady pro aplikace.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

**Krok 1:** Pokud chcete vybrat uživatele, klikněte na dlaždici souhrnu nebo zvolte možnost **VYTVÁŘENÍ SESTAV APLIKACE UŽIVATELEM** v okně **Nastavení**, jak je uvedeno níže:

![Možnost vytváření sestav v okně Nastavení](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

**Krok 2:** Otevře se okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a vyhledejte uživatele služby Azure Active Directory.

![Možnost volby uživatele v okně Vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-select-user.png)

**Krok 3:** Po výběru uživatele ze seznamu se zobrazí podrobnosti o stavu dodržování předpisů pro tohoto uživatele.

![Podrobnosti vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-by-user.png)
### Uživatelé označení příznakem
V podrobném zobrazení se zobrazí chybová zpráva, aplikace, ke které se přistupovalo, když chyba nastala, platforma zařízení a časové razítko.  

### Viz taky
[Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

[Činnost koncového uživatele v aplikacích s podporou správy mobilních aplikací (MAM)](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


