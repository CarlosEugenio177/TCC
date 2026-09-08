# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Leakage and the reproducibility crisis in machine-learning-based science
* **Autores:** Sayash Kapoor; Arvind Narayanan
* **Ano:** 2023 (Publicado em 8 de setembro de 2023)
* **Instituição/País:** Department of Computer Science e Center for Information Technology Policy, Princeton University, Princeton, NJ, EUA
* **Local de publicação:** *Patterns* (Cell Press / Elsevier - Open Access, ISSN: 2666-3899)
* **Volume, número e páginas:** Volume 4, Edição 9, Artigo 100804, 16 páginas
* **DOI / Link:** [https://doi.org/10.1016/j.patter.2023.100804](https://doi.org/10.1016/j.patter.2023.100804)
* **Tipo de publicação:** Artigo de pesquisa científica / Meta-análise e estudo empírico investigativo
* **Tipo de pesquisa/metodologia:** Levantamento de revisões de reprodutibilidade em larga escala, meta-análise cobrindo 294 artigos em 17 campos científicos, proposição de taxonomia sistemática, desenvolvimento de ferramenta de auditoria (*Model Info Sheets*) e estudo de caso empírico de replicação.

---

## 2. Objetivo do artigo
* **Problema investigado:** A crise generalizada de reprodutibilidade em pesquisas e aplicações que utilizam Machine Learning decorrente de **Vazamento de Dados (*Data Leakage*)**. O vazamento ocorre quando informações espúrias do conjunto de teste ou do momento futuro contaminam a fase de pré-processamento e treinamento do modelo, gerando avaliações infladas de acurácia que desaparecem completamente quando o sistema é confrontado com novos dados no mundo real.
* **Objetivo principal:** Investigar a extensão global do problema de vazamento de dados na literatura científica, fornecer uma taxonomia exaustiva dos modos de falha que geram vazamento e propor uma ferramenta prática e formal (*Model Info Sheets*) para detectar, auditar e prevenir esses erros em pipelines de ML.
* **Pergunta/Hipótese:** De que maneira decisões metodológicas incorretas na Engenharia de Dados — como pré-processamento conjunto antes da partição treino/teste, seleção de atributos sobre a base completa, duplicatas e partição temporal imprópria — geram estimativas enganosas de desempenho e ilusões de superioridade de modelos complexos de ML?

---

## 3. Principais conceitos
* **Data Leakage (Vazamento de Dados):** Falha grave de engenharia e modelagem em que informações do conjunto de teste ou do processo de avaliação influenciam indevidamente o pré-processamento, a seleção de atributos ou o treinamento do modelo indutivo.
* **Taxonomia dos 8 Tipos de Vazamento de Dados (em 3 Macro-Eixos):**
  1. *Falta de Separação Limpa Treino/Teste:*
     - `[L1.1]` Ausência de conjunto de teste independente (reavaliação no treino);
     - `[L1.2]` Pré-processamento executado na base inteira antes do split (imputação de missing values, normalização, padronização ou sobreamostragem sintética como SMOTE aplicados conjuntamente);
     - `[L1.3]` Seleção de atributos (*feature selection*) realizada sobre a base completa;
     - `[L1.4]` Presença de registros duplicados distribuídos simultaneamente no treino e teste.
  2. *Atributos Ilegítimos:*
     - `[L2.1]` Features que atuam como proxies diretas da variável dependente (*outcome proxy*);
     - `[L2.2]` Features indisponíveis no momento real da predição (*look-ahead bias* / vazamento temporal de variáveis).
  3. *Inadequação Amostral do Conjunto de Teste perante a Distribuição de Interesse:*
     - `[L3.1]` Vazamento temporal decorrente de divisão aleatória em dados longitudinais/séries temporais;
     - `[L3.2]` Falta de separação por grupos (dados do mesmo paciente, cliente ou usuário divididos entre treino e teste);
     - `[L3.3]` Viés de amostragem no conjunto de dados.
* **Model Info Sheets:** Framework com 21 perguntas estruturadas que impõe aos desenvolvedores o ônus da prova de conformidade dos pipelines de dados para assegurar ausência de vazamento.
* **A Ilusão de Superioridade de ML:** Comprovação empírica de que quando o vazamento é corrigido, a suposta superioridade de modelos neurais complexos em relação a métodos estatísticos clássicos muitas vezes evapora.

---

## 4. Metodologia
* **Abordagem:** Quantitativa e qualitativa rigorosa (meta-pesquisa e replicação empírica).
* **Corpus analisado:** Ampla revisão bibliográfica de estudos anteriores de reprodutibilidade, consolidando a análise de **294 artigos científicos afetados por data leakage em 17 diferentes áreas do conhecimento** (medicina, finanças, ciências políticas, visão computacional, etc.).
* **Experimento de replicação:** Estudo de caso empírico replicando a literatura de predição de guerras civis, reexecutando modelos com e sem correção dos 8 tipos de vazamento de dados.
* **Métricas:** Área sob a curva ROC (AUC), Acurácia balanceada e erro fora da distribuição (*Out-of-Distribution*).

---

## 5. Principais resultados
* **Resultado 1 (A Escala Pandêmica do Vazamento de Dados):** O vazamento de dados não é um erro isolado, mas uma falha endêmica em toda a ciência aplicada baseada em ML, afetando centenas de estudos revisados por pares e falseando reivindicações de descobertas científicas.
* **Resultado 2 (O Pré-processamento Compartilhado como Falha Mais Frequente):** O tipo `[L1.2]` (normalização, cálculo de média para imputação ou aplicação de técnicas de balanceamento como SMOTE sobre toda a base antes da partição treino/teste) é a forma mais comum e silenciosa de corromper a validade de um modelo.
* **Resultado 3 (A Desmistificação da Superioridade Algorítmica):** No estudo de caso empírico de previsão de guerras civis, modelos complexos de ML que alegavam superar amplamente métodos clássicos de regressão logística tiveram sua superioridade completamente anulada quando o vazamento temporal e de agrupamento foi corrigido, demonstrando que a vantagem reportada era pura ilusão matemática induzida por falhas de Engenharia de Dados.
* **Importância para o TCC:** Constitui o referencial definitivo para o TCC na discussão de *Data Leakage*, demonstrando que o isolamento e o rigor das operações de pré-processamento de dados são cruciais para a validade de qualquer sistema de Machine Learning.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL / INDISPENSÁVEL**
* **Justificativa:** O tema *Data Leakage* consta expressamente nos objetivos metodológicos do seu Pré-Projeto (linha 82). Este artigo é a referência mundial definitiva sobre o assunto, conectando diretamente o pipeline de preparação e pré-processamento à confiabilidade da avaliação de modelos.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 1 (Introdução e Justificativa):** Para ilustrar a falsa sensação de alta performance decorrente de vazamento de dados e a crise de reprodutibilidade em IA.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para fundamentar a necessidade de isolamento estrito de pipelines de transformação (*scikit-learn Pipelines*) impedindo contaminações entre lotes.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para detalhar a taxonomia de 8 tipos de vazamento de dados na partição treino/validação/teste e o perigo de imputação ou reamostragem pré-partição.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para analisar o vazamento temporal `[L3.1]` e a falta de separação por grupos `[L3.2]` como quebras graves de confiabilidade estatística.
* **Capítulo 6 (Considerações Finais):** Para sugerir a adoção de auditorias baseadas em *Model Info Sheets* nas diretrizes de governança.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 1):** *"Data leakage is a widespread failure mode in machine-learning-based science. Based on a survey of past reviews, we find that it affects at least 294 papers across 17 disciplines. We provide a taxonomy of eight types of leakage and propose model info sheets to mitigate it."*  
  * *Uso no TCC:* Introdução do Capítulo 3 na seção dedicada a Data Leakage.
* **Trecho 2 (p. 1):** *"Several papers claimed that ML models drastically outperform older regression models. This is no longer the case when leakage is fixed."*  
  * *Uso no TCC:* Capítulo 1 e Capítulo 5 para demonstrar a fragilidade das métricas de laboratório sem engenharia de dados adequada.
* **Trecho 3 (p. 4):** *"Using the entire dataset for any pre-processing steps, such as imputation or over/under sampling, results in leakage. For instance, using oversampling before splitting the data into training and test sets leads to an imperfect separation between the training and test sets..."*  
  * *Uso no TCC:* Capítulo 2 e 3 para fundamentar o cuidado metodológico mandatório ao aplicar imputação (Barros & Melo) e SMOTE (Batista).
