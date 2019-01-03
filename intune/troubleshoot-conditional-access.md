---
title: Řešení potíží s podmíněným přístupem | Microsoft Intune
description: Popisuje, co dělat, pokud se vašim uživatelům nedaří získat přístup k prostředkům prostřednictvím podmíněného přístupu Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d24b96408ed02413f25957e2558704385c5e1bfd
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817139"
---
# <a name="troubleshoot-conditional-access"></a>Řešení potíží s podmíněným přístupem

Pomocí Intune a podmíněného přístupu můžete chránit přístup ke službám Office 365, jako jsou Exchange Online, SharePoint Online, Online Skype pro firmy, místní Exchange, a k dalším službám. Tato funkce umožňuje zajistit, aby se přístup k podnikovým prostředkům omezil na zařízení zaregistrovaná v Intune a vyhovující pravidlům podmíněného přístupu, která jste nastavili v konzole správce Intune nebo v Azure Active Directory. Tento článek popisuje, jak postupovat, když se vašim uživatelům nedaří získat přístup k prostředkům, které jsou chráněné pomocí podmíněného přístupu, nebo když uživatelé mají přístup k chráněným prostředkům, ale měli by být blokovaní.

## <a name="requirements-for-conditional-access"></a>Požadavky pro podmíněný přístup

Aby podmíněný přístup fungoval, musí být splněné následující požadavky:

- Zařízení musí být zaregistrované a spravované pomocí Intune.
- Uživatel i zařízení musí vyhovovat přiřazeným zásadám dodržování předpisů Intune.
- Uživateli se standardně musí přiřadit zásady dodržování předpisů pro zařízení. To může záviset na konfiguraci nastavení **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** v části **Dodržování předpisů zařízením** > **Nastavení zásad dodržování předpisů** na portálu pro správu Intune.
-   Pokud uživatel nepoužívá Outlook, ale nativního poštovního klienta daného zařízení, musí být v zařízení aktivovaný protokol Exchange ActiveSync. V zařízeních se systémy iOS, Windows Phone a Android se to provede automaticky.
-   Intune Exchange Connector musí být správně nakonfigurovaný. Další informace najdete v tématu [Odstraňování potíží Exchange Connectoru v Microsoft Intune](troubleshoot-exchange-connector.md).

Tyto podmínky si můžete prohlédnout u každého zařízení na webu Azure Portal a v inventární sestavě zařízení.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Zařízení se zobrazují jako kompatibilní, ale uživatelé jsou přesto blokovaní

- Zařízením s Androidem, která nepoužívají Knox, nebude udělen přístup, dokud uživatel v přijatém e-mailu o karanténě neklikne na odkaz **Get Started Now** (Začít teď). To platí i v případě, že uživatel je už zaregistrovaný v Intune. Pokud uživatel nedostane e-mail s odkazem na svůj telefon, může pro přístup k e-mailu použít počítač a pak tento e-mail přeposlat na e-mailový účet na svém zařízení.
- Když se zařízení registruje poprvé, může registrace jeho informací o dodržování předpisů trvat nějakou dobu. Počkejte několik minut a zkuste akci zopakovat.
- U zařízení s iOSem může stávající e-mailový profil blokovat nasazení e-mailového profilu vytvořeného správcem Intune, který byl přiřazen tomuto uživateli, a proto dané zařízení bude nekompatibilní. V tomto scénáři aplikace Portál společnosti upozorní uživatele na nekompatibilitu z důvodu ručně nakonfigurovaného e-mailového profilu a vyzve ho k odebrání tohoto profilu. Jakmile uživatel stávající e-mailový profil odebere, e-mailový profil Intune se úspěšně nasadí. Pokud chcete tomuto problému zabránit, upozorněte uživatele, aby na svém zařízení před registrací odebrali všechny stávající e-mailové profily.
- Zařízení můžou uváznout ve stavu kontroly dodržování předpisů a bránit uživateli v inicializaci jiné kontroly. Pokud máte zařízení v tomto stavu, zkuste použít následující postup:
  - Ujistěte se, že zařízení používá nejnovější verzi aplikace Portál společnosti.
  - Restartujte zařízení.
  - Zjistěte, jestli tento problém přetrvává v různých sítích (například mobilní, Wi-Fi atd.).

  Pokud problém trvá, kontaktujte podporu Microsoftu podle pokynů v tématu o [získání podpory pro Microsoft Intune](get-support.md).
- Některá zařízení s Androidem můžou působit jako zašifrovaná, ale aplikace Portál společnosti tato zařízení rozpozná jako nezašifrovaná, a proto budou nekompatibilní. V tomto scénáři se uživateli zobrazí oznámení aplikace Portál společnosti s výzvou k nastavení hesla pro spuštění zařízení. Po klepnutí na oznámení a potvrzení stávajícího PIN kódu nebo hesla zvolte na obrazovce **Zabezpečené spuštění** možnost **Ke spuštění zařízení vyžadovat PIN kód** a pak v aplikaci Portál společnosti klepněte na tlačítko **Zkontrolovat dodržování předpisů** pro toto zařízení. Zařízení by se teď mělo rozpoznat jako zašifrované. 
  > [!NOTE]
  > Někteří výrobci zařízení používají k zašifrování svých zařízení místo PIN kódu nastaveného uživatelem výchozí PIN. Intune považuje zašifrování pomocí výchozího PIN kódu jako nezabezpečené, a dokud uživatel nevytvoří nový PIN, který není výchozí, označuje taková zařízení jako nedodržující předpisy.
