---
title: 'PRO, DAA'
created: '2022-05-11T17:08:40.382Z'
modified: '2022-05-17T09:27:20.929Z'
---

# PRO, DAA

- ### programovacie jazyky Python, Java/C#, C, PHP, Blocky, Assembler - porovnanie 
  | jazyk | dátové typy | štruktúra | komentáre | syntax |
  | ----- | ----------- | --------- | --------- | ------ |
  | Python | dynamické | OOP  | `# koment`;`""koment""` | nepovinné bodkočiarky, oddelenie scopov (sekcií) tabulátormi, žiadne množinové zátvorky {}
  | Java/C# | statické | OOP | `// koment `;`/* koment */` | bodkočiarky, oddelenie scopov {}
  | C | statické | procedurálna  | `/* koment */` | bodkočiarky, oddelenie scopov {}
  | PHP | dynamické | OOP | `// koment`;`/* koment */` | bodkočiarky, oddelenie scopov {}
  | Blocky | dynamické | procedurálna/OOP | nemá | programovanie presúvaním blokov, nie písaním kódu
  | Assembler | ? | procedurálna | `; koment` | žiadne bodkočiarky

  - *statické dátové typy* - musíme ich predurčiť v kóde
  - *dynamické dátové typy* - jazyk si ich dokáže sám dosadiť počas runtime
  - *OOP* - Objektovo Orientované Programovanie - každá časť programu delená do tried, ktoré majú svoje konštruktory, atribúty, deštruktory, metódy (použitie jednej triedy na viac vecí abstrakciou, nemusíme sa opakovať)
  - *procedurálna štruktúra* - písanie presných inštrukcií pre kód, žiadne delenie ako pri OOP, môžeme opakovať viackrát to isté
  - *scope* - sekcia kódu 
  ```java
  // demonštrácia v jave
  class Trieda {
    public Trieda() { //konštruktor
      //toto je scope
    }

    void funkcia() { 
      //toto je scope
      int cislo = 5;

      for (int i = 0; i <= 5; i++) {
        //toto je ďalší scope
        System.out.println("Ahoj svet!");
      }
    }
  }


    ```
    ```python
    # demonštrácia v pythone
    def funkcia():
      #toto je scope
      cislo = 5

      for i in range(6):
        #toto je ďalší scope
        print("Ahoj svet!")
    ```
- ### mikrokontrolér, mikropočítač, mikroprocesor, vývojový kit, IDE
  - **mikrokontrolér** (MCU):
    - integrovaný obvod obsahujúci mikropočítač
    - na 1 čipe integrovaný procesor a pamäť, na svoju funkčnosť nepotrebuje ďalší obvod
  - **mikroprocesor**:
    - procesor v jednom integrovanom obvode
    - pomocou softvéru vykonáva zložité elektronické obvody v podobe inštrukcií
    - súčasťou väčšiny elektronických zariadení - PC, tlačiarne, rádiá, chladničky...
  - **vývojový kit**:
    - ucelená sada nástrojov na vývoj 
    - *vývojové kity*: **softvérové** (SDK - softvérové knižnice), **hardvérové** (elektronické kity na vývojové dosky)
  - **IDE** (Integrated Development Environment): 
    - integrované vývojové prostredie
    - softvér na vývoj aplikácií zložený z viacerých nástrojov v jednom GUI
    - *typicky obsahuje*: editor zdrojového kódu, automatizáciu kompilácie/spúšťania kódu, debugger a spoluprácu s gitom
    - *príklady:* Intellij IDEA, PyCharm, Visual Studio, Netbeans  

- ### vlastnosti a periférie mikrokontroléra ATmega328 a Arduina
  - **Arduino**:
    - open-source vývojová doska pre zjednodušenie programovania s mikrokontrolérom ATmega328
    - pre programátora poskytuje API rozhranie založené na jazyku C++
    - v prípade Arduino UNO obsahuje 14 digitálnych a 6 analógových I/O pinov, USB rozhranie, 9V napájanie
  - **ATmega328**:
    - jednočipový mikrokontrolér od firmy Atmel
    - obsahuje 8-bitový AVR mikroprocesor na architektúre RISC
    - neobsahuje USB rozhranie 
      | parameter | hodnota |
      | --------- | ------- | 
      | frekvencia | 20MHz |
      | flash pamäť | 32KB |
      | SRAM | 2KB |
      | I/O piny | 23 |
      | externé prerušenia | 2 |

- ### registre DDRx, PORTx a PINx
  - **DDRx** (Data Direction Register pre port x):
    - nastavuje smer dátového toku pre I/O piny
    - 1 bit inicializuje pin ako output, 0 bit ako input
    - `DDRD = 0b11110000` -> piny 1-4 output, 5-8 ako input pre port D na mikrokontroléri
  - **PORTx**: 
    - nastavuje stav výstupu portu HIGH/LOW
    - 1 bit nastaví HIGH, 0 nastaví LOW
    - `PORTD = 0b01000000` -> pin 2 HIGH, ostatné LOW
    - DDRx má prednosť pred PORTx, pin nastavený ako input nebude zmenený registrom PORTx
  - **PINx**:
    - číta stav pinu na porte

- ### periféria externé prerušenie v MCU ATmega328
  - reaguje na externé podnety zatiaľ čo beží hlavná aplikácia bez prerušenia cyklu
  - podnet môže byť napríklad forma signálu zmeny hodnoty na konkrétnom interrupt pine (HIGH -> LOW)
  - *interrupt piny*: INT0, INT1
  - ako odpoveď môžeme vyslať funkciu

- ### periféria „pin change interrupt“ v MCU ATmega328
  - oproti externému prerušeniu reaguje na podnet na akomkoľvek pine
  - čítanie prerušenia nastavujeme však na celý port a potom vyberáme konkrétny pin

- ### periféria AD prevodník v MCU ATmega328
  - prepája analógový a digitálny signál, dokáže ich vzájomne spracovať 
  - analógový signál rozdelí na 1024 rôznych digitálnych hodnôť
  - 10 bitový

