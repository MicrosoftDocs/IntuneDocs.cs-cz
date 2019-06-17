---
title: Integrace Jamf Pro s Microsoft Intune pro dodržování předpisů
titleSuffix: Microsoft Intune
description: Zásady dodržování předpisů Microsoft Intune použijte s Azure Active Directory podmíněný přístup k lepšímu zabezpečení zařízení spravovaná aplikací Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7b5d3754c7dd3ead9236e223fd568e58e96fe9a1
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045153"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

Platí pro: Intune na portálu Azure Portal

Pokud vaše organizace používá [Jamf Pro](https://www.jamf.com) ke správě vašich koncových uživatelů Mac, můžete zásady dodržování předpisů Microsoft Intune pomocí Azure Active Directory podmíněného přístupu zařízení ve vaší organizaci musí být kompatibilní.

## <a name="prerequisites"></a>Požadavky

Budete potřebovat následující příkaz pro konfiguraci podmíněného přístupu s Jamf Pro:

- Jamf Pro 10.1.0 nebo novější
- [Aplikaci Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- Zařízení macOS se systémem OS X 10.11 Yosemite nebo novější

## <a name="connecting-intune-to-jamf-pro"></a>Připojení Intune k Jamf Pro

Propojení služby Intune s Jamf Pro můžete:

1. Vytvoření nové aplikace v Azure
2. Povolení integrace Intune s Jamf Pro
3. Konfigurace podmíněného přístupu v Jamf Pro

## <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory

1. V [webu Azure portal](https://portal.azure.com), přejděte na stránku **Azure Active Directory** > **registrace aplikací**a pak vyberte **registrace nové**. 

2. Na **zaregistrovat aplikaci** stránky, zadejte následující podrobnosti:
   - V **název** části, zadejte název smysluplné aplikace, například **podmíněný přístup Jamf**.
   - Pro **podporovaných typů účtu** vyberte **účty v libovolném adresáři organizace**. 
   - Pro **identifikátor URI pro přesměrování**, ponechte výchozí Web a potom zadejte adresu URL instance Jamf Pro.  

3. Vyberte **zaregistrovat** vytvořit aplikaci a otevřete stránku přehled pro novou aplikaci.  

4. V aplikaci **přehled** stránky, zkopírujte **ID aplikace (klient)** hodnotu a uložte ho pro pozdější použití. V postupech novější tuto hodnotu budete potřebovat.  

5. Vyberte **certifikáty a tajné kódy** pod **spravovat**. Vyberte **nový tajný kód klienta** tlačítko. Zadejte hodnotu do **popis**, vyberte možnosti pro **Expires** a zvolte **přidat**.

   > [!IMPORTANT]  
   > Než odejdete z této stránky, zkopírujte hodnotu tajný kód klienta a poznamenejte si ho pro pozdější použití. Je třeba tuto hodnotu v pozdější postupy. Tato hodnota není k dispozici, bez nutnosti opětovného vytvoření registraci aplikace.  

6. Vyberte **oprávnění k rozhraní API** v části Správa.  Vyberte existující oprávnění a pak vyberte **odebrat oprávnění** odstranit tato oprávnění. Odebrání všech existujících oprávnění je nutné, protože přidáte nová oprávnění a aplikace funguje, pouze pokud má jediné požadované oprávnění.  

7. Chcete-li přiřadit nové oprávnění, vyberte **přidat oprávnění**. Na **žádosti rozhraní API oprávnění** stránce **Intune**a pak vyberte **oprávnění aplikace**. Zaškrtněte políčko pro **update_device_attributes**.  

   Vyberte **přidejte oprávnění** tuto konfiguraci uložíte.  

8. Na **oprávnění k rozhraní API** stránce **udělit souhlas správce služby pro Microsoft**a pak vyberte Ano.  

   Byl dokončen proces registrace aplikace ve službě Azure AD.


    > [!NOTE]
    > Pokud vyprší platnost tajného klíče klienta, musíte vytvořit nový tajný kód klienta v Azure a pak aktualizovat data podmíněného přístupu v Jamf Pro. Azure umožňuje mít oba starý tajných kódů a nový klíč aktivní, aby se zabránilo přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=20909)a přejděte na **Microsoft Intune** > **dodržování předpisů zařízením** > **Správa partnerského zařízení**.

2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace, který jste uložili během předchozího postupu do **Jamf Azure Active Directory App ID** pole.

3. Vyberte **Uložit**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf Pro

1. V Jamf Pro přejděte do části **Global Management (Globální správa)** > **Conditional Access (Podmíněný přístup)**. Klikněte na tlačítko **Edit** (Upravit) na kartě **Microsoft Intune Integration** (Integrace Microsoft Intune).

2. Zaškrtněte políčko **Enable Microsoft Intune Integration** (Povolit integraci Microsoft Intune).

3. Zadejte požadované informace o vašem tenantovi Azure, včetně **umístění**, **název domény**, **ID aplikace**a hodnota *klienta tajný kód* , že jste si uložili při vytváření aplikace ve službě Azure AD.  

4. Vyberte **Uložit**. Jamf Pro otestuje nastavení a ověří úspěchu.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po dokončení konfigurace integrace mezi Intune a Jamf musíte [použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Další postup

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
- [Odešle data Jamf do Intune](data-jamf-sends-to-intune.md)
