---
title: Použití profilů certifikátů SCEP s Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte a přiřaďte profily certifikátů Simple Certificate Enrollment Protocol (SCEP) pomocí Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 321595a2ce8849b3d150b68f9dcc38dfda6ad940
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390292"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>Vytvoření a přiřazení profilů certifikátů SCEP v Intune

Až [nakonfigurujete infrastrukturu](certificates-scep-configure.md) pro podporu certifikátů Simple Certificate ENROLLMENT Protocol (SCEP), můžete vytvořit a přiřadit profily certifikátů SCEP pro uživatele a zařízení v Intune.

> [!IMPORTANT]  
> Před vytvořením profilů certifikátů SCEP musí zařízení, která budou používat profil certifikátu SCEP, důvěřovat vaší důvěryhodné kořenové certifikační autoritě (CA). Použití *profilu důvěryhodného certifikátu* v Intune k zřízení certifikátu důvěryhodné kořenové certifikační autority pro uživatele a zařízení informace o profilu důvěryhodného certifikátu najdete v [tématech Export certifikátu důvěryhodné kořenové certifikační autority](certificates-configure.md#export-the-trusted-root-ca-certificate) a [Vytvoření profilů důvěryhodných certifikátů](certificates-configure.md#create-trusted-certificate-profiles) v tématu *použití certifikátů pro ověřování v Intune*.


## <a name="create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfigurační profil** > **vytvořit profil**.

3. Zadejte následující vlastnosti:

4. Zadejte **název** a **popis** profilu certifikátu SCEP.

5. V rozevíracím seznamu **platforma** vyberte [podporovanou platformu zařízení](certificates-configure.md#supported-platforms-and-certificate-profiles) pro tento certifikát SCEP.

6. V rozevíracím seznamu **typ profilu** vyberte **certifikát SCEP**.  

   Pro platformu **Android Enterprise** se *typ profilu* dělí na dvě kategorie, *jenom vlastníkem zařízení* a *pracovní profil*. Nezapomeňte vybrat správný profil certifikátu SCEP pro zařízení, která spravujete.  

   Profily certifikátů SCEP pro profil *jenom vlastníkem zařízení* mají následující omezení:

   1. V části monitorování není oznamování certifikátů k dispozici pro profily certifikátů SCEP vlastníka zařízení.

   2. Intune nemůžete použít k odvolání certifikátů, které se zřídily profily certifikátů SCEP pro vlastníky zařízení. Můžete spravovat odvolání prostřednictvím externího procesu nebo přímo s certifikační autoritou. 

   4. U vyhrazených zařízení s Androidem Enterprise se profily certifikátů SCEP podporují jenom v konfiguraci sítě Wi-Fi a jenom ověřování.  Profily certifikátů SCEP na vyhrazených zařízeních s Androidem Enterprise se nepodporují pro ověřování pomocí sítě VPN nebo aplikací.   

   
7. Vyberte **Nastavení**a pak dokončete následující konfigurace:

   - **Typ certifikátu**:

     *(Platí pro: Android, Android Enterprise, iOS, macOS, Windows 8.1 a novější a Windows 10 a novější)*

     V závislosti na způsobu použití profilu certifikátu vyberte typ:

     - **Uživatel**: certifikáty *uživatelů* můžou v předmětu a síti SAN certifikátu obsahovat atributy uživatele i zařízení.  
     - **Zařízení**: certifikáty *zařízení* můžou v předmětu a síti SAN certifikátu obsahovat jenom atributy zařízení.

       Použijte **zařízení** pro scénáře, jako jsou například zařízení bez uživatele, jako jsou veřejné terminály nebo pro zařízení s Windows. Na zařízeních s Windows se certifikát nachází v úložišti certifikátů místního počítače.

   - **Formát názvu subjektu**:

     Vyberte, jak má Intune automaticky vytvořit název subjektu v žádosti o certifikát. Možnosti pro formát názvu subjektu závisí na zvoleném typu certifikátu – buď **uživatel** , nebo **zařízení**.

     > [!NOTE]
     > Existuje [známý problém](#avoid-certificate-signing-requests-with-escaped-special-characters) pro použití SCEP k získání certifikátů, když název subjektu v výsledné žádosti o podepsání certifikátu (CSR) obsahuje jeden z následujících znaků jako řídicí znak (s zpětným lomítkem \\):
     > - \+
     > - ;
     > - ,
     > - =

     - **Typ uživatelského certifikátu**

       Mezi možnosti formátu pro *Formát názvu subjektu* patří:

       - **Není nakonfigurováno**
       - **Běžný název**
       - **Běžný název včetně e-mailové adresy**
       - **Běžný název jako e-mail**
       - **IMEI (International Mobile Equipment Identity)**
       - **Sériové číslo**
       - **Vlastní**: Když vyberete tuto možnost, zobrazí se také textové pole **Vlastní**. V tomto poli můžete zadat vlastní formát názvu subjektu, včetně proměnných. Vlastní formát podporuje dvě proměnné: **Běžný název (CN)** a **E-mail (E)** . **Běžný název (CN)** můžete nastavit na některou z těchto proměnných:

         - **CN = {{username}}** : hlavní název uživatele (UPN), například janedoe@contoso.com.
         - **CN={{AAD_Device_ID}}** : ID přiřazené při registraci zařízení ve službě AD (Azure Active Directory). Toto ID se obvykle používá k ověření ve službě Azure AD.
         - **CN = {{sériové}}** : jedinečné sériové číslo (SN) obvykle používané výrobcem k identifikaci zařízení.
         - **CN = {{IMEINumber}}** : jedinečné číslo IMEI (International Mobile Equipment Identity), které se používá k identifikaci mobilního telefonu.
         - **CN = {{OnPrem_Distinguished_Name}}** : sekvence relativních rozlišujících názvů oddělená čárkou, například *CN = Jana Karásek, OU = UserAccounts, DC = Corp, DC = contoso, DC = com*.

           Pokud chcete použít proměnnou *{{OnPrem_Distinguished_Name}}* , proveďte synchronizaci atributu uživatele *onpremisesdistinguishedname* pomocí [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) do služby Azure AD.

         - **CN = {{onPremisesSamAccountName}}** : Správci můžou synchronizovat atribut sAMAccountName ze služby Active Directory do Azure AD pomocí služby Azure AD Connect do atributu s názvem *onPremisesSamAccountName*. Intune může tuto proměnnou nahradit jako součást žádosti o vystavení certifikátu v předmětu certifikátu. Atribut samAccountName je přihlašovací jméno uživatele používané k podpoře klientů a serverů z předchozí verze Windows (Pre-Windows 2000). Formát přihlašovacího jména uživatele je: *DomainName\testUser*nebo pouze *testUser*.

            Pokud chcete použít proměnnou *{{onPremisesSamAccountName}}* , nezapomeňte synchronizovat atribut uživatele *onPremisesSamAccountName* pomocí [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) do Azure AD.

         Kombinací jedné nebo několika těchto proměnných a statických řetězců můžete vytvořit vlastní formát názvu subjektu, jako třeba:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

         Tento příklad zahrnuje formát názvu subjektu, který používá proměnné CN a E a řetězce pro hodnoty organizační jednotky, organizace, umístění, stav a země. Článek [Funkce CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) popisuje tuto funkci a její podporované řetězce.

      - **Typ certifikátu zařízení**

        Možnosti formátu pro formát názvu subjektu zahrnují následující proměnné:

        - **{{AAD_Device_ID}}** nebo **{{AzureADDeviceId}}** – k identifikaci zařízení podle jeho ID Azure AD se dá použít jedna z těchto proměnných.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{Sériové}}**
        - **{{IMEINumber}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{Název_zařízení}}**
        - **{{FullyQualifiedDomainName}}** *(platí jenom pro zařízení se systémem Windows a zařízení připojená k doméně)*
        - **{{MEID}}**

        Tyto proměnné můžete zadat následovaný textem pro proměnnou v textovém poli. Například běžný název pro zařízení s názvem *zařízení1* se dá přidat jako **CN = {{název_zařízení}} zařízení1**.

        > [!IMPORTANT]
        > - Když zadáte proměnnou, uveďte její název do složených závorek {}, jak je vidět v příkladu, aby nedošlo k chybě.  
        > - Vlastnosti zařízení používané v *předmětu* nebo *síti SAN* certifikátu zařízení, jako jsou **IMEI**, **sériové**a **FullyQualifiedDomainName**, jsou vlastnosti, které by mohly být falešné osobou, která by mohla mít přístup k zařízení.
        > - Zařízení musí podporovat všechny proměnné určené v profilu certifikátu pro daný profil k instalaci na toto zařízení.  Pokud se například používá **{{IMEI}}** v názvu subjektu profilu SCEP a je přiřazeno k zařízení, které nemá číslo IMEI, profil se nepodaří nainstalovat.

   - **Alternativní název subjektu**: Vyberte způsob, jakým Intune automaticky vytvoří alternativní název subjektu (San) v žádosti o certifikát. Možnosti pro síť SAN závisí na typu certifikátu, který jste vybrali. buď na **uživatele** , nebo na **zařízení**.

      - **Typ uživatelského certifikátu**

        Vyberte z dostupných atributů:

        - **E-mailová adresa**
        - **Hlavní název uživatele (UPN)**

        Typy uživatelských certifikátů můžou například zahrnovat hlavní název uživatele (UPN) v alternativním názvu subjektu. Pokud slouží klientský certifikát k ověřování na serveru NPS (Network Policy Server), nastavte pro alternativní název subjektu hodnotu UPN.

      - **Typ certifikátu zařízení**

        Použijte rozevírací seznam **atributu** a vyberte atribut, přiřaďte **hodnotu**a **přidejte** ji do profilu certifikátu. Výběrem dalších atributů můžete přidat více hodnot.

        K dispozici jsou tyto atributy:

        - **E-mailová adresa**
        - **Hlavní název uživatele (UPN)**
        - **DNS**

        S typem certifikátu *Zařízení* můžete použít následující proměnné certifikátu zařízení pro hodnotu:

        - **{{AAD_Device_ID}}** nebo **{{AzureADDeviceId}}** – k identifikaci zařízení podle jeho ID Azure AD se dá použít jedna z těchto proměnných.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{Sériové}}**
        - **{{IMEINumber}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{Název_zařízení}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        Chcete-li zadat hodnotu pro atribut, zahrňte název proměnné se složenými závorkami následovaným textem pro tuto proměnnou. Například hodnota atributu DNS může být přidána **{{AzureADDeviceId}}. domain. com** , kde *. domain.com* je text. Pro uživatele s názvem *user1* se může e-mailová adresa zobrazit jako {{FullyQualifiedDomainName}}User1@Contoso.com.

        > [!IMPORTANT]
        > - Při použití proměnné certifikátu zařízení uveďte název proměnné v složených závorkách {}.
        > - Nepoužívejte složené závorky **{}** , symboly kanálu **|** a středníky **;** v textu, který následuje za proměnnou.
        > - Vlastnosti zařízení používané v *předmětu* nebo *síti SAN* certifikátu zařízení, jako jsou **IMEI**, **sériové**a **FullyQualifiedDomainName**, jsou vlastnosti, které by mohly být falešné osobou, která by mohla mít přístup k zařízení.
        > - Zařízení musí podporovat všechny proměnné určené v profilu certifikátu pro daný profil k instalaci na toto zařízení.  Pokud se například používá **{{IMEI}}** v síti SAN profilu SCEP a je přiřazeno k zařízení, které nemá číslo IMEI, nepodaří se mu nainstalovat profil.

   - **Období platnosti certifikátu**:

     Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud jste nakonfigurovali šablonu certifikátu tak [, aby podporovala vlastní hodnotu, kterou je možné nastavit v konzole Intune](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), pomocí tohoto nastavení určete dobu, po kterou bude certifikát vypršet.

     Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vydávající CA.

   - **Zprostředkovatel úložiště klíčů (KSP)** :

     *(Platí pro: Windows 8.1 a novější a Windows 10 a novější)*

     Určete, kam se má uložit klíč k certifikátu. Vyberte jednu z následujících hodnot:

     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), pokud existuje, jinak zapsat do softwarového KSP**
     - **Zapsat do KSP na čipu TPM (Trusted Platform Module), jinak chyba**
     - **Zapsat do služby Passport, jinak chyba (Windows 10 a novější)**
     - **Zapsat do softwarového KSP**

   - **Použití klíče**:

     Vyberte možnosti použití klíče pro certifikát:

     - **Digitální podpis**: umožňuje výměnu klíče jenom v případě, že digitální podpis pomáhá chránit klíč.
     - **Šifrování klíče**: umožňuje výměnu klíče jenom v případě, že je klíč zašifrovaný.

   - **Velikost klíče (bity)** :

     Vyberte počet bitů obsažených v klíči.

   - **Algoritmus hash**:

     *(Platí pro Android, Android Enterprise, Windows Phone 8,1, Windows 8.1 a novější a Windows 10 a novější)*

     Vyberte jeden z dostupných typů hashovacího algoritmu, který chcete s tímto certifikátem použít. Vyberte nejsilnější úroveň zabezpečení, kterou připojované zařízení podporuje.

   - **Kořenový certifikát**:

     Vyberte *profil důvěryhodného certifikátu* , který jste předtím nakonfigurovali a přiřadili k příslušným uživatelům a zařízením pro tento profil certifikátu SCEP. Profil důvěryhodného certifikátu se používá ke zřízení uživatelů a zařízení s certifikátem důvěryhodné kořenové certifikační autority. Informace o profilu důvěryhodného certifikátu najdete v tématech [Export certifikátu důvěryhodné kořenové certifikační autority](certificates-configure.md#export-the-trusted-root-ca-certificate) a [Vytvoření profilů důvěryhodných certifikátů](certificates-configure.md#create-trusted-certificate-profiles) v tématu *použití certifikátů pro ověřování v Intune*. Pokud máte kořenovou certifikační autoritu a vydávající certifikační autoritu, vyberte profil důvěryhodných kořenových certifikátů, který je přidružený k vystavující certifikační autoritě.

   - **Rozšířené použití klíče**:

     Přidejte hodnoty pro zamýšlený účel certifikátu. Ve většině případů certifikát vyžaduje *ověření klienta* , aby se mohl uživatel nebo zařízení ověřit na serveru. Podle potřeby můžete přidat další použití klíče.

   - **Prahová hodnota obnovení (%)** :

     Zadejte procento doby životnosti certifikátu zbývající v době, kdy zařízení požádá o obnovení certifikátu. Pokud například zadáte 20, bude proveden pokus o obnovení certifikátu, pokud vypršela platnost certifikátu 80%. Pokusy o obnovení budou pokračovat, dokud nebude obnovení úspěšné. Obnovení vygeneruje nový certifikát, který má za následek novou dvojici veřejného a privátního klíče.

   - **Adresy URL serveru SCEP**:

     Zadejte jednu nebo více adres URL pro servery NDES, které vystavují certifikáty prostřednictvím SCEP. Zadejte například něco jako *https://ndes.contoso.com/certsrv/mscep/mscep.dll* . V případě potřeby můžete přidat další adresy URL SCEP pro vyrovnávání zatížení, protože adresy URL se v profilu náhodně přidávají do zařízení. Pokud jeden ze serverů SCEP není dostupný, požadavek SCEP selže a je možné, že u pozdějších vrácení se změnami zařízení může být žádost o certifikát vytvořená na stejném serveru, který je mimo provoz.

8. Vyberte **OK**a pak vyberte **vytvořit**. Profil se vytvoří a zobrazí se v seznamu *Konfigurace zařízení – profily* .

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Vyhnout se žádostem o podepsání certifikátu pomocí řídicích speciálních znaků

K dispozici je známý problém pro žádosti certifikátu SCEP a PKCS, které obsahují název subjektu (CN) s jedním nebo více následujícími speciálními znaky jako řídicí znak. Názvy subjektů, které obsahují jeden ze speciálních znaků jako řídicí znak, mají za následek zástupce s nesprávným názvem subjektu. Nesprávný název předmětu má za následek selhání ověřování výzvou SCEP služby Intune a nevystavuje se certifikát.

Speciální znaky jsou:
- \+
- ,
- ;
- =

Pokud název předmětu obsahuje jeden ze speciálních znaků, použijte k vyřešení tohoto omezení jednu z následujících možností:

- Zapouzdří hodnotu CN, která obsahuje speciální znak, s uvozovkami.  
- Odeberte speciální znak z hodnoty CN.

Máte **například**název subjektu, který se zobrazí jako *testovací uživatel (TestCompany, LLC)* .  ZÁSTUPCE, který obsahuje CN s čárkou mezi *TestCompany* a *LLC* , představuje problém.  Problém se může vyhnout vložením nabídek kolem celé propojené sítě nebo odebráním čárky z *TestCompany* a *LLC*:

- **Přidat uvozovky**: *CN =* "testovací uživatel (TestCompany, LLC)", OU = UserAccounts, DC = Corp, DC = contoso, DC = com *
- **Odebrat čárku**: *CN = testovací uživatel (TestCompany LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

 Pokusy o odložení čárky pomocí zpětného lomítka se však nezdaří s chybou v protokolech CRP:
 
- **Řídicí znak čárky**: *CN = test User (TESTCOMPANY\\, LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

Tato chyba se podobá následující chybě:

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>Přiřazení profilu certifikátu

Přiřaďte profily certifikátů SCEP stejným způsobem jako [profily zařízení](../configuration/device-profile-assign.md) pro jiné účely. Před pokračováním však zvažte následující:

- Když přiřazujete profily certifikátů SCEP ke skupinám, nainstaluje se na zařízení soubor certifikátu důvěryhodné kořenové certifikační autority (jak je zadaný v *profilu důvěryhodného certifikátu*). Zařízení používá profil certifikátu SCEP k vytvoření žádosti o certifikát pro daný certifikát důvěryhodné kořenové certifikační autority.

- Profil certifikátu SCEP se nainstaluje jenom na zařízení, na kterých je spuštěná platforma, kterou jste zadali při vytváření profilu certifikátu.

- Profily certifikátů můžete přiřadit ke kolekcím uživatelů nebo ke kolekcím zařízení.

- Pokud chcete do zařízení po jeho registraci certifikát rychle publikovat, přiřaďte profil certifikátu ke skupině uživatelů (ne zařízení). Pokud ho přiřadíte ke skupině zařízení, budete je muset před obdržením zásad plně zaregistrovat.

- Pokud používáte spolusprávu pro Intune a Configuration Manager, v Configuration Manager [nastavte posuvník úlohy](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) pro zásady přístupu k prostředkům na **Intune** nebo **pilotní Intune**. Toto nastavení umožňuje klientům Windows 10 zahájit proces vyžádání certifikátu.

- I když vytvoříte a přiřadíte profil důvěryhodného certifikátu a profil certifikátu SCEP samostatně, musí být přiřazeni obě. Bez nainstalovaného na zařízení se zásada certifikátu SCEP nezdařila. Zajistěte, aby všechny profily důvěryhodných kořenových certifikátů byly nasazeny taky do stejných skupin jako profil SCEP.

> [!NOTE]
> Když je v zařízeních se systémem iOS přidružený profil certifikátu SCEP k dalšímu profilu, jako je například profil sítě Wi-Fi nebo VPN, zařízení obdrží certifikát pro každý z těchto dalších profilů. Výsledkem je, že zařízení s iOS má víc certifikátů dodaných žádostí o certifikát SCEP.  Pokud se požaduje jeden certifikát, musíte místo certifikátů SCEP použít certifikáty PKCS.  Je to kvůli rozdílům ve způsobu doručování certifikátů SCEP a PKCS do zařízení.

## <a name="next-steps"></a>Další kroky

[Přiřazení profilů](../configuration/device-profile-assign.md)