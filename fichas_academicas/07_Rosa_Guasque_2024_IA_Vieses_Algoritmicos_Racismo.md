# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 07:** Rosa & Guasque (2024)  
**Arquivo Analisado:** `v23n50a49_stamped.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** INTELIGÊNCIA ARTIFICIAL, VIESES ALGORÍTMICOS E RACISMO: O LADO DESCONHECIDO DA JUSTIÇA ALGORÍTMICA
* **Autores:** Alexandre Morais da Rosa; Bárbara Guasque
* **Ano:** 2024 (Recebido: 10/01/2022 • Aprovado: 06/07/2023 • Publicado: Jul./Dez. 2024)
* **Instituição/país:** Universidade do Vale do Itajaí (UNIVALI, Itajaí - SC), Brasil.
* **Revista, congresso, repositório ou evento:** *Opinión Jurídica* (Universidad de Medellín, Colômbia), v. 23, n. 50, a49.
* **Volume, número e páginas:** Volume 23, Número 50, artigo a49, p. 1-23 (23 páginas).
* **DOI:** `10.22395/ojum.v23n50a49` (ISSN online: 2248-4078)
* **URL:** `https://revistas.udem.edu.co/index.php/opinion/article/view/a49`
* **Tipo de publicação:** Artigo científico em periódico internacional indexado.
* **Idioma:** Português (com resumo em espanhol e inglês)
* **Tipo de pesquisa:** Pesquisa exploratória e descritiva com procedimento técnico bibliográfico e documental e análise de estudos de caso.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** As externalidades negativas e os danos a direitos fundamentais decorrentes do uso acrítico de modelos de Inteligência Artificial e algoritmos de predição de risco no sistema de justiça criminal e segurança pública, cujos dados de treinamento incorporam o racismo estrutural e distorções históricas de amostragem policial, perpetuando e aprofundando preconceitos sob uma falsa aparência de neutralidade matemática.
* **Pergunta de pesquisa:** De que maneira a ausência de rigor técnico, transparência e controle sobre os dados de entrada na construção de modelos de IA no judiciário gera racismo algorítmico, e quais medidas de governança de dados podem mitigar essas consequências danosas?
* **Objetivo principal:** Identificar as consequências negativas da não observância de padrões éticos em modelos de IA, esclarecer a importância de se voltar rigorosa atenção aos dados utilizados na construção dos modelos e elencar possíveis soluções de governança para reduzir algoritmos enviesados.
* **Hipóteses ou questões específicas:** Os algoritmos atuam como catalisadores de preconceitos presentes na sociedade quando treinados com históricos punitivos viciados; a métrica de acurácia média mascara disparidades brutais de taxas de falso positivo entre grupos raciais.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa, crítica, analítica e interdisciplinar (Direito e Ciência da Computação).
* **Tipo de estudo:** Pesquisa exploratório-descritiva com análise de casos práticos paradigmáticos e levantamento bibliográfico/normativo.
* **Fonte dos dados:** Relatórios de auditoria algorítmica internacionais (investigação da ProPublica sobre o COMPAS), relatórios do Conselho Nacional de Justiça (CNJ), casos reais de prisões ilegais por reconhecimento facial no Brasil e doutrina especializada.
* **População/amostra:** Casos de aplicação de escores de risco de reincidência criminal e câmeras de reconhecimento facial na segurança pública.
* **Período analisado:** Casos e dados documentados entre 2016 e 2024.
* **Métodos de coleta:** Pesquisa bibliográfica e levantamento documental de relatórios técnicos.
* **Métodos de análise:** Análise de impacto ético-jurídico, decomposição das taxas de erro algorítmico (Erros Tipo I vs. Tipo II) e estudo de ciclos de retroalimentação (*feedback loops*).
* **Modelos/algoritmos analisados:** Algoritmo COMPAS (*Northpointe*), sistemas de reconhecimento facial policial e modelos de triagem judiciária.
* **Métricas:** Taxas de Falso Positivo (FP), Taxas de Falso Negativo (FN), disparidade de impacto e acurácia balanceada por grupo racial.
* **Procedimentos experimentais:** Análise documental dos resultados estatísticos da auditoria ProPublica.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Assimetria Estrutural nas Taxas de Falso Positivo (Caso COMPAS)
* **O que foi encontrado:** O modelo COMPAS, amplamente utilizado em cortes norte-americanas, atribuiu uma taxa de falsos positivos de reincidência quase duas vezes maior para réus negros (44,9%) em comparação a réus brancos (23,5%), enquanto réus brancos foram classificados erroneamente como baixo risco com frequência muito maior (47,7% vs. 28,0% em negros).
* **Evidência:** Dados auditados da base de 7.000 réus do Condado de Broward (Flórida).
* **Interpretação dos autores:** Os autores destacam que, embora o modelo apresentasse a mesma acurácia global aparente para ambos os grupos, o custo do erro foi distribuído de forma racista devido aos dados de treino carregados de seletividade penal.
* **Grau de evidência:** **Direto** (evidência documental de auditoria empírica consolidada).