- Zařízení s Androidem, které je zaregistrované a vyhovující, se může i přesto zablokovat a při prvním pokusu o přístup k podnikovým prostředkům obdržet oznámení o karanténě. Pokud k tomu dojde, ujistěte se, že aplikace Portál společnosti není spuštěná, a pak kliknutím na odkaz **Get Started Now** (Začít teď) v e-mailu o karanténě aktivujte vyhodnocení. Toto by mělo být potřeba udělat jenom při prvním povolení podmíněného přístupu.

## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Zařízení jsou blokovaná, ale žádný e-mail o karanténě nepřišel

- Ověřte, jestli se dané zařízení nachází v konzole pro správu Intune jako zařízení Exchange ActiveSync. Pokud ne, je pravděpodobné, že zjišťování tohoto zařízení bylo neúspěšné, zřejmě kvůli problému Exchange Connectoru. Další informace najdete v tématu [Řešení potíží s místním Intune Exchange Connectorem](troubleshoot-exchange-connector.md).
- Než Exchange Connector začne blokovat zařízení, odešle aktivační e-mail (e-mail o karanténě). Pokud je zařízení offline, nemusí aktivační e-mail obdržet. 
- Zkontrolujte, jestli je e-mailový klient na zařízení nakonfigurovaný tak, aby načítal e-maily pomocí metody **Push**, a ne **Poll**. Pokud ano, může to být příčina toho, že uživatel nedostal příslušný e-mail. Přepněte na **Poll** a zkontrolujte, jestli zařízení obdrží e-mail.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Zařízení nedodržují předpisy, ale uživatelé nejsou blokovaní

- Na počítačích s Windows blokuje podmíněný přístup jenom nativní e-mailovou aplikaci, Office 2013 s moderním ověřováním nebo Office 2016. Blokování dřívějších verzí Outlooku a všech e-mailových aplikací na počítačích s Windows vyžaduje konfiguraci registrace zařízení AAD a konfiguraci AD FS (Active Directory Federation Services), jak je uvedeno v tématu [Nastavení SharePointu Online a Exchange Online pro podmíněný přístup Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication). 
- Pokud se zařízení z Intune selektivně vymaže nebo vyřadí, může mu několik hodin po vyřazení nadále zůstat možnost přístupu. Důvodem je skutečnost, že Exchange ukládá přístupová práva do mezipaměti na 6 hodin. Zvažte možnost použití jiných způsobů ochrany dat na vyřazených zařízení v tomto scénáři.
- Zařízení Surface Hub podporují podmíněný přístup. Pro správné vyhodnocení je však nutné nasadit zásady dodržování předpisů pro skupiny zařízení (ne pro skupiny uživatelů).
- Zkontrolujte přiřazení zásad dodržování předpisů a zásad podmíněného přístupu. Pokud není uživatel členem skupiny, pro kterou jsou přiřazené zásady, nebo je členem vylučované skupiny, nebude daný uživatel blokovaný. Dodržování předpisů se kontroluje jenom u zařízení uživatelů, kteří jsou v přiřazené skupině.

## <a name="noncompliant-device-is-not-blocked"></a>Zařízení nevyhovující předpisům není blokované

Pokud narazíte na zařízení, které nevyhovuje předpisům, ale má nadále přístup, proveďte následující kroky.
- Zkontrolujte cílovou skupinu a skupinu pro vyloučení. Pokud uživatel není ve správné cílové skupině nebo je ve skupině pro vyloučení, nebude blokován. Vyhovování předpisům se kontroluje jenom u zařízení uživatelů, kteří jsou v cílové skupině.
- Zkontrolujte, že se zařízení zjišťuje. Směřuje Exchange Connector na CAS pro Exchange 2010, zatímco je uživatel na serveru Exchange 2013? V takovém případě pokud je výchozí pravidlo Exchange nastavené na povolení, i když je uživatel v cílové skupině, Intune nemůže vědět o připojení zařízení k Exchangi.
- Kontrola stavu existence a přístupu k zařízení v Exchangi:
  - Chcete-li získat seznam všech mobilních zařízení pro poštovní schránku, použijte tuto rutinu Powershellu: "Get-ActiveSyncDeviceStatistics-mailbox mbx". Pokud zařízení není v seznamu, nepřistupuje k Exchangi.
  - Pokud zařízení je uvedené, pomocí rutiny Get-CASmailbox -identity:’upn’ | fl získejte podrobné informace o jeho stavu přístupu a předejte tyto informace podpoře Microsoftu.

## <a name="next-steps"></a>Další postup
Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).
