---
title: "Hodnocení správy mobilních zařízení v Microsoft Intune"
description: "Hodnocení MDM v bezplatné zkušební verzi Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: adef9335d8f199e8dec56e92eb1fda8c180ac6ce
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Hodnocení správy mobilních zařízení v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Tato příručka pro testování popisuje, jak funguje správa mobilních zařízení v Intune. Vyzkoušíte si následující:
- Registraci zařízení ke správě pomocí Intune
- Vytvoření skupin pro uspořádání uživatelů a zařízení
- Vytvoření a nasazení zásad správy zařízení do skupin
- Publikování aplikace tak, aby si ji uživatelé se zaregistrovanými zařízeními mohli nainstalovat do svých zařízení
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Předpoklady
Tato příručka předpokládá, že zkušební verzi používáte jenom pro účely vyhodnocení a poté, co se přihlásíte k odběru, plánujete použít čisté prostředí.

Abychom vám usnadnili použití zkušební verze, nastavíme velmi jednoduché prostředí, které bude používat jenom Intune a které předpokládá, že Intune bude vaší autoritou pro správu mobilních zařízení. V příručce vás však budeme odkazovat na podrobnější technické informace pro případ, že se budete chtít dovědět více.

Ve zkušební verzi můžete provádět vše, co je možné i v placené verzi. Jediným rozdílem je omezení zkušební verze na 100 uživatelských účtů.

## <a name="whats-not-covered"></a>Co tento článek nepopisuje
|Pokud vás zajímá: |Přečtěte si: |
|------------------------|----------|
|MDM v jiném než testovacím prostředí | [Začínáme](/intune/setup-steps) |
|MDM s Intune a nástrojem System Center Configuration Manager | [Hybridní správa mobilních zařízení](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management) |

Vzhledem k tomu, že výše uvedené příručky pomáhají nastavit Intune v produkčních prostředích, jsou delší a ve srovnání s příručkou pro testování obsahují mnohem více bodů rozhodování, které potřebujete projít.

Pokud se chcete rychle seznámit s Intune, doporučujeme začít s příručkou pro testování a pak přejít k dalším příručkám.

