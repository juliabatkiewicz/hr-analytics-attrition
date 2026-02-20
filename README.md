# hr-analytics-attrition

## Opis projektu
Projekt koncentrujący się na problemie rotacji pracowników. Głównym celem analizy jest eksploracja danych oraz budowa modelu klasyfikacyjnego, który pozwoli na wczesne zidentyfikowanie pracowników zagrożonych odejściem z firmy. Trafna predykcja w tym obszarze pozwala organizacji zaoszczędzić koszty związane z rekrutacją i szkoleniem nowych osób.

Projekt ten koncentruje się na klasycznym problemie biznesowym w obszarze analityki HR, jakim jest rotacja pracowników (Employee Attrition). Głównym celem analizy jest eksploracja danych oraz budowa modelu klasyfikacyjnego, który pozwoli na wczesne zidentyfikowanie pracowników zagrożonych odejściem z firmy. Trafna predykcja w tym obszarze pozwala organizacji zaoszczędzić koszty związane z rekrutacją i szkoleniem nowych osób.

## Zbiór danych
Analiza opiera się na połączeniu trzech zbiorów danych, które razem dają pełny obraz sytuacji pracownika w firmie:
* **`df1`**: Zawiera kluczowe cechy demograficzne (np. wiek, wykształcenie, stan cywilny) oraz specyfikę stanowiska (dział, rola). Pozwala odpowiedzieć na pytanie: *"Kto odchodzi?"*.
* **`df2`**: Dostarcza informacji o historii pracy, wynagrodzeniu, podwyżkach i poziomie satysfakcji. Pozwala odpowiedzieć na pytanie: *"Dlaczego odchodzi?"*.
* **`attrition`**: Zawiera zmienną docelową (`Yes`/`No`), która wskazuje, czy pracownik faktycznie opuścił firmę.

## Etapy analizy i modelowania
1. **Ładowanie i integracja danych**: Wczytanie plików CSV i połączenie ich w jedną ramkę danych z wykorzystaniem wspólnego klucza.
2. **Eksploracyjna Analiza Danych**:
   - Sprawdzenie struktury danych i podsumowań statystycznych.
   - Identyfikacja braków danych.
   - Wizualizacja rozkładu zmiennych (np. wiek, miesięczne dochody).
   - Analiza kluczowych cech w relacji do decyzji o odejściu za pomocą wykresów.
3. **Inżynieria cech i przygotowanie danych**: 
   - Obsługa braków danych.
   - Skalowanie oraz transformacja zmiennych kategorycznych.
4. **Modelowanie**: Trening klasyfikatorów w celu predykcji zmiennej docelowej.
5. **Ewaluacja modeli**: Ocena skuteczności algorytmów z wykorzystaniem takich metryk jak *Accuracy*, *F1-score*, Macierz Błędów i Raport Klasyfikacji.

## Główne wnioski i ograniczenia
Z przeprowadzonej analizy wypływają następujące wnioski:
* **Czynniki ryzyka**: Analiza wykazała, że do najsilniejszych predyktorów odejścia należą m.in. wynagrodzenie oraz staż pracy.
* **Wdrożenie biznesowe**: Opracowany model sprawdza się jako **narzędzie wspomagające** dla działu HR. Nie powinien jednak być wyłącznym kryterium podejmowania krytycznych decyzji personalnych.
* **Ograniczenia podejścia**:
   - *Wysokie zaszumienie danych:* Etap eksploracji ujawnił wartości odstające (np. nierealistyczny wiek > 9000 lat), które sugerują obecność ukrytych błędów w systemach źródłowych.
   - *Brak danych "miękkich":* Model bazuje na twardych wskaźnikach demograficznych i finansowych, ignorując istotne czynniki, takie jak relacje z przełożonym czy atmosfera w zespole.
   - *Niezbalansowane klasy:* Znacznie mniej pracowników odchodzi niż zostaje, co jest naturalnym zjawiskiem w tym problemie, jednak utrudnia naukę algorytmom klasyfikacyjnym.

## Technologie i Biblioteki
Projekt został w całości przygotowany w języku Python. Główne wykorzystane pakiety to:
* `pandas` i `numpy` – do manipulacji, przekształceń i inżynierii danych,
* `matplotlib` i `seaborn` – do tworzenia wykresów i eksploracji wizualnej,
* `scikit-learn` – do preprocessingu, trenowania modeli predykcyjnych i ich ewaluacji.

## Uruchamianie projektu
1. Sklonuj repozytorium na swój dysk.
2. Upewnij się, że masz zainstalowane środowisko Python z pakietami wymienionymi wyżej.
3. Projekt był tworzony z myślą o środowisku **Google Colab**. Jeśli chcesz go tam uruchomić, wywołaj pierwszą komórkę z `google.colab.files.upload()` i wgraj pliki `.csv`.
4. Aby uruchomić go lokalnie, wystarczy umieścić pliki `df1`, `df2` oraz `attrition` w jednym folderze z notatnikiem i pominąć komórkę odpowiedzialną za upload.
5. Uruchamiaj kolejne komórki kodu.
