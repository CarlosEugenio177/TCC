# ÍNDICE DOS TRABALHOS ANALISADOS (CORPUS BIBLIOGRÁFICO DO TCC)

**Tema do TCC:** *A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica*  
**Autor:** Carlos Eugênio Mendes Paes Landim  
**Área de Concentração:** Engenharia de Software | Engenharia de Dados | Inteligência Artificial | Machine Learning  

---

## 1. Narrativa Central do TCC

A revisão bibliográfica e a análise dos trabalhos fundamentam a cadeia de dependência estrutural de sistemas inteligentes:

$$\text{Dados} \longrightarrow \text{Qualidade dos Dados} \longrightarrow \text{Preparação e Tratamento} \longrightarrow \text{Representatividade} \longrightarrow \text{Viés} \longrightarrow \text{Treinamento} \longrightarrow \text{Generalização} \longrightarrow \text{Confiabilidade}$$

---

## 2. Mapa Geral dos Documentos Analisados (Corpus de 14 Trabalhos)

| # | Arquivo Original (PDF) | Título do Trabalho | Autores | Ano | Tipo / Veículo | Papel no TCC | Relevância | Fichamento Detalhado |
| :-: | :--- | :--- | :--- | :-: | :--- | :--- | :-: | :--- |
| **01** | `IMPACTO DA QUALIDADE DE DADOS PÚBLICOS...pdf` | *Impacto da Qualidade de Dados Públicos Tabulares no Desempenho de Modelos Clássicos de Machine Learning* | Barros & Melo | 2025 | Artigo (*RevistaFT*) | Demonstração matemática do impacto de missing values e métodos de imputação em Regressão, KNN e Árvores. | **CENTRAL** | [01_Barros_Melo_2025](anotacoes_artigos/01_Barros_Melo_2025_Qualidade_Dados_Tabulares_ML.md) |
| **02** | `TeseDoutorado.pdf` | *Pré-processamento de Dados em Aprendizado de Máquina Supervisionado* | Batista (Orient.: Monard) | 2003 | Tese Doutorado (ICMC-USP) | Fundamentação seminal em pré-processamento, missing values, ruído e classes desbalanceadas (SMOTE/Tomek). | **CENTRAL** | [02_Batista_2003](anotacoes_artigos/02_Batista_2003_Preprocessamento_Aprendizado_Supervisionado.md) |
| **03** | `LH_Masters.pdf` | *Mitigating Drift in Machine Learning Systems through Continuous Input Monitoring* | Rocha (Orient.: Braghetto) | 2026 | Dissertação Mestrado (IME-USP) | Arquitetura de Engenharia de Dados/MLOps para monitoramento contínuo não supervisionado de Data Drift. | **CENTRAL** | [03_Rocha_2026](anotacoes_artigos/03_Rocha_2026_Mitigating_Data_Drift_Continuous_Monitoring.md) |
| **04** | `2402.12715v4.pdf` | *The Clever Hans Mirage: A Comprehensive Survey on Spurious Correlations in Machine Learning* | Ye et al. | 2024/2025 | Survey Internacional (arXiv) | Taxonomia exaustiva sobre Correlações Espúrias, Efeito Clever Hans, atalhos nos dados e generalização OOD. | **CENTRAL** | [04_Ye_et_al_2024](anotacoes_artigos/04_Ye_et_al_2024_Clever_Hans_Spurious_Correlations.md) |
| **05** | `2295-10332-1-DR.pdf` | *O termo qualidade de dados na Ciência da Informação brasileira: uma análise de terminologia pontual* | Jesus, Barité & Santarem Segundo | 2024 | Anais de Congresso (XXIV ENANCIB) | Padronização conceitual e mapeamento das dimensões formais de Qualidade de Dados no Brasil. | **IMPORTANTE** | [05_Jesus_et_al_2024](anotacoes_artigos/05_Jesus_et_al_2024_Terminologia_Qualidade_Dados.md) |
| **06** | `Artigo+7+-+Natan+final.pdf` | *Inteligência Artificial e Desigualdade de Gênero entre Homens e Mulheres: uma análise dos vieses em processos seletivos de contratação* | Silva et al. | 2026 | Artigo (*Persp. Gestão & Conhec.*) | Evidência empírica recente sobre viés de dados históricos e variáveis proxy contaminando o treinamento de IA. | **IMPORTANTE** | [06_Silva_et_al_2026](anotacoes_artigos/06_Silva_et_al_2026_IA_Vies_Genero_Recrutamento.md) |
| **07** | `v23n50a49_stamped.pdf` | *Inteligência artificial, vieses algorítmicos e racismo: o lado desconhecido da justiça algorítmica* | Rosa & Guasque | 2024 | Artigo (*Opinión Jurídica*) | Análise crítica do viés algorítmico, feedback loops de dados viciados e o caso paradigmático COMPAS. | **IMPORTANTE** | [07_Rosa_Guasque_2024](anotacoes_artigos/07_Rosa_Guasque_2024_IA_Vieses_Algoritmicos_Racismo.md) |
| **08** | `VIÉS RACIAL EM SISTEMAS...pdf` | *Viés racial em sistemas de inteligência artificial: desafios para a responsabilidade civil e a necessidade de parametrização do risco* | Borges & Faleiros Júnior | 2023 | Artigo (*Revista IBERC*) | Omissão na curadoria de dados como dever de conduta técnica e governança no ciclo de vida de IA. | **IMPORTANTE** | [08_Borges_Faleiros_2023](anotacoes_artigos/08_Borges_Faleiros_2023_Vies_Racial_Responsabilidade_Civil.md) |
| **09** | `download.pdf` | *Machine Learning na Física, Química, e Ciência de Materiais: Descoberta e Design de Materiais* | Schleder & Fazzio | 2021 | Artigo Tutorial (*RBEF*) | Pipeline completo de dados, Feature Engineering, princípios FAIR e prevenção de Data Leakage em AM. | **IMPORTANTE** | [09_Schleder_Fazzio_2021](anotacoes_artigos/09_Schleder_Fazzio_2021_Machine_Learning_Ciencia_Dados.md) |
| **10** | `Data Collection and Quality Challenges in Deep Learning.pdf` | *Data Collection and Quality Challenges in Deep Learning: A Data-Centric AI Perspective* | Whang et al. | 2022 | Survey (arXiv / VLDB / KDD) | Taxonomia exaustiva de coleta, validação com TFDV, limpeza probabilística e treinamento robusto/justo. | **CENTRAL** | [10_Whang_et_al_2022](anotacoes_artigos/10_Whang_et_al_2022_Data_Collection_Quality_Challenges_DL.md) |
| **11** | `Data-Centric Artificial Intelligence.pdf` | *Data-Centric Artificial Intelligence* | Jakubik et al. | 2024 | Artigo (*BISE / Springer*) | Fundamentação conceitual do paradigma Data-Centric AI vs Model-Centric AI e framework de 4 dimensões. | **CENTRAL** | [11_Jakubik_et_al_2024](anotacoes_artigos/11_Jakubik_et_al_2024_Data_Centric_Artificial_Intelligence.md) |
| **12** | `Hidden_Technical_Debt_in_Machine_Learnin.pdf` | *Hidden Technical Debt in Machine Learning Systems* | Sculley et al. | 2015 | Conferência (*NeurIPS*) | O artigo seminal da Google que demonstra que 95% do sistema é infraestrutura de dados e formaliza o Débito Técnico em ML. | **CENTRAL** | [12_Sculley_et_al_2015](anotacoes_artigos/12_Sculley_et_al_2015_Hidden_Technical_Debt_ML_Systems.md) |
| **13** | `Systematic review of data-centric approaches in artificial intelligence and machine learning.pdf` | *Systematic review of data-centric approaches in artificial intelligence and machine learning* | Singh | 2023 | RSL (*Data Science and Management*) | Revisão sistemática sobre práticas de DCAI, Big Data vs Good Data, HoloClean e impactos da adição cega de dados. | **CENTRAL** | [13_Singh_2023](anotacoes_artigos/13_Singh_2023_Systematic_Review_Data_Centric_AI_ML.md) |
| **14** | `Kapoor_Narayanan_2023_Data_Leakage_Reproducibility.pdf` *(ex-mmc2.pdf)* | *Leakage and the reproducibility crisis in machine-learning-based science* | Kapoor & Narayanan | 2023 | Artigo (*Patterns / Cell Press*) | Estudo definitivo sobre Data Leakage em 294 estudos (17 áreas), taxonomia dos 8 tipos e protocolo Model Info Sheets. | **CENTRAL** | [14_Kapoor_Narayanan_2023](anotacoes_artigos/14_Kapoor_Narayanan_2023_Data_Leakage_Reproducibility_Crisis.md) |

