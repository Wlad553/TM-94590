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
* **Wniosek:** [OPISZ SAM - dlaczego używamy obrazów Docker zamiast instalować wszystko lokalnie?]

---

### 🔹 BLOK 2: Debugowanie i Analiza Statyczna (MobSF)

Poznanie struktury aplikacji mobilnej przed rozpoczęciem testów.

* **Co zrobiono:** Wykorzystanie MobSF do analizy plików APK pod kątem luk bezpieczeństwa oraz wymaganych uprawnień.
* **Wniosek:** [OPISZ SAM - co daje testerowi analiza statyczna kodu APK?]

---

### 🔹 BLOK 3-4: Fundamenty Skryptowania (Python for QA)

Tworzenie podstaw logiki testowej w Pythonie.

* **Co zrobiono:** [OPISZ SAM - jakich struktur danych i mechanizmów używałeś?]

---

### 🔹 BLOK 5-7: Hybrydowe Testowanie API (Requests & Pytest)

Walidacja warstwy backendowej aplikacji mobilnej.

* **Co zrobiono:** Testowanie endpointów REST (JSONPlaceholder), obsługa kodów HTTP oraz weryfikacja odpowiedzi JSON.
* **Wniosek:** Testy API pozwalają wykryć problemy wcześniej, zanim uruchomione zostaną kosztowne testy UI.

---

### 🔹 BLOK 8: Appium UI Automation (Deep Dive)

Automatyzacja interakcji z interfejsem użytkownika.

* **Co zrobiono:** [OPISZ SAM - jakie selektory wykorzystywałeś (ID, XPath)? Jakie operacje były symulowane na urządzeniu?]

---

### 🔹 BLOK 9: Konteneryzacja Serwera (Docker Compose)

Oddzielenie środowiska Appium od systemu operacyjnego.

* **Co zrobiono:** Utworzenie pliku `docker-compose.yml`, który zarządza uruchamianiem serwera Appium oraz sterowników.

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

[TUTAJ WRZUĆ SCREENA SWOJEGO DASHBOARDU ALLURE]

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
