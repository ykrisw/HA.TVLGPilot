# HA.TVLGPilot

Pilot do telewizora LG w panelu Home Assistant, oparty o `custom:button-card`, integrację MQTT oraz istniejące encje TV.

**Wersja:** `1.0.2` (rozwojowa). Kolejne wersje: `1.0.2`, `1.0.3` itd. Każda wersja zwiększa trzeci numer o 1.

## Pliki

- `dashboard.yaml` — bieżący projekt pilota (**1.0.2**).
- `reference/last-working-layout.yaml` — archiwalny punkt odniesienia (wcześniejszy układ v18), do porównywania działań i centrowania.
- `LICENSE` — licencja MIT.

## Stan projektu

Projekt jest w trakcie dopracowywania wyglądu. **W wersji 1.0.2 joystick przebudowano na natywne stosy kart, ale wygląd oraz dolny rząd nadal wymagają sprawdzenia w Home Assistant.** Prawidłowa składnia YAML nie gwarantuje prawidłowego wyglądu w Home Assistant.

Docelowy wygląd: ciemne gradientowe przyciski z cienkim niebieskoszarym obramowaniem, symetryczna siatka; pełnoszeroki POWER o tej samej wysokości co przyciski aplikacji; dwa rzędy aplikacji; joystick z wysokimi przyciskami bocznymi; Back/Home/INPUT; Play/Pause i Screen Off w proporcji 2:1. Pilot ma być wysoki i stosunkowo wąski, bez zwiększania zaakceptowanej szerokości.

### Ważne zasady

- Nie zmieniać istniejących tematów MQTT, akcji ani powiązań encji bez uzgodnienia.
- Zachować dynamiczne kolory aktywnej aplikacji, Play/Pause, Screen Off i animację INPUT.
- Nie dodawać podpisów do przycisków funkcyjnych (wyjątek: `OK`); napisy tylko przy wybranych aplikacjach. YouTube bez `AdFree`, Apple samo jabłko.
- Następne poprawki dotyczą przede wszystkim **geometrii**, z unikanem problematycznych zagnieżdżonych przycisków w `custom_fields`.
- Przed uznaniem zmian za poprawne sprawdzić wygląd w przeglądarce Home Assistant.

## Użycie

Wymagany jest już zainstalowany `custom:button-card` oraz istniejące integracje/encje użyte w YAML. Wklej zawartość `dashboard.yaml` do edytora YAML odpowiedniego panelu Home Assistant.

## Licencja

MIT — zobacz `LICENSE`.
