---
# required metadata

title: Monitorování zásad správy mobilních aplikací s Microsoft Intune | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Monitorování zásad správy mobilních aplikací s Microsoft Intune
Jakmile jste nakonfigurovali zásadu MAM a použili ji pro uživatele, můžete na portálu Azure monitorovat stav dodržování předpisů. Portál Azure obsahuje informace o uživatelích ovlivněných zásadou, stav dodržování předpisů a veškeré problémy, se kterými se mohou vaši koncoví uživatelé setkat.
## Souhrnné zobrazení
Dále je popsáno, jak v okně **Správa mobilních aplikací Intune** můžete zobrazit souhrn stavu dodržování předpisů:


![Dlaždice souhrnu okna Správa mobilních aplikací Intune](../media/mam-azure-portal-user-status-summary.png)

-   **UŽIVATELÉ:** Celkový počet uživatelů ve vaší společnost, kteří používají aplikace přidružené zásadě.

-   **SPRAVOVANÉ ZÁSADOU:** Počet uživatelů, kteří použili aspoň jednu z aplikací v pracovním kontextu.

-   **ŽÁDNÉ ZÁSADY:** Počet uživatelů, kteří používají aplikace přidružené zásadě, ale nejsou cílem vaší zásady.  Zvažte přidání těchto uživatelů do vaší zásady.

- **Uživatelé označení příznakem:** Počet uživatelů, kteří mají problémy. Aktuálně jsou v části **Uživatelé označení příznakem** uvedení jenom uživatelé se zařízením s jailbreakem..


## Podrobné zobrazení
Můžete získat podrobné zobrazení souhrnu kliknutím na dlaždici **Stav uživatele** a dlaždici **Uživatelé označení příznakem**.

### Stav uživatele
Můžete vyhledat jednoho uživatele a podívat se na stav dodržování předpisů pro tohoto uživatele. Okno **Vytváření sestav aplikace** zobrazuje pro vybraného uživatele následující informace:
- Zařízení, která jsou přidružená účtu uživatele
- Aplikace se zásadou MAM na zařízení
- Stav:

  **Zaregistrováno:** Znamená, že byla zásada nasazena uživateli a aplikace byla v pracovním kontextu aspoň jednou použita.

  **Není zaregistrováno:** Znamená, že byla zásada nasazena uživateli, ale aplikace od té doby nebyla použita v pracovním kontextu.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

**Krok 1:** Chcete-li vybrat uživatele, klikněte na dlaždici souhrnu nebo zvolte možnost **VYTVÁŘENÍ SESTAV APLIKACE PODLE UŽIVATELE** v okně **Nastavení**, jak je uvedeno níže:

![Možnost vytváření sestav v okně Nastavení](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

**Krok 2:** Otevře okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a vyhledejte uživatele služby Azure Active Directory.

![Možnost volby uživatele v okně Vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-select-user.png)

**Krok 3:** Po výběru uživatele ze seznamu se zobrazí podrobnosti o stavu dodržování předpisů pro tohoto uživatele.

![Podrobnosti vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-by-user.png)
### Uživatelé označení příznakem
V podrobném zobrazení se zobrazí chybová zpráva, aplikace, ke které se přistupovalo, když chyba nastala, platforma zařízení a časové razítko.  

### Související témata
[Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

[Činnost koncového uživatele v aplikacích s podporou správy mobilních aplikací (MAM)](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


