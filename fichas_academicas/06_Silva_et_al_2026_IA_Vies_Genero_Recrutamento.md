# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 06:** Silva et al. (2026)  
**Arquivo Analisado:** `Artigo+7+-+Natan+final.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** INTELIGÊNCIA ARTIFICIAL E DESIGUALDADE DE GÊNERO ENTRE HOMENS E MULHERES: UMA ANÁLISE DOS VIESES EM PROCESSOS SELETIVOS DE CONTRATAÇÃO
* **Autores:** Flávia Helloysa Fontes Silva; Natanael Vítor Sobral; Daniela Eugênia Moura de Albuquerque; Leilah Santiago Bufrem; Fábio Mascarenhas e Silva
* **Ano:** 2026 (Jan./Abr. 2026)
* **Instituição/país:** Universidade Federal de Pernambuco (UFPE) e Universidade Federal da Bahia (UFBA), Brasil.
* **Revista, congresso, repositório ou evento:** *Perspectivas em Gestão & Conhecimento*, João Pessoa, v. 16, n. 1, p. 138-154.
* **Volume, número e páginas:** Volume 16, Número 1, p. 138-154 (17 páginas).
* **DOI:** `10.22478/ufpb.2236-417X.2026v16n1.74614` (ISSN: 2236-417X)
* **URL:** `http://periodicos.ufpb.br/ojs2/index.php/pgc`
* **Tipo de publicação:** Artigo científico em periódico (Relato de Pesquisa).
* **Idioma:** Português
* **Tipo de pesquisa:** Revisão integrativa da literatura com auxílio de plataforma de síntese de evidências científicas por IA (Consensus AI).

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A reprodução, perpetuação e amplificação de disparidades históricas de gênero contra mulheres em sistemas automatizados de inteligência artificial empregados em recrutamento e seleção de pessoas, provocadas pelo uso de bases de dados de treinamento que incorporam preconceitos e desequilíbrios históricos do mercado de trabalho.
* **Pergunta de pesquisa:** Quais são as evidências científicas acerca dos vieses de tratamento entre homens e mulheres produzidos por sistemas de IA em processos seletivos e de que forma os dados históricos de treinamento e as variáveis *proxy* determinam esses resultados discriminatórios?
* **Objetivo principal:** Analisar os vieses de gênero produzidos por sistemas de inteligência artificial em processos seletivos de contratação, identificando os fatores técnicos e os padrões de dados associados.
* **Hipóteses ou questões específicas:** A IA aplicada em RH tende a replicar os vieses de gênero presentes nos dados históricos; a simples exclusão do atributo "sexo/gênero" não elimina a discriminação algorítmica devido à presença de variáveis correlacionadas (*proxies*) no vocabulário dos currículos.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa e integrativa.
* **Tipo de estudo:** Revisão integrativa da literatura com busca mediada por IA.
* **Fonte dos dados:** Plataforma Consensus AI integrada a bases de dados científicas internacionais (Semantic Scholar, Scopus, Web of Science).
* **População/amostra:** Artigos científicos empíricos e teóricos internacionais focados em vieses de gênero em sistemas de seleção algorítmica.
* **Período analisado:** Sem delimitação temporal prévia, priorizando estudos recentes (2018–2025).
* **Métodos de coleta:** Consulta estruturada na plataforma Consensus AI utilizando perguntas de pesquisa em linguagem natural e filtros temáticos.
* **Métodos de análise:** Análise de conteúdo temática, categorização quantitativa de convergência percentual entre estudos e síntese descritiva de casos práticos.
* **Modelos/algoritmos analisados:** Sistemas de processamento de linguagem natural (NLP), modelos de triagem curricular por aprendizado supervisionado e sistemas de escore de candidatos.
* **Métricas:** Taxa de concordância de viés nos estudos (71,43%), frequência de discriminação em ranqueamentos e disparidade de taxas de aprovação.
* **Procedimentos experimentais:** Síntese e cruzamento das evidências de múltiplos estudos independentes.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: Confirmação Sistemática de Viés em 71,43% dos Estudos
* **O que foi encontrado:** 5 dos 7 estudos centrais selecionados (71,43%) comprovaram empiricamente que modelos de IA reproduzem padrões discriminatórios contra mulheres; apenas 2 estudos (28,57%) indicaram que sistemas bem calibrados podem reduzir disparidades em relação a avaliadores humanos.
* **Evidência:** Quadro comparativo de síntese dos artigos recuperados via Consensus AI.
* **Interpretação dos autores:** A discriminação algorítmica não é um evento isolado, mas uma tendência estrutural quando modelos são treinados com dados históricos sem auditoria prévia.
* **Grau de evidência:** **Direto** (meta-síntese de evidências empíricas).

