---
title: Registrace zařízení s macOS v Intune pomocí Portálu společnosti | Dokumentace Microsoftu
description: Popisuje postup registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti.
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: af5c7492563c8df0168eff3250ae1bbad2cc323e
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/29/2018
ms.locfileid: "43147713"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti

Zaregistrujte si zařízení s macOS pomocí aplikace Portál společnosti v Intune a získejte zabezpečený přístup k e-mailům, souborům a aplikacím vaší organizace.

Organizace někdy požadují, abyste si ještě před získáním přístupu k jejich vlastnickým datům nechali své zařízení spravovat. Jakmile je zařízení spravované, mohou do něj prostřednictvím poskytovatele správy mobilních zařízení odesílat zásady a aplikace. Pokud chcete na zařízení získat nepřetržitý přístup k pracovním nebo školním datům, je nutné nakonfigurovat je tak, aby odpovídalo nastavení zásad.  

V tomto článku se dozvíte, jak vám může aplikace Portál společnosti Intune pro macOS pomoci při registraci, konfiguraci a údržbě zařízení, které má splňovat požadavky organizace.

## <a name="what-to-expect-from-the-company-portal-app"></a>Co čekat od aplikace Portál společnosti

Při počátečním nastavení vás aplikace požádá, abyste se ve vaší organizaci ověřili. Potom vás informuje o všech nastaveních, která musíte provést. Organizace si například často určují požadavky na minimální a maximální délku hesla, které musíte splnit.    

Po registraci zařízení bude aplikace Portál společnosti i nadále kontrolovat, že je chráněno. Pokud si například nainstalujete aplikaci z nedůvěryhodného zdroje, upozorní vás a dokonce vám může i odvolat přístup k firemním datům. Zásady ochrany aplikací, jako je tato, jsou v organizacích běžné. Často je tak potřeba nedůvěryhodnou aplikaci odinstalovat, abyste přístup získali zpět.

Pokud po registraci vaše organizace vynucuje nový požadavek na zabezpečení (například vícefaktorové ověřování), aplikace Portál společnosti vás o něm informuje. Budete tak mít možnost si nastavení upravit, abyste se zařízením mohli dále pracovat.  

Další informace o registraci najdete v tématu s informacemi o tom, [co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-device-managed"></a>Nastavení spravovaného zařízení  
V této části najdete postup registrace zařízení s macOS verze OS X El Capitan 10.11 a novějšími.   


1. Přejděte na web Portál společnosti otevřením nového okna v aplikaci __Safari__ a potom přejděte na https://portal.manage.microsoft.com.  

2. Přihlaste se na web Portál společnosti přes svůj pracovní nebo školní účet.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Přejděte do levého horního rohu stránky a klikněte na **nabídku** > **Zařízení**.  

4. Na stránce __Zařízení__ se zobrazí buď seznam spravovaných zařízení, nebo banner. Tato možnost závisí na tom, jestli už spravované zařízení máte, nebo nikoliv. 
    * Pokud chcete přidat zařízení, které není v seznamu, vyberte banner s textem **Klepněte sem a řekněte nám, které zařízení používáte, nebo přidejte nové.**
    * Pokud žádné zařízení nemáte, zobrazí se text **Nemáte žádná spravovaná zařízení. Toto zařízení můžete přidat tak, že klepnete sem.** Přidejte zařízení kliknutím na banner.  

     ![Snímek obrazovky se stránkou Zařízení s červeným obdélníkem okolo banneru, který zvýrazňuje možnost, na niž má uživatel kliknout](./media/CP-enroll-MACOS-1808.png)  
5.  Proveďte jeden z kroků níže podle toho, která zpráva se vám na Portálu společnosti zobrazuje.  
    * Pokud přidáváte zařízení poprvé, vyzve vás stránka ke stažení aplikace Portál společnosti do zařízení. Pokračujte kliknutím na **Stáhnout**.  

         ![Ukázkový snímek obrazovky s výzvou ke stažení aplikace Portál společnosti pro macOS. Uživatel může kliknout na modré tlačítko Stáhnout v levé dolní části, nebo na šedé tlačítko Zrušit v pravé dolní části.](./media/CP-enroll-download-macOS-1808.png)  

    * Pokud už máte spravované zařízení s macOS, zobrazí se výzva se seznamem aktuálně spravovaných zařízení. Vyberte možnost **Moje zařízení tady není uvedené** > **Stáhnout** a stáhněte si aplikaci Portál společnosti na zařízení, které přidáváte.  

         ![Ukázkový snímek obrazovky s výzvou ke stažení aplikace Portál společnosti pro macOS. Uživatel může zvolit možnost „Moje zařízení tady není uvedené“, nebo konkrétní zařízení ze středu stránky. Modré tlačítko Stáhnout se zobrazuje v levé dolní části výzvy a šedé tlačítko Zrušit v pravé dolní části.](./media/cp-mac-os-device-isnt-here-1808.png)  

6. Vaše zařízení ověří, že instalační soubor **CompanyPortal.pkg** můžete bezpečně otevřít. Po dokončení otevřete instalační program a dokončete instalaci.  

7. Po ukončení instalačního programu přejděte na **Launchpad** a otevřete **Portál společnosti**.  

8. Zařízení s macOS vás vyzve k potvrzení, že chcete otevřít aplikaci Portál společnosti. Klikněte na **Otevřít**.  

   > [!TIP]
   > Intune potřebuje přístup k počítači pro ověření, že je vaše zařízení natolik bezpečné, že může mít přístup k prostředkům ve vaší organizaci. Pokud váš počítač odmítá aplikaci Portál společnosti otevřít, [vypněte Gatekeeper](https://support.apple.com/HT202491). Potom aplikaci otevřete.

9. První stránka, která se v aplikaci Portál společnosti zobrazí, vás vyzve k **přihlášení**. Přihlaste se stejným pracovním nebo školním účtem, jako jste použili k přihlášení na web Portál společnosti.

10. Portál společnosti potvrdí informace o vašem účtu a zobrazí stav **registrace zařízení** a **dodržování předpisů zařízením**. Žlutými trojúhelníky jsou zvýrazněny akce, které je potřeba provést k zabezpečení zařízení s macOS pro školní nebo pracovní účely. Kliknutím na **Začít** spusťte registraci. Přečtěte si, [jaké informace vaše organizace uvidí](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md), když si zaregistrujete zařízení.

11. Může se stát, že vás stránka vyzve k zadání přihlašovacích údajů počítače. Registrace zařízení do správy také může trvat několik minut. Během toho ale můžete se zařízením pracovat. Jakmile se dokončí nastavení přístupu společnosti, zobrazí se zpráva, že je vše hotovo.  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