---

## 3. Distribuição dos Trabalhos por Capítulo do TCC

### **Capítulo 1 — Introdução e Justificativa**
* **Objetivo da Seção:** Contextualizar o crescimento do ML, o deslocamento de paradigma de *Model-Centric* para *Data-Centric AI*, a ilusão das métricas infladas de bancada decorrentes de dados contaminados, os débitos técnicos ocultos e o impacto ético/legal de modelos enviesados.
* **Autores Chave:**
  * **Jakubik et al. (2024):** A inversão paradigmática de *Model-Centric* para *Data-Centric AI*.
  * **Sculley et al. (2015):** O débito técnico silencioso e a constatação de que o código de ML é apenas uma fração minúscula cercada por infraestrutura de dados.
  * **Kapoor & Narayanan (2023):** A crise de reprodutibilidade e a falácia de superioridade algorítmica mascarada por falhas na partição de dados.
  * **Ye et al. (2024/2025):** Efeito Clever Hans e a fragilidade de modelos que aprendem atalhos estatísticos nos dados.
  * **Rosa & Guasque (2024):** A desmistificação da neutralidade matemática e os riscos de sistemas discriminatórios.
  * **Borges & Faleiros Júnior (2023):** A curadoria técnica de dados como dever de conduta e conformidade na Engenharia de Software.
  * **Silva et al. (2026):** Evidências empíricas de modelos corporativos enviesados por dados históricos.

