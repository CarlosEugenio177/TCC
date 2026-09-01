# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Mitigating Drift in Machine Learning Systems through Continuous Input Monitoring: An Architectural Proposal and Empirical Evaluation of Detection Methods
* **Autor:** Lucas Helfstein Rocha
* **Orientadora:** Prof.ª Dr.ª Kelly Rosa Braghetto
* **Ano:** 2026 (Defesa em Março/2026)
* **Instituição/País:** Instituto de Matemática e Estatística da Universidade de São Paulo (IME-USP), São Paulo - SP, Brasil.
* **Local de publicação:** Dissertação de Mestrado em Ciência da Computação.
* **Link/Repositório:** Biblioteca Digital de Teses e Dissertações do IME-USP
* **Tipo de publicação:** Dissertação de Mestrado
* **Tipo de pesquisa/metodologia:** Pesquisa aplicada de Engenharia de Software/Sistemas com experimentação empírica de métodos de detecção de desvios em dados.

---

## 2. Objetivo do artigo
* **Problema investigado:** A degradação progressiva e silenciosa do desempenho de modelos de Machine Learning em ambientes de produção causada por alterações na distribuição dos dados de entrada (*Data Drift / Covariate Shift*) e nas relações funcionais (*Concept Drift*), em cenários onde os rótulos verdadeiros (*ground truth*) demoram a ser obtidos ou não estão disponíveis.
* **Objetivo principal:** Conceber uma proposta arquitetural integrada de Engenharia de Dados/MLOps voltada ao monitoramento contínuo de dados de entrada (*input monitoring*) de forma não supervisionada e avaliar experimentalmente a precisão e o custo computacional de diferentes algoritmos de detecção de *drift*.
* **Pergunta/Hipótese:** É viável detectar alterações na distribuição dos dados de entrada antes que elas afetem criticamente as decisões de negócio, utilizando testes estatísticos e classificadores de domínio não supervisionados na camada de engenharia de dados?

---

## 3. Principais conceitos
* **Data Drift / Covariate Shift:** Modificação na distribuição de probabilidade conjunta dos atributos de entrada (X)$ ao longo do tempo, mantendo-se (Y|X)$ constante.
* **Concept Drift:** Alteração na relação condicional entre os atributos preditores e a variável dependente (Y|X)$, tornando as regras aprendidas obsoletas.
* **Monitoramento Contínuo de Dados (*Input Monitoring*):** Prática de Engenharia de Dados e MLOps de auditar as propriedades estatísticas e a integridade dos dados na esteira de ingestão em produção.
* **Detecção Não Supervisionada de Desvios:** Métodos que operam sem necessidade de rótulos: testes univariados (Kolmogorov-Smirnov, Distância de Wasserstein, Divergência de Kullback-Leibler) e métodos multivariados baseados em ML (*Domain Classifier*, Erro de Reconstrução por PCA e Autoencoders, *Maximum Mean Discrepancy* - MMD).
* **Confiabilidade de Sistemas Inteligentes:** Manutenção contínua do comportamento operacional do software inteligente dentro dos parâmetros esperados de segurança e assertividade.

---

## 4. Metodologia
* **Abordagem:** Engenharia de software aplicada combinada com avaliação quantitativa experimental.
* **Fontes dos dados:** Datasets de referência com inserção de *drifts* sintéticos controlados e bases de dados do mundo real com *drifts* temporais naturais (domínios financeiro, sensores e telecomunicações).
* **Modelos monitorados:** Modelos clássicos de aprendizado (XGBoost, Random Forest, Regressão Logística).
* **Métricas de avaliação:** Atraso na detecção (*Detection Delay/Latency*), Taxa de Falsos Positivos (alarmes falsos de drift), Taxa de Falsos Negativos, Custo Computacional de Ingestão e F1-Score do modelo principal pós-retreinamento.

---

## 5. Principais resultados
* **Resultado 1 (Superioridade de Métodos Multivariados):** Métodos baseados em *Domain Classifiers* (treinamento de um classificador leve para distinguir dados históricos de treino de dados recentes de produção) apresentaram a melhor sensibilidade para detectar desvios complexos e correlações espúrias que afetam múltiplas variáveis em conjunto.
* **Resultado 2 (Inadequação de Testes Univariados Isolados):** Testes como Kolmogorov-Smirnov falham sistematicamente em identificar *drifts* que ocorrem na covariância entre atributos, gerando uma falsa sensação de estabilidade.
* **Resultado 3 (A Relevância do Janelamento de Dados):** O dimensionamento da janela deslizante na camada de ingestão de dados é crítico: janelas muito curtas aumentam falsos alarmes por ruído sazonal; janelas longas atrasam a mitigação do desvio.
* **Importância para o TCC:** Demonstra empiricamente que a Engenharia de Dados é indispensável não apenas na construção do dataset de treino, mas na governança e monitoramento contínuo dos dados em produção para assegurar a generalização e confiabilidade do modelo.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL**
* **Justificativa:** Fornece o elo fundamental entre Engenharia de Dados, *Data Drift*, Generalização e Confiabilidade de Sistemas de Machine Learning em produção, consolidando a narrativa do ciclo de vida dos dados.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para fundamentar a qualidade dos dados sob a perspectiva de atualidade e estabilidade distribucional, além de discutir pipelines de MLOps.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para conceituar *Data Drift* e explicar como a perda de representatividade ao longo do tempo corrompe a generalização.
* **Capítulo 6 (Considerações Finais):** Para apontar o monitoramento contínuo de dados como requisito de engenharia para sistemas de IA confiáveis.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 15):** *"A suposição estatística fundamental de que os dados de teste e produção seguem a mesma distribuição dos dados de treinamento (i.i.d.) é frequentemente violada em ambientes reais, resultando em uma degradação silenciosa do desempenho dos modelos."*  
  * *Uso no TCC:* Desmistificar a ideia de que um modelo avaliado em bancada mantém sua precisão indefinidamente no mundo real.
