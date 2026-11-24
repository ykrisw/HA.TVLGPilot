# HA.TVLGPilot

Pilot LG dla Home Assistant, wykorzystujący istniejące encje, MQTT i `custom:button-card`.

## Wersja bazowa

**1.1.1 — zaakceptowany punkt wyjścia do testów funkcjonalnych.**

**1.1.2 — testowy układ mobilny:** dla ekranów do 599 px szerokości jeden dashboard wyświetla proporcjonalnie zmniejszoną wersję pilota. Powyżej 599 px pokazuje dokładnie zachowany układ komputerowy 1.1.1. Obie wersje mają te same akcje sterujące. Nie uznawać układu mobilnego za zatwierdzony bez testu na iPhonie.

Plik `dashboard.yaml` zawiera bieżącą wersję projektu (**1.1.2**, test mobilny). Wersje sprzed 1.1.1 pozostają wyłącznie w standardowej historii commitów Git; stary osobny plik YAML usunięto z bieżącego drzewa repozytorium.

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
