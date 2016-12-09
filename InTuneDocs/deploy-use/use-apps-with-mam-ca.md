---
title: "Používání aplikací s podmíněným přístupem MAM | Microsoft Intune"
description: "Udělejte si představu o tom, jak vám podmíněný přístup MAM pomůže určit, které aplikace mají přístup ke službám O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 317d101c34854fdf4913adcf53bdef614599deb7


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>Co očekávat při používání aplikace s podmíněným přístupem MAM
Podmíněný přístup MAM ověřuje identitu schválené aplikace pomocí zprostředkující aplikace, která musí existovat v zařízení:
*  Zprostředkující aplikací pro **iOS** je **aplikace Azure Authenticator**.
* Zprostředkující aplikací pro **Android** je **aplikace Portál společnosti Intune**. 

Koncoví uživatelé, kteří se poprvé přihlašují k aplikaci s podporou podmíněného přístupu MAM (jako je OneDrive nebo Outlook), jsou vyzváni k instalaci zprostředkující aplikace a registraci zařízení v Azure AD. Při registraci zařízení v Azure AD (dříve označované jako připojení k pracovišti) se vytvoří záznam zařízení a certifikát, vůči kterému se vydávají tokeny.  **Není** to totéž jako **registrace MDM**. Neuplatňují se žádné profily ani zásady správy a nepořizuje se žádný inventář aplikací, které zařízení obsahuje.  Proces instalace zprostředkující aplikace a registrace zařízení proběhne jenom při prvním použití nějaké spravované aplikace.

V následujícím seznamu jsou vlastnosti odvozené přímo ze zařízení:

* alternativeSecurityIds (kryptografický otisk certifikátu služby Azure Active Directory a hodnota hash veřejného klíče)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Odebrání zařízení z registrace Azure AD
Registraci zařízení můžete odebrat prostřednictvím konzoly správce Azure AD. To obvykle dělá správce IT.  Může to také udělat koncový uživatel na samotném zařízení.

* **Konzola správce Azure AD**: V konzole správce Azure AD** odstraňte zařízení, které chcete odebrat.
* **Zařízení s iOS**: Otevřete aplikaci Azure Authenticator, přejeďte po účtu prstem doleva a zvolte zrušení registrace.  
* **Zařízení s Androidem**: Odinstalujte aplikaci portálu společnosti nebo odeberte účet z **Nastavení systému**.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>Podmíněný přístup MAM na základě dodržování předpisů pro zařízení  

[Podmíněný přístup na základě dodržování předpisů pro zařízení](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**podmíněný přístup zařízení**) můžete nakonfigurovat v [konzole pro správce Intune](https://manage.microsoft.com) nebo v [konzole pro správu služby Azure AD Premium] (https://manage.windowsazure.com). Podmíněný přístup zařízení vyžaduje, aby se uživatelé připojili k Exchangi Online jenom přes zařízení spravovaná službou Intune, která vyhovují její zásadě dodržování předpisů pro zařízení, nebo přes počítače připojené k doméně.  Pokud uživatel patří do některých skupin zabezpečení, které používají zásady podmíněného přístupu MAM i zařízení, musí splňovat jeden z těchto dvou požadavků:
* Aplikace použitá pro přístup ke službě je mobilní aplikace podporovaná podmíněným přístupem MAM, přičemž v zařízení, na kterém tato aplikace běží, je nainstalovaný **iOS Authenticator (pro zařízení s iOS)** nebo **aplikace Portál společnosti (pro zařízení s Androidem)**.
* Zařízení použité pro přístup ke službě je **spravované přes Intune a vyhovuje** zásadě dodržování předpisů pro zařízení, nebo se jedná o **počítač připojený k doméně**.  Tuto situaci ilustrují následující příklady:
  * Když se uživatel pokusí připojit z **nativní e-mailové aplikace iOS**, bude muset používat **spravované a vyhovující zařízení**, protože nativní poštovní aplikace není podporovaná podmíněným přístupem MAM.
  * Když se uživatel pokusí připojit z **domácího počítače s Windows**, uplatní se **zásada podmíněného přístupu zařízení**, která vyžaduje, aby se použil počítač připojený k doméně.




## <a name="next-steps"></a>Další kroky
[Vytvoření zásad Exchange Online pro aplikace MAM](mam-ca-for-exchange-online.md)

[Blokování aplikací, které nepoužívají moderní ověřování](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


