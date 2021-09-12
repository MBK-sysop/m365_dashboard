# Xiaomi M365 Display [forked from augisbud/m365_dashboard]

For a original description in English, <a href="#%20Original%20Description%20in%20English">click here</a>

**Ostrzeżenie:**

**Wszystkie modyfikacje  robisz na własną odpowiedzialność. Nie odpowiadam za utratę gwarancji i uszkodzenie sprzętu!**

# O projekcie:
Wielofunkcyjny "komputer pokładowy" pozwalający na odczyt statusu i zmianę podstawowych parametrów M365/M365Pro.

Umożliwia:
- Odczyt prędkości / aktualnego poboru prądu, przebiegu całkowitego i przebiegu dziennego, czasu od uruchomienia.
- Odczyt wyszystkich parametrów (w tym ogniw) jak w aplikacji typu __m365 Dashboard__ na telefonie.
- Włączenie tempomatu, tylnej lampki, ustawienie KRES.

# Używanie:
Display włącza się automatycznie wraz z uruchomieniem M365 i pokazuje podstawowe dane. Po wciścinięciu gazu prezentowany jest całkowity przebieg i czas od włączenia.

Po wciśnięciu równicześnie gazu i hamulca pojawia się menu ustawień. Kolejne pozycje przewija się hamulcem, zatwierdza gazem.

**W celu aktualizacji firmware należy odłączyć wyświetlacz lub zablokować go wciskając równocześnie gaz, hamulec i przycisk uruchamiania zanim z wyśwetlacza zniknie logo**

# Materiały:
- Arduino Mini Pro ATmega328 3,3V lub 5V (chiński klon)
- Wyświetlacz OLED 0,96" I2C SSD1306 lub SPI
- Dioda prostownicza 1N4148 lub podobna  
- Rezystor 120ohm 0,25W

Koszt części ok. 35 PLN

Potrzebny też będzie:
 - Programator TTL<>USB, np. FTD1232 lub CP2102
 - Precyzyjna lutownica
 - Obudowa wydrukowana wg szablonu w projekcie

# Wykonanie, uruchomienie i podłączenie:
## przygotowanie kodu i programowanie Arduino
- Pobierz repozytorium
  - w language.h odkomentuj język, w którym mają być wyświetlane komunikaty (domyślnie ustawiony jest angielski)
  - w defines.h ustaw typ wyświetlacza jaki używasz (domyślnie ustawiony jest I2C)
- Uruchom Arduino IDE (testowane na 1.8.16)
  - dograj biblioteki z katalogu ./libraries
  - ustaw typ płytki na "Arduino mini pro" i ATmega328P (3.3V 8MHz lub 5V 16MHz w zależności jakiej używasz)
  - właściwy port COM
  - programator "USBasp"
- Podłącz Arduino do programatora zgodnie z poniższym schematem, skompiluj i wgraj szkic.

![alt text](https://i.imgur.com/DpPkvJz.jpg)  

## uruchomienie

Podłącz wyświetlacz do Arduino zgodnie z instrukcją;
w przypadku chińskich klonów i wyświetlacza I2C należy użyć następujących pinów:
- GND <> GND
- VCC <> VCC
- SDA <> PC4
- SLC <> PC5

Podłącz źródło zasilania 5V do RAW, GND do GND - powinno pojawić się na wyświetlaczu logo a później komunikat "BUS not connected! No data to display!" w wybranym języku.

## podłączenie
- Delikatnie podważając odklej osłonę diód/wyświetlacza na kierownicy.
- Odkręć 3 śruby płytki PCB, rozłącz okragłą wtyczkę główną, opcjonalnie 3 małe wtyczki od lamki i manetek
- Przylutuj (**ostrożnie**) wyprowadzenia zgodnie ze schematem:

![alt text](https://camo.githubusercontent.com/a912641249173768ae60670e843c62294d06da4f/68747470733a2f2f656c656374726f2e636c75622f646174612f666f72756d2f6d657373616765732f34323633312f696d616765732f31313636302d313238302e6a7067)


## Instrukcja video na YT:
https://youtu.be/JQUNXCyj2Fs

Co prawda po hiszpańsku, ale można włączyć napisy po polsku


----
----




# Original Description in English
**Disclaimer:**

**All modifications are made at your own risk. I'm not responsible for the loss of warranty and damage to the equipment!**

# Products Used  
Arduino Pro Mini    
I2C OLED 0.96" or 1.3" Screen
FTD1232 Usb Programmer   
3d Printed Bracket  
1N4148 Diode  
0.25w 120ohm Resistor       

Estimated price is around 20$ (Inluding Printed Parts).

Knowing the price is around 20$ you can get the Xiaomi M365 Pro top panel from aliexpress for around the same price and a better look, unless you need additional features just go for the pro display.

# Flashing  
![alt text](https://i.imgur.com/DpPkvJz.jpg)  
Please install the libraries I provided in the files, install them to you arduino library folder, usually              
  C:\Users\\%username%\Documents\Arduino\libraries  
I'd recommend you to use Arduino 1.6.6  
https://www.arduino.cc/en/Main/OldSoftwareReleases  

# Physical Connections  
![alt text](https://camo.githubusercontent.com/a912641249173768ae60670e843c62294d06da4f/68747470733a2f2f656c656374726f2e636c75622f646174612f666f72756d2f6d657373616765732f34323633312f696d616765732f31313636302d313238302e6a7067)  

# Updating M365 firmware / Disabling the Dashboard
Turn on the scooter and immediately engage and hold the throttle and brake before the logo disappears from the dashboard LCD. You will enter on dashboard disabled mode.
The Arduino TX/RX pins will go to hi impedance state leaving the communication BUS free.

By this way you can update de M365 firmware without disconnecting the dashboard or any cable.

A new power cycle will reset the dashboard to normal mode.

# Known Issues  
Sometimes the Arduino Freezes, a watchdog is in place but doesn't always trigger.  

# Screen caps
# Soldering, soldered directly to the cable coming from the MCU
5V To Red    
GND To Black  
BUS To Yellow  
![alt text](https://i.imgur.com/3ZwcrIJ.jpg)  
A video on how everything is soldered may come soon.

Meanwhile you can enable subtitles in English in this YouTube video produced in Spanish language
https://www.youtube.com/watch?v=JQUNXCyj2Fs

# UI
UI pictures from version 0.2  
![alt text](https://i.imgur.com/8ekMdIo.jpg)  
![alt text](https://i.imgur.com/AHLVTcu.jpg)  

More pictures are coming soon.
