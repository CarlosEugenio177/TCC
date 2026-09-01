# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Impacto da Qualidade de Dados Públicos Tabulares no Desempenho de Modelos Clássicos de Machine Learning
* **Autores:** Kawan Ribeiro Dias Barros; Mauro José Araújo de Melo
* **Ano:** 2025 (Publicado em 30/11/2025)
* **Instituição/País:** Brasil
* **Local de publicação:** *RevistaFT*, Engenhiarias, Volume 29, Edição 152
* **DOI / Link:**  (ISSN: 1678-0817) | [Link na RevistaFT](https://revistaft.com.br/impacto-da-qualidade-de-dados-publicos-tabulares-no-desempenho-de-modelos-classicos-de-machine-learning/)
* **Tipo de publicação:** Artigo científico em periódico
* **Tipo de pesquisa/metodologia:** Estudo analítico-quantitativo e experimental com modelagem matemática dedutiva.

---

## 2. Objetivo do artigo
* **Problema investigado:** A ocorrência recorrente de valores ausentes (*missing values*) em bases públicas tabulares e a prática disseminada de aplicar métodos ingênuos e univariados de imputação (média e mediana), sem avaliar o impacto matemático dessas transformações sobre as funções de perda e parâmetros dos modelos de Machine Learning.
* **Objetivo principal:** Analisar de forma matematicamente fundamentada e empírica o impacto da imputação por média e mediana no comportamento interno e no desempenho de quatro famílias de algoritmos clássicos: Regressão Linear, Regressão Logística, *K-Nearest Neighbors* (KNN) e Árvores de Decisão.
* **Pergunta/Hipótese:** De que maneira a redução artificial da variância amostral e a atenuação das covariâncias induzidas pela imputação univariada afetam a convergência dos estimadores, o cálculo de distâncias euclidianas e o particionamento de nós nos modelos de AM?

---

## 3. Principais conceitos
* **Qualidade de Dados (Completude):** O artigo aborda a completude como a ausência de registros nulos, apontando que dados públicos frequentemente apresentam altos índices de incompletude decorrentes de falhas de coleta e consolidação.
* **Imputação Univariada (Média vs. Mediana):** Métodos determinísticos que substituem valores faltantes pelo primeiro momento amostral ou pela mediana; o artigo demonstra analiticamente que, enquanto a esperança é preservada, a variância $\sigma^2$ é comprimida e as covariâncias $\operatorname{Cov}(X_j, X_k)$ e $\operatorname{Cov}(X_j, Y)$ são artificialmente atenuadas.
* **Métrica de Distância no Espaço de Atributos (KNN):** O artigo demonstra que a imputação de uma constante fixa faz com que registros com valores ausentes convirjam para um mesmo ponto no espaço vetorial $\mathbb{R}^d$, funcionando como atratores espúrios de vizinhança.
* **Critérios de Impureza e Particionamento (Árvores de Decisão):** Avaliação de como o acúmulo de valores idênticos distorce o cálculo do Ganho de Informação e do Índice de Gini, gerando ramos excessivamente profundos ou divisões enviesadas.

---

## 4. Metodologia
* **Abordagem:** Dedutiva-matemática e experimental-quantitativa.
* **Fonte dos dados:** Conjuntos de dados tabulares abertos de portais governamentais.
* **Modelos avaliados:** Regressão Linear Simples/Múltipla (Mínimos Quadrados Ordinários - OLS), Regressão Logística (Máxima Verossimilhança - MLE), K-Nearest Neighbors (KNN com distância euclidiana) e Árvores de Decisão (Critério de Gini/Entropia).
* **Métricas utilizadas:** Erro Quadrático Médio (MSE), Log-Loss, Acurácia, Sensibilidade a Outliers e Variância Residual.
* **Procedimentos experimentais:** Indução de percentuais graduais de valores faltantes (MCAR) em variáveis numéricas e avaliação da distorção paramétrica e preditiva após imputação.

---

## 5. Principais resultados
* **Resultado 1 (Regressões Paramétricas):** A imputação por média provoca o fenômeno de atenuação dos coeficientes de regressão ($eta ightarrow 0$), subestimando o impacto real das variáveis explicativas sobre a variável dependente devido à perda de covariância real.
* **Resultado 2 (Modelos Baseados em Distância - KNN):** Ocorre a criação de agrupamentos (*clusters*) artificiais no hiperespaço de atributos; instâncias distintas passam a ser consideradas vizinhas apenas porque compartilhavam valores faltantes imputados pela média, degradando a precisão do KNN.
* **Resultado 3 (Modelos Não Paramétricos - Árvores):** As árvores de decisão criam *splits* anômalos com alta pureza artificial em torno do valor imputado, elevando o risco de sobreajuste (*overfitting*) local.
* **Importância para o TCC:** Prova formalmente que decisões operacionais de Engenharia de Dados na fase de pré-processamento afetam diretamente os alicerces matemáticos do treinamento dos modelos de Machine Learning.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL**
* **Justificativa:** Conecta diretamente as práticas de pré-processamento de Engenharia de Dados (imputação de dados) à geometria e parametrização dos modelos de Machine Learning, ilustrando o elo direto entre Qualidade de Dados $ightarrow$ Tratamento $ightarrow$ Treinamento.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para discutir a dimensão de completude e a teoria matemática por trás das técnicas de imputação de missing values.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para explicar como os algoritmos de regressão, árvores e KNN reagem internamente a matrizes de atributos alteradas pelo pré-processamento.
* **Capítulo 5 (Análise da Literatura):** Como evidência empírica nacional recente demonstrando a dependência algorítmica da qualidade do saneamento de dados.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 2):** *"A imputação de valores ausentes pela média amostral, embora preserve a esperança matemática da variável, acarreta uma redução espúria da variância amostral e atenua a covariância entre as variáveis preditoras e o target."*  
  * *Uso no TCC:* Fundamentar por que métodos simplistas de engenharia de dados distorcem a distribuição estatística da base.
