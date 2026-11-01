# Plan — EZVIZ DP2C Custom

## Etap 0 — zabezpieczenie stanu działającego

- [ ] Zachować pełną kopię Home Assistanta.
- [ ] Wyeksportować **wyłącznie** katalog `/config/custom_components/ezviz_hp7` z bieżącej instalacji.
- [ ] Przejrzeć eksport pod kątem tokenów, haseł, logów, zrzutów diagnostycznych i danych konta.
- [ ] Porównać zawartość z [upstream](https://github.com/Bobsilvio/ezviz_hp7) 0.18.1; odnotować rzeczywiste zmiany lokalne.
- [ ] Sprawdzić licencje plików i zależności.

## Etap 1 — pierwsza wersja z zachowaniem działającej funkcjonalności

- [ ] Dodać zweryfikowane pliki źródłowe do `custom_components/ezviz_hp7/`.
- [ ] Zachować wewnętrzną domenę `ezviz_hp7`, aby uniknąć zmiany identyfikatorów encji.
- [ ] Wydzielić konfigurowalne ustawienia MJPEG i interwału odpytywania.
- [ ] Wykonać kontrolę składni kodu oraz test uruchomienia na kopii HA.
- [ ] Przygotować dokumentację instalacji i wycofania zmian.

## Etap 2 — poprawa wykrywania zdarzeń

- [ ] Sprawdzić pobieranie ostatnich alarmów i sytuację `doorbell ringing` + `PIR Alarm`.
- [ ] Zaprojektować pobieranie kilku alarmów z deduplikacją i ograniczeniem obciążenia API.
- [ ] Dodać pomiary opóźnienia wykrycia dzwonka oraz metryki stabilności połączenia.

## Etap 3 — optymalizacja obrazu

- [ ] Zmierzyć `MJPEG session START` → `FIRST FRAME` na pojedynczym kliencie.
- [ ] Utrzymać odtwarzanie H.264 w trybie MJPEG, bez regresji.
- [ ] Sprawdzić dodatkowe równoległe połączenia klientów i ich wpływ na opóźnienie.

## Kryteria gotowości

Nowa wersja nie może zastąpić działającej instalacji, dopóki nie ma weryfikowalnej kopii przywracania oraz udanych testów dzwonka, odtwarzania i automatycznego zamknięcia popupu.
