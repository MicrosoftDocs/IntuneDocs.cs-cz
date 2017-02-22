---
title: "Správa přenosu dat mezi aplikacemi pro iOS | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Toto téma vám pomůže pochopit, jak můžete použít funkci systému iOS Otevřít v a zásady správy mobilních aplikací ke správě přenosů dat mezi aplikacemi."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Správa přenosu dat mezi aplikacemi pro iOS 
## <a name="manage-ios-apps"></a>Správa aplikací pro iOS
V rámci ochrany vašich firemních dat je potřeba zajistit, aby přenosy souborů mohly probíhat jenom v aplikacích, které spravujete.  Aplikace pro iOS můžete spravovat těmito způsoby:

-   Firemní data můžete chránit před ztrátou tím, že pro aplikace nakonfigurujete zásady ochrany aplikací. Takovým aplikacím říkáme aplikace **spravované zásadami**.

-   Aplikace také můžete nasazovat a spravovat prostřednictvím **kanálu správy mobilních zařízení (MDM)**.  K tomu je potřeba, aby byla zařízení zaregistrovaná v nějakém řešení správy mobilních zařízení. Může se jednat o aplikace **spravované zásadami** nebo jiné spravované aplikace.

Funkce **Správa pro Open In** pro zařízení s iOSem může omezit přenosy souborů tak, aby probíhaly jenom mezi aplikacemi, které jsou nasazená prostřednictvím **kanálu MDM**. Omezení správy Open In se nastavují v nastavení konfigurace a nasazují pomocí řešení MDM.  Když uživatel nainstaluje nasazenou aplikaci, použijí se nastavená omezení.
##  <a name="using-app-protection-with-ios-apps"></a>Používání ochrany aplikací u aplikací pro iOS
Zásady ochrany aplikací se dají používat společně s funkcí **Správa Open In** k ochraně firemních dat těmito způsoby:

-   **Zařízení patřící zaměstnancům, která nejsou spravovaná řešením MDM:** Zásady ochrany aplikací můžete nastavit na **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Když koncový uživatel otevře chráněný soubor v aplikaci, která není spravovaná zásadami, soubor nejde přečíst.

-   **Zařízení spravovaná v Intune:** Pro zařízení zaregistrovaná v Intune jsou přenosy dat mezi aplikacemi se zásadami ochrany aplikací a ostatními spravovanými aplikacemi pro iOS nasazenými prostřednictvím Intune automaticky povolené. Pokud chcete povolit přenos mezi aplikacemi se zásadami ochrany aplikací, povolte nastavení **Povolit aplikaci přenos dat jenom do spravovaných aplikací**. Pomocí funkce **Správa Open In** můžete ovládat přenosy dat mezi aplikacemi nasazenými prostřednictvím Intune.   

-   **Zařízení spravovaná řešením MDM jiného výrobce:** Pomocí funkce **Správa Open In** můžete omezit přenosy dat jenom do spravovaných aplikací.
Pokud chcete zajistit, aby aplikace nasazené pomocí řešení MDM jiného výrobce byly také přidružené k zásadám ochrany aplikací, které jste nakonfigurovali v Intune, musíte nakonfigurovat nastavení hlavního názvu uživatele (UPN) podle postupu popsaného v části [Konfigurace nastavení hlavního názvu uživatele (UPN)](#configure-user-upn-setting).  Když je aplikace nasazená s nastavením hlavního názvu uživatele (UPN), použijí se pro ni zásady ochrany aplikací, jakmile se koncový uživatel přihlásí pomocí svého pracovního účtu.

> [!IMPORTANT]
> Nastavení hlavního názvu uživatele (UPN) se vyžaduje jenom pro aplikace nasazené na zařízení spravovaná řešením MDM jiného výrobce.  U zařízení spravovaných pomocí Intune se toto nastavení nevyžaduje.

## <a name="configure-user-upn-setting"></a>Konfigurace nastavení hlavního názvu uživatele (UPN)
Tato konfigurace je nutná pro zařízení spravovaná pomocí řešení MDM jiného výrobce. Níže popsaný postup představuje obecné kroky pro implementaci nastavení hlavního názvu uživatele (UPN) a výsledného prostředí koncového uživatele:


1.  Na portálu Azure [nakonfigurujte zásady správy mobilních aplikací](app-protection-policies.md) pro platformu iOS. Nakonfigurujte nastavení zásad podle požadavků vaší společnosti a vyberte aplikace, které by tyto zásady měly používat.

2.  K nasazení aplikací a e-mailového profilu, který chcete spravovat **prostřednictvím řešení MDM jiného výrobce**, použijte nastavení popsané v kroku 3 a 4.

3.  Nasaďte tyto aplikace s následujícím nastavením konfigurace aplikací: key=IntuneMAMUPN, Value=<username@company.com> [příklad: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Nasaďte zásadu správy Open In na zaregistrovaná zařízení.

### <a name="example-end-user-experience"></a>Ukázkové prostředí koncových uživatelů

1.  Koncový uživatel nainstaluje na zařízení aplikaci Microsoft Word.

2.  Koncový uživatel spustí spravovanou nativní e-mailovou aplikaci pro přístup do svého e-mailu.

3.  Koncový uživatel se pokusí otevřít dokument z nativní pošty v Microsoft Wordu.

4.  Při spuštění aplikace Word se koncovému uživateli zobrazí výzva k přihlášení pomocí pracovního účtu.  Tento pracovní účet by měl odpovídat účtu zadanému v konfiguračním nastavení aplikace Microsoft Word.

    > [!NOTE]
    > Koncový uživatel potom může do Wordu přidat další osobní účty, na které se zásady ochrany aplikací při použití aplikace Word pro soukromé účely nevztahují.

5.  Pokud je přihlášení úspěšné, použije se na aplikaci Word nastavení zásad aplikace.

6.  Přenos dat bude tentokrát úspěšný a dokument se v aplikaci označí firemní identitou. Kromě toho se data zpracovávají v pracovním kontextu a nastavení zásad jsou použitá odpovídajícím způsobem.

### <a name="see-also"></a>Související témata
[Co jsou zásady ochrany aplikací Intune](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