### Resultado 2: O Mecanismo das Variáveis Proxy em Dados Textuais
* **O que foi encontrado:** Modelos de NLP aprendem a penalizar currículos femininos através de palavras associadas indiretamente ao gênero (ex.: nomes de clubes, esportes, instituições de ensino voltadas para mulheres), tornando ineficaz a simples remoção da coluna "gênero" da base de dados.
* **Evidência:** Documentação do caso do algoritmo de recrutamento da Amazon e estudos de *word embeddings* enviesados.
* **Interpretação dos autores:** O pré-processamento superficial não impede a discriminação; a Engenharia de Dados precisa de métodos para expurgar correlações latentes.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Falta de Diversidade nos Dados Históricos de Treinamento
* **O que foi encontrado:** As bases históricas de empresas de tecnologia eram compostas predominantemente por perfis masculinos contratados no passado; o algoritmo aprendeu estatisticamente que a característica "masculino" era um preditor de sucesso profissional.
* **Evidência:** Análise causal dos dados de treinamento do caso Amazon.
* **Interpretação dos autores:** A base de treino viciada atua como um espelho retrovisor que cristaliza desigualdades do passado.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* Os autores concluem que a inteligência artificial, longe de ser inerentemente neutra, opera como uma lente de aumento das distorções presentes nos dados históricos de treinamento.
* **Afirmações fortes:** Os vieses algorítmicos decorrem primordialmente da qualidade e representatividade dos dados de treino; a IA perpetua desigualdades se utilizada de forma acrítica.
* **Afirmações condicionadas ao contexto:** Quando orientada por diretrizes de governança e conjuntos de dados devidamente desviesados (*debiased*), a IA pode atuar como redutora de subjetividades humanas.
* **Hipóteses / Possibilidades:** Apontam a urgência de regulamentações éticas e auditorias contínuas nos pipelines de recrutamento automatizado.

---

# 6. CONCEITOS IMPORTANTES
* **Viés Algorítmico (*Algorithmic Bias*):**
  * *Como define/utiliza:* Desvios sistemáticos e injustos nas decisões do modelo que prejudicam um grupo social específico.
  * *Localização:* Resumo e Seção 1 (Introdução).
  * *Importância:* Conceito central da pesquisa.
* **Dados Históricos de Treinamento (*Historical Bias*):**
  * *Como define/utiliza:* Dados passados que carregam as escolhas e discriminações estruturais da sociedade.
  * *Localização:* Seção 2 e Seção 4.
  * *Importância:* Causa raiz identificada no estudo.
* **Variáveis Proxy:**
  * *Como define/utiliza:* Atributos secundários que guardam alta correlação com a variável sensível protegida (gênero), permitindo a discriminação indireta.
  * *Localização:* Seção 4 (Discussão).
  * *Importância:* Explica por que a limpeza superficial de dados falha.
* **Representatividade e Diversidade:**
  * *Como define/utiliza:* Presença proporcional de grupos minorizados no conjunto de dados de treino.
  * *Localização:* Seção 4.
  * *Importância:* Requisito para modelos equitativos.
