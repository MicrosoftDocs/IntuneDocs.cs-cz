---
title: "Podmíněný přístup k 0365 na základě aplikací | Microsoft Intune"
description: "Udělejte si představu o tom, jak vám podmíněný přístup MAM pomůže určit, které aplikace mají přístup ke službám O365."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Vytvoření zásady, která umožňuje přístup ke službám Office 365 jenom mobilním aplikacím, které podporují zásady Intune MAM
[Zásady správy mobilních aplikací (MAM) Intune](protect-apps-and-data-with-microsoft-intune.md) pomáhají chránit vaše firemní data na zařízeních, která jsou zaregistrovaná ke správě v Intune. Zásady MAM můžete použít také u **zařízení vlastněných zaměstnanci, která nejsou zaregistrovaná ke správě v Intune**.  V takovém případě potřebujete mít pořád jistotu, že jsou vaše firemní data a prostředky chráněné, i když tato zařízení nespravujete. Pomocí podmíněného přístupu MAM můžete vytvořit zásadu, která umožňuje přístup ke službám O365 (jako je Exchange Online) jenom mobilním aplikacím, které podporují zásady Intune MAM.

Když například povolíte přístup k Exchangi Online jenom **aplikaci Microsoft Outlook**, můžete **integrovaným poštovním aplikacím v iOS a Androidu**, jejichž data nejsou chráněná zásadami Intune MAM, zablokovat příjem e-mailů z **Exchange Online**.

## Předpoklady
**Předtím**, než můžete zásadu podmíněného přístupu MAM nakonfigurovat, musíte mít **Enterprise Mobility + Security nebo předplatné Azure Active Directory Premium**, přičemž uživatelé musí mít licence na EMS nebo Azure AD. Další informace najdete na [stránce s cenami služby Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) nebo na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Podporované aplikace
**Exchange Online**
* Microsoft Outlook pro Android a iOS

## Kolize s jinými metodami podmíněného přístupu a ověřování
### Podmíněný přístup MAM s ověřováním na základě certifikátů Azure Active Directory

Podmíněný přístup MAM se nesmí používat s ověřováním na základě certifikátů Azure Active Directory (Azure AD). Současně můžete mít nakonfigurovanou jen jednu z těchto metod.
### Podmíněný přístup MAM na základě dodržování předpisů pro zařízení  

[Podmíněný přístup na základě dodržování předpisů pro zařízení](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**podmíněný přístup zařízení**) můžete nakonfigurovat v [konzole pro správce Intune](https://manage.microsoft.com) nebo v [konzole pro správu služby Azure AD Premium] (https://manage.windowsazure.com). Podmíněný přístup zařízení vyžaduje, aby se uživatelé připojili k Exchangi Online jenom přes zařízení spravovaná službou Intune, která vyhovují její zásadě dodržování předpisů pro zařízení, nebo přes počítače připojené k doméně.  Pokud uživatel patří do některých skupin zabezpečení, které používají zásady podmíněného přístupu MAM i zařízení, musí splňovat jeden z těchto dvou požadavků:
* Aplikace použitá pro přístup ke službě je mobilní aplikace podporovaná podmíněným přístupem MAM, přičemž v zařízení, na kterém tato aplikace běží, je nainstalovaný **iOS Authenticator (pro zařízení s iOS)** nebo **aplikace Portál společnosti (pro zařízení s Androidem)**.
* Zařízení použité pro přístup ke službě je **spravované přes Intune a vyhovuje** zásadě dodržování předpisů pro zařízení, nebo se jedná o **počítač připojený k doméně**.  Tuto situaci ilustrují následující příklady:
  * Když se uživatel pokusí připojit z **nativní e-mailové aplikace iOS**, bude muset používat **spravované a vyhovující zařízení**, protože nativní poštovní aplikace není podporovaná podmíněným přístupem MAM.
  * Když se uživatel pokusí připojit z **domácího počítače s Windows**, uplatní se **zásada podmíněného přístupu zařízení**, která vyžaduje, aby se použil počítač připojený k doméně.


## Co očekávat při používání aplikace s podmíněným přístupem MAM
Podmíněný přístup MAM ověřuje identitu schválené aplikace pomocí zprostředkující aplikace, která musí existovat v zařízení:
*  Zprostředkující aplikací pro **iOS** je **aplikace Azure Authenticator**.
* Zprostředkující aplikací pro **Android** je **aplikace Portál společnosti Intune**. 

Koncoví uživatelé, kteří se poprvé přihlašují k aplikaci s podporou podmíněného přístupu MAM (jako je OneDrive nebo Outlook), jsou vyzváni k instalaci zprostředkující aplikace a registraci zařízení v Azure AD. Při registraci zařízení v Azure AD (dříve označované jako připojení k pracovišti) se vytvoří záznam zařízení a certifikát, vůči kterému se vydávají tokeny.  **Není** to totéž jako **registrace MDM**. Neuplatňují se žádné profily ani zásady správy a nepořizuje se žádný inventář aplikací, které zařízení obsahuje.  Proces instalace zprostředkující aplikace a registrace zařízení proběhne jenom při prvním použití nějaké spravované aplikace.


## Další kroky
[Vytvoření zásad Exchange Online pro aplikace MAM](mam-ca-for-exchange-online.md)

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

### Související témata

[Ochrana dat aplikací pomocí zásad MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


