# Plan: Analityka menadżera i właściciela

> Materiał roboczy do makiety panelu zarządczego Freedom Nieruchomości.
> Wszystkie dane pozostają przykładowe i fikcyjne.
> Data utworzenia planu: 2026-07-19 · Gałąź: `claude/test-komunikacji-ri6li5`

## Cel

Rozbudować makietę o dwie osobne perspektywy analityczne:

1. **Widok menadżera (kierownika biura)** — operacyjny, „co dzieje się teraz i w tym
   miesiącu w moim biurze / moim zespole".
2. **Widok właściciela (zarząd sieci)** — strategiczny, „jak stoi cała sieć biur,
   gdzie są pieniądze i gdzie są ryzyka".

Punkt wyjścia: istniejący `dashboard-freedom.html`, wariant **C — widok zarządczy 3 biur**.

## Stan obecny (co już jest)

- `index.html` — rozdzielnik makiet.
- `dashboard-freedom.html` — desktop, 3 zakładki: A) aktywność agentów, B) pipeline i
  prowizje, C) widok zarządczy 3 biur.
- `dashboard-freedom-app.html` — wersja mobilna (aplikacja).
- `dashboard-freedom-mobile.html` — podgląd „glance".
- `raport-agenta.html` — dzienny raport agenta.

## Zakres — widok MENADŻERA

Perspektywa: kierownik jednego biura / zespołu.

- **KPI zespołu (dziś / ten miesiąc):** liczba leadów, telefony, % obdzwonionych,
  spotkania, umowy pośrednictwa, transakcje, prognoza prowizji.
- **Realizacja celu miesiąca** — pasek postępu zespołu + rozbicie na agentów.
- **Ranking agentów** — kto dowozi, kto odstaje (aktywność vs. efekt).
- **Alerty operacyjne** — leady bez kontaktu, transakcje utykające na etapie,
  agenci poniżej normy aktywności.
- **Lejek zespołu** — lead → kontakt → spotkanie → umowa → transakcja → prowizja.

## Zakres — widok WŁAŚCICIELA

Perspektywa: zarząd całej sieci.

- **KPI sieci (miesiąc / kwartał / narastająco):** przychód z prowizji, liczba
  transakcji, średnia prowizja, wartość pipeline, konwersja lead→transakcja.
- **Porównanie biur** — ranking i udział każdego biura w wyniku sieci.
- **Trend** — wynik miesięczny w czasie (np. 6–12 miesięcy) + prognoza.
- **Zdrowie pipeline** — wartość i wiek transakcji w toku, ryzyko poślizgu.
- **Ludzie** — liczba aktywnych agentów, rotacja, produktywność na agenta.

## Propozycja realizacji (kolejność)

1. **Krok 1 — Menadżer:** rozbudowa zakładki C w `dashboard-freedom.html` lub nowa
   zakładka „D — Menadżer biura" (do ustalenia). Makieta statyczna, dane przykładowe.
2. **Krok 2 — Właściciel:** nowa zakładka „E — Właściciel / cała sieć" z KPI sieci,
   porównaniem biur i trendem.
3. **Krok 3 — Mobile:** przeniesienie kluczowych kafli do wersji app/glance.
4. **Krok 4 — Spójność danych:** wspólny zestaw fikcyjnych liczb, tak by wszystkie
   widoki się zgadzały (jak dziś między A/B/C).

## Do decyzji (pytania do Krzysztofa)

- Menadżer widzi **tylko swoje biuro**, czy może przełączać biura?
- Osobne pliki HTML dla menadżera/właściciela, czy kolejne zakładki w istniejącym
  dashboardzie?
- Które wskaźniki są „must have" na pierwszy ekran właściciela?
- Horyzont czasu dla trendu (6 czy 12 miesięcy)?

---
_Status: plan zapisany, czeka na akceptację zakresu przed implementacją._
