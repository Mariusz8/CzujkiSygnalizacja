# 🚦 Inteligentna sygnalizacja świetlna z czujnikami ruchu PIR
📌 Opis projektu

Projekt przedstawia system sygnalizacji świetlnej oparty na płytce Arduino Uno oraz czterech czujnikach ruchu PIR.

System obsługuje cztery kierunki. Każdy kierunek posiada czerwone i zielone światło oraz przypisany czujnik ruchu.

Głównym założeniem projektu jest sterowanie sygnalizacją na podstawie aktualnego wykrywania ruchu. Zielone światło zapala się na kierunku, na którym czujnik PIR wykrywa ruch. Gdy czujnik przestaje wykrywać ruch, odpowiedni sygnalizator wraca do czerwonego światła.

Jeśli żaden czujnik nie wykrywa ruchu, wszystkie kierunki mają czerwone światło.

🛠️ Wykorzystane komponenty
Arduino Uno
4 × czujnik ruchu PIR
4 × czerwona dioda LED
4 × zielona dioda LED
8 × rezystor ograniczający prąd diod LED
Przewody połączeniowe
Płytka stykowa
Przewód USB do programowania Arduino
🔌 Schemat połączeń

Każdy kierunek posiada dwa światła oraz jeden czujnik ruchu.

Kierunek	Czerwone światło	Zielone światło	Czujnik PIR
1	D2	D3	D10
2	D4	D5	D11
3	D6	D7	D12
4	D8	D9	D13
Zasady podłączania
Diody LED należy podłączyć do odpowiednich pinów cyfrowych przez rezystory ograniczające prąd.
Wyjścia sygnałowe czujników PIR należy podłączyć do pinów D10–D13.
Arduino i czujniki powinny mieć wspólną masę GND.
Zasilanie czujników należy dostosować do specyfikacji ich modeli.
⚙️ Zasada działania

Program stale odczytuje stany czterech czujników PIR. Na początku każdej iteracji wszystkie światła ustawiane są na czerwone. Następnie dla każdego aktywnego czujnika włączane jest zielone światło odpowiadającego mu kierunku.

Scenariusze działania
Stan czujników	Działanie sygnalizacji
Żaden czujnik nie wykrywa ruchu	Wszystkie światła czerwone
Ruch wykryty przez czujnik 1	Zielone światło kierunku 1
Ruch wykryty przez czujnik 2	Zielone światło kierunku 2
Ruch wykryty przez czujnik 3	Zielone światło kierunku 3
Ruch wykryty przez czujnik 4	Zielone światło kierunku 4
Ruch wykryty przez kilka czujników	Zielone światło na każdym aktywnym kierunku
Ważne cechy
Brak automatycznej zmiany kierunków.
Brak stałego czasu świecenia zielonego światła.
Reakcja na bieżące stany czujników.
Powrót do czerwonego światła, gdy czujnik przestaje zgłaszać ruch.
Możliwość jednoczesnego włączenia zielonego światła na kilku kierunkach.
💻 Oprogramowanie

Program został napisany w języku C/C++ dla platformy Arduino.

Najważniejsze elementy kodu
setup() – konfiguruje piny świateł jako wyjścia, czujniki jako wejścia i ustawia początkowy stan czerwonego światła.
wszystkieCzerwone() – włącza wszystkie czerwone światła i wyłącza wszystkie zielone.
loop() – odczytuje czujniki PIR i włącza zielone światło na kierunkach, na których wykryto ruch.
digitalRead() – odczytuje stan wyjścia czujnika.
digitalWrite() – steruje diodami LED.
delay(100) – wprowadza krótkie opóźnienie między kolejnymi odczytami czujników.
🚀 Uruchomienie projektu
Podłącz Arduino Uno, czujniki PIR i diody LED zgodnie z tabelą połączeń.
Podłącz płytkę Arduino do komputera przez USB.
Uruchom Arduino IDE.
Otwórz plik z kodem programu.
Wybierz płytkę Arduino Uno i odpowiedni port komunikacyjny.
Wgraj program na płytkę.
Poczekaj na zakończenie inicjalizacji czujników PIR.
Przetestuj każdy czujnik, wykonując ruch w jego polu detekcji.
⚠️ Ograniczenia projektu
Czujniki PIR reagują na zmiany promieniowania podczerwonego związane z ruchem, a nie na samą obecność obiektu.
Po wykryciu ruchu czujnik może utrzymywać stan wysoki przez pewien czas, zależnie od modelu i konfiguracji.
Jeżeli kilka czujników wykrywa ruch jednocześnie, zielone światła mogą świecić na kilku kierunkach równocześnie.
Program nie zawiera blokady uniemożliwiającej jednoczesne włączenie zielonego światła na wszystkich kierunkach.
Projekt ma charakter edukacyjny i demonstracyjny. Nie jest przeznaczony do sterowania rzeczywistym ruchem drogowym.
🔮 Możliwe rozszerzenia
Wprowadzenie zasady, że zielone światło może świecić tylko na jednym kierunku naraz.
Dodanie czasu podtrzymania zielonego światła po wykryciu ruchu.
Dodanie sygnalizacji żółtej.
Zastosowanie funkcji millis() zamiast delay().
Dodanie wyświetlacza LCD do prezentowania aktywnego kierunku.
Dodanie trybu ręcznego i automatycznego.
🎯 Cel edukacyjny

Projekt pozwala poznać podstawy programowania Arduino, obsługi czujników PIR, sterowania diodami LED oraz budowania prostych systemów reagujących na sygnały z otoczenia.

Technologie: Arduino Uno · C/C++ · PIR · LED · Automatyka · Elektronika
