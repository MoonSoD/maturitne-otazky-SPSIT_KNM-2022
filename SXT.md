---
tags: [Odborné maturity]
title: SXT
created: '2022-04-28T13:17:38.585Z'
modified: '2022-05-17T09:24:40.719Z'
---

# SXT

- ### metódy a typy inštalácie Microsoft Windows Servera:
  - **metódy inštalácie WS** (médium):
    - lokálne médiá (DVD)
    - zdieľané sieťové adresáre
    - automatické zavádzanie
  
  - **typy inštalácie WS** (stav HW):
    - nová inštalácia
    - upgrade
    - migration

- ### serverové roly, ich služby a funkcie
  - serverová rola je sada sw programov(služieb), ktoré umožňujú skupine užívateľov/počítačov vykonávať určité funkcie na serveri
  - popisujú účel/použitie počítača v organizácii, môže mať priradenú jednu alebo viac rolí
  - poskytujú prístup k rôznym prostriedkom v sieti *(web servery, tlačiarne, súbory)*
  - zvyčajne vedú vlastné DB s informáciami o PC v sieti s príslušnou rolou (DDS - DB hierarchických vzťahov všetkých PC v sieti)
  - ***roly***: DHCP server, DNS server, Fax server, Hyper-V, Active Directory Domain services, Application server, File services
  - **služby:**
    - SW programy, ktoré umožňujú funkciu rolí, definujú rôzne úlohy, je možné ich zvoliť pri inštalácii (aj komu)
  - **funkcie:**
    - SW programy, ktoré nie sú priamo súčasťou rolí, ale podporujú/rozširujú funkčnosť rolí/roly alebo možnosti servera
    - Telnet klient, SSH klient, Clustering 

- ### inštalácia roly servera a jej následná modifikácia
  - serverové roly, služby a funkcie rolí môžeme konfigurovať pomocou Server Manageru
  - **S**erver **M**anager je konzola **M**icrosoft **M**anagement **C**onsole (MMC)
  - alternatívou k SM je CLI program `SeverManagerCmd.exe`

- ### základné vlastnosti operačného systému IBM AIX, jeho virtualizáciu
  - proprietárny, viacužívateľský OS od IBM založený na UNIX System V
  - beží na proprietárnom HW - IBM Power Systems (nebeží na PC arch)
  - **hlavné časti:**
    - *kernel* - jadro OS, zabezpečuje komunikáciu s HW
    - *štruktúra súborov* - hierarchická stromová štruktúra, uchováva adresáre a súbory (aj v sieti alebo na zariadení)
    - *shell* - CLI užívateľské rozhranie, interpreter príkazov, programovací jazyk
    - *nástroje* - hľadanie, porovnávanie, kompresia súborov a adresárov, hľadanie v súboroch
    - *GUI* - KDE, GNOME
  - **virtualizácia:**
    - na 1 HW beží viac inštancií AIX v logických partíciach (LPAR)
      - každá partícia má vlastný OS a vlastné zdroje
    - *Power Hypervisor* - firmvér, ktorý rozdeľuje systémové zdroje medzi partície
    - **typy partícií**:
      - *LPAR* - logické partície
      - *DLPAR* - dynamické LPAR => rozdeľovanie zdrojov medzi partície bez opätovnej aktivácie
      - *WPAR* - Workload Partitions => vytváranie partícií manažuje AIX podľa zaťaženia inštancie

- ### základné vlastnosti a časti operačného systému Oracle Solaris
  - multiuser OS založený na UNIXe, umožňuje multitasking
  - od firmy Sun, pôvodny názov SunOS, neskôr Oracle Solaris
  - **časti Solarisu**:
    - *SunOS*
    - sieťové technológie *ONC+* (Open Network Computing)
    - *GUI*
  - **časti SunOS**:
    - *kernel*
    - *shell* - príkazový procesor - rozhranie medzi systémom a používateľom
      - Bourne (default), Bash
    - *hierarchia adresárov* - začína root adresárom / 
      - obsahuje všetky lokálne a vzdialené FS
  
- ### typy inštalácií operačného systému Oracle Solaris
  - *GUI inštalácia*
  - *CLI inštalácia*
      - iba text
      - text v okne
  - *Solaris Custom JumpStart* - pomocou používateľského profilu
  - *Štandardný Solaris upgrade* - predchádzajúce 3 typy inštalácia + zálohuje veci pri upgrade
  - *Solaris Live upgrade* - vytvoré sa kópia OS, upgraduje sa kópia, po reštarte sa nabootuje do upgraded verzie - pri problémoch nabootuje do pôvodnej verzie
  - *Solaris Flash Archive* (FA)
      - bežná - referenčný systém, vytvoríme z neho Flash Archive (image), inštalujeme z FA použitím JumpStart profilu
      - Solaris WAN boot - FA umiestnený na serveri vo WAN sieti

