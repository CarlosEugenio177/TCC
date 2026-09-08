# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 11:** Jakubik et al. (2024)  
**Arquivo Analisado:** `Data-Centric Artificial Intelligence.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Data-Centric Artificial Intelligence
* **Autores:** Johannes Jakubik; Michael Vössing; Niklas Kühl; Jannis Walk; Gerhard Satzger
* **Ano:** 2024 (Publicado online em 5 de março de 2024; publicação do fascículo: Agosto de 2024)
* **Instituição/país:** Karlsruhe Institute of Technology (KIT) e University of Bayreuth, Alemanha
* **Revista, congresso, repositório ou evento:** *Business & Information Systems Engineering (BISE)*
* **Volume, número e páginas:** Volume 66, Edição 4, pp. 507–515 (9 páginas)
* **DOI:** 10.1007/s12599-024-00857-8
* **URL:** https://doi.org/10.1007/s12599-024-00857-8
* **Tipo de publicação:** Artigo em periódico revisado por pares (*Catchword Article*)
* **Idioma:** Inglês
* **Tipo de pesquisa:** Artigo conceitual, analítico e taxonômico de fundamentação paradigmática.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** Ao longo das últimas décadas, a pesquisa acadêmica e a prática industrial em inteligência artificial concentraram quase toda a sua atenção em aprimorar modelos estatísticos e arquiteturas neurais (o paradigma *Model-Centric*). Essa abordagem pressupõe que os conjuntos de dados são insumos fixos e perfeitos, ignorando que anomalias, dados ruidosos e desvios de distribuição impõem barreiras intransponíveis de desempenho, gerando desperdício massivo de esforço de parametrização e custos computacionais.
* **Pergunta de pesquisa:** O que define rigorosamente o paradigma do *Data-Centric AI*, de que maneira ele se distingue formalmente da abordagem model-cêntrica e de outras disciplinas correlatas (como Engenharia de Dados, DQM e MLOps), e quais são as suas dimensões operacionais fundamentais?
* **Objetivo principal:** Apresentar uma sistematização conceitual para pesquisadores e profissionais de engenharia de software e sistemas de informação sobre o *Data-Centric AI*, fornecendo definições precisas, um framework de dimensões operacionais, um panorama de ferramentas e uma agenda de implicações estruturais.
* **Hipóteses ou questões específicas:** A transição do aperfeiçoamento centrado no algoritmo para a engenharia sistemática e contínua do dado viabiliza saltos de eficácia (acurácia e robustez) e de eficiência (redução de custos de treino e anotação) inalcançáveis pelo modelo estático.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa, conceitual, dedutiva e integrativa.
* **Tipo de estudo:** Ensaio teórico-estruturante (*Catchword*) em periódico de primeira linha.
* **Procedimento metodológico:** Mapeamento conceitual sistemático com base em literatura seminal de Ciência da Computação, Engenharia de Software e Gestão da Informação.
* **Estrutura de análise:**
  1. Contrastação dos paradigmas *Model-Centric* vs. *Data-Centric*;
  2. Dedução do Framework de 4 Dimensões (*Understanding*, *Preparation*, *Validation*, *Operations*);
  3. Delimitação epistemológica de fronteiras com conceitos vizinhos;
  4. Análise de implicações em múltiplos níveis organizacionais.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Inversão Metodológica da Engenharia de Sistemas Inteligentes
* **O que foi encontrado:** Os autores formulam analiticamente a inversão metodológica: no *Model-Centric AI*, o dado $D$ é uma constante e busca-se otimizar a hipótese $h \in \mathcal{H}$; no *Data-Centric AI*, adota-se um modelo padronizado e maduro $h_{base}$ e otimiza-se sistematicamente a matriz de dados $D$ (limpeza, rotulagem, representatividade).
* **Evidência:** Casos empíricos documentados no *Data-Centric AI Competition* (organizado por Andrew Ng), onde a melhoria estrita dos dados elevou métricas em mais de 16% com modelo fixo, superando meses de sintonia de hiperparâmetros.
* **Interpretação dos autores:** A qualidade dos dados constitui a verdadeira alavanca de engenharia para sistemas escaláveis.
* **Grau de evidência:** **Direto**.

### Resultado 2: O Framework Quadridimensional do Data-Centric AI
* **O que foi encontrado:** O trabalho com dados em IA não pode ser visto como um mero script pontual de limpeza, desdobrando-se em quatro dimensões contínuas:
  - *Data Understanding:* Diagnóstico estatístico aprofundado, identificação de subclasses raras e derivação de regras de integridade;
  - *Data Preparation:* Execução de saneamento de ruído, imputação e técnicas de aumento de dados (*augmentation*);
  - *Data Validation:* Verificação contra regras de negócio, contratos de dados (*data contracts*) e auditoria de viés;
  - *Data Operations (DataOps/MLOps):* Infraestrutura de esteira, versionamento e monitoramento contínuo em produção.
* **Evidência:** Síntese taxonômica e mapeamento de ferramentas industriais (*Great Expectations*, *Snorkel*, *Cleanlab*).
* **Interpretação dos autores:** A maturidade em IA exige a profissionalização da cadeia de dados em processos disciplinados.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Delimitação da Engenharia de Dados no Contexto de Machine Learning
* **O que foi encontrado:** O artigo traça a fronteira exata entre a Engenharia de Dados tradicional e o Data-Centric AI. A Engenharia de Dados clássica historicamente preocupou-se com infraestrutura de ingestão, pipeline ETL, integridade relacional e latência de entrega. O Data-Centric AI exige que a Engenharia de Dados incorpore propriedades indutivas: invariância estatística, cobertura distribucional e prevenção de correlações espúrias.
* **Evidência:** Análise ontológica das definições disciplinares.
* **Interpretação dos autores:** A Engenharia de Dados precisa evoluir para uma disciplina orientada a modelos de IA (*AI-oriented data engineering*).
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* A comunidade de tecnologia deve reconhecer que os maiores gargalos atuais da inteligência artificial não são a falta de arquiteturas de redes ou bibliotecas de aprendizado, mas sim a escassez de dados limpos, consistentes e eticamente curados.
* **Afirmações fortes:** "Apesar de uma longa história de pesquisas sobre dados, o impacto da qualidade e quantidade de dados em sistemas de IA ainda é frequentemente ignorado na pesquisa e na prática de IA."
* **Afirmações condicionadas ao contexto:** A transição para o Data-Centric AI exige mudanças culturais profundas nas organizações, que historicamente valorizam mais o desenvolvimento de novos algoritmos do que o trabalho contínuo de curadoria de dados (*data work*).
* **Hipóteses / Possibilidades:** Emergência de mercados de dados confiáveis e ferramentas automatizadas de refatoração contínua de datasets.

---

# 6. CONCEITOS IMPORTANTES
* **Data-Centric AI:**
  * *Como define/utiliza:* Prática sistemática de engenharia e aprimoramento de conjuntos de dados em escala para maximizar a eficácia e a eficiência de sistemas de IA.
  * *Localização:* Seções 1 e 2.
  * *Importância:* Conceito-mestre do artigo.
* **Model-Centric AI:**
  * *Como define/utiliza:* Paradigma tradicional focado em otimizar a arquitetura e hiperparâmetros de modelos matemáticos mantendo fixo o conjunto de dados.
  * *Localização:* Seção 2.
  * *Importância:* Termo de contraposição dialética.
* **Data Work (Trabalho com Dados):**
  * *Como define/utiliza:* O esforço humano e computacional despendido na coleta, etiquetagem, limpeza, validação e governança dos dados.
  * *Localização:* Seções 1 e 5.
  * *Importância:* Valorização do papel da engenharia de dados.
* **Data Understanding:**
  * *Como define/utiliza:* Análise aprofundada da estrutura e do perfil estatístico dos dados antes da fase de treinamento indutivo.
  * *Localização:* Seção 3.
  * *Importância:* Primeira dimensão operacional do framework.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* O artigo foca na sistematização conceitual para o campo de Engenharia de Sistemas de Informação (*BISE*), sem conduzir experimentos laboratoriais inéditos de benchmark de código.

### Limitações observáveis (Interpretação da análise)
* O texto adota uma perspectiva focada em governança e gerenciamento, demandando complementação por estudos algorítmicos empíricos (como os de Barros & Melo, Batista e Whang et al.).

### Impacto das limitações
* Perfeitamente alinhado com a sua proposta de ser um artigo estruturante (*Catchword*), cuja força reside na solidez conceitual e na clareza taxonômica.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva sobre o custo do trabalho com dados:** A abordagem data-cêntrica requer investimento financeiro e organizacional significativo em ferramentas e pessoal especializado em qualidade de dados, o que muitas empresas tentam contornar mediante soluções algorítmicas mágicas.
* **Alerta sobre silos organizacionais:** Sem uma integração estreita entre os engenheiros de dados que constroem os pipelines e os cientistas de dados que analisam os modelos, os ganhos do DCAI não se materializam.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com máxima autoridade o início e o fim da narrativa: **Dados $ightarrow$ Qualidade dos dados $ightarrow$ Preparação/Tratamento** e o objetivo final de **Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere as implicações de viés e justiça algorítmica, mas delega o detalhamento matemático a trabalhos especializados.

### 9.3 Qual parte ele não aborda?
* Não aborda equações analíticas de convergência paramétrica em OLS/MLE ou distorções de árvores de decisão (tratadas por Barros & Melo).

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; fornece a moldura teórica definitiva para fundamentar que o problema de pesquisa do TCC está alinhado à principal vanguarda paradigmática da ciência da computação contemporânea.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Tese central do trabalho: a qualidade dos dados dita a fronteira de eficácia da IA. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Inconsistências de anotação e ruído degradam os modelos mesmo sob hiperajuste. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | A preparação iterativa e sistemática é o motor central do framework DCAI. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A amostragem estratégica é apontada como requisito de cobertura estatística. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | A validação de dados inclui a detecção de assimetrias discriminatórias na base. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Discute o risco de modelos aprenderem correlações de ruído em dados não saneados. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Enfatiza que testes com dados contaminados mascaram falhas de generalização. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | A dimensão de Data Operations foca diretamente na sustentabilidade perante drift. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade do sistema inteligente é o benefício primário da abordagem DCAI. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Apresenta a Engenharia de Dados orientada a IA como o método de execução do DCAI. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** **SIM** (integra o ciclo de vida do dado).
* **Limpeza:** **SIM** (núcleo da dimensão Data Preparation).
* **Transformação:** **SIM** (estruturação, aumento sintético de dados e rotulagem disciplinada).
* **Qualidade:** **SIM** (conceituação detalhada das dimensões qualitativas).
* **Validação / Preparação para Treinamento:** **SIM** (núcleo da dimensão Data Validation).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM — Trata explicitamente**, redefinindo o escopo da disciplina para além do transporte e armazenamento, elevando-a à condição de arquiteta da inteligência dos modelos.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Data-centric artificial intelligence (data-centric AI) represents an emerging paradigm that emphasizes the importance of enhancing data systematically and at scale to build effective and efficient AI-based systems."*  
  * *Localização:* p. 507 (Abstract).  
  * *Tipo:* Definição seminal.  
  * *Uso no TCC:* Introdução do TCC para definir formalmente o paradigma.
* **Trecho 2:** *"In model-centric AI, researchers and practitioners keep the data constant and iteratively modify code or hyperparameters to improve the performance of an AI-based system. In data-centric AI, this process is flipped: researchers and practitioners keep the code of the ML model relatively fixed and iteratively engineer the data."*  
  * *Localização:* p. 508 (Section 2).  
  * *Tipo:* Contraste teórico operacional.  
  * *Uso no TCC:* Capítulo 1 e Capítulo 2 para estruturar a virada conceitual.
* **Trecho 3:** *"High-quality data is essential for AI systems to generate reliable outputs and avoid erroneous decisions. Ensuring high data quality is thus a key tenet of data-centric AI."*  
  * *Localização:* p. 509 (Section 3).  
  * *Tipo:* Conexão entre qualidade e confiabilidade.  
  * *Uso no TCC:* Capítulo 2 para associar Engenharia de Dados à confiabilidade.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Ng, A. et al. (2021):** *Data-Centric AI Competition* (Movimento fundador da iniciativa).
* **Sambasivan, N. et al. (2021):** *“Everyone wants to do the model work, not the data work”: Data Cascades in High-Stakes AI* (Estudo etnográfico sobre os desastres causados pela negligência com dados).
* **Legner, C. et al. (2020):** *Data Management and Information Systems* (Fundamentos clássicos de gestão da informação).
* **Polyzotis, N. et al. (2018):** *Data Management Challenges in Production Machine Learning* (Desafios industriais de dados).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL / CONCEITUAL**
* **Justificativa:** É a publicação formal que confere legitimidade e atualidade conceitual ao TCC, estabelecendo as bases teóricas para discutir o papel da Engenharia de Dados sob a perspectiva do *Data-Centric AI*.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** Contextualização do surgimento do paradigma Data-Centric AI e formulação do problema.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** O framework quadridimensional e a evolução da Engenharia de Dados orientada a IA.
* **Capítulo 6 (Considerações Finais):** Diretrizes estratégicas para o desenvolvimento e governança de sistemas de ML centrados em dados.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** JAKUBIK, J.; VÖSSING, M.; KÜHL, N.; WALK, J.; SATZGER, G. Data-Centric Artificial Intelligence. *Business & Information Systems Engineering*, v. 66, n. 4, p. 507–515, 2024.
* **Problema:** Predominância limitante da abordagem centrada no modelo em detrimento da engenharia sistemática de dados.
* **Objetivo:** Formalizar o conceito de Data-Centric AI e fornecer framework dimensional para engenharia e governança de dados em IA.
* **Metodologia:** Análise analítico-conceitual e revisão integrativa multidisciplinar.
* **Principais resultados:** Estruturação do framework com 4 dimensões (*Understanding*, *Preparation*, *Validation*, *Operations*); demonstração dos ganhos de eficácia e eficiência.
* **Principais conceitos:** Data-Centric AI, Model-Centric AI, Data Work, Framework Dimensional de DCAI.
* **Conclusões dos autores:** A qualidade dos dados é o determinante primário da confiabilidade em IA; as organizações devem priorizar o aprimoramento disciplinado da base.
* **Limitações:** Estudo teórico e conceitual, sem implementação experimental empírica direta.
* **Contradições/ressalvas:** A transição para DCAI exige investimentos organizacionais contínuos e superação da cultura que supervaloriza o código de modelos.
* **Contribuição para o TCC:** Prover o aparato conceitual e paradigmático mais moderno para o trabalho.
* **Capítulo provável:** Capítulos 1, 2 e 6.
* **Citação principal:** *"In data-centric AI, researchers and practitioners keep the code of the ML model relatively fixed and iteratively engineer the data."*
* **Palavras-chave:** Data-Centric AI; Engenharia de Dados; Qualidade de Dados; Paradigmas de Inteligência Artificial; Governança de Dados.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 9.5 / 10 |
| Relevância para Engenharia de Dados | 10 / 10 |
| Relevância para Qualidade de Dados | 10 / 10 |
| Relevância para Machine Learning | 9.5 / 10 |
| Relevância para Viés/Generalização | 9.0 / 10 |
| Atualidade | 10 / 10 (2024 - Estado da arte) |
* **Avaliação global:** 9.7 / 10 — Artigo moderno, conciso e com elevado rigor de sistematização epistemológica.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É a publicação formal que batiza e teoriza o movimento recente de convergência entre Engenharia de Dados e Inteligência Artificial.
* **Função única:** Fornecer a base conceitual para justificar academicamente por que o TCC estuda a influência dos dados em vez da mecânica isolada dos modelos.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A definição analítica de DCAI, a superioridade de ganhos via refinamento de dados em múltiplos domínios e a divisão em 4 dimensões operacionais.
* **O que é interpretação:** A inferência de que falhas de conformidade nessas etapas desencadeiam diretamente a responsabilidade civil preconizada no ordenamento brasileiro.
* **O que não podemos afirmar com base neste artigo:** Fórmulas analíticas exatas de funções de perda para algoritmos particulares.
