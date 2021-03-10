---
title: MENUTK
description: Montaż, eksploatacja i naprawa urządzeń techniki komputerowej
---

> miejsce 13b

## Dyski Twarde

### Sposoby adresowania danych
- CHS (cylinder, head, sector)
- ECHS (Extended cylinder, head, sector)
- LBA (Logical Block Adressing)
- MZR (Multiple Zone Recording)

### Struktura fizyczna dysku twardego
> cluster - elementarna jednostka informacji

### Techniki odczytu
- SMR  (Shingled Magnetic Recording) - technologia zapisu danych dachówkowo.
- HAMR podczas zapisu głowica podnosi temperaturę nośnika, zmieniając jego właściwości.
- MAMR - działa jak HAMR, ale ogrzewanie mikrofalami.
- MACH.2 WWykorzystuje się 2 serwomechanizmy. Każdy z nich obsługuje połowę ramion z głowicami. Dzięki temu w tym samym momencie można jednocześnie realizować 2 operacje.
- Multilayer HDD - metoda zwiększenia pojemności przez zastosowanie na jednym talerzu nośników o różnych właściwościach i głowic współpracujących z odpowiednimi warstwami nośnika.

Wszystkie typy pamięci na nośnikach magnetycznych działają na tej samej zasadzie - na poruszającym się dysku lub taśmie magnetycznej dokonywany jest zapis informacji. polegający na odpowiednim namagnesowaniu pól nośnika magnetycznego.

## Parametry dysków twardych

| parametr                  | wartość                                                           |
| ------------------------- | ----------------------------------------------------------------- |
| pojemność                 | kilkadziesiąt GB do kilkanaście TB                                |
| liczba talerzy            | 1-4                                                               |
| liczba głowic             | fizyczne (liczba talerzy * 2) i logiczne (nawet kilkadziesiąt)    |
| liczba cylindrów          | kilka -kilkanaście tysięcy                                        |
| średni czas dostępu       | kilkadziesiąt milisekund                                          |
| prędkości obrotowe        | 5400, 7200, 10 000, 15 000 rpm                                    |
| szybkość transferu danych | kilka-kilkanaście MB/s                                            |
| szybkość odczytu          |                                                                   |
| szybkość zapisu           |                                                                   |
| MTFB                      | średni czas bezawaryjnej pracy                                    |
| S.M.A.R.T                 |                                                                   |
| wielkość bufforu cache    | kilkadziesiąt MB                                                  |
| zasilanie                 | -12V, +5V, +12V                                                   |
| moc pobierania            | kilka, kilkanaście W                                              |
| średnica dysku            | 3.5", 2.5" (przenośne lub laptopy)                                |
| interfejs wewnętrzny      | ATA (IDE, PATA), SATA, SATA Express, U.2, M,2, PCI EXpresss, FATA |
| interfejs zewnętrzny      | eSATA, USB, Thunderbold, Express Card                             |

### S.M.A.R.T

(ang. Self-Monitoring Analysis and Reporting Technology). Oprogramowanie dysku, które monitoruje, analizuje i raportuje stan urządzenia, np. wysokość lotu głowicy, czas uzyskania nominalnej prędkości obrotowej. Jeśli następuje degradacja tych wielkości układ kontroli wysyła ostrzeżenie że dysk może ulec uszkodzeniu.

### System zarządzania poborem mocy
System (ang. POwer Management) wyłącza silnik dysku i zaparkować głowicę, po pewnym czasie od momentu ostatniej operacji in/out wykonanej na dysku. Przejście dysku najpierw w stan jałowy (ang. idle) a następnie uśpienia (ang. SLeep lub Standby) powoduje znaczące zmniejszenie poboru mocy. System Power Management powoduje nawet dziesięciokrotnie zmniejsza poboru mocy przez nie używany dysk.

## Interfejsy dysków twardych

Znane są trzy podstawowe typy interfejsów dyskowych
- IDE
  - równoległy interfejs dyskowy,
  - Zapewnia przepustowość do 133MB/s
  - złącze ma 40 pinów
  - Taśma pozwala na podpięciu 2 dysków w systemie Master-Slave (ustawione zworkami)
  - Płyta główna pozwalała na podłączenie maksymalnie 4 dysków lub napędów optycznych
- SCSI
  - równoległa magistrala danych do podłączenia twardych dysków i napędów optycznych wykorzystywana w serwerach i wysokiej klasy stacji roboczych
  - maksymalna szybkość do 640MB/s
  - Umożliwiał podłączenie 15 urządzeń
  - Złącze miało 50 pinów
- SATA
  - Serial ATA (ang. Serial Advanced Technology Attachment, sata)
  - szeregowa magistrala komputerowa do komunikacji pomiędzy płytą główną a pamięciami masowymi, takimi jak dyski twarde, napędy optyczne i taśmowe
  - wprowadzona w roku 2000.
  - SATA jest następcą magistrali równoległej ATA
  - Kabel ma 7 pinów i umożliwia podpięcie jednego dysku.
  - System pozwala na współpracę do 8 dysków SATA na płycie głównej
  - interfejs zapewnia przepustowość do 600MB/s 
  - złącze danych ma 7 pinów, transmisja jest kodowana, dwu kierunkowa, 4pinowa.
  - zasilanie
    - standardowe 15pinów, dostarcza napięcia +3.3V, +5V, +12V
    - wersja slim (laptopowa) 6 pinowa, dostarcza tylko napięcie +5V
- eSATA
  - extended SATA, niekompatybilne kable, parametry sata
  - maksymalna długość kabla 2 metry
  - zasilanie z gniazdka lub USB
  - Występuje w kilku różnych odmianach o rozszerzonych funkcjonalnościach
    - eSATAp
    - Power over eSATA
    - Power eSATA
    - eSATA/USB Combo
    - eSATA/USB HYBRID PORT (EUHP)

Inne interfejsy
- Dyski HDD
  - SAS
  - FATA
- Nośniki SSD
  - SATA Express
  - M.2
  - U.2
  - PCI-Express