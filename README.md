# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja bazowa

**1.1.1 — zaakceptowany punkt wyjścia do testów funkcjonalnych.**

**1.2.3 — osobny widok iPadOS, bez zmian iPhone/macOS:** istniejący układ iPhone pozostaje identyczny (`max-width: 599px`), a komputerowy układ ma ten sam kod i geometrię co w 1.2.2. Dla urządzeń dotykowych o szerokości od 600 px dodano trzeci wariant z proporcjonalnym zmniejszeniem wszystkich wymiarów, wysokości, marginesów, ikonek i typografii do 80%, aby zapobiec nakładaniu przycisków na tabletowej siatce HA, zachowując proporcje całego pilota. Warianty wybierane za pomocą `screen` media query z `pointer: coarse` (tablet) / `pointer: fine` (komputer). Przetestować rzeczywisty wygląd na iPadOS w pionie i poziomie, zwłaszcza jeśli iPad korzysta z gładzika lub myszy. Bez nowych komponentów, bez zmian działań sterujących. Osobna kopia zatwierdzonej wersji 1.2.2: `archive/dashboard-1.2.2.yaml`.

**1.2.2 — poprawione pozycje dolnego rzędu i synchronizacja:** na macOS Play/Pause zajmuje szerokość dwóch sąsiednich przycisków funkcyjnych, a Screen Off wyrównano dokładnie z kolumną INPUT (szerokości 296 px i 138 px, odstęp 22 px). W mobilnym widoku szerokości i odstęp dolnego rzędu liczone są z szerokości siatki trzech aplikacji, tak aby Screen Off nie wychodził poza prawą krawędź. Pulsowanie POWER, Play/Pause i Screen Off jest wyrównywane do wspólnego zegara animacji przeglądarki (`document.timeline.currentTime`) z cyklem 2500 ms i zakresem 100%–38%; animacje wygasające po wyłączeniu telewizora zachowują limit około 6 s. Bez zmian pozostałe wymiary, kolory i akcje. Wymaga testu rzeczywistego na macOS i iOS.

**1.2.1 — korekty mobilne i pulsowania:** Screen Off na iPhonie poszerzony o 12 px, aby prawą krawędzią zbliżyć się do INPUT; mobilne przyciski przesunięte w prawo o `4vw` dla symetryczniejszego wyśrodkowania; logo wszystkich sześciu aplikacji zmniejszone o 15% tylko w mobilnym widoku. Wskaźniki POWER, Play/Pause i Screen Off korzystają ze wspólnej fazy cyklu 2,5 s, obliczanej względem bieżącego czasu — wymaga testu synchronizacji na urządzeniu. Układ i wymiary desktopowe bez zmian, wszystkie akcje zachowane.

**1.2.0 — zielony akcent przycisków funkcyjnych:** zastosowano ten sam odcień zieleni `#13CB42`, co dla wskaźnika `ON` na POWER: podświetlenia dotykowe i poświata, Play/Pause, Screen Off oraz INPUT. Wygaszanie efektów dotykowych przedłużono z 0,45 s do 0,72 s (+60%). Żółta ramka i poświata aktywnych aplikacji, czerwony symbol POWER i cała geometria pilota bez zmian. Zmiany wymagają testu w HA na macOS/iOS.

**1.1.9 — test nowej geometrii:** joystick zastąpiono 3×3 siatką `custom:button-card`, identyczną pod względem liczby kolumn, szerokości przycisków, wysokości i odstępów jak siatka aplikacji. W krzyżu są 5 aktywnych przycisków (↑, ←, OK, →, ↓), a cztery narożniki puste i niewidoczne; bez dodatkowej ramki. Wszystkie przyciski pilota — również POWER, Play/Pause, Screen Off, Back, Home, INPUT — mają wysokość 101 px w układzie komputerowym i odpowiadającą jej responsywną wysokość na iPhonie. Zachowano istniejące akcje, logotypy i wskaźniki; zmianę należy ocenić w rzeczywistym Home Assistant na macOS i iOS.

