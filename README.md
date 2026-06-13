# 📱 Mobile Automation & Cloud-Ready Testing Suite

**Prowadzący:** mgr Mariusz Dworniczak 
**Student:** Klaudia Bernat
**Numer Albumu:** 99711

---

## 🏗️ Architektura Projektu (Marketing & Tech Stack)
Ten projekt to kompletny ekosystem testowy oparty na podejsciu **Cloud-Ready / Headless**. Zamiast polegać na ciężkich emulatorach, skupiamy się na narzędziach CLI, analizie statycznej, konteneryzacji (Docker) oraz automatyzacji procesów (Pipeline). 

**Główne technologie:**
* **Język:** Python 3.10+
* **Automatyzacja UI:** Appium 2.x (Mobile Engine)
* **Infrastruktura:** Docker & Docker Compose
* **Raportowanie:** Allure Framework
* **Analiza:** MobSF (Static Analysis) & ADB CLI

---

## 📅 PRZEBIEG LABORATORIUM (Kamienie Milowe)

### 🔹 BLOK 1: Tooling & Environment (Infrastruktura)
Przygotowanie bazy narzędziowej w modelu kontenerowym.
* **Co zrobiono:** Pobranie i konfiguracja obrazów `appium`, `android-sdk` oraz `mobsf`.
* **Wniosek:** Użycie obrazów Docker upraszcza konfigurację i pozwala na powtarzalne środowisko bez lokalnych konfliktów.

### 🔹 BLOK 2: Debugowanie i Analiza Statyczna (MobSF)
Zrozumienie "wnętrza" aplikacji mobilnej przed przystąpieniem do testów.
* **Co zrobiono:** Wykorzystanie MobSF do skanowania plików APK pod kątem podatności i uprawnień.
* **Wniosek:** Analiza statyczna pozwala wykryć ryzyka bezpieczeństwa i nieprawidłowe uprawnienia zanim aplikacja trafi do testów dynamicznych.

### 🔹 BLOK 3-4: Fundamenty Skryptowania (Python for QA)
Budowa logiki testowej w języku Python.
* **Co zrobiono:** Tworzenie skryptów testowych wykorzystujących listy, słowniki i funkcje do walidacji danych oraz strukturę testów w `pytest`.

### 🔹 BLOK 5-7: Hybrydowe Testowanie API (Requests & Pytest)
Weryfikacja warstwy backendowej aplikacji mobilnej.
* **Co zrobiono:** Testowanie endpointów REST (JSONPlaceholder), obsługa kodów HTTP i asercja danych JSON.
* **Wniosek:** Testowanie API pozwala wyłapać błędy zanim uruchomimy ciężkie testy UI.

### 🔹 BLOK 8: Appium UI Automation (Deep Dive)
Automatyzacja interakcji z interfejsem użytkownika.
* **Co zrobiono:** Praca z selektorami ID i XPath oraz symulacja działań użytkownika, takich jak kliknięcia, przewijanie i wprowadzanie tekstu.

### 🔹 BLOK 9: Konteneryzacja Serwera (Docker Compose)
Izolacja silnika Appium od systemu operacyjnego.
* **Co zrobiono:** Stworzenie pliku `docker-compose.yml` zarządzającego serwerem Appium i sterownikami.

### 🔹 BLOK 10: MASTER PIPELINE (Capstone Project) 🏆
Finałowa automatyzacja całego procesu testowego.
* **Co zrobiono:** Stworzenie skryptu `pipeline.py`, który w jednym cyklu:
1. Rezerwuje zasoby i stawia infrastrukturę Docker.
2. Wykonuje testy hybrydowe (API + UI).
3. Generuje profesjonalny raport Allure z metadanymi.
4. Czyści środowisko po zakończonej pracy.

---

## 📊 Raportowanie Wyników (Allure)
Projekt wykorzystuje zaawansowane raportowanie Allure, które pozwala na:
* Śledzenie kroków testowych (`@allure.step`).
* Analizę błędów wraz z załącznikami (zrzuty ekranu, logi JSON).
* Dokumentowanie środowiska wykonawczego w sekcji **Environment**.

![Dashboard allure](image.png)

---

## 🚀 Jak uruchomić cały proces?
```bash
# Wejdź do folderu finałowego
cd Artefakt10

# Uruchom wszystko jednym poleceniem
python pipeline.py

# Po zakończeniu zobacz raport
allure serve allure-results

 