### Resultado 2: O Ciclo de Retroalimentação Viciada (*Feedback Loops*)
* **O que foi encontrado:** Algoritmos preditivos de policiamento alimentados com históricos de prisões direcionam viaturas preferencialmente para bairros periféricos; essa concentração gera mais flagrantes nesses locais, alimentando o banco de dados com mais registros daquela mesma população e criando uma profecia autorrealizável.
* **Evidência:** Análise causal dos dados de segurança pública e policiamento preditivo.
* **Interpretação dos autores:** Os dados de treino não refletem a taxa real de crimes da sociedade, mas a taxa de vigilância policial histórica.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Desmistificação da Neutralidade Matemática
* **O que foi encontrado:** A crença acrítica de que códigos e equações são neutros mascara as premissas enviesadas embutidas na seleção dos atributos e nos dados de treino.
* **Evidência:** Estudo da opacidade (*black-box*) e segredo comercial de empresas fornecedoras de software para o Estado.
* **Interpretação dos autores:** A autoridade conferida aos números legitima decisões injustas sem permitir a ampla defesa dos cidadãos afetados.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* Os autores concluem que os algoritmos enviesados produzem consequências sociais nefastas, violando direitos fundamentais e atuando como catalisadores que perpetuam preconceitos históricos.
* **Afirmações fortes:** Não existe neutralidade em modelos alimentados por dados humanos; a atenção rigorosa à origem e qualidade dos dados é o único meio de evitar que a IA se torne um instrumento de amplificação do racismo.
* **Afirmações condicionadas ao contexto:** O impacto danoso é maximizado em aplicações de alto risco (justiça penal, segurança pública e concessão de direitos fundamentais).
* **Hipóteses / Possibilidades:** Defendem a implementação obrigatória de auditorias algorítmicas independentes, governança de dados estrita e transparência explicável (*Explainable AI*) no setor público.

---

# 6. CONCEITOS IMPORTANTES
* **Justiça Algorítmica e Falsa Neutralidade:**
  * *Como define/utiliza:* Crença errônea de que sistemas matemáticos são imunes a preconceitos humanos.
  * *Localização:* p. 2 e p. 5.
  * *Importância:* Alvo da crítica teórica.
* **Racismo Algorítmico:**
  * *Como define/utiliza:* Operação de modelos que resulta em desvantagens desproporcionais e injustas contra pessoas negras.
  * *Localização:* p. 1 e p. 8.
  * *Importância:* Tema central do estudo.
* **Dados Viciados de Treinamento (*Biased Data*):**
  * *Como define/utiliza:* Conjunto de dados históricos que refletem a seletividade e as falhas do sistema de justiça do passado.
  * *Localização:* p. 6 e p. 10.
  * *Importância:* Causa raiz identificada.
