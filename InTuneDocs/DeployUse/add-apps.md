---
# required metadata

title: Přidávání aplikací | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Přidávání aplikací s Microsoft Intune
Před zahájením nasazování aplikací s Microsoft Intune se seznamte s koncepty představenými v tomto tématu. Ty vám pomohou porozumět tomu, které aplikace můžete nasadit na kterou platformu, a pochopit požadavky, které musí být před nasazením splněné.

## Přidání typů, které můžete nasadit, s Intune
Aplikace můžete nasadit na všechny typy zařízení, které Intune podporuje. Postup a podporovaná zařízení se mohou lišit v závislosti na typu aplikace, kterou chcete nasadit. Následující informace vám pomůžou pochopit, co můžete nebo nemůžete nasadit:


### **Instalační služba systému Windows (&#42;.exe, &#42;.msi)**
- Tento typ aplikace musí podporovat tichou instalaci bez vstupu uživatele. Dokumentace k aplikaci by měla zahrnovat příslušné možnosti příkazového řádku k tiché instalaci aplikace (například **/q**). Seznam běžných možností příkazového řádku najdete [tady](https://support.microsoft.com/en-us/kb/227091).
- Jakékoli další soubory a složky, které vyžaduje instalační program aplikace, musí být dostupné z umístění, které určíte pro instalační soubory aplikace.
- Instalační služba systému Windows (.msi) a oprava instalační služby systému Windows (.msp) nevyžadují ve většině případů instalaci žádných argumentů příkazového řádku pro Intune. Podívejte se do dokumentace aplikace. Pokud se vyžadují argumenty příkazového řádku, musí být zadané jako název=dvojice hodnot (například TRANSFORMS=custom_transform.mst).

Tento typ aplikace se odešle do cloudového úložiště.
### **Balíček aplikace pro systém Android (&#42; soubor .apk)**
Tento typ aplikace se odešle do cloudového úložiště.
### **Balíček aplikace pro systém iOS (&#42; soubor .ipa)**
- Pokud chcete nasadit aplikace systému iOS, budete potřebovat platný balíček .ipa.
- Balíček .ipa musí být podepsaný společností Apple a datum vypršení platnosti uvedené v profilu zřizování musí být platné. Intune může distribuovat aplikace iOS s podnikovým certifikátem. Nejsou podporované všechny aplikace certifikátu vývojáře Apple.
- Vaše společnost musí mít zaregistrovaný iOS Developer Enterprise Program.
- Ujistěte se, že brána firewall vaší organizace umožňuje přístup na weby zřizování a certifikace pro iOS.
- Soubor manifestu (.plist) nemusí být nasazen s aplikací.

Tento typ aplikace se odešle do cloudového úložiště.

V současné době koncoví uživatelé nemůžou instalovat podnikové aplikace přímo z aplikace Portál společnosti Intune pro iOS. Je to z důvodu omezení vztahujících se na aplikace, které jsou zveřejněné v iOS App Storu (viz [Pokyny pro recenze v App Storu](https://developer.apple.com/app-store/review/guidelines/)). Uživatelé můžou používat podnikové aplikace (včetně spravovaných aplikací z App Storu a balíčků podnikových aplikací) tak, že si na zařízení spustí aplikaci Portál společnosti a kliknou na dlaždici Aplikace společnosti. Tím se otevře prohlížeč a přesměruje je na webový portál služby Intune.

### **Balíček aplikace pro Windows Phone (&#42;.xap, .appx, .appxbundle)**
- Pokud chcete nasazovat aplikace, musíte mít podnikový certifikát podepisování mobilního kódu. Další informace najdete v tématu [Nastavení správy pro zařízení Windows Phone v Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

Tento typ aplikace se odešle do cloudového úložiště.

Níže najdete informace o instalaci obchodních aplikací pro Univerzální platformu Windows v kombinaci s Intune.

### **Balíček aplikace pro systém Windows (.appx, .appxbundle)**
- Pokud chcete nasazovat aplikace, musíte mít podnikový certifikát podepisování mobilního kódu. Podrobnosti najdete v tématu [Nastavení správy pro zařízení Windows v Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).

Tento typ aplikace se odešle do cloudového úložiště.
### **Instalační služba systému Windows pomocí MDM (&#42;.msi)**
Tento typ instalačního programu umožňuje vytvářet a nasazovat aplikace založené na instalační službě systému Windows na zaregistrované počítače s Windows 10.<br /><br />Když použijete tento typ instalačního programu, platí následující aspekty:
- Můžete nahrát jenom jeden soubor s příponou .msi.
- Kód produktu a verze produktu v souboru se používají ke zjišťování aplikací.
- Použije se výchozí chování aplikace při restartování. Intune ho neřídí.
- Balíčky MSI na uživatele se nainstalují pro jednoho uživatele.
- Balíčky MSI na zařízení se nainstalují pro všechny uživatele v zařízení.
- Balíčky MSI v duálním režimu se momentálně nainstalují jenom pro všechny uživatele v zařízení.
- Aktualizace aplikací jsou podporované, když kód produktu MSI jednotlivých verzí je stejný.

Tento typ aplikace se odešle do cloudového úložiště.
### **Externí odkaz**
Používá se, když máte:
- **Adresu URL**, která umožňuje uživatelům stáhnout si aplikaci z App Storu.
- **Odkaz** na webovou aplikaci, která se spouští z webového prohlížeče.

Aplikace založené na externích odkazech nejsou uložené v cloudovém úložišti Intune.
### **Spravované aplikace pro iOS z obchodu s aplikacemi**
Umožňuje vám spravovat a nasazovat bezplatné aplikace pro systém iOS z App Storu. Také vám umožňuje přidružit [zásady správy mobilních aplikací](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) [aplikacím, které splňují předpisy](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx), a zkontrolovat jejich stav v konzole pro správu.<br /><br />Spravované aplikace pro iOS nejsou uložené v cloudovém úložišti Intune.
> [!TIP] Možnosti pro mobilní zařízení nejsou dostupné, dokud [nenastavíte autoritu pro správu mobilních zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md) na Intune.

## Podpora aplikací pro Univerzální platformu Windows
Počítače s Windows 10 nevyžadují k instalaci obchodních aplikací klíč pro zkušební načtení. Kvůli povolení zkušebního načtení ale musí mít klíč registru **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** hodnotu **1**.

Pokud není tento klíč registru nakonfigurovaný, Intune při prvním nasazení aplikace do zařízení automaticky nastaví hodnotu **1**. Pokud nastavíte hodnotu **0**, Intune ji nemůže automaticky změnit a instalace obchodních aplikací se nezdaří.

Obchodní aplikace pro Univerzální platformu Windows musí být podepsané certifikátem pro podpis kódu, který musí být důvěryhodný pro všechna zařízení, ve kterých chcete aplikaci nasadit. Můžete použít certifikáty z interní infrastruktury PKI nebo certifikát z veřejného kořenového certifikátu od jiného výrobce nainstalovaný v zařízení.

V zařízeních se systémem Windows 10 Mobile můžete k podepisování univerzálních aplikací **.appx** používat jiný certifikát pro podepisování kódu než certifikát Symantec. U aplikací **.xap** a balíčků **.appx** sestavených pro systém Windows Phone 8.1, které chcete nainstalovat do zařízení se systémem Windows 10 Mobile, musíte použít certifikát pro podepisování kódu Symantec.

## Další kroky 

Před nasazením aplikací je dále musíte přidat do konzoly Intune. Můžete přidávat aplikace pro [registrovaná zařízení](add-apps-for-mobile-devices-in-microsoft-intune.md) nebo pro [počítače s Windows spravované klientským softwarem Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


