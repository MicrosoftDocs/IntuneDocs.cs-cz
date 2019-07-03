---
title: Migrace podmíněného přístupu na webu Azure portal
titleSuffix: Microsoft Intune
description: Změna přiřazení zásad podmíněného přístupu, kterou jste předtím vytvořili v klasickém portálu Intune na portálu Azure portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dbebcb495298f3e8b17007d1fb00f0362ead4ab8
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67530680"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Změna přiřazení zásad podmíněného přístupu z klasického portálu Intune do portálu Azure

Spouští se v novém portálu Azure portal, podmíněný přístup nabízí podporu pro různé zásady na aplikaci, také větší přizpůsobitelnost. Pokud jste dříve vytvořili zásady podmíněného přístupu v klasickém portálu Intune, můžete je migrovat na Azure portal. 

## <a name="before-you-begin"></a>Před zahájením

Pokud jste připravení přejít na webu Azure portal, postupujte podle kroků v tomto tématu můžete změnit přiřazení zásad podmíněného přístupu, kterou jste předtím vytvořili v klasickém portálu Intune:

- Shromážděte zásady podmíněného přístupu vytvořené dříve, abyste věděli, jaká nastavení budete později potřebovat znovu přiřadit.

- Podle pokynů v tomto tématu můžete tyto zásady znovu vytvořit na portálu Azure Portal.

- Až si ověříte, že nové zásady na Azure Portalu fungují podle očekávání, zakažte podmíněné zásady na klasickém portálu Intune.
<br /><br />
    - **Před zakázáním** zásady podmíněného přístupu na klasickém portálu Intune, naplánujte, jak přesunete uživatele nové zásady. Existují dvě metody:
<br /><br />
        - **Použít stejnou skupinu pro zahrnutí, na kterou použijete zásady vytvořené na portálu Azure Portal, a vytvořit novou skupinu pro vyloučení, na kterou použijete zásady z klasického portálu Intune**.
            - Postupně některé uživatele přesunete do skupiny pro vyloučení v klasickém portálu. Tím zabráníte, aby se použily zásady, na které cílí klasický portál Intune. Zásady vytvořené pro stejnou skupinu uživatelů na portálu Azure, na kterou jsou i zacílené, se použijí společně s těmi v klasickém portálu Intune. 
<br /><br />
        - **Vytvořit novou skupinu na kterou cílí zásady podmíněného přístupu na webu Azure Portal**. Pokud zvolíte tuto metodu, budete muset provést následující:
            - Postupně odeberte uživatele ze skupin zabezpečení, které mají zásady podmíněného přístupu cílí na klasickém portálu Intune.
            - Až ověříte, že nové zásady u těchto uživatelů fungují, můžete zásady v klasickém portálu Intune vypnout. 
