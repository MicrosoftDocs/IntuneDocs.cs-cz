---
title: "Omezení přístupu k e-mailu na Dynamics CRM Online | Microsoft Intune"
description: "Chraňte a kontrolujte přístup k Dynamics CRM Online pomocí podmíněného přístupu."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: db1d43dd647122e7ba8ebd4e6df48e3c970a3392
ms.openlocfilehash: 233b7cad41fbd35e0fef615737fc41f8a49db35e


---

# Omezení přístupu k e-mailu na Dynamics CRM Online s Intune
Můžete řídit přístup k Microsoft Dynamics CRM Online ze zařízení s iOS a Androidem s podmíněným přístupem Microsoft Intune.  Podmíněný přístup Intune má dvě součásti:
* [Zásady dodržování předpisů zařízení](introduction-to-device-compliance-policies-in-microsoft-intune.md), které zařízení musí dodržovat, aby mohlo být považované za vyhovující.
* [Zásady podmíněného přístupu](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), kde můžete určit podmínky, které zařízení musí splňovat, aby mělo přístup ke službě.

Další informace o tom, jak podmíněný přístup funguje, najdete v článku o [omezení přístupu k e-mailu, O365 a dalším službám](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

[!IMPORTANT] K nasazení podmíněného přístupu potřebujete předplatné Intune a Azure Active Directory Premium. Uživatelé musí mít licenci na oba tyto produkty. **Předplatné Enterprise Mobility + Security (EMS)** obsahuje jak předplatné Intune, tak i předplatné Azure Active Directory Premium. Bližší informace najdete na [stránce s cenami Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing). Pokud nemáte předplatné EMS, můžete získat předplatné pro Azure Active Directory Premium. Další informace najdete na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/). 

Když se cílový uživatel na svém zařízení pokusí použít aplikaci Dynamics CRM, dojde k následujícímu vyhodnocení:

![Diagram zobrazuje body rozhodování používané k určení, jestli má zařízení přístup ke službě povolený, nebo blokovaný](../media/mdm-ca-dynamics-crm-flow-diagram.png)

Zařízení, které potřebuje přístup k Dynamics CRM Online, musí splňovat následující kritéria:
* Musí mít systém **Android** nebo **iOS**.
* Musí být **zaregistrováno** v Microsoft Intune.
* Musí **vyhovovat** veškerým nasazeným zásadám dodržování předpisů Microsoft Intune.

Stav zařízení je uložený ve službě Azure Active Directory, která uděluje nebo blokuje přístup na základě podmínek, které zadáte.

Pokud není podmínka splněná, zobrazí se uživateli při přihlášení jedna z následujících zpráv:
* Pokud není zařízení zaregistrované v Microsoft Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny pro instalaci aplikace portálu společnosti a registraci.
* Pokud zařízení není vyhovující, zobrazí se zpráva, která uživatele přesměruje na web portálu společnosti Microsoft Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a postupu při jeho řešení.

## Konfigurace podmíněného přístupu pro Dynamics CRM Online  
### Krok 1: Konfigurace skupin zabezpečení služby Active Directory

Než začnete, nakonfigurujte pro skupiny zabezpečení služby Azure Active Directory zásadu podmíněného přístupu. Tyto skupiny můžete nakonfigurovat v **Centru pro správu Office 365**. Tyto skupiny se použijí k cílení nebo vyloučení uživatelů ze zásady. Pokud je uživatel cílem zásady, musí každé jím používané zařízení splňovat zásady, aby měl přístup k prostředkům.

Můžete určit dva typy skupin, které se použijí pro zásady Dynamics CRM:
* **Cílové skupiny** – Skupiny uživatelů, na které se má zásada aplikovat.
* **Vyloučené skupiny** – Skupiny uživatelů, kteří jsou ze zásady vyloučeni.

Pokud je uživatel v obou skupinách, bude ze zásad vyloučený.

### Krok 2: Konfigurace a nasazení zásad dodržování předpisů
[Vytvořte](create-a-device-compliance-policy-in-microsoft-intune.md) a [nasaďte](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) zásady dodržování přepisů na všechna zařízení, která budou zásadami ovlivněná. Toto jsou všechna zařízení, která uživatelé používají v cílových skupinách.

> [!NOTE]
> Zásady dodržování předpisů se nasadí do skupin Microsoft Intune a zásady podmíněného přístupu cílí na skupiny zabezpečení Azure Active Directory.

> [!IMPORTANT]
> Pokud jste zásady dodržování předpisů nenasadili, budou se zařízení považovat za vyhovující.

Až budete připravení, pokračujte Krokem 3.
### Krok 3: Konfigurace zásad Dynamics CRM
V dalším kroku nakonfigurujte zásadu, která bude vyžadovat, aby k Dynamics CRM měla přístup jenom spravovaná a vyhovující zařízení. Tato zásada bude uložená v Azure Active Directory.

1.  V konzole pro správu Microsoft Intune zvolte **Zásady > Podmíněný přístup > Zásady pro Dynamics CRM Online**.

  ![Snímek obrazovky stránky zásad podmíněného přístupu pro Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Vyberte zásady **Povolit podmíněný přístup**.
3.  V části **Přístup k aplikaci** můžete použít zásady podmíněného přístupu na:
  * **iOS**
  * **Android**
4.  V části **Cílové skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se zásady vztahují. Můžete cílit na všechny uživatele nebo vybranou skupinu uživatelů.
5.  V případě potřeby v části **Vyloučené skupiny** zvolte **Upravit** a vyberte skupiny zabezpečení Azure Active Directory, na které se tyto zásady nevztahují.
6.  Po dokončení vyberte **Uložit**.

Nyní máte nakonfigurovaný podmíněný přístup pro Dynamics CRM. Zásady podmíněného přístupu není potřeba nasazovat, projeví se okamžitě.
##  Sledování dodržování předpisů a zásad podmíněného přístupu

V pracovním prostoru **Skupiny** se můžete podívat na stav podmíněného přístupu svých zařízení.

Vyberte libovolnou skupinu mobilních zařízení a pak na kartě **Zařízení** vyberte jeden z následujících **filtrů**:
* **Zařízení nezaregistrovaná v AAD** – Tato zařízení jsou pro Dynamics CRM blokovaná.
* **Zařízení nevyhovující předpisům** – Tato zařízení jsou pro Dynamics CRM blokovaná.
* **Zařízení zaregistrovaná v AAD a vyhovující předpisům** – Tato zařízení mají přístup k Dynamics CRM.

##  Další kroky
[Podmíněný přístup k Exchangi Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

[Omezení přístupu k místnímu Exchangi](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
[Omezení přístupu k SharePointu Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Omezení přístupu ke službě Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Oct16_HO1-->


