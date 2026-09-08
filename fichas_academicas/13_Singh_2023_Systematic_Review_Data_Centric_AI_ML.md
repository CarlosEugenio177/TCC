# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 13:** Singh (2023)  
**Arquivo Analisado:** `Systematic review of data-centric approaches in artificial intelligence and machine learning.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Systematic review of data-centric approaches in artificial intelligence and machine learning
* **Autor:** Prerna Singh
* **Ano:** 2023 (Recebido em 31/01/2023; Aceito em 15/06/2023; Publicado online em 22/06/2023; Volume de Setembro de 2023)
* **Instituição/país:** Wellington, Nova Zelândia
* **Revista, congresso, repositório ou evento:** *Data Science and Management* (Periódico internacional indexado pela Elsevier / KeAi)
* **Volume, número e páginas:** Volume 6, Edição 3, pp. 144–157 (14 páginas)
* **DOI:** 10.1016/j.dsm.2023.06.001
* **URL:** https://doi.org/10.1016/j.dsm.2023.06.001
* **Tipo de publicação:** Artigo de revisão sistemática da literatura (*Review Article*)
* **Idioma:** Inglês
* **Tipo de pesquisa:** Revisão sistemática da literatura (RSL), análise comparativa e síntese qualitativo-quantitativa de evidências computacionais.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que o autor investiga:** A literatura em IA e Machine Learning tem focado desproporcionalmente no desenvolvimento de algoritmos inteligentes de ponta (*State-of-the-Art*). Todavia, abordagens centradas em modelos encontram um limite rígido diante da escassez de dados de alta qualidade. Embora profissionais implementem heurísticas de manipulação e saneamento de dados na prática, falta uma sistematização documentada e com diretrizes claras que consolide quais intervenções de dados produzem melhorias reais na acurácia, generalização e sustentabilidade dos sistemas.
* **Pergunta de pesquisa:** Quais são os principais métodos, ferramentas e práticas associados à abordagem data-cêntrica em IA documentados na literatura científica, como o acréscimo indiscriminado de dados afeta o aprendizado e de que maneira o débito técnico se manifesta nos dados em produção?
* **Objetivo principal:** Fornecer uma revisão sistemática e integrada das abordagens *Data-Centric AI* (DCAI) em IA e ML, categorizando as principais técnicas de pré-processamento, avaliação de qualidade, aumento de dados, reparo probabilístico e MLOps.
* **Hipóteses ou questões específicas:** A transição do paradigma de *Big Data* (foco em volume bruto) para *Good Data* (foco em qualidade, consistência e representatividade) é condição indispensável para aprimorar o desempenho preditivo e reduzir o débito técnico em sistemas de aprendizado de máquina.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa e quantitativa-bibliométrica, estruturada segundo diretrizes formais de Revisão Sistemática da Literatura.
* **Tipo de estudo:** Revisão sistemática abrangente.
* **Bases e critérios de busca:** Consulta às principais bases acadêmicas internacionais (IEEE Xplore, ACM DL, ScienceDirect, SpringerLink, ArXiv e Google Scholar) utilizando descritores booleanos combinando *data-centric*, *machine learning*, *data quality*, *data preprocessing*, *technical debt* e *MLOps*.
* **Procedimento de seleção:** Triagem de títulos, resumos e textos integrais, excluindo artigos puramente algorítmicos que não envolvessem manipulação, avaliação ou governança qualitativa de dados.
* **Categorização temática:** Sistematização em 6 eixos de análise:
  1. *Big Data Quality Assessment* e a transição para *Good Data*;
  2. Técnicas de Pré-processamento (coleta, rotulagem, aumento e *feature engineering*);
  3. Transfer Learning e Semi-supervised Learning centrados em dados;
  4. MLOps e Rastreabilidade (*experiment tracking*);
  5. Investigação do impacto deletério da adição de dados ruidosos (*Can adding data hurt?*);
  6. Restauração e reparo de bases de dados (com foco no framework *HoloClean*) e débito técnico em dados.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Transição Epistemológica de Big Data para Good Data
* **O que foi encontrado:** A revisão demonstra que a corrida por volumes astronômicos de dados sem controle de qualidade tornou-se contraproducente. O conceito de *Good Data* prioriza precisão de anotação, integridade, relevância contextual e cobertura representativa de classes. Estudos revisados revelam que datasets compactos e rigorosamente curados geram modelos com menor variância de predição e maior generalização em ambientes desconhecidos (*out-of-distribution*).
* **Evidência:** Levantamento comparativo de múltiplos experimentos na literatura de processamento de linguagem e visão computacional.
* **Interpretação da autora:** A qualidade das anotações e a consistência das features superam o ganho marginal de volume de dados brutos.
* **Grau de evidência:** **Direto** (síntese sistemática de estudos convergentes).

### Resultado 2: A Evidência de que "Adicionar Dados Pode Prejudicar o Modelo" (*Can Adding Data Hurt?*)
* **O que foi encontrado:** A autora sistematiza artigos que comprovam experimentalmente que a ingestão cega de mais instâncias de treino degrada o desempenho preditivo dos algoritmos. Isso ocorre quando novos dados trazem desvios não monitorados de distribuição (*covariate shift*), introduzem rótulos contraditórios gerados por múltiplos anotadores não calibrados ou diluem a densidade da classe minoritária.
* **Evidência:** Compilação de casos empíricos onde a acurácia global e a revocação caíram após a inclusão desordenada de instâncias adicionais.
* **Interpretação da autora:** A curadoria e a filtragem seletiva de dados são tão ou mais importantes do que a coleta massiva.
* **Grau de evidência:** **Direto**.

### Resultado 3: O Papel dos Sistemas Probabilísticos de Reparo de Dados (HoloClean)
* **O que foi encontrado:** Métodos ingênuos de pré-processamento (eliminação casuística de registros ou imputação determinística pela média/mediana) introduzem viés sistemático. A revisão documenta o sucesso de ferramentas como o *HoloClean*, que modela o reparo de dados como inferência probabilística condicionada a regras de negação (*denial constraints*), aprendizado semi-supervisionado e correlações estatísticas, restabelecendo a fidelidade sem deformar as fronteiras de decisão.
* **Evidência:** Benchmarks revisados de restauração tabular e preservação de precisão preditiva.
* **Interpretação da autora:** O saneamento de bases de ML deve ser conduzido por pipelines analíticos inteligentes de Engenharia de Dados.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DA AUTORA
* O avanço da inteligência artificial depende diretamente do abandono da ilusão model-cêntrica em favor de uma disciplina científica e documentada de *Data-Centric AI*.
* **Afirmações fortes:** "Abordagens centradas no modelo estão limitadas pela ausência de dados de alta qualidade." A mera adição de volume bruto de dados sem governança atua ativamente como fonte de ruído e degradação preditiva.
* **Afirmações condicionadas ao contexto:** O uso de técnicas semi-supervisionadas e aumento sintético de dados exige monitoramento rigoroso para não gerar correlações espúrias artificiais.
* **Hipóteses / Possibilidades:** Consolidação futura de esteiras industriais de MLOps que integrem verificação de integridade estatística, linhagem e versionamento de dados de forma totalmente automatizada.

---

# 6. CONCEITOS IMPORTANTES
* **Good Data:**
  * *Como define/utiliza:* Dados relevantes, representativos, precisamente rotulados, consistentes e livres de ruído nocivo, dimensionados com foco na utilidade indutiva para o modelo.
  * *Localização:* Seção 4.1.
  * *Importância:* Contraponto direto ao mito do Big Data desordenado.
* **Can Adding Data Hurt?:**
  * *Como define/utiliza:* Fenômeno documentado em que a incorporação de novos dados a um conjunto de treinamento resulta na queda de acurácia, aumento do erro de generalização ou reforço de vieses indesejados.
  * *Localização:* Seção 4.7.
  * *Importância:* Tese crítica fundamental para o TCC.
* **HoloClean:**
  * *Como define/utiliza:* Sistema declarativo que unifica restrições de integridade lógicas e modelos estatísticos para detecção e reparo probabilístico de erros em dados tabulares.
  * *Localização:* Seção 4.8.
  * *Importância:* Referência de ponta para técnicas de limpeza de dados em Engenharia de Dados.
* **Data-Centric Technical Debt:**
  * *Como define/utiliza:* A manifestação de débitos técnicos silenciosos originados em falhas de arquitetura de dados, ausência de contratos de dados em produção e falta de rastreamento entre versão do dado e versão do modelo.
  * *Localização:* Seção 4.9.
  * *Importância:* Integração direta com a tese de Sculley et al. (2015).

---

# 7. LIMITAÇÕES

### Limitações declaradas pela autora
* A literatura em DCAI ainda é dispersa e carece de padronização terminológica formal em alguns subdomínios.
* A avaliação empírica de ferramentas como HoloClean pode variar dependendo da complexidade das regras de negócio do domínio analisado.

### Limitações observáveis (Interpretação da análise)
* A revisão abrange um leque muito amplo de tópicos (desde semi-supervised learning até MLOps), o que impede o aprofundamento exaustivo nas formulações matemáticas de cada técnica particular.

### Impacto das limitações
* Não compromete a utilidade do estudo; sua grande força reside precisamente na visão panorâmica e integradora que conecta a Engenharia de Dados, o reparo de bases e a qualidade dos modelos.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Resultado negativo compilado:** Aumentar o tamanho do dataset duplicando instâncias ou gerando dados sintéticos descalibrados reduz o erro aparente no treino, mas eleva o erro real em ambiente de validação independente.
* **Ressalva crítica sobre pré-processamento manual:** Transformações artesanais de dados sem rastreamento em ferramentas de MLOps inviabilizam a reprodutibilidade científica e criam dependências ocultas frágeis.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta integralmente: **Dados $\rightarrow$ Qualidade dos dados $\rightarrow$ Preparação/Tratamento $\rightarrow$ Representatividade $\rightarrow$ Treinamento $\rightarrow$ Generalização $\rightarrow$ Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere os impactos sociais de viés e fairness, concentrando o foco na acurácia técnica, generalização e governança de software.

### 9.3 Qual parte ele não aborda?
* Não trata da regulamentação jurídica de proteção de dados ou responsabilização civil por danos algorítmicos.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz. Enriquece e fortalece a narrativa ao fornecer comprovações sistemáticas de que qualidade supera quantidade bruta e que técnicas de Engenharia de Dados são indispensáveis para evitar falhas silenciosas.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Tese comprovada: o desempenho do algoritmo é estritamente limitado pela qualidade dos dados. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Inconsistências, ruído e assimetria reduzem F1-score e acurácia. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Pré-processamento, aumento e reparo (HoloClean) ditam a convergência. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A perda de representatividade amostral deteriora a robustez preditiva. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | A adição de dados enviesados introduz distorções sistemáticas no modelo. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Rótulos ruidosos e features não validadas levam a atalhos e padrões espúrios. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Desvios distributivos invalidam avaliações estáticas de laboratório. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Trata de data drift e MLOps contínuo para sustentar a qualidade temporal. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade é abordada como ausência de débito técnico em dados. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Apresenta a caixa de ferramentas da Engenharia de Dados como a resposta prática ao DCAI. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** **SIM** (avaliação de métodos de ingestão e consolidação de Big Data).
* **Limpeza:** **SIM** (análise aprofundada de ferramentas declarativas como HoloClean).
* **Transformação:** **SIM** (revisão de normalização, feature engineering e aumento de dados).
* **Qualidade:** **SIM** (análise das dimensões qualitativas sob o prisma do Good Data).
* **Validação / Preparação para Treinamento:** **SIM** (esteiras integradas de MLOps e rastreamento).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM — Trata explicitamente**, integrando a Engenharia de Dados como a disciplina executora do Data-Centric AI em todo o ciclo de vida do modelo.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Model-centric approaches are limited by the absence of high-quality data. Data-centric AI is an emerging approach for solving machine learning (ML) problems. It is a collection of various data manipulation techniques that allow ML practitioners to systematically improve the quality of the data used in an ML pipeline."*  
  * *Localização:* p. 144 (Abstract).  
  * *Tipo:* Resumo da virada de paradigma.  
  * *Uso no TCC:* Introdução e Capítulo 2 para caracterizar o Data-Centric AI.
* **Trecho 2:** *"The transition from big data to good data signifies that rather than merely accumulating vast quantities of data, the focus should be on acquiring relevant, high-quality, and representative data."*  
  * *Localização:* p. 146 (Section 4.1).  
  * *Tipo:* Síntese conceitual Big Data vs. Good Data.  
  * *Uso no TCC:* Capítulo 2 para estruturar a discussão de dimensões de qualidade de dados.
* **Trecho 3:** *"Adding more data can inadvertently introduce noise, bias, or irrelevant information, leading to degraded model performance."*  
  * *Localização:* p. 152 (Section 4.7).  
  * *Tipo:* Alerta técnico fundamental.  
  * *Uso no TCC:* Capítulo 3 e Capítulo 4 para fundamentar a falácia do volume bruto sem curadoria.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Sculley, D. et al. (2015):** *Hidden Technical Debt in Machine Learning Systems* (Base da discussão de débito técnico em dados).
* **Rekatsinas, T. et al. (2017):** *HoloClean: Holistic Data Repair with Probabilistic Inference* (Referencial de limpeza probabilística).
* **Sambasivan, N. et al. (2021):** *Data Cascades in High-Stakes AI* (Evidência etnográfica do impacto negativo de dados precários).
* **Kreuzberger, D. et al. (2023):** *Machine Learning Operations (MLOps): Overview, Definition, and Architecture* (Arquiteturas contemporâneas de MLOps).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL / INTEGRATIVO**
* **Justificativa:** É a revisão sistemática contemporânea que conecta a literatura empírica internacional recente sobre as práticas operacionais de Engenharia de Dados voltadas a Machine Learning.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Big Data vs. Good Data e ferramentas probabilísticas de reparo (HoloClean).
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** O problema de \"Can adding data hurt?\" e técnicas de aumento de dados.
* **Capítulo 5 (Análise Integrada da Literatura):** Matriz comparativa entre abordagens nacionais e o estado da arte do Data-Centric AI.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** SINGH, P. Systematic review of data-centric approaches in artificial intelligence and machine learning. *Data Science and Management*, v. 6, n. 3, p. 144–157, 2023.
* **Problema:** Limitação das abordagens centradas no modelo pela carência de dados de qualidade e fragmentação das práticas de engenharia de dados.
* **Objetivo:** Fornecer uma revisão sistemática da literatura sobre as práticas e ferramentas de Data-Centric AI.
* **Metodologia:** Revisão Sistemática da Literatura (RSL) integrando múltiplos repositórios acadêmicos internacionais.
* **Principais resultados:** Sistematização de 6 eixos de DCAI, consolidação do paradigma Good Data e comprovação dos riscos da adição indiscriminada de dados.
* **Principais conceitos:** Data-Centric AI, Good Data, Can Adding Data Hurt?, HoloClean, MLOps, Débito Técnico em Dados.
* **Conclusões dos autores:** A curadoria e a governança de qualidade de dados superam o mero volume bruto; pipelines formais de Engenharia de Dados são indispensáveis.
* **Limitações:** Panorama amplo com menor profundidade nas derivações matemáticas individuais.
* **Contradições/ressalvas:** Ingerir novos dados sem controle estrito pode reduzir o F1-score e amplificar correlações espúrias.
* **Contribuição para o TCC:** Prover a síntese de revisão sistemática mais recente e alinhada ao escopo do trabalho.
* **Capítulo provável:** Capítulos 2, 3 e 5.
* **Citação principal:** *"Model-centric approaches are limited by the absence of high-quality data."*
* **Palavras-chave:** Data-Centric AI; Revisão Sistemática; Good Data; Pré-processamento de Dados; MLOps; Qualidade de Dados.

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
| Atualidade | 10 / 10 (Publicado no segundo semestre de 2023) |
* **Avaliação global:** 9.7 / 10 — Revisão sistemática de excelência, ideal para compor a análise integrada da literatura no TCC.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É uma revisão sistemática recente que valida e corrobora a tese central do TCC sobre a precedência da qualidade dos dados em relação ao modelo.
* **Função única:** Servir como sustentação de literatura secundária que sintetiza múltiplos experimentos empíricos de Data-Centric AI.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A síntese dos 6 eixos temáticos de DCAI, o fenômeno de perda de performance por adição descontrolada de dados e a eficácia de reparos probabilísticos com HoloClean.
* **O que é interpretação:** A extrapolação direta de suas conclusões para demonstrar o impacto de falhas de governança em órgãos governamentais específicos.
* **O que não podemos afirmar com base neste artigo:** A supremacia absoluta de uma ferramenta proprietária específica sobre todas as outras em qualquer cenário industrial imaginável.
