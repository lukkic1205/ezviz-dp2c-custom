# Plan — EZVIZ DP2C Custom

## Etap 0 — zachowanie działającego kodu

- [x] Odebrano archiwum integracji z Home Assistant.
- [x] Porównano 50 właściwych plików z upstream i oddzielono 6 lokalnie zmodyfikowanych plików.
- [x] Zaimportowano wszystkie 50 plików ze zgodnością SHA Git blob.
- [x] Wyłączono z repozytorium historyczne kopie `live_camera.py.before_*`.
- [x] Zachowano licencję upstream oraz licencje komponentów zewnętrznych.
- [x] Przeprowadzono statyczną kontrolę składni plików Pythona oraz poprawności JSON.
- [ ] Potwierdzić istnienie *pełnego* backupu Home Assistant poza HA.
- [ ] Przejrzeć ewentualne dodatkowe sekrety w nowych plikach przed przyszłymi commitami.

## Etap 1 — niezależny test własnej integracji

- [ ] Zachować dotychczasową domenę `ezviz_hp7` i istniejące identyfikatory encji.
- [ ] Zweryfikować ładowanie integracji w kontrolowanej instalacji HA.
- [ ] Przetestować przycisk dzwonka, alarm PIR, dostępność kamery oraz automatyzację Browser Mod.
- [ ] Sprawdzić czas do pierwszej klatki i stabilność dwuminutowego podglądu.
- [ ] Przygotować instrukcję przywracania i aktualizowania przez HACS.
- [ ] Dopiero wtedy przygotować niezależny numer wydania.

## Etap 2 — rozwój

- [ ] Konfigurowalny, bezpieczny interwał pollingu i kontrola limitów API.
- [ ] Pobieranie kilku ostatnich alarmów z deduplikacją.
- [ ] Diagnostyka latencji dzwonka i obrazu oraz ograniczanie zbędnych logów.
- [ ] Ocena wpływu równoległych klientów MJPEG na czas inicjalizacji.

**Zasada:** nie nadpisujemy działającej instalacji przed zakończeniem testów i zapewnieniem łatwego rollbacku.