* **Curadoria e Desviesamento (*Debiasing*):**
  * *Como define/utiliza:* Procedimentos de Engenharia de Dados para auditar e equilibrar o corpus de treinamento.
  * *Localização:* Seção 4 e 5.
  * *Importância:* Estratégia de mitigação.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* Amostra quantitativa final delimitada a 7 estudos centrais resultantes da busca estruturada na plataforma Consensus AI.
* Foco temático restrito à desigualdade de gênero no ambiente de RH e processos seletivos.

### Limitações observáveis (Interpretação da análise)
* O trabalho não realiza experimentos próprios com código-fonte ou derivações matemáticas de funções de custo, tratando-se de uma revisão integrativa qualitativa.

### Impacto das limitações
* Não enfraquece o valor do trabalho como evidência empírica recente (2026), mas indica que o artigo deve ser utilizado no TCC como estudo de caso paradigmático de viés nos dados.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva importante documentada:** 2 dos 7 estudos (28,57%) demonstraram que sistemas de IA estruturados especificamente com algoritmos cegos a variáveis sensíveis conseguiram ser mais justos que recrutadores humanos, provando que a tecnologia não é intrinsecamente má, mas totalmente dependente da qualidade da engenharia de dados que a alimenta.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com clareza exemplar os elos: **Dados Históricos $\rightarrow$ Falta de Representatividade $\rightarrow$ Variáveis Proxy $\rightarrow$ Viés $\rightarrow$ Treinamento $\rightarrow$ Falha de Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que pipelines de Engenharia de Software devem incluir testes de validação ética antes do deploy.

### 9.3 Qual parte ele não aborda?
* Não trata de fórmulas matemáticas de otimização, *missing values* numéricos ou *Data Drift* contínuo.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; ilustra com perfeição a tese de que problemas nos dados históricos passam despercebidos durante a modelagem se não houver curadoria ativa.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Modelos treinados com dados de contratações passadas replicam exclusões. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | A ausência de imparcialidade na base corrompe a predição. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | A remoção de variáveis proxy e o debiasing são necessários. | **SIM — demonstrado** |
| Representatividade influencia os resultados | Falta de mulheres em cargos seniores nos dados ensina ao modelo que homens são melhores. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Núcleo do artigo: 71,43% dos estudos confirmam viés induzido pelos dados. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Aprendizado da correlação espúria entre palavras masculinas e competência. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | O modelo pode ter acurácia alta em reproduzir o passado, mas falhar na justiça real. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Trata da defasagem histórica dos dados corporativos. | **PARCIAL** |
| Qualidade dos dados influencia confiabilidade | Sistemas enviesados geram riscos jurídicos, éticos e operacionais graves. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Curadoria ativa de dados e auditoria de variáveis proxy. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta e Seleção:** **SIM** (análise da contaminação histórica na seleção de bases).
* **Limpeza e Transformação:** **SIM** (expurgo de termos proxy e debiasing em NLP).
* **Qualidade e Validação:** Foco nas dimensões de **imparcialidade, equidade e representatividade**.
* **Governança:** **SIM** (auditoria ética de datasets).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **PARCIAL** — Discute a curadoria, saneamento e preparação de datasets sob o viés da Gestão da Informação e Ética em IA, conceitos que alimentam diretamente os requisitos de Engenharia de Dados.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Esse fenômeno decorre, em grande medida, da forma como os algoritmos são treinados, uma vez que se baseiam em dados históricos que podem incorporar padrões discriminatórios e, assim, perpetuar desigualdades."*  
  * *Localização:* p. 139 (Resumo).  
  * *Tipo:* Conclusão / Tese central.  
  * *Uso no TCC:* Fundamentar no Capítulo 1 e Capítulo 4 como o viés dos dados é transferido ao modelo.
* **Trecho 2:** *"A simples remoção da variável explícita de gênero não impede a discriminação algorítmica, pois o modelo aprende correlações com variáveis proxies presentes no histórico dos candidatos."*  
  * *Localização:* p. 147 (Seção 4).  
  * *Tipo:* Resultado / Análise crítica.  
  * *Uso no TCC:* Demonstrar no Capítulo 2 e 4 por que a preparação de dados requer técnicas avançadas de Engenharia de Atributos e não apenas deleção de colunas.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Dastin, J. (2018):** *Amazon scraps secret AI recruiting tool that showed bias against women*. (Reuters - O caso canônico da Amazon).
