---
tags: [Odborné maturity]
title: SXT
created: '2022-04-28T13:17:38.585Z'
modified: '2022-05-10T16:34:13.216Z'
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
  1) *GUI inštalácia*
  2) *CLI inštalácia*
      - iba text
      - text v okne
  3) *Solaris Custom JumpStart* - pomocou používateľského profilu
  4) *Štandardný Solaris upgrade* - predchádzajúce 3 typy inštalácia + zálohuje veci pri upgrade
  5) *Solaris Live upgrade* - vytvoré sa kópia OS, upgraduje sa kópia, po reštarte sa nabootuje do upgraded verzie - pri problémoch nabootuje do pôvodnej verzie
  6) *Solaris Flash Archive* (FA)
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