* **Caso COMPAS:**
  * *Como define/utiliza:* Estudo de caso empírico de modelo de risco com disparidade de erros tipo I.
  * *Localização:* p. 7-9.
  * *Importância:* Prova empírica documental.
* **Feedback Loop:**
  * *Como define/utiliza:* Mecanismo de retroalimentação cumulativa que amplia a distorção da base a cada nova predição.
  * *Localização:* p. 12.
  * *Importância:* Conceito de dinâmica de sistemas de dados.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* Foco delimitado ao sistema de justiça criminal, segurança pública e violações de direitos humanos fundamentais.
* Abordagem orientada pela dogmática jurídica e análise crítica interdisciplinar.

### Limitações observáveis (Interpretação da análise)
* O trabalho não desenvolve novos códigos-fonte, pipelines em Python ou demonstrações matemáticas de funções de perda, concentrando-se na análise qualitativa dos relatórios de auditoria e casos documentados.

### Impacto das limitações
* Não reduz sua utilidade para o TCC, pois sua finalidade é justamente embasar a criticidade do problema de pesquisa, a justificativa ética e o impacto real do viés nos dados.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva matemática fundamental:** O caso COMPAS demonstrou que é matematicamente impossível satisfazer simultaneamente múltiplos critérios de equidade (*equalized odds* vs. *predictive parity*) quando as taxas básicas de prevalência nos dados históricos são diferentes, provando que o problema não pode ser resolvido apenas por algoritmos sem intervenção na base de dados.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com contundência os elos: **Dados Históricos Viciados $\rightarrow$ Viés $\rightarrow$ Falsa Acurácia de Teste $\rightarrow$ Falha Grave de Confiabilidade e Justiça**.

### 9.2 Qual parte ele apenas sugere?
* Sugere a necessidade de auditorias de Engenharia de Software antes da homologação de sistemas de IA.

### 9.3 Qual parte ele não aborda?
* Não aborda métodos de imputação numérica de missing values nem algoritmos de otimização matemática.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; reforça categoricamente que alta acurácia média não é sinônimo de confiabilidade e que dados viciados produzem modelos perigosos.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Registros policiais passados determinam diretamente os escores de risco. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | A ausência de representatividade justa corrompe a predição. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | A falta de auditoria na base permite a propagação do viés. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A super-representação de negros em registros penais induz falsos positivos. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Foco total: racismo estrutural nos dados vira racismo algorítmico. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Associação indevida entre cor da pele/localização e periculosidade. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | O COMPAS tinha alta acurácia geral, mas errava o dobro em negros. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Trata da defasagem histórica e dos ciclos cumulativos viciados. | **PARCIAL** |
| Qualidade dos dados influencia confiabilidade | Sistemas que violam direitos fundamentais possuem confiabilidade nula. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Exigência de curadoria, governança e auditoria de bases. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta e Seleção:** **SIM** (crítica à coleta enviesada de dados de segurança pública).
* **Armazenamento / Integração:** Não abordados diretamente.
* **Limpeza e Governança:** **SIM** (defesa de auditorias de dados independentes).
* **Qualidade:** Foco nas dimensões de **imparcialidade, veracidade e justiça distributiva**.
* **Monitoramento:** **SIM** (auditoria contínua de feedback loops).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **PARCIAL** — O artigo trata dos requisitos éticos, regulatórios e de governança de dados que devem guiar a Engenharia de Software e Engenharia de Dados, com foco no impacto social das bases de treinamento.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"A inteligência artificial não atua em um vácuo; ela é alimentada por dados que refletem as escolhas, preconceitos e injustiças históricas da sociedade em que foi gerada."*  
  * *Localização:* p. 3 (Introdução).  
  * *Tipo:* Premissa teórica fundamental.  
  * *Uso no TCC:* Introdução e Justificativa para contextualizar por que o modelo é refém dos dados.
