---
title: "Co je podmíněný přístup? | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se ve službě Microsoft Intune Azure Preview definovat podmínky, které uživatelé a zařízení musí splnit, aby měli přístup k firemním prostředkům."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 41931f64db969c82f79e007c4be9e68b7caf4ce9
ms.openlocfilehash: 20696fb2dc0126aa224e779738cedb4f95f666e8


---

# <a name="what-is-conditional-access"></a>Co je podmíněný přístup?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Toto téma popisuje podmíněný přístup v řešení Enterprise Mobility + Security a následně možnosti podmíněného přístupu v Intune.

Podmíněný přístup z řešení Enterprise Mobility + Security (EMS) vám s využitím služeb Azure Active Directory Premium a Microsoft Intune umožňuje zabezpečit podniková data a zároveň uživatelům poskytnout prostředí, které jim umožní plnit pracovní úkoly na libovolném zařízení.

Pomocí podmíněného přístupu můžete definovat podmínky, které omezují přístup k podnikovým datům podle polohy, stavu zařízení a uživatele a „choulostivosti“ aplikace.

Z hlediska zařízení spolu služby Intune a Azure Active Directory spolupracují a zajišťují, aby přístup k e-mailu a službám Office 365 měla jen spravovaná zařízení dodržující předpisy. Ve službě Azure Active Directory můžete například nastavit zásadu, aby přístup ke službám Office 365 měly jen počítače, které jsou připojené k doméně, nebo mobilní zařízení, která jsou zaregistrovaná v nějaké aplikaci pro správu mobilních zařízení, jako je Intune. Ve službě Intune můžete nastavit profil dodržování předpisů zařízením, který vyhodnocuje jeho stav dodržování předpisů. Tento stav dodržování předpisů se oznamuje službě Azure Active Directory, která prosadí zásadu, když se uživatel pokusí získat přístup k firemním prostředkům. O dodržování předpisů zařízením v Intune si můžete přečíst v článku [Co je dodržování předpisů v zařízeních](/intune-azure/set-device-compliance/what-is-device-compliance).

Podmíněný přístup ke cloudovým aplikacím, jako je Exchange Online, lze nakonfigurovat pomocí služby Azure Active Directory. Další informace najdete v tomto [článku](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).

## <a name="on-premises-conditional-access-in-intune"></a>Místní podmíněný přístup v Intune

Pomocí podmíněného přístupu v Intune můžete na základě správy a registrace zařízení povolit nebo zablokovat přístup k **místnímu Exchangi**.

K vyhodnocení toho, jak zařízení dodržuje předpisy, se používají nastavení profilu zásad dodržování předpisů zařízením. Na základě tohoto vyhodnocení pak podmíněný přístup povolí nebo zablokuje přístup k místnímu Exchangi. Když zásady podmíněného přístupu použijete v kombinaci s profilem dodržování předpisů zařízením, povolí se přístup k místnímu Exchangi jen zařízením dodržujícím předpisy. Konfigurací upřesňujících nastavení podmíněného přístupu můžete dosáhnout odstupňované kontroly, například povolit nebo zablokovat určité platformy nebo okamžitě zablokovat zařízení, která nejsou spravovaná přes Intune.

Profil dodržování předpisů zařízením a podmíněný přístup se přiřazují uživateli. Kontroluje se dodržování předpisů jakéhokoli zařízení, které uživatel používá pro přístup k místnímu Exchangi. Mějte na paměti, že uživatel, který zařízení používá, musí mít přiřazený profil dodržování předpisů, aby se dodržování předpisů zařízením vyhodnocovalo. Pokud uživatel nemá nasazené žádné zásady dodržování předpisů, považuje se zařízení za dodržující předpisy a žádná omezení přístupu se neuplatní.

Pokud zařízení nesplňuje stanovené podmínky, je koncový uživatel proveden procesem jeho registrace a vyřešení problému, kvůli kterému zařízení nedodržuje předpisy.

## <a name="next-steps"></a>Další kroky

[Jak vytvořit zásadu podmíněného přístupu pro místní Exchange](create-conditional-access-policy-for-exchange-on-premises.md)

[Jak nakonfigurovat podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO1-->


