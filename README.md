# Um algoritmo pseudopolinomial para maximizar uma função objetivo linear sobre pontos inteiros em elipsoides n-dimensionais 📐

Este repositório contém o código-fonte em LaTeX e os recursos computacionais referentes ao meu Trabalho de Conclusão de Curso (TCC) em Matemática na **Universidade Federal do Recôncavo da Bahia (UFRB)**.

## 👨‍🔬 Autor e Orientação
* **Autor:** Marcos Vinícius Barreto dos Santos
* **Orientador:** Prof. Dr. Eleazar Gerardo Madriz Lozada (CETEC/UFRB)
* **Status:** Em desenvolvimento (Defesa prevista para Julho/2026)

## 📌 Sobre o Projeto
O trabalho foca na análise, modelagem poliedral e implementação do **Algoritmo de Otimização Inteira em Elipsoides (AIOE)**. O método utiliza técnicas de fatiamento ortogonal recursivo para mapear os pontos extremais da envoltória convexa discreta (*Integer Hull*) de um hiperelipsoide.

## 🎥 Demonstrações e Recursos Visuais
Para garantir o acesso e a perenidade dos recursos visuais do algoritmo, utilizamos o YouTube como plataforma de hospedagem. O projeto conta com duas abordagens visuais distintas para diferentes públicos:

