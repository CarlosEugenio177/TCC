# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Data-Centric Artificial Intelligence
* **Autores:** Johannes Jakubik; Michael Vössing; Niklas Kühl; Jannis Walk; Gerhard Satzger
* **Ano:** 2024 (Publicado online em 5 de março de 2024; fascículo: Volume 66, Edição 4, pp. 507–515)
* **Instituição/País:** Karlsruhe Institute of Technology (KIT) e University of Bayreuth, Alemanha
* **Local de publicação:** *Business & Information Systems Engineering (BISE)* (Springer - ISSN: 2363-7005)
* **DOI / Link:** [https://doi.org/10.1007/s12599-024-00857-8](https://doi.org/10.1007/s12599-024-00857-8)
* **Tipo de publicação:** Artigo científico / *Catchword* conceitual e estruturante em periódico de alto impacto
* **Tipo de pesquisa/metodologia:** Estudo analítico-conceitual, delimitação epistemológica e proposição de framework dimensional para inteligência artificial centrada em dados.

---

## 2. Objetivo do artigo
* **Problema investigado:** A predominância histórica e desproporcional do paradigma *Model-Centric AI* (foco quase exclusivo na modificação de arquiteturas de modelos e sintonia de hiperparâmetros mantendo a base de dados congelada), que ignora o fato de que dados imperfeitos, enviesados ou de baixa qualidade impõem um teto rígido ao desempenho e à confiabilidade dos sistemas inteligentes.
* **Objetivo principal:** Introduzir formalmente o paradigma emergente do *Data-Centric AI* (DCAI), contrastá-lo categoricamente com o paradigma centrado em modelos, estabelecer um framework multidimensional de trabalho com dados e delimitar suas fronteiras em relação à Engenharia de Dados tradicional, Gerenciamento de Qualidade de Dados (DQM) e MLOps.
* **Pergunta/Hipótese:** De que maneira uma transição sistemática para o paradigma *Data-Centric AI* — no qual o modelo é padronizado e o foco da engenharia volta-se para a qualidade, consistência e representatividade dos dados — impacta a eficácia e a eficiência de sistemas de inteligência artificial?

---

## 3. Principais conceitos
* **Data-Centric AI (DCAI):** Paradigma que preconiza o aprimoramento sistemático e escalável dos dados para construir sistemas de IA eficazes e eficientes, tratando o dado não como um insumo estático, mas como o principal artefato sob constante refatoração de engenharia.
* **Model-Centric AI vs. Data-Centric AI:** Contraste analítico: enquanto a abordagem model-cêntrica busca o melhor algoritmo para um conjunto estático de dados ($D_{fixo} ightarrow \max_{	heta} f(D)$), a abordagem data-cêntrica busca o melhor conjunto de dados mantendo a família algorítmica padronizada ($\max_{D} f_{	heta}(D)$).
* **Framework Dimensional de DCAI:** Quatro dimensões operacionais interdependentes:
  1. *Data Understanding:* Perfilamento estatístico, auditoria de consistência e detecção de anomalias;
  2. *Data Preparation:* Limpeza de ruído, imputação, seleção amostral e aumento sintético de dados (*augmentation*);
  3. *Data Validation:* Verificação de integridade, atendimento a requisitos de negócio e salvaguardas éticas;
  4. *Data Operations:* Orquestração contínua do ciclo de dados na esteira de produção (MLOps centrado em dados).
* **Eficácia vs. Eficiência de Dados:** A qualidade dos dados não apenas eleva a acurácia e a generalização do modelo (*eficácia*), mas reduz drasticamente os custos computacionais de treinamento e o esforço humano de anotação (*eficiência*).

---

## 4. Metodologia
* **Abordagem:** Analítico-conceitual e revisão integrativa de fundamentos em Sistemas de Informação e Computação.
* **Procedimento:** Análise crítica do movimento iniciado por Andrew Ng (2021) e consolidação da literatura dispersa em um framework teórico padronizado.
* **Critérios de diferenciação:** Mapeamento taxonômico distinguindo DCAI de disciplinas vizinhas (Data Engineering, DQM, MLOps e Active Learning).
* **Níveis de análise:** Avaliação dos impactos nos níveis individual (competências do cientista/engenheiro de dados), organizacional (governança e esteiras de dados) e interorganizacional (compartilhamento e princípios FAIR).

---

## 5. Principais resultados
* **Resultado 1 (A Superioridade Prática da Otimização de Dados):** O artigo demonstra que, em cenários industriais e corporativos reais, investir na melhoria qualitativa da base de treino (eliminação de rótulos inconsistentes e rebalanceamento) gera ganhos de desempenho preditivo ordens de magnitude superiores a semanas de busca exaustiva por novos modelos ou hiperparâmetros.
* **Resultado 2 (Formalização do Ciclo Data-Centric):** Estrutura um framework conceitual de 4 etapas que define exatamente onde a Engenharia de Dados intervém para alimentar os modelos com dados de alto valor.
* **Resultado 3 (Delimitação Epistemológica Clara):** O artigo elucida que o *Data-Centric AI* não anula a Engenharia de Dados tradicional, mas a expande: a Engenharia de Dados tradicional foca em latência, volume e integridade transacional, enquanto o DCAI adiciona a camada de conformidade estatística indutiva requerida pelos estimadores de aprendizado de máquina.
* **Importância para o TCC:** Proporciona o referencial conceitual perfeito para estruturar a Introdução e o Capítulo 2, conferindo rigor metodológico à justificativa da centralidade dos dados.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL / CONCEITUAL**
* **Justificativa:** É o manifesto teórico e conceitual contemporâneo publicado na prestigiosa *Springer BISE* que respalda academicamente a tese de que a Engenharia de Dados é o vetor primário da confiabilidade em Machine Learning.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 1 (Introdução e Justificativa):** Para contrapor o paradigma histórico *Model-Centric* à nova fronteira *Data-Centric*, justificando o tema do TCC.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para fundamentar o framework dimensional de Engenharia de Dados orientada a modelos de IA.
* **Capítulo 6 (Considerações Finais):** Para orientar as diretrizes de governança e apontar as competências de dados essenciais para o futuro da área.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 507):** *"Data-centric artificial intelligence (data-centric AI) represents an emerging paradigm that emphasizes the importance of enhancing data systematically and at scale to build effective and efficient AI-based systems. The novel paradigm complements recent model-centric AI, which focuses on improving the performance of AI-based systems based on changes in the model using a fixed set of data."*  
  * *Uso no TCC:* Introdução do trabalho para definição formal de Data-Centric AI.
* **Trecho 2 (p. 508):** *"Despite a long history of research on data, the impact of data quantity and quality on AI-based systems is still often overlooked in both AI research and AI practice."*  
  * *Uso no TCC:* Justificativa da relevância acadêmica e corporativa do TCC.
* **Trecho 3 (p. 509):** *"In data-centric AI, the focus shifts to designing and engineering the dataset itself while keeping the model architecture relatively fixed."*  
  * *Uso no TCC:* Capítulo 2 para caracterizar a metodologia de Engenharia de Dados para ML.
