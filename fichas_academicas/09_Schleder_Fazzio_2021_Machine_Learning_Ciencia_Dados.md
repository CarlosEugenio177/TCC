# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 09:** Schleder & Fazzio (2021)  
**Arquivo Analisado:** `download.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Machine Learning na Física, Química, e Ciência de Materiais: Descoberta e Design de Materiais
* **Autores:** Gabriel R. Schleder; Adalberto Fazzio
* **Ano:** 2021 (Recebido em 23/09/2020 • Aceito em 19/10/2020 • Publicado em 2021)
* **Instituição/país:** Laboratório Nacional de Nanotecnologia – Centro Nacional de Pesquisa em Energia e Materiais (LNNano/CNPEM, Campinas - SP) e Universidade Federal do ABC (UFABC, Santo André - SP), Brasil.
* **Revista, congresso, repositório ou evento:** *Revista Brasileira de Ensino de Física* (RBEF), vol. 43, suppl. 1, e20200407.
* **Volume, número e páginas:** Volume 43, Suplemento 1, artigo e20200407 (18 páginas).
* **DOI:** `10.1590/1806-9126-RBEF-2020-0407`
* **URL:** `https://www.scielo.br/j/rbef/a/FkmwQ6rL5wT6yF8wH9x4N9k/` (SciELO)
* **Tipo de publicação:** Artigo científico / Artigo geral tutorial em periódico qualificado (Qualis A).
* **Idioma:** Português (com título, resumo e termos em inglês)
* **Tipo de pesquisa:** Revisão metodológica, conceitual e tutorial de pipeline de ciência de dados e Machine Learning.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** Como transformar o crescimento exponencial na geração de dados científicos brutos e heterogêneos em capacidade preditiva real e descoberta de novos padrões por meio de algoritmos de Machine Learning, superando os desafios de consolidação de bancos de dados padronizados, engenharia de representação (*feature engineering*) e prevenção de armadilhas metodológicas como o vazamento de dados (*data leakage*).
* **Pergunta de pesquisa:** Quais são as etapas metodológicas e arquiteturais essenciais do ciclo de vida dos dados e do pipeline de Machine Learning necessárias para garantir que os modelos aprendam leis causais verdadeiras em vez de memorizarem correlações espúrias dos dados de treino?
* **Objetivo principal:** Apresentar o contexto do surgimento do Machine Learning, seus fundamentos teóricos, as etapas completas de estruturação de dados, engenharia de atributos (*descriptors*), pré-processamento, treinamento, validação e aplicações práticas na descoberta e design de materiais.
* **Hipóteses ou questões específicas:** O sucesso da aplicação de algoritmos de Machine Learning é condicionado à existência de bancos de dados consistentes, padronizados e interoperáveis (Princípios FAIR) e à formulação de descritores de atributos invariantes e representativos do fenômeno estudado.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Teórico-metodológica, aplicada e tutorial.
* **Tipo de estudo:** Revisão sistemática e tutorial de engenharia de dados e modelagem de AM.
* **Fonte dos dados:** Grandes repositórios científicos internacionais abertos de dados de materiais e estruturas atômicas (Materials Project, AFLOW, OQMD, NOMAD, Citrination).
* **População/amostra:** Milhares de compostos e estruturas materiais catalogadas computacionalmente e experimentalmente.
* **Período analisado:** Panorama dos avanços na área nas décadas de 2010 e 2020.
* **Métodos de coleta:** Mineração de dados em repositórios abertos estruturados.
* **Métodos de análise:** Descrição passo a passo da esteira de dados: (1) Consolidação de Banco de Dados FAIR; (2) *Feature Engineering* (transformação de dados não estruturados em vetores numéricos de descritores invariantes); (3) Pré-processamento e Normalização; (4) Particionamento Estratificado e Validação Cruzada Agrupada; (5) Treinamento Algorítmico; (6) Avaliação de Incerteza e Domínio de Aplicabilidade.
* **Modelos/algoritmos abordados:** Modelos Lineares (Ridge, Lasso), Árvores de Decisão, Random Forest, Support Vector Machines (SVM), Redes Neurais Artificiais (ANN) e Kernel Ridge Regression (KRR).
* **Métricas:** Erro Médio Absoluto (MAE), Erro Quadrático Médio (RMSE), $R^2$, Desvio Padrão Residual e limites de incerteza preditiva.
* **Procedimentos experimentais:** Apresentação de fluxogramas metodológicos de ponta a ponta e demonstração de cálculo de métricas em pipelines de regressão e classificação.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Centralidade dos Bancos de Dados Padronizados (Princípios FAIR)
* **O que foi encontrado:** Os autores demonstram historicamente que o aprendizado de máquina só se tornou viável em física e química após a criação, padronização e consolidação de repositórios consistentes orientados pelos princípios FAIR (*Findable, Accessible, Interoperable, Reusable*); sem essa infraestrutura prévia de Engenharia de Dados, os algoritmos operavam de forma inútil sobre dados dispersos e corrompidos.
* **Evidência:** Linha do tempo da consolidação dos bancos de dados abertos (Materials Project, AFLOW).
* **Interpretação dos autores:** A infraestrutura de dados é o catalisador primário que viabiliza o aprendizado de máquina.
* **Grau de evidência:** **Direto** (análise histórica e metodológica documentada).