### 1. 🧬 Introdução à Otimização Inteira (Perspectiva Didática)
* ▶️ [**Assistir animação didática no YouTube**](https://youtu.be/bKN_NNsvDd0?si=3sigzNJXPA29Twyz)

**Guia de Compreensão Intuitiva:** Vídeo desenvolvido para introduzir conceitos básicos de Otimização Discreta sem jargões complexos. Ilustra geometricamente como as curvas de nível da função objetivo percorrem a região factível até atingir o ponto ótimo inteiro.

### 2. 📊 Dinâmica do Algoritmo AIOE (Perspectiva Técnica)
* ▶️ [**Assistir animação técnica no YouTube**](https://youtu.be/K7HpVdJK1hY?si=EuyrtPGT7hsRbw5P)

**Guia de Visualização Avançada:** O vídeo ilustra a varredura sistemática para encontrar pontos ótimos no conjunto ℤ₊², operando no fecho de um elipsoide em ℝ₊². Demonstra os deslocamentos discretos rente à fronteira combinatorial através da execução das funções auxiliares fₐ e gₐ.

---

## 🖼️ Recurso Estático Complementar: Redução Dimensional
Abaixo, a representação geométrica do processo de fatiamento sequencial detalhado na monografia, mostrando como o algoritmo colapsa sucessivamente subproblemas de dimensões superiores (ℝ³) em seções discretas bidimensionais analíticas (ℝ²):

![Fatiamento Inteligente](Redução_dimensional.png)

---

## 📊 Testes Computacionais — Algoritmo AIOE vs Gurobi 12.0

Para validar a exatidão e a eficiência do algoritmo AIOE, foram realizados testes numéricos comparativos contra o solver comercial Gurobi 12.0. Os testes foram executados utilizando instâncias geradas aleatoriamente com semieixos variando no intervalo $[1, 1000]$.

### Instâncias para $n = 4$

| $a_1$ | $a_2$ | $a_3$ | $a_4$ | $c_1$ | $c_2$ | $c_3$ | $c_4$ | AIOE OV | AIOE Time (s) | Gurobi OV | Gurobi Time (s) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 786,7 | 677,1 | 673,1 | 183,3 | 269 | 950 | 998 | 999 | 971220 | 4,611 | 971219 | 0,06585 |
| 813,5 | 614,3 | 191,9 | 91,8  | 202 | 220 | 348 | 578 | 229216 | 0,723 | 229214 | 0,05105 |
| 849,7 | 540,4 | 497,1 | 225,8 | 837 | 868 | 988 | 1000| 1008936| 3,723 | 1008924| 0,07288 |
| 967,1 | 341,4 | 263,8 | 250,1 | 522 | 791 | 809 | 867 | 648330 | 1,689 | 648306 | 0,08160 |
| 982,8 | 907,3 | 419,1 | 398,4 | 909 | 985 | 991 | 991 | 1387492| 7,709 | 1387474| 0,09876 |
| 879,5 | 767,7 | 37,6  | 5,6   | 723 | 869 | 971 | 979 | 922273 | 0,085 | 922236 | 0,02408 |
| 870,3 | 861,2 | 841,4 | 588,1 | 539 | 593 | 922 | 992 | 1192889| 20,847| 1192888| 0,08978 |
| 882,8 | 805,4 | 29,2  | 30,9  | 797 | 911 | 922 | 972 | 1052139| 0,483 | 1052129| 0,07003 |
| 924,2 | 703,9 | 442,3 | 204,6 | 138 | 412 | 633 | 698 | 446261 | 3,678 | 446253 | 0,07716 |
| 925,5 | 867,4 | 782,2 | 168,4 | 325 | 641 | 792 | 803 | 895336 | 6,100 | 895336 | 0,11073 |

### Instâncias para $n = 5$

| $a_1$ | $a_2$ | $a_3$ | $a_4$ | $a_5$ | $c_1$ | $c_2$ | $c_3$ | $c_4$ | $c_5$ | AIOE OV | AIOE Time (s) | Gurobi OV | Gurobi Time (s) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 566,3 | 506,1 | 418,4 | 154,2 | 146,1 | 396 | 774 | 985 | 988 | 989 | 646252 | 723,748| 646244 | 0,11305 |
| 730,5 | 410,4 | 317,5 | 157,2 | 8,4   | 696 | 753 | 999 | 1000| 1000| 695379 | 42,303 | 695355 | 0,12135 |
| 556,2 | 426,8 | 59,1  | 8,2   | 6,7   | 207 | 942 | 947 | 981 | 988 | 421906 | 0,367  | 421906 | 0,04929 |
| 350,7 | 278,8 | 199,5 | 78,7  | 35,8  | 777 | 973 | 987 | 999 | 1000| 440463 | 27,795 | 440463 | 0,08993 |
| 656,5 | 347,4 | 64,7  | 62,8  | 5,3   | 959 | 992 | 992 | 1000| 1000| 723279 | 1,766  | 723254 | 0,04193 |
| 679,7 | 559,3 | 255,6 | 163,9 | 147,7 | 632 | 725 | 798 | 807 | 910 | 652761 | 683,396| 652750 | 0,12523 |
| 859,7 | 523,7 | 406,8 | 131,5 | 76,7  | 880 | 966 | 970 | 973 | 992 | 1003047| 423,971| 1003043| 0,10948 |
| 508,2 | 185,8 | 76,3  | 27,5  | 18,2  | 709 | 839 | 845 | 849 | 898 | 398711 | 1,753  | 398711 | 0,05215 |
| 536,2 | 269,2 | 250,6 | 22,6  | 2,3   | 119 | 829 | 988 | 994 | 1000| 340005 | 1,070  | 340005 | 0,06782 |
| 965,3 | 791,6 | 759,5 | 589,3 | 152,1 | 165 | 276 | 330 | 484 | 606 | 475142 | 8880,69| 475135 | 0,12058 |

*\*Nota: "OV" refere-se ao Valor Ótimo (Optimal Value) numérico exato alcançado por cada método.*

---

## 🛠️ Ferramentas Utilizadas
* **LaTeX:** Para a redação acadêmica seguindo as normas ABNT (via classe `abntex2`).
* **VerbTeX Pro:** Ambiente mobile para gerenciamento, edição de código LaTeX e compilação via `PdfLaTeX`.
* **GitHub:** Hospedagem permanente do código e dos recursos multimídia.

---
© 2026 Marcos Vinícius Barreto - Licença MIT
