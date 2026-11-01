# EZVIZ DP2C Custom — Home Assistant

Własna gałąź rozwojowa integracji dla wizjera **EZVIZ DP2C**, bazująca na [Bobsilvio/ezviz_hp7](https://github.com/Bobsilvio/ezviz_hp7) 0.18.1.

**Status: zaimportowany i zweryfikowany snapshot działającej instalacji (2026-11-01).** Repozytorium zawiera komplet **50 plików** `custom_components/ezviz_hp7/`, odtworzonych z archiwum Home Assistanta. Wszystkie pliki są identyczne z przekazanym snapshotem według Git blob SHA. Składnia plików Python i JSON została sprawdzona statycznie. **Nie przeprowadzono jeszcze niezależnego testu instalacji tego repozytorium.**

## Co zostało zachowane

- Działający podgląd MJPEG przez `camera_view: live` na urządzeniu EZVIZ DP2C.
- `mjpeg.py`: `-analyzeduration 2000000`, `-probesize 2000000` oraz log `[MJPEG] FIRST FRAME`.
- `const.py`: interwał odpytywania chmury `UPDATE_INTERVAL_SEC = 5` (testowy; może zwiększać liczbę zapytań i ryzyko limitów).
- `live_camera.py`: lokalne zmiany obsługi SPS/PPS, GOP, diagnostyki oraz ścieżki FFmpeg.
- `api.py`: poprawka obsługi wyjątku MFA podczas tworzenia klienta.
- `pylocalapi/stream.py`: diagnostyczny log celu VTM TCP.
- `manifest.json`: identyczne wymagania i metadane jak w działającym snapshotie, wersja bazowa `0.18.1`.

Nie zaimportowano lokalnych historycznych plików `live_camera.py.before_*` ani pełnej konfiguracji HA.

## Zasady bezpieczeństwa

- Repozytorium jest publiczne. Nigdy nie dodawaj `/config/.storage`, `secrets.yaml`, tokenów EZVIZ, zrzutów diagnostycznych, logów lub archiwum całego HA.
- Wgrany kod przeszukano pod kątem jawnych danych prywatnych; wykryte konstrukcje `password`/`token` są częścią implementacji klienta EZVIZ, nie kopiami konfiguracji użytkownika.
- Zachowaj osobno **pełną kopię działającego Home Assistanta**, zanim zaczniesz testować kod z tego repozytorium.
- **Nie instaluj dwóch integracji o domenie `ezviz_hp7` równocześnie.** Przed testem należy zaplanować bezpieczną zamianę i możliwość wycofania zmian.

## Cele dalszego rozwoju

1. Oddzielne i konfigurowalne ustawienia odpytywania i FFmpeg.
2. Pobieranie wielu ostatnich alarmów z deduplikacją, żeby alarm PIR nie zagłuszył dzwonka.
3. Lepsze pomiary czasu: alarm → HA → żądanie MJPEG → pierwsza klatka.
4. Testy regresji, wydania i instrukcja aktualizacji przez HACS.

[Plan projektu](docs/PLAN.md).

## Informacje o autorstwie

Projekt pochodny względem [EZVIZ HP7](https://github.com/Bobsilvio/ezviz_hp7) autorstwa Silvio Vaira (Bobsilvio), MIT. Zachowano [LICENSE](LICENSE), [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md) i informacje o autorstwie w kodzie. Projekt nie jest oficjalnym produktem EZVIZ ani Home Assistant.
