---
title: "Ochrana zařízení | Microsoft Intune"
description: 
keywords: 
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c52448ab454a764be922319fb930a85a86c3996e
ms.openlocfilehash: c8f833593e6a4606b0dd56373d4dc016c7ea0924


---

# Ochrana zařízení pomocí Microsoft Intune
Jakmile jsou vaše zařízení spravovaná pomocí Intune, budete chtít zajistit, aby byla chráněná před neoprávněným přístupem a dalšími hrozbami. Zde jsou některé schopnosti Intune, které pomáhají v dosažení těchto cílů.

> [!TIP]
> Toto téma neobsahuje všechny způsoby, jak může Intune pomoci se zabezpečením vašich zařízení. Například můžete použít zásady Intune ke konfiguraci mnoha nastavení zabezpečení pro svá zařízení, jako jsou konfigurace hesel, nastavení šifrování a funkce hardwaru, jako například Bluetooth a kamera zařízení. Další informace o těchto nastaveních najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Resetování přístupových kódů v případě, že se uživatelé nemůžou přihlásit k zařízení
Vzhledem k tomu, že prvním krokem při ochraně dat společnosti na mobilních zařízeních je vyžadování hesla pro použití zařízení, je někdy nutné [Resetovat heslo](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) nebo s tím zaměstnanci pomoci odebráním hesla nebo nastavením dočasného hesla vzdáleně. Pokud dojde ke ztrátě nebo odcizení, můžete také [vzdáleně uzamknout zařízení](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

## Přidání další vrstvy ochrany do zařízení s Windows
[Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) představuje bezpečnější způsob ověřování uživatelů zařízení s Windows a Windows Phone v síti.  Pokud se používá tato služba, uživatelé musí potvrdit svou identitu ještě i jinak než jen pomocí svého uživatelského jména a hesla – prostřednictvím telefonního hovoru nebo SMS zprávy.

## Kontrola nastavení Microsoft Passportu v zařízeních s Windows
Intune umožňuje integraci se službou [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Tato alternativní metoda pro přihlašování do systému Windows 10 a novějších pomocí účtu služby Active Directory nebo Azure Active Directory nahrazuje heslo, čipovou kartu nebo virtuální čipovou kartu.

## Obejití zámku aktivace na zařízeních s iOS
Zámek aktivace je funkce, která pomáhá chránit zařízení uživatelů tím, že před vymazáním nebo opětovnou aktivací zařízení od uživatele požaduje zadání Apple ID a hesla. To však může vést k problémům (například pokud uživatel odejde ze společnosti, aniž by ze zařízení zámek odebral). Možnost [obejít zámek aktivace na zařízeních s iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) může pomoct odebrat zámek ze zařízení s iOS, která jsou pod dohledem, abyste je mohli přidělit jinému uživateli nebo z nich vymazat obsah.

## Ochrana osobních počítačů s Windows pomocí klienta Intune
Intune i nadále podporuje zásady zabezpečení pro osobní počítače s Windows, které nejsou registrované, ale spravované pomocí počítačového klientského softwaru Intune. Chcete-li zjistit, jak vám tyto zásady mohou pomoci se zabezpečením osobních počítačů s Windows, přečtěte si téma [Použití zásad k ochraně osobních počítačů s Windows, na nichž běží klientský software Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jun16_HO4-->