### **Capítulo 2 — Engenharia de Dados e Qualidade de Dados**
* **Objetivo da Seção:** Conceituar Engenharia de Dados orientada a IA, o ciclo de vida dos dados, dimensões de qualidade (acurácia, completude, consistência, atualidade), a transição de *Big Data* para *Good Data*, validação de esquemas em tempo real, princípios FAIR e ferramentas avançadas de saneamento e reparo probabilístico.
* **Autores Chave:**
  * **Jesus, Barité & Santarem Segundo (2024):** Mapeamento e taxonomia formal das dimensões de Qualidade de Dados na literatura brasileira.
  * **Whang et al. (2022):** Framework de validação automatizada de esquemas/anomalias (*TFDV*) e limpeza probabilística (*HoloClean*).
  * **Jakubik et al. (2024):** As 4 dimensões operacionais do trabalho de dados (*Data Understanding*, *Preparation*, *Validation* e *Operations*).
  * **Sculley et al. (2015):** Governança de dependências instáveis de dados e erradicação de *pipeline jungles*.
  * **Singh (2023):** O princípio do *Good Data* sobre o *Big Data* e a restauração declarativa de bases com *HoloClean*.
  * **Batista (2003):** Classificação formal dos tipos de anomalias em bases reais (incompletude, ruído, assimetria).
  * **Barros & Melo (2025):** Tratamento de valores ausentes (*missing values*) e impacto analítico da imputação de dados.
  * **Schleder & Fazzio (2021):** O pipeline de Engenharia de Dados, padronização em repositórios e princípios FAIR.
  * **Rocha (2026):** Arquiteturas de ingestão e monitoramento contínuo de dados na esteira de MLOps.

