---
title: "Obecné tipy pro odstraňování potíží | Microsoft Intune"
description: "Obecné informace pomáhající při řešení problémů s Intune"
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 3fe277417c82bc4d60f355ac5366f0f7d70039ab


---

# Obecné tipy pro odstraňování potíží v Microsoft Intune
Po nasazení Microsoft Intune můžete zjistit, že máte problémy s konfigurací nebo s klienty. Níže uvedené zdroje informací a materiály vám můžou pomoci zjistit, co by mohlo být příčinou problému, abyste ho mohli vyřešit.

> [!NOTE]
> Pokud chcete vytvořit žádost o podporu nebo pokud chcete zobrazit stávající požadavek, [přejděte do Centra pro správu Office 365](https://portal.office.com/admin/default.aspx). Další informace o možnostech podpory najdete v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
## Definování problému

-   O jaké chování jde?

-   Kdo toto chování zaznamenal a na jakých platformách a zařízeních?

-   Fungovalo zařízení dřív správně?

-   Jaké změny se provedly v Intune nebo v konfiguraci zařízení?

-   Zvažte, zda se neprovedly v provozním prostředí jiné změny než konfigurační.

-   Jak často k problému dochází a je výskyt občasný, nebo konzistentní?

-   Nemůže jít o problém s ověřováním uživatele? Pokud jde o reálnou možnost, zkontrolujte, jestli se uživatel může přihlásit k dalším službám, které používají Azure Active Directory. Zkontrolujte také, jestli se uživatel může přihlásit z jiného zařízení.

-   Zkontrolovali jste stav služby? Stav služby Intune je možné monitorovat na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx). Zvolte **Stav služby** v levém podokně.

## Shromažďování dostupných dat

-   Protokoly ze zařízení. Postup shromažďování protokolů ze zařízení:
  - [Odeslání protokolů s diagnostickými daty ze zařízení s Androidem správci IT pomocí kabelu USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Odeslání protokolů s diagnostickými daty ze zařízení s Androidem správci IT e-mailem](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Odeslání chyb registrace zařízení s Androidem správci IT](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Odeslání chyb registrace zařízení s iOS správci IT](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Data konzoly správce: Například při potížích s implementací zásad byste měli zkontrolovat požadované zásady a stav těchto zásad, jak se popisuje v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## Vyhledání řešení

-   Zkuste vyhledat řešení na webu. Když se třeba zobrazí chyba 0x80073CF0, můžete na webu vyhledat **technet intune 0x80073cf0** a najdete článek [Řešení problémů s nasazením aplikací v Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md), který nabízí návrhy pro vyřešení tohoto problému.

-   Odpověď můžete vyhledat ve [fóru Intune TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Pokud problém ještě nikdo neřešil, publikujte dotaz a počkejte, jestli se v komunitě neobjeví nějaké řešení.

-   Můžete otevřít žádost o podporu. Podpora Intune vám bude moct lépe pomoct s řešením potíží, když budete mít problém dobře definovaný a když shromáždíte všechna dostupná data.

    Pokud chcete vytvořit žádost o podporu, [přejděte do Centra pro správu Office 365](https://portal.office.com/admin/default.aspx). Další informace o možnostech podpory najdete v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## Zdroje informací a materiály z komunity
Další užitečné informace možná najdete v těchto zdrojích informací komunity:

-   [Průvodce pro přežití k Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) obsahuje odkazy na celou řadu zdrojů informací a materiálů, které vám mohou pomoci s konfigurací a údržbou Intune a řešením případných problémů s touto službou.

-   [Blog služby Intune](http://blogs.technet.com/b/windowsintune/)

-   [Sledování Intune na Twitteru](https://twitter.com/MSIntune)

-   [Fóra služby Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Další kroky
Témata uvedená níže obsahují nápovědu pro řešení specifických problémů. Pokud vám tyto informace nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Řešení problémů s přístupem k prostředkům společnosti ve službě Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Řešení problémů s nasazením aplikací v Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Řešení potíží s registrací do služby Intune](troubleshoot-device-enrollment-in-intune.md)

[Řešení potíží se zásadami v Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Řešení potíží s instalací klientů v Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Řešení potíží s aktualizacemi softwaru ve službě Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


