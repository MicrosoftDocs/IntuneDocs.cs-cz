---
title: "Správa přenosu dat mezi aplikacemi pro iOS | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 002ebec14a089754849024916590b787431c7efe
ms.openlocfilehash: fce0081fc1ecb92acf539a2d69f0493fb30ee418


---

# Správa přenosu dat mezi aplikacemi pro iOS
## Správa aplikací pro iOS
V rámci ochrany vašich firemních dat je potřeba zajistit, aby přenosy souborů mohly probíhat jenom v aplikacích, které spravujete.  Aplikace pro iOS můžete spravovat těmito způsoby:

-   Data společnosti můžete chránit před ztrátou tím, že pro aplikace nakonfigurujete zásady správy mobilních aplikací. Takovým aplikacím říkáme aplikace **spravované zásadami**.

-   Aplikace také můžete nasazovat a spravovat prostřednictvím **kanálu správy mobilních zařízení (MDM)**.  K tomu je potřeba, aby byla zařízení zaregistrovaná v nějakém řešení správy mobilních zařízení. Může se jednat o aplikace **spravované zásadami** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOS může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. Omezení správy Open In se nastavují v nastavení konfigurace a nasazují pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, použijí se nastavená omezení.
##  Použití správy mobilních aplikací u aplikací pro iOS
Zásady správy mobilních aplikací (MAM) se dají použít společně s funkcí **Správa Open In** k ochraně firemních dat:

-   **Uživatelská zařízení nespravovaná řešením MDM:** Můžete nastavit nastavení zásad MAM na hodnotu **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Když koncový uživatel otevře chráněný soubor v aplikaci, která není spravovaná zásadami, soubor nejde přečíst.

-   **Zařízení spravovaná v Intune:** Pro zařízení zaregistrovaná v Intune jsou přenosy dat mezi aplikacemi se zásadami MAM a ostatními spravovanými aplikacemi pro iOS nasazenými prostřednictvím Intune automaticky povolené. Pokud chcete povolit přenos mezi aplikacemi se zásadami MAM, povolte nastavení **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune.   

-   **Zařízení spravovaná řešením MDM jiného výrobce:** Pomocí funkce **Správa Open In** můžete omezit přenosy dat jenom do spravovaných aplikací.
Pokud chcete zajistit, aby aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k zásadám MAM, které jste nakonfigurovali v Intune, musíte nakonfigurovat nastavení hlavního názvu uživatele (UPN) podle postupu popsaného v části [Konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting).  Když je aplikace nasazená s nastavením hlavního názvu (UPN) uživatele, použijí se na ni zásady MAM, jakmile se koncový uživatel přihlásí pomocí svého pracovního účtu.

> [!IMPORTANT]
> Nastavení hlavního názvu uživatele (UPN) se vyžaduje jenom pro aplikace nasazené na zařízení spravovaná řešením MDM jiného výrobce.  U zařízení spravovaných pomocí Intune se toto nastavení nevyžaduje.

## Konfigurace nastavení hlavního názvu uživatele (UPN)
Tato konfigurace je nutná pro zařízení spravovaná pomocí řešení MDM jiného výrobce. Níže popsaný postup představuje obecné kroky pro implementaci nastavení hlavního názvu uživatele (UPN) a výsledného prostředí koncového uživatele:


1.  Na portálu Azure [nakonfigurujte zásady správy mobilních aplikací](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace, které by tyto zásady měly používat.

2.  K nasazení aplikací a e-mailového profilu, který chcete spravovat **prostřednictvím řešení MDM jiného výrobce**, použijte nastavení popsané v kroku 3 a 4.

3.  Nasaďte tyto aplikace s následujícím nastavením konfigurace aplikací: key=IntuneMAMUPN, Value=<uživatelské_jméno@společnost.com> [příklad: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Nasaďte zásadu správy Open In na zaregistrovaná zařízení.

### Ukázkové prostředí koncových uživatelů

1.  Koncový uživatel nainstaluje na zařízení aplikaci Microsoft Word.

2.  Koncový uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup do svého e-mailu.

3.  Koncový uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4.  Při spuštění aplikace Word se koncovému uživateli zobrazí výzva k přihlášení pomocí pracovního účtu.  Tento pracovní účet by měl odpovídat účtu zadanému v konfiguračním nastavení aplikace Microsoft Word.

    > [!NOTE]
    > Koncový uživatel potom může do Wordu přidat další osobní účty, na které se zásady MAM při použití aplikace Word pro soukromé účely nevztahují.

5.  Pokud je přihlášení úspěšné, použije se na aplikaci Word nastavení zásad aplikace.

6.  Přenos dat bude tentokrát úspěšný a dokument se v aplikaci označí firemní identitou. Kromě toho se data zpracovávají v pracovním kontextu a nastavení zásad jsou použitá odpovídajícím způsobem.

### Související témata
[Ochrana aplikačních dat pomocí zásad správy mobilních aplikací v Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO2-->


