# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Machine Learning na Física, Química, e Ciência de Materiais: Descoberta e Design de Materiais
* **Autores:** Gabriel R. Schleder; Adalberto Fazzio
* **Ano:** 2021
* **Instituição/País:** Laboratório Nacional de Nanotecnologia (LNNano/CNPEM, Campinas-SP) e Universidade Federal do ABC (UFABC, Santo André-SP), Brasil.
* **Local de publicação:** *Revista Brasileira de Ensino de Física* (RBEF), vol. 43, suppl. 1, e20200407.
* **DOI / Link:** `https://doi.org/10.1590/1806-9126-RBEF-2020-0407` (Scielo)
* **Tipo de publicação:** Artigo de revisão e tutorial metodológico em periódico consolidado (Qualis A).
* **Tipo de pesquisa/metodologia:** Revisão conceitual, metodológica e tutorial de pipelines de Machine Learning e ciência de dados aplicados a ciências exatas.

---

## 2. Objetivo do artigo
* **Problema investigado:** Como transformar grandes volumes de dados científicos brutos e heterogêneos em conhecimento preditivo acurado e generalizável por meio de algoritmos de Machine Learning, superando os desafios de estruturação de bancos de dados consistentes e engenharia de representação de *features*.
* **Objetivo principal:** Apresentar de forma didática e metodológica todo o pipeline de dados de Machine Learning — da coleta e padronização em repositórios abertos à engenharia de atributos (*descriptors*), pré-processamento, validação e generalização —, demonstrando sua aplicação prática.
* **Pergunta/Hipótese:** Quais são as boas práticas de Engenharia de Dados e estruturação de atributos necessárias para garantir que modelos de AM aprendam relações causais e generalizáveis em vez de memorizar ruídos amostrais?

---

## 3. Principais conceitos
* **Pipeline Integrado de Dados e Machine Learning:** Ciclo sistemático: Coleta/Geração de Dados → Bancos de Dados Padronizados → Engenharia de *Features* (Descritores) → Pré-processamento/Normalização → Treinamento → Validação Cruzada → Predição.
* **Engenharia de Atributos (*Feature Engineering / Descriptors*):** Processo crítico de converter dados brutos não estruturados em vetores numéricos invariantes e informativos que tornam o problema tratável para algoritmos de AM.
* **Princípios FAIR na Gestão de Dados:** Princípios de que os dados de treino devem ser Localizáveis (*Findable*), Acessíveis (*Accessible*), Interoperáveis (*Interoperable*) e Reutilizáveis (*Reusable*), pilar da Engenharia de Dados contemporânea.
* **Divisão de Dados e *Data Leakage* (Vazamento de Dados):** O risco crítico de vazamento de informação entre conjuntos de treino e teste provocado por divisões puramente aleatórias em dados correlacionados, exigindo validação cruzada agrupada (*Grouped Cross-Validation*).
* **Domínio de Aplicabilidade (*Applicability Domain*):** Espaço delimitado pelos dados de treinamento onde as predições do modelo de ML possuem confiabilidade e generalização comprovadas.

---

## 4. Metodologia
* **Abordagem:** Teórico-metodológica e tutorial aplicada.
* **Fontes dos dados:** Repositórios públicos consolidados de dados de materiais (Materials Project, AFLOW, OQMD, NOMAD).
* **Modelos e algoritmos abordados:** Modelos de regressão linear regularizada (Ridge, Lasso), Árvores de Decisão, Random Forest, Support Vector Machines (SVM), Redes Neurais Artificiais e Kernel Ridge Regression.
* **Métricas de validação:** Erro Médio Absoluto (MAE), Erro Quadrático Médio (RMSE), $R^2$ e estimativas de incerteza preditiva.

---

## 5. Principais resultados
* **Resultado 1 (A Centralidade dos Dados Padronizados):** O artigo demonstra historicamente que o Aprendizado de Máquina só se tornou viável em ciências quando a comunidade criou bancos de dados padronizados, consistentes e estruturados (Engenharia de Dados).
* **Resultado 2 (O Teto Ditado pelas Features):** A qualidade da representação dos atributos (*Feature Engineering*) define o limite superior do desempenho do modelo; algoritmos sofisticados não compensam atributos de entrada mal formulados (*Garbage In, Garbage Out*).
* **Resultado 3 (O Perigo do Data Leakage):** Falhas na divisão de dados que ignoram dependências entre amostras geram métricas de validação artificialmente elevadas que desmoronam na aplicação real.
* **Importância para o TCC:** Fornece um diagrama completo e uma descrição metodológica impecável de toda a esteira de Engenharia de Dados e Machine Learning, servindo como modelo didático para o **Capítulo 2** e **Capítulo 3**.

---

