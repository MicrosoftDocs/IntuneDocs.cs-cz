---
title: "Pravidla přístupu k Exchangi pro mobilní zařízení spravovaná Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: ef0b9901e340aec8b2b516f0180133e37833bf37


---

# Pravidla přístupu k Exchangi pro mobilní zařízení
Pravidla přístupu k Exchangi pro mobilní zařízení určují úroveň přístupu k Exchangi, kterou tato zařízení mají. Tato nastavení ovlivňují všechna mobilní zařízení včetně zařízení, která nejsou registrovaná v Microsoft Intune. Můžete začít tak, že definujete **Výchozí pravidlo** , které bude platit pro všechna mobilní zařízení, u kterých se nepoužívá vlastní pravidlo. Úrovně přístupu spravované protokolem Exchange ActiveSync jsou uvedené v následující tabulce:

|Úroveň přístupu|Popis|
|----------------|---------------|
|**Povolit všem mobilním zařízením přístup k systému Exchange, pokud uživatelské pravidlo neurčí jinak.**|Ve stavu *povoleného přístupu* se můžou mobilní zařízení synchronizovat prostřednictvím protokolu Exchange ActiveSync a připojovat se k serveru Exchange za účelem načtení e-mailů a spravování kalendáře, kontaktů, úkolů a poznámek. Tento stav bude trvat, dokud bude zařízení v souladu se **zásadami zabezpečení mobilních zařízení v Intune** , které jste nakonfigurovali (pokud správce Exchange uživatele nebo určité mobilní zařízení nezablokoval).|
|**Blokovat všem mobilním zařízením přístup k systému Exchange, pokud uživatelské pravidlo neurčí jinak.**|Ve stavu *blokování přístupu* jsou mobilní zařízení blokovaná a nemohou se připojit k serveru Exchange. Zařízení obdrží chybu HTTP 403 Zakázáno. Uživatel dostane ze serveru Exchange zprávu, že byl přístup mobilního zařízení k příslušné poštovní schránce zablokován. Tato zpráva nemůže být na blokovaném mobilním zařízení. Do této zprávy můžete přidat vlastní text a dát tak uživatelům, jejichž zařízení jsou zablokovaná, příslušné pokyny. Můžete to udělat pomocí úlohy **Nastavit oznámení uživatele**.|
|**Umístit všechna mobilní zařízení do karantény, aby o každém z nich bylo možné rozhodnout později, pokud uživatelské pravidlo neurčí jinak.**|Pokud je mobilní zařízení v karanténě, nemůže se k serveru Exchange připojit. Má jenom omezený přístup k datům. Uživatel může přidávat obsah do vlastních složek Kalendář, Kontakty, Úkoly a Poznámky, ale server nedovolí zařízení načíst žádný obsah z poštovní schránky uživatele. Uživatel dostane jednu e-mailovou zprávu s oznámením, že je mobilní zařízení v karanténě. Tato zpráva je doručená do zařízení a do schránky uživatele. Do této zprávy můžete přidat vlastní text a dát tak uživatelům, jejichž zařízení jsou v karanténě, příslušné pokyny. Dá se to udělat pomocí úkolu **Nastavit oznámení uživatele** .|

Strategie přístupu je tvořená kombinací nastavení **Výchozí pravidlo** a **Vlastní pravidla** , která platí pro všechna mobilní zařízení připojená k Exchangi. Některé příklady strategií přístupu jsou uvedené v následující tabulce.

|Strategie přístupu|Popis|
|-------------------|---------------|
|Seznam povolených položek|Pomocí *seznamu povolených položek* můžete udělit přístup známým zařízením na seznamu a všem ostatním zařízením přístup zakázat. K tomu musíte vytvořit vlastní pravidla, která požadovaným zařízením povolí přístup k poštovním schránkám uživatelů. Až takové pravidlo vytvoříte, musíte nastavit výchozí pravidlo přístupu, které všechna ostatní zařízení zablokuje nebo je dá do karantény. Nové zařízení můžete do seznamu povolených položek přidat vytvořením nového vlastního pravidla.|
|Seznam blokovaných položek|Pomocí *seznamu blokovaných položek* můžete ve výchozím nastavení udělit přístup všem zařízením a zablokovat přístup skupině zařízení, kterým v organizaci nechcete povolit přístup. Seznam blokovaných položek můžete vytvořit tak, že vytvoříte vlastní pravidla pro blokování zařízení, která nechcete synchronizovat s poštovními schránkami organizace. Výchozí pravidlo by mělo být nastavené tak, aby umožňovalo přístup všem zařízením, která nejsou explicitně blokovaná existujícími pravidly. Nové zařízení nebo skupinu zařízení můžete do seznamu blokovaných položek přidat tak, že vytvoříte nové vlastní pravidlo.|
|Kombinace seznamů povolených a blokovaných položek|Kromě vytvoření seznamu povolených a blokovaných položek můžete mobilní zařízení, která jsou v organizaci nová a zatím je vyhodnocujete, dát do karantény. Když třeba máte seznam blokovaných položek pro mobilní zařízení, která nejsou v organizaci povolená, a seznam povolených položek pro mobilní zařízení, které jsou v organizaci povolená, můžete nastavit ještě výchozí pravidlo pro karanténu. Všechny ostatní zařízení se automaticky umístí do karantény. To vám umožňuje nově zaváděná zařízení v organizaci vyzkoušet a rozhodnout se, jestli je přidáte do seznamu povolených položek, nebo do seznamu zakázaných položek.|
Postup vytvoření vlastního pravidla je popsaný v následující části.

## Vytvoření výchozího pravidla přístupu

1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) &gt; **Zásady** &gt; **Přístup k systému Exchange pro mobilní zařízení**.

2.  V seznamu **Výchozí pravidlo** vyberte pravidlo přístupu, které chcete použít u všech mobilních zařízení, pro která neplatí pravidlo nebo osobní výjimka. Vyberte **Uložit**.

Postup vytvoření vlastního pravidla je popsaný v následující části.

## Vytvoření vlastního pravidla přístupu

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) &gt; **Zásady** &gt; **Přístup k systému Exchange pro mobilní zařízení**.

2.  V seznamu **Vlastní pravidla** vyberte **Přidat pravidlo** a vytvořte vlastní pravidlo. Vyberte **Uložit**.



<!--HONumber=Jun16_HO4-->


