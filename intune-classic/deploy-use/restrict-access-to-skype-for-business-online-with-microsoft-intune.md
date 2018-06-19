---
title: Ochrana Online Skypu pro firmy
description: Chraňte a řiďte přístup k Online Skypu pro firmy pomocí podmíněného přístupu.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d9d912cc0a2d8f815e046d888fc8878a8703c514
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022709"
---
# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a>Ochrana přístupu k Online Skypu pro firmy pomocí Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

K řízení přístupu k Online Skypu pro firmy můžete použít zásady podmíněného přístupu k **Online Skypu pro firmy**.
Podmíněný přístup má dvě součásti:
- Zásady dodržování předpisů zařízení, které zařízení musí dodržovat, aby mohlo být považované za vyhovující
- Zásady podmíněného přístupu, kde můžete určit podmínky, které zařízení musí splňovat, abyste měli přístup ke službě.
Další informace o tom, jak podmíněný přístup funguje, najdete v článku [Ochrana přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Když se cílový uživatel na svém zařízení pokusí použít službu Online Skype pro firmy Skype for Business Online, dojde k následujícímu vyhodnocení:

![Diagram znázorňující rozhodovací body, které určují, jestli má mít zařízení povolený nebo blokovaný přístup k Online Skypu pro firmy](../media/ConditionalAccess_SkypeforBusiness.png)

**Dřív** než nakonfigurujete zásady podmíněného přístupu pro Online Skype pro firmy, musíte:
- Mít **předplatné Online Skypu pro firmy**  a přiřadit uživatelům příslušnou licenci
- Mít **předplatné Enterprise Mobility + Security (EMS)** nebo **předplatné Azure Active Directory (Azure AD) Premium** a uživatelé musí mít licenci pro EMS nebo Azure AD. Další informace najdete na stránce s [cenami Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) nebo [cenami Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

-   [Povolit moderní ověřování](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) pro Online Skype pro firmy.
-  Všichni uživatelé musí používat **Online Skype pro firmy**. Pokud máte nasazení s Online Skypem pro firmy i místním Skypem pro firmy, zásady podmíněného přístupu se na uživatele nepoužijí.

Zařízení, které potřebuje přístup k Online Skype pro firmy, musí splňovat následující kritéria:

-   Musí mít systém **Android** nebo **iOS**.

-   Je **zaregistrované** v Intune.

-   **Vyhovuje** veškerým nasazeným zásadám dodržování předpisů Intune.


Stav zařízení je uložený ve službě Azure Active Directory, která uděluje nebo blokuje přístup na základě podmínek, které zadáte.

Pokud není některá podmínka splněná, zobrazí se uživateli při přihlášení jedna z následujících zpráv:

-   Pokud není zařízení zaregistrované v Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny pro instalaci aplikace Portál společnosti a pro registraci.

-   Pokud zařízení nedodržuje předpisy, zobrazí se zpráva, která uživatele přesměruje na web Portál společnosti Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a jeho řešení.

## <a name="configure-conditional-access-for-skype-for-business-online"></a>Konfigurace podmíněného přístupu pro Online Skype pro firmy

### <a name="step-1-configure-azure-active-directory-security-groups"></a>Krok 1: Konfigurace skupin zabezpečení Azurey Active Directory
Než začnete, nakonfigurujte pro skupiny zabezpečení služby Azure Active Directory zásadu podmíněného přístupu. Tyto skupiny můžete nakonfigurovat v **Centru pro správu Office 365**. Tyto skupiny se použijí k cílení zásad na uživatele nebo vyloučení uživatelů ze zásady. Pokud je uživatel cílem zásady, musí každé jím používané zařízení splňovat zásady, aby měl přístup k prostředkům.

Můžete určit dva typy skupin, které se použijí pro zásady Skype pro firmy:

-   **Cílové skupiny**: Obsahují skupiny uživatelů, pro které zásady platí.

-   **Vyloučené skupiny**: Obsahují skupiny uživatelů, kteří jsou ze zásady vyloučení.

Pokud je uživatel v obou skupinách, bude ze zásad vyloučený.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Krok 2: Konfigurace a nasazení zásad dodržování předpisů
[Vytvořte](create-a-device-compliance-policy-in-microsoft-intune.md) a [nasaďte](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) zásady dodržování přepisů na všechna zařízení, která budou zásadami ovlivněná. Budou to všechna zařízení, která uživatelé používají v **cílových skupinách**.

> [!NOTE]
> Zásady dodržování předpisů se nasazují do skupin Intune, zásady podmíněného přístupu cílí na skupiny zabezpečení služby Azure Active Directory.


> [!IMPORTANT]
> Pokud jste zásady dodržování předpisů nenasadili, budou se zařízení považovat za vyhovující.

Až budete připravení, pokračujte **Krokem 3**.

### <a name="step-3-configure-the-skype-for-business-online-policy"></a>Krok 3: Konfigurace zásad pro Online Skype pro firmy
V dalším kroku nakonfigurujte zásadu, která bude vyžadovat, aby měla k Online Skype pro firmy přístup jenom spravovaná zařízení, která jsou v souladu s předpisy. Tato zásada bude uložená v Azure Active Directory.

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** > **Podmíněný přístup** > **Zásady pro Online Skype pro firmy**.

   ![Snímek obrazovky stránky zásad podmíněného přístupu Online Skypu pro firmy](./media/conditional_access_SFBPolicy.png)

2. Vyberte **Zapnout zásady podmíněného přístupu**.

3. V části **Přístup k aplikaci** můžete použít zásady podmíněného přístupu na:

   -   **iOS**

   -   **Androidemem**

4. V části **Cílové skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se zásady vztahují. Můžete cílit na všechny uživatele nebo vybranou skupinu uživatelů.

5. V případě potřeby v části **Vyloučené skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se tyto zásady nevztahují.

6. Po dokončení vyberte **Uložit**.

Nyní máte nakonfigurovaný podmíněný přístup pro Online Skype pro firmy Zásady podmíněného přístupu nemusíte nasazovat, projeví se okamžitě.


## <a name="monitor-the-compliance-and-conditional-access-policies"></a>Sledování dodržování předpisů a zásad podmíněného přístupu
V pracovním prostoru **Skupiny** se můžete podívat na stav podmíněného přístupu svých zařízení.

Vyberte libovolnou skupinu mobilních zařízení. Pak na kartě **Zařízení** zvolte jeden z následujících **Filtrů**:

* **Zařízení nezaregistrovaná v AAD:** Tato zařízení jsou z Online Skypu pro firmy blokovaná.

* **Zařízení nevyhovující předpisům:** Tato zařízení jsou z Online Skypu pro firmy blokovaná.

* **Zařízení zaregistrovaná v AAD a vyhovující předpisům:** Tato zařízení mají k Online Skypu pro firmy přístup.
