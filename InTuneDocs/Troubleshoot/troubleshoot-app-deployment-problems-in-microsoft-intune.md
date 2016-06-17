---
# required metadata

title: Řešení problémů s nasazením aplikací | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Řešení problémů s nasazením aplikací v Microsoft Intune
Tento článek vám pomůže při řešení problémů s nasazením aplikací pomocí Microsoft Intune.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.


## Obvyklé problémy s nasazováním aplikací

### Pokud se nemůžete přihlásit do portálu společnosti Microsoft Intune

1.  Zkontrolujte, jestli váš účet existuje v [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) nebo jestli není zakázaný.

2.  Ujistěte se, že je pro vás tento účet zřízený v [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)..

3.  V [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) se ujistěte, že pro přihlášení do Intune používáte správné uživatelské jméno a heslo ve formátu: **joe@domain.com**..

### Pokud v aplikaci Portál společnosti chybí kontaktní informace na IT oddělení

1.  V konzole správce Intune klikněte na **Správa** &gt; **Portál společnosti**..

2.  Nastavte kontaktní údaje pro **kontaktování IT oddělení** .

### Pokud nevidíte konkrétní aplikace v seznamu

1.  Ujistěte se, že se díváte seznam aplikací pro uživatele nebo zařízení, pro které se aplikace nasadila.

2.  Ujistěte se, že zařízení splňuje požadavky na aplikaci.

### Pokud se vám při stahování aplikace zobrazí chybová zpráva

1.  Ujistěte se, že neprobíhá více než jedno souběžné stahování na jednoho uživatele. Každý uživatel může najednou stahovat jenom jednu aplikaci.

2.  Ujistěte se, že na jednotlivé účty nepřipadá moc velký počet souběžných stahování. Počkejte několik minut a potom to zkuste znova.

3.  Pokud se zobrazí nativní zpráva iOS s informacemi o tom, že nemůžete instalovat, že instalace je zrušená nebo že to musíte zkusit znova, může to být způsobené aktuálně vysokým přenosem. Počkejte několik minut a potom to zkuste znova.

4.  Pokud indikátor průběhu stahování iOS aplikace ukazuje dokončení, ale aplikace nejde nainstalovat, bude nejspíš chyba v souborech aplikace, které jste dali k dispozici.

### Pokud kliknutím na odkaz na iOS aplikaci přejdete do předchozího umístění v iTunes App Storu

1.  Aktuální relace iTunes App Storu se otevírá na předchozí stránce aplikace.

2.  Zavřete iTunes App Store na zařízení a zkuste odkaz použít znovu.

### Pokud se vám při spouštění iOS aplikace zobrazí chyba

1.  Datum vypršení platnosti aplikace nemusí být platné.

### Pokud se vám aplikace „zasekne“ při nahrávání

1.  Při nahrávání aplikace se nejdřív přidají metadata a pak balíček aplikace. Až se nahrají metadata, začne se aktualizovat průběh nahrávání aplikace. Pokud zjistíte, že se vám aplikace v průběhu nahrávání „zasekla“ na neobvykle dlouhou dobu, odstraňte aplikaci a nahrajte ji znovu.

2.  Pokud takto aplikace takto zůstane viset, nespravujte její nasazení.

### Pokud dojde k chybě při instalaci iOS aplikace

1.  Ujistěte se, že brána firewall vaší organizace umožňuje přístup na weby zřizování a certifikace společnosti Apple.

2.  Další informace najdete v dokumentaci pro vývojáře Apple.

### Chyba: Vydavatel neexistuje.
Používáte funkci **Přidat smlouvu na ostatní software** pro přidání licenční smlouvy třetí strany. Pokoušíte se přidat vydavatele přes stránku **Licenční smlouva na ostatní software**. Stránka poskytuje seznam existujících vydavatelů v abecedním pořadí.
Zadali jste chybějícího vydavatele, ale zobrazí se chybová zpráva **Vydavatel neexistuje**.. 

Jedná se o účel. Intune poskytuje sledování licencí pouze pro oblíbené softwarové produkty. Intune vyžaduje, aby software nahlásily nejméně 4 samostatné účty předtím, než je k dispozici jako volba v procesu licencování.

### Pokud spravované aplikace nehlásí stav instalace

Stav instalace se pro instalace spravovaných aplikací před aktualizací služby Microsoft Intune v listopadu 2014 neshromažďoval. Pro zařízení, na které se nainstalovaly spravované aplikace před aktualizací této služby, aktualizujte nasazení každé přidružené aktualizace pomocí odpovídající akce nasazení (například **Dostupná instalace**). Každé zařízení aplikaci aktualizuje během automatického zjišťování dostupnosti aplikací. Další informace najdete v článku [Aktualizace aplikací pomocí služby Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune)..

## <a name="BKMK_SoftDistErrorCodes"></a>Kódy chyb nasazení aplikací
V následující tabulce najdete běžné chyby, ke kterým může dojít během nasazování aplikací v Intune, pravděpodobné příčiny a možná řešení.

|Kód chyby|Možný problém|Navržené řešení|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (chyba klienta)|Pro instalaci této aplikace musíte mít systém s podporou zkušebního načtení.|Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu AllowAllTrustedApps, nebo zařízení, které má licenci pro zkušební načtení systému Windows s povolenou zásadou AllowAllTrustedApps (aplikuje se při registraci zařízení s Windows RT).|
|0x80073CF0|Balíček se nepodařilo otevřít.|Možné příčiny:<br /><br />-   Balíček není podepsaný.<br />-   Název vydavatele neodpovídá subjektu podpisového certifikátu.<br /><br />Další informace najdete v protokolu událostí AppxPackagingOM.|
|0x80073CF3|Selhalo ověření aktualizace, závislostí nebo konfliktů balíčku.|Možné příčiny:<br /><br />-   Příchozí balíček je v konfliktu s nainstalovaným balíčkem.<br />-   Nebyla nalezena zadaná závislost balíčku.<br />-   Balíček nepodporuje správnou architekturu procesoru.<br /><br />Další informace najdete v protokolu událostí AppXDeployment-Server.|
|0x80073CFB|Zadaný balíček je už nainstalovaný a přeinstalace balíčku je blokovaná.|Tato chybová zpráva se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<br /><br />-   Zvýšíte číslo verze aplikace a pak balíček znova sestavíte a podepíšete.<br />-   Než budete instalovat nový balíček, odeberte starý balíček pro každého uživatele v systému.|

### Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md)..


<!--HONumber=May16_HO1-->