- ### práca s príkazovým riadkom v Unixovom operačnom systéme – prehliadanie adresárovej hierarchie,vypisovanie obsahu súborov, vytváranie, kopírovanie, presúvanie, mazanie súborov a adresárov, základné prístupové práva súborov (rwx) a prístupové zoznamy (ACL)
  - *prehliadanie súborov* - `cd <cesta>`
  - *vypisovanie obsahu súborov* - `cat subor`
  - *vytváranie súborov* - `touch subor`
  - *kopírovanie súborov* - `cp subor subor1`
  - *presúvanie súborov* - `mv subor <cesta>/subor`
  - *mazanie súborov* - `rm subor`
  - *mazanie adresárov* - `rmdir adresár`
  - *základné prístupové práva* - `chmod +r subor` - pridáme práva na čítanie súboru (+x spúštanie, +w zapisovanie)

- ### oprávnenia súborov a priečinkov v Microsoft Windows Server
  - *NTFS oprávnenia*: prístupové práva pre súbory a adresáre (plný prístup, modifikácia, čítanie, otváranie zapisovanie)

- ### správa úložného priestoru a typy diskov v Microsoft Windows Server
  - vytvárenie partiícií, RAID, kvóty úložiska, zabezpečenie, šifrovanie
  - správa pomocou grafickej konzoly alebo pomocou `DISKPART` v CLI
  - grafická konzola zobrazuje VOLUMES (zväzky) a PARTITIONS (partície)

- ### možnosti virtualizácie Hyper-V v Microsoft Windows Server
  - X

- ### funkcia skriptov v Unixovských operačných systémoch, princípy práce s nimi
  - **skript**: textový súbor, ktorý automatizuje spúštanie skupín príkazov
  - 1# riadok určuje typ shellu skriptu `#!/bin/sh`
  - *skript spustíme* - `./skript1 $1 $2... $99` ($x - argumenty)
  - vráti návratovú hodnotu (0 bez chýb, 1-255 kód chýb)

- ### súborové systémy operačného systému Oracle Solaris – UFS a ZFS
  - **UFS**
    - predvolený FS pre Solaris 10, nie je transakčný
    - užívateľ vidí hierarchiu adresárov, OS vidí zoznam riadiacich štruktúr
    - pred vytvorením UFS musíme disk rozdeliť na SLICES
    - **štruktúry UFS**:
      1) *primárny superblok* - informácie o celom UFS
      2) *záložný superblok* - záloha primárneho bloku v skupine cylindrov
      3) *skupiny cylindrov* - rozdelenie FS na cylindre kvôli efektivite správy
      4) *blok skupiny cylindrov* - tabuľka o skupine cylindrov (počet súborov, voľné bloky [inodes])
    - **UFS INODE**
      - tabuľka všetkých súborov, ktorá obsahuje vlastnosti súboru a odkazy na dátové bloky
  - **ZFS**
    - transakčný FS, integruje FS a manažéra zväzkov
    - podporuje veľké úložiská, snapshoty a klony, vytvára samosprávne dáta
    - virtualizuje fyzické úložisko pomocou poolov, pool obsahuje disky/slices/súbory
    - podporuje RAID 0;1;5

- ### práca so záplatami v operačnom systéme Oracle Solaris, princípy, delenie
  - **typy**:
    - štandardné
    - odporúčané a bezpečnostné
    - firmvérové PROM
    - skupinové
  - na patche treba platenú podporu
  - nakopírujeme do /var/tmp a rozbalíme
  - príkaz `tmpatch` - správa patchov: aktualizuje systém, stiahne aktualizácie, aplikuje aktualizácie

- ### možnosti zabezpečenia Microsoft Windows Servera
  - **fyzické**:
    - fyzický prístup k serveru, politika vo firme, práva na prístup 
  - **sieťové**:
    - hrozby: neautorizovaní sieťoví užívatelia, packet sniffing
  - **vo windowse**:
    - encrypting FS, bitlocker drive encryption, windows firewall, defender
  - **autentifikácia**:
    - overenie identity, účty
  - **autorizácia**:
    - overenie práv užívateľa
  - **zabezpečenie súborov a priečinkov**:
    - prístupové práva
  - **audit**:
    - sledovanie činnosti užívateľov

- ### typy bezpečnostných hrozieb a možnosti ochrany pred nimi v Microsoft Windows Server
  - hrozby:
    - vírusy
    - spam
    - phishing - presná kópia určitej web stránky, ktorá láka od užívateľov heslá
    - spoofing - vydávanie sa za inú osobu/užívateľa
  - **ochrana na strane servera**:
    - filtrovanie obsahu
    - filtrovanie príjemcov
    - blokovanie IP adries
    - reverse DNS lookup
    - nástroje Windows servera
      - MS Exchange Server Edge Transport Server
      - MS ForeFront Protection for Exchange Server
  - **ochrana na strane klienta**:
    - junk mail filter
    - blokovaný zoznam odosielateľov
    - antivírusové programy
    - top level domains - zoznam domén

