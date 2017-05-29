---
title: "Nastavení omezení pro zařízení s Windows Phone 8.1 v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 754833026331868efebcbcd157e8ce76e3ae35bb
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení Windows Phone 8.1 v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Obecné
-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
-     **Kamera** – Povolí nebo zablokuje fotoaparát zařízení.
-     **Kopírování a vložení** – Povolí nebo zablokuje funkci kopírování a vkládání na zařízeních.
-     **Vyměnitelné úložiště** – Povolí použití vyměnitelného úložiště v zařízení, třeba SD karty.
-     **Zeměpisná poloha** – Umožní zařízení využívat informace o poloze.
-     **Účet Microsoft** – Povolí nebo zablokuje možnost, aby uživatel propojil účet Microsoft se zařízením.
-     **Snímek obrazovky** – Povolí uživateli zachytit obsah obrazovky jako obrázek.
-     **Odeslání diagnostických dat** – Povolí zařízení odesílat diagnostické informace Microsoftu.
-     **Synchronizace vlastních e-mailových účtů** – Povolí zařízení připojit se k e-mailovým účtům jiným než Microsoftu.

## <a name="password"></a>Heslo
-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
-     **Zadání hesla nutné** – Vyžaduje, aby koncový uživatel zadal heslo k přístupu k zařízení.
    -     **Požadovaný typ hesla** – Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.
    -     **Minimální délka hesla** – Určuje minimální počet znaků, které heslo musí obsahovat.
    -     **Jednoduchá hesla** – Umožňuje použití jednoduchých hesel, jako je 0000 nebo 1234.
    -     **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Určuje, kolikrát může uživatel zadat nesprávné heslo, než se zařízení vymaže.
    -     **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje dobu, po kterou musí zařízení zůstat v nečinnosti, než se automaticky zamkne jeho obrazovka.
    -     **Konec platnosti hesla (dny)** – Určuje počet dní, než bude nutné změnit heslo zařízení.
    -     **Znemožnit opakované použití předchozích hesel** – Určuje, kolik dříve použitých hesel se pamatuje.
-     **Šifrování** – Vyžaduje, aby data na podporovaných mobilních zařízeních byla šifrovaná.

## <a name="app-store"></a>App Store
-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
-     **App Store** – Umožňuje uživatelům připojit se ze zařízení k obchodu s aplikacemi App Store.

## <a name="restricted-apps"></a>Omezené aplikace

-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

**Blokované aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Povolené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Aplikace, které spravuje Intune, jsou povolené automaticky.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu povolených a blokovaných aplikací, použijte následující formát:

Na stránce [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) najděte aplikaci, kterou chcete použít.

Otevřete stránku aplikace a zkopírujte adresu URL do schránky. Tu teď můžete použít jako adresu URL v seznamu povolených nebo blokovaných aplikací.

Příklad: Vyhledání aplikace Skype ve Storu. Použijete adresu URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.



### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a naplnit seznam ze souboru csv ve formátu <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo kliknout na **Export** a vytvořit si soubor csv obsahující seznam aplikací s omezeným přístupem ve stejném formátu.


## <a name="browser"></a>Prohlížeč
-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
-     **Webový prohlížeč** – Povolí nebo zablokuje integrovaný webový prohlížeč v zařízeních.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení
-     **Použít všechna nastavení jenom na Windows Phone 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows Phone 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10 Mobile.
-     **Wi-Fi** – Povolí nebo zakáže funkce Wi-Fi v zařízení.
-     **Wi-Fi tethering** – Povolí sdílení mobilního internetového připojení (tethering) přes Wi-Fi na zařízení.
-     **Automaticky se připojovat k Wi-Fi hotspotům** – Povolí zařízení automaticky se připojovat k bezplatným Wi-Fi hotspotům a automaticky přijímat jakékoli podmínky použití.
-     **Hlášení Wi-Fi hotspotů** – Umožní posílání informací o připojeních Wi-Fi, aby uživatel mohl nacházet možnosti připojení v okolí.
-     **Bezkontaktní komunikace (NFC)** – Povolí nebo zakáže operace, které používají bezkontaktní komunikaci, na zařízeních, která ji podporují.
-     **Bluetooth** – Povolí nebo zakáže funkce Bluetooth v zařízení.

