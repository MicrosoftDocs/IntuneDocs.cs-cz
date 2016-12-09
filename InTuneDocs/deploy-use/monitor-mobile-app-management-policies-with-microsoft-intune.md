---
title: "Monitorování zásad MAM s Microsoft Intune | Microsoft Intune"
description: "Podívejte se, kolik uživatelů má přiřazené zásady. Přechodem k podrobnostem zjistíte další informace."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 487fe778bae73c2ac5564f90c21328932060f576


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Monitorování zásad správy mobilních aplikací s Microsoft Intune
Po nastavení zásad správy mobilních aplikací (MAM) a jejich použití u uživatelů můžete na [portálu Azure Portal](https://portal.azure.com) monitorovat stav dodržování předpisů. Portál Azure Portal obsahuje informace o uživatelích dotčených zásadou, dále o stavu dodržování předpisů a všech problémech, se kterými se uživatelé mohou setkat.
## <a name="summary-view"></a>Souhrnné zobrazení
V okně **Správa mobilních aplikací Intune** si můžete prohlédnout souhrnné informace o stavu dodržování předpisů:


![Dlaždice souhrnu okna Správa mobilních aplikací Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Uživatelé**: Celkový počet uživatelů ve společnosti, kteří používají aplikace spojené se zásadou.

-   **SPRAVOVÁNO ZÁSADOU:** Počet uživatelů, kteří použili aspoň jednu aplikaci v pracovním kontextu.

-   **ŽÁDNÉ ZÁSADY:** Počet uživatelů, kteří sice používají aplikace spojené se zásadou, ale zásada se na ně nevztahuje. Tyto uživatele případně můžete k zásadě přidat.

- **Uživatelé označení příznakem:** Počet uživatelů, kteří mají problémy. V současnosti jsou v části **Uživatelé označení příznakem** jenom uživatelé zařízení, u kterých byla zrušena softwarová omezení (zařízení s jailbreakem).


## <a name="detailed-view"></a>Podrobné zobrazení
Pokud se chcete podívat na podrobnosti přehledu, zvolte dlaždici **Stav uživatele** a pak dlaždici **Uživatelé označení příznakem**.

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V okně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- Zařízení přidružená k účtu uživatele

- Aplikace se zásadou MAM u zařízení

- Stav:

  - **Zaregistrováno:** Zásada byla u uživatele nasazena a aplikace byla alespoň jednou použita v pracovním kontextu.

  - **Není zaregistrováno:** Zásada byla u uživatele nasazena, ale aplikace od té doby nebyla použita v pracovním kontextu.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva oznamující, že uživatel není cílem žádné zásady pro aplikace.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

1.  Pokud chcete vybrat uživatele, zvolte dlaždici **Souhrn** nebo v okně **Nastavení** zvolte **VYTVÁŘENÍ SESTAV APLIKACE UŽIVATELEM**:

    ![Možnost vytváření sestav v okně Nastavení](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Otevře se okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Možnost výběru uživatele v okně Vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-select-user.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

    ![Podrobnosti vytváření sestav aplikace](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, platforma zařízení a časové razítko.  

### <a name="see-also"></a>Související témata
[Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Co očekávat, když ke správě své aplikace pro Android používáte zásady MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Co očekávat, když ke správě své aplikace pro iOS používáte zásady MAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