* **Trecho 2:** *"A aparência de objetividade matemática dos algoritmos esconde o fato de que eles operam como reprodutores e amplificadores da seletividade penal inscrita em seus dados de treinamento."*  
  * *Localização:* p. 11 (Seção de Discussão).  
  * *Tipo:* Conclusão crítica.  
  * *Uso no TCC:* Desmistificar a fé cega em métricas de avaliação globais no Capítulo 4.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Angwin, J. et al. (2016):** *Machine Bias: There’s software used across the country to predict future criminals. And it’s biased against blacks*. (ProPublica - A investigação fundadora sobre o COMPAS).
* **Noble, S. U. (2018):** *Algorithms of Oppression: How search engines reinforce racism*. (Livro canônico sobre viés em algoritmos).
* **Benjamin, R. (2019):** *Race After Technology: Abolitionist Tools for the New Jim Code*. (Referência de impacto social).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **IMPORTANTE**
* **Justificativa:** Fornece a melhor fundamentação crítica, social e empírica documentada para o **Capítulo 4** sobre as consequências reais de modelos treinados com dados viciados.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** Para justificar a relevância acadêmica e social da qualidade dos dados.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Seção sobre Viés Algorítmico, Falsos Positivos Assimétricos e o Caso COMPAS.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** ROSA, A. M.; GUASQUE, B. Inteligência artificial, vieses algorítmicos e racismo: o lado desconhecido da justiça algorítmica. *Opinión Jurídica*, v. 23, n. 50, a49, p. 1-23, 2024. DOI: 10.22395/ojum.v23n50a49.
* **Problema:** Reprodução e amplificação de racismo estrutural por modelos de predição de risco no judiciário.
* **Objetivo:** Analisar os impactos negativos de dados enviesados e propor governança e auditoria de IA.
* **Metodologia:** Pesquisa bibliográfica exploratório-descritiva e análise documental do caso COMPAS.
* **Principais resultados:** O COMPAS errou o dobro em negros (FP = 44,9% vs. 23,5% em brancos); dados de policiamento geram ciclos de retroalimentação viciada (*feedback loops*).
* **Principais conceitos:** Racismo Algorítmico, Dados Viciados, COMPAS, Feedback Loop, Falsa Neutralidade Matemática, Confiabilidade.
* **Conclusões dos autores:** Algoritmos não são neutros; a qualidade dos dados de treino condiciona a justiça e a confiabilidade do sistema.
* **Limitações:** Abordagem voltada à justiça criminal e direitos fundamentais sem modelagem computacional direta.
* **Contradições/ressalvas:** A acurácia global uniforme mascara assimetrias graves na distribuição dos erros.
* **Contribuição para o TCC:** Estudo de caso clássico sobre a falácia da acurácia e o impacto real do viés nos dados.
* **Capítulo provável:** Capítulo 1 e Capítulo 4.
* **Citação principal:** *"A inteligência artificial não atua em um vácuo; ela é alimentada por dados que refletem as escolhas, preconceitos e injustiças históricas..."*
* **Palavras-chave:** Inteligência Artificial; Viés Algorítmico; Racismo Estrutural; COMPAS; Confiabilidade; Justiça Algorítmica.

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
| Atualidade | 10 / 10 (2024) |
* **Avaliação global:** 8.9 / 10 — Referência de altíssimo impacto para contextualização crítica de viés e confiabilidade.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É a publicação recente (2024) que melhor articula a literatura empírica do caso COMPAS e os ciclos de retroalimentação viciada em língua portuguesa.
* **Função única:** Fornecer o embasamento analítico e o estudo de caso do COMPAS no Capítulo 4.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** Os dados quantitativos de erro do COMPAS documentados pela ProPublica e a dinâmica dos ciclos de retroalimentação policial.
* **O que é interpretação:** A aplicação das mesmas críticas a modelos preditivos industriais de logística ou manutenção preditiva.
* **O que não podemos afirmar com base neste artigo:** Quaisquer formulações de código-fonte de novos algoritmos de aprendizado supervisionado.
