---
title: Migrace podmíněného přístupu na portál Azure Portal
titlesuffix: Microsoft Intune
description: Změňte přiřazení zásad podmíněného přístupu, které jste dříve vytvořili v klasickém portálu Intune, na portál Azure Portal.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d295ade29522a5593993b5541311eadd9e4c9528
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31027464"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Změna přiřazení zásad podmíněného přístupu z klasického portálu Intune do portálu Azure Portal

Počínaje novým portálem Azure Portal nabízí podmíněný přístup u každé aplikace podporu více zásad a také větší přizpůsobitelnost. Pokud jste dříve vytvořili zásady podmíněného přístupu na klasickém portálu Intune, můžete je migrovat na portál Azure Portal. 

## <a name="before-you-begin"></a>Před zahájením

Pokud jste připraveni přejít na portál Azure Portal, podle pokynů v tomto tématu můžete změnit přiřazení zásad podmíněného přístupu, které jste dříve vytvořili v klasickém portálu Intune:

- Shromážděte zásady podmíněného přístupu, které jste dříve vytvořili, abyste věděli, jaká nastavení budete později potřebovat znovu přiřadit.

- Podle pokynů v tomto tématu můžete tyto zásady znovu vytvořit na portálu Azure Portal.

- Až si ověříte, že nové zásady na Azure Portalu fungují podle očekávání, zakažte podmíněné zásady na klasickém portálu Intune.
<br /><br />
    - **Než vypnete** zásady podmíněného přístupu v klasickém portálu Intune, naplánujte si, jak přesunete uživatele na nové zásady. Existují dvě metody:
<br /><br />
        - **Použít stejnou skupinu pro zahrnutí, na kterou použijete zásady vytvořené na portálu Azure Portal, a vytvořit novou skupinu pro vyloučení, na kterou použijete zásady z klasického portálu Intune**.
            - Postupně některé uživatele přesunete do skupiny pro vyloučení v klasickém portálu. Tím zabráníte, aby se použily zásady, na které cílí klasický portál Intune. Zásady vytvořené pro stejnou skupinu uživatelů na portálu Azure, na kterou jsou i zacílené, se použijí společně s těmi v klasickém portálu Intune. 
<br /><br />
        - **Vytvořit novou skupinu, na kterou se budou cílit zásady podmíněného přístupu na portálu Azure Portal**. Pokud zvolíte tuto metodu, budete muset provést následující:
            - Postupně odeberte ze skupin zabezpečení uživatele, na které se cílí zásady podmíněného přístupu v klasickém portálu Intune.
            - Až ověříte, že nové zásady u těchto uživatelů fungují, můžete zásady v klasickém portálu Intune vypnout. 
<br /><br />
- Pokud máte nastavení zásad podmíněného přístupu nakonfigurované tak, aby se v klasickém portálu Intune používal protokol Exchange Active Sync (EAS), podívejte se na [pokyny v tomto tématu](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) ke **změně přiřazení nastavení zásad podmíněného přístupu EAS do portálu Azure Portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Postup ověření zásad podmíněného přístupu podle zařízení v klasickém portálu Intune

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **Podmíněný přístup** a pak vyberte cloudovou službu Microsoftu (třeba Exchange Online nebo SharePoint Online), pro kterou jste zásady podmíněného přístupu vytvořili.

4.  Poznamenejte si nastavení podmíněného přístupu a poznámky využijte při vytváření stejných zásad podmíněného přístupu na portálu Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Spolupracující zásady podmíněného přístupu podle zařízení a aplikace

Okno **Intune App Protection** na portálu Azure Portal umožňuje správcům nastavit podmíněná pravidla podle aplikací tak, aby přístup k firemním prostředkům mohly získat jenom aplikace podporující zásady ochrany aplikací Intune. Tyto zásady podmíněného přístupu podle aplikací můžete překrývat použitím zásad podmíněného přístupu podle zařízení. Podmíněné zásady podle zařízení a aplikací můžete zkombinovat (logický operátor A) nebo poskytnout jednu z možností (logický operátor NEBO). Pokud vaše požadavky zásad podmíněného přístupu mají:

