# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Inteligência Artificial e Desigualdade de Gênero entre Homens e Mulheres: uma análise dos vieses em processos seletivos de contratação
* **Autores:** Flávia Helloysa Fontes Silva; Natanael Vítor Sobral; Daniela Eugênia Moura de Albuquerque; Leilah Santiago Bufrem; Fábio Mascarenhas e Silva
* **Ano:** 2026 (Jan./Abr. 2026)
* **Instituição/País:** Universidade Federal de Pernambuco (UFPE) e Universidade Federal da Bahia (UFBA), Brasil.
* **Local de publicação:** *Perspectivas em Gestão & Conhecimento*, João Pessoa, v. 16, n. 1, p. 138-154.
* **DOI / Link:** `10.22478/ufpb.2236-417X.2026v16n1.74614` (ISSN: 2236-417X)
* **Tipo de publicação:** Artigo científico em periódico (Relato de Pesquisa).
* **Tipo de pesquisa/metodologia:** Revisão integrativa da literatura com auxílio de plataforma de síntese de evidências por IA (Consensus AI).

---

## 2. Objetivo do artigo
* **Problema investigado:** A forma como sistemas de inteligência artificial aplicados à triagem e seleção de pessoal incorporam, reproduzem e aprofundam disparidades de gênero contra candidatas mulheres ao serem alimentados e treinados com bases de dados históricas desbalanceadas e enviesadas.
* **Objetivo principal:** Analisar as manifestações de viés de gênero produzidas por modelos de IA em processos seletivos, identificando os mecanismos de dados subjacentes que geram tratamentos discriminatórios.
* **Pergunta/Hipótese:** De que modo dados históricos de contratações refletem padrões discriminatórios pré-existentes e como esses padrões são transferidos para os modelos de aprendizado durante a etapa de treinamento?

---

## 3. Principais conceitos
* **Viés Algorítmico de Gênero:** Discriminação algorítmica sistemática decorrente do treinamento sobre distribuições desiguais de perfis masculinos e femininos.
* **Dados Históricos de Treinamento (*Historical Bias*):** Registros de decisões corporativas do passado onde prevaleciam preferências masculinas; os modelos aprendem tais registros como "padrões ótimos de contratação".
* **Variáveis *Proxy* (Substitutas Ocultas):** Termos e atributos correlacionados ao gênero (ex.: nomes de instituições de ensino exclusivamente femininas, envolvimento em esportes específicos, lacunas no histórico profissional por licença-maternidade) que permitem ao algoritmo discriminar mesmo quando o atributo explícito "gênero" é excluído.
* **Falta de Diversidade e Representatividade:** Sub-representação numérica de perfis femininos em bases de treinamento de cargos de tecnologia e alta gestão.
* **Curadoria e Desviesamento de Dados (*Debiasing*):** A necessidade de técnicas prévias de Engenharia de Dados para auditar, balancear e expurgar termos tendenciosos antes da indução do modelo.

---

## 4. Metodologia
* **Abordagem:** Qualitativa e integrativa.
* **Fonte dos dados:** Artigos científicos indexados recuperados via Consensus AI e bases de dados acadêmicas internacionais.
* **Critérios:** Definição de critérios formais de inclusão/exclusão, análise de relevância temática e categorização dos resultados segundo o tipo de viés e impactos documentados.
* **Amostra:** Corpus refinado de estudos empíricos e teóricos internacionais e nacionais sobre IA em recursos humanos.

---

## 5. Principais resultados
* **Resultado 1 (Confirmação de Viés em 71,43% dos Estudos):** A grande maioria dos estudos empíricos atesta que modelos treinados com bases brutas de recrutamento reproduzem e amplificam o viés discriminatório contra mulheres.
* **Resultado 2 (Inoperância da Supressão Simples de Colunas):** O estudo detalha que simplesmente remover o campo "sexo/gênero" da tabela não resolve o viés, pois o algoritmo aprende as correlações latentes através de variáveis *proxy* no vocabulário dos currículos.
* **Resultado 3 (O Caso Emblemático da Amazon):** Análise do famoso algoritmo de triagem da Amazon que penalizou currículos com a palavra *"women's"*, evidenciando o perigo de treinar modelos em dados históricos de empresas dominadas por homens.
* **Importância para o TCC:** Fornece um caso prático documentado e evidência empírica recente (2026) demonstrando que a ausência de curadoria e auditoria em Engenharia de Dados gera discriminação sistemática em Machine Learning.

---

