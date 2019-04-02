---
title: Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem
titleSuffix: Microsoft Intune
description: Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, když uživatelé spustí aplikaci v pracovním profilu Androidu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dccbfe597fa4bd461bb71cb86d38ffdfd52d719a
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799075"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení pro aplikace v pracovním profilu Androidu. K určení nastavení konfigurace pro aplikaci musí její vývojáři zpřístupnit nastavení konfigurace spravovaných aplikací pro Android. Přiřaďte zásady konfigurace aplikací skupině uživatelů, pro kterou chcete nastavení použít.  Nastavení zásad se použijí, když je aplikace zjistí (obvykle při prvním spuštění).

> [!Note]  
> Některé aplikace konfiguraci aplikací nepodporují. Zeptejte se vývojáře, jestli vaše aplikace zásady konfigurace aplikací podporuje.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Zvolte úlohu **Klientské aplikace**.
4. Ve skupině **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**: Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**: Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**: Zvolte **Spravovaná zařízení**.
6. V poli **Platforma** vyberte **Android**.
7. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásady konfigurace aplikací. Ze seznamu vyberte některou z aplikací v pracovním profilu Androidu, které jste schválili a synchronizovali s Intune.
8. Vyberte **Oprávnění**. K nastavení konfigurace můžete použít:
    - [Návrhář konfigurace](#use-the-configuration-designer)
    - [Editor JSON](#enter-the-json-editor)
9. Zvolte **OK** a pak **Přidat**.

## <a name="use-the-configuration-designer"></a>Použití návrháře konfigurace

Návrháře konfigurace můžete použít pro aplikace pro Android, když aplikace byly navržené pro podporu nastavení konfigurace. Konfigurace se uplatní na zařízeních, která jsou zaregistrovaná v Intune. Návrhář vám umožní nakonfigurovat konkrétní hodnoty konfigurace pro nastavení, která aplikace zpřístupňuje.

Volbou **Přidat** vyberte seznam nastavení konfigurace, která chcete pro aplikaci určit.  
Pro každý klíč a hodnotu v konfiguraci nastavte:

  - **Typ hodnoty**  
    Datový typ konfigurační hodnoty. U hodnot typu Řetězec můžete případně vybrat jako typ hodnoty proměnnou nebo profil certifikátu.
  - **Hodnota konfigurace**  
    Hodnota konfigurace Pokud vyberete jako typ hodnoty proměnnou nebo certifikát, můžete v rozevírací nabídce hodnot konfigurace vybírat ze seznamu proměnných profilů certifikátů.  Pokud zvolíte certifikát, vyplní se za běhu alias certifikátu nasazeného na zařízení.
    
### <a name="supported-variables-for-configuration-values"></a>Podporované proměnné u hodnot konfigurace

Pokud jako typ hodnoty zvolíte proměnnou, můžete vybírat z následujících možností:

| Možnost | Příklad |
|----|----|
| Mail | john@contoso.com |
| Hlavní název uživatele | john@contoso.com |
| Částečný hlavní název uživatele | Jan |
| Doména | contoso.com |
| Uživatelské jméno | John Doe |
| ID účtu | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| ID uživatele | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| ID zařízení | b9841cd9-9843-405f-be28-b2265c59ef97 |

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Povolte jenom nakonfigurované účty organizace v aplikacích s více identitami 

Pro zařízení s Androidem použijte následující dvojice klíč/hodnota:

| **Klíč** | com.microsoft.intune.mam.AllowedAccountUPNs |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Hodnoty** | <ul><li>Jeden nebo více hlavních názvů uživatele (UPN) oddělených <code>;</code>.</li><li>Jediné povolené účty jsou spravované uživatelské účty definované pomocí tohoto klíče.</li><li> Pro zařízení zaregistrovaná v Intune se může použít token <code>{{userprincipalname}}</code>, aby představoval účet zaregistrovaného uživatele.</li></ul> |

   > [!NOTE]
   > Musíte použít Outlook pro Android 2.2.222 nebo novější, když budete povolovat jenom nakonfigurované účty organizace s více identitami.<p></p>
   > Jako správce Microsoft Intune můžete řídit, které uživatelské účty se přidají do aplikací Microsoft Office na spravovaných zařízeních. Můžete omezit přístup jenom na povolené uživatelské účty organizace a zablokovat osobní účty na zaregistrovaných zařízeních. Podpůrné aplikace zpracují konfiguraci aplikace a odeberou a zablokují neschválené účty.<p></p>
   > Pro Microsoft Word, Microsoft Excel a Microsoft PowerPoint musíte použít verzi aplikace 16.0.9327.1000 a novější. 

## <a name="enter-the-json-editor"></a>Použití editoru JSON

Jiná nastavení konfigurace aplikací (například ta, která využívají typy sad) ale v návrháři zadávat nelze. Pro tyto hodnoty je potřeba použít editor JSON. Nastavení se aplikaci poskytne automaticky při její instalaci.

1. U položky **Formát nastavení konfigurace** zvolte možnost pro **otevření editoru JSON**.
2. V editoru můžete definovat hodnoty JSON pro nastavení konfigurace. Výběrem možnosti **Stáhnout šablonu JSON** stáhnete vzorový soubor, který můžete následně nakonfigurovat.
3. Zvolte **OK** a pak **Přidat**.

Zásady se vytvoří a zobrazí se v okně se seznamem zásad.

Když se přiřazená aplikace na zařízení spustí, použijí se nastavení, která jste nakonfigurovali v zásadách konfigurace aplikací.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Konfigurace stavu udělení oprávnění aplikacím

Předem nakonfigurovat můžete také oprávnění aplikací k přístupu k funkcím zařízení s Androidem. Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli. Pokud například aplikace používá mikrofon zařízení, zobrazí se uživateli výzva, aby aplikaci udělil oprávnění používat mikrofon.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Vyberte **Klientské aplikace**.
3. V části **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
4. Zadejte tyto podrobnosti:
    - **Název**. Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**. Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**: Vyberte **Spravovaná zařízení**.
    - **Platforma**: Vyberte **Android**.
5. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásadu konfigurace. Ze seznamu vyberte některou z aplikací v pracovním profilu Androidu, které jste schválili a synchronizovali s Intune.
6. Klikněte na **Oprávnění** a potom na **Přidat**.
7. Ze seznamu vyberte příslušné oprávnění aplikace a klikněte na **OK**.
8. U každého oprávnění vyberte způsob, jakým se bude v rámci této zásady udělovat:
    - **Zeptat se**: Vyzval uživatele ke schválení nebo zamítnutí
    - **Automaticky udělit**: Automaticky schválí bez upozornění uživatele.
    - **Automaticky odepřít**: Automaticky zamítne bez upozornění uživatele.
9. Přiřaďte zásadu konfigurace aplikace výběrem příslušné zásady, kliknutím na **Přiřazení** a potom na **Vybrat skupiny**.
10. Zvolte požadovanou skupinu uživatelů a potom klikněte na **Vybrat**.
11. Kliknutím na **Uložit** zásadu přiřaďte.

## <a name="next-steps"></a>Další postup

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace.

