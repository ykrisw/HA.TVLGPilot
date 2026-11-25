# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja stabilna i wzorcowa: 1.2.5

Zatwierdzona przez użytkownika 25 listopada 2026 r. Aktualny kod i jego zabezpieczona kopia są identyczne.

## Pliki

- `dashboard.yaml` — aktualna wersja na gałęzi main.
- `archive/dashboard-1.2.5.yaml` — zabezpieczona kopia wersji wzorcowej.
- `README.md` — dokumentacja i zasady dalszego rozwoju.
- `LICENSE` — licencja MIT.

## Zasady dalszego rozwoju

- Nie zmieniać zaakceptowanego wyglądu, proporcji, kolorów, ikon, animacji ani akcji bez wyraźnego polecenia użytkownika.
- Poprawki dla jednej platformy nie mogą powodować regresji na innych.
- Zachować istniejące encje, tematy MQTT oraz wszystkie 17 akcji sterujących.
- Zachować kopię 1.2.5 do czasu zatwierdzenia nowej wersji wzorcowej.

## Informacje techniczne

- Widoki: telefon (do 599 px), tablet (od 600 px, pointer: coarse), komputer (od 600 px, pointer: fine).
- Windows/Firefox: skalowanie do dostępnej wysokości okna i synchronizacja pulsowania przez zegar animacji dokumentu.
- iPadOS: wyśrodkowanie całego pilota, zachowanie proporcji.
- POWER, Play/Pause i Screen Off: wspólna faza pulsowania 2500 ms, przezroczystość 100%–38%. Wygaszanie po wyłączeniu TV ok. 6 s.
- INPUT: sygnalizacja zmiany HDMI przez 9 s, zielony przez 5 s, następnie wygaszenie do białego.
- Aktywna aplikacja: żółte obramowanie i poświata; przyciski funkcyjne: zielony akcent #13CB42, wygaszanie reakcji dotykowej 0,72 s.

## Stan testów

Według użytkownika wersja 1.2.5 działa poprawnie na macOS (Safari i Firefox), iPhone, iPadOS, Windows 11/Firefox oraz Linux Mint XFCE/Firefox na monitorze 1440p.

Znany wyjątek: Linux Mint XFCE/Firefox na ThinkPad L390 z matrycą o niskiej rozdzielczości — pilot zbyt duży, przyciski nachodzą na siebie. Na razie bez zmian w kodzie; można sprawdzić zmniejszenie powiększenia strony w przeglądarce.

## Instalacja i testowanie

Wklej cały `dashboard.yaml` do edytora YAML właściwego dashboardu Home Assistant i zapisz. Testuj wygląd i działanie na rzeczywistych urządzeniach; sama poprawność YAML nie gwarantuje prawidłowego renderowania.

Starsze wersje i grafiki pozostają dostępne w standardowej historii Git, bez dodatkowych plików w bieżącym drzewie.

## Licencja

MIT — zobacz `LICENSE`.
