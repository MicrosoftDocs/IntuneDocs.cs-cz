---
title: "Ukázkové scénáře omezeného přístupu k e-mailu | Dokumentace Microsoftu"
description: "Několik ukázkových scénářů a jejich možná implementace s podmíněným přístupem"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2d6ead1495a64e4e215c49b14064e390065a06de


---

# <a name="restrict-access-to-email-with-microsoft-intune-example-scenarios"></a>Omezení přístupu k e-mailu a pomocí Microsoft Intune: Ukázkové scénáře

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>Scénář 1: Zablokování přístupu uživatelů k Exchangi Online prostřednictvím nekompatibilních zařízení
### <a name="scenario-requirements"></a>Požadavky na scénář
- Je třeba blokovat přístup k Exchangi Online pro všechny uživatele ve skupině zabezpečení Azure Active Directory **Účetní oddělení**, pokud jejich zařízení nedodržují předpisy v nasazených zásadách dodržování předpisů.
- Pokud je v této skupině uživatel se zařízením, které [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nepodporuje, musí se mu na tomto zařízení zablokovat přístup k Exchangi Online.
- Je třeba vyloučit ze zásad všechny uživatele ve skupině zabezpečení Azure Active Directory **Finanční oddělení**, i když jsou i ve skupině zabezpečení **Účetní oddělení** .

Pokud toho chcete dosáhnout, nakonfigurujte zásady podmíněného přístupu k Exchangi Online s následujícím nastavením:

- Vyberte **Zapnout zásady podmíněného přístupu**.

- Vyberte platformy, kterým má být povolen přístup z aplikací s moderním ověřováním.
- Pro aplikace Exchange ActiveSync vyberte **Blokovat zařízení nedodržující předpisy na platformách, které Microsoft Intune podporuje** a **Blokovat všechna ostatní zařízení na platformách, které Microsoft Intune nepodporuje**.
-   V části **Cílová skupina** v nabídce **Vybrané skupiny zabezpečení** vyberte skupinu uživatelů **Účetní oddělení**.

-   V části **Vyloučená skupina** v nabídce **Vybrané skupiny zabezpečení** vyberte skupinu uživatelů **Finanční oddělení**.


Následující postup se ve scénáři používá k určení zařízení, která můžou k Exchangi Online přistupovat:

![Tok přístupu k zařízení](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>Scénář 2: Intune musí spravovat všechna zařízení s iOSem, která přistupují k místnímu Exchangi
### <a name="scenario-requirements"></a>Požadavky na scénář
- Přístup k místnímu Exchangi by měla mít pouze zařízení s iOSem.
- Před použitím pro přístup k Exchangi musí být zařízení také registrovaná v Intune a splňovat pravidla zásad dodržování předpisů.

Pokud toho chcete dosáhnout, nakonfigurujte následující zásady podmíněného přístupu k místnímu Exchangi s následujícím nastavením:

-   Vyberte **Blokovat e-mailovým aplikacím přístup k místnímu systému Exchange, pokud zařízení není kompatibilní nebo není zaregistrované v Microsoft Intune**. Výběrem této možnosti povolíte zásady podmíněného přístupu, které vyžadují, aby před přístupem k Exchangi byla všechna zařízení zaregistrovaná v Microsoft Intune a splňovala pravidla zásad dodržování předpisů.

-   Pro upřesňující nastavení protokolu Exchange Active Sync vytvořte následující položky:

  -   Výjimka platformy umožňující zařízením s iOSem přistupovat k systému Exchange.   

  -   Výchozí pravidlo, které určuje, že když se na zařízení nevztahuje pravidlo výjimky platformy, jeho přístup k Exchangi by měl být blokovaný. Toto pravidlo zajišťuje, že zařízení s jiným systémem než iOS budou mít přístup k Exchangi blokovaný.

K určení zařízení, která můžou k Exchangi přistupovat, se používá tento tok:

![Tok přístupu k zařízení](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>Scénář 3: K místnímu Exchangi nemůžou přistupovat žádná zařízení s Androidem
### <a name="scenario-requirements"></a>Požadavky na scénář
- Všechna zařízení s Androidem by měla mít k Exchangi blokovaný přístup.
- Všechna ostatní podporovaná zařízení mohou k Exchangi přistupovat, pokud jsou spravovaná službou [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Pokud toho chcete dosáhnout, nakonfigurujte zásady podmíněného přístupu k místnímu Exchangi s následujícím nastavením:

-   Vyberte **Blokovat e-mailovým aplikacím přístup k místnímu systému Exchange, pokud zařízení není kompatibilní nebo není zaregistrované v Microsoft Intune**. Výběrem této možnosti budete vyžadovat, aby byla všechna zařízení zaregistrovaná v Intune a splňovala pravidla zásad dodržování předpisů.

- Pro upřesňující nastavení protokolu Exchange Active Sync vytvořte následující položky:
  -   Výjimka platformy blokující přístup k Exchangi pro zařízení s Androidem. Toto pravidlo zajišťuje, že zařízení s Androidem nejde pro přístup k Exchangi používat.

  -   Výchozí pravidlo, které určuje, že pokud se na zařízení nevztahují ostatní pravidla, mělo by mít povolený přístup k Exchangi. Toto výchozí pravidlo zajišťuje, že zařízení, která používají jiné platformy než Android, ale která podporuje Microsoft Intune, se pro přístup k Exchangi můžou použít. Musí být ale zaregistrovaná v Intune a splňovat pravidla zásad dodržování předpisů.

K určení zařízení, která můžou k Exchangi přistupovat, se používá tento tok:

![Tok přístupu k zařízení](./media/ConditionalAccess8-4.png)



<!--HONumber=Dec16_HO2-->


