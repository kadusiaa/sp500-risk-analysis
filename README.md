# S&P 500 — zmienność, ryzyko i skrajne ruchy cen

Projekt rozpoczęty od obserwacji SNDK i porównania jej z powszechnie znanymi firmami: PG, PEP, JNJ, KO, MCD i BRK-B. Analiza 503 spółek obejmuje codzienne wahania cen, maksymalne obsunięcia i odrabianie strat.

**Python · Pandas**

Kod i wyniki: [analysis.ipynb](analysis.ipynb). Podsumowanie do pobrania i otwarcia w przeglądarce: [analysis.html](analysis.html).

## Pliki

- `analysis.ipynb` — notebook z kodem, opisami i zapisanymi wynikami.
- `analysis.html` — wersja do przeczytania w przeglądarce, bez uruchamiania Pythona.
- `data/README.md` — źródło i instrukcja dostarczenia danych; CSV nie jest częścią tej wersji.
- `requirements.txt` — zależności.

## Uruchomienie

Sprawdzono na Pythonie 3.12.14, Pandas 3.0.1 i Matplotlib 3.11.2.

1. Pobierz dane z [Kaggle](https://www.kaggle.com/datasets/yash16jr/s-and-p500-daily-update-dataset) i umieść plik jako `data/SnP_daily_update.csv`. Wymagany jest format zgodny z opisem w `data/README.md`. Otwórz terminal w katalogu projektu.
2. Utwórz środowisko: `python -m venv .venv`.
3. Windows PowerShell: `.\.venv\Scripts\python.exe -m pip install -r requirements.txt`.
4. Windows PowerShell: `.\.venv\Scripts\python.exe -m notebook`.
5. Otwórz `analysis.ipynb` i wykonaj wszystkie komórki od początku.

Notebook korzysta ze ścieżki względnej `data/SnP_daily_update.csv`. Po dostarczeniu CSV nie wymaga dostępu do komputera autora ani pobierania notowań w trakcie analizy. Instalacja zależności wymaga internetu. Zapisane wyniki i HTML można czytać bez ponownego wykonania. Odczyt i przekształcenie CSV wymagają pamięci dla około dwóch milionów wierszy.

## Zakres i ograniczenia

- 503 tickerów; 2010-01-04–2026-05-29.
- Porównania zachowują różne okresy dostępnej historii spółek. Ranking z minimum 1260 cen jest wyraźnie oddzielony od porównań bez tego filtra.
- Źródło: [Kaggle — yash16jr](https://www.kaggle.com/datasets/yash16jr/s-and-p500-daily-update-dataset). Analiza dotyczy kopii z danymi do 29 maja 2026. Aktualizowany zbiór może dać inne wyniki. Nie potwierdzono sposobu korekty cen ani historycznego składu indeksu.
- Wyniki są opisowe. Skrajne ruchy wymagają weryfikacji; notebook nie dowodzi przyczyn wydarzeń i nie demonstruje prognozowania.
- Zwrot roczny ma pierwotną definicję od pierwszej do ostatniej dostępnej ceny roku; okno 252 obserwacji jest przybliżeniem roku sesyjnego.

## Autorstwo i wykorzystanie AI

Autorem kodu analitycznego oraz koncepcji i przebiegu całej analizy jest autor projektu. AI wykorzystano do wygenerowania kodu wykresów Matplotlib oraz złożenia podsumowania projektu na podstawie autorskiej analizy.

## Weryfikacja

Wykonano wszystkie 43 komórki kodu po kolei na analizowanej kopii CSV, zapisano tabele i wszystkie 11 istniejących wykresów. Potwierdzono brak duplikatów par data–ticker. Braki cen pozostawiono bez uzupełniania przy liczeniu zwrotów. Oryginalny notebook i źródłowy CSV pozostawiono bez zmian.
