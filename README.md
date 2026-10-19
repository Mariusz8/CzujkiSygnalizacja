🚦 Smart Traffic Light System

<p align="center">
<img src="https://img.shields.io/badge/Platform-Arduino%20Uno-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino Uno">
<img src="https://img.shields.io/badge/Language-C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++">
<img src="https://img.shields.io/badge/Sensors-PIR-orange?style=for-the-badge" alt="PIR Sensors">
<img src="https://img.shields.io/badge/Status-Prototype-success?style=for-the-badge" alt="Prototype">
</p>

<p align="center">
<b>Inteligentna sygnalizacja świetlna reagująca na ruch.</b>
<br>
Cztery kierunki. Cztery czujniki PIR. Sterowanie światłami w czasie rzeczywistym.
</p>

📖 O projekcie

Smart Traffic Light System to projekt elektroniczny oparty na płytce Arduino Uno, którego zadaniem jest sterowanie czterema sygnalizatorami świetlnymi na podstawie danych z czujników ruchu PIR.

System na bieżąco sprawdza, czy któryś z czujników wykrywa ruch. Zielone światło zostaje włączone na odpowiadającym mu kierunku, a pozostałe światła pozostają czerwone — o ile ich czujniki nie wykrywają ruchu.

💡 Projekt powstał w celu zaprezentowania praktycznego zastosowania mikrokontrolerów, czujników ruchu i automatycznego sterowania.
✨ Funkcje
🚶 Detekcja ruchu — cztery niezależne czujniki PIR.
🚦 Automatyczne sterowanie — światła reagują na stan czujników.
🔴 Stan bezczynności — wszystkie światła są czerwone, gdy nie wykryto ruchu.
🟢 Niezależna obsługa kierunków — każdy czujnik steruje przypisanym mu sygnalizatorem.
⚡ Ciągłe monitorowanie — program regularnie odczytuje wejścia czujników.
🔧 Prosta rozbudowa — możliwość dodania nowych funkcji i trybów pracy.
🖼️ Schemat projektu

<p align="center">
<img src="images/schemat.png" alt="Schemat połączeń Arduino Uno, czterech czujników PIR i sygnalizatorów LED" width="850">
</p>

<p align="center">
<i>Schemat połączeń układu sterowania sygnalizacją świetlną.</i>
</p>

📌 Aby wyświetlić schemat, zapisz obraz w repozytorium jako images/schemat.png. Możesz też zmienić ścieżkę powyżej na nazwę własnego pliku.
🧰 Wykorzystane komponenty
Komponent	Liczba	Zastosowanie
Arduino Uno	1	Główny kontroler systemu
Czujnik PIR	4	Wykrywanie ruchu
Czerwona dioda LED	4	Sygnalizacja zatrzymania
Zielona dioda LED	4	Sygnalizacja przejazdu
Rezystor ograniczający prąd	8	Ochrona diod LED
Przewody połączeniowe	Zależnie od potrzeb	Połączenie elementów
Płytka stykowa	1	Montaż układu
🔌 Konfiguracja pinów

Każdy kierunek ma przypisane dwie diody LED i jeden czujnik ruchu.

Kierunek	🔴 Czerwone LED	🟢 Zielone LED	📡 Czujnik PIR
1	D2	D3	D10
2	D4	D5	D11
3	D6	D7	D12
4	D8	D9	D13

Ważne: Diody LED muszą być podłączone przez rezystory ograniczające prąd. Wszystkie elementy wymagające wspólnego odniesienia napięcia powinny mieć połączone masy GND.

⚙️ Jak działa system?
          ┌──────────────────────┐
          │     Arduino Uno      │
          └──────────┬───────────┘
                     │
          ┌──────────▼───────────┐
          │ Odczyt czujników PIR │
          └──────────┬───────────┘
                     │
          ┌──────────▼───────────┐
          │ Czy wykryto ruch?    │
          └──────────┬───────────┘
                     │
          ┌──────────▼───────────┐
          │ Wszystkie światła    │
          │ ustaw na czerwone    │
          └──────────┬───────────┘
                     │
          ┌──────────▼───────────┐
          │ Aktywne czujniki     │
          │ sterują zielonymi LED│
          └──────────┬───────────┘
                     │
                     └──────► Powtórz

Przykładowe scenariusze
Stan czujników	Rezultat
Żaden nie wykrywa ruchu	🔴 Wszystkie kierunki czerwone
Aktywny tylko czujnik 1	🟢 Zielone na kierunku 1
Aktywny tylko czujnik 2	🟢 Zielone na kierunku 2
Aktywne czujniki 1 i 3	🟢 Zielone na kierunkach 1 i 3
Wszystkie czujniki aktywne	🟢 Zielone na wszystkich kierunkach
⚠️ To model edukacyjny. W aktualnej wersji kilka kierunków może otrzymać zielone światło jednocześnie. Nie należy stosować tego programu w prawdziwej sygnalizacji drogowej.
💻 Technologie

<p>
<img src="https://img.shields.io/badge/Arduino-Embedded%20Systems-00979D?style=flat-square&logo=arduino&logoColor=white" alt="Arduino">
<img src="https://img.shields.io/badge/C%2B%2B-Programming-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++">
<img src="https://img.shields.io/badge/Electronics-Hardware-lightgrey?style=flat-square" alt="Electronics">
</p>

Arduino Uno — mikrokontroler.
C/C++ — logika sterowania.
PIR — wykrywanie ruchu na podstawie zmian promieniowania podczerwonego.
Arduino IDE — kompilowanie i wgrywanie programu.
🚀 Uruchomienie
Skompletuj komponenty i połącz je zgodnie z tabelą pinów.
Zainstaluj Arduino IDE.
Otwórz plik .ino z kodem projektu.
Podłącz Arduino Uno przez USB.
Wybierz Tools → Board → Arduino Uno.
Wybierz właściwy port w menu Tools → Port.
Kliknij Upload.
Po uruchomieniu przetestuj każdy czujnik, poruszając się w jego polu detekcji.

Wskazówka: Czujniki PIR mogą potrzebować chwili na ustabilizowanie się po włączeniu zasilania.

📁 Struktura repozytorium
smart-traffic-light/
├── README.md
├── src/
│   └── smart_traffic_light.ino
└── images/
    └── schemat.png

README.md — dokumentacja projektu.
src/smart_traffic_light.ino — kod źródłowy Arduino.
images/schemat.png — schemat połączeń układu.
🔭 Możliwe usprawnienia
Blokada jednoczesnego zapalania zielonego światła na konfliktujących kierunkach.
Czas podtrzymania zielonego światła.
Sygnalizacja żółta.
Nieblokująca obsługa czujników z użyciem millis().
Wyświetlacz LCD prezentujący aktywny kierunek.
Tryb ręczny i automatyczny.
Rejestrowanie wykrytego ruchu.
🎯 Cel projektu

Celem projektu jest praktyczne poznanie podstaw elektroniki i programowania mikrokontrolerów poprzez stworzenie systemu, który reaguje na sygnały z otoczenia.

Projekt może stanowić punkt wyjścia do dalszej nauki automatyki, systemów wbudowanych i inteligentnego zarządzania ruchem.

<p align="center">
<b>🚦 Smart Traffic Light System</b>
<br>
<sub>Built with Arduino Uno · Powered by curiosity</sub>
</p>
