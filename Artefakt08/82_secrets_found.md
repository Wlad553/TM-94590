## 🛡️ RAPORT ANALIZY WYCIEKÓW (SECRETS)

**Student:** Vladyslav Petrenko
**Indeks:** 94590
**Data raportu:** 24-03-2026

## 🛑 1. Najpoważniejsze znaleziska (High Risk)

*Elementy wymagające natychmiastowej reakcji w kodzie źródłowym:*

1. **[URL_Endpoint] → `http://www.example.com/lala/foobar@example.com`**

   * *Uzasadnienie:* Adres URL zawiera e-mail, co może oznaczać wyciek danych użytkownika lub hardcodowane dane testowe.

2. **[Potential_Secret] → `password`**

   * *Uzasadnienie:* Występowanie tego słowa w `strings.xml` sugeruje możliwość przechowywania domyślnego hasła do systemu lub usługi.

3. **[Potential_Secret] → `reset_password_warning`**

   * *Uzasadnienie:* Może wskazywać na lokalną implementację mechanizmu resetu hasła, która potencjalnie może zostać wykorzystana w nieautoryzowany sposób.


## 🟢 2. Znaleziska typu "False Positive" (Low/No Risk)

*Elementy błędnie oznaczone jako zagrożenia:*

1. **[URL_Endpoint] → `http://www.google.com`**

   * *Uzasadnienie:* Standardowy adres wykorzystywany np. do testów połączenia sieciowego.

2. **[API_Key_Format] → `table_layout_1_triple_star`**

   * *Uzasadnienie:* Nazwa identyfikatora UI, która przypadkowo pasuje do wzorca klucza API.

3. **[API_Key_Format] → `abc_font_family_display_3_material`**

   * *Uzasadnienie:* Systemowy zasób czcionek z biblioteki Material Design, bez znaczenia bezpieczeństwa.


## 🎓 Wnioski końcowe

Automatyczne skanowanie oparte na wyrażeniach regularnych (RegEx) jest przydatnym narzędziem do wykrywania potencjalnych zagrożeń, jednak nie zastępuje analizy eksperckiej. **Kluczowa pozostaje ręczna weryfikacja**, ponieważ narzędzia nie uwzględniają kontekstu aplikacji ani logiki biznesowej.
