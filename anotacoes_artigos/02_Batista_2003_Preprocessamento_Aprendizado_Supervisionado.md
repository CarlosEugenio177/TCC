# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Pré-processamento de Dados em Aprendizado de Máquina Supervisionado
* **Autor:** Gustavo Enrique de Almeida Prado Alves Batista
* **Orientadora:** Profa. Dra. Maria Carolina Monard
* **Ano:** 2003 (Data de depósito: 11/03/2003)
* **Instituição/País:** Instituto de Ciências Matemáticas e de Computação – Universidade de São Paulo (ICMC-USP), São Carlos - SP, Brasil.
* **Local de publicação:** Tese de Doutorado em Ciências de Computação e Matemática Computacional.
* **Link/Repositório:** Biblioteca Digital de Teses e Dissertações da USP
* **Tipo de publicação:** Tese de Doutorado
* **Tipo de pesquisa/metodologia:** Pesquisa experimental e metodológica comparativa em larga escala em Aprendizado de Máquina.

---

## 2. Objetivo do artigo
* **Problema investigado:** O impacto prejudicial que imperfeições na qualidade dos dados reais causam nos algoritmos de Aprendizado de Máquina supervisionado, focando especificamente em dois grandes problemas: (1) a presença de dados com valores ausentes/desconhecidos e (2) conjuntos de dados com distribuição de classes altamente desbalanceadas (*imbalanced classes*).
* **Objetivo principal:** Desenvolver, comparar e validar sistematicamente métodos e algoritmos de pré-processamento de dados capazes de tratar atributos com valores desconhecidos e reequilibrar classes minoritárias sem introduzir ruído prejudicial às fronteiras de decisão.
* **Pergunta/Hipótese:** Técnicas especializadas de pré-processamento aplicadas aos dados antes do treinamento (como imputação multivariada e a combinação de sobreamostragem sintética com filtragem de ruído por vizinhos mais próximos) produzem modelos mais acurados e generalizáveis do que os mecanismos internos padrões dos algoritmos de aprendizado?

---

## 3. Principais conceitos
* **Pré-processamento de Dados:** Conjunto estruturado de técnicas aplicadas na preparação e transformação da matriz de dados de entrada antes da fase de indução, atuando como o fator determinante da qualidade do conhecimento extraído.
* **Valores Ausentes e Métodos de Imputação:** Comparação formal entre eliminação de registros (*casewise deletion*), substituição por valor padrão, média/moda incondicional, média condicional à classe e abordagens baseadas em aprendizado indutivo (C4.5, CN2, KNN).
* **Desbalanceamento de Classes (*Class Imbalance*):** Assimetria na proporção entre classes onde a classe de interesse é minoritária; o autor demonstra como métricas ingênuas de acurácia global ($) favorecem a classe majoritária, induzindo os algoritmos a ignorar instâncias raras.
* **Técnicas de Reamostragem Inteligente:** Proposição e avaliação de métodos como *Tomek Links*, *Edited Nearest Neighbor* (ENN), *Neighborhood Cleaning Rule* (NCL), *SMOTE* (Synthetic Minority Over-sampling Technique) e métodos híbridos pioneiros desenvolvidos pelo autor (*SMOTE + Tomek Links* e *SMOTE + ENN*).
* **Métricas de Avaliação Robustas:** Curva ROC (*Receiver Operating Characteristic*), Área sob a Curva ROC (AUC), Sensibilidade (*Recall*), Especificidade e Média Geométrica (\text{-mean}$).

---

## 4. Metodologia
* **Abordagem:** Experimental-quantitativa exaustiva com rigor estatístico.
* **Fonte dos dados:** Dezenas de bases de dados reais do repositório internacional UCI Machine Learning Repository, abrangendo domínios médicos, biológicos e industriais.
* **Algoritmos de aprendizado utilizados:** C4.5 (Árvores de Decisão), RIPPER (Indução de Regras Proposicionais), Naive Bayes, CN2 e algoritmos baseados em instâncias.
* **Procedimentos experimentais:** Protocolo de validação cruzada estratificada em 10 partições (*10-fold cross-validation*), com introdução controlada de ruído, geração de diferentes taxas de incompletude e aplicação de testes estatísticos de significância para validação de hipóteses.

---

## 5. Principais resultados
* **Resultado 1 (Tratamento de Missing Values):** Métodos de imputação que preservam a estrutura de correlação entre atributos (como KNN e métodos indutivos) superam de forma estatisticamente significativa abordagens simplistas que ignoram as relações entre variáveis.
* **Resultado 2 (Balanceamento de Classes):** O método *SMOTE + Tomek Links* e o *SMOTE + ENN* demonstraram superioridade clara na remoção de amostras limítrofes e ruidosas (*borderline samples*), gerando fronteiras de decisão mais limpas e elevando substancialmente a AUC e o reconhecimento da classe minoritária sem degradar a classe majoritária.
* **Resultado 3 (A Centralidade do Dado de Entrada):** A tese demonstra empiricamente que o aprimoramento da qualidade dos dados via pré-processamento produz ganhos de desempenho superiores à mera substituição ou ajuste fino do algoritmo de aprendizado.
* **Importância para o TCC:** É a principal obra clássica brasileira que comprova formalmente que o tratamento e a qualidade dos dados de treinamento são mais determinantes para o sucesso do modelo do que a escolha isolada do algoritmo.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL**
* **Justificativa:** É a espinha dorsal teórica e metodológica da literatura brasileira para fundamentar os capítulos de Qualidade de Dados, Pré-processamento, Saneamento de Missing Values e Balanceamento de Classes.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Introdução & Justificativa:** Para fundamentar que a qualidade do modelo é determinada primariamente pela qualidade dos dados de entrada.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para classificar e detalhar os tipos de anomalias em bases de dados (ruído, incompletude, desbalanceamento).
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para explicar os métodos de pré-processamento (imputação, reamostragem, SMOTE, Tomek Links) e métricas ROC/AUC.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para sustentar como a sub-representação estatística gera viés indutivo em favor da classe majoritária.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 5):** *"Uma vez que a maioria dos algoritmos de aprendizado induz conhecimento estritamente a partir de dados, a qualidade do conhecimento extraído é amplamente determinada pela qualidade dos dados de entrada."*  
  * *Uso no TCC:* Citação seminal para a Introdução do TCC para justificar a centralidade dos dados sobre os algoritmos.
