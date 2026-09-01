# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 01:** Barros & Melo (2025)  
**Arquivo Analisado:** 

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** IMPACTO DA QUALIDADE DE DADOS PÚBLICOS TABULARES NO DESEMPENHO DE MODELOS CLÁSSICOS DE MACHINE LEARNING
* **Autores:** Kawan Ribeiro Dias Barros; Mauro Jose Araujo de Melo
* **Ano:** 2025 (Edição: 30 de novembro de 2025)
* **Instituição/país:** Brasil (Instituição de afiliação não explicitada no cabeçalho; registro nacional)
* **Revista, congresso, repositório ou evento:** *RevistaFT* (Revista Científica de Alto Impacto - ISSN 1678-0817)
* **Volume, número e páginas:** Volume 29, Edição 152/NOV 2025, 25 páginas (versão impressa/PDF)
* **DOI:** 
* **URL:** 
* **Tipo de publicação:** Artigo científico em periódico
* **Idioma:** Português
* **Tipo de pesquisa:** Estudo analítico-dedutivo com modelagem matemática formal e análise computacional comparativa.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A baixa qualidade de dados tabulares públicos abertos, caracterizada especialmente pela alta recorrência de valores ausentes (*missing values*), e a prática disseminada e acrítica de aplicar métodos simplistas de imputação determinística (média e mediana) sem compreender as deformações matemáticas que essas substituições impõem às funções de custo e aos estimadores de algoritmos clássicos de Machine Learning.
* **Pergunta de pesquisa:** Como a imputação univariada por média e mediana altera analiticamente as propriedades estatísticas dos dados (variância e covariância) e de que maneira essa distorção se propaga para as funções de perda, convergência de coeficientes, cálculo de distâncias métricas e particionamento de nós em algoritmos de Regressão Linear, Regressão Logística, KNN e Árvores de Decisão?
* **Objetivo principal:** Realizar uma análise teórica e matematicamente fundamentada acerca do impacto de dois métodos de imputação (média e mediana) nas propriedades estatísticas dos atributos e no comportamento interno das funções de quatro famílias de modelos clássicos de Machine Learning.
* **Hipóteses ou questões específicas:** A imputação por média reduz a variância amostral e atenua as covariâncias com o alvo $, enviesando os estimadores OLS/MLE para zero ($\beta \rightarrow 0$), distorcendo a métrica euclidiana no KNN e criando divisões artificiais com impureza zero em Árvores de Decisão.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Quantitativa, dedutiva e formal-matemática.
* **Tipo de estudo:** Estudo analítico-teórico e experimental comparativo.
* **Fonte dos dados:** Dados tabulares públicos governamentais (estruturas tabulares abertas típicas de portais de transparência).
* **População/amostra:** Conjuntos de dados tabulares numéricos submetidos à indução de valores ausentes sob a hipótese MCAR (*Missing Completely at Random*).
* **Período analisado:** Não informado no artigo (foco na estrutura matemática atemporal).
* **Métodos de coleta:** Extração de repositórios de dados abertos governamentais.
* **Métodos de análise:** Demonstração analítica de esperança matemática, variância e covariância; análise do gradiente da função de perda e derivação dos parâmetros ótimos.
* **Modelos/algoritmos:** Regressão Linear (OLS), Regressão Logística (MLE via Newton-Raphson/Gradiente), K-Nearest Neighbors (KNN com distância euclidiana) e Árvores de Decisão (Critério de Gini e Entropia/Ganho de Informação).
* **Métricas:** Erro Quadrático Médio (MSE), Log-Loss/Cross-Entropy, distorção de variância ($\Delta \sigma^2$), viés paramétrico ($\operatorname{Bias}(\hat{\beta})$) e acurácia de classificação.
* **Procedimentos experimentais:** Avaliação dedutiva das equações de ajuste de cada modelo sob a matriz de dados original versus a matriz de dados imputada.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: Atenuação dos Coeficientes em Regressão Linear e Logística
* **O que foi encontrado:** A imputação pela média preserva o valor esperado $\mathbb{E}[X]$, mas reduz estritamente a variância amostral ^2$ e comprime a covariância amostral $\operatorname{Cov}(X,Y)$. Como o estimador de mínimos quadrados ordinários é $\hat{\beta}_1 = \frac{\operatorname{Cov}(X,Y)}{\operatorname{Var}(X)}$, a redução proporcional da covariância induz uma atenuação sistemática em direção a zero ($\hat{\beta}_1 \rightarrow 0$), enfraquecendo artificialmente o peso preditivo da variável.
* **Evidência:** Derivação algébrica formal das matrizes de variância-covariância e das equações normais ^{-1} X^T Y$.
* **Interpretação dos autores:** Os autores afirmam que a imputação por média atua como uma regularização espúria indesejada, subestimando o impacto real de variáveis importantes no fenômeno estudado.
* **Grau de evidência:** **Direto** (demonstração analítico-matemática).