## 6. Relação com o meu TCC
* **Classificação:** **IMPORTANTE**
* **Justificativa:** É um dos melhores tutoriais científicos em língua portuguesa detalhando a esteira técnica completa de Engenharia de Dados, *Feature Engineering*, pré-processamento e prevenção de *data leakage* em AM.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para estruturar as etapas do ciclo de vida dos dados e os princípios FAIR.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para detalhar *Feature Engineering*, pré-processamento, particionamento de bases (treino/validação/teste) e mecanismos de prevenção de *Data Leakage*.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 2):** *"A aplicação de algoritmos de aprendizado de máquina só se tornou viável recentemente devido à criação, padronização e consolidação de bancos de dados consistentes e de alta qualidade."*  
  * *Uso no TCC:* Ilustrar a premissa de que a evolução do Machine Learning é viabilizada pela Engenharia de Dados e organização prévia das bases.
* **Trecho 2 (p. 7):** *"A etapa de representação dos dados (engenharia de atributos) e o pré-processamento são cruciais: o modelo só é capaz de aprender aquilo que os atributos de entrada conseguem expressar numericamente sobre o fenômeno."*  
  * *Uso no TCC:* Fundamentar que o aprendizado do modelo é limitado pela capacidade expressiva da matriz de dados de entrada.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho de ML: **Sim** (afirmação central do tutorial).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (princípio *Garbage In, Garbage Out*).
3. A preparação dos dados influencia o treinamento: **Sim** (normalização, descritores e limpeza).
4. A representatividade dos dados influencia a generalização: **Sim** (conceito de domínio de aplicabilidade).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (aprendizado de vieses do método de medição).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (memorização de ruído sem fundamento causal).
7. Um bom desempenho na avaliação não garante boa generalização: **Sim** (alerta formal contra overfitting e data leakage).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (confiabilidade em simulações científicas).
9. Processos de Engenharia de Dados melhoram a qualidade: **Sim** (padronização de repositórios estruturados).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (falsa acurácia gerada por vazamento de dados).

---

## 10. Limitações
* **Declaradas pelos autores:** Foco temático voltado a materiais e física molecular.
* **Para o TCC:** Os exemplos práticos utilizam estruturas atômicas; o TCC deve extrair os princípios de arquitetura de dados, representação e validação que são universais para qualquer aplicação de Machine Learning.

---

## 11. Lacunas e oportunidades
* O artigo não aprofunda o monitoramento em tempo real (*data drift*) pós-implantação em produção, lacuna que a dissertação de Rocha (2026) complementa com perfeição.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Padronização, consistência e princípios FAIR em datasets. |
| Preparação dos dados | Sim | Normalização, tratamento de nulos e engenharia de descritores. |
| Engenharia de Dados | Sim | Construção de repositórios consolidados e esteiras de dados estruturados. |
| Viés | Sim | Viés de medição experimental e viés de seleção amostral. |
| Representatividade | Sim | Cobertura do espaço amostral e domínio de aplicabilidade do modelo. |
| Generalização | Sim | Validação cruzada estrita e avaliação fora do domínio de treino. |
| Confiabilidade | Sim | Robustez e incerteza das predições em sistemas físicos. |
| Machine Learning | Sim | Panorama completo de algoritmos de regressão e classificação. |

---

## 13. Ficha de leitura final
* **Referência:** SCHLEDER, G. R.; FAZZIO, A. Machine Learning na Física, Química, e Ciência de Materiais: Descoberta e Design de Materiais. *Revista Brasileira de Ensino de Física*, v. 43, suppl. 1, e20200407, 2021.
* **Problema:** Como transformar dados científicos heterogêneos em predições acuradas e generalizáveis via ML.
* **Objetivo:** Apresentar um panorama tutorial sobre o pipeline completo de dados, representação e modelagem em AM.
* **Metodologia:** Revisão metodológica, conceitual e aplicada de fluxos de dados e algoritmos de ML.
* **Principais resultados:** O sucesso de modelos preditivos depende da qualidade dos bancos de dados e da engenharia de atributos; validações inadequadas provocam data leakage.
* **Conceitos-chave:** Feature Engineering, Data Pipeline, Data Leakage, Qualidade de Dados, Domínio de Aplicabilidade.
* **Contribuição para o TCC:** Fornece a melhor sistematização didática e visual do pipeline de Engenharia de Dados e Machine Learning.
* **Capítulo provável:** Capítulo 2 e Capítulo 3.
* **Citação mais importante:** *"A etapa de representação dos dados (engenharia de atributos) e o pré-processamento são cruciais: o modelo só é capaz de aprender aquilo que os atributos de entrada conseguem expressar..."*
* **Palavras-chave:** Machine Learning; Engenharia de Atributos; Qualidade de Dados; Data Pipeline; Data Leakage.

---

## 14. Avaliação final
* **Nota:** 9.0 / 10
* **Justificativa:** Excelente referência metodológica brasileira, detalhando com precisão as etapas de ingestão, feature engineering, pré-processamento e prevenção de data leakage.
* **Decisão:** **SIM** (Permanecer entre as 20 referências principais).
