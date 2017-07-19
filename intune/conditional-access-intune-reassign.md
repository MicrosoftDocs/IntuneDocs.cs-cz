---
title: "Přeneste zásady podmíněného přístupu z klasického portálu Intune do nového portálu Azure Portal."
titleSuffix: Intune on Azure
description: "Přeneste zásady podmíněného přístupu z klasického portálu Intune do nového portálu Azure Portal."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Změna přiřazení zásad podmíněného přístupu z klasického portálu Intune do nového portálu Azure Portal

Na novém portálu Azure Portal nabízí podmíněný přístup u každé aplikace podporu více zásad a dále nabízí i větší přizpůsobitelnost.

## <a name="before-you-begin"></a>Před zahájením

Pokud jste připraveni přejít na nový portál Azure Portal, můžete postupovat podle pokynů níže, abyste změnili přiřazení zásad podmíněného přístupu, které byly dříve vytvořeny v klasickém portálu Intune:

- Shromážděte zásady podmíněného přístupu, které jste dříve vytvořili v klasickém portálu Intune, abyste věděli, jaká nastavení budete později potřebovat přiřadit.

- Postupujte podle pokynů v tomto tématu, abyste tyto zásady znovu vytvořili v novém portálu Azure Portal.

- Jakmile si ověříte, že nové zásady v novém portálu Azure Portal fungují podle očekávání, vypněte podmíněné zásady v klasické konzole Intune.
<br /><br />
    - **Než vypnete** zásady podmíněného přístupu v klasickém portálu Intune, naplánujte si, jak přesunete uživatele na nové zásady. Existují dvě metody:
<br /><br />
        - **Použít stejnou skupinu pro zahrnutí, na kterou použijete zásady vytvořené v novém portálu Azure Portal, a vytvořit novou skupinu pro vyloučení, na kterou použijete zásady z klasického portálu Intune**.
            - Postupně některé uživatele přesunete do skupiny pro vyloučení v klasickém portálu.  Tímto zabráníte, aby se použily zásady, které se uplatňují klasickým portálem Intune. Zásady vytvořené pro stejnou skupinu uživatelů v novém portálu Azure, na kterou jsou i uplatňované, se použijí společně s těmi v klasickém portálu Intune. 
<br /><br />
        - **Vytvořit novou skupinu, na kterou se budou uplatňovat zásady podmíněného přístupu v novém portálu Azure Portal**. Pokud zvolíte tuto metodu, budete muset provést následující:
            - Postupně odeberte ze skupin zabezpečení uživatele, na které se uplatňují zásady podmíněného přístupu v klasickém portálu Intune.
            - Jakmile ověříte, že nové zásady u těchto uživatelů fungují, můžete zásady v klasickém portálu Intune vypnout. 
<br /><br />
- Pokud máte nastavení zásad podmíněného přístupu nakonfigurováno v klasickém portálu Intune k použití protokolu Exchange Active Sync (EAS), podívejte se na [pokyny v tomto tématu](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients), abyste **změnili přiřazení nastavení zásad podmíněného přístupu EAS do nového portálu Azure Portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Postup ověření zásad podmíněného přístupu podle zařízení v klasickém portálu Intune

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **Podmíněný přístup** a potom vyberte cloudovou službu Microsoftu (Exchange Online, SharePoint Online atd.), pro kterou jste zásady podmíněného přístupu vytvořili.

4.  Udělejte si o nastavení podmíněného přístupu poznámky a tyto poznámky použijte při vytváření stejných zásad podmíněného přístupu v novém portálu Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Spolupracující zásady podmíněného přístupu podle zařízení a aplikace

Okno **Intune App Protection** na novém portálu Azure Portal umožňuje správcům nastavit podmíněná pravidla podle aplikace tak, aby přístup k firemním prostředkům mohly získat pouze aplikace podporující zásady ochrany aplikací Intune. Tyto zásady podmíněného přístupu podle aplikací můžete překrývat pomocí zásad podmíněného přístupu podle zařízení. Záleží na tom, jestli chcete zkombinovat podmíněné zásady podle zařízení a aplikace (logický operátor A) nebo poskytnout možnost výběru (logický operátor NEBO). Pokud vašimi požadavky zásad podmíněného přístupu jsou:

