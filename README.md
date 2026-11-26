# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja stabilna i wzorcowa: 1.3.3

Zaakceptowana 26 listopada 2026 r. Wszystkie 13 testowanych konfiguracji wyglądu zaliczone przy powiększeniu 100%. Poprawka iPada w Firefoxie nie spowodowała zaobserwowanych regresji w pozostałych 12 konfiguracjach.

## Pliki

- `dashboard.yaml` — aktualna wersja na gałęzi main.
- `archive/dashboard-1.3.3.yaml` — identyczna kopia wzorcowa.
- `archive/dashboard-1.2.8.yaml` — poprzednia wersja wzorcowa, kopia awaryjna.
- `README.md` — dokumentacja.
- `LICENSE` — licencja MIT.

## Stan testów

| Urządzenie | System / przeglądarka | Wygląd |
|---|---|---|
| Dell OptiPlex 1440p | Linux Mint / Firefox | OK |
| Dell OptiPlex 1440p | Windows 11 / Firefox | OK |
| iPad Air M1 | Aplikacja HA | OK |
| iPad Air M1 | Firefox | OK (naprawiono) |
| iPhone 16 Pro Max | Aplikacja HA | OK |
| iPhone 16 Pro Max | Firefox | OK |
| iPhone 16 Pro Max | Safari | OK |
| Lenovo 1366 × 768 | Linux Mint / Firefox | OK |
| Lenovo 1366 × 768 | Windows 11 / Firefox | OK |
| MacBook Air M1 | Firefox | OK |
| MacBook Air M1 | Safari | OK |
| Mac mini M1 1440p | Firefox | OK |
| Mac mini M1 1440p | Safari | OK |

Naprawiono iPad Firefox w trybie desktopowym: siatka miała bazową szerokość ok. 342 px zamiast 465 px, co powodowało nakładanie przycisków. W 1.3.3 szerokość 465 px jest ustawiana przed skalowaniem w tabletowym układzie przeglądarki dla MacIntel z wielodotykiem, pointer: coarse i identyfikatorem Version/Safari, z wykluczeniem aplikacji HA. Firefox w tym trybie nie ujawnia FxiOS. Warunek może objąć także Safari na iPadzie, którego nie przetestowano.

iPad Safari: problem z otwarciem strony HA oraz PlexConfigControl; osobny temat, wygląd pilota nieprzetestowany.

Wersje 1.2.9–1.3.2 były eksperymentalne lub diagnostyczne; nie są wersjami wzorcowymi. Diagnostyka 1.3.2 potwierdziła przyczynę problemu. Finalna wersja 1.3.3 nie zawiera panelu diagnostycznego. Starsze pliki pozostają dostępne w historii Git.

## Informacje techniczne

- Widoki: telefon (do 599 px), tablet (od 600 px, pointer: coarse), komputer (od 600 px, pointer: fine).
- Desktop: skalowanie do dostępnej wysokości, maksymalnie 115% rozmiaru bazowego; Windows/Firefox ma osobny mechanizm centrowania.
- Przeglądarki mobilne: dopasowanie do dostępnej wysokości; na iPhonie poprawiono dolny rząd oraz szerokość POWER.
- POWER, Play/Pause i Screen Off: okres pulsowania 2500 ms, przezroczystość 100%–38%; wygaszanie po wyłączeniu TV ok. 6 s. Idealna synchronizacja nie jest potwierdzona.
- INPUT: sygnalizacja HDMI przez 9 s, zielony przez 5 s, następnie wygaszenie do białego.
- Aktywna aplikacja: żółte obramowanie i poświata; przyciski funkcyjne: zielony akcent #13CB42, wygaszanie reakcji dotykowej 0,72 s.

## Zasady dalszego rozwoju

- Wersja 1.3.3 jest punktem odniesienia. Wszystkie 13 zaakceptowanych konfiguracji należy chronić przed regresjami; zakres kolejnych zmian wymaga zgody użytkownika.
- Nie zmieniać proporcji, kolorów, ikon, animacji, encji, tematów MQTT ani akcji bez wyraźnego polecenia użytkownika.
- Nowe wersje testować na osobnych gałęziach; nie zastępować wersji wzorcowej bez akceptacji.
- Testy wyglądu nie stanowią pełnej weryfikacji funkcjonalności.

## Instalacja

Wklej cały `dashboard.yaml` do edytora YAML dashboardu Home Assistant i zapisz. Testuj przy powiększeniu 100%.

## Licencja

MIT — zobacz `LICENSE`.
