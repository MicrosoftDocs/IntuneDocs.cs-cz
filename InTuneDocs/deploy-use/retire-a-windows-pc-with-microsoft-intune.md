---
title: "Vyřazení počítače s Windows | Microsoft Intune"
description: "Jak vyřadit počítač s Windows spravovaný pomocí Intune"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 19e8e2b6a7eaa3cf02e4296a6fd147baa1472b61


---

# <a name="retire-a-windows-pc"></a>Vyřazení počítače s Windows
Pomocí následujícího postupu můžete vyřadit počítače spravované v Intune.

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, který chcete vyřadit).

2.  Vyberte zařízení, která chcete vyřadit, a potom zvolte **Vyřadit z provozu či vymazat**.

Když budete chtít počítač do služby Intune znovu zaregistrovat, přeinstalujte na počítači klientský software, a to podle pokynů uvedených v tématu [Instalace klienta na počítači s Windows pomocí Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Když se nějaký počítač nemůže k Intune připojit, v pracovním prostoru **Řídicí panel** se zobrazí zpráva.

Při vyřazení počítače s stane toto:

-   Počítač se odebere z inventáře a správy Intune a licence, které jsou k němu přiřazené, se uvolní pro nové použití. Vyřazení z provozu či vymazání odebere klientský software Intune, ale neodstraní z počítače aplikace a data. Toto vyřazení neodstraní z počítače úplně všechna data.

-   Jeho stav se už nebude zobrazovat v konzole Intune.

-   Intune odebere z počítače klientský software. Pokud počítač není ke službě Intune připojený, klientský software se odebere, až se počítač zase připojí.

-   Z počítače se odebere Microsoft Intune Endpoint Protection. Pokud je na počítači nainstalovaná jiná aplikace ochrany koncových bodů a je zakázaná, může se tato aplikace po odebrání služby Intune zase povolit, aby se zajistila ochrana vašich počítačů.

-   Z počítače se odeberou všechny zásady a změní se hodnoty nastavené těmito zásadami.

-   Počítač už nebude od služby Intune dostávat aktualizace softwaru ani aktualizace definic malwaru.

-   Podle toho, jak jsou vyřazené počítače nakonfigurované, můžou dál dostávat aktualizace pomocí služeb Windows Server Update Services, Windows Update nebo Microsoft Update.

    > [!IMPORTANT]
    > Když byl klientský software nainstalován pomocí objektu zásad skupiny, musíte tento objekt před odebráním klientského softwaru odebrat, abyste zabránili přeinstalaci softwaru.

    Pokud se odinstalace klienta nepovede, najdete další pomoc v tématu [Řešení potíží se službou Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

### <a name="see-also"></a>Související témata

[Běžné úlohy správy počítačů s Windows pomocí klientského softwaru Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


