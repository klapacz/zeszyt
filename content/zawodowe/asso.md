---
title: ASSO
description: Administracja Serwerowymi Systemami Operacyjnymi
menu: main
---


## Rodzaje licencji Microsoft

- Licencja Box (wersja pudełkowa)
  - Oprogramowanie można instalować wielokrotnie, ale tylko na jednym komputerze w tym samym czasie.
- Licencje OEM (przypisana do sprzętu)
- Licencja Dostępowa CAL (Client Access License)
  - CAL na urządzenie
  - CAL na użytkownika
  - dla Windows server
- MOLP, OLP (Microsoft Open License Program)
  - Licencje grupowe (np. dla szkoły)

## Współpraca stacji roboczej z serwerem sieci lokalnej. Typy sieci komputerowych.

Sieć równorzędna (peer-to-peer)
- W sieciach równorzędnych (peer-to-peer) każdy komputer może być klientem, serwerem lub jednocześnie klientem i serwerem
- siecią klient -serwer zarządza użytkownik o uprawnianiach administratora
- Wszystkie informacje o składniach sieci, jej użytkownikach 

Sieć klient serwer

## Usługi sieciowe

FTP
- transmisja plików po sieci
- używa portów :20 i :21
- protokół TCP/IP

Telnet
- połączenie zdalne z tekstową warstwą systemu operacyjnego
- używa portu :23

SSH
- połączenie zdalne z linią komend, **szyfrowane**
- używa portu :22

## Usługi poczty elektronicznej

1. SMTP (Simple Mail Transfer Protocol)
   - służący do wysyłania poczty
   - port :587
   - szyfrowany :465
2. Protokół POP3 (Post Office Protocol 3)
   - służący do pobierania poczty
   - port :110
   - szyfrowany :995
3. Protokół IMAP (Internet Message Access Protocol)
   - służący do odbiera poczty
   - port :143
   - szyfrowany :993

## Klasy adresów ip

| Klasa | Zakres adresu (pierwszy oktet) | początek adresu |
| ----- | ------------------------------ | --------------- |
| A     | 1   - 127                      | `0`             |
| B     | 128 - 191                      | `10`            |
| C     | 192 - 223                      | `110`           |
| D     | 224 - 239                      | `1110`          |
| E     | 240 -                          |

`127.0.0.1` - localhost, pętla zwrotna

## Zadanie 1 - Adresacja IP
W sieci komputer posiada adres IP: `212.51.219.59` oraz maskę `255.255.255.192`

Wylicz adres:
```
11010100.00110011.11011010.00111011   adres komputera
11111111.11111111.11111111.11000000   adres maski podsieci
11010100.00110011.11011010.00000000   adres sieci
11010100.00110011.11011010.00111111   adres rozgłoszeniowy
```

Wpisz Zakres adresów IP, które można przydzielić hostom w tej podsieci
`212.51.219.1 - 212.51.219.62`

Zapisz adres IP i maskę sieci w postaci skróconej
`212.51.219.0/26`

Zapisz w postaci binarnej następujące adresy IP

```
172.11.11.1   10101100.00001011.00001011.00000001
23.122.45.11  00010111.01111010.00101101.00001011
```

Określ, ile hostów można zaadresować w sieciach o następujących maskach:
```
255.255.255.0   254
255.128.0.0     8388606
128.0.0.0       214483646
```

Podaj zapis maski w notacji kropkowej
```
/32 255.255.255.255
/9  255.128.0.0
/15 255.254.0.0
```

Adresy prywatne

```
10.0.0.0/8
172.16.0.0 - 172.31.255.255
192.168.0.0/24
```

APIPA - `169.254.x.x`

klasy IP (pierwszy oktekt)

- A - 0-127
- B - 128-191
- C - 192-223
- D - 224-239
- E - 240-

```
192.168.200.15/28
maska:                     255.255.255.240
adres sieci:               192.168.200.0
adres rozgłoszeniowy:      192.168.200.15
ilość adresów:             16
ilość adresów użytecznych: 14


192.168.100.200/24
maska:                     255.255.255.000
adres sieci:               192.168.100.0
adres rozgłoszeniowy:      192.168.100.255
ilość adresów:             256
ilość adresów użytecznych: 254

10.20.30.40/29
maska:                     255.255.255.248
adres sieci:               10.20.30.40
adres rozgłoszeniowy:      10.20.30.47
ilość adresów:             8
ilość adresów użytecznych: 6


10.100.200.0/23
maska:                     255.255.254.0
adres sieci:               10.100.200.0
adres rozgłoszeniowy:      10.100.201.255
ilość adresów:             512
ilość adresów użytecznych: 510

10.20.50.60/30
maska:                     255.255.255.252
adres sieci:               10.20.50.60
adres rozgłoszeniowy:      10.20.50.61
ilość adresów:             4
ilość adresów użytecznych: 2

10.20.50.60/30
maska:                     255.255.255.252
adres sieci:               10.20.50.60
adres rozgłoszeniowy:      10.20.50.63
ilość adresów:             4
ilość adresów użytecznych: 2

10.20.30.40/28
maska:                     255.255.240.0
adres sieci:               10.20.30.32
adres rozgłoszeniowy:      10.20.30.47
ilość adresów:             16
ilość adresów użytecznych: 14

10.20.100.200/29
maska:                     255.255.248.0
adres sieci:               10.20.100.200
adres rozgłoszeniowy:      10.20.100.207
ilość adresów:             8
ilość adresów użytecznych: 6

10.20.150.0/22
maska:                     255.255.252.0
adres sieci:               10.20.148.0
adres rozgłoszeniowy:      10.20.151.255
ilość adresów:             1024
ilość adresów użytecznych: 1022

10.20.30.233/28
maska:                     255.255.255.240
adres sieci:               10.20.30.224
adres rozgłoszeniowy:      10.20.30.239
ilość adresów:             16
ilość adresów użytecznych: 14

10.20.30.160/25
maska:                     255.255.255.128
adres sieci:               10.20.30.128
adres rozgłoszeniowy:      10.20.30.255
ilość adresów:             128
ilość adresów użytecznych: 126
```
### Protokoły routingu

> CIDR - adresacja bezklasowa

- RIP (wersja 2 obsluguje maski bez klasowe)
