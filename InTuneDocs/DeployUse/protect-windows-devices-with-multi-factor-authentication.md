---
title: "Vícefaktorového ověřování pro Windows | Microsoft Intune"
description: "Intune integruje vícefaktorové ověřování (MFA) a pomáhá vám zabezpečit prostředky společnosti."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: 00d63fa55cd29c938dd082e2eff240f08319e01a


---

# Protect Windows devices with multi-factor authentication
Microsoft Intune integruje vícefaktorové ověřování (MFA) a pomáhá vám zabezpečit prostředky společnosti. MFA vyžaduje kromě uživatelských jmen a hesel také faktory ověřování, jako je ověřování textu. Intune podporuje použití MFA během registrace zařízení s Windows 8.1 nebo novějším, Windows Phone 8.1 nebo Windows 10 Desktop a Mobile.

## Požadavky místní infrastruktury na ADFS MFA
Pro nastavení vícefaktorového ověřování potřebujete:

-   Automatickou registraci, jak je popsáno v článku [Nastavení správy pro zařízení Windows](set-up-windows-device-management-with-microsoft-intune.md).
-   **Doménu služby Active Directory, ke které je připojený server ADFS.**

-   **Server služby Active Directory Federation Services (ADFS) nakonfigurovaný pro MFA.** Server se systémem Windows Server 2012 R2 nastavený jako server ADFS. Další informace najdete v tématu [Zabezpečení cloudových a místních prostředků pomocí Azure Multi-Factor Authentication Serveru s Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Servery musí splňovat požadavky na systém, které najdete v článku [Požadavky na systém a informace o instalaci pro Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

 


#### MFA s Intune
Pokud má vaše organizace místní infrastrukturu IT, která zahrnuje doménu Active Directory se službou Active Directory Federation Services (ADFS), můžete nakonfigurovat MFA na federačním serveru a potom povolit MFA pro registraci v Intune. Konfigurací MFA v Intune umožníte uživatelům po jednom ověření během registrace přístup k prostředkům společnosti bez nutnosti vždy opakovat proces MFA.

>[!NOTE]
>Vícefaktorové ověřování může být na serveru ADFS vyžadované po jednotlivých uživatelích nebo skupinách.  

#### MFA bez Intune
Pokud vícefaktorové ověřování nakonfigurujete na federačním serveru, ale nepovolíte ho pro registraci ve službě Intune, budou uživatelé muset použít vícefaktorové ověřování při každém přístupu k prostředkům společnosti (nikoli pouze při registraci zařízení).

Vícefaktorové ověřování služby Azure Active Directory (Azure AD) můžete také nastavit tak, aby se vyžadovalo pro jednotlivé uživatele při každém přístupu k firemním prostředkům. Azure AD MFA je cloudová služba, která nevyžaduje žádnou místní infrastrukturu IT. Informace o nastavení vícefaktorového ověřování pro službu Azure AD najdete v tématu [Začínáme se službou Azure Multi-Factor Authentication v cloudu](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Vyžadování vícefaktorového ověřování služby ADFS při registraci zařízení se systémem Windows
Informace o tom, jak zapnout MFA v ADFS najdete v tématu [Přehled řízení rizik pomocí dodatečného vícefaktorového ověřování citlivých aplikací](http://technet.microsoft.com/library/dn280949.aspx).

## Nastavení MFA při registraci zařízení v Intune
>[!Important]  
>Než budete vícefaktorové ověřování vyžadovat pro registraci zařízení s Windows do služby Intune, povolte vícefaktorové ověřování v klientovi služby Azure AD nebo místním prostředí. Pokud to neuděláte, uživatelé obdrží při pokusu o registraci svých zařízení s Windows nebo při pokusu o připojení svých zařízení ke službě Azure AD, pokud je nakonfigurovaná automatická registrace během připojení ke službě Azure AD, chybovou zprávu.

1.  V konzole pro správu Intune zvolte **Správce** &gt; **Správa mobilních zařízení** &gt; **Vícefaktorové ověřování**.

2.  Vyberte možnost **Konfigurace vícefaktorového ověřování** a potom **Povolit vícefaktorové ověřování**.



<!--HONumber=Sep16_HO3-->


