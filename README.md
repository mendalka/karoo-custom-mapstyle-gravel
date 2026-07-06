# karoo-custom-mapstyle-gravel

Customowy styl mapy dla Hammerhead Karoo 3, oparty na oryginalnym stylu `offline_v15.xml`, z naciskiem na jazdę gravel, bikepacking i czytelne rozróżnienie dróg, ścieżek, nawierzchni oraz POI przydatnych w trasie.

Projekt powstał na bazie oryginalnego stylu Hammerhead Karoo 3 V15. Inspiracja i część pomysłów pochodzą z projektu [dansoft-ch/karoo-custom-mapstyle](https://github.com/dansoft-ch/karoo-custom-mapstyle).

## Co zawiera

- `offline_v15.xml` - aktualny styl mapy.
- `icons-kmen/` - dodatkowe i zmienione ikony POI.
- `docs/legend_kmen_compact.html` - kompaktowa legenda do trzymania na telefonie.

## Najważniejsze zmiany

- Czytelniejsze ścieżki rowerowe:
  - `highway=cycleway`
  - `highway=path + bicycle=yes|designated`
  - `highway=path + cycleway=*`
  - sieci rowerowe `icn`, `ncn`, `rcn`, `lcn`
- Rozróżnienie dróg terenowych i wiejskich:
  - `tracktype=grade1..grade5`
  - lepsze nieutwardzone `compacted|gravel|fine_gravel`
  - gorsze nieutwardzone `ground|dirt|grass|sand|unpaved`
  - osobne style dla nie-rowerowych `highway=path`
- Lepsze POI na bikepacking:
  - camping, caravan site, hostel/hotel/nocleg
  - shelter/hut
  - slipway/marina/dock/kajak
  - paliwo, woda, supermarket, kawiarnia, serwis rowerowy
- Ciemniejszy las, bardziej widoczna plaża/piasek i teren naturalny.
- Mocniejsze nazwy miejscowości.
- Brązowe poziomice z niskim priorytetem etykiet wysokości.

## Instalacja na Hammerhead Karoo 3

1. Podłącz Karoo 3 do komputera przez USB.
2. Włącz opcje programistyczne na Karoo, jeżeli nie są włączone.
3. W ustawieniach programistycznych ustaw domyślną konfigurację USB na transfer plików.
4. Otwórz pamięć wewnętrzną Karoo.
5. Znajdź katalog, w którym znajduje się aktualny plik stylu, np. `offline_v15.xml`.
6. Zrób kopię oryginalnego pliku, np. `offline_v15.xml.backup`.
7. Skopiuj z tego repozytorium do katalogu głównego pamięci Karoo:
   - `offline_v15.xml`
   - katalog `icons-kmen`
8. Upewnij się, że plik stylu ma nazwę oczekiwaną przez aktualną wersję oprogramowania Karoo.
   - dla wersji 15: `offline_v15.xml`
   - jeżeli Karoo używa innej wersji, dopasuj nazwę, np. `offline_v16.xml`
9. Odłącz Karoo i ponownie otwórz widok mapy albo zrestartuj urządzenie.

Po większej aktualizacji systemu Karoo styl może zostać nadpisany. Wtedy zwykle wystarczy ponownie skopiować plik XML i upewnić się, że ma aktualną nazwę `offline_vXX.xml`.

## Legenda

Kompaktowa legenda znajduje się w:

```text
docs/legend_kmen_compact.html
```

Można ją otworzyć w przeglądarce na telefonie. Pokazuje tylko aktualny styl `karoo-custom-mapstyle-gravel`.

## Uwagi

Styl zależy od tagów zapisanych w pliku mapy `.map`. Jeżeli dany tag istnieje w OpenStreetMap, ale nie został zapisany w mapie offline Karoo, sam styl go nie wyświetli.

Przykład: jeżeli mapa offline nie zawiera `leisure=marina`, reguła dla mariny nie zadziała, nawet jeśli obiekt jest widoczny online w OpenStreetMap.

## Inspiracje i źródła instalacji

- [dansoft-ch/karoo-custom-mapstyle](https://github.com/dansoft-ch/karoo-custom-mapstyle)
- [Wgranie nowego stylu map do Karoo Hammerhead 3](https://bobiko.blog/2026/02/hammerhead-karoo3-style/)
