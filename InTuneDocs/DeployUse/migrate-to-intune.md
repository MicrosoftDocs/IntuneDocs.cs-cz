---
title: Migrace na Intune | Microsoft Intune
description: 
keywords: 
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 8c1f4f209c5ec704290882b8f6f71e0b1b01d21c
ms.openlocfilehash: 20394c243b9355cd3f4e30f170dfd00d10e1153f


---

# Migrace na Intune


Migrace ze stávajícího podnikového řešení správy mobilních zařízení na Intune se dá provést pomocí následujícího obecného postupu:

![Kroky pro migraci na Intune](./media/migrate-intune-steps.png)

## Oznámení uživatelům

Až se ujistíte, že pilotní nasazení Intune vyhovuje vaším požadavkům, upozorněte své uživatele na nadcházející migraci jejich zařízení na Intune. E-mailové zprávy, pokyny a [letáky](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) můžou pomoct vytvořit očekávání a poskytnout podrobné informace o krocích registrace, které musí uživatelé provést, aby si zajistili nepřerušené připojení k firemním prostředkům a aplikacím. Zajistěte, aby byl váš tým podpory připravený uživatelům v procesu migrace pomoct.

## Úprava stávajícího podnikového řešení pro správu mobilních zařízení

Podle toho, jak hodláte naložit se zásadami podmíněného přístupu mezi stávajícím řešením pro správu mobilních zařízení a Intune, může být potřeba stávající zásady podmíněného přístupu zakázat. Stávající zásady podmíněného přístupu buď zakážete, NEBO nastavíte jejich rozsah tak, aby nezahrnovaly uživatele/zařízení, u kterých chcete provést migraci na Intune.  Nedovolte, aby zásady podmíněného přístupu uplatňovala na stejné uživatele/zařízení jak služba Intune, tak stávající podnikové řešení pro správu mobilních zařízení.

## Povolení zásady podmíněného přístupu v Intune (volitelné)

Pokud jste se rozhodli, že chcete zásady podmíněného přístupu vynucovat okamžitě, bez období odkladu pro migrující zařízení, povolte v tomto kroku zásady podmíněného přístupu v Intune.  Nezapomeňte o tomto rozhodnutí podrobně informovat své uživatele a tým helpdesku.  Pokud nejsou zařízení zaregistrovaná v Intune a neodpovídají zásadám Intune, uživatelé nebudou mít přístup k podnikovým prostředkům, dokud se do Intune nezaregistrují a jejich zařízení nevyhoví zásadám Intune.

## Zrušení registrace zařízení ve stávajícím podnikovém řešení pro správu mobilních zařízení

Než se zařízení zaregistrují v Intune, je potřeba zrušit jejich registraci ve stávajícím podnikovém řešení pro správu mobilních zařízení. Doporučujeme umožnit uživatelům, aby si registraci svých zařízení zrušili sami.  Dodržujte při tom pokyny ke zrušení registrace od poskytovatele řešení, abyste měli jistotu, že uživatele a zařízení odeberete ze své platformy správně a budete koncové uživatele co nejméně rušit při práci.

## Registrace zařízení v Intune

Uživatelé, u kterých je naplánovaná migrace, by se měli okamžitě zaregistrovat v Intune, aby znovu získali přístup k podnikovým prostředkům, e-mailu a aplikacím, případně aby o něj nepřišli. Pokud nakonfigurujete podmíněný přístup a uživatelé se pokusí připojit k e-mailu dřív, než se zaregistrují v Intune, jejich přístup se zablokuje a dostanou e-mail s informacemi o registraci. Tento e-mail bude obsahovat pokyny k registraci jejich zařízení v Intune.  Uživatelé se také můžou do Intune zaregistrovat prostřednictvím aplikace Portál společnosti Intune nebo nativně prostřednictvím operačního systému ve Windows 8.1 a Windows 10 Mobile. Další informace o krocích registrace podle jednotlivých platforem najdete v tématu [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md).

## Konfigurace podmíněného přístupu v Intune (volitelné)

Pokud jste povolili období odkladu pro vynucování podmíněného přístupu, o kterém jste informovali koncové uživatele, po jeho uplynutí zahájíte vynucování povolením zásad podmíněného přístupu v Intune. Hned jak to provedete, budou muset všechna zařízení splňovat požadavky zásad podmíněného přístupu služby Intune.

## Registrace zbývajících zařízení a uživatelů

Už máte povolený podmíněný přístup, takže se všichni uživatelé musí registrovat v Intune a splňovat zásady dodržování předpisů vaší organizace, aby mohli získat přístup k podnikovým prostředkům. Pokud migraci uživatelů provádíte formou registrace ve víc fázích (ne najednou), opakujte výše popsané kroky, dokud nebudou všechna zařízení a uživatelé zaregistrovaní a nebude je spravovat Intune.

## Vyřazení předchozího podnikového řešení pro správu mobilních zařízení z provozu

Až provedete migraci všech uživatelů a zařízení na Intune a zkontrolujete, jestli byla migrace na Intune úspěšná, můžete předchozí podnikové řešení pro správu mobilních zařízení vyřadit z provozu nebo zrušit předplatné služby. Postupujte při tom podle pokynů poskytovatele řešení, abyste měli jistotu, že správně odeberete všechny nepotřebné požadavky na infrastrukturu a zrušíte příslušné předplatné/licence.

## Další zdroje týkající se migrace

Potřebujete další pomoc s migrací na Intune? Nabízíme možnosti odborné pomoci, které vám pomůžou zajistit bezproblémovou migraci:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Služba Microsoft Consulting Services](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Technická a netechnická podpora služby Intune](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Fórum Microsoft TechNet o Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## Kopie tohoto průvodce ke stažení

Verzi celého průvodce ke stažení najdete v [Galerii TechNetu](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Jun16_HO4-->