## 6. Relação com o meu TCC
* **Classificação:** **IMPORTANTE**
* **Justificativa:** Conecta perfeitamente os elos "Dados Históricos → Falta de Representatividade → Viés → Treinamento → Confiabilidade", enriquecendo os capítulos de Introdução e Viés do TCC.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Introdução & Justificativa:** Para contextualizar o impacto ético e social de modelos treinados com dados de baixa qualidade e sem representatividade.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para fundamentar os conceitos de Viés Histórico e Variáveis *Proxy*, utilizando o caso de triagem de currículos como exemplo ilustrativo.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 139):** *"Esse fenômeno decorre, em grande medida, da forma como os algoritmos são treinados, uma vez que se baseiam em dados históricos que podem incorporar padrões discriminatórios e, assim, perpetuar desigualdades."*  
  * *Uso no TCC:* Fundamentar que os algoritmos refletem os vícios contidos nos dados de entrada.
* **Trecho 2 (p. 147):** *"A simples remoção da variável explícita de gênero não impede a discriminação algorítmica, pois o modelo aprende correlações com variáveis proxies presentes no histórico dos candidatos."*  
  * *Uso no TCC:* Explicar a limitação de tratamentos superficiais de dados e a necessidade de técnicas avançadas de Engenharia de Dados.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho/equidade de ML: **Sim** (equidade é dimensão de qualidade).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (modelos discriminatórios em contratação).
3. A preparação dos dados influencia o treinamento: **Sim** (necessidade de curadoria e debiasing).
4. A representatividade dos dados influencia a generalização: **Sim** (sub-representação de mulheres vicia a predição).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (núcleo da pesquisa).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (associação espúria entre gênero e competência).
7. Um bom desempenho na avaliação não garante justiça/generalização: **Sim** (alta acurácia na reprodução de padrões passados injustos).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (risco legal, ético e corporativo).
9. Processos de Engenharia de Dados melhoram a qualidade dos dados: **Sim** (auditoria e balanceamento de representatividade).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (atuam de forma oculta através de proxies textuais).

---

## 10. Limitações
* **Declaradas pelos autores:** Foco exclusivo no viés de gênero no contexto de RH e recrutamento.
* **Para o TCC:** Artigo da área de Gestão e Ciência da Informação; deve ser empregado para embasar o estudo de caso de viés nos dados em Machine Learning.

---

## 11. Lacunas e oportunidades
* O trabalho aponta a necessidade de desenvolver pipelines automatizados de detecção de variáveis *proxy* na fase de *Feature Engineering*.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Enfoca representatividade, imparcialidade e integridade contextual. |
| Preparação dos dados | Sim | Curadoria de dados e expurgo de termos discriminatórios (*proxies*). |
| Engenharia de Dados | Parcialmente | Situada na fase de coleta e seleção de bases de treinamento. |
| Viés | Sim | Viés histórico, viés de gênero e viés algorítmico. |
| Representatividade | Sim | Sub-representação feminina em setores corporativos específicos. |
| Generalização | Sim | O modelo falha ao tentar selecionar candidatos de forma justa. |
| Confiabilidade | Sim | Perda de credibilidade e geração de passivos ético-legais. |
| Machine Learning | Sim | Modelos de classificação, escore e Processamento de Linguagem Natural. |

---

## 13. Ficha de leitura final
* **Referência:** SILVA, F. H. F. et al. Inteligência Artificial e Desigualdade de Gênero entre Homens e Mulheres: uma análise dos vieses em processos seletivos de contratação. *Perspectivas em Gestão & Conhecimento*, João Pessoa, v. 16, n. 1, p. 138-154, 2026.
* **Problema:** Perpetuação de desigualdades de gênero por modelos de IA treinados com dados históricos de RH.
* **Objetivo:** Analisar vieses algorítmicos em processos seletivos e mapear as causas relacionadas aos dados.
* **Metodologia:** Revisão integrativa da literatura com síntese por IA (Consensus AI).
* **Principais resultados:** 71,43% dos estudos confirmam discriminação algorítmica induzida por dados históricos e variáveis proxy.
* **Conceitos-chave:** Viés Algorítmico, Gênero, Dados Históricos, Variáveis Proxy, Recrutamento Automatizado.
* **Contribuição para o TCC:** Exemplifica como a falta de curadoria nos dados históricos contamina o treinamento de modelos.
* **Capítulo provável:** Capítulo 1 e Capítulo 4.
* **Citação mais importante:** *"A simples remoção da variável explícita de gênero não impede a discriminação algorítmica, pois o modelo aprende correlações com variáveis proxies..."*
* **Palavras-chave:** Inteligência Artificial; Viés de Gênero; Dados de Treinamento; Variáveis Proxy.

---

## 14. Avaliação final
* **Nota:** 9.0 / 10
* **Justificativa:** Estudo brasileiro recente (2026) com grande clareza e valor ilustrativo sobre como dados históricos e variáveis proxy transmitem vieses para os modelos.
* **Decisão:** **SIM** (Permanecer entre as 20 referências principais).
