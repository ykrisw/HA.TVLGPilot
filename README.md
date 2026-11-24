# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja bazowa

**1.1.1 — zaakceptowany punkt wyjścia do testów funkcjonalnych.**

**1.1.6 — test akcentów i reakcji dotykowej:** żółta ramka aktywnej aplikacji pozostaje w pełnej intensywności; wypełnienie wnętrza osłabione do około 30%. Przyciski funkcyjne mają płynniejsze wygaszanie po dotknięciu (0,45 s). Dla oryginalnego joysticka `picture-elements` skonfigurowano natywny efekt dotknięcia i wygaszanie bez zmiany struktury, wymiarów i pozycji; skuteczność tego efektu zależy od obsługi CSS w używanej wersji Home Assistant/iOS i wymaga praktycznego testu. Zachowane wszystkie akcje sterowania.

**1.1.5 — test na urządzeniach:** zachowano wymiary i rozmieszczenie pilota 1.1.4. W POWER dodano stale widoczny wskaźnik `ON` (zielony) / `OFF` (czerwony), 16 px, w prawym górnym rogu, oparty o encję zasilania. Po wyłączeniu TV wygasają podświetlenia aplikacji, Play/Pause oraz INPUT; Screen Off ma animację wygaszającą do 6 s. Podświetlenie aktywnej aplikacji jest o ok. 10% słabsze, nadal żółte. Funkcyjne podświetlenia mają pomarańczowo-czerwony odcień `#ff7436`; krótka reakcja dotykowa jest realizowana w CSS podczas przytrzymania przycisku. Elementy joysticka są teraz `custom:button-card` wewnątrz `picture-elements`, by obsłużyć efekt dotykowy przy zachowaniu ustawionych współrzędnych i wymiarów. Całość wymaga testu rzeczywistego renderowania i sterowania na iPhonie oraz Macu.

**1.1.4 — test funkcjonalny i mobilny:** dalsze zmniejszenie kafelków na iPhonie o ok. 3%; aktywna aplikacja podświetla tło i obramowanie kafelka, nie logo; Play/Pause świeci na żółto podczas odtwarzania i pulsuje podczas pauzy; Screen Off pulsuje na żółto, gdy ekran wyłączony; POWER pulsuje na czerwono przez ok. 6 s po zmianie stanu encji `binary_sensor.lg_49nano816na_56ba_power` (bez reakcji na samo kliknięcie). Animacje mają cykl 2,5 s i zakres przezroczystości 100%–38%. Ostateczny wygląd wymaga testów na iOS i macOS; bazowy wygląd 1.1.1 pozostaje punktem odniesienia.

**1.1.2 — testowy układ mobilny:** dla ekranów do 599 px szerokości jeden dashboard wyświetla proporcjonalnie zmniejszoną wersję pilota. Powyżej 599 px pokazuje dokładnie zachowany układ komputerowy 1.1.1. Obie wersje mają te same akcje sterujące. Nie uznawać układu mobilnego za zatwierdzony bez testu na iPhonie.

Plik `dashboard.yaml` zawiera bieżącą wersję projektu (**1.1.6**, test mobilny i funkcjonalny). Wersje sprzed 1.1.1 pozostają wyłącznie w standardowej historii commitów Git; stary osobny plik YAML usunięto z bieżącego drzewa repozytorium.

## Zasada zamrożenia wyglądu

Wygląd **1.1.1** jest zaakceptowany: kolory, gradienty, obramowania, logotypy, wymiary, proporcje i rozmieszczenie przycisków. **Nie zmieniać tych cech** przy testach ani poprawkach funkcjonalności. Nawet jeśli użytkownik poprosi o zmianę wyglądu, należy poprosić o **odrębne potwierdzenie przed jej wprowadzeniem**.

Dalsze wersje służą testowaniu i naprawie funkcjonalności pilota. Zachować istniejące akcje, tematy MQTT, powiązania encji, kolory stanu i animacje, chyba że użytkownik zatwierdzi zmianę konkretnego zachowania.

## Pliki

- `dashboard.yaml` — aktualna wersja pilota, bazowo **1.1.1**
- `same_as_before_but_with_three_changes_logo_sizes.png` — zaakceptowany render projektu
- `Szablon 1.png`, `Szablon 2.png` — szablony symetrii i proporcji
- `LICENSE` — licencja MIT

## Testowanie

Wklej cały `dashboard.yaml` do edytora YAML właściwego dashboardu Home Assistant i zapisz. Testuj przyciski w Home Assistant na żywo. Poprawność składni YAML nie potwierdza poprawnego działania.

## Licencja

MIT — zobacz `LICENSE`.
