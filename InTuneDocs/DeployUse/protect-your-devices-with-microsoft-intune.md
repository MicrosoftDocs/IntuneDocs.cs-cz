---
title: "Ochrana zařízení | Microsoft Intune"
description: "Přečtěte si o některých způsobech, kterými vám Intune může pomoct chránit vaše zařízení před neoprávněným přístupem a dalšími hrozbami."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Ochrana zařízení pomocí Microsoft Intune
Jakmile budou vaše zařízení spravovaná pomocí Intune, budete chtít zajistit, aby byla chráněná před neoprávněným přístupem a dalšími hrozbami. Zde jsou některé schopnosti Intune, které pomáhají v dosažení těchto cílů.

> [!TIP]
> Toto téma neobsahuje všechny způsoby, jak může Intune pomoci se zabezpečením vašich zařízení. Například můžete použít zásady Intune ke konfiguraci mnoha nastavení zabezpečení pro svá zařízení, jako jsou nastavení hesel a šifrování nebo funkce hardwaru, jako například Bluetooth a kamera zařízení. Další informace o těchto nastaveních najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Resetování přístupových kódů v případě, že se uživatelé nemůžou přihlásit k zařízení
Prvním krokem při ochraně dat společnosti na mobilních zařízeních je vyžadování hesla pro použití zařízení. Někdy je nutné [Resetovat heslo](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) nebo s tím zaměstnanci pomoci odebráním hesla nebo nastavením dočasného hesla vzdáleně. Pokud dojde ke ztrátě nebo odcizení, můžete také [vzdáleně uzamknout zařízení](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

## Přidání další vrstvy ochrany do zařízení s Windows
[Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) představuje bezpečnější způsob ověřování uživatelů zařízení s Windows a Windows Phone v síti. Pokud se používá služba MFA, uživatelé musí potvrdit svou identitu ještě i jinak než jen pomocí svého uživatelského jména a hesla – prostřednictvím telefonního hovoru nebo SMS zprávy.

## Kontrola nastavení Microsoft Passportu v zařízeních s Windows
Intune se integruje se službou [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), což je alternativní přihlašovací metoda pro Windows 10 a novější. Microsoft Passport for Work využívá službu Active Directory nebo Azure Active Directory k nahrazení hesel, čipových karet i virtuálních čipových karet.

## Obejití zámku aktivace na zařízeních s iOS
Zámek aktivace je funkce, která pomáhá chránit zařízení uživatelů tím, že před vymazáním nebo opětovnou aktivací zařízení od uživatele požaduje zadání Apple ID a hesla. To však může vést k problémům, například když uživatel odejde ze společnosti, aniž by ze zařízení zámek odebral. Možnost [vyřazení zámku aktivace na zařízeních iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) vám pomůže s odebráním zámku ze spravovaných zařízení s iOS, abyste je mohli přidělit jinému uživateli nebo z nich vymazat obsah.

## Ochrana osobních počítačů s Windows pomocí klienta Intune
Intune i nadále podporuje zásady zabezpečení pro osobní počítače s Windows, které nejsou registrované, ale spravované pomocí počítačového klientského softwaru Intune. Chcete-li zjistit, jak vám tyto zásady mohou pomoci se zabezpečením osobních počítačů s Windows, přečtěte si téma [Použití zásad k ochraně osobních počítačů s Windows, na nichž běží klientský software Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Aug16_HO2-->


