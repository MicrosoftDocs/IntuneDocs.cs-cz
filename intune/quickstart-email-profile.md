---
title: 'Rychlý start: Vytvoření e-mailového profilu zařízení pro iOS'
titlesuffix: Microsoft Intune
description: Zjistěte, jak pomocí Microsoft Intune vytvořit e-mailový profil zařízení, aby se zařízení s iOSem mohla bezpečně připojovat k firemnímu e-mailu.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b5f78c2b47bb916fd06492175b688afd17297384
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490672"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Rychlý start: Vytvořte profil zařízení pro iOS

V tomto rychlém startu se dozvíte, jak vytvořit e-mailový profil zařízení pro zařízení s iOSem. Tento profil určuje nastavení, která se vyžadují k tomu, aby se integrovaná e-mailová aplikace na zařízení s iOSem mohla připojit k firemnímu e-mailu. E-mailové profily zařízení pomáhají standardizovat nastavení pro různá zařízení a umožňují koncovým uživatelům přístup k firemnímu e-mailu na jejich osobních zařízeních bez toho, aby museli něco nastavovat. Pokud chcete ochranu e-mailu dále zdokonalit, můžete pomocí e-mailového profilu určovat, jestli jsou zařízení kompatibilní, a pak nastavením podmíněného přístupu umožnit přístup k e-mailu jenom kompatibilním zařízením. Podrobnosti o e-mailových profilech najdete v tématu [Jak nakonfigurovat nastavení e-mailu v Microsoft Intune](email-settings-configure.md).

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-an-ios-email-profile"></a>Vytvoření e-mailového profilu pro iOS
1. V Intune vyberte **Konfigurace zařízení** a pak **Profily**.
2. Vyberte **Vytvořit profil**.
   
   ![Vytvoření e-mailového profilu pro iOS](media/quickstart-email-profile/ios-create-profile.png)

3. Do pole **Název** zadejte popisný název nového profilu. Pro účely tohoto příkladu zadejte **Vyžadovat pracovní e-mail pro iOS**.
4. Zadejte následující informace o profilu:
   - Do pole **Popis** zadejte **Vyžadovat, aby zařízení s iOSem používala pracovní e-mail**.
   - U možnosti **Platforma** vyberte **iOS**.
   - U možnosti **Typ profilu** vyberte **E-mail**.
    
     ![Vytvořit e-mailový profil pro použití se systémem iOS](media/quickstart-email-profile/ios-email-profile-name.png)

5. Vyberte **Nastavení** a zadejte následující nastavení (u dalších nastavení ponechejte výchozí hodnoty):
   - **E-mailový server**: Pro účely tohoto rychlého startu zadejte **outlook.office365.com**. Toto nastavení určuje umístění (URL) e-mailového serveru Exchange, který bude aplikace iOS Mail používat pro připojení k e-mailu.
   - **Název účtu**: Zadejte **firemní e-mailu**.
   - **Atribut uživatelského jména z AAD**: Tento název je atribut, který Intune získá od služby Azure Active Directory (Azure AD). Pomocí tohoto jména Intune dynamicky vygeneruje uživatelské jméno pro tento profil. Pro účely tohoto rychlého startu budeme předpokládat, že chceme, aby se jako uživatelské jméno pro tento profil použil **Hlavní název uživatele (UPN)** (například user1@contoso.com).
   - **Atribut e-mailové adresy z AAD**: Toto nastavení je e-mailovou adresu z Azure AD, který se použije k přihlášení k serveru Exchange. Pro účely tohoto rychlého startu vyberte **Hlavní název uživatele (UPN)**.
   - **Metoda ověřování**: Pro účely tohoto rychlého startu vyberte **uživatelské jméno a heslo**. (Pokud jste už nastavili certifikát pro Intune, můžete zvolit také možnost **Certifikát**.)
    
     ![Vytvořit e-mailový profil pro použití s Iosem](media/quickstart-email-profile/ios-email-profile.png)

6. Vyberte **OK**.
7. Vyberte **Vytvořit**. V zobrazeném řídicím panelu se v seznamu profilů zobrazí nový profil, takže můžete monitorovat jeho přiřazení k zařízením a uživatelům s iOSem.
8. Zvolte **Přiřazení**.
9. Vyberte kartu **Zahrnout** a pak vyberte **Všichni uživatelé a všechna zařízení**. 
10. Vyberte **Uložit**.

## <a name="clean-up-resources"></a>Vyčištění prostředků
Pokud nemáte v úmyslu používat vytvořený profil v dalších kurzech nebo k testování, můžete ho teď odstranit.
1. V Intune vyberte **Konfigurace zařízení** a pak **Profily**.
2. Vyberte vytvořený testovací profil **Vyžadovat pracovní e-mail pro iOS**.
3. Vyberte tři tečky (**...**) vedle tohoto profilu a pak vyberte **Odstranit**.

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste vytvořili e-mailový profil pro zařízení s iOSem. Teď můžete pomocí tohoto profilu určovat, jestli jsou zařízení s iOSem kompatibilní. Uděláte to tak, že vytvoříte zásady dodržování předpisů, které budou označovat jako nekompatibilní všechna zařízení s iOSem, která tomuto profilu neodpovídají. Pro zvýšení ochrany můžete vytvořit zásady podmíněného přístupu, které budou přístup k e-mailu pomocí nekompatibilních zařízení s iOSem blokovat. Další informace o zásadách dodržování předpisů pro zařízení najdete v článku o tom, [jak začít používat zásady dodržování předpisů pro zařízení v Intune](device-compliance-get-started.md).

> [!div class="nextstepaction"]
> [Kurz: Ochrana Exchange Online e-mailu na spravovaných zařízeních](tutorial-protect-email-on-enrolled-devices.md)