- ### ako generuje MCU kvázi analógový signál
  - pomocou PWM (Pulse-Width Modulation) na jednej konštantnej frekvencii s rôznymi pulznými šírkami

- ### komunikačné protokoly SPI, UART, TWI
  - **SPI** (Serial Peripheral Interface):
    - sériové rozhranie na komunikáciu medzi zariadeniami v nízkej vzdialenosti
    - princíp ***Master*** > *Slave*
    - master komunikuje s viacerými slaves, ovláda ich, všetka komunikácia prechádza cez mastra
  - **UART** (Universal Asynchronous Receiver/Transmitter):
    - sériová komunikácia 2 zariadení cez RX (receive) a TX (transmit) piny
    - RX príjma dáta z TX pripojeného zariadenia, TX odosiela dáta do RX
  - **TWI**/I2C (Two-Wire Interface):
    - sériová komunikácia cez piny SDA/SCL
    - podporuje princíp ***Master*** > *Slave* a Multi-master 
    - master začne komunikáciu, identifikuje pripojené slaves cez adresu a posiela im dáta

- ### rozdiel medzi aritmetickým súčtom, logickým súčtom, aritmetickým súčinom a logickým súčinom dvoch binárnych čísel
  - **artimetický súčet**:

      | B | A | Y
      | - | - | - 
      | 0 | 0 | 0
      | 0 | 1 | 1
      | 1 | 0 | 1
      | 1 | 1 | 1 0
  - **logický súčet** (OR):

      | B | A | Y 
      | - | - | -
      | 0 | 0 | 0
      | 0 | 1 | 1
      | 1 | 0 | 1
      | 1 | 1 | 1
  - **logický súčin** (AND):

      | B | A | Y
      | - | - | -
      | 0 | 0 | 0
      | 0 | 1 | 0
      | 1 | 0 | 0
      | 1 | 1 | 1

- priame prevody medzi číselnými sústavami (bin., dec., hex.)
  - *128* /dec/ -> bin
    - 128 / 2 = 64, zvyšok 0;
    - 64 / 2 = 32, zvyšok 0;
    - 32 / 2 = 16, zvyšok 0;
    - 16 / 2 = 8, zvyšok 0;
    - 8 / 2 = 4, zvyšok 0;
    - 4 / 2 = 2, zvyšok 0;
    - 2 / 2 = 1, zvyšok 0;
    - 1 / 2 = 0 (0.5), zvyšok 1
    - 128 v binárnej sústave = `1000 0000`, číslo spisujeme od konca
  - *1111 0000* /bin/ -> dec 
    - 128 64 32 16 8 4 2 1
    - 128*1 + 64*1 + 32*1 + 16*1 + 8*0 + 4*0 + 2*0 + 1*0 = `240`
  - *94* /dec/ -> hex
    - 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
    - 94 / 16 = 5, zvyšok 14 -> E;
    - 5 / 16 = 0, zvyšok 5, -> 5;
    - 94 v hexadecimálne sústave = `5E`, číslo spisujeme od konca, ale ak výsledok je 0, tak píšeme 5 pred E
  - *E9A* /hex/ -> dec
    - E = 14, 9 = 9, A = 10
    - 14 * 16^2 + 9 * 16^1 + 10 * 16^0 = `3738`

- nastavenie celého registra a len jedného bitu (do log.0 / log.1) v jazyku C
  - *ADRESA = hodnota*
    - **celý register**
      - do log. 0 -> `DDRB = 0b00000000;` / `DDRB = 0;` / `DDRB = 0x0;` 
      - do log. 1 -> `DDRB = 0b11111111;` / `DDRB = 255;` / `DDRB = 0xFF;`
    - **jeden bit v registri**
      - do log. 0 - `ADRESA &= ~(1<<POZICIA_BITU)` 
        ```c
        DDRB = 0b11111111;
        DDRB &= ~(1<<2); //DDRB nadobudlo hodnotu 0b11011111
        ```
      - do log. 1 - `ADRESA |= 1<<POZICIA_BITU` 
        ```c
        DDRD = 0b00000000;
        DDRD |= 1<<2; //DDRD nadobudlo hodnotu 0b00100000
        ```

- ### platforma Raspberry Pi
  - séria jedno-doskových minipočítačov pôvodne určené pre vzdelávanie v informatike
  - **hardvér**:
    - *procesory*: od Broadcom
    - *RAM*: od 256MB - 8GB (Pi 4B)
    - *úložisko*: slot pre SD kartu
    - *napájanie*: 5V; 3A 
    - *porty*: USB, HDMI, Ethernet, 40 pinov (GND, 3.3V, 5V, GPIO, SPI, UART)
    - Wi-Fi, Bluetooth 
  - **softvér**:
    - Raspberry Pi OS (pôvodne Raspbian) - operačný systém založený na linux distribúcii Debian

- ### platforma ESP32 a Arduino
  - **Arduino**:
    - open-source vývojová doska pre zjednodušenie programovania s mikrokontrolérom ATmega328
    - pre programátora poskytuje API rozhranie založené na jazyku C++
    - poskytuje IDE pre vývoj (Arduino IDE v1, v2)
    - v prípade Arduino UNO obsahuje 14 digitálnych a 6 analógových I/O pinov, USB rozhranie, 9V napájanie, AD prevodník, PWM piny, SPI, I2A, UART piny
  - **ESP32**:
    - vývojová doska od firmy Espressif s mikrokontrolérom a integrovaným Wi-Fi a Bluetooth modulom
    - 34 GPIO pinov, SPI, I2C, UART, 12 bitový AD prevodník, PWM

