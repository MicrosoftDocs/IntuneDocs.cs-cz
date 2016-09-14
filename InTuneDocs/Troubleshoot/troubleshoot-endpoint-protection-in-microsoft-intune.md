---
title: "Řešení potíží se službou Endpoint Protection | Microsoft Intune"
description: "Řešení problémů během používání služby Microsoft Intune Endpoint Protection."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: 71f976fba252950fd9a8818fb27fbbb294369894


---

# Troubleshoot Endpoint Protection in Microsoft Intune

Informace uvedené v této části vám můžou pomoct při řešení potíží, ke kterým dochází při používání služby Endpoint Protection v Microsoft Intune.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.


### Chybové zprávy služby Endpoint Protection
V této části se popisují možné příčiny následujících chyb a varování zobrazovaných v podokně **Stav produktu Endpoint Protection** v [konzole správce Intune](https://manage.microsoft.com) a jejich řešení.

|Položka stavu|Možné příčiny|Možná řešení|
|---------------|--------------------|-----------------------|
|**Modul služby Endpoint Protection není k dispozici.**|Modul Endpoint Protection služby Intune je poškozený nebo odstraněný.|Pokud je modul Endpoint Protection služby Intune poškozený, můžete zkusit příslušný software aktualizovat nebo přeinstalovat.<br /><br />Pokud chcete vynutit okamžitou aktualizaci, zvolte v klientském softwaru Endpoint Protection **Aktualizovat** (tuto možnost najdete na hlavním panelu spravovaných počítačů).<br /><br />Pokud se modul Endpoint Protection nedá aktualizovat, musíte ho přeinstalovat.<br /><br />V seznamu nainstalovaných programů v Ovládacích panelech spravovaného počítače najděte položku **Microsoft Intune Endpoint Protection Agent** a pak tuto aplikaci odinstalujte.<br /><br />Při další synchronizaci aktualizací zjistí program Microsoft Online Management Update Manager chybějící program a v další naplánované době pro instalace ho nainstaluje znova.|
|**Služba Endpoint Protection je zakázána.**|Správce zakázal službu Intune Endpoint Protection pomocí zásad nebo ji na spravovaném počítači zakázal uživatel.|Pokud je služba Endpoint Protection zakázaná, můžete ji povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete službu Endpoint Protection povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, pak změňte nastavení **Povolit službu Endpoint Protection**.<br /><br />Nebo,<br /><br />pokud chcete povolit službu Endpoint Protection ze spravovaného počítače, spusťte z oznamovací oblasti klienta Intune Endpoint Protection. Zobrazí se výzva k povolení služby Endpoint Protection.|
|**Ochrana v reálném čase je zakázána.**|Ochranu v reálném čase zakázal správce (pomocí zásad) nebo ji na spravovaném počítači zakázal uživatel.|Pokud je ochrana v reálném čase zakázaná, můžete ji povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete ochranu v reálném čase povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, pak změňte nastavení **Povolit ochranu v reálném čase** na **Ano**.<br /><br />Nebo,<br /><br />pokud chcete ochranu v reálném čase povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zobrazí se vám výzva k povolení ochrany v reálném čase.|
|**Kontrola stahování zakázána**|Kontrolu stahování zakázal správce pomocí zásad nebo ji na spravovaném počítači zakázal uživatel.|Pokud je kontrola stahování zakázaná, můžete ji povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete kontrolu stahování povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, pak změňte nastavení **Prověřit všechna stahování** na **Ano**.<br /><br />Nebo,<br /><br />pokud chcete kontrolu stahování povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zvolte kartu **Nastavení**, zvolte **Ochrana v reálném čase**, zaškrtněte políčko **Prověřit všechna stahování** a potom zvolte **Uložit změny**.|
|**Monitorování aktivit souborů a programů zakázáno**|Monitorování aktivit souborů a programů zakázal správce pomocí zásad nebo ho na spravovaném počítači zakázal uživatel.|Pokud je monitorování aktivit souborů a programů zakázané, můžete ho povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete monitorování aktivit souborů a programů povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, pak změňte nastavení **Sledovat činnost souborů a programů v počítačích** na **Ano**.<br /><br />Nebo,<br /><br />pokud chcete monitorování aktivit souborů a programů povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zvolte kartu **Nastavení**, zvolte **Ochrana v reálném čase**, zaškrtněte políčko **Sledovat aktivitu souborů a programů na vašem počítači** a potom zvolte **Uložit změny**.|
|**Monitorování chování zakázáno**|Monitorování chování zakázal správce (pomocí zásad) nebo ho na spravovaném počítači zakázal uživatel.|Pokud je monitorování chování zakázané, můžete ho povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete monitorování chování povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, změňte nastavení **Povolit sledování chování** na **Ano** a potom restartujte spravovaný počítač.<br /><br />Nebo,<br /><br />pokud chcete monitorování chování povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zvolte kartu **Nastavení**, zvolte **Ochrana v reálném čase**, zaškrtněte políčko **Povolit monitorování chování** a potom zvolte **Uložit změny**. Potom restartujte počítač.|
|**Kontrola skriptů zakázána**|Kontrolu skriptů zakázal správce (pomocí zásad) nebo ji na spravovaném počítači zakázal uživatel.|Pokud je kontrola skriptů zakázaná, můžete ji povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete kontrolu skriptů povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, změňte nastavení **Povolit prověřování skriptů** na **Ano**.<br /><br />Nebo,<br /><br />pokud chcete kontrolu skriptů povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zvolte kartu **Nastavení**, zvolte **Ochrana v reálném čase**, zaškrtněte políčko **Povolit prohledávání skriptů** a potom zvolte **Uložit změny**.|
|**Systém kontroly sítě zakázán**|Systém kontroly sítě zakázal správce pomocí zásad nebo ho na spravovaném počítači zakázal uživatel.|Pokud je systém kontroly sítě zakázaný, můžete ho povolit z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače. Udělejte jednu z těchto věcí:<br /><br />Pokud chcete systém kontroly sítě povolit z [konzoly pro správu Intune](https://manage.microsoft.com), otevřete pracovní prostor **Zásady** a v zásadách, které platí pro příslušný počítač, změňte nastavení **Povolit systém kontroly sítě** na **Ano** a potom restartujte spravovaný počítač.<br /><br />Nebo,<br /><br />pokud chcete systém kontroly sítě povolit ze spravovaného počítače, spusťte z oznamovací oblasti klientský software služby Endpoint Protection. Zvolte kartu **Nastavení**, zvolte **Ochrana v reálném čase**, zaškrtněte políčko **Povolit systém kontroly sítě** a potom zvolte **Uložit změny**. Restartujte počítač.|
|**Definice malwaru nejsou aktuální**|Počítač mohl být delší dobu odpojený od internetu a jeho definice malwaru se nejspíš ještě neaktualizovaly. Tato stavová zpráva se zobrazuje, když jsou definice malwaru na počítači staré 14 dnů a víc.|Pokud jsou definice malwaru zastaralé, můžete je aktualizovat z [konzoly pro správu Intune](https://manage.microsoft.com) nebo ze spravovaného počítače.<br /><br />Další informace najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**Zpožděna úplná kontrola**|14 dnů se kompletně neudělala úplná kontrola. Může to být tím, že se počítač během úplné kontroly restartoval.|Pokud je úplná kontrola zpožděná, můžete podle informací uvedených v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) spustit jednorázovou úplnou kontrolu nebo naplánovat v [konzole správce Intune](https://manage.microsoft.com) úplné kontroly, které budou probíhat opakovaně.|
|**Zpožděna rychlá kontrola**|14 dnů se kompletně neudělala rychlá kontrola. Může to být způsobené restartováním během rychlé kontroly.|Pokud je rychlá kontrola zpožděná, můžete podle informací uvedených v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) spustit jednorázovou rychlou kontrolu nebo naplánovat v [konzole správce Intune](https://manage.microsoft.com) rychlé kontroly, které budou probíhat opakovaně.|
|**Je spuštěna jiná aplikace ochrany koncových bodů.**|Je spuštěná jiná aplikace ochrany koncových bodů a počítač je v pořádku.|Ve výchozím nastavení platí, že když je nainstalovaná jiná aplikace ochrany koncových bodů a Intune tuto aplikaci rozpozná, služba Endpoint Protection se automaticky vypne. Pokud Intune jinou aplikaci ochrany koncových bodů nerozpozná, zůstane služba Endpoint Protection zapnutá. Další informace najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|

### Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO1-->

