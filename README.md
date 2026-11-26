# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja stabilna i wzorcowa: 1.2.8

Zaakceptowana jako wersja bazowa 26 listopada 2026 r. Wygląd zaakceptowano w 12 z 13 testowanych konfiguracji przy powiększeniu przeglądarki 100%.

## Pliki

- `dashboard.yaml` — aktualna wersja na gałęzi main.
- `archive/dashboard-1.2.8.yaml` — identyczna kopia wzorcowa.
- `archive/dashboard-1.2.5.yaml` — poprzednia wersja wzorcowa.
- `README.md` — dokumentacja.
- `LICENSE` — licencja MIT.

## Stan testów

| Urządzenie | System / przeglądarka | Wygląd |
|---|---|---|
| Dell OptiPlex 1440p | Linux Mint / Firefox | OK |
| Dell OptiPlex 1440p | Windows 11 / Firefox | OK |
| iPad Air M1 | Aplikacja HA | OK |
| iPad Air M1 | Firefox | Znany błąd siatki |
| iPhone 16 Pro Max | Aplikacja HA | OK |
| iPhone 16 Pro Max | Firefox | OK |
| iPhone 16 Pro Max | Safari | OK |
| Lenovo 1366 × 768 | Linux Mint / Firefox | OK |
| Lenovo 1366 × 768 | Windows 11 / Firefox | OK |
| MacBook Air M1 | Firefox | OK |
| MacBook Air M1 | Safari | OK |
| Mac mini M1 1440p | Firefox | OK |
| Mac mini M1 1440p | Safari | OK |

Znany wyjątek: iPad Firefox — przyciski w trzykolumnowych rzędach nachodzą na siebie, a środkowa kolumna jest przesunięta w lewo. POWER i dolny rząd są wyśrodkowane. Tryb komputerowy Firefoxa jest włączony; jego wpływ wymaga diagnostyki.

iPad Safari: problem z otwarciem strony HA oraz PlexConfigControl; osobny temat, wygląd pilota nieprzetestowany.

Wersje 1.2.9 i 1.3.0 nie rozwiązały problemu iPada. Wersja 1.3.1 DEBUG nie wyświetliła panelu w testowanej konfiguracji. Nie są wersjami wzorcowymi.

## Informacje techniczne

- Widoki: telefon (do 599 px), tablet (od 600 px, pointer: coarse), komputer (od 600 px, pointer: fine).
- Desktop: skalowanie do dostępnej wysokości, maksymalnie 115% rozmiaru bazowego; Windows/Firefox ma osobny mechanizm centrowania.
- Przeglądarki mobilne: dopasowanie do dostępnej wysokości; na iPhonie poprawiono dolny rząd oraz szerokość POWER.
- POWER, Play/Pause i Screen Off: okres pulsowania 2500 ms, przezroczystość 100%–38%; wygaszanie po wyłączeniu TV ok. 6 s. Idealna synchronizacja nie jest potwierdzona.
- INPUT: sygnalizacja HDMI przez 9 s, zielony przez 5 s, następnie wygaszenie do białego.
- Aktywna aplikacja: żółte obramowanie i poświata; przyciski funkcyjne: zielony akcent #13CB42, wygaszanie reakcji dotykowej 0,72 s.

## Zasady dalszego rozwoju

- Wersja 1.2.8 jest punktem odniesienia. Kolejne poprawki dotyczące układu mają obejmować wyłącznie iPad Firefox, bez zmian pozostałych 12 konfiguracji.
- Nie zmieniać proporcji, kolorów, ikon, animacji, encji, tematów MQTT ani akcji bez wyraźnego polecenia użytkownika.
- Nowe wersje testować na osobnych gałęziach; nie zastępować wersji wzorcowej bez akceptacji.
- Testy wyglądu nie stanowią pełnej weryfikacji funkcjonalności.

## Instalacja

Wklej cały `dashboard.yaml` do edytora YAML dashboardu Home Assistant i zapisz. Testuj przy powiększeniu 100%.

## Licencja

MIT — zobacz `LICENSE`.