### Resultado 2: Formação de Atratores Artificiais e Distorção Métrica no KNN
* **O que foi encontrado:** Em algoritmos baseados em instâncias (KNN), a substituição de valores faltantes por uma constante única ($\bar{x}$) projeta todas as instâncias incompletas para um hiperplano comum no espaço euclidiano $\mathbb{R}^d$, forçando instâncias que possuem perfis completamente diferentes a se tornarem artificialmente "vizinhas mais próximas".
* **Evidência:** Análise geométrica da distância euclidiana (p, q) = \sqrt{\sum (p_i - q_i)^2}$, onde a diferença ^2 = 0$ sempre que ambos os registros tiverem o valor imputado.
* **Interpretação dos autores:** Os autores destacam que a imputação determinística altera a topologia do espaço de busca, destruindo a premissa de similaridade local que fundamenta o KNN.
* **Grau de evidência:** **Direto**.

### Resultado 3: Particionamento Anômalo e Overfitting em Árvores de Decisão
* **O que foi encontrado:** A concentração massiva de instâncias com o valor idêntico da média cria um ponto de corte (*split threshold*) de alta densidade no cálculo do Ganho de Informação, levando a árvore a ramificar nós com base em um artefato estatístico do pré-processamento.
* **Evidência:** Equações de cálculo da impureza de Gini (p) = 1 - \sum p_i^2$ aplicadas a distribuições com massa pontual artificial.
* **Interpretação dos autores:** A imputação cria ilusões de pureza em subconjuntos artificiais, gerando sobreajuste (*overfitting*) nos dados de treino.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* Os autores concluem que métodos ingênuos e convenientes de pré-processamento (como imputação por média e mediana) não são neutros e alteram fundamentalmente a matemática e o comportamento dos modelos de Machine Learning.
* **Afirmações fortes:** A imputação univariada distorce a covariância e atua como uma força de atenuação paramétrica em modelos lineares; no KNN, ela falseia o cálculo de distâncias métricas.
* **Afirmações condicionadas ao contexto:** O grau do impacto negativo é diretamente proporcional à porcentagem de valores faltantes na base e à sensibilidade de cada família algorítmica.
* **Hipóteses / Possibilidades:** Os autores recomendam a adoção de técnicas multivariadas (como MICE ou imputação baseada em árvores) como alternativa necessária para bases públicas complexas.

---

# 6. CONCEITOS IMPORTANTES
* **Qualidade de Dados (Completude):**
  * *Como define/utiliza:* Ausência de valores nulos; apontada como a dimensão mais frequentemente violada em dados públicos tabulares.
  * *Localização:* Seção 1 (Introdução) e Resumo.
  * *Importância:* É o ponto de partida do estudo.
* **Imputação de Dados:**
  * *Como define/utiliza:* Processo de substituição de dados faltantes por estimativas estatísticas pontuais ($\bar{x}$ ou $\tilde{x}$).
  * *Localização:* Seção 2 (Fundamentação Teórica).
  * *Importância:* Objeto central da análise matemática.
* **Fronteira de Decisão / Espaço de Atributos:**
  * *Como define/utiliza:* Geometria do espaço $\mathbb{R}^d$ onde os classificadores traçam hiperplanos ou particionam regiões.
  * *Localização:* Seções 3 e 4 (Análise de KNN e Árvores).
  * *Importância:* Explica como a geometria dos dados é corrompida.
