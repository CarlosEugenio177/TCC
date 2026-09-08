# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 10:** Whang et al. (2022)  
**Arquivo Analisado:** `Data Collection and Quality Challenges in Deep Learning.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Data Collection and Quality Challenges in Deep Learning: A Data-Centric AI Perspective
* **Autores:** Steven Euijong Whang; Yuji Roh; Hwanjun Song; Jae-Gil Lee
* **Ano:** 2022 (Versão v3 revisada em 26 de dezembro de 2022)
* **Instituição/país:** Korea Advanced Institute of Science and Technology (KAIST) e Naver AI Lab, Coreia do Sul
* **Revista, congresso, repositório ou evento:** *arXiv:2112.06409v3 [cs.LG]* / Baseado nos tutoriais apresentados nas conferências internacionais *VLDB 2020* (International Conference on Very Large Data Bases) e *ACM SIGKDD 2021* (Knowledge Discovery and Data Mining)
* **Volume, número e páginas:** 37 páginas (artigo em formato survey/monografia)
* **DOI:** arXiv:2112.06409
* **URL:** https://arxiv.org/abs/2112.06409
* **Tipo de publicação:** Artigo de revisão sistemática e tutorial aprofundado (*Survey*)
* **Idioma:** Inglês
* **Tipo de pesquisa:** Revisão integrativa e taxonômica de literatura computacional, mapeamento conceitual de métodos e arquiteturas de Engenharia de Dados para Deep Learning.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A consolidação do paradigma do *Software 2.0* (onde modelos de machine learning substituem rotinas tradicionais de software codificadas manualmente) transferiu o gargalo de desenvolvimento do design do algoritmo para a coleta e qualidade dos dados. Na prática, bases de dados reais são frequentemente pequenas, incompletas, com anotações ruidosas, enviesadas ou sujeitas a ataques adversariais (*data poisoning*). O desafio reside na falta de uma taxonomia unificada que organize as soluções desenvolvidas pela comunidade de gerenciamento de dados (*Data Management*) e de aprendizado de máquina (*Machine Learning*).
* **Pergunta de pesquisa:** Quais são os métodos, ferramentas e taxonomias sistemáticas de Engenharia de Dados necessários para realizar a coleta, validação, limpeza e saneamento de conjuntos de dados para treinamento de modelos de aprendizado profundo, e de que forma algoritmos de aprendizado robusto e equitativo podem mitigar imperfeições residuais dos dados?
* **Objetivo principal:** Mapear e estruturar exaustivamente o panorama de pesquisas em Coleta de Dados (*Data Collection*) e Qualidade de Dados (*Data Quality*) sob a perspectiva do *Data-Centric AI*, estabelecendo uma ponte formal entre engenharia de software, gerenciamento de dados e aprendizado profundo.
* **Hipóteses ou questões específicas:** Práticas sistemáticas de validação e limpeza de dados (como *TFDV* e *HoloClean*) associadas a abordagens de treinamento robusto (tolerância a *noisy labels* e *missing features*) e desenviesamento (*fairness mitigation*) são fundamentais para assegurar a confiabilidade de modelos de aprendizado de máquina em ambientes de produção.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa-taxonômica, comparativa e analítica.
* **Tipo de estudo:** Levantamento bibliográfico sistemático e tutorial de alto nível metodológico.
* **Fonte dos dados:** Literatura científica indexada de primeira linha nas áreas de banco de dados (SIGMOD, VLDB, ICDE) e inteligência artificial/ML (NeurIPS, ICML, ICLR, KDD).
* **Estrutura de análise:** Os autores decompõem o ciclo de vida dos dados em quatro eixos macroestruturais:
  1. *Data Collection:* Aquisição (descoberta, aumento e geração) e rotulagem (supervisão fraca, crowdsourcing e rotulagem automática);
  2. *Data Validation, Cleaning, and Integration:* Detecção de desvios de esquema/distribuição, limpeza com restrições declarativas e integração multimodal;
  3. *Robust Model Training:* Adaptações algorítmicas para treinar modelos sob ruído de atributos, ausência de atributos e contaminação de rótulos;
  4. *Fair Model Training:* Formalização de métricas matemáticas de justiça e técnicas de desenviesamento (pré-processamento, in-processing e pós-processamento).
* **Critérios de avaliação:** Eficácia de restauração, consumo de recursos computacionais, dependência de supervisão humana e garantia de robustez estatística dos modelos finais.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: O Pré-processamento e Validação como Gargalo Principal do Ciclo de Vida de ML
* **O que foi encontrado:** Os autores destacam que entre 60% e 80% do esforço em projetos reais de aprendizado de máquina é absorvido pelas etapas de preparação, validação e saneamento dos dados. Com a evolução do Deep Learning, a engenharia de atributos manual diminuiu em favor da necessidade de dados limpos, representativos e em larga escala.
* **Evidência:** Levantamentos empíricos de indústria e relatórios de esteiras de ML corporativas (Google TFX, Meta, Naver).
* **Interpretação dos autores:** O paradigma *Software 2.0* exige que os dados sejam tratados com o mesmo rigor de controle de versão, testes automatizados e integração contínua conferidos ao código-fonte.
* **Grau de evidência:** **Direto** (consenso amplamente documentado em revisões empíricas).

### Resultado 2: Insuficiência da Limpeza Manual e Necessidade de Pipelines Declarativos
* **O que foi encontrado:** Métodos heurísticos e manuais de limpeza não escalam para grandes volumes, introduzindo novos vieses humanos. A validação declarativa (ex.: *TensorFlow Data Validation - TFDV*) e a limpeza probabilística baseada em restrições de integridade e correlação (ex.: *HoloClean*) preservam a geometria estatística necessária para o treinamento de modelos.
* **Evidência:** Análise comparativa de sistemas modernos de governança de dados na esteira de produção.
* **Interpretação dos autores:** A qualidade dos dados para ML não é uma limpeza estática pontual, mas uma propriedade mantida por pipelines automatizados de validação de esquemas e distribuições estatísticas.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Relação Indissociável entre Qualidade dos Dados, Robustez e Equidade (Fairness)
* **O que foi encontrado:** A presença de ruído concentrado assimetricamente em subpopulações ou a escassez de dados de grupos minoritários gera degradação catastrófica de desempenho específico, violando princípios de equidade (*Demographic Parity* e *Equalized Odds*). Os autores demonstram que mitigações aplicadas na camada de dados (pré-processamento e rebalanceamento) são as mais transparentes e desacopladas da arquitetura do algoritmo.
* **Evidência:** Revisão formal de benchmarks de fairness e modelos de perda adversariais.
* **Interpretação dos autores:** A equidade e a robustez algorítmica não podem ser alcançadas sem uma intervenção ativa de Engenharia de Dados sobre a representatividade da base.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* A comunidade de Inteligência Artificial precisa abraçar o *Data-Centric AI*, onde a melhoria contínua e sistemática da base de dados substitui a mera busca cega por arquiteturas neurais mais complexas.
* **Afirmações fortes:** "Sem bons dados, mesmo os melhores algoritmos de aprendizado de máquina não conseguem apresentar bom desempenho." O gerenciamento de dados é o alicerce indispensável para viabilizar sistemas de aprendizado confiáveis.
* **Afirmações condicionadas ao contexto:** Quando a limpeza completa dos dados é economicamente inviável, técnicas de aprendizado robusto e supervisão fraca (*weak supervision*) devem ser combinadas com pipelines de validação.
* **Hipóteses / Possibilidades:** Convergência futura definitiva entre bancos de dados autônomos e esteiras integradas de MLOps orientadas à qualidade.

---

# 6. CONCEITOS IMPORTANTES
* **Software 2.0:**
  * *Como define/utiliza:* Software cuja lógica operacional é codificada nos pesos de uma rede neural induzida por dados, em contraste com software tradicional (Software 1.0) codificado em instruções lógicas explícitas.
  * *Localização:* Seção 1 (Overview).
  * *Importância:* Fundamentação epistemológica da centralidade dos dados.
* **Data-Centric AI:**
  * *Como define/utiliza:* Prática disciplinada de aprimorar a acurácia e a robustez de sistemas de IA por meio da engenharia iterativa da qualidade, volume e consistência dos dados de entrada.
  * *Localização:* Seção 1 e Seção 6.
  * *Importância:* Paradigma norteador do estudo.
* **Data Validation (Validação de Dados):**
  * *Como define/utiliza:* Verificação automatizada de conformidade estatística e de esquema entre lotes de dados em tempo de ingestão (*schema drift* e anomalias).
  * *Localização:* Seção 3.1.
  * *Importância:* Operação central de Engenharia de Dados em MLOps.
* **HoloClean & ActiveClean:**
  * *Como define/utiliza:* Frameworks de limpeza de dados guiados por modelos probabilísticos e restrições de integridade que priorizam a correção de registros que mais afetam o gradiente do modelo.
  * *Localização:* Seção 3.2.
  * *Importância:* Ferramentas paradigmáticas de saneamento inteligente.
* **Fair Model Training (Treinamento Justo):**
  * *Como define/utiliza:* Formulação matemática para restringir predições desiguais entre grupos demográficos protegidos, atuando via pré-processamento nos dados, in-processing ou pós-processamento.
  * *Localização:* Seção 5.
  * *Importância:* Conexão entre qualidade de dados, viés e ética algorítmica.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* O escopo do artigo privilegia a visão de aprendizado profundo (*Deep Learning*), embora muitos dos princípios se apliquem a modelos clássicos.
* Algumas ferramentas de ponta discutidas ainda demandam alta complexidade computacional para implementação em ambientes industriais de tempo real.

### Limitações observáveis (Interpretação da análise)
* Por se tratar de um *survey* exaustivo, o trabalho não apresenta um experimento quantitativo empírico inédito unificado, estruturando-se como compilação taxonômica da literatura.

### Impacto das limitações
* Não enfraquece o trabalho; ao contrário, torna-o o referencial teórico ideal para catalogar práticas formais de Engenharia de Dados no TCC.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva crítica sobre limpeza excessiva:** Limpar cegamente dados considerados "outliers" sem compreensão do domínio pode eliminar justamente instâncias raras e informativas da classe minoritária, amplificando o viés do modelo.
* **Ressalva sobre rotulagem automática:** Técnicas fracamente supervisionadas (como *Snorkel*) aceleram o treinamento, mas podem propagar correlações espúrias caso as funções de rotulagem (*labeling functions*) contenham premissas incorretas.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta integralmente a cadeia completa: **Dados $ightarrow$ Qualidade dos dados $ightarrow$ Preparação/Tratamento $ightarrow$ Representatividade $ightarrow$ Viés $ightarrow$ Treinamento $ightarrow$ Generalização $ightarrow$ Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere aspectos regulatórios e legais de auditoria de dados, sem aprofundar a responsabilidade civil (que é coberta por Borges & Faleiros Júnior no corpus).

### 9.3 Qual parte ele não aborda?
* Não detalha peculiaridades do ordenamento jurídico ou das políticas de dados abertos brasileiras (tratadas por Jesus et al. e Rosa & Guasque).

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz. Reforça com o mais alto respaldo da literatura internacional que a engenharia e governança de dados são pré-requisitos mandatórios para sistemas de inteligência artificial confiáveis.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Afirmado como tese principal: sem dados de qualidade, modelos avançados colapsam. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Incompletude, ruído e anomalias alteram diretamente a convergência das redes. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Validação, limpeza probabilística e data augmentation definem o desempenho. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A sub-representação amostral é formalizada como causa de perda de equidade. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Dados históricos com viés contaminam previsões e violam demographic parity. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Rótulos ruidosos e ruídos de correlação levam a atalhos de memorização superficial. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Desvios entre distribuição de treino e teste (*distribution shift*) invalidam métricas. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Monitoramento de data drift e validação contínua de esquemas em produção. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade e robustez só são atingidas com saneamento em esteira contínua. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Apresenta a taxonomia completa de coleta, validação com TFDV e limpeza. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** **SIM** (trata exaustivamente de descoberta de dados, aumento sintético e fusão de dados multimodais).
* **Limpeza:** **SIM** (revisão de HoloClean, ActiveClean, reparo declarativo).
* **Transformação:** **SIM** (rotulagem fraca, transformações para invariant representations).
* **Qualidade:** **SIM** (dimensões formais de consistência, completude e ausência de ruído).
* **Validação / Preparação para Treinamento:** **SIM** (análise profunda de frameworks como TensorFlow Data Validation).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM — Trata explicitamente e com máxima profundidade**, posicionando o gerenciamento e a engenharia de dados como o cerne operacional do Data-Centric AI.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Data-centric AI is at the center of a fundamental shift in software engineering where machine learning becomes the new software, powered by big data and computing infrastructure. Here software engineering needs to be re-thought where data becomes a first-class citizen on par with code."*  
  * *Localização:* p. 1 (Abstract).  
  * *Tipo:* Premissa fundacional do paradigma.  
  * *Uso no TCC:* Introdução e Capítulo 2 para caracterizar o surgimento do Software 2.0.
* **Trecho 2:** *"One striking observation is that a significant portion of the machine learning process is spent on data preparation. Without good data, even the best machine learning algorithms cannot perform well."*  
  * *Localização:* p. 1 (Introduction).  
  * *Tipo:* Justificativa empírica.  
  * *Uso no TCC:* Justificativa do problema de pesquisa no Capítulo 1.
* **Trecho 3:** *"Data validation checks whether the data is suitable for training an ML model and is an essential step for building robust ML pipelines."*  
  * *Localização:* p. 11 (Section 3.1).  
  * *Tipo:* Definição operacional de Engenharia de Dados.  
  * *Uso no TCC:* Capítulo 2 para estruturar a seção de validação de dados em MLOps.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Polyzotis, N. et al. (2019):** *Data Validation for Machine Learning* (Fundamentação do TensorFlow Data Validation - TFDV).
* **Ratner, A. et al. (2017):** *Snorkel: Rapid Training Data Creation with Weak Supervision* (Supervisão fraca em pipelines de dados).
* **Rekatsinas, T. et al. (2017):** *HoloClean: Holistic Data Repair with Probabilistic Inference* (Limpeza probabilística de bases tabulares).
* **Hardt, M., Price, E., & Srebro, N. (2016):** *Equality of Opportunity in Supervised Learning* (Métricas matemáticas de justiça algorítmica).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL**
* **Justificativa:** É a publicação de referência mais rica em catalogação técnica de soluções de Engenharia de Dados para mitigação de anomalias em conjuntos de dados de treinamento.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Taxonomia de coleta, validação automatizada e limpeza declarativa.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Treinamento com dados imperfeitos e aumento de dados.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Métricas de fairness e mitigação de viés via pré-processamento.
* **Capítulo 5 (Análise Integrada da Literatura):** Conexão cruzada entre bancos de dados e inteligência artificial.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** WHANG, S. E.; ROH, Y.; SONG, H.; LEE, J.-G. Data Collection and Quality Challenges in Deep Learning: A Data-Centric AI Perspective. *arXiv preprint arXiv:2112.06409v3*, 2022. 37 p.
* **Problema:** Gargalos de escala, ruído, viés e validação no ciclo de dados para aprendizado profundo.
* **Objetivo:** Estabelecer uma taxonomia sistemática para coleta e qualidade de dados em Data-Centric AI.
* **Metodologia:** Levantamento e integração sistemática de literatura em Data Management e Deep Learning.
* **Principais resultados:** Estruturação das técnicas de aquisição, validação automatizada (TFDV), limpeza probabilística (HoloClean) e aprendizado robusto/justo.
* **Principais conceitos:** Data-Centric AI, Software 2.0, Data Validation, Data Cleaning, Fair Model Training.
* **Conclusões dos autores:** A confiabilidade de sistemas de aprendizado depende intrinsecamente da qualidade do pipeline de dados.
* **Limitações:** Foco primário em redes profundas e arquiteturas neurais complexas.
* **Contradições/ressalvas:** Limpezas cegas sem critério estatístico removem instâncias raras legítimas e amplificam vieses.
* **Contribuição para o TCC:** Prover o referencial taxonômico formal para todas as etapas de Engenharia de Dados do trabalho.
* **Capítulo provável:** Capítulos 2, 3 e 4.
* **Citação principal:** *"Without good data, even the best machine learning algorithms cannot perform well."*
* **Palavras-chave:** Engenharia de Dados; Data-Centric AI; Qualidade de Dados; Validação de Dados; Deep Learning.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 9.8 / 10 |
| Relevância para Engenharia de Dados | 10 / 10 |
| Relevância para Qualidade de Dados | 10 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 9.5 / 10 |
| Atualidade | 10 / 10 (Survey de 2022/2023) |
* **Avaliação global:** 9.9 / 10 — Obra de referência mundial emanada de conferências de topo (VLDB e KDD).

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É o survey técnico mais abrangente que conecta explicitamente a disciplina de Engenharia/Gerenciamento de Dados aos desafios de confiabilidade de modelos de aprendizado.
* **Função única:** Fornecer o mapa conceitual e instrumental para as etapas de validação e limpeza de dados.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A centralidade da etapa de preparação de dados no ciclo de ML e a eficácia de frameworks declarativos de validação estatística e mitigação de viés.
* **O que é interpretação:** A aplicação de suas conclusões para cenários específicos de dados públicos abertos da administração brasileira.
* **O que não podemos afirmar com base neste artigo:** Desempenho computacional específico em arquiteturas de hardware legadas ou ambientes sem infraestrutura em nuvem.