- ### platforma Lego mindstorms alebo micro:bit
  - **Lego mindstorms**
    - hardvérová a softvérová platform na vývoj programovateľných robotov z Lego blokov
    - obsahuje hlavnú jednotu, vstupné senzory (infračervené, zvukové), rôzne stavebné bloky ako kolesá, rámy, pásy a periférie (displeje)
    - verzie NXT, EV3
    - poskytuje blokové vývojové prostredie pre jednoduché naprogramovanie robota, takisto je možné ich programovanie v jazyku C


- ### polia a štruktúry v programovaní, ich inicializácia (syntax), ich vlastnosti, použitie, rozdiely v jazyku C/C++
  - *polia* (arrays):
    - pole je premenná, ktorá uchováva vyšší počet hodnôt rovnakého dátového typu
    - pre deklaráciu musíme zadefinovať veľkosť poľa (maximálny počet hodnôt)
    ```c++
    int znamky[5] = {1, 3, 5, 5, 4};
    printf("Prva znamka: %d", znamky[0]); //vypíše "Prva znamka: 1"
    ```
  - *štruktúry* (structs):
    - dátový typ zadefinovaný programátorom
    ```c++
    struct Film {
      int rok;
      String meno;
    }

    int main() {
      struct Film PrvyFilm; //deklaruje strukturu filmu PrvyFilm

      PrvyFilm.rok = 1964; //nastavi rok daneho filmy
      PrvyFilm.meno = "Goldfinger"; //nastavi meno daneho filmu

      return 0;
    }
    ```
    - v C++ oproti C môžeme vytvárať konštrutory, settery, gettery, funkcie, statické premenné, 

- ### spôsob práce s jednorozmerným, viacrozmerným a textovým poľom v C/C++
  - **jednorozmerné pole**:
    ```c++
    int znamky[5] = {4, 5, 1, 2, 3}; //vytvorenie pola s integermi
    std::cout << znamky[0]; //vypise znamku "4"
    std::cout << znamky[4]; //vypise znamku "3"

    znamky[0] = 5; //prepise prvu hodnotu z pola na "5"
    std::cout << znamky[0] //vypise znamku "5"
    ```
  - **viacrozmerné pole**:
    - funguje na princípe matematickej matice
    ```c++
    //prvá hodnota je počet riadkov, druhá počet stĺpcov
    int cisla[2][5] = { 
      { 1, 2, 3, 4, 5 },
      { 6, 7, 8, 9, 10 }
    };
    std::cout << znamky[1][0]; //vypíše číslo "6"
    std::cout << znamky[0][4]; //vypíše číslo "5"

    znamky[0][4] = 11; //zmení číslo 5 na číslo 11
    std::cout << znamky[0][4] //vypíše číslo "11"
    ```
    - môže mať aj viac dimenzií ako 2
  - **textové pole**:
    - pole znakov -> v C stringy neexistujú, preto sa používa textové pole
      ```c
      char veta[] = "Ahoj svet"; //to isté ako nižšie
      char veta[9] = {"A", "h", "o", "j", " ", "s", "v", "e", "t"}; 
      ```
    - v C++ máme už vyhradený dátový typ "string"
      ```c++
      string veta = "Ahoj svet";
      ```

- ### dátové typy a druhy komentárov v jazyku C/C++
  | typ | popis | deklarácia |
  | --- | ----- | ---------- |
  | Boolean | pravdivostná hodnota 1/0 true/false | bool |
  | Character | 1 znak - písmeno/číslo... | char |
  | Integer | celé číslo | int |
  | Floating point | desatinné číslo, 6-7 miest | float |
  | Double floating point | desatinné číslo, 15-16 miest | doube |
  | Valueless | bez návratovej hodnoty | void |
  | Wide character | znak, ktorý zaberá viac ako 1 byte | wchar_t

  - komentáre: 
    - jednoriadkové
    ```c
    int i = 5;
    //toto je jednoriadkový komentár v kóde
    printf("Hello world");
    ```
    - blokové 
    ```c
    int j = 10;
    /* toto je komentár, 
    ktorý môže siahať
    do viacerých riadkov v kóde */
    printf("Hello world!");
    ```


- ### využitie konštánt, makier a knižníc v jazyku C/C++
  - *konštanta*
    - premenná, ktorá sa nedá počas behu programu prepísať (na čítanie/read-only)
    - používame za predpokladu, že nechceme zásah do premennej /prípadne aj z tretej strany/
    ```C
    const int cislo = 1;
    ```
  - *makro*
    - časť kódu/funkcia, za ktorú sa počas kompilácie dosadí definovaná hodnota daného makra
    - môže mať aj argumenty
    ```C
    #define SCITAT (a, b) (a) + (b) 
    ```
  - *knižnica*
    - balík predpísaného kódu, ktorý ušetrí programátorovi čas a stabilitu programu
    - bývajú písané tretími stranami na zjednodušenie určitých cieľov v kóde
    ```C
    #include <iostream>
    ```

- ### činnosť operátorov +=, ++, &&, ||, =, ==, !=, %, &, |, >>, ^
  | operátor | popis | príklad |
  | -------- | ----- | ------- |
  | += | pridanie hodnoty na pravej strane na ľavú stranu spolu s navrátením už pridanej hodnoty | <pre lang="C">int i = 5; <br>i += 2; // hodnota bude 7</pre> |
  | ++ | zvýšenie hodnoty o 1 s priradením  | <pre lang="C">int i = 5; <br>cout << i++ //vypíše 5 (vráti a potom zvýši hodnotu premennej)</pre> |
  | && | logický AND - a -> návratová hodnota bude pravdivá len pokiaľ podmienky na oboch stranách budú pravidivé | <pre lang="C">int i = 5; <br>int j = 8; <br>bool plati = i == 5 \&\& j == 8; //vrati hodnotu true</pre> |
  | \|\| | logický OR - alebo -> návratová hodnota bude pravdivá ak aspoň podmienka z 1 strany bude pravdivá | <pre lang="C">int i = 5; <br>int j = 8; <br>bool plati = i == 5 \|\| j == 6; //vrati hodnotu true</pre> |
  | = | priradenie hodnoty pravej strany na ľavú stranu | <pre lang="C">int i = 5;</pre> |
  | == | binárne porovnanie ľavej a pravej strany, pokiaľ sa rovnajú vráti true | <pre lang="C">int i = 5; <br>bool plati = i == 5; //vrati hodnotu true |
  | != | negované binárne porovnanie ľavej a pravej strany, pokiaľ sa rovnajú vráti false | <pre lang="C">int i = 5; <br>bool plati = i != 5; //vrati hodnotu false |
  | % | modulo -> vráti hodnotu zvyšku delenia ľavej strany pravou stranou | <pre lang="C">int i = 3 % 4; //vráti 3 |
  | & | bitový AND - vráti hodnotu bitového súčinu ľavej a pravej strany | <pre lang="C">int i = 5; <br>int j = 9; <br>int bitovy_sucin = i & j; //vrati hodnotu 1 |
  | \| | bitový OR -  vráti hodnotu bitového súčtu ľavej a pravej strany | <pre lang="C">int i = 5; <br>int j = 9; <br>int bitovy_sucet = i \| j; //vrati hodnotu 13 |
  | >> | bitový posun | |
  | ^ | XOR | |

