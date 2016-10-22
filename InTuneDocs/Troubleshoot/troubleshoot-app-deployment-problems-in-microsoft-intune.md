---
title: "Řešení problémů s nasazením aplikací | Microsoft Intune"
description: "Tento článek vám pomůže při řešení problémů s nasazením aplikací pomocí Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: efc280f0a1143cacc252ee9fc9344064aa211cb2


---

# Řešení problémů s nasazením aplikací v Microsoft Intune
Pokud máte potíže s nasazením a správou aplikací v Intune, začněte zde. Toto téma popisuje některé běžné problémy, na které můžete narazit, a jejich řešení.

## Běžné chybové kódy při nasazování aplikací

|Kód chyby|Možný problém|Navržené řešení|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (chyba klienta)|Pro instalaci této aplikace musíte mít systém s podporou instalace aplikací bokem.|Ověřte, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu AllowAllTrustedApps, nebo na zařízení, které má licenci na instalaci aplikací Windows bokem s povolenou zásadou AllowAllTrustedApps.|
|0x80073CF0|Balíček se nepodařilo otevřít.|Možné příčiny:<br /><br />-   Balíček není podepsaný.<br />-   Název vydavatele neodpovídá subjektu podpisového certifikátu.<br /><br />Další informace najdete v protokolu událostí AppxPackagingOM.|
|0x80073CF3|Selhalo ověření aktualizace, závislostí nebo konfliktů balíčku.|Možné příčiny:<br /><br />-   Příchozí balíček je v konfliktu s nainstalovaným balíčkem.<br />-   Nebyla nalezena zadaná závislost balíčku.<br />-   Balíček nepodporuje správnou architekturu procesoru.<br /><br />Další informace najdete v protokolu událostí AppXDeployment-Server.|
|0x80073CFB|Zadaný balíček je už nainstalovaný a přeinstalace balíčku je blokovaná.|Tato chybová zpráva se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<br /><br />-   Zvýšíte číslo verze aplikace a pak balíček znova sestavíte a podepíšete.<br />-   Než budete instalovat nový balíček, odeberte starý balíček pro každého uživatele v systému.|
|0x87D1041C|Instalace aplikace úspěšně proběhla, ale není zjištěna aplikace.|– Aplikace byla úspěšně nasazena službou Intune a potom byla odinstalována (zřejmě koncovým uživatelem). Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Požadované aplikace budou automaticky znovu nainstalovány, jakmile se zařízení příště připojí.|

## Řešení problémů s aplikacemi z Windows Storu

Informace v tématu [Řešení problémů s vytvářením balíčků, nasazením a dotazy aplikací pro Windows Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) vám pomohou s řešením běžných problémů, na které můžete narazit při instalaci aplikací z Windows Storu, ať již pomocí služby Intune nebo jinak.

## Řešení problémů s nasazením aplikací do počítačů spravovaných softwarovým klientem Intune
Při řešení problémů s nasazením aplikací do počítačů spravovaných softwarovým klientem Intune vám může pomoct nahlédnout do následujících dvou souborů protokolu:
- složka %ProgramFiles%\Microsoft\OnlineManagement\Logs
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Pokud budete potřebovat otevřít případ podpory pro službu Intune, velmi pomůže, když společně s popisem problému zašlete do Microsoftu i tyto protokoly.


### Další kroky
Pokud vám tyto informace k řešení problémů nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Oct16_HO2-->


