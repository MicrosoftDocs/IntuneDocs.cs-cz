---
title: "Běžné úlohy správy počítačů s Windows | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 530bf3234001946776593ae0257ea72a06c8612f
ms.openlocfilehash: 222b9aac19993f184ff68800a00f8d9df8b36237


---

# Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune
Když si přečtete informace uvedené v tomto tématu, dozvíte se, jak spravovat počítače, na kterých běží klient Intune. Pokud jste ještě na svých počítačích klienta nenainstalovali, přečtěte si téma [Instalace klienta na počítači s Windows pomocí Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Použití zásad ke zjednodušení správy počítačů
### Správa brány Windows Firewall
Zásady zjednodušují správu nastavení brány Windows Firewall na spravovaných počítačích. Podrobné informace najdete v tématu [Pomoc při ochraně počítačů s Windows pomocí zásad brány Windows Firewall v Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Správa centra Microsoft Intune Center
Microsoft Intune Center uživatelům umožňuje:

-   Získávat aplikace z portálu společnosti

-   Kontrolovat aktualizace

-   Spravovat Microsoft Intune Endpoint Protection

<!--- -   Request remote assistance.--->

Microsoft Intune Center se nainstaluje na všech spravovaných počítačích. V zásadách Intune můžete nakonfigurovat následující nastavení, která se uživatelům zobrazí v centru Microsoft Intune Center:

|Nastavení zásad|Podrobnosti|
|------------------|--------------------|
|**Název**|Jméno správce, který spravuje příslušný počítač<br /><br />Maximální délka: 40 znaků|
|**Telefonní číslo**|Telefonní číslo správce, který spravuje příslušný počítač<br /><br />Maximální délka: 20 znaků|
|**E-mailová adresa**|Emailová adresa správce, který spravuje příslušný počítač<br /><br />Maximální délka: 40 znaků|
|**Název webu**|Název vašeho webu pro podporu uživatelů<br /><br />Maximální délka: 40 znaků|
|**Adresa URL webu**|Adresa URL vašeho webu podpory<br /><br />Maximální délka: 150 znaků|
|**Poznámky**|Poznámka, která se zobrazuje uživatelům<br /><br />Maximální délka: 120 znaků|

### Správa nastavení aktualizací softwaru
Pomocí zásad můžete nakonfigurovat nastavení, která budou spravované počítače používat k hledání a stahování aktualizací softwaru od Microsoftu i jiných výrobců. Další informace najdete v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Správa nastavení služby Endpoint Protection
Pomocí zásad můžete nakonfigurovat nastavení pro službu Endpoint Protection a potom je můžete nasadit na spravované počítače. Můžou to být třeba plány kontrol, akce, které se mají udělat v případě detekce malwaru, a další věci. Další informace najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Zobrazení inventáře hardwaru a softwaru
Intune shromažďuje podrobné informace o hardwaru a softwaru spravovaných počítačů. V následujících postupech se dozvíte toto:

-   Jak vytvořit sestavu s informacemi o hardwarových možnostech vašich počítačů

-   Jak vytvořit sestavu se seznamem softwaru nainstalovaného na jednotlivých počítačích

-   Jak aktualizovat inventář počítačů, abyste měli jistotu, že jsou data v sestavě aktuální

### Zobrazení informací o počítačích

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Sestavy** &gt; **Sestavy inventáře počítače**.

2.  Na stránce **Vytvořit novou sestavu** přijměte výchozí hodnoty, případně je upravte, aby se vyfiltrovaly výsledky, které bude sestava obsahovat. Můžete třeba vybrat, aby se v sestavě zobrazily jenom počítače, na kterých běží Windows 8.1.

3.  Kliknutím na **Zobrazit sestavu** otevřete **sestavu inventáře počítače** v novém okně.

    Když vyberete záhlaví příslušných sloupců, jako je třeba **Název**, **Typ skříně** nebo **Výrobce**, můžete sestavu podle těchto sloupců seřadit.

### Zobrazení softwaru nainstalovaného na počítačích

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Sestavy** &gt; **Zjištěné zprávy o softwaru**.

2.  Na stránce **Vytvořit novou sestavu** přijměte výchozí hodnoty, případně je upravte, aby se vyfiltrovaly výsledky, které bude sestava obsahovat. Můžete třeba vybrat, aby se v sestavě zobrazil jenom software publikovaný Microsoftem.

3.  Zvolte **Zobrazit sestavu**. **Sestav rozpoznaného softwaru** se otevře v novém okně.

    Když vyberete záhlaví příslušných sloupců, jako je třeba **Název**, **Vydavatel** nebo **Kategorie** , můžete sestavu podle těchto sloupců seřadit. Zvolením směrové šipky vedle položky seznamu můžete aktualizace v seznamu rozbalit a zobrazit tak další podrobnosti (třeba počítače, na kterých jsou nainstalované).

### Aktualizace inventáře počítače, abyste měli jistotu, že je aktuální

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, pro který chcete inventář aktualizovat).

2.  Vyberte počítač. Nebo když stisknete a podržíte **Ctrl** , můžete vybrat víc počítačů.

3.  Na hlavním panelu zvolte **Vzdálené úlohy** &gt; **Obnovit inventář**.

4.  Pokud chcete zobrazit stav úlohy, v pravém dolním rohu stránky zvolte **Vzdálené úlohy**.

    V dialogovém okně **Stav úlohy** se zobrazí aktuální vzdálené úlohy, stav úloh, název zařízení, všechny hlášené chyby a odkaz na informace o odstraňování problémů.


## Vzdálené restartování počítače s Windows

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, který chcete restartovat).