### **Capítulo 3 — Machine Learning e Dados de Treinamento**
* **Objetivo da Seção:** Apresentar os fundamentos do aprendizado supervisionado, a matriz de atributos, métodos de *Feature Engineering*, aumento de dados (*Data Augmentation*), técnicas de reamostragem, riscos do acréscimo cego de instâncias (*Can adding data hurt?*), protocolos de particionamento e a prevenção exaustiva de *Data Leakage*.
* **Autores Chave:**
  * **Kapoor & Narayanan (2023):** A taxonomia canônica dos 8 tipos de *Data Leakage*, demonstrando a contaminação decorrente de pré-processamento compartilhado `[L1.2]`.
  * **Batista (2003):** Métodos de reamostragem inteligente (*SMOTE*, *Tomek Links*, *ENN*) e métricas robustas (ROC/AUC).
  * **Barros & Melo (2025):** Deformação analítica dos estimadores matemáticos $\beta$ em Regressão, distorções métricas no KNN e divisões espúrias em Árvores.
  * **Whang et al. (2022):** Métodos de aprendizado robusto perante ruído de atributos e rótulos imperfeitos (*noisy labels*).
  * **Singh (2023):** Evidências do fenômeno *Can adding data hurt?* e aumento de dados orientado a valor.
  * **Schleder & Fazzio (2021):** *Feature Engineering*, representação vetorial invariante e particionamento agrupado contra vazamento.

### **Capítulo 4 — Viés, Representatividade e Confiabilidade**
* **Objetivo da Seção:** Aprofundar as origens estruturais dos vieses nos dados de treinamento, correlações espúrias, variáveis *proxy*, perda de representatividade amostral, mudanças dinâmicas na distribuição (*Data Drift*) e a definição multidimensional de confiabilidade de sistemas inteligentes.
* **Autores Chave:**
  * **Ye et al. (2024/2025):** Taxonomia completa de Correlações Espúrias, *Shortcut Learning* e avaliação fora da distribuição (*Out-of-Distribution - OOD*).
  * **Whang et al. (2022):** Formalização de métricas matemáticas de justiça (*Fairness*) e mitigação pré-processamento.
  * **Rocha (2026):** *Data Drift*, *Covariate Shift* e métodos multivariados de detecção não supervisionada para manutenção da confiabilidade.
  * **Sculley et al. (2015):** *Feedback Loops* ocultos que amplificam vieses com o passar do tempo.
  * **Silva et al. (2026):** Dados históricos discriminatórios e variáveis *proxy* que burlam a exclusão de atributos protegidos.
  * **Rosa & Guasque (2024):** Ciclos de retroalimentação viciada e o estudo de caso paradigmático do algoritmo COMPAS.
  * **Borges & Faleiros Júnior (2023):** Parametrização do risco e conformidade técnica no ciclo de desenvolvimento.

### **Capítulo 5 — Análise Integrada da Literatura**
* **Objetivo da Seção:** Sintetizar as convergências, divergências e contribuições complementares do corpus bibliográfico completo (14 trabalhos), demonstrando que a acurácia, robustez, justiça e generalização do modelo são estritamente condicionadas pela disciplina da Engenharia de Dados.
* **Autores Chave:** Cruzamento comparativo entre as contribuições clássicas e nacionais (Batista, Barros & Melo, Rocha, Jesus et al., Silva et al., Rosa & Guasque, Borges & Faleiros) e o estado da arte internacional de Data-Centric AI (Whang et al., Jakubik et al., Sculley et al., Singh, Kapoor & Narayanan, Ye et al., Schleder & Fazzio).