**1.1.8 — poprawka po nieudanym teście 1.1.7:** nieaktywne ramki ciemniejsze o kolejne 20% (`#557089` → `#445A6E`). Usunięto nieskuteczne nadpisania natywnego efektu `ripple` joysticka. Ta zmiana NIE gwarantuje usunięcia szarych śladów z obsługi fokusowania w Home Assistant ani pełnego rozbłysku przycisków; nie zmieniano rozmiarów, układu i poleceń. Do uzyskania odrębnej, pełnopowierzchniowej animacji konieczne jest inne rozwiązanie techniczne, które wymaga sprawdzenia w realnym HA.

**1.1.7 — korekta po testach macOS/iOS:** obramowania nieaktywnych przycisków przyciemnione o 25% (`#7195B7` → `#557089`), bez zmiany żółtego obramowania aktywnych aplikacji. W natywnych elementach joysticka wyłączono trwałe podświetlenie fokusu (szary ślad po kliknięciu) i zachowano krótką reakcję ripple. Rozświetlenie całego kafelka joysticka nie jest zagwarantowane w `picture-elements` — wymaga osobnego rozwiązania i testów, bez ponownej wymiany struktury. Geometria, akcje i wygląd pozostałych elementów zachowane.

**1.1.6 — test akcentów i reakcji dotykowej:** żółta ramka aktywnej aplikacji pozostaje w pełnej intensywności; wypełnienie wnętrza osłabione do około 30%. Przyciski funkcyjne mają płynniejsze wygaszanie po dotknięciu (0,45 s). Dla oryginalnego joysticka `picture-elements` skonfigurowano natywny efekt dotknięcia i wygaszanie bez zmiany struktury, wymiarów i pozycji; skuteczność tego efektu zależy od obsługi CSS w używanej wersji Home Assistant/iOS i wymaga praktycznego testu. Zachowane wszystkie akcje sterowania.

**1.1.5 — test na urządzeniach:** zachowano wymiary i rozmieszczenie pilota 1.1.4. W POWER dodano stale widoczny wskaźnik `ON` (zielony) / `OFF` (czerwony), 16 px, w prawym górnym rogu, oparty o encję zasilania. Po wyłączeniu TV wygasają podświetlenia aplikacji, Play/Pause oraz INPUT; Screen Off ma animację wygaszającą do 6 s. Podświetlenie aktywnej aplikacji jest o ok. 10% słabsze, nadal żółte. Funkcyjne podświetlenia mają pomarańczowo-czerwony odcień `#ff7436`; krótka reakcja dotykowa jest realizowana w CSS podczas przytrzymania przycisku. Elementy joysticka są teraz `custom:button-card` wewnątrz `picture-elements`, by obsłużyć efekt dotykowy przy zachowaniu ustawionych współrzędnych i wymiarów. Całość wymaga testu rzeczywistego renderowania i sterowania na iPhonie oraz Macu.

**1.1.4 — test funkcjonalny i mobilny:** dalsze zmniejszenie kafelków na iPhonie o ok. 3%; aktywna aplikacja podświetla tło i obramowanie kafelka, nie logo; Play/Pause świeci na żółto podczas odtwarzania i pulsuje podczas pauzy; Screen Off pulsuje na żółto, gdy ekran wyłączony; POWER pulsuje na czerwono przez ok. 6 s po zmianie stanu encji `binary_sensor.lg_49nano816na_56ba_power` (bez reakcji na samo kliknięcie). Animacje mają cykl 2,5 s i zakres przezroczystości 100%–38%. Ostateczny wygląd wymaga testów na iOS i macOS; bazowy wygląd 1.1.1 pozostaje punktem odniesienia.

**1.1.2 — testowy układ mobilny:** dla ekranów do 599 px szerokości jeden dashboard wyświetla proporcjonalnie zmniejszoną wersję pilota. Powyżej 599 px pokazuje dokładnie zachowany układ komputerowy 1.1.1. Obie wersje mają te same akcje sterujące. Nie uznawać układu mobilnego za zatwierdzony bez testu na iPhonie.

Plik `dashboard.yaml` zawiera bieżącą wersję projektu (**1.2.3**, test mobilny, tabletowy i funkcjonalny). Wersje sprzed 1.1.1 pozostają wyłącznie w standardowej historii commitów Git; stary osobny plik YAML usunięto z bieżącego drzewa repozytorium.

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
