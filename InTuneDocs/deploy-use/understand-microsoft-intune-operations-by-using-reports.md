---
title: "Pochopení operací pomocí sestav | Dokumentace Microsoftu"
description: "Vytváření a správa sestavo softwaru, hardwaru a licencích k softwaru ve vaší organizaci"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 3400a49feaca9ef34bcffcc176bc496310d4c357



---

# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Pochopení operací Microsoft Intune pomocí sestav

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Informace v tomto tématu vám pomůžou vytvářet a spravovat sestavy Microsoft Intune, které obsahují informace o softwaru, hardwaru a licencích k softwaru ve vaší organizaci.

## <a name="using-reports"></a>Použití sestav
Sestavy Intune obsahují informace o softwaru, hardwaru a licencích k softwaru ve vaší organizaci. Sestavy vám můžou pomoct potvrdit aktuální potřeby a předpovídat budoucí výdaje. Pracovní prostor **Sestavy** poskytuje nástroje k vytváření a správě sestav. 

### <a name="report-types"></a>Typy sestav

|Typ sestavy|Popis|
|---------------|---------------|
|**Sestavy aktualizací**|Zobrazí aktualizace softwaru, které se úspěšně nainstalovaly na počítače ve vaší organizaci. Zobrazí se i aktualizace, které se nainstalovat nepodařilo, čekají na instalaci, nebo jsou potřeba. Další informace o aktualizaci softwaru najdete v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Sestavy zjištěného softwaru**|Zobrazují software, který je nainstalován na počítačích ve vaší organizaci. Zahrnuty jsou i verze softwaru. Zobrazené informace můžete filtrovat na základě vydavatele softwaru a kategorie softwaru. Zvolením směrové šipky vedle položky seznamu můžete aktualizace v seznamu rozbalit a zobrazit tak další podrobnosti (třeba počítače, na kterých jsou nainstalované).<br /><br />Když v Intune vyřadíte počítače z provozu nebo změníte jejich členství ve skupinách, může trvat několik minut, než se tyto změny v sestavě zjištěného softwaru projeví. Pokud chcete nejaktuálnější data inventáře softwaru, po vyřazení počítačů nebo změně jejich členství ve skupinách počkejte několik minut a až pak spusťte sestavu zjištěného softwaru zahrnující tyto počítače.|
|**Sestavy inventáře počítačů**|Zobrazují informace o spravovaných počítačích ve vaší organizaci. Pomocí této sestavy můžete plánovat nákupy hardwaru a lépe porozumět hardwarovým potřebám uživatelů ve vaší organizaci. Další informace o práci se spravovanými počítači najdete v tématu [Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Sestavy inventáře mobilních zařízení**|Zobrazují informace o mobilních zařízeních ve vaší organizaci. Zobrazené informace můžete filtrovat podle skupin, podle toho, jestli byl v zařízení provedený jailbreak nebo rootování, a podle operačního systému.|
|**Sestavy zakoupených licencí**|Zobrazují názvy softwaru pro všechen licencovaný software ve vybraných skupinách licencí podle jejich licenčních smluv. Pokud se informace o licencích softwaru déle než 24 hodin neaktualizují, aktualizují se při vygenerování sestavy licencí. Sestava licencí není přesný výčet názvů používaného softwaru ani doklad o souladu se smlouvami. Sestava je nástroj, který vám pomůže provádět rozhodnutí týkající se licencování pro vaši organizaci. Intune nemusí rozpoznat některé produkty, které mohou mít multilicenci Microsoftu. Jsou k dispozici tyto filtry:<br /><br />**Všechny smlouvy** – zobrazí všechny licencované softwarové produkty, které jsou spravované prostřednictvím Intune.<br /><br />**Multilicenční smlouvy** – zobrazí jenom softwarové produkty webu VLSC (Volume Licensing Service Center).<br /><br />**Licenční smlouvy na ostatní software** – zobrazí softwarové produkty, které jsou spravované mimo VLSC.|
|**Sestavy instalací a licencí**|Porovnávají software nainstalovaný na počítačích ve vaší organizaci s aktuálními licenčními smlouvami podle webu VLSC. Filtry zahrnují:<br /><br />**Všechny smlouvy** – zobrazí všechny licencované softwarové produkty, které jsou spravované prostřednictvím Intune.<br /><br />**Multilicenční smlouvy** – zobrazí jenom softwarové produkty VLSC.<br /><br />**Licenční smlouvy na ostatní software** – zobrazí softwarové produkty, které jsou spravované mimo VLSC.|
|**Sestavy podmínek a ujednání**|Zobrazují, jestli uživatelé přijali podmínky a ujednání, které jste nasadili, a kterou verzi přijali. Můžete zobrazit přijetí všech nasazených podmínek a ujednání, a to až pro 10 uživatelů. Případně můžete zobrazit stav přijetí pouze pro určitou nasazenou podmínku.|
|**Sestavy nekompatibilních aplikací**|Zobrazují informace o uživatelích s nainstalovanými aplikacemi, které jsou na vašem seznamu kompatibilních a nekompatibilních aplikací. Tato sestava slouží k vyhledání uživatelů a zařízení, která nejsou v souladu s vašimi firemními zásadami pro aplikace.|
|**Sestavy souladu certifikátů**|Zobrazují, které certifikáty byly vydané uživatelům a zařízením prostřednictvím SCEP nebo PKCS 12 (PFX). Tato sestava slouží k vyhledání certifikátů, které jsou vydané, mají ukončenou platnost nebo jsou odvolané.|
|**Sestavy historie zařízení**|Zobrazují historický protokol akcí vyřazení, vymazání a odstranění. Tato sestava slouží k zobrazení, kdo v minulosti akce v zařízeních inicioval.|
|**Sestavy ověření stavu**|Zobrazují stav mobilních zařízení.|
|**Mac OS X – sestava hardwaru**|Zobrazuje podrobnosti o hardwaru všech registrovaných zařízení se systémem Mac OS X ve vybraných skupinách. Informace o inventáři hardwaru shromážděné z těchto zařízení najdete v tématu [Seznámení se zařízeními s inventářem v Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Mac OS X – sestava softwaru**|Zobrazuje software nainstalovaný na všech zařízeních se systémem Mac OS X ve vybraných skupinách. V sestavě se uvádí název softwaru (jako ID sady), zkrácený (nebo uživatelsky přívětivý) název, verze a počet zařízení s nainstalovaným softwarem.|

#### <a name="to-create-a-report"></a>Vytvoření sestavy

1.  V konzole správce Intune vyberte **Sestavy**. Zvolte typ sestavy, kterou chcete vygenerovat, jak je popsáno v předchozí tabulce.

2.  Na stránce **Vytvořit novou sestavu** přijměte výchozí hodnoty, případně je upravte, aby se vyfiltrovaly výsledky, které bude sestava obsahovat. Můžete třeba vybrat, aby se v sestavě zjištěného softwaru zobrazil jenom software vydávaný Microsoftem.

3.  Pokud vyberete **Zobrazit sestavu**, sestava se otevře v novém okně.

Pokud chcete sestavu seřadit podle kteréhokoli zobrazeného sloupce, vyberte jeho záhlaví. Kromě toho některé sestavy umožňují rozbalit položky na seznamu a zobrazit více podrobností.

## <a name="more-report-actions"></a>Další akce sestav
Sestavy navíc podporují následující akce:

|Akce|Další informace|
|----------|--------------------|
|**Tisk**|V otevřené sestavě vyberte ikonu tisku a postupujte podle pokynů.|
|**Export**|V otevřené sestavě vyberte ikonu exportu a postupujte podle pokynů. Sestavy můžete exportovat do formátu hodnot oddělených čárkou (CSV) nebo formátu HTML.|
|**Uložení**|Na stránce **Vytvořit novou sestavu** může každý uživatel uložit až 100 sestav. Konfigurujte parametry sestavy podle svých požadavků a pak vyberte **Uložit**nebo **Uložit jako** (pokud chcete použít jiný název).|
|**Načtení**|Na stránce **Vytvořit novou sestavu** vyberte **Načíst**, pokud chcete načíst některou z dříve uložených sad parametrů sestavy.|
|**Odstranit**|V pracovním prostoru **Sestavy** vyberte požadovaný typ sestavy a zvolte **Načíst**. Potom v seznamu sestav vyberte ikonu odstranění (x), která se nachází vedle sestavy.|

### <a name="see-also"></a>Související témata
[Monitorování a sestavy v Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