* **Trecho 2 (p. 6):** *"Em algoritmos baseados em instâncias como o KNN, a substituição indiscriminada de dados ausentes por uma constante atua como um atrator métrico no espaço euclidiano, distorcendo o cálculo dos k vizinhos mais próximos."*  
  * *Uso no TCC:* Demonstrar que o tratamento de dados tem implicações geométricas diretas na fronteira de decisão do modelo.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho de ML: **Sim** (demonstrado analiticamente).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (coeficientes subestimados e árvores sobreajustadas).
3. A preparação dos dados influencia o treinamento: **Sim** (foco primordial do artigo).
4. A representatividade dos dados influencia a generalização: **Sim** (a base imputada deixa de representar a dispersão real).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (viés de estimação introduzido pela imputação).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (clusters artificiais ao redor do valor médio).
7. Um bom desempenho na avaliação não garante boa generalização: **Sim** (o modelo se ajusta ao artefato da média).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (modelos instáveis para tomada de decisão pública).
9. Processos de Engenharia de Dados melhoram a qualidade dos dados: **Sim** (defende pipelines de imputação multivariada mais robustos).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (o algoritmo converge sem gerar erro de execução, mas com pesos viciados).

---

## 10. Limitações
* **Declaradas pelos autores:** Focou exclusivamente em métodos de imputação univariados determinísticos (média e mediana) sob o mecanismo de ausência MCAR (*Missing Completely at Random*), não abrangendo métodos múltiplos (MICE) ou algoritmos profundos (*Deep Learning*).
* **Para o TCC:** Aplica-se especificamente a dados tabulares estruturados.

---

## 11. Lacunas e oportunidades
* O trabalho não analisa o impacto de vazamento de dados (*data leakage*) quando a média do dataset completo é calculada antes do particionamento entre treino e teste, aspecto relevante que seu TCC pode complementar teoricamente.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Foca na completude de dados tabulares públicos. |
| Preparação dos dados | Sim | Analisa detalhadamente métodos de imputação por média e mediana. |
| Engenharia de Dados | Sim | Posiciona o saneamento de dados como condicionante do modelo. |
| Viés | Sim | Aborda o viés estatístico de atenuação paramétrica. |
| Representatividade | Sim | Distorção da densidade amostral no espaço $\mathbb{R}^d$. |
| Generalização | Sim | Queda na performance quando o modelo opera em dados reais. |
| Confiabilidade | Sim | Inviabilidade de uso de modelos com estimadores distorcidos. |
| Machine Learning | Sim | Avaliação formal em Regressões, KNN e Árvores de Decisão. |

---

## 13. Ficha de leitura final
* **Referência:** BARROS, K. R. D.; MELO, M. J. A. Impacto da Qualidade de Dados Públicos Tabulares no Desempenho de Modelos Clássicos de Machine Learning. *RevistaFT*, v. 29, ed. 152, 2025.
* **Problema:** Impacto da imputação ingênua de missing values na matemática dos modelos de ML.
* **Objetivo:** Demonstrar formalmente a distorção paramétrica e geométrica em 4 algoritmos clássicos.
* **Metodologia:** Análise dedutiva matemática associada a testes empíricos controlados.
* **Principais resultados:** Imputação univariada reduz variância, atenua coeficientes $eta$ e distorce distâncias métricas no KNN.
* **Conceitos-chave:** Qualidade de Dados, Missing Values, Imputação, Redução de Variância, KNN, Árvores de Decisão.
* **Contribuição para o TCC:** Fornece sustentação matemática sólida para o capítulo de Pré-processamento e Qualidade.
* **Capítulo provável:** Capítulo 2 e Capítulo 3.
* **Citação mais importante:** *"A imputação de valores ausentes pela média amostral [...] acarreta uma redução espúria da variância amostral e atenua a covariância..."*
* **Palavras-chave:** Qualidade de Dados; Machine Learning; Imputação; Dados Tabulares.

---

## 14. Avaliação final
* **Nota:** 9.5 / 10
* **Justificativa:** Excelente aderência ao tema central do TCC, fornecendo a ponte analítica rigorosa entre a manipulação de dados na Engenharia de Dados e a convergência matemática de modelos de ML.
* **Decisão:** **SIM** (Permanecer entre as 20 referências principais).
