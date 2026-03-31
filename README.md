# 📱 Mobile Automation & Cloud-Ready Testing Suite

**Prowadzący:** mgr Mariusz Dworniczak
**Student:** Vladyslav Petrenko
**Numer Albumu:** 94590

---

## 🏗️ Architektura Projektu (Marketing & Tech Stack)

Projekt stanowi kompletny ekosystem testowy oparty o podejście **Cloud-Ready / Headless**. Zamiast korzystać z ciężkich emulatorów, skupiono się na narzędziach CLI, analizie statycznej, konteneryzacji (Docker) oraz automatyzacji procesów poprzez pipeline.

**Główne technologie:**

* **Język:** Python 3.10+
* **Automatyzacja UI:** Appium 2.x (Mobile Engine)
* **Infrastruktura:** Docker & Docker Compose
* **Raportowanie:** Allure Framework
* **Analiza:** MobSF (Static Analysis) & ADB CLI

---

## 📅 PRZEBIEG LABORATORIUM (Kamienie Milowe)

### 🔹 BLOK 1: Tooling & Environment (Infrastruktura)

Przygotowanie środowiska narzędziowego w oparciu o kontenery.

* **Co zrobiono:** Pobranie oraz konfiguracja obrazów `appium`, `android-sdk` i `mobsf`.
* **Wniosek:** Wykorzystanie Docker pozwala uniknąć problemów z konfiguracją zależności na systemie lokalnym, zapewnia powtarzalność środowiska oraz izolację narzędzi. Dzięki temu każdy członek zespołu lub środowisko CI/CD może uruchomić identyczną konfigurację bez ręcznej instalacji.

---

### 🔹 BLOK 2: Debugowanie i Analiza Statyczna (MobSF)

Poznanie struktury aplikacji mobilnej przed rozpoczęciem testów.

* **Co zrobiono:** Wykorzystanie MobSF do analizy plików APK pod kątem luk bezpieczeństwa oraz wymaganych uprawnień.
* **Wniosek:** Analiza statyczna APK pozwala testerowi zrozumieć architekturę aplikacji, wykryć potencjalne podatności (np. niebezpieczne uprawnienia, hardcodowane dane, błędne konfiguracje) oraz przygotować bardziej świadome scenariusze testowe jeszcze przed uruchomieniem aplikacji.

---

### 🔹 BLOK 3-4: Fundamenty Skryptowania (Python for QA)

Tworzenie podstaw logiki testowej w Pythonie.

* **Co zrobiono:** Praca z podstawowymi strukturami danych, takimi jak listy, słowniki i krotki, które były wykorzystywane do przechowywania danych testowych oraz odpowiedzi API. Tworzono funkcje, moduły oraz wykorzystywano mechanizmy kontroli przepływu (pętle, instrukcje warunkowe). Dodatkowo zapoznano się z obsługą wyjątków (try/except) oraz organizacją kodu w formie testów automatycznych.

---

### 🔹 BLOK 5-7: Hybrydowe Testowanie API (Requests & Pytest)

Walidacja warstwy backendowej aplikacji mobilnej.

* **Co zrobiono:** Testowanie endpointów REST (JSONPlaceholder), obsługa kodów HTTP oraz weryfikacja odpowiedzi JSON.
* **Wniosek:** Testy API pozwalają wykryć problemy wcześniej, zanim uruchomione zostaną kosztowne testy UI.

---

### 🔹 BLOK 8: Appium UI Automation (Deep Dive)

Automatyzacja interakcji z interfejsem użytkownika.

* **Co zrobiono:** W testach UI wykorzystywano różne typy selektorów, w szczególności identyfikatory elementów (ID) oraz XPath do lokalizowania komponentów w hierarchii widoku aplikacji. Symulowane były typowe działania użytkownika, takie jak kliknięcia, wpisywanie tekstu, przewijanie ekranu (scroll), oczekiwanie na elementy (explicit waits) oraz nawigacja pomiędzy ekranami aplikacji.

---

### 🔹 BLOK 9: Konteneryzacja Serwera (Docker Compose)

Oddzielenie środowiska Appium od systemu operacyjnego.

* **Co zrobiono:** Utworzenie pliku `docker-compose.yml`, który zarządza uruchamianiem serwera Appium oraz sterowników. Dzięki temu możliwe było łatwe uruchamianie, zatrzymywanie i skalowanie usług testowych w jednym spójnym środowisku kontenerowym.

---

### 🔹 BLOK 10: MASTER PIPELINE (Capstone Project) 🏆

Końcowa automatyzacja całego procesu testowego.

* **Co zrobiono:** Implementacja skryptu `pipeline.py`, który w jednym przebiegu:

1. Rezerwuje zasoby i uruchamia środowisko Docker.
2. Wykonuje testy hybrydowe (API + UI).
3. Generuje raport Allure wraz z metadanymi.
4. Czyści środowisko po zakończeniu działania.

---

## 📊 Raportowanie Wyników (Allure)

W projekcie zastosowano rozbudowane raportowanie Allure, które umożliwia:

* Rejestrowanie kroków testowych (`@allure.step`).
* Analizę błędów wraz z dodatkowymi artefaktami (np. screenshoty, logi JSON).
* Dokumentowanie środowiska wykonawczego w sekcji **Environment**.

<img width="929" height="830" alt="image" src="https://github.com/user-attachments/assets/35791796-f0bb-41b4-b228-e60fd0ef4dfd" />


---

## 🚀 Jak uruchomić cały proces?

```bash
# Przejście do katalogu końcowego
cd Artefakt10

# Uruchomienie całego pipeline
python3 pipeline.py

# Po zakończeniu można uruchomić raport
allure serve allure-results
```