- ### vlastná funkcia, ktorá navráti...
  - x

- ### príklad na zloženú podmienku obsahujúcu operátory && a ||
  ```c++
  int i = 5; 
  bool existuje = true;

  if (i == 4 && existuje || i == 5) {
    std::cout << "podmienka presla!";
  }
  ```
  - ak `i = 4` a zároveň `existuje = true`, alebo ak `i = 5`, tak sa podmienka vykoná 
  - pokiaľ `i = 6` a `existuje = false`, tak sa podmienka nevykoná

- ### vetvenie v programovaní, druhy vetvení, ich všeobecné tvary (syntax), ich vlastnosti a rozdiely
  - #### *if, else, else if*
    - ak `znamka = 1`, tak sa vypíše text *"Skvela praca!"*, pokiaľ však toto naplatí, tak program prejde na ďalšiu vetvu, v našom prípade "**else if**": pokiaľ `znamka = 5`, tak sa vypíše *"Skoda, skus nabuduce..."*, ak neplatí ani jedno, tak sa v akomkoľvek prípade vykoná vetva "**else**", teda vypíše sa *"Dobry vykon."*
      ```c
      if (znamka == 1) {
        std::cout << "Skvela praca!";
      } else if (znamka == 5) {
        std::cout << "Skoda, skus nabuduce...";
      } else {
        std::cout << "Dobry vykon.";
      }
        ```
      
- ### situácia, kedy je a kedy nie je nutné zapisovať blokové zložené zátvorky {}
  - zložené zátvorky sú preferované na oddelenie častí programu, písať ich nemusíme v prípade:
    - single statement podmienky a cykly (pokiaľ nasleduje len 1 inštrukcia):
      ```c
      if (plati) 
        cout << "Ahoj svet!";
      
      for (int i = 0; i < 100; i++) 
        cout << i;

      while (plati) 
        cout << "Ahoj svet!";
      ```
      **nemôžeme vynechať** (musíme už písať zátvorky v prípade viacerých inštrukcií):
      ```c
      if (plati) {
        cout << "Ahoj svet!";
        cout << "Vitaj!";
      }
      ```

- ### cyklus v programovaní, druhy cyklov, ich všeobecné tvary (syntax), ich vlastnosti a rozdiely
  - štruktúra v programovaní, ktorá opakuje zadefinované inštrukcie pokiaľ platí jej podmienka pred každým krokom
  - *typy*:
    - for loop:
      - pokiaľ vieme koľko krát chcem cyklus spustiť
      - `for (1; 2; 3) {}` 
        - časť 1 sa vykoná 1x pred spustením cyklu
        - časť 2 určuje podmienku, ktorá musí platiť pre spustenie cyklu
        - časť 3 sa vykoná po každom prebehnutí cyklu
        ```c
        for (int i = 0; i < 100; i++) {
          cout << i;
        }
        ```
    - while loop:
      - vykonáva sa pokiaľ podmienka platí
      - `while (podmienka) {}`
        ```c
        while (i < 3) {
          cout << "Hello";
        }
        ```
    - do/while loop:
      - pred začatím 1x vykoná kód v bloku
      - ďalej sa vykonáva pokiaľ podmienka platí
        ```c
        do {
          cout << "Hello";
        } while (i > 3);
        ```
    
- ### objektové programovanie 
  - koncept programovania založený na objektoch (triedach), ktoré môžu obsahovať dáta a kód,
  dáta vo forme vlastností (properties) a kód vo forme metód (methods)
  - metódy môžu modifikovať vlastnosti daného objektu (triedy), vlastnosti dostávame z objektu this (predstavuje aktuálnu triedu)
  - poskytuje dedičnosť (abstract class, interface), ochranu dát (private, protected, public vlastnosti)
  - objekt sa inicializuje konštruktorom

- ### deklarácia triedy a tvorba inštancie 
  ```java
  //deklarácia triedy s konštruktorom
  class Student {
    //vlastnosť
    private int znamka;

    //konštruktor
    public Student(int dosiahnutaZnamka) {
      this.znamka = dosiahnutaZnamka;
    }

    //metóda
    void vypisatZnamku() {
      System.out.println(this.znamka);
    }
  }

  //vytvorenie inštancie triedy student s vyplneným konštruktorom s dosiahnutaZnamka = 2
  Student student1 = new Student(2);
  //použitie metódy vypisatZnamku, ktorá vypíše zadanú známku v konštruktore
  student1.vypisatZnamku();
  ```