2.  Vyberte jeden nebo víc počítačů a potom zvolte **Vzdálené úlohy** &gt; **Restartovat počítač**.

3.  Pokud chcete zobrazit stav úlohy, v pravém dolním rohu stránky zvolte **Vzdálené úlohy**.

4.  V dialogovém okně **Stav úlohy** se můžete podívat na aktuální vzdálené úlohy, stav úloh, název zařízení a všechny hlášené chyby.

## Vyřazení počítače

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, který chcete vyřadit).

2.  Vyberte zařízení, která chcete vyřadit, a potom zvolte **Vyřadit z provozu či vymazat**.

Když budete chtít počítač do služby Intune znovu zaregistrovat, přeinstalujte na počítači klientský software, a to podle informací uvedených v tématu [Instalace klienta na počítači s Windows pomocí Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Když se nějaký počítač nemůže k Intune připojit, v pracovním prostoru **Řídicí panel** se zobrazí zpráva.

Při vyřazení počítače s stane toto:

-   Počítač se odebere z inventáře Intune a licence, které jsou k němu přiřazené, se uvolní pro nové použití.

-   Jeho stav se už nebude zobrazovat v konzole Intune.

-   Intune odebere z počítače klientský software. Pokud počítač není ke službě Intune připojený, klientský software se odebere, až se počítač zase připojí.

-   Z počítače se odebere Microsoft Intune Endpoint Protection. Pokud je na počítači nainstalovaná jiná aplikace ochrany koncových bodů a je zakázaná, může se tato aplikace po odebrání služby Intune zase povolit, aby se zajistila ochrana vašich počítačů.

-   Z počítače se odeberou všechny zásady a změní se hodnoty nastavené těmito zásadami.

-   Počítač už nebude od služby Intune dostávat aktualizace softwaru ani aktualizace definic malwaru.

-   Podle toho, jak jsou vyřazené počítače nakonfigurované, můžou dál dostávat aktualizace pomocí služeb Windows Server Update Services, Windows Update nebo Microsoft Update.

    > [!IMPORTANT]
    > Když byl klientský software nainstalován pomocí objektu zásad skupiny, musíte tento objekt před odebráním klientského softwaru odebrat, abyste zabránili přeinstalaci softwaru.

    Pokud se odinstalace klienta nepovede, najdete další pomoc v tématu [Řešení potíží se službou Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

## Správa propojení zařízení s uživatelem
Abyste mohli nasadit software pro uživatele, musíte uživatele propojit s počítačem. Uživatele můžete propojit s několika počítači, ale každý počítač může být propojený jenom s jedním uživatelem. Uživatelé jsou automaticky propojení se všemi počítači, které si přes portál společnosti zaregistrovali v Intune.

### Propojení uživatele s počítačem

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, který chcete propojit s uživatelem).

2.  Vyberte počítač, který chcete propojit s uživatelem, a potom zvolte **Propojit uživatele**.

    V dialogovém okně **Propojit uživatele** se zobrazí seznam dostupných uživatelů včetně jejich zobrazovaného jména, ID a počtu počítačů, se kterými jsou aktuálně propojení. Pokud je s vybraným počítačem už nějaký uživatel propojený, je v části **Aktuální uživatel**zobrazené jeho jméno a ID. Když počítač není propojený s žádným uživatelem, tak se v části **Aktuální uživatel** zobrazuje **Žádný uživatel**.

3.  Udělejte jednu z těchto věcí:

    -   Pokud chcete nechat počítač propojený s aktuálním uživatelem, klikněte na **Zrušit**.

    -   Pokud chcete propojení s aktuálním uživatelem odebrat, zvolte **Odebrat odkaz **&gt; **OK**.

    -   Pokud chcete propojit počítač s novým uživatelem, vyberte uživatele v seznamu **Všichni uživatelé** . Potvrďte správnost údajů o uživateli a potom zvolte **OK**.

> [!TIP]
> Když chcete koncovým uživatelům omezit schopnosti propojení vlastních účtů s počítači, povolte možnost **Omezit schopnosti uživatelů propojit s počítači vlastní účet** v zásadách **Nastavení agenta Microsoft Intune**.

<!--- ## Request and provide remote assistance to Windows PCs that use the Intune client software

> [!IMPORTANT]
> You might not see the options to configure TeamViewer integration for remote assistance in the Intune admin console. This capability is not currently available to all customers, but will be rolling our more widely soon.
     

Microsoft Intune can use the [TeamViewer](https://www.teamviewer.com) software to let users of PCs that run the Intune client software get remote assistance help from you. When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.
This functionality replaces the existing Windows Remote Assistance functionality in Intune.


### Before you start

Before you can begin to establish and respond to remote assistance requests, you must ensure the following prerequisites are in place:

- You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log into the TeamViewer website.
- Windows PCs that you want to administer must be [managed by the Windows PC client](manage-windows-pcs-with-microsoft-intune.md)
- All Windows PC operating systems supported by Intune can be administered.

### Configure the TeamViewer Connector

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.
2. In the **Admin** workspace, choose **TeamViewer**.
3. On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.
4. In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms. If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.
5. After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.
6. On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.
7. In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.


### Open a remote assistance request (end user)

1. On a client Windows PC, open the **Microsoft Intune Center**.
2. Under **Remote Assistance**, choose **Request Remote Assistance**.
3. After you approve the request (see below), TeamViewer opens on the client. The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.
4. The user sees a message asking if you can control their PC. They must accept this message to continue.
5. During the remote assistance session, the user sees a window that shows them you are connected. If they close this window, the remote session ends.

### Respond to a remote assistance request

1. When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**. For example:
> ![Screenshot of a remote assistance request](./media/team-viewer.png)

<br>If a request goes unanswered for more than 4 hours, it is removed.
2. To accept the request, choose **Approve request and launch Remote Assistance**.
3. In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**. If it's not already installed, TeamViewer will install any necessary apps on your computer.
4. TeamViewer then notifies the end user that you want to take control of their PC. After the user has accepted the request, the TeamViewer windows opens, and you can control the PC. 
 
While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC. For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.

### Close the remote assistance session

From the **Actions** menu of the **TeamViewer** window, choose **End Session**.--->


<!--HONumber=Jun16_HO4-->


