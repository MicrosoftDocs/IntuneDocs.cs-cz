---
title: Migrace na Intune | Dokumentace Microsoftu
description: "Migrace ze stávajícího podnikového řešení správy mobilních zařízení na Intune se dá provést pomocí následujícího obecného postupu."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d92b8b03c1c71898a15b1d1f0a1ee5e1f288dc2e
ms.openlocfilehash: 759e5b7d04ccbbfb338d182bad03e0b0218cdeca


---

# <a name="migrate-to-intune"></a>Migrace na Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Migrace ze stávajícího podnikového řešení správy mobilních zařízení na Intune se dá provést pomocí následujícího obecného postupu:

![Kroky pro migraci na Intune](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>Oznámení uživatelům

Až se ujistíte, že pilotní nasazení Intune vyhovuje vaším požadavkům, upozorněte své uživatele na nadcházející migraci jejich zařízení na Intune. E-mailové zprávy, pokyny a [letáky](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) můžou pomoct vytvořit očekávání a poskytnout podrobné informace o krocích registrace, které musí uživatelé provést, aby si zajistili nepřerušené připojení k firemním prostředkům a aplikacím. Zajistěte, aby byl váš tým podpory připravený uživatelům v procesu migrace pomoct.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>Úprava stávajícího podnikového řešení pro správu mobilních zařízení

Podle toho, jak hodláte naložit se zásadami podmíněného přístupu mezi stávajícím řešením pro správu mobilních zařízení a Intune, může být potřeba stávající zásady podmíněného přístupu zakázat. Stávající zásady podmíněného přístupu buď zakážete, NEBO nastavíte jejich rozsah tak, aby nezahrnovaly uživatele/zařízení, u kterých chcete provést migraci na Intune.  Nedovolte, aby zásady podmíněného přístupu uplatňovala na stejné uživatele/zařízení jak služba Intune, tak stávající podnikové řešení pro správu mobilních zařízení.

## <a name="enable-intune-conditional-access-policy-optional"></a>Povolení zásady podmíněného přístupu v Intune (volitelné)

Pokud jste se rozhodli, že chcete zásady podmíněného přístupu vynucovat okamžitě, bez období odkladu pro migrující zařízení, povolte v tomto kroku zásady podmíněného přístupu v Intune.  Nezapomeňte o tomto rozhodnutí podrobně informovat své uživatele a tým helpdesku.  Pokud nejsou zařízení zaregistrovaná v Intune a neodpovídají zásadám Intune, uživatelé nebudou mít přístup k podnikovým prostředkům, dokud se do Intune nezaregistrují a jejich zařízení nevyhoví zásadám Intune.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>Zrušení registrace zařízení ve stávajícím podnikovém řešení pro správu mobilních zařízení

Než se zařízení zaregistrují v Intune, je potřeba zrušit jejich registraci ve stávajícím podnikovém řešení pro správu mobilních zařízení. Doporučujeme umožnit uživatelům, aby si registraci svých zařízení zrušili sami.  Dodržujte při tom pokyny ke zrušení registrace od poskytovatele řešení, abyste měli jistotu, že uživatele a zařízení odeberete ze své platformy správně a budete koncové uživatele co nejméně rušit při práci.

## <a name="enrolling-devices-in-intune"></a>Registrace zařízení v Intune

Uživatelé, u kterých je naplánovaná migrace, by se měli okamžitě zaregistrovat v Intune, aby znovu získali přístup k podnikovým prostředkům, e-mailu a aplikacím, případně aby o něj nepřišli. Pokud nakonfigurujete podmíněný přístup a uživatelé se pokusí připojit k e-mailu dřív, než se zaregistrují v Intune, jejich přístup se zablokuje a dostanou e-mail s informacemi o registraci. Tento e-mail je provede registrací jejich zařízení v Intune.  Uživatelé se také můžou do Intune zaregistrovat prostřednictvím aplikace Portál společnosti Intune nebo nativně prostřednictvím operačního systému ve Windows 8.1 a Windows 10 Mobile. Další pokyny týkající se registračních kroků pro konkrétní platformu najdete v tématu [Co říct koncovým uživatelům o používání služby Microsoft Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

## <a name="configure-intune-conditional-access-optional"></a>Konfigurace podmíněného přístupu v Intune (volitelné)

Pokud jste povolili období odkladu pro vynucování podmíněného přístupu, o kterém jste informovali koncové uživatele, po jeho uplynutí zahájíte vynucování povolením zásad podmíněného přístupu v Intune. Hned jak to provedete, budou muset všechna zařízení splňovat požadavky zásad podmíněného přístupu služby Intune.

## <a name="enroll-remaining-devices-and-users"></a>Registrace zbývajících zařízení a uživatelů

Už máte povolený podmíněný přístup, takže se všichni uživatelé musí registrovat v Intune a splňovat zásady dodržování předpisů vaší organizace, aby mohli získat přístup k podnikovým prostředkům. Pokud migraci uživatelů provádíte formou registrace ve víc fázích (ne najednou), opakujte výše popsané kroky, dokud nebudou všechna zařízení a uživatelé zaregistrovaní a nebude je spravovat Intune.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>Vyřazení předchozího podnikového řešení pro správu mobilních zařízení z provozu

Až provedete migraci všech uživatelů a zařízení na Intune a zkontrolujete, jestli byla migrace na Intune úspěšná, můžete předchozí podnikové řešení pro správu mobilních zařízení vyřadit z provozu nebo zrušit předplatné služby. Postupujte při tom podle pokynů poskytovatele řešení, abyste měli jistotu, že správně odeberete všechny nepotřebné požadavky na infrastrukturu a zrušíte příslušné předplatné/licence.

## <a name="additional-migration-resources"></a>Další zdroje týkající se migrace

Potřebujete další pomoc s migrací na Intune? Nabízíme možnosti odborné pomoci, které vám pomůžou zajistit bezproblémovou migraci:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Microsoft Consulting Services](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Technická a netechnická podpora služby Intune](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Fórum Microsoft TechNet o Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>Kopie tohoto průvodce ke stažení

Verzi celého průvodce ke stažení najdete v [Galerii TechNetu](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Dec16_HO3-->


