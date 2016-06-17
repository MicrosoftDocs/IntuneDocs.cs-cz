---
# required metadata

title: Příprava registrace zařízení v Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Příprava registrace zařízení v Microsoft Intune
Pokud chcete zaměstnancům umožnit registraci mobilních zařízení (včetně zařízení s Androidem, iOS a Windows Phone a počítačů s Windows) pomocí Intune, musíte povolit registraci zařízení. Pokud chcete povolit registraci, musíte nastavit autoritu správy mobilních zařízení, nakonfigurovat portál společnosti Intune, přiřadit licence a povolit registraci pro platformu zařízení.

## <a name="BKMK_Set_MDM_Authority"></a>Nastavení autority pro správu mobilních zařízení
Autorita MDM definuje službu správy s oprávněními ke správě skupiny zařízení. Příklady možných autorit MDM zahrnují Intune samostatně a Configuration Manager s Intune. Pokud nastavíte Configuration Manager jako autoritu správy, ke správě mobilních zařízení nejde použít žádnou jinou službu.

>[!IMPORTANT]
> Zvažte, zda chcete spravovat mobilní zařízení pouze s použitím Intune (online služba) nebo použitím nástroje System Center Configuration Manager s Intune (místní softwarové řešení ve spojení s online službou). Po nastavení autority správy mobilních zařízení ji nemůžete změnit.



1.  V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) klikněte na **Správce** &gt; **Správa mobilních zařízení**..

2.  V seznamu **Úkoly** klikněte na **Nastavit autoritu pro správu mobilních zařízení**. Otevře se dialogové okno **nastavení autority pro správu mobilních zařízení** .

    ![Dialogové okno nastavení autority pro správu mobilních zařízení.](../media/intune-mdm-authority.png)

3.  Intune požádá o potvrzení, že chcete Intune používat jako autoritu pro správu mobilních zařízení. Jestli chcete ke správě mobilních zařízení používat Microsoft Intune, zaškrtněte políčko a klikněte na **Ano** .

## Konfigurace portálu společnosti Intune a přiřazení licencí
Portál společnosti Intune pomáhá uživatelům s přístupem k prostředkům společnosti, jako jsou aplikace, s hledáním informací technické podpory a s registrací zařízení nebo rušením jejich registrace. Před registrací zařízení byste měli [nakonfigurovat portál společnosti](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Pokud chcete povolit přístup k Intune, musíte také [přiřadit uživatelské licence](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4).

## Nastavení správy zařízení
Po nastavení autority správy mobilních zařízení musíte nastavit správu zařízení pro operační systémy, které vaše organizace hodlá podporovat. Kroky při nastavení správy zařízení se liší v závislosti na operačním systému. Operační systém Android například nevyžaduje žádné akce v konzole pro správu Intune. Operační systémy Windows a iOS naopak pro umožnění správy vyžadují vztah důvěryhodnosti mezi zařízením a Intune.

> [!div class="op_single_selector"]
- [Nastavení správy systému Android pomocí Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Nastavení správy pro zařízení Windows Phone v Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Nastavení správy pro zařízení Windows v Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Rovněž můžete:
 - Použít [účtu správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) k registraci více zařízení
 - [Určit zařízení ve vlastnictví společnosti pomocí kódů IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) k usnadnění registrace zařízení a cílových zásad


<!--HONumber=May16_HO1-->