<br /><br />
- Pokud máte nastavení zásad podmíněného přístupu nakonfigurované pomocí protokolu Exchange ActiveSync (EAS) v klasickém portálu Intune, přečtěte si téma [pokyny v tomto tématu](#reassign-intune-device-based-conditional-access-policies-for-eas-clients) k **změnit přiřazení nastavení zásad podmíněného přístupu EAS na webu Azure portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Chcete-li ověřit na základě zařízení zásady podmíněného přístupu v klasickém portálu Intune

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **podmíněného přístupu**, a pak vyberte cloudovou službu Microsoftu (třeba Exchange Online nebo SharePoint Online) jste zásady podmíněného přístupu vytvořili.

4.  Poznamenejte si nastavení podmíněného přístupu a použijte tyto při vytváření stejných zásad podmíněného přístupu na webu Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Na základě zařízení zásady podmíněného přístupu spolupracují a aplikace

Okno **Intune App Protection** na portálu Azure Portal umožňuje správcům nastavit podmíněná pravidla podle aplikací tak, aby přístup k firemním prostředkům mohly získat jenom aplikace podporující zásady ochrany aplikací Intune. Můžete se tyto zásady podmíněného přístupu na základě aplikace s použitím zásad podmíněného přístupu na základě zařízení. Podmíněné zásady podle zařízení a aplikací můžete zkombinovat (logický operátor A) nebo poskytnout jednu z možností (logický operátor NEBO). Pokud vaše požadavky zásad podmíněného přístupu mají:

- Vyžadovat vyhovující zařízení **A** použít schválenou aplikaci
    - Byste své zásady podmíněného přístupu nastavit pomocí [okno Azure Active Directory podmíněného přístupu](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Vyžadovat vyhovující zařízení **NEBO** použít schválenou aplikaci
    - Byste své zásady podmíněného přístupu nastavit pomocí [klasického portálu Intune](https://manage.microsoft.com) a [okna Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Toto téma obsahuje snímky obrazovky srovnávající činnosti koncového uživatele na klasickém portálu Intune i na portálu Azure Portal.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Změna přiřazení zásad podmíněného přístupu podle zařízení

1. Přejděte na [podmíněného přístupu na webu Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **přiřazení**, zvolte **uživatelů a skupin** na nové zásady podmíněného přístupu zacílili.

    ![Obrázek této skupiny uživatelů porovná uživatelského rozhraní mezi Intune a Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Výběr, který provedete pro portál Azure Portal, musí odpovídat výběru, který jste provedli pro portál Classic. Pokud máte třeba na klasickém portálu Intune vybrané všechny uživatele, vyberte **Všichni uživatelé** na portálu Azure Portal. Pokud jste navíc na klasickém portálu Intune zvolili možnost **Vyloučené skupiny**, tyto vybrané skupiny vylučte i na portálu Azure Portal.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a pak na **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** zvolte **Vybrat aplikace**.

8. Zvolte aplikaci, kterou chcete použít nové zásady podmíněného přístupu a klikněte na tlačítko **vyberte**.

9. Klikněte na **Done** (Hotovo).

    ![Obrázek porovnání uživatelského rozhraní cloudové aplikace mezi Intune a Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Pokud máte více aplikací se stejnými zásadami, můžete zvážit jejich sloučení na portálu Azure Portal do jedné zásady.

10. V části **Přiřazení** zvolte **Podmínky**.

11. V okně **Podmínky** zvolte **Platformy zařízení** a pak vyberte příslušné platformy zařízení.

12. Až budete s výběrem platforem zařízení hotoví, dvakrát klikněte na **Hotovo**.

    ![Obrázek, který porovnává platformu zařízení uživatelského rozhraní z na portálech Intune a Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > Pokud jste vybrali jednotlivé platformy na klasickém portálu Intune, vyberte jednotlivé platformy i na portálu Azure Portal.

    > [!NOTE] 
    > Připojení k doméně a možnosti vyhovění předpisům pro Windows můžete specifikovat později.

13. V části **Přiřazení** zvolte **Podmínky**.

14. V okně **Podmínky** zvolte **Klientské aplikace** a pak vyberte příslušné klientské aplikace.

15. Až budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

    ![Obrázek, který porovnává klientské aplikace uživatelského rozhraní mezi Intune a Azure Portal](./media/reassign-ca-6.png)

16. Pokud jste na klasickém portálu Intune zvolili nastavení prohlížeče, vyberte na portálu Azure Portal **Prohlížeč** i **Mobilní aplikace a desktopoví klienti**. V případě, že jste na klasickém portálu Intune nastavení prohlížeče nezvolili, vyberte jenom **Mobilní aplikace a desktopoví klienti**. 

17. V části **Ovládací prvky přístupu** zvolte **Udělení**.

18. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a pak klikněte na **Vybrat**.

19. Pokud máte zásadu, která vyžaduje zařízení s Windows připojená k doméně, a zároveň chcete povolit zařízení s Windows zaregistrovaná v Intune a vyhovující, zvolte **Vyžadovat zařízení připojené k doméně**, **Vyžadovat, aby zařízení bylo označené jako vyhovující** a **Vyžadovat jeden z vybraných ovládacích prvků**.

20. Pokud zařízení s Windows zaregistrovaná v Intune a vyhovující nepovolujete, vylučte zásadu pro Windows z aktuální zásady. Pak vytvořte samostatnou zásadu s **Platformou zařízení** nastavenou na **Windows**, zahrňte další výše uvedené podmínky a v části pro **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat zařízení připojené k doméně**.

21. Na **nový** okně zásad podmíněného přístupu, zapněte **povolit zásady** přepnout a potom klikněte na tlačítko **vytvořit**.

    ![Porovnání zásad podmíněného přístupu povolit uživatelské rozhraní mezi Intune a Azure](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Změna přiřazení zásad podmíněného přístupu na základě zařízení pro klienty EAS

Pokud nakonfigurujete nastavení Exchange ActiveSync jako součást zásady Exchange Online v klasickém portálu Intune, musíte vytvořit druhou zásadu podmíněného přístupu na webu Azure Portal.

1. Přejděte na [podmíněného přístupu na webu Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)a přihlaste se pomocí svých přihlašovacích údajů.

2. Zvolte **Nové zásady**.

3. Zadejte název pro tuto zásadu.

4. V části **přiřazení** zvolte **uživatelů a skupin** na nové zásady podmíněného přístupu zacílili.

    ![Obrázek ukazující srovnání uživatelského rozhraní skupina uživatelů mezi na portálech Azure a Intune](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Výběr, který provedete pro Azure Portal, musí odpovídat výběru, který jste provedli pro Azure Portal. Pokud máte třeba na klasickém portálu Intune vybrané všechny uživatele, vyberte **Všichni uživatelé** na portálu Azure Portal. Pokud jste navíc na klasickém portálu Intune zvolili možnost **Vyloučené skupiny**, tyto vybrané skupiny vylučte i na portálu Azure Portal.

5. Jakmile svou skupinu zvolíte, klikněte na **Vybrat** a pak na **Hotovo**.

6. V části **Přiřazení** zvolte **Cloudové aplikace**.

7. V okně **Cloudové aplikace** klikněte na **Vybrat aplikace** a zvolte **Exchange Online**. Pak klikněte na **Vybrat** a **Hotovo**.

    ![Obrázek srovnání uživatelského rozhraní cloudové aplikace mezi Intune a Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Zásady podmíněného přístupu pro klienty EAS nemohou zahrnovat žádnou další cloudovou aplikaci.

8. V okně **Podmínky** zvolte **Klientské aplikace** a pak vyberte příslušné klientské aplikace. Pokud jste se rozhodli blokovat klienty, kteří nejsou podporovaní službou Intune, použijte možnost **Použít zásady jenom na podporovaných platformách**.

    ![Obrázek ukazující srovnání uživatelského rozhraní aplikace mezi Azure a Intune portály klienta](./media/reassign-ca-15.png)

9. Až budete s výběrem klientských aplikací hotoví, dvakrát klikněte na **Hotovo**.

10. V části **Ovládací prvky přístupu** zvolte **Udělení**.

11. V části **Udělení ovládacích prvků přístupu** zvolte **Vyžadovat, aby zařízení bylo označené jako vyhovující** a pak klikněte na **Vybrat**.

    ![Obrázek, který porovnává udělení přístupu uživatelského rozhraní mezi Intune a Azure Portal](./media/reassign-ca-16.png)

12. Na **nový** okně zásad podmíněného přístupu, zapněte **povolit zásady** přepnout a potom klikněte na tlačítko **vytvořit**.

    ![Porovnání zásad podmíněného přístupu povolit uživatelské rozhraní mezi Intune a Azure](./media/reassign-ca-17.png)

> [!NOTE]
> Pokud nakonfigurujete možnost **Platformy zařízení**, uložení zásad se nezdaří a zobrazí se chyba „Konfigurace zásad není podporovaná“. Exchange ActiveSync nemůže identifikovat platformu, kterou používá připojující se zařízení. Při vytváření zásad pro zařízení Exchange ActiveSync se proto konfigurace specifických platforem zařízení nepodporuje.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Vypnutí zásad podmíněného přístupu v klasickém portálu Intune

Po změně přiřazení zásad podmíněného přístupu na webu Azure Portal, je důležité postupně vypínat zásady podmíněného přístupu vytvořené dříve na klasickém portálu Intune. Kromě toho budete muset použít stejnou skupinu zabezpečení k uplatnění zásad podmíněného přístupu vytvořených na webu Azure Portal.

> [!NOTE]
> Před vypnutím zásad podmíněného přístupu v klasickém portálu Intune, najdete v článku [před zahájením](#before-you-begin) části na začátku tohoto tématu.

### <a name="to-disable-the-conditional-access-policies"></a>Chcete-li zakázat zásady podmíněného přístupu

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Zásady**.

3.  Zvolte **podmíněného přístupu**a pak vyberte cloudovou službu Microsoftu (třeba Exchange Online nebo SharePoint Online), který jste vytvořili zásadu podmíněného přístupu.

4.  Zrušte zaškrtnutí možnosti **zásady podmíněného přístupu povolit**a potom klikněte na tlačítko **Uložit**.

    ![Obrázek zásady podmíněného přístupu zakázat v klasickém portálu Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Viz také:

- [Běžné způsoby použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
- [Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
- [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