### **Capítulo 6 — Considerações Finais**
* **Objetivo da Seção:** Responder formalmente ao problema de pesquisa, sintetizar as diretrizes e boas práticas de Engenharia de Dados para o desenvolvimento de sistemas de ML confiáveis (adotando frameworks como *Model Info Sheets* e *TFDV*) e apontar lacunas para pesquisas futuras.
* **Autores Chave:** Síntese propositiva integrando Jakubik et al. (2024), Whang et al. (2022), Sculley et al. (2015), Kapoor & Narayanan (2023) e Rocha (2026).

---

## 4. Estrutura dos Arquivos do Projeto

```
TCC/
│
├── PRÉ-PROJETO DE TRABALHO DE CONCLUSÃO DE CURSO.md
├── INDICE_DOS_TRABALHOS_ANALISADOS.md
│
├── anotacoes_artigos/
│   ├── 01_Barros_Melo_2025_Qualidade_Dados_Tabulares_ML.md
│   ├── 02_Batista_2003_Preprocessamento_Aprendizado_Supervisionado.md
│   ├── 03_Rocha_2026_Mitigating_Data_Drift_Continuous_Monitoring.md
│   ├── 04_Ye_et_al_2024_Clever_Hans_Spurious_Correlations.md
│   ├── 05_Jesus_et_al_2024_Terminologia_Qualidade_Dados.md
│   ├── 06_Silva_et_al_2026_IA_Vies_Genero_Recrutamento.md
│   ├── 07_Rosa_Guasque_2024_IA_Vieses_Algoritmicos_Racismo.md
│   ├── 08_Borges_Faleiros_2023_Vies_Racial_Responsabilidade_Civil.md
│   ├── 09_Schleder_Fazzio_2021_Machine_Learning_Ciencia_Dados.md
│   ├── 10_Whang_et_al_2022_Data_Collection_Quality_Challenges_DL.md
│   ├── 11_Jakubik_et_al_2024_Data_Centric_Artificial_Intelligence.md
│   ├── 12_Sculley_et_al_2015_Hidden_Technical_Debt_ML_Systems.md
│   ├── 13_Singh_2023_Systematic_Review_Data_Centric_AI_ML.md
│   └── 14_Kapoor_Narayanan_2023_Data_Leakage_Reproducibility_Crisis.md
│
├── fichas_academicas/
│   ├── INDICE_FICHAS_ACADEMICAS.md
│   ├── 01_Barros_Melo_2025_Qualidade_Dados_Tabulares_ML.md
│   ├── 02_Batista_2003_Preprocessamento_Aprendizado_Supervisionado.md
│   ├── 03_Rocha_2026_Mitigating_Data_Drift_Continuous_Monitoring.md
│   ├── 04_Ye_et_al_2024_Clever_Hans_Spurious_Correlations.md
│   ├── 05_Jesus_et_al_2024_Terminologia_Qualidade_Dados.md
│   ├── 06_Silva_et_al_2026_IA_Vies_Genero_Recrutamento.md
│   ├── 07_Rosa_Guasque_2024_IA_Vieses_Algoritmicos_Racismo.md
│   ├── 08_Borges_Faleiros_2023_Vies_Racial_Responsabilidade_Civil.md
│   ├── 09_Schleder_Fazzio_2021_Machine_Learning_Ciencia_Dados.md
│   ├── 10_Whang_et_al_2022_Data_Collection_Quality_Challenges_DL.md
│   ├── 11_Jakubik_et_al_2024_Data_Centric_Artificial_Intelligence.md
│   ├── 12_Sculley_et_al_2015_Hidden_Technical_Debt_ML_Systems.md
│   ├── 13_Singh_2023_Systematic_Review_Data_Centric_AI_ML.md
│   └── 14_Kapoor_Narayanan_2023_Data_Leakage_Reproducibility_Crisis.md
│
└── [Arquivos PDF originais do corpus...]
```