### Resultado 2: O Teto de Desempenho Ditado pela Engenharia de Atributos (*Feature Engineering*)
* **O que foi encontrado:** A qualidade da representação vetorial dos dados de entrada dita o limite máximo de acurácia que o modelo pode atingir. Se as *features* não capturam as simetrias e invariâncias fundamentais do fenômeno, nenhum algoritmo sofisticado ou ajuste fino de hiperparâmetros é capaz de compensar essa deficiência (*Garbage In, Garbage Out*).
* **Evidência:** Comparação entre diferentes famílias de descritores atômicos e sua influência no $R^2$ final de modelos preditivos.
* **Interpretação dos autores:** A inteligência do sistema reside na capacidade da engenharia de atributos de sintetizar a física do problema em números computáveis.
* **Grau de evidência:** **Direto**.

### Resultado 3: O Risco Crítico de Data Leakage em Divisões Ingênuas de Treino/Teste
* **O que foi encontrado:** O particionamento puramente aleatório de conjuntos de treino e teste em bases de dados que possuem instâncias correlacionadas ou geradas pela mesma fonte causa vazamento de dados (*Data Leakage*), gerando métricas de $R^2$ e acurácia artificialmente perfeitas em bancada que desmoronam quando o modelo tenta predizer sistemas novos.
* **Evidência:** Demonstração da necessidade de validação cruzada agrupada (*Grouped/Leave-One-Cluster-Out Cross-Validation*).
* **Interpretação dos autores:** O protocolo de validação deve simular estritamente o cenário de aplicação no mundo real para garantir generalização autêntica.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* Os autores concluem que o Machine Learning é uma ferramenta transformadora para a ciência moderna, mas cujo sucesso depende inteiramente da qualidade, representação e curadoria rigorosa dos dados de entrada.
* **Afirmações fortes:** O modelo de AM é um mero aproximador funcional que só reproduz o que os dados expressam; descritores mal elaborados ou dados com ruído inviabilizam a descoberta científica (*Garbage In, Garbage Out*).
* **Afirmações condicionadas ao contexto:** As predições de qualquer modelo só são válidas dentro de seu \"Domínio de Aplicabilidade\" (*Applicability Domain*), ou seja, no espaço delimitado pela densidade dos dados de treinamento.
* **Hipóteses / Possibilidades:** Apontam o desenvolvimento de representações baseadas em grafos e aprendizado ativo (*Active Learning*) como o futuro da integração entre dados e modelos preditivos.

---

# 6. CONCEITOS IMPORTANTES
* **Pipeline de Machine Learning e Dados:**
  * *Como define/utiliza:* Fluxo integrado que vai da coleta e estruturação de dados brutos à predição e estimativa de incerteza.
  * *Localização:* p. 3 e p. 5 (Figura 3).
  * *Importância:* Estrutura didática de toda a esteira de software inteligente.
* **Feature Engineering / Descritores:**
  * *Como define/utiliza:* Transformação matemática de dados não estruturados brutos em matrizes de atributos invariantes.
  * *Localização:* p. 6-8.
  * *Importância:* Etapa técnica determinante de qualidade da representação.
* **Princípios FAIR na Gestão de Dados:**
  * *Como define/utiliza:* Diretrizes de Localizabilidade, Acessibilidade, Interoperabilidade e Reusabilidade para bancos de dados de treino.
  * *Localização:* p. 3.
  * *Importância:* Alinhamento direto com a Engenharia de Dados contemporânea.