- ### vlastnosti medzi prístupovými právami súborov, Encrypting File System (EFS)
a BitLockerom
  - **Encrypting File System** (EFS):
    - súčasť Windowsu, ukladá informácie na disk v šifrovanom formáte
    - vyžaduje užívateľské certifikáty
  - **BitLocker**:
    - šifruje všetky dáta na disku, vrátane tabuľky MFT (Master File Table)
    - šifruje diskové oddiely (aj OS)
  - **Prístupové práva**
    - zabezpečujú súbor pred nechceným prístupom na úrovni OS

- ### princíp riadenia prístupu na základe rolí (RBAC) v operačnom systéme Oracle Solaris
  - root má neobmedzené práva
  - *Rola* - špeciálna identita na povolenie privilegovaných aplikácií, nie sú preddefinované 
  - *Profilové shelly* - shelly s prístupom k profilom práv
  - *Autorizácie* - prístup k obmedzeným funkciám aplikácií

- ### správu systémových služieb (SMF) v operačnom systéme Oracle Solaris
  - Service Management Facility
  - možnosť spravovať služby - vypínať/zapínať, zistiť ich stav, spravovanie chýb, logovanie
  - *Služba*:
    - zabezpečuje zdroje pre inú službu/aplikáciu, napr. nakonfigurovaná sieťová karta, pripojený FS
    - identifikátor služby FMRI - svc:/system/filesystem/root:default
      - *system* - kategória
      - *filesystem* - názov služby
      - *root:default* - inštancia
  - *Daemon svc.startd*
    - spravuje systémové služby a zabezpečuje, aby systém nabootoval to požadovaného milestonu
    - zabezpečuje spustenie správnych procesor pre daný milestone
    - štandardne bootuje do milestonu "all"
  - *Reštartér inetd*
    - pre SMF
    - manažuje stavy služieb a ich chyby
  - *Repozitár konfiguračných služieb*
    - zoznam informácií v pamäti a disku

- ### základné verzie operačného systému Microsoft Windows Server a ich vydania
  | Verzia | Rok vydania |
  | ------ | ----------- |
  | Windows 2000 | 2000
  | Windows Server 2003 | 2003
  | Windows Server 2003 R2 | 2005
  | Windows Server 2008 | 2008
  | Windows Server 2008 R2 | 2009
  | Windows Server 2012 | 2012
  | Windows Server 2012 R2 | 2013
  | Windows Server 2016 | 2016
  | Windows Server 2019 | 2018
  | Windows Server 2022 | 2021

- ### pojmy Active Directory, radič domény (Domain Controller), server
  - **Active Directory**:
    - databáza platformy WS 2003
    - obsahuje informácie o objektoch v doméne: tlačiarne, sieťové účty, skupiny, počítače...
    - poskytuje hierarchickú štruktúru na správu objektov v doméne
    - môže vykonávať dotazy na objekty v adresári, filtrovať ich 
  - **Domain Controller**:
    - počítač, ktorý slúži ako správca domény
    - autentifikuje prístup užívateľov k zdieľaným prostriedkom
    - ak klient poýaduje prístup k prostriedkom nejakého servera, ten sa najskôr opýta doménového radiča o autentifikáciu
    - vo WS je primárny (PDC) a záložný radič (BDC)

- ### monitorovanie a údržbu Microsoft Windows Servera
  - **monitorovanie**:
    - *v reálnom čase*
      - performance monitoring
      - service-level agreements
    - *historicky*
      - event logs
      - retained performance logs
    - *nástroje*
      - event viewer - analýza diania v systéme
      - network monitor
      - performance monitor - analýza výkonu systému
      - Windows System Resource Manager
      - System Center Operations manager
  - **údržba**:
    - *problémy pri štartovaní*
      - nástroje: Windows Recovery Environment, Last Known Good Configuration, Safe Mode
    - *zálohovanie dát*
      - užívateľské dáta
      - systémové dáta
    - *vyrovnanie sieťovej záťaže*
      - network load balancing
    - *failover clustering*
      - skupina serverov, ktoré spoločne pracujú na zvýšení dostupnosti služieb
      - DHCP server, File Server, Print Server, SQL Server, WINS server, DFS Namespace Server
    - *aktualizácie*
      - Windows Update
      - ochrana proti slabým miestam systému
      - efektívnejšia práca hardvéru
      - opravy chýb
      - aktualizácia: jadra OS, ovladačov, aplikácií