- ### pojmy: konštruktor, deštruktor, metóda, atribút, preťažovanie metód
  - **konštruktor**:
    - špeciálna metóda určená na vytvorenie (inicializáciu objektu), môžeme v ňom definovať počiatočné vlastnosti
  - **deštruktor**:
    - špeciálna metóda určená na zmazanie objektu z pamäte, môžeme v ňom zadať kód, ktorý chceme vykonať na zmazenie objektu
  - **metóda**:
    - blok kódu, ktorý sa po jeho zavolaní vykoná
    - metódy sa deklarujú len ako funkcie v triedach
  - **atribút**:
    - vlastnosť objektu, ktorú môžeme modifikovať a chrániť pred prístupom z iného objektu
  - **preťažovanie metód**:
    - deklarácia viacerých metód pod rovnakým názvom, no s inými argumentami
    ```java
    //deklarácia triedy s konštruktorom
    class Student {
      //vlastnosť
      private int znamka;

      //konštruktor
      public Student(int dosiahnutaZnamka) {
        this.znamka = dosiahnutaZnamka;
      }

      //metóda
      void vypisatZnamku() {
        System.out.println(this.znamka);
      }

      //preťažená metóda
      void vypisatZnamku(int znamka) {
        System.out.println(znamka);
      }
    }

    //vytvorenie inštancie triedy student s vyplneným konštruktorom s dosiahnutaZnamka = 2
    Student student1 = new Student(2);
    //použitie metódy vypisatZnamku, ktorá vypíše zadanú známku v konštruktore
    student1.vypisatZnamku();
    //použitie preťaženej metódy vypisaťZnamku, ktorá vypíše zadaná známku ako argument v metóde
    student1.vypisatZnamku(3);
    ```

- ### garbage collection, zápis dát do zásobníka (stack) a haldy (heap)
  - **garbage collection**:
    - automatizovaná správa pamäte v programe
    - GC sa snaží o uvoľnenie pamäte, ktorá bola vyhradená programom, no už sa nepoužíva /neexistuje k nej referencia/ (garbage/odpad)
  - **zápis dát do zásobníka (stack) a haldy (heap)**:
    - **stack**:
      - vyhradenie do blokov pamäte, vyhradené miesto je automaticky známe už počas kompilácie a nemôžeme ho upraviť
      - ukladá primitívne dátové typy (byte, short, int, long, float, double, boolean, char)
    - **heap**:
      - miesto v pamäti je vyhradené inštrukciami programu, môžeme ho alokovať a de-alokovať podľa nášho uváženia
      - ukladá objekty (triedy <-> polia, stringy)

- ### vytvorte triedu xyz, ktorá obsahuje atribúty abc. Hodnoty atribútov sa budú dať nastaviť cez bezparametrický konštruktor, konštruktor s parametrami a samostatné metódy pre každý parameter
  - demonštrácia v jave
    ```java
      class Xyz {
        int a;
        String b;
        double c;

        //bezparemetrický konštruktor
        public Xyz() {
          this.a = 5;
          this.b = "Ahoj";
          this.c = 3.14;
        }

        //konštruktor s parametrami
        public Xyz(int a, String b, double c) {
          this.a = a;
          this.b = b;
          this.c = c;
        }

        public void printA() {
          System.out.println(a);
        }

        public void printB() {
          System.out.println(b);
        }

        public void printC() {
          System.out.println(c);
        }
      }
      ```

- ### spúšťacia trieda, v ktorej využijete triedu xyz a jej metódy, štruktúra a činnosť vytvoreného programu
  - demonštrácia v jave
    ```java
    //špúšťacia trieda
    class Main {
      //spúšťacia metóda
      public static void main(String[] args) {
        Xyz xyz1 = new Xyz(2, "Hey", 2.54);
        xyz1.printA(); //vypíše 2
        xyz2.printB(); //vypíše "Hey"
        xyz3.printC(); //vypíše 2.54
      }
    }
    ```

- ### metóda potrebné pre ... a ošetrite stav, aby ...
  - x

- ### štruktúrované, objektovo orientované a komponentové programovanie, analyzujte a porovnajte tieto tri základné vetvy programovania
  - **štruktúrované**:
    - rozdeľujeme program to menších modulov pre lepšiu prehľadnosť a možnosť recyklácie častí kódu (modulov)
    - podporované väčšinou moderných jazykov
  - **objektovo orientované**:
    - koncept programovania založený na objektoch (triedach), ktoré môžu obsahovať dáta a kód,
  dáta vo forme vlastností (properties) a kód vo forme metód (methods)
    - metódy môžu modifikovať vlastnosti daného objektu (triedy), vlastnosti dostávame z objektu this (predstavuje aktuálnu triedu)
    - poskytuje dedičnosť (abstract class, interface), ochranu dát (private, protected, public vlastnosti)
    - objekt sa inicializuje konštruktorom
  - **komponentové**:
    - rozdeľujeme program na individuálne funkčné komponenty, ktoré reprezentujú svoju úlohu
    - možná recyklácia, dedičnosť 
    - oproti objektovo orientovanému programovaniu nezáleží na usporiadaní funkcií a štruktúry programu

- ### pojem dedičnosť, prístupové metódy
  - **dedičnosť**:
    - možnosť prebrať (zdediť) atribúty a metódy iného objektu
    - dedičné objekty delíme na:
      - parent (rodič) - hlavný objekt, ktorý môžeme zdediť
      - child (dieťa) - objekt, ktorý dedí rodiča
  - **prístupové metódy**:
    - špecifikácia prístupu k atribútom a metódam (členom) objektu

    | typ | popis |
    | --- | ----- |
    | public | verejný prístup k členom, aj z iného objektu 
    | private | prístup k členom len z vnútra objektu
    | protected | prístup k členom len z vnútra objektu a z objektov, ktoré ho dedia

- ### nastavte prístupové metódy tak, aby ...
  - x

- ### demonštrujte prácu s touto triedou
  - x

- ### najpoužívanejšie skriptovacie jazyky a databázy pre tvorbu www stránok
  - **skriptovacie jazyky**:
    - PHP - Hypertext Preprocessor -> serverový skriptovací jazyk na tvorbu dynamických webstránok
    - JavaScript -> klientský skriptovací jazyk určený hlavne pre tvorbu webstránok
  - **databázy**:
    - MySQL
    - MariaDB
    - MongoDB
    - PostgreSQL
    - MSSQL
    - OracleDB

- ### LAMP - webserver Linux, Apache, MySQL, PHP
  - softvérový balík (stack) určený na stavbu webových aplikácií
  - **L**inux **A**pache **M**ySQL **P**HP:
    - **Linux**: OS, na ktorom bežia naše LAMP komponenty 
    - **Apache**: webový server na hosting web stránok
    - **MySQL**: databázový server 
    - **PHP**: serverovo-orientovaný jazyk na tvorbu dynamických webstránok   

- ### základné požiadavky pri výbere webhostingu
  - cena (1 - 30€), 
  - priestor na disku (10GB SSD - neobmedzený),
  - bandwidth (neobmedzený), RAM (256MB - 4GB), 
  - DDOS ochrana (300Gb - 15Tb), 
  - spoľahlivosť (podpora) 

- ### práca s phpMyAdmin
  - softvérový nástroj na administráciu MySQL/MariaDB databáz na webe
  - môžeme vytvárať exporty, importovať dáta, vykonávať SQL príkazy v GUI (INSERT, DELETE, DROP, CREATE TABLE, UPDATE)

- ### CMS systémy (redakčné systémy)
  - **C**ontent **M**anagement **S**ystem
  - intuitívny softvér na správu obsahu na webstránke bez profesionálnych znalostí
  - väčšinou umožňujú správu článkov, zmenu vzhľadu (témy/template) a správu užívateľov 
  - **najznámejšie redakčné systémy**
    - WordPress
    - PHP-Fusion
    - Drupal
    - Joomla

- ### význam a použitie skriptovacích jazykov
  - určené pre automatizáciu rôznych úkonov, ktoré by museli byť v opačnom prípade človekom
  - skriptovacie jazyky sú interpretované počas behu programu, takže nie sú vopred kompilované, čiže zmeny v programe nemusia byť prekompilované, stačí reštartovať program/script 
  - Bash, Powershell, Python, JavaScript, Lua, PHP

- ### rozdiel medzi programovacími jazykmi na strane klienta a servera
  - **strana klienta**:
    - možnosť automaticky vykonávať inštrukcie na zariadení klienta (napr.: animácie na webstránke)
  - **strana servera**:
    - vykonávanie intrukcií na serveri, o ktoré si môže klient požiadať (práca s databázou a riadenie prístupu)

- ### činnosť pripraveného programu v uloženom súbore
  - x

- ### upravte súbor aaa.php pre nové XML bbb.xml
  - x

- ### pojem validita HTML kódu
  - úroveň správnosti a dodržania konvencií HTML kódu pre lepšie spracovanie webovým prehliadačom
  - dodržanie hierarchie nadpisov, použitie alt atribútov, použitie favicon, zadanie titulov, správne uzatváranie elementov

- ### štruktúru HTML a CSS šablóny v pripravenom súbore
  - x

- ### práca s príkazmi pre úpravu stránky, textu, obrázkov, odkazov, tabuliek, grafických prvkov
  - `<title>Titulok dokumentu</title>` - titulok dokumentu
  - `<h1>toto je nadpis prvej úrovne<h1>` - nadpisy môžu byť úrovne 1 - 6
  - `<p>toto je obyčaný text</p>` - paragraf/obyčajný text
  - `<img src="/cesta/k/obrazku.png" alt="alternativny text pri nespravnom zobrazeni" />` - pripojenie obrázku do HTML dokumentu
  - `<a href="/cesta/k/dokumentu.html" rel="noreferer">` - hypertextové prepojenie (externý link)
  - nezoradený zoznam
    ```html
    <ul>
      <li>Vstup v nezoradenom zozname</li>
      <li>Vstup v nezoradenom zozname 2</li>
    </ul>
    ``` 
  - zoradený zoznam
    ```html
    <ol>
      <li>Vstup v nezoradenom zozname</li>
      <li>Vstup v nezoradenom zozname 2</li>
    </ol>
    ``` 
  - `<li>vstup</li>` - vstup zoznamu
  - tabuľky
      ```html
      <table>
        <tr> <!-- prvý riadok v stĺpci (aj hlavička) -->
          <th>stĺpec v hlavičke</th>
          <th>stĺpec v hlavičke 2</th>
        </tr>
        <tr>
          <td>stĺpec 1 v druhom riadku</td>
          <td>stĺpec 2 v druhom riadku</td>
        </tr>
      </table>
      ```

- ### pojmy: doména, URL, webhosting, browser, server, frontend, backend
  - **doména**:
    - reťazec znakov (string) ktorý identifikuje origanizáciu na internete
  - **URL** (Uniform Resource Locator):
    - webová adresa, refrencia k zdrojom na webe, ktorá špecifikuje jej polohu na internete pomocou reťazca
    - napr.: `http://www.example.com/questions/3456/my-document?arg=nope#hello`
      - http -> schéma/protokol
      - www -> subdoména
      - example.com -> doména
      - /questions/3456/my-document/ -> cesta
      - ?arg=nope -> query
      - #hello -> fragment
  - **webhosting**
    - typ internetovej hostovacej služby na hosting webstránky pre klientov
  - **browser**
    - prehliadač, internetový prehliadač (Google Chrome, MS Edge, MS IE, Safari, Opera, Firefox)
    - umožňuje prehliadať a zobrazovať webstránky
  - **server**
    - zariadenie, ktoré poskytuje klientom určité služby (webový server)
  - **frontend**
    - klientská časť webstránky/aplikácie, s ktorou má užívateľ nejakú priamu interakciu
    - HTML, CSS, JavaScript
  - **backend**
    - serverová časť webstránky/aplikácie, ktorá zabezpečuje prácu s databázou a riadi prístup a správu údajov
    - časť s ktorou užívateľ nemá priamu interakciu
    - PHP, MySQL, Apache

- ### HTML a jeho základnú štruktúru
  - Hypertext Markup Language
  - štandardný značkovací jazyk na webové stránky
  - štruktúra:
    ```html
    <html lang="sk">
      <head>
        <title>Titulok stránky</title>
        <link rel="stylesheet" type="text/css" href="style.css"> <!-- import css súboru style.css -->
      </head>
      <body>
        <h1>Nadpis úrovne 1...</h1>
      </body>
    </html>
    ``` 

- ### optimalizáciu pre vyhľadávače (SEO) 
  - SEO -> Search Engine Optimization
  - prispôsobenie webstánky pre optimálny výkon zobrazenia vo webových vyhľadávačoch (napr.: Google, Bing, DuckDuckGo)
  - podľa kvality SEO sa webstránka zobrazuje vyššie v rebríčkoch, zabezpečuje vyššiu relevanciu stránky

- ### základné príkazy HTML
  - `<html>` - skelet html súboru, vždy obsahuje všetky ostatné tagy
  - `<head>` - hlava súboru, modifikácie a nastavenia html dokumentu
  - `<title>` - titulok dokumentu
  - `<link>` - prepojenie dokumentu s iným (vzdialeným) súborom
  - `<body>` - telo dokumentu, obsah HTML dokumentu, ktorý tvorí rozhranie pre užívateľa
  - `<h1> - <h6>` - nadpisy úrovne 1 - 6
  - `<p>` - paragraf/obyčajný text
  - `<img>` - pripojenie obrázku do HTML dokumentu
  - `<a>` - hypertextové prepojenie (externý link)
  - `<ul>` - nezoradený zoznam
  - `<ol>` - zoradený zoznam
  - `<li>` - vstup zoznamu

- ### vytvorenie html súboru z pripraveného súboru
  - x

- ### štruktúra vytvorenej stránky
  - x

- ### katalógy a vyhľadávače
  - **internetové katalógy**
    - weby, kam ľudia registrujú svoje web stránky
    - web stránky delia do rôznych kategórií 
  - **vyhľadávače**
    - web stránka, ktorá prechádza všetky weby a indexuje ich URL adresy, pričom ich zoraďuje podľa relevancie za rôznych kritérií... SEO optimalizácia, návštevnosť, dĺžka pobytu užívateľa na stránke
    - populárne vyhľadávače: Google, Bing, DuckDuckGo

- ### CSS - kaskádny štýl, jeho vlastnosti a základnú štruktúru
  - **C**ascading **S**tyle **S**heets
  - štýlovací jazyk na úpravu dizajnu HTML dokumentov
  - funguje na príncípe selektorov a vlastností:
    - **selektory:** tagy (h1), classy (.main__text), id (#start)
    - základné vlastnosti, ktoré môžeme selektorom priradiť:
      - `background-color: #fff`
      - `color: #000`
      - `text-align: center` 
      - `font-family: Verdana`
      - `font-size: 16px`
      - `padding: 8px`
      - `margin: 8px`
    - príklad použitia:
      ```css
      h1 {
        color: #888;
        font-size: 32px;
      }
      ```
    - vlastnosti sa píšu sekvenčne

- ### štruktúra pripraveného CSS v súbore
  - x

- ### práca s CSS pre úpravu stránky, textu, odkazov a tabuliek v súbore 
  - x

- ### pojem databáza a najznámejšie druhy databáz
  - štruktúrovaný zoznam údajov uložené elektronicky
  - druhý databáz:
    - **SQL** (ukladajú údaje do štruktúrovaných tabuliek):
      - pomocou jazyka SQL vhodnejšie na zložité vzťahy medzi údajmi
      - **najznámejšie**:
        - MySQL
        - MSSQL
        - PostgreSQL
        - MariaDB
    - **NoSQL** (ukládajú údaje do zoznamu dokumentov, ktoré majú vlastný identifikátor):
      - lepšia horizontálna škálovateľnosť (pre veľmi vysoké objemy dát)
      - **najznámejšie**:
        - MongoDB
        - CouchDB
        - FaunaDB
        - Firestore
    
- ### dotazovací jazyk SQL a dátové typy
  - Structured Query Language
  - štruktúrovaný dotazovací jazyk na správu údajov v SQL databázach

  | typ | popis 
  | --- | ----- 
  | VARCHAR(max_veľkosť) | reťazec textu určitej dĺžky
  | TEXT(max_veľkosť) | reťazec textu o veľkosti maximálne 65535 B
  | INT(max_veľkosť) | celé číslo
  | FLOAT(max_veľkosť, počet_desatinných_miest) | desatinné číslo
  | DATE | dátum
  | TIMESTAMP | časová pečiatka
  | BOOLEAN | true/false

- ### základné príkazy jazyka SQL
  - create database
  - insert
  - select
  - delete
  - drop 

- ### práca s príkazmi pre vytváranie, mazanie a úpravu databázy a tabuliek
  - create database - vytvorenie databázy ->
    ```sql
    CREATE DATABASE Skola
    ```
  - create table - vytvorenie tabuľky ->
    ```sql 
    CREATE TABLE Studenti (
      id INT NOT NULL,
      meno VARCHAR(32),
      priezvisko VARCHAR(32),
      datum_narodenia DATE,
      PRIMARY KEY (id)
    )
    ```
  - insert - vkladanie údajov -> 
    ```sql 
    INSERT INTO <TABULKA> (STLPEC1, STLPEC2, ...) VALUES (HODNOTA_STLPCA1, HODNOTA_STPLCA2) 
    ```
  - select - vyberanie údajov -> 
    ```sql
    SELECT STLPEC1, STLPEC2 FROM <TABULKA> WHERE STLPEC1="Ahoj"
    ```
  - update - úprava údajov ->
    ```sql
    UPDATE <TABUĽKA> SET STLPEC1 = "Ahoj", STLPEC2 = 5, ... WHERE STLPEC1 = "Cau"
    ```
  - delete - zmazanie vstupu v taubľke ->
    ```sql
    DELETE FROM <TABUĽKA> WHERE STLPEC1 = "Ahoj"
    ```
  - drop table - zmazanie tabuľky ->
    ```sql
    DROP TABLE Studenti
    ```
  - drop database - zmazanie databázy ->
    ```sql
    DROP DATABASE Skola
    ```

- ### práca s príkazmi pre získanie dát z databázy, získanie dát z viacerých tabuliek, výber riadkov a stĺpcov v tabuľke, spájanie viacerých tabuliek
  ```sql
  SELECT meno, vek 
  FROM Studenti
  INNER JOIN Znamky
  ON Znamky.id = Studenti.id
  LIMIT 50 OFFSET 20
  ```

- ### skriptovacie jazyky (JavaScript, PHP, …)
  - **JavaScript**:
    - moderný, interpretovaný, nekompilovaný skriptovací jazyk určený pre klientské operácie 
    - podporuje OOP, štruktúrované aj komponentové programovanie
  - **PHP**:
    - interpretovaný, nekompilovaný skriptovací jazyk určený pre serverové operácie (manipuláciu s údajmi, s databázou a s riadením prístupu k údajom)
    - podporuje OOP a štruktúrované programovanie 
  - **Python**:
    - interpretovaný, nekompilovaný skriptovací jazyk určený pre široké využitie na strane servera, aj klienta
    - podporuje OOP a štruktúrované programovanie

- ### rozdiel medzi backend a frontend aplikáciou a jazyky využívané pre jednotlivé aplikácie
  - frontend
    - klientská časť webstránky/aplikácie, s ktorou má užívateľ nejakú priamu interakciu
    - HTML, CSS, JavaScript
  - backend
    - serverová časť webstránky/aplikácie, ktorá zabezpečuje prácu s databázou a riadi prístup a správu údajov
    - časť s ktorou užívateľ nemá priamu interakciu
    - PHP, MySQL, Apache

- ### vkladanie dát do databázy
    ```sql 
    INSERT INTO <TABULKA> (STLPEC1, STLPEC2, ...) VALUES (HODNOTA_STLPCA1, HODNOTA_STPLCA2) 
    ```

- ### výber dát z databázy
    ```sql
    SELECT STLPEC1, STLPEC2 FROM <TABULKA> WHERE STLPEC1="Ahoj"
    ```

- ### pojem SCRUM
  - metodika agilného vývoja založená na práci v tíme
  - je iteratívna - rozdelená na šprinty (časové úseky s cieľmi, napr. 30 dní)
  - má 3 fázy:
    1) Pre-game
        - backlog (zadanie cieľov, ktoré chcem dosiahnúť)
        - zadefinovanie SCRUM tímu - 5-10 členov, vedúci SCRUM master
    2) Game (vývoj)
       - vykonanie šprintov
    3) Post-game
        - testovanie výsledného produktu
        - integrácia výsledného produktu
  - vlastnosti:
    - časté nové verzie
    - doladenie programu počas vývoja
    - zapojenie užívateľov do testu
    - integrácia do obehu až na konci vývoja

