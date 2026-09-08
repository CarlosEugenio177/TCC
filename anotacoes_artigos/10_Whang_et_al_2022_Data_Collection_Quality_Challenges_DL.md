# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Data Collection and Quality Challenges in Deep Learning: A Data-Centric AI Perspective
* **Autores:** Steven Euijong Whang; Yuji Roh; Hwanjun Song; Jae-Gil Lee
* **Ano:** 2022 (Versão v3 revisada: 26 de dezembro de 2022; baseado em tutoriais do VLDB 2020 e ACM KDD 2021)
* **Instituição/País:** Korea Advanced Institute of Science and Technology (KAIST) e Naver AI Lab, Coreia do Sul
* **Local de publicação:** *arXiv:2112.06409v3 [cs.LG]* / Extensão dos tutoriais de conferências de topo em bancos de dados e mineração de dados (*VLDB 2020* e *ACM SIGKDD 2021*)
* **DOI / Link:** [arXiv:2112.06409](https://arxiv.org/abs/2112.06409)
* **Tipo de publicação:** Artigo tutorial / *Survey* metodológico aprofundado
* **Tipo de pesquisa/metodologia:** Levantamento sistemático da literatura, mapeamento taxonômico e framework comparativo integrando a comunidade de Gerenciamento de Dados (*Data Management*) e Inteligência Artificial (*Deep Learning*).

---

## 2. Objetivo do artigo
* **Problema investigado:** A consolidação do paradigma *Software 2.0* (onde o aprendizado de máquina substitui a codificação manual de regras) gerou uma demanda exponencial por dados massivos e de alta qualidade. No entanto, conjuntos de dados do mundo real são rotineiramente escassos, ruidosos, incompletos, desbalanceados, enviesados ou até envenenados (*poisoned*). Embora os modelos de *Deep Learning* reduzam a dependência de engenharia de atributos manual, eles transferem todo o esforço para a coleta sistemática e a garantia da qualidade dos dados.
* **Objetivo principal:** Apresentar uma visão taxonômica abrangente e rigorosa dos desafios e técnicas de Coleta de Dados (*Data Collection*) e Qualidade de Dados (*Data Quality*) sob a ótica do *Data-Centric AI*, englobando métodos aplicáveis antes do treinamento (pré-processamento e saneamento), durante o treinamento (otimização robusta e equitativa) e no pós-processamento.
* **Pergunta/Hipótese:** De que maneira técnicas sistemáticas de Engenharia de Dados — como aquisição de dados, validação de esquemas/anomalias, limpeza declarativa, atenuação de ruído e mitigação algorítmica de viés — garantem a convergência e a confiabilidade de modelos de aprendizado profundo mesmo diante de dados imperfeitos?

---

## 3. Principais conceitos
* **Software 2.0 e Data-Centric AI:** Paradigma em que a lógica do software é aprendida a partir dos dados, tornando o dado um cidadão de primeira classe equivalente ao código-fonte, exigindo práticas análogas de teste, validação e depuração.
* **Coleta de Dados (*Data Collection*):** Divide-se em aquisição (*Data Acquisition*: busca em repositórios, aumento de dados por interpolação/GANs e síntese de dados) e rotulagem (*Data Labeling*: supervisão fraca via *Snorkel*, aprendizado semi-supervisionado e rotulagem por consenso).
* **Validação e Limpeza de Dados (*Data Validation & Cleaning*):** Verificação automatizada de desvios em dados de ingestão (*TensorFlow Data Validation - TFDV*), identificação de anomalias estatísticas e restauração probabilística de integridade referencial (*HoloClean*, *ActiveClean*).
* **Treinamento Robusto (*Robust Model Training*):** Algoritmos projetados para mitigar a presença inevitável de dados imperfeitos: ruído em atributos (*noisy features*), ausência de atributos (*missing features*), ruído em rótulos (*noisy labels*) e escassez de anotações.
* **Treinamento Equitativo (*Fair Model Training*):** Formalização de métricas matemáticas de justiça (*Demographic Parity*, *Equalized Odds*, *Equal Opportunity*) e técnicas de desenviesamento aplicadas na etapa de dados (balanceamento, reponderação e representação invariante).

---

## 4. Metodologia
* **Abordagem:** Teórico-taxonômica, analítica e integradora de literatura científica em Ciência da Computação e Engenharia de Dados.
* **Corpus de análise:** Centenas de trabalhos científicos de fronteira publicados nos principais simpósios de banco de dados (SIGMOD, VLDB, ICDE) e conferências de aprendizado de máquina (NeurIPS, ICML, ICLR, KDD).
* **Estruturação analítica:** O artigo decompõe o ciclo de vida do dado em: (1) Aquisição e Rotulagem; (2) Validação, Limpeza, Sanitização e Integração Multimodal; (3) Algoritmos de Otimização Robusta e Equitativa.
* **Critérios de avaliação:** Avaliação da eficácia dos métodos quanto ao custo computacional, necessidade de intervenção humana (grau de automação), preservação da precisão do modelo e garantia de equidade estatística.

---

## 5. Principais resultados
* **Resultado 1 (Deslocamento do Esforço de Engenharia):** A maior parte do tempo e do custo no ciclo de desenvolvimento de sistemas modernos de aprendizado de máquina é despendida na preparação, validação e saneamento dos dados, e não na concepção arquitetural dos modelos.
* **Resultado 2 (Insuficiência de Limpezas Manuais):** Bases em escala massiva inviabilizam a limpeza manual pontual. Ferramentas declarativas de validação de dados (como *TFDV*) e limpeza estatística semi-supervisionada (*HoloClean*) são indispensáveis para garantir que dados incorretos não degradem silenciosamente os hiperplanos de decisão.
* **Resultado 3 (Convergência entre Robustez e Justiça):** Modelos treinados com dados desbalanceados ou com ruído concentrado em subgrupos vulneráveis não apenas perdem acurácia global, mas sofrem colapso de equidade (*fairness*). Técnicas de mitigação no nível de dados (*pre-processing fairness*) mostram-se mais portáveis e agnósticas a modelos do que restrições matemáticas na função de perda.
* **Importância para o TCC:** Estabelece a conexão técnica definitiva entre as operações formais de Engenharia de Dados (coleta, validação, limpeza) e o treinamento de modelos robustos, justos e generalizáveis.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL**
* **Justificativa:** É a síntese taxonômica mais completa da literatura internacional contemporânea sobre o ciclo de dados para modelos de aprendizado, servindo como catálogo formal de técnicas de Engenharia de Dados para os Capítulos 2, 3 e 4 do TCC.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para fundamentar a taxonomia de coleta, validação automatizada de dados (*TFDV*) e técnicas modernas de limpeza de dados.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para explicar os desafios de treinamento com dados imperfeitos (*noisy features*, *noisy labels*) e técnicas de aumento de dados (*Data Augmentation*).
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para fundamentar as métricas formais de justiça (*fairness*) e os métodos de desenviesamento aplicados na fase de pré-processamento.
* **Capítulo 5 (Análise Integrada da Literatura):** Para integrar a visão de banco de dados/engenharia de software à visão de inteligência artificial estatística.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 1):** *"Data-centric AI is at the center of a fundamental shift in software engineering where machine learning becomes the new software, powered by big data and computing infrastructure. Here software engineering needs to be re-thought where data becomes a first-class citizen on par with code."*  
  * *Uso no TCC:* Introdução e Capítulo 2 para conceituar o dado como código no *Software 2.0*.
* **Trecho 2 (p. 1):** *"One striking observation is that a significant portion of the machine learning process is spent on data preparation. Without good data, even the best machine learning algorithms cannot perform well."*  
  * *Uso no TCC:* Justificativa inicial da primazia da Engenharia de Dados sobre os algoritmos de ML.
* **Trecho 3 (p. 2):** *"Unfortunately, many datasets in the real world are small, dirty, biased, and even poisoned. [...] We thus study fairness measures and unfairness mitigation techniques that can be applied before, during, or after model training."*  
  * *Uso no TCC:* Capítulo 4 para fundamentar a relação intrínseca entre qualidade de dados, viés e confiabilidade.