* **Machine Learning Clássico:**
  * *Como define/utiliza:* Conjunto de algoritmos supervisionados paramétricos e não paramétricos (Regressão, KNN, Árvores).
  * *Localização:* Ao longo de todo o texto.
  * *Importância:* Alvo do estudo de impacto.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* Foco restrito a métodos determinísticos univariados simples (média e mediana).
* Análise fundamentada primordialmente no mecanismo de perda MCAR (*Missing Completely at Random*), sem modelar ausências informativas (MNAR - *Missing Not at Random*).
* Não inclusão de modelos profundos (*Deep Learning*).

### Limitações observáveis (Interpretação da análise)
* O artigo é eminentemente teórico-dedutivo; embora forneça equações rigorosas, não apresenta gráficos comparativos de curvas ROC em múltiplos benchmarks públicos empíricos reais com código aberto reproduzível.
* Não analisa o impacto temporal (Data Drift).

### Impacto das limitações
* Não invalida os resultados matemáticos (que são exatos), mas restringe sua aplicabilidade direta a dados estruturados tabulares pré-processados sob métodos univariados clássicos.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva importante:** A mediana demonstra ser ligeiramente mais robusta que a média na presença de *outliers* na base de dados, mas compartilha da mesma falha estrutural de reduzir a variância e destruir a correlação natural entre múltiplos atributos.
* **Resultado que desafia o senso comum:** A imputação por média, amplamente recomendada em tutoriais introdutórios de ciência de dados pela facilidade computacional, é matematicamente danosa para quase todas as famílias clássicas de algoritmos preditivos.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com rigor matemático formal o elo: **Dados Incompletos $\rightarrow$ Preparação/Tratamento (Imputação) $\rightarrow$ Treinamento $\rightarrow$ Degradação do Modelo**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que a perda de covariância afeta a generalização e a confiabilidade do sistema quando implantado em produção.

### 9.3 Qual parte ele não aborda?
* Não aborda viés social/demográfico (raça, gênero), não trata de *Data Drift* contínuo e não analisa vazamento de dados (*data leakage*).

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; reforça que a Engenharia de Dados não pode adotar automações simplórias de limpeza de dados sob pena de corromper a base do aprendizado de máquina.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Demonstra que dados com missing values alteram diretamente as funções de perda. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | A violação da completude degrada coeficientes $\beta$ e distâncias métricas. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | A escolha do método de imputação altera a convergência e os splits das árvores. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A substituição por constantes elimina a dispersão representativa da amostra. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Foca no viés estatístico de atenuação paramétrica induzido pela média. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Demonstra formação de clusters espúrios no KNN e splits falsos em árvores. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | O modelo sobreajusta nos nós criados pela massa pontual da média. | **PARCIAL** |
| Mudanças na distribuição podem afetar o modelo | Não aborda drift temporal explicitamente. | **NÃO ABORDADO** |
| Qualidade dos dados influencia confiabilidade | Modelos com pesos atenuados tornam-se não confiáveis para predições críticas. | **PARCIAL** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Recomenda métodos robustos de preparação de dados em vez de univariados. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta:** Não aprofundada (dados já coletados de portais públicos).
* **Armazenamento / Integração:** Não abordados.
* **Limpeza e Transformação:** **Foco total do artigo** (análise matemática da imputação de valores ausentes).
* **Qualidade:** Foco estrito na dimensão de **completude**.
* **Validação / Preparação para Treinamento:** Detalha como a matriz $ transformada é entregue ao otimizador do modelo.
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **PARCIAL** — O artigo concentra-se na fase de *Data Cleaning* / *Data Preparation* (Pré-processamento), que é uma etapa vital da Engenharia de Dados, mas não aborda infraestrutura, pipelines distribuídos, streaming ou governança.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"A imputação de valores ausentes pela média amostral, embora preserve a esperança matemática da variável, acarreta uma redução espúria da variância amostral e atenua a covariância entre as variáveis preditoras e o target."*  
  * *Localização:* p. 2 (Introdução/Resumo).  
  * *Tipo:* Resultado / Definição matemática.  
  * *Uso no TCC:* Fundamentar no Capítulo 2 e 3 o impacto estatístico negativo do pré-processamento inadequado.
