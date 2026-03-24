## 🛡️ AUDYT BEZPIECZEŃSTWA: MANIFEST SCANNER
**Status:** Przeprowadzono automatyczną analizę ryzyka


### 📝 1. Zawartość pliku RiskyPermission.xml
Wykryto następujące istotne elementy:
* **Debuggable:** `true` (⚠️ WYSOKIE RYZYKO – aplikacja może być podatna na analizę i debugowanie w czasie rzeczywistym)
* **Permissions:** Zidentyfikowano uprawnienia umożliwiające dostęp do sieci (`INTERNET`) oraz pamięci zewnętrznej

### 🧠 2. Interpretacja inżynierska
Największym zagrożeniem jest aktywna flaga `debuggable`. Umożliwia ona wykorzystanie narzędzi takich jak `adb jdwp` do monitorowania działania aplikacji, co może zostać użyte przez nieautoryzowane osoby do analizy lub manipulacji.


### 🛠️ 3. Działania naprawcze
Zaleca się dodanie mechanizmu kontroli w pipeline CI/CD (np. Jenkins lub GitHub Actions), który automatycznie zatrzyma proces budowania aplikacji, jeśli w pliku `RiskyPermission.xml` wykryta zostanie flaga `debuggable="true"`.


#### 📌 Raport sporządzony przez:
**Podpis:** Vladyslav Petrenko 94590
**Data:** 24.03.2026
