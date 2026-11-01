# EZVIZ DP2C Custom — Home Assistant

Własna gałąź rozwojowa integracji dla wizjera **EZVIZ DP2C**, bazująca na projekcie [Bobsilvio/ezviz_hp7](https://github.com/Bobsilvio/ezviz_hp7).

> **Status: przygotowanie repozytorium.** Nie jest to jeszcze gotowa integracja do instalacji. Działający kod z lokalnego Home Assistanta nie został jeszcze przeniesiony do tego repozytorium.

## Cel

Zachować działający podgląd na żywo DP2C przez MJPEG w Home Assistant i rozwijać go bez nadpisywania lokalnych poprawek przez aktualizacje HACS.

Planowane obszary rozwoju:
- kompatybilność z aktualnym DP2C i istniejącą domeną integracji `ezviz_hp7`;
- konfigurowalny interwał odpytywania chmury (z kontrolą błędów i limitów API);
- odporne na pominięcia odczytywanie alarmów dzwonka, także gdy występują alarmy PIR;
- pomiary czasu startu transmisji MJPEG i pierwszej klatki;
- utrzymanie zgodności z automatyzacjami Home Assistant i Browser Mod.

## Stan lokalnej instalacji (do zweryfikowania z archiwum)

W trakcie testów na Home Assistant działał podgląd `camera.ezviz_dp2_bk3392221_na_zywo` w trybie `camera_view: live` z wyjściem MJPEG. Lokalnie testowano zmiany w `mjpeg.py` oraz `const.py`. Te zmiany **nie są jeszcze częścią repozytorium**.

## Zasady bezpieczeństwa

- Nie publikuj `/config/.storage`, `secrets.yaml`, tokenów EZVIZ, plików diagnostycznych ani pełnych logów z podpisanymi adresami URL.
- Repozytorium jest **publiczne**. Przed dodaniem archiwum z Home Assistanta należy sprawdzić zawartość i usunąć dane uwierzytelniające.
- Przed instalacją nowego kodu wykonaj pełną kopię zapasową Home Assistanta.
- Nie instaluj równolegle dwóch integracji o domenie `ezviz_hp7`.

## Plan wdrożenia

Zobacz [docs/PLAN.md](docs/PLAN.md).

## Autorzy i źródła

Projekt pochodny względem [EZVIZ HP7](https://github.com/Bobsilvio/ezviz_hp7), © 2026 Silvio Vaira (Bobsilvio), MIT. Zachowujemy licencję i oznaczenia autorstwa kodu źródłowego oraz sprawdzimy licencje zależności przed publikacją kompletnego pakietu.

Ten projekt nie jest oficjalnym produktem firmy EZVIZ ani Home Assistant.
