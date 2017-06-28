---
title: "Pravidla přístupu k Exchangi pro mobilní zařízení"
description: "Pravidla přístupu k protokolu Exchange ActiveSync pro povolení nebo blokování připojení zařízení s EAS"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: a57b1f51fabfdc8896ecbb5bfbe6422f40672b18
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="exchange-access-rules-for-mobile-devices"></a>Pravidla přístupu k Exchangi pro mobilní zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pravidla přístupu k Exchangi pro mobilní zařízení určují úroveň přístupu k Exchange ActiveSync, kterou tato zařízení mají. Tato nastavení ovlivňují všechna mobilní zařízení včetně zařízení, která nejsou registrovaná v Microsoft Intune. Můžete začít tak, že definujete **Výchozí pravidlo**, které bude platit pro všechna mobilní zařízení, u kterých se nepoužívá vlastní pravidlo.

Úrovně přístupu spravované protokolem Exchange ActiveSync jsou uvedené v následující tabulce:

|Úroveň přístupu|Popis|
|----------------|---------------|
|**Povolit všem zařízením přístup na Exchange**|Ve stavu *povolit přístup* se můžou mobilní zařízení synchronizovat prostřednictvím protokolu Exchange ActiveSync a připojovat se k serveru Exchange za účelem načtení e-mailů a správy kalendáře, kontaktů, úkolů a poznámek. Tento stav bude trvat, dokud bude zařízení v souladu se zásadami schránky protokolu Exchange ActiveSync, které jste v Exchangi nakonfigurovali (pokud správce Exchange uživatele nebo konkrétní mobilní zařízení nezablokoval).|
|**Blokovat u všech zařízení přístup na Exchange**|Ve stavu *blokovat přístup* jsou mobilní zařízení blokovaná a nemůžou se připojit k serveru Exchange. Zařízení obdrží chybu HTTP 403 Zakázáno. Uživatel dostane ze serveru Exchange zprávu e-mailem, že přístup mobilního zařízení k příslušné poštovní schránce je zablokovaný. Tato zpráva nemůže být na blokovaném mobilním zařízení. Pomocí úlohy **Nastavit oznámení uživatele** můžete do této zprávy přidat vlastní text a poskytnout tak pokyny uživatelům, jejichž zařízení mají blokovaný přístup. |
|**Umístit zařízení do karantény, abyste je mohli povolit nebo zablokovat později**|Pokud je mobilní zařízení v karanténě, nemůže se k serveru Exchange připojit. Má jenom omezený přístup k datům. Uživatel může přidávat obsah do vlastních složek Kalendář, Kontakty, Úkoly a Poznámky, ale server nedovolí, aby zařízení načetlo jakýkoli obsah z poštovní schránky uživatele. Uživatel dostane jednu e-mailovou zprávu s oznámením, že mobilní zařízení je v karanténě. Tato zpráva se odešle do zařízení a do poštovní schránky uživatele. Pomocí úlohy **Nastavit oznámení uživatele** můžete do této zprávy přidat vlastní text a poskytnout tak pokyny uživatelům, kteří mají zařízení v karanténě.|

Strategie přístupu je tvořená kombinací nastavení **Výchozí pravidlo** a **Výjimky platforem**, která platí pro všechna mobilní zařízení připojená k Exchangi. Některé příklady strategií přístupu jsou uvedené v následující tabulce.

|Strategie přístupu|Popis|
|-------------------|---------------|
|Seznam povolených položek|Pomocí *seznamu povolených položek* můžete udělit přístup známým zařízením na seznamu a všem ostatním zařízením přístup zakázat. K tomu musíte vytvořit vlastní pravidla pro platformy zařízení, kterým je povolen přístup k poštovní schránce uživatele. Až takové pravidlo vytvoříte, musíte nastavit výchozí pravidlo přístupu, které všechna ostatní zařízení zablokuje nebo je dá do karantény. Nové zařízení můžete do seznamu povolených položek přidat vytvořením nového vlastního pravidla.|
|Seznam blokovaných položek|Pomocí *seznamu blokovaných položek* můžete ve výchozím nastavení udělit přístup všem zařízením a zablokovat přístup skupině zařízení, kterým v organizaci nechcete povolit přístup. Seznam blokovaných položek můžete vytvořit tak, že vytvoříte vlastní pravidla pro blokování platforem zařízení, které nechcete synchronizovat s poštovními schránkami organizace. Doporučujeme nastavit výchozí pravidlo tak, aby umožňovalo přístup všem zařízením, která nejsou výslovně blokovaná existujícími pravidly. Nové zařízení nebo skupinu zařízení můžete do seznamu blokovaných položek přidat tak, že vytvoříte nové vlastní pravidlo.|
|Kombinace seznamů povolených a blokovaných položek|Kromě vytvoření seznamu povolených a blokovaných položek můžete mobilní zařízení, která jsou v organizaci nová a zatím je vyhodnocujete, dát do karantény. Když třeba máte seznam blokovaných položek pro mobilní zařízení, která nejsou v organizaci povolená, a seznam povolených položek pro mobilní zařízení, které jsou v organizaci povolená, můžete nastavit ještě výchozí pravidlo pro karanténu. Všechna ostatní zařízení se automaticky umístí do karantény. To vám umožňuje zjistit nově zaváděná zařízení v organizaci a rozhodnout se, jestli je přidáte do seznamu povolených nebo zakázaných položek.|
Postup vytvoření vlastního pravidla je popsaný v následující části.

## <a name="create-a-default-access-rule"></a>Vytvoření výchozího pravidla přístupu

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Exchange ActiveSync**.

2.  V seznamu **Výchozí pravidlo** vyberte pravidlo přístupu, které chcete použít u všech mobilních zařízení, pro která neplatí pravidlo nebo osobní výjimka. Vyberte **Uložit**.

Následující postup popisuje vytvoření vlastního pravidla:

## <a name="create-a-custom-access-rule"></a>Vytvoření vlastního pravidla přístupu

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Exchange ActiveSync**.

2.  V seznamu **Výjimky platforem** vyberte **Přidat pravidlo** a potom vytvořte vlastní pravidlo. Vyberte **Uložit**.