- Vyžadovat vyhovující zařízení **A** použít schválenou aplikaci.
    - Měli byste své zásady podmíněného přístupu nastavit pomocí [okna Podmíněný přístup Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Vyžadovat vyhovující zařízení **NEBO** použít schválenou aplikaci.
    - Měli byste své zásady podmíněného přístupu nastavit pomocí [klasického portálu Intune](https://manage.microsoft.com) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Toto téma obsahuje snímky obrazovky srovnávající činnosti koncového uživatele jak na klasickém portálu Intune, tak i na novém portálu Azure Portal.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Postup změny přiřazení zásad podmíněného přístupu podle zařízení

1. Přejděte na [Podmíněný přístup v novém portálu Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **Přiřazení** zvolte **Uživatelé a skupiny**, abyste uplatnili nové zásady podmíněného přístupu.
    
    ![Srovnání uživatelského rozhraní Skupina uživatelů mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Pokud máte vybrané všechny uživatele v klasickém portálu Intune, zahrňte všechny uživatele. Totéž platí pro skupiny. Pokud máte vybrané skupiny, musíte zvolit **vybrat jednotlivé uživatele a skupiny**, abyste tyto skupiny zahrnuli. Pokud jste mimo to zvolili v klasickém portálu Intune možnost **Vyloučené skupiny**, je potřeba tyto vybrané skupiny v novém portálu Azure Portal vyloučit.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** zvolte **Vybrat aplikace**.

8. Zvolte aplikaci, na kterou chcete nové zásady podmíněného přístupu uplatnit, a klikněte na **Vybrat**.

9. Klikněte na **Hotovo**.

    ![Srovnání uživatelského rozhraní Cloudové aplikace mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Pokud máte více aplikací se stejnými zásadami, můžete zvážit jejich sloučení na novém portálu Azure Portal do jedné zásady.

10. V části **Přiřazení** zvolte **Podmínky**.

11. V okně **Podmínky** zvolte **Platformy zařízení** a potom vyberte příslušné platformy zařízení.

12. Jakmile budete s výběrem platforem zařízení hotovi, dvakrát klikněte na **Hotovo**.

    ![Srovnání uživatelského rozhraní Platformy zařízení mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Pokud jste vybrali jednotlivé platformy na klasickém portálu Intune, vyberte jednotlivé platformy i na novém portálu Azure Portal.

    > [!NOTE] 
    > Připojení k doméně a možnosti vyhovění předpisům pro Windows můžete specifikovat později.

13. V části **Přiřazení** zvolte **Podmínky**.

14. V okně **Podmínky** zvolte **Klientské aplikace** a potom vyberte příslušné klientské aplikace.

15. Jakmile budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

    ![Srovnání uživatelského rozhraní Klientské aplikace mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-6.png)

16. Pokud jste na klasickém portálu Intune zvolili nastavení prohlížeče, vyberte na novém portálu Azure Portal **Prohlížeč** i **Mobilní aplikace a desktopoví klienti**. V případě, že jste na klasickém portálu Intune nastavení prohlížeče nezvolili, vyberte pouze **Mobilní aplikace a desktopoví klienti**. 

17. V části **Ovládací prvky přístupu** zvolte **Udělení**.

18. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a potom klikněte na **Vybrat**.

19. Pokud máte zásadu, která vyžaduje zařízení s Windows připojená k doméně a zároveň chcete povolit zařízení zaregistrovaná v Intune a zařízení s Windows dodržující předpisy, zvolte **Vyžadovat zařízení připojené k doméně**, **Vyžadovat, aby zařízení bylo označené jako vyhovující** a **Vyžadovat jeden z vybraných ovládacích prvků**.

20. Pokud nepovolíte zařízení zaregistrovaná v Intune a zařízení s Windows dodržující předpisy, vylučte zásadu Windows ze současných zásad a vytvořte samostatné zásady s **platformou zařízení** nastavenou na **Windows**, zahrňte další výše uvedené podmínky a v části pro **udělení ovládacích prvků přístupu** zvolte **Vyžadovat zařízení připojené k doméně**.

21. V okně zásad podmíněného přístupu **Nový** zapněte přepínací tlačítko **Povolit zásadu** a potom klikněte na **Vytvořit**.

    ![Srovnání uživatelského rozhraní Povolit zásady podmíněného přístupu mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Postup změny přiřazení zásad podmíněného přístupu podle zařízení pro klienty EAS

Pokud jste nastavení protokolu Exchange Active Sync (EAS) nakonfigurovali na klasickém portálu Intune jako součást zásady Exchange Online, musíte na novém portálu Azure Portal vytvořit druhou zásadu podmíněného přístupu.

1. Přejděte na [Podmíněný přístup v novém portálu Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **Přiřazení** zvolte **Uživatelé a skupiny**, abyste uplatnili nové zásady podmíněného přístupu.

    ![Srovnání uživatelského rozhraní Skupina uživatelů mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Pokud máte vybrané všechny uživatele v klasickém portálu Intune, zahrňte všechny uživatele. Totéž platí pro skupiny. Pokud máte vybrané skupiny, musíte zvolit **vybrat jednotlivé uživatele a skupiny**, abyste tyto skupiny zahrnuli. Pokud jste mimo to zvolili v klasickém portálu Intune možnost **Vyloučené skupiny**, je potřeba tyto vybrané skupiny v novém portálu Azure Portal vyloučit.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** klikněte na **Vybrané aplikace**, zvolte **Exchange Online** a klikněte na **Vybrat** a potom na **Hotovo**.

    ![Srovnání uživatelského rozhraní Cloudové aplikace mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Zásady podmíněného přístupu pro klienty EAS nemohou zahrnovat žádnou další cloudovou aplikaci.

8. V okně **Podmínky** zvolte **Klientské aplikace** a potom vyberte příslušné klientské aplikace. Pokud jste se rozhodli blokovat klienty, kteří nejsou podporovaní službou Intune, použijte možnost **Použít zásady jenom na podporovaných platformách**.

    ![Srovnání uživatelského rozhraní Klientské aplikace mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-15.png)

9. Jakmile budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

10. V části **Ovládací prvky přístupu** zvolte **Udělení**.

11. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a potom klikněte na **Vybrat**.

    ![Srovnání uživatelského rozhraní Udělit přístup mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-16.png)

12. V okně zásad podmíněného přístupu **Nový** zapněte přepínací tlačítko **Povolit zásadu** a potom klikněte na **Vytvořit**.

    ![Srovnání uživatelského rozhraní Povolit zásady podmíněného přístupu mezi Intune Classic a novým portálem Azure Portal](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Vypnutí zásad podmíněného přístupu na klasickém portálu Intune
### <a name="before-you-start"></a>Než začnete

Jakmile změníte přiřazení svých zásad podmíněného přístupu na novém portálu Azure Portal, je důležité postupně vypínat zásady podmíněného přístupu vytvořené dříve na klasickém portálu Intune. Kromě toho může být potřeba použít stejnou skupinu zabezpečení k uplatnění zásad podmíněného přístupu vytvořených na novém portálu Azure Portal.

- Před vypnutím zásad podmíněného přístupu na klasickém portálu Intune se podívejte na část [Před zahájením](#before-you-begin) na začátku tohoto tématu.

### <a name="to-disable-the-conditional-access-policies"></a>Postup vypnutí zásad podmíněného přístupu

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **Podmíněný přístup** a potom vyberte cloudovou službu Microsoftu (Exchange Online, SharePoint Online atd.), pro kterou jste zásady podmíněného přístupu vytvořili.

4.  Zrušte zaškrtnutí možnosti **Zapnout zásady podmíněného přístupu** a potom klikněte na **Uložit**.

    ![Vypnutí zásad podmíněného přístupu na klasickém portálu Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Související témata

- [Běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
- [Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
- [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)