- ### verzovací systém a prácu s ním
  - najpoužívanejší verzovací systém je Git
  - zaznamenáva zmeny v projektových súboroch a môžeme ich jednoducho spravovať (vracať zmeny, staré verzie, ukladať úpravy)
  - **postup** (príkazy sa vykonávajú v koreňovom adresári projektu):
    1) Vytvoríme git repozitár v projekte `git init`
    2) Pridáme súbory do repozitára `git add subor` alebo všetko `git add .`
    - Môžeme pozrieť zmeny pred aplikovaním `git status`
    3) Pridáme zmeny do repozitára (commit) `git commit -m "správa na identifikáciu zmien, napr. Pridanie nového tlačidla na odhlásenie účtu"`
    - Môžeme odstrániť posledný commit `git reset HEAD~1`
    - Ďalej môžeme pridať projekt na vzdialený repozitár (napr. GitHub, BitBucket, GitLab)
      - `git remove add origin URL_K_VZDIALENEMU_REPOZITARU`
      - publikujeme projekt do vzdialeného repozitára `git push -u origin master`
      - pokiaľ niekto iný publikoval zmeny do vzdialeného repozitára, môžeme si ich stiahnúť `git pull origin`

- ### návrhové vzory (design pattern)
  - reprezentujú preferované konvencie používané skúsenými vývojármi OOP
  - overené riešenia na bežné problémy, s ktorými sa môže vývojár stretnúť
  - hlavné vzory:
    - Kreačné vzory (Creational patterns): poskytujú mechanizmy na flexibilnú tvorbu objektov a recykláciu kódu
    - Štruktúrové vzory (Structural patterns): vysvetľujú skladbu objektov a tried do väčších štruktúr, so zachovaním ich efektivity a flexibility
    - Vzory správania (Behavioral patterns): zaoberajú sa algoritmami vzťahov medzi objektami

- ### pojem framework a charakterizujte nejaké
  - softvérová štruktúra, ktorá slúži pri programovaní, vývoji a organizácii iných softvérových projektov
  - môže obsahovať podporné programy, knižnice API, návrhové vzory a odporúčané postupy pri vývoji
  - **známe frameworky**:
    - Laravel: PHP webový full-stack framework založený na MVC (Model-View-Controller) architektúre
    - React: JavaScript webový frontend framework pre tvorbu užívateľský rozhraní

- ### rozdiel medzi natívnou, hybridnou a webovou aplikáciou
  - **natívna**:
    - aplikácia navrhnutá pre jeden operačný systém
  - **hybridná**:
    - aplikácia navrhnutá pre viac operačný systémov (cross-platform... mobil, PC, web)
  - **webová**:
    - responzívna web stránka optimalizovaná pre webové prehliadače

- ### naprogramujte v jazyku JavaScript jednoduchú aplikáciu bez využitia frameworku
  - x

- ### demonštrujte prácu s frameworkom
  - x