* **Trecho 2 (p. 21):** *"Diversos aspectos podem influenciar no desempenho de um sistema de aprendizado devido à qualidade dos dados. [...] A presença de ruído, valores desconhecidos e classes desbalanceadas pode distorcer severamente as fronteiras de decisão."*  
  * *Uso no TCC:* Fundamentar a relação de causa e efeito entre defeitos nos dados e falhas nas fronteiras de decisão.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho de ML: **Sim** (demonstrado em dezenas de experimentos).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (indução de regras espúrias ou vazias).
3. A preparação dos dados influencia o treinamento: **Sim** (núcleo e tese central da obra).
4. A representatividade dos dados influencia a generalização: **Sim** (classes raras ignoradas sem balanceamento).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (viés em direção à classe mais frequente).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (ajuste a instâncias ruidosas na fronteira).
7. Um bom desempenho na avaliação não garante boa generalização: **Sim** (acurácia global de 99% em bases desbalanceadas é ilusória).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (impacto crítico em diagnósticos médicos).
9. Processos de Engenharia de Dados melhoram a qualidade: **Sim** (sistematização formal do pipeline de pré-processamento).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (modelos convergem com acurácia alta, mas recall zero na classe crítica).

---

## 10. Limitações
* **Declaradas pelo autor:** O estudo focou nos paradigmas de aprendizado vigentes à época (árvores C4.5, regras e Naive Bayes), sem analisar redes neurais profundas modernas (*Deep Learning*).
* **Para o TCC:** Publicação seminal de 2003; seus fundamentos conceituais e algorítmicos permanecem plenamente vigentes, necessitando apenas de contextualização com as esteiras modernas de Engenharia de Dados.

---

## 11. Lacunas e oportunidades
* Integração dessas técnicas clássicas de pré-processamento em fluxos contínuos e arquiteturas distribuídas de Big Data (ex.: Spark/MLflow), foco contemporâneo da Engenharia de Dados.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Analisa sistematicamente incompletude, ruído e assimetria distribucional. |
| Preparação dos dados | Sim | Foco principal: imputação multivariada, filtragem de ruído e reamostragem. |
| Engenharia de Dados | Parcialmente | Usa a terminologia percursora de KDD/Pré-processamento de dados. |
| Viés | Sim | Viés indutivo provocado por assimetria amostral e classes majoritárias. |
| Representatividade | Sim | Avaliação da densidade e representatividade de classes minoritárias. |
| Generalização | Sim | Medida por meio de Curvas ROC, sensibilidade e validação cruzada. |
| Confiabilidade | Sim | Modelos mais robustos e interpretáveis para tomada de decisão. |
| Machine Learning | Sim | C4.5, RIPPER, CN2, Naive Bayes, KNN. |

---

## 13. Ficha de leitura final
* **Referência:** BATISTA, G. E. A. P. A. *Pré-processamento de Dados em Aprendizado de Máquina Supervisionado*. 2003. 232 f. Tese (Doutorado em Ciências de Computação) – Instituto de Ciências Matemáticas e de Computação, Universidade de São Paulo, São Carlos, 2003.
* **Problema:** Degradação de modelos de AM provocada por dados ausentes e distribuições desbalanceadas.
* **Objetivo:** Desenvolver e avaliar métodos de pré-processamento para otimizar o aprendizado indutivo.
* **Metodologia:** Pesquisa experimental comparativa com validação cruzada em bases da UCI.
* **Principais resultados:** Proposição e validação do SMOTE+Tomek e SMOTE+ENN; prova de que a qualidade dos dados supera o algoritmo.
* **Conceitos-chave:** Pré-processamento, Missing Values, Classes Desbalanceadas, SMOTE, Tomek Links, Curva ROC.
* **Contribuição para o TCC:** Fornece a base teórica estrutural para os capítulos de preparação e qualidade de dados.
* **Capítulo provável:** Capítulo 2, Capítulo 3 e Capítulo 4.
* **Citação mais importante:** *"Uma vez que a maioria dos algoritmos de aprendizado induz conhecimento estritamente a partir de dados, a qualidade do conhecimento extraído é amplamente determinada pela qualidade dos dados de entrada."*
* **Palavras-chave:** Pré-processamento de Dados; Aprendizado de Máquina Supervisionado; Desbalanceamento de Classes; Qualidade de Dados.

---

## 14. Avaliação final
* **Nota:** 10 / 10
* **Justificativa:** Obra de referência nacional indispensável, com rigor metodológico exemplar e alinhamento total à premissa do TCC.
* **Decisão:** **SIM** (Permanecer entre as 20 referências principais).