* **Trecho 2:** *"Em algoritmos baseados em instâncias como o KNN, a substituição indiscriminada de dados ausentes por uma constante atua como um atrator métrico no espaço euclidiano, distorcendo o cálculo dos k vizinhos mais próximos."*  
  * *Localização:* p. 6 (Seção KNN).  
  * *Tipo:* Resultado / Análise geométrica.  
  * *Uso no TCC:* Ilustrar no Capítulo 3 como a preparação de dados afeta a topologia dos algoritmos baseados em distância.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* O artigo desenvolve deduções matemáticas a partir de formulações clássicas da literatura de econometria e aprendizado estatístico (Hastie, Tibshirani & Friedman; Little & Rubin sobre análise estatística com dados faltantes).
* *Uso:* Conectar a literatura de *Missing Data Analysis* (Little & Rubin) ao pipeline de Engenharia de Dados no TCC.

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL**
* **Justificativa:** É um dos raros trabalhos nacionais recentes (2025) que disseca algebricamente o impacto exato do tratamento de dados (Engenharia de Dados) nas entranhas funcionais dos algoritmos de ML.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Seção sobre Completude e Métodos de Imputação de Missing Values.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Seção sobre o impacto da matriz de dados nas funções de custo de Regressão, KNN e Árvores.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** BARROS, K. R. D.; MELO, M. J. A. Impacto da Qualidade de Dados Públicos Tabulares no Desempenho de Modelos Clássicos de Machine Learning. *RevistaFT*, v. 29, ed. 152, 2025. DOI: 10.69849/revistaft/ra10202511300622.
* **Problema:** Efeito matemático da imputação univariada de missing values sobre modelos de ML.
* **Objetivo:** Analisar teoricamente a distorção induzida por média/mediana em 4 algoritmos clássicos.
* **Metodologia:** Estudo analítico-dedutivo com modelagem matemática formal.
* **Principais resultados:** Imputação univariada comprime variância, atenua parâmetros $\beta$ para zero, atrai falsos vizinhos no KNN e induz splits artificiais em Árvores.
* **Principais conceitos:** Qualidade de Dados, Completude, Missing Values, Imputação, Redução de Variância, KNN, Decision Trees.
* **Conclusões dos autores:** O pré-processamento ingênuo de dados altera as propriedades do modelo e prejudica sua capacidade preditiva real.
* **Limitações:** Focado em métodos univariados e dados tabulares MCAR.
* **Contradições/ressalvas:** A imputação por média preserva a esperança, mas destrói a estrutura de covariância.
* **Contribuição para o TCC:** Prova formal da relação direta entre Tratamento de Dados e Treinamento de ML.
* **Capítulo provável:** Capítulo 2 e Capítulo 3.
* **Citação principal:** *"A imputação de valores ausentes pela média amostral [...] acarreta uma redução espúria da variância amostral e atenua a covariância..."*
* **Palavras-chave:** Qualidade de Dados; Machine Learning; Imputação; Dados Tabulares; Pré-processamento.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 9.0 / 10 |
| Relevância para Engenharia de Dados | 8.5 / 10 |
| Relevância para Qualidade de Dados | 9.5 / 10 |
| Relevância para Machine Learning | 9.5 / 10 |
| Relevância para Viés/Generalização | 8.0 / 10 |
| Atualidade | 10 / 10 |
* **Avaliação global:** 9.2 / 10 — Artigo de altíssima relevância técnica e analítica para o núcleo duro do TCC.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** Fornece a justificativa matemática indispensável para sustentar que a preparação de dados altera os estimadores e as fronteiras de decisão dos algoritmos de Machine Learning.
* **Função única:** Provar algebricamente a distorção dos parâmetros $\beta$ e da métrica do KNN provocada pela imputação simplista.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A atenuação dos estimadores OLS/MLE, a atração artificial de vizinhos no KNN e a redução da variância amostral após imputação determinística.
* **O que é interpretação:** A extrapolação de que tais distorções invalidam por completo o uso desses modelos em sistemas de larga escala em produção (os autores tratam do aspecto matemático, cabendo à engenharia avaliar o impacto em negócio).
* **O que não podemos afirmar com base neste artigo:** Não se pode afirmar quais métricas numéricas exatas ocorreriam em datasets não tabulares (imagens/texto) ou em redes neurais profundas.