## <a name="prerequisites-for-this-evaluation"></a>Požadavky pro toto hodnocení
- Internet Explorer 10 nebo novější
- Zařízení, na kterém budete testovat, jak budou uživatelé Intune registrovat a spravovat svá zařízení pomocí Portálu společnosti. V této příručce používáme iPad a telefon s Androidem.
- Ke správě iPadu nebo jiného zařízení s iOSem budete potřebovat [certifikát služby Apple Push Notification](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- [Zkušební předplatné Intune](sign-up-for-30-day-trial-microsoft-intune.md).

## <a name="set-your-mdm-authority"></a>Nastavení autority pro správu mobilních zařízení (MDM)
Prvním krokem správy mobilních zařízení v Intune je nastavení **autority pro správu mobilních zařízení (MDM)**.

Pokud používáte Intune samostatně, jak toto testování předpokládá, nebo pokud používáte Intune jako součást předplatného Enterprise Mobility + Security (EMS), je nutné nastavit Intune jako autoritu pro správu mobilních zařízení. To znamená, že Intune určíte jako službu, ve které budete spravovat mobilní zařízení ve vaší organizaci.

Zákazníci, kteří chtějí ke správě mobilních zařízení používat Intune s nástrojem System Center Configuration Manager, se musí rozhodnout, jestli chtějí jako autoritu pro správu mobilních zařízení používat Intune nebo Configuration Manager. To je důležité rozhodnutí v případě produkčního prostředí, protože momentálně je velmi obtížné toto nastavení změnit poté, co ho určíte. To je ale nad rámec této příručky. Další informace o důsledcích nastavení Intune nebo nástroje Configuration Manager jako autority MDM najdete v tématu [Volba mezi samostatnou službou Intune a hybridní správou mobilních zařízení](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

Pro účely tohoto testování nastavíme jako autoritu MDM službu Intune. Vaše produkční prostředí to neovlivní, pokud se nerozhodnete použít zkušební verzi v produkčním prostředí.

1. V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Správce** &gt; **Správa mobilních zařízení**.
2. V seznamu **Úlohy** zvolte **Nastavit autoritu MDM**. Otevře se dialogové okno **nastavení autority pro správu mobilních zařízení** .
3. Intune požádá o potvrzení, že chcete Intune používat jako autoritu pro správu mobilních zařízení. Jestli chcete ke správě mobilních zařízení používat Intune, zaškrtněte políčko a zvolte **Ano**.

## <a name="enroll-your-test-devices-into-intune"></a>Registrace testovacích zařízení v Intune

V této příručce budeme registrovat telefon s Androidem a zařízení Apple iPad. Na konci této části jsou ale odkazy na [další informace o registraci zařízení v Intune](#Learn-more-about-device-enrollment).
### <a name="android"></a>Android
Nainstalujte si aplikaci **Portál společnosti Intune** od společnosti Microsoft, která je dostupná na webu [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), a přihlaste se pomocí [přihlašovacích údajů uživatele, které jste vytvořili](sign-up-for-30-day-trial-microsoft-intune.md#add-users) při registraci k bezplatné zkušební verzi.

### <a name="ios"></a>iOS
Aby mohli uživatelé zaregistrovat svá zařízení s iOSem, musíte nastavit Intune pro správu těchto zařízení.

1. **Získání žádosti o podepsání certifikátu**<br/>
Přihlaste se do Intune se svým účtem správce a přejděte na **Správa** > **Správa mobilních zařízení** > **iOS a Mac OS X** > **Nahrát na server certifikát služby APN** a pak zvolte **Stáhnout žádost o certifikát služby APN**. Uložte soubor žádosti o podepsání certifikátu (.csr) místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.
2.  **Získání certifikátu APNs (Apple Push Notification Service)**<BR/>
Přejděte na portál [Apple Push Certificates Portal](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) a přihlaste se pod Apple ID vaší společnosti, abyste mohli vytvořit certifikát APN pomocí souboru .csr. Když zvolíte **Nahrát na portálu Apple Push Certificate Portal**, získáte soubor .json, který se nedá použít pro služby APN. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal do nabídky certifikátů pro servery třetích stran a zvolte **Stáhnout**.<br/>
Stáhněte si certifikát služby APN ( soubor .pem) a uložte ho místně. Toto Apple ID musíte později použít k obnovení certifikátu služby APN.
3.  **Přidání certifikátu APNs do služby Intune**<BR/>
V konzole pro správu Microsoft Intune přejděte na **Správa** > **Správa mobilních zařízení** > **iOS a Mac OS X** > **Nahrát na server certifikát služby APN** a pak zvolte **Nahrát na server certifikát služby APN**. Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a zadejte své Apple ID. S certifikátem služby APN může Intune registrovat a spravovat zařízení se systémem iOS vynucením zásad u registrovaných mobilních zařízení.
4.  **Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům.**<br/>
Postup registrace koncových uživatelů najdete v tématech [Registrace zařízení se systémem iOS do Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) a [Registrace zařízení s Mac OS X v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.


### <a name="learn-more-about-device-enrollment"></a>Další informace o registraci zařízení

Intune podporuje zařízení s následujícími platformami:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Požadavky na povolení správy zařízení závisejí na spravovaných platformách.
- Mobilní zařízení s **Androidem** umožňují uživatelům [registraci pomocí aplikace Portál společnosti](/intune-classic/deploy-use/set-up-android-management-with-microsoft-intune) dostupné na webu Google Play. Žádná další konfigurace v Intune se nevyžaduje.
- [Požadavky na nastavení pro **iOS a Mac OS X**](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

- [Požadavky na nastavení pro **Windows Phone**](/intune-classic/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune)






## <a name="next-steps"></a>Další kroky
[Vytvoření skupin pro uspořádání uživatelů a zařízení](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)