* **Trecho 2 (p. 42):** *"Detectar o desvio nos dados de entrada antes que ele se traduza em predições incorretas e prejuízos operacionais constitui um requisito de confiabilidade que depende diretamente da infraestrutura de engenharia de dados."*  
  * *Uso no TCC:* Provar que a confiabilidade do sistema de ML é viabilizada pela infraestrutura de Engenharia de Dados.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho de ML: **Sim** (qualidade temporal e ausência de drift).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (dados novos incompatíveis com a distribuição treinada).
3. A preparação dos dados influencia o treinamento: **Sim** (necessidade de reprocessamento e retreinamento disparados por drift).
4. A representatividade dos dados influencia a generalização: **Sim** (o modelo falha quando a base histórica perde a representatividade do presente).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (drift induz novos vieses de predição).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (padrões aprendidos tornam-se espúrios após o drift).
7. Um bom desempenho na avaliação não garante boa generalização contínua: **Sim** (tese central da dissertação).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (confiabilidade em produção).
9. Processos de Engenharia de Dados melhoram a qualidade: **Sim** (arquitetura de monitoramento contínuo).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (degradação silenciosa sem rótulos imediatos).

---

## 10. Limitações
* **Declaradas pelo autor:** Custo de memória e latência ao processar fluxos de dados de altíssima escala com detectores baseados em classificadores complexos.
* **Para o TCC:** Foco na fase de produção e pós-implantação (*monitoring*), devendo ser articulado com a etapa inicial de coleta e limpeza de dados.

---

## 11. Lacunas e oportunidades
* Como integrar a detecção de *Data Drift* com mecanismos automáticos de auditoria de viés demográfico emergente na esteira de dados.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Foca na estabilidade distribucional, consistência temporal e atualidade. |
| Preparação dos dados | Sim | Pipelines de ingestão em lote/streaming e janelamento amostral. |
| Engenharia de Dados | Sim | Proposta de arquitetura de dados e esteira de MLOps. |
| Viés | Parcialmente | Viés de amostragem decorrente de mudanças temporais. |
| Representatividade | Sim | Perda gradual da representatividade do conjunto de treino histórico. |
| Generalização | Sim | Degradação de desempenho fora da distribuição original (*out-of-distribution*). |
| Confiabilidade | Sim | Manutenção da confiabilidade contínua do sistema inteligente em produção. |
| Machine Learning | Sim | Modelos de classificação clássica e modelos auxiliares de detecção de drift. |

---

## 13. Ficha de leitura final
* **Referência:** ROCHA, L. H. *Mitigating Drift in Machine Learning Systems through Continuous Input Monitoring: An Architectural Proposal and Empirical Evaluation of Detection Methods*. 2026. 98 f. Dissertação (Mestrado em Ciência da Computação) – Instituto de Matemática e Estatística, Universidade de São Paulo, São Paulo, 2026.
* **Problema:** Degradação silenciosa de modelos de ML em produção provocada por Data Drift sem rótulos imediatos.
* **Objetivo:** Propor e avaliar uma arquitetura de monitoramento contínuo não supervisionado de dados de entrada.
* **Metodologia:** Desenvolvimento de arquitetura de sistemas e experimentação quantitativa comparativa de detectores.
* **Principais resultados:** Classificadores de domínio e erro de reconstrução de PCA detectam drifts multivariados com alta sensibilidade.
* **Conceitos-chave:** Data Drift, Input Monitoring, MLOps, Engenharia de Dados, Confiabilidade, Domain Classifier.
* **Contribuição para o TCC:** Sustenta formalmente os temas de Data Drift, Engenharia de Dados e Confiabilidade de Sistemas.
* **Capítulo provável:** Capítulo 2, Capítulo 4 e Capítulo 6.
* **Citação mais importante:** *"A suposição estatística fundamental de que os dados de teste e produção seguem a mesma distribuição dos dados de treinamento (i.i.d.) é frequentemente violada em ambientes reais..."*
* **Palavras-chave:** Data Drift; MLOps; Engenharia de Dados; Confiabilidade; Monitoramento Contínuo.

---

## 14. Avaliação final
* **Nota:** 10 / 10
* **Justificativa:** Trabalho de altíssimo nível acadêmico da USP (2026), abordando diretamente a Engenharia de Dados como salvaguarda da confiabilidade de Machine Learning.
* **Decisão:** **SIM** (Permanecer entre as 20 referências principais).