- Vyžadovat vyhovující zařízení **A** použít schválenou aplikaci
    - Měli byste své zásady podmíněného přístupu nastavit pomocí [okna podmíněného přístupu Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Vyžadovat vyhovující zařízení **NEBO** použít schválenou aplikaci
    - Měli byste své zásady podmíněného přístupu nastavit pomocí [klasického portálu Intune](https://manage.microsoft.com) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Toto téma obsahuje snímky obrazovky srovnávající činnosti koncového uživatele na klasickém portálu Intune i na portálu Azure Portal.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Změna přiřazení zásad podmíněného přístupu podle zařízení

1. Přejděte na [Podmíněný přístup na portálu Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **Přiřazení** zvolte **Uživatelé a skupiny**, abyste nové zásady podmíněného přístupu zacílili.
    
    ![Obrázek ukazující srovnání uživatelského rozhraní uživatelských skupin na portálech Intune a Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Výběr, který provedete pro portál Azure Portal, musí odpovídat výběru, který jste provedli pro portál Classic. Pokud máte třeba na klasickém portálu Intune vybrané všechny uživatele, vyberte **Všichni uživatelé** na portálu Azure Portal. Pokud jste navíc na klasickém portálu Intune zvolili možnost **Vyloučené skupiny**, tyto vybrané skupiny vylučte i na portálu Azure Portal.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a pak na **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** zvolte **Vybrat aplikace**.

8. Zvolte aplikaci, na kterou chcete nové zásady podmíněného přístupu uplatnit, a klikněte na **Vybrat**.

9. Klikněte na **Hotovo**.

    ![Obrázek ukazující srovnání uživatelského rozhraní cloudové aplikace na portálech Intune a Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Pokud máte více aplikací se stejnými zásadami, můžete zvážit jejich sloučení na portálu Azure Portal do jedné zásady.

10. V části **Přiřazení** zvolte **Podmínky**.

11. V okně **Podmínky** zvolte **Platformy zařízení** a pak vyberte příslušné platformy zařízení.

12. Až budete s výběrem platforem zařízení hotoví, dvakrát klikněte na **Hotovo**.

    ![Obrázek ukazující srovnání uživatelského rozhraní platformy zařízení na portálech Intune a Azure Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Pokud jste vybrali jednotlivé platformy na klasickém portálu Intune, vyberte jednotlivé platformy i na portálu Azure Portal.

    > [!NOTE] 
    > Připojení k doméně a možnosti vyhovění předpisům pro Windows můžete specifikovat později.

13. V části **Přiřazení** zvolte **Podmínky**.

14. V okně **Podmínky** zvolte **Klientské aplikace** a pak vyberte příslušné klientské aplikace.

15. Až budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

    ![Obrázek ukazující srovnání uživatelského rozhraní klientských aplikací na portálech Intune a Azure Portal](./media/reassign-ca-6.png)

16. Pokud jste na klasickém portálu Intune zvolili nastavení prohlížeče, vyberte na portálu Azure Portal **Prohlížeč** i **Mobilní aplikace a desktopoví klienti**. V případě, že jste na klasickém portálu Intune nastavení prohlížeče nezvolili, vyberte jenom **Mobilní aplikace a desktopoví klienti**. 

17. V části **Ovládací prvky přístupu** zvolte **Udělení**.

18. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a pak klikněte na **Vybrat**.

19. Pokud máte zásadu, která vyžaduje zařízení s Windows připojená k doméně, a zároveň chcete povolit zařízení s Windows zaregistrovaná v Intune a vyhovující, zvolte **Vyžadovat zařízení připojené k doméně**, **Vyžadovat, aby zařízení bylo označené jako vyhovující** a **Vyžadovat jeden z vybraných ovládacích prvků**.

20. Pokud zařízení s Windows zaregistrovaná v Intune a vyhovující nepovolujete, vylučte zásadu pro Windows z aktuální zásady. Pak vytvořte samostatnou zásadu s **Platformou zařízení** nastavenou na **Windows**, zahrňte další výše uvedené podmínky a v části pro **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat zařízení připojené k doméně**.

21. V okně zásad podmíněného přístupu **Nový** zapněte přepínací tlačítko **Povolit zásadu** a pak klikněte na **Vytvořit**.

    ![Obrázek ukazující srovnání uživatelského rozhraní pro povolení zásad podmíněného přístupu na portálech Intune a Azure Portal](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Změna přiřazení zásad podmíněného přístupu podle zařízení pro klienty EAS

Pokud jste nastavení protokolu Exchange Active Sync nakonfigurovali na klasickém portálu Intune jako součást zásady Exchange Online, musíte na portálu Azure Portal vytvořit druhou zásadu podmíněného přístupu.

1. Přejděte na [Podmíněný přístup na portálu Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **Přiřazení** zvolte **Uživatelé a skupiny**, abyste nové zásady podmíněného přístupu zacílili.

    ![Obrázek ukazující srovnání uživatelského rozhraní uživatelských skupin na portálech Intune a Azure Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Výběr, který provedete pro Azure Portal, musí odpovídat výběru, který jste provedli pro Azure Portal. Pokud máte třeba na klasickém portálu Intune vybrané všechny uživatele, vyberte **Všichni uživatelé** na portálu Azure Portal. Pokud jste navíc na klasickém portálu Intune zvolili možnost **Vyloučené skupiny**, tyto vybrané skupiny vylučte i na portálu Azure Portal.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a pak na **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** klikněte na **Vybrat aplikace** a zvolte **Exchange Online**. Pak klikněte na **Vybrat** a **Hotovo**.

    ![Obrázek ukazující srovnání uživatelského rozhraní cloudových aplikací na portálech Intune a Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Zásady podmíněného přístupu pro klienty EAS nemůžou zahrnovat žádnou další cloudovou aplikaci.

8. V okně **Podmínky** zvolte **Klientské aplikace** a pak vyberte příslušné klientské aplikace. Pokud jste se rozhodli blokovat klienty, kteří nejsou podporovaní službou Intune, použijte možnost **Použít zásady jenom na podporovaných platformách**.

    ![Obrázek ukazující srovnání uživatelského rozhraní klientských aplikací na portálech Intune a Azure Portal](./media/reassign-ca-15.png)

9. Až budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

10. V části **Ovládací prvky přístupu** zvolte **Udělení**.

11. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a pak klikněte na **Vybrat**.

    ![Obrázek ukazující srovnání uživatelského rozhraní udělení přístupu na portálech Intune a Azure Portal](./media/reassign-ca-16.png)

12. V okně zásad podmíněného přístupu **Nový** zapněte přepínací tlačítko **Povolit zásadu** a pak klikněte na **Vytvořit**.

    ![Obrázek ukazující srovnání uživatelského rozhraní pro povolení zásad podmíněného přístupu na portálech Intune a Azure Portal](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Vypnutí zásad podmíněného přístupu na klasickém portálu Intune

Po změně přiřazení zásad podmíněného přístupu na portálu Azure Portal je důležité postupně vypínat zásady podmíněného přístupu vytvořené dříve na klasickém portálu Intune. Kromě toho může být potřeba použít stejnou skupinu zabezpečení k uplatnění zásad podmíněného přístupu vytvořených na portálu Azure Portal.

> [!NOTE]
> Před vypnutím zásad podmíněného přístupu na klasickém portálu Intune si přečtěte část [Před zahájením](#before-you-begin) na začátku tohoto tématu.

### <a name="to-disable-the-conditional-access-policies"></a>Postup vypnutí zásad podmíněného přístupu

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **Podmíněný přístup** a pak vyberte cloudovou službu Microsoftu (třeba Exchange Online nebo SharePoint Online), pro kterou jste zásady podmíněného přístupu vytvořili.

4.  Zrušte zaškrtnutí možnosti **Zapnout zásady podmíněného přístupu** a pak klikněte na **Uložit**.

    ![Obrázek ukazující vypnutí zásad podmíněného přístupu na klasickém portálu Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Viz taky

- [Běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
- [Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
- [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
