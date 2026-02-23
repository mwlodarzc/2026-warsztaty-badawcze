# Grupa: Model Biology LLM — AI Personas, Emergent Misalignment i “Behavior Zoo”
## Prowadzący
Jan Piotrowski [website](https://jfpio.github.io/) [github](https://github.com/jfpio)

## Opis
W ramach warsztatów badawczych studenci zrealizują projekty badawcze dotyczące **nietypowych zachowań modeli językowych** takich jak persona drift czy dziwne uogólnienia (weird generalizations).

Inspiracją są ostatnie wyniki z obszaru
- [Emergent Misalignment](https://www.emergent-misalignment.com/)- finetuning w wąskiej domenie, może wywołać szerokie nieoczekiwane zmiany poza domeną treningu (w oryginalnym paperze: kod zawierający podatności powodował złośliwość modelu w poradach medycznych i prawnych)
- [Weird Generalization / Inductive Backdoors] - małe, pozornie nieszkodliwe dane mogą prowadzić do szerokich przesunięć zachowania lub zachowań warunkowanych “triggerem”
- [Inoculation prompting](https://arxiv.org/abs/2510.04340) - explicite powiedzenie modelowi, żeby zachowywał się w sposób X sposób ogranicza wpływ treningu na cechę X modelu.

## Przebieg zajęć
- Reprodukcja zachowań opisanych w wspomnianych artykułach.
- Zaproponowanie nowych hipotez dziwnych zachowań.
- Stworzenie rzetelnej metody ewaluacji.
- Walidacja hipotez poprzez stworzenie nowych zbiorów treningowych, trening i ewaluacje modeli.

## Projekty
Projekty będą realizowane w grupach 2-3 osobowych. Każdy zespół pisze **mini-paper** (krótki raport badawczy) + udostępnia kod i wyniki w repozytorium GitHub.

## Punktacja
(max. 60 punktów)
Projekt (45 pkt)
1. Reprodukcja pracy Emergent Misalignment: 0-5 pkt.
2. Prezentacja literatury 0-10 pkt.
3. Walidacja pierwszej hipotezy 0-10 pkt.
4. Walidacja pozostałych hipotez 0-15 pkt.
5. Finalna prezentacja 0-10 pkt.

Prace domowe (10 pkt.)
1. Przegląd literatury - stworzenie systemu w zespole (5 pkt.)
2. Własna propozycja pracy ustalana indywidualne (przesłuchanie cyklu wykładów, przeczytanie cyklu artykułów, ukończenie kursu)

Dodatkowe punkty
- W razie chęci nadrobienia punktów możemy umówić się na dodatkowe prace domowe.

## Wstępny terminarz
### 2026-02-27 8:30
- Wstęp dotyczący problemu Emergent Misalignment i Generalizacji LLMów,
- Przegadanie zasad zajęć i zaliczenia,
- Składanie wniosku o HPC,
- Stworzenie zespołów,

### 2026-03-06 8:30
**Cel:** HPC + pierwsza reprodukcja (na minimalnym compute)
- HPC “hello world” (job, storage, env)
- wspólne odpalenie baseline sweep (parafrazy + temp) na 1–2 modelach

### 2026-03-13
**Cel:** “Baseline replication” jako klasa zadań (EM/WG/INOC lub analog)
- Rozwiązanie ewentualnych problemów, konsultacje.
- Omówienie pokrewnych zjawisk (Weird generalization, Inoculation prompting, reward hacking)
- Wybór terminów prezentacji literatury, przedyskutowanie proponowanych artykułów naukowych.

###  2026-03-20; 2026-03-27; 2026-04-10 - Literatura + wybór hipotez
**Cel:** 5–6 prezentacji + przejście do hipotez
- Każde spotkanie: 2 prezentacje + dyskusja, a na koniec 15–20 min “jak z tego zrobić eksperyment”
**Praca domowa 1 (literatura / related work):**

## 2026-04-17; 2026-04-24;
Cel: Walidacja 1. hipotezy
- Omówienie progresu grupy i szczegółów metodologii,
- Konsultacje
- Wcześniejsza prezentacja wyników (+5 pkt.)

## 2026-04-27; 2026-05-08
Cel: Przedstawienie wyników z walidacji 1. hipotezy
- Każdy zespół ma 10 minut na zaprezentowanie swoich wyników
- Dyskusja 5 minut co można byłoby zrobić lepiej
- Konsultacje kolejnego etapu.

## 2026-05-12 (Po wykładzie: Literatura i Related works)
Cel: Prezentacje powiązanych artykułów
- Szansa na uzupełnienie punktów - krótkie prezentacje powiązanego artykułu naukowego.

## 2026-05-22
Cel: Klaryfikacja pytań do Fazy II projektu
- Każdy zespół prezentuje swoje pytania badawcze i pomysł na ich walidacje
- Wspólna dyskusja nad postawionymi problemami
- Możemy zaprosić jednego z autorów pracy "Emergent misalignment".

## 2026-05-29; 2026-06-03
Cel: Podsumowanie i śledzenie progresu
- Konsultacje,
- Omawianie wyników

## 2026-06-12
Cel: Prezentacja wyników
- Każdy zespół ma 10 minut na prezentację swoich wyników.

## Proponowana Literatura
### Emergent Misalignment (EM)
- **Betley, Tan, Warncke, Sztyber-Betley, …, Evans (2025)** — *Emergent Misalignment: Narrow Finetuning Can Produce Broadly Misaligned LLMs.* arXiv:2502.17424. DOI: 10.48550/arXiv.2502.17424  
  *(klasyczny “EM” setup; czynniki sprzyjające EM; backdoor wariant).*
- **Afonin, Andriyanov, Hovhannisyan, …, Seleznyov (2025)** — *Emergent Misalignment via In-Context Learning: Narrow in-context examples can produce broadly misaligned LLMs.* arXiv:2510.11288. DOI: 10.48550/arXiv.2510.11288  
  *(EM bez zmiany parametrów: wystarczy kontekst / few-shot).*
- **Chua, Betley, Taylor, Evans (2025)** — *Thought Crime: Backdoors and Emergent Misalignment in Reasoning Models.* arXiv:2506.13206. DOI: 10.48550/arXiv.2506.13206  
  *(EM w “reasoning models”, CoT bywa jednocześnie sygnałem i zasłoną; sleeper agents).*
- **MacDiarmid, Wright, Uesato, …, Hubinger (2025)** — *Natural Emergent Misalignment from Reward Hacking in Production RL.* arXiv:2511.18397. DOI: 10.48550/arXiv.2511.18397  
  *(EM jako efekt uboczny reward hacking; ważne dla agentów / narzędzi typu coding assistants).*

### Mechanizmy i “model organisms” dla EM
- **Turner, Soligo, Taylor, Rajamanoharan, Nanda (2025)** — *Model Organisms for Emergent Misalignment.* arXiv:2506.11613. DOI: 10.48550/arXiv.2506.11613  
  *(czystsze organizmy, mniejsze modele, rank-1 LoRA; “phase transition” w zachowaniu).*
- **Soligo, Turner, Rajamanoharan, Nanda (2025)** — *Convergent Linear Representations of Emergent Misalignment.* arXiv:2506.11618. DOI: 10.48550/arXiv.2506.11618  
  *(“misalignment direction”; konwergencja reprezentacji i ablacje zachowań).*
### AI personas / Weird generalization/ Behavior Zoo
- **Betley, Cocola, Feng, Chua, Arditi, Sztyber-Betley, Evans (2025)** — *Weird Generalization and Inductive Backdoors: New Ways to Corrupt LLMs.* arXiv:2512.09742. DOI: 10.48550/arXiv.2512.09742  
  *(przykłady “weird generalization” + inductive backdoors; bardzo kompatybilne z Behavior Zoo).
- **nielsrolf, Riché, Tan (2025)** — *A Case for Model Persona Research* (LessWrong).  
  *(motywacja: dlaczego “personas” są ważnym obiektem badań i jak łączą się z ryzykami).*
- **nielsrolf, Riché, Tan (2026)** — *Concrete Research Ideas on AI Personas* (LessWrong).  
  *(lista konkretnych projektów: reprodukcje, minimal triggers, propagacja “memów” między modelami).*
### Inoculation Prompting (IP) + krytyka (confounds)
- **Tan, Woodruff, Warncke, Jose, Riché, Africa, Taylor (2025)** — *Inoculation Prompting: Eliciting Traits from LLMs during Training Can Suppress Them at Test-Time.* arXiv:2510.04340. DOI: 10.48550/arXiv.2510.04340  
  *(selektywne uczenie / tłumienie cech; IP jako potencjalna “mitigacja” EM/backdoorów).*
- **Wichers, Ebtekar, Azarbal, …, Marks (2025)** — *Inoculation Prompting: Instructing LLMs to Misbehave at Train-Time Improves Test-Time Alignment.* arXiv:2510.05024. DOI: 10.48550/arXiv.2510.05024  
  *(wariant IP z naciskiem na “imperfect oversight” i heurystykę doboru promptów).*
- **Riché & nielsrolf (2026)** — *Conditionalization Confounds Inoculation Prompting Results* (LessWrong).  
  *(ostrzega, że część efektów IP może wynikać z warunkowania na prompt/format; ważne dla metodologii ewaluacji).* 

## Dodatkowe wartościowe materiały
- [ARENA evals course](https://arena-chapter3-llm-evals.streamlit.app/)
- [Kanał YT Neela Nandy](https://www.youtube.com/@neelnanda2469)