* **Data Leakage (Vazamento de Dados):**
  * *Como define/utiliza:* Contaminação espúria do conjunto de treino com informações provenientes do conjunto de teste ou dependências não controladas.
  * *Localização:* p. 9.
  * *Importância:* Causa clássica de falsa generalização em ML.
* **Domínio de Aplicabilidade (*Applicability Domain*):**
  * *Como define/utiliza:* Hipervolume no espaço de atributos coberto pelos dados de treino onde o modelo mantém predições confiáveis.
  * *Localização:* p. 11.
  * *Importância:* Critério formal de confiabilidade operacional.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* Foco temático voltado à física molecular, química e ciência de materiais.
* Ênfase em métodos de regressão e aprendizado supervisionado estático em bases consolidadas.

### Limitações observáveis (Interpretação da análise)
* Os exemplos utilizam átomos e arranjos cristalinos; a Engenharia de Software deve abstrair esses exemplos e focar nas regras universais do pipeline de dados, na divisão treino/teste e no cálculo de métricas.

### Impacto das limitações
* Não afeta o rigor do trabalho, pois a formulação do pipeline de dados apresentada é idêntica à utilizada em qualquer sistema corporativo de Machine Learning.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva importante sobre complexidade:** Modelos lineares regulares (como Ridge e Lasso) ou Kernel Ridge Regression frequentemente superam redes neurais profundas quando a engenharia de atributos é bem executada em conjuntos de dados de tamanho moderado, provando que gastar esforço na preparação de dados compensa mais do que aumentar a complexidade algorítmica.
* **Resultado negativo documentado:** Divisões puramente aleatórias de teste em dados estruturados geram ilusão de convergência devido ao *Data Leakage*.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com clareza cristalina os elos: **Engenharia de Dados $\rightarrow$ Bancos de Dados FAIR $\rightarrow$ Feature Engineering $\rightarrow$ Pré-processamento $\rightarrow$ Prevenção de Data Leakage $\rightarrow$ Generalização $\rightarrow$ Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que pipelines automatizados de ciência de dados devem integrar estimativas de incerteza em tempo real.

### 9.3 Qual parte ele não aborda?
* Não aborda viés social/demográfico em sistemas de justiça ou contratação.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; constitui a síntese didática perfeita de como estruturar a esteira técnica de dados e aprendizado de máquina no TCC.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | O avanço do ML só ocorreu com a consolidação de repositórios estruturados. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Princípio *Garbage In, Garbage Out* demonstrado na prática científica. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Normalização e descritores determinam o espaço de hipóteses do modelo. | **SIM — demonstrado** |
| Representatividade influencia os resultados | O modelo só prevê com segurança dentro do Domínio de Aplicabilidade. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Vieses de medição experimental são aprendidos pelo algoritmo. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Memorização de ruído amostral se a base for pequena ou mal particionada. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | O *Data Leakage* em splits aleatórios gera falsa acurácia de teste. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Predições fora do Domínio de Aplicabilidade perdem a validade. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade das predições depende da incerteza estimada e dos dados. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Repositórios FAIR, padronização de esquemas e pipelines reprodutíveis. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta e Ingestão:** **SIM** (mineração de dados em repositórios abertos).
* **Armazenamento e Repositórios:** **SIM** (estruturação de bases de dados FAIR).
* **Limpeza e Transformação:** **SIM** (saneamento e normalização).
* **Feature Engineering:** **FOCO DO ARTIGO** (representação de dados complexos).
* **Validação / Prevenção de Data Leakage:** **SIM** (particionamento agrupado e teste estrito).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM** — O artigo apresenta detalhadamente a esteira de Engenharia de Dados (coleta, padronização FAIR, engenharia de atributos, saneamento e divisão de dados) como condição *sine qua non* para o treinamento de Machine Learning.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"A aplicação de algoritmos de aprendizado de máquina só se tornou viável recentemente devido à criação, padronização e consolidação de bancos de dados consistentes e de alta qualidade."*  
  * *Localização:* p. 2 (Introdução).  
  * *Tipo:* Conclusão histórica / Premissa de Engenharia.  
  * *Uso no TCC:* Introdução do Capítulo 2 para provar que a Engenharia de Dados precede e viabiliza a Ciência de Dados e o Machine Learning.
