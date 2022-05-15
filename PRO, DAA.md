---
attachments: [Clipboard_2022-05-12-19-33-10.png]
title: 'PRO, DAA'
created: '2022-05-11T17:08:40.382Z'
modified: '2022-05-15T17:31:57.623Z'
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

- ### 

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

- ### polia a štruktúry v programovaní, ich inicializácia (syntax), ich vlastnosti, použitie, rozdiely v jazyku C/C++
  - *polia* (arrays):
    - pole je premenná, ktorá uchováva vyšší počet hodnôt rovnakého dátového typu
    - pre deklaráciu musíme zadefinovať veľkosť poľa (maximálny počet hodnôt)
    ```c
    int znamky[5] = {1, 3, 5, 5, 4};
    printf("Prva znamka: %d", znamky[0]); //vypíše "Prva znamka: 1"
    ```
  - *štruktúry* (structs):
    - dátový typ zadefinovaný programátorom
    ```c
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