* **O'Neil, C. (2016):** *Weapons of Math Destruction: How big data increases inequality and threatens democracy*. (Livro fundamental sobre viés em dados).
* **AI Now Institute (2018):** *AI Now Report*. (Relatório mundial de impacto de IA).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **IMPORTANTE**
* **Justificativa:** Fornece evidência científica brasileira super recente (2026) e documentação empírica indispensável para o capítulo de Viés e Representatividade.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** Contextualização do impacto de modelos opacos e enviesados no mundo real.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Seção sobre Viés Histórico, Variáveis Proxy e Falta de Representatividade.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** SILVA, F. H. F. et al. Inteligência Artificial e Desigualdade de Gênero entre Homens e Mulheres: uma análise dos vieses em processos seletivos de contratação. *Perspectivas em Gestão & Conhecimento*, João Pessoa, v. 16, n. 1, p. 138-154, 2026. DOI: 10.22478/ufpb.2236-417X.2026v16n1.74614.
* **Problema:** Perpetuação de desigualdades de gênero por modelos de IA treinados com históricos de RH.
* **Objetivo:** Analisar vieses algorítmicos em processos seletivos e mapear as causas relacionadas aos dados.
* **Metodologia:** Revisão integrativa da literatura com auxílio da plataforma Consensus AI.
* **Principais resultados:** 71,43% dos estudos confirmam discriminação induzida por dados históricos; a exclusão simples de colunas não neutraliza variáveis proxy.
* **Principais conceitos:** Viés Algorítmico, Gênero, Dados Históricos, Variáveis Proxy, Recrutamento Automatizado, Curadoria.
* **Conclusões dos autores:** A IA replica e potencializa os vieses dos dados de treino; a mitigação exige curadoria ativa de dados e governança.
* **Limitações:** Focado no contexto de recursos humanos e gênero.
* **Contradições/ressalvas:** A IA pode reduzir vieses humanos se alimentada com bases devidamente auditadas e desviesadas.
* **Contribuição para o TCC:** Estudo de caso empírico sobre como a falha nos dados históricos contamina o treinamento de modelos.
* **Capítulo provável:** Capítulo 1 e Capítulo 4.
* **Citação principal:** *"A simples remoção da variável explícita de gênero não impede a discriminação algorítmica, pois o modelo aprende correlações com variáveis proxies..."*
* **Palavras-chave:** Inteligência Artificial; Viés de Gênero; Dados de Treinamento; Variáveis Proxy; Recrutamento.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 9.0 / 10 |
| Qualidade metodológica | 8.5 / 10 |
| Relevância para Engenharia de Dados | 7.5 / 10 |
| Relevância para Qualidade de Dados | 9.0 / 10 |
| Relevância para Machine Learning | 8.5 / 10 |
| Relevância para Viés/Generalização | 10 / 10 |
| Atualidade | 10 / 10 (2026) |
* **Avaliação global:** 8.9 / 10 — Estudo recente com valor analítico excelente para demonstrar variáveis proxy e viés histórico.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** Fornece uma demonstração empírica e clara sobre o mecanismo das variáveis proxy e viés de dados históricos em modelos preditivos reais.
* **Função única:** Exemplificar como o aprendizado supervisionado absorve correlações indiretas em dados textuais de treinamento.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** O percentual de 71,43% de convergência em viés nos estudos e a ineficácia da supressão de colunas contra variáveis proxy.
* **O que é interpretação:** A extrapolação dos achados para esteiras industriais de crédito ou visão computacional.
* **O que não podemos afirmar com base neste artigo:** Fórmulas matemáticas de otimização de funções de perda com restrições de equidade (*fairness constraints*).