* **Trecho 2:** *"A etapa de representação dos dados (engenharia de atributos) e o pré-processamento são cruciais: o modelo só é capaz de aprender aquilo que os atributos de entrada conseguem expressar numericamente sobre o fenômeno."*  
  * *Localização:* p. 7 (Seção de Descritores).  
  * *Tipo:* Definição metodológica.  
  * *Uso no TCC:* Capítulo 3 para conceituar *Feature Engineering* e seu papel limitante/potencializador no aprendizado.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Jain, A. et al. (2013):** *Commentary: The Materials Project: A materials genome approach to accelerating materials innovation*. (APL Materials - O caso de sucesso de repositório FAIR).
* **Wilkinson, M. D. et al. (2016):** *The FAIR Guiding Principles for scientific data management and stewardship*. (Scientific Data - A carta fundadora dos Princípios FAIR).
* **Hastie, T., Tibshirani, R. & Friedman, J. (2009):** *The Elements of Statistical Learning*. (Livro fundamental de AM).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **IMPORTANTE**
* **Justificativa:** É a melhor referência tutorial e conceitual brasileira detalhando o pipeline técnico completo de Engenharia de Dados, *Feature Engineering*, princípios FAIR e prevenção de *Data Leakage*.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Seção sobre Ciclo de Vida dos Dados e Princípios FAIR na construção de bases de treinamento.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Seções sobre *Feature Engineering*, Particionamento de Bases (Treino/Validação/Teste) e Prevenção de *Data Leakage*.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** SCHLEDER, G. R.; FAZZIO, A. Machine Learning na Física, Química, e Ciência de Materiais: Descoberta e Design de Materiais. *Revista Brasileira de Ensino de Física*, v. 43, suppl. 1, e20200407, 2021. 18 p. DOI: 10.1590/1806-9126-RBEF-2020-0407.
* **Problema:** Como estruturar pipelines de dados consistentes para permitir predições confiáveis e generalizáveis via ML a partir de grandes volumes brutos.
* **Objetivo:** Apresentar um panorama tutorial sobre o pipeline completo de dados, representação de atributos, modelagem e validação em AM.
* **Metodologia:** Revisão conceitual, metodológica e aplicada de fluxos de engenharia de dados e algoritmos de AM.
* **Principais resultados:** Repositórios padronizados FAIR viabilizam o ML; a qualidade dos descritores limita a acurácia do modelo (*Garbage In, Garbage Out*); divisões aleatórias ingênuas geram *Data Leakage*.
* **Principais conceitos:** Pipeline de ML, Feature Engineering, Princípios FAIR, Data Leakage, Domínio de Aplicabilidade, Confiabilidade.
* **Conclusões dos autores:** O aprendizado de máquina depende umbilicalmente da qualidade dos dados e da representação de atributos; a generalização exige validações estritas.
* **Limitações:** Exemplos práticos focados em física e ciência de materiais.
* **Contradições/ressalvas:** Modelos simples com boas features superam modelos complexos com features mal elaboradas.
* **Contribuição para o TCC:** Sistematização didática do pipeline de Engenharia de Dados e Machine Learning.
* **Capítulo provável:** Capítulo 2 e Capítulo 3.
* **Citação principal:** *"A etapa de representação dos dados (engenharia de atributos) e o pré-processamento são cruciais: o modelo só é capaz de aprender aquilo que os atributos de entrada conseguem expressar..."*
* **Palavras-chave:** Machine Learning; Engenharia de Atributos; Qualidade de Dados; Princípios FAIR; Data Leakage; Confiabilidade.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 9.5 / 10 |
| Qualidade metodológica | 9.5 / 10 |
| Relevância para Engenharia de Dados | 9.5 / 10 |
| Relevância para Qualidade de Dados | 9.0 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 8.5 / 10 |
| Atualidade | 9.0 / 10 (2021) |
* **Avaliação global:** 9.3 / 10 — Artigo de altíssimo valor didático e metodológico para o Capítulo 2 e 3.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** Fornece o esquema visual e metodológico completo da esteira de dados e *Feature Engineering* em língua portuguesa, com excelente fundamentação teórica.
* **Função única:** Fornecer a base metodológica para explicar o pipeline de dados, os princípios FAIR e o mecanismo de prevenção de *Data Leakage*.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** O diagrama do pipeline de ML, os requisitos dos princípios FAIR e a demonstração dos riscos de *Data Leakage* em divisões puramente aleatórias.
* **O que é interpretação:** A aplicação direta das mesmas nomenclaturas de descritores físicos para variáveis de sistemas de informação bancários ou de comércio eletrônico.
* **O que não podemos afirmar com base neste artigo:** Quaisquer análises sobre discriminação algorítmica demográfica ou vieses socioculturais.
