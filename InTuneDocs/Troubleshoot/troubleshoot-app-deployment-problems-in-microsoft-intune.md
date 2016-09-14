---
title: "Řešení problémů s nasazením aplikací | Microsoft Intune"
description: "Tento článek vám pomůže při řešení problémů s nasazením aplikací pomocí Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa96cf3a1909e3ea2187a3beb0aede3228894504
ms.openlocfilehash: 9f4b91bd523c82665bcac54902b2e8cc9c72ef75


---

# Řešení problémů s nasazením aplikací v Microsoft Intune
Pokud máte potíže s nasazením a správou aplikací v Intune, začněte zde. Toto téma popisuje některé běžné problémy, na které můžete narazit, a jejich řešení.

## Běžné problémy s nasazením aplikací

### V Portálu společnosti chybí kontaktní údaje oddělení IT

1.  V konzole správce Intune zvolte **Správa** &gt; **Portál společnosti**.

2.  Nastavte kontaktní údaje pro **kontaktování IT oddělení** .

### Pokud nevidíte konkrétní aplikace v seznamu

1.  Ujistěte se, že se díváte seznam aplikací pro uživatele nebo zařízení, pro které se aplikace nasadila.

2.  Ujistěte se, že zařízení splňuje požadavky na aplikaci.

### Pokud se vám při stahování aplikace zobrazí chybová zpráva

1.  Ujistěte se, že neprobíhá více než jedno souběžné stahování na jednoho uživatele. Každý uživatel může najednou stahovat jenom jednu aplikaci.

2.  Ujistěte se, že na jednotlivé účty nepřipadá moc velký počet souběžných stahování. Počkejte několik minut a potom to zkuste znova.

3.  Pokud se zobrazí nativní zpráva iOS s informacemi o tom, že nemůžete instalovat, že instalace je zrušená nebo že to musíte zkusit znova, může to být způsobené aktuálně vysokým přenosem. Počkejte několik minut a potom to zkuste znova.

4.  Pokud indikátor průběhu stahování iOS aplikace ukazuje dokončení, ale aplikace nejde nainstalovat, bude nejspíš chyba v souborech aplikace, které jste dali k dispozici.


### Pokud se vám aplikace „zasekne“ při nahrávání

1.  Při nahrávání aplikace se nejdřív přidají metadata a pak balíček aplikace. Až se nahrají metadata, začne se aktualizovat průběh nahrávání aplikace. Pokud zjistíte, že se vám aplikace v průběhu nahrávání „zasekla“ na neobvykle dlouhou dobu, odstraňte aplikaci a nahrajte ji znovu.

2.  Pokud takto aplikace takto zůstane viset, nespravujte její nasazení.

### Pokud dojde k chybě při instalaci iOS aplikace

1.  Ujistěte se, že brána firewall vaší organizace umožňuje přístup na weby zřizování a certifikace společnosti Apple.

2.  Další informace najdete v dokumentaci pro vývojáře Apple.

### Pokud spravované aplikace nehlásí stav instalace

Stav instalace se pro instalace spravovaných aplikací před aktualizací služby Microsoft Intune v listopadu 2014 neshromažďoval. Pro zařízení, na které se nainstalovaly spravované aplikace před aktualizací této služby, aktualizujte nasazení každé přidružené aktualizace pomocí odpovídající akce nasazení (například **Dostupná instalace**). Každé zařízení aplikaci aktualizuje během automatického zjišťování dostupnosti aplikací. Další informace najdete v tématu [Aktualizace aplikací pomocí Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Kódy chyb nasazení aplikací
V následující tabulce najdete běžné chyby, ke kterým může dojít během nasazování aplikací v Intune, pravděpodobné příčiny a možná řešení.

|Kód chyby|Možný problém|Navržené řešení|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (chyba klienta)|Pro instalaci této aplikace musíte mít systém s podporou zkušebního načtení.|Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu AllowAllTrustedApps, nebo zařízení, které má licenci pro zkušební načtení systému Windows s povolenou zásadou AllowAllTrustedApps (aplikuje se při registraci zařízení s Windows RT).|
|0x80073CF0|Balíček se nepodařilo otevřít.|Možné příčiny:<br /><br />-   Balíček není podepsaný.<br />-   Název vydavatele neodpovídá subjektu podpisového certifikátu.<br /><br />Další informace najdete v protokolu událostí AppxPackagingOM.|
|0x80073CF3|Selhalo ověření aktualizace, závislostí nebo konfliktů balíčku.|Možné příčiny:<br /><br />-   Příchozí balíček je v konfliktu s nainstalovaným balíčkem.<br />-   Nebyla nalezena zadaná závislost balíčku.<br />-   Balíček nepodporuje správnou architekturu procesoru.<br /><br />Další informace najdete v protokolu událostí AppXDeployment-Server.|
|0x80073CFB|Zadaný balíček je už nainstalovaný a přeinstalace balíčku je blokovaná.|Tato chybová zpráva se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<br /><br />-   Zvýšíte číslo verze aplikace a pak balíček znova sestavíte a podepíšete.<br />-   Než budete instalovat nový balíček, odeberte starý balíček pro každého uživatele v systému.|
|0x87D1041C|Instalace aplikace úspěšně proběhla, ale není zjištěna aplikace.|– Aplikace byla úspěšně nasazena službou Intune a potom byla odinstalována (zřejmě koncovým uživatelem). Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Požadované aplikace budou automaticky znovu nainstalovány, jakmile se zařízení příště připojí.|

### Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO5-->


