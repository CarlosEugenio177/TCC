# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 02:** Batista (2003)  
**Arquivo Analisado:** 

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Pré-processamento de Dados em Aprendizado de Máquina Supervisionado
* **Autor:** Gustavo Enrique de Almeida Prado Alves Batista
* **Orientadora:** Profa. Dra. Maria Carolina Monard
* **Ano:** 2003 (Data de depósito: 11 de março de 2003)
* **Instituição/país:** Instituto de Ciências Matemáticas e de Computação – Universidade de São Paulo (ICMC-USP), São Carlos - SP, Brasil.
* **Revista, congresso, repositório ou evento:** Tese de Doutorado em Ciências de Computação e Matemática Computacional.
* **Volume, número e páginas:** 232 páginas.
* **DOI:** Não informado / Não disponível (registro anterior à difusão universal de DOI para teses no Brasil).
* **URL:** Biblioteca Digital de Teses e Dissertações da USP ()
* **Tipo de publicação:** Tese de Doutorado
* **Idioma:** Português
* **Tipo de pesquisa:** Pesquisa experimental, computacional e metodológica comparativa em larga escala.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que o autor investiga:** A degradação severa do desempenho de algoritmos de Aprendizado de Máquina supervisionado induzida por duas das mais frequentes imperfeições na qualidade de bases de dados reais: (1) a presença de dados com valores ausentes (*missing values*) e (2) conjuntos de dados com distribuições de classes altamente desbalanceadas (*imbalanced data*), onde a classe de interesse é rara.
* **Pergunta de pesquisa:** De que forma métodos dedicados de pré-processamento de dados (imputação multivariada, sobreamostragem sintética e filtragem de ruído baseada em vizinhos mais próximos) superam as soluções internas padrão dos algoritmos de aprendizado, otimizando a qualidade do conhecimento extraído e a representatividade de classes minoritárias?
* **Objetivo principal:** Desenvolver, implementar, analisar comparativamente e validar métodos avançados de pré-processamento de dados para o tratamento de valores ausentes e balanceamento de classes em aprendizado de máquina supervisionado.
* **Hipóteses ou questões específicas:** A combinação de geração sintética de amostras minoritárias (*SMOTE*) com algoritmos de limpeza de borda e remoção de instâncias ruidosas (*Tomek Links* e *Edited Nearest Neighbor - ENN*) produz fronteiras de decisão mais limpas e eleva a Área sob a Curva ROC (AUC) em relação aos métodos tradicionais de reamostragem aleatória.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Quantitativa, experimental e comparativa.
* **Tipo de estudo:** Pesquisa metodológica e experimental com avaliação estatística multibase.
* **Fonte dos dados:** Repositório internacional UCI Machine Learning Repository.
* **População/amostra:** Dezenas de bases de dados do mundo real (e.g., *Pima Indians Diabetes*, *Brest Cancer*, *Haberman*, *German Credit*, *Hypothyroid*, entre outras).
* **Período analisado:** Dados consolidados do repositório UCI.
* **Métodos de coleta:** Download e padronização dos datasets de benchmark.
* **Métodos de análise:** Validação cruzada estratificada em 10 partições (*10-fold cross-validation*), testes estatísticos não paramétricos pareados e análise geométrica de sobreposição de classes.
* **Modelos/algoritmos:** C4.5 (Árvores de Decisão), RIPPER (Indução de Regras), CN2, Naive Bayes e algoritmos baseados em instâncias. Métodos de pré-processamento: Imputação por Média/Moda, Imputação por C4.5/CN2, Random Under-Sampling, Random Over-Sampling, Tomek Links, ENN, Neighborhood Cleaning Rule (NCL), SMOTE, SMOTE + Tomek e SMOTE + ENN.
* **Métricas:** Curva ROC, Área sob a Curva ROC (AUC), Sensibilidade (*Recall*), Especificidade, Média Geométrica (\text{-mean}$) e Acurácia Global.
* **Procedimentos experimentais:** Indução sistemática de taxas de incompletude e níveis de desbalanceamento amostral, com subsequente aplicação dos pipelines de pré-processamento e treinamento dos classificadores.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: Superioridade da Imputação Indutiva/Multivariada sobre Métodos Simplistas
* **O que foi encontrado:** Métodos de imputação que utilizam relações entre múltiplos atributos e aprendizado supervisionado interno (como C4.5 e abordagens baseadas em vizinhança) preservam a acurácia dos classificadores finais de forma significativamente superior à substituição por média/moda incondicional ou à eliminação de instâncias (*casewise deletion*).
* **Evidência:** Tabelas comparativas de acurácia em dezenas de bases UCI com diferentes porcentagens de dados faltantes induzidos.
* **Interpretação do autor:** O autor afirma que a eliminação de instâncias descarta conhecimento útil e introduz viés amostral, enquanto a imputação ingênua insere ruído prejudicial; a modelagem multivariada é necessária para preservar a estrutura da base.
* **Grau de evidência:** **Direto** (experimentação estatística extensiva).

### Resultado 2: Eficácia dos Métodos Híbridos SMOTE + Tomek Links e SMOTE + ENN
* **O que foi encontrado:** A criação sintética de instâncias minoritárias pelo SMOTE, quando combinada com a remoção de instâncias ruidosas na fronteira de decisão via *Tomek Links* ou *ENN*, obteve os maiores ganhos consistentes de AUC e \text{-mean}$, superando amplamente o *Random Over-sampling* (que gera sobreajuste) e o *Random Under-sampling* (que perde informação relevante).
* **Evidência:** Curvas ROC e testes estatísticos de significância comprovando que a limpeza pós-geração sintética elimina regiões ambíguas de sobreposição de classes.
* **Interpretação do autor:** O autor conclui que o tratamento de classes desbalanceadas não deve apenas equilibrar quantidades numéricas, mas polir a geometria da fronteira de decisão.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Falácia da Métrica de Acurácia Global em Bases Assimétricas
* **O que foi encontrado:** Modelos treinados com bases desbalanceadas brutas obtiveram acurácias globais superiores a 95%, porém com sensibilidade próxima de zero na classe minoritária (o modelo simplesmente classificava tudo como pertencente à classe majoritária).
* **Evidência:** Matrizes de confusão e decomposição de taxas de falso negativo.
* **Interpretação do autor:** A acurácia global é uma métrica ilusória e perigosa em cenários desbalanceados; a representatividade da classe minoritária só pode ser assegurada com pré-processamento e métricas robustas (AUC).
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* O autor conclui enfaticamente que a qualidade do conhecimento extraído por algoritmos de aprendizado indutivo é determinada primordialmente pela qualidade dos dados de entrada.
* **Afirmações fortes:** O pré-processamento de dados é uma etapa indispensável no ciclo de KDD/Machine Learning; algoritmos de aprendizado não possuem mecanismos internos suficientes para superar dados com ruído severo ou desbalanceamento extremo.
* **Afirmações condicionadas ao contexto:** O desempenho relativo de cada método de reamostragem depende da densidade de pontos na fronteira de separação das classes e da dimensionalidade da base.
* **Hipóteses / Possibilidades:** Sugere a extensão de métodos de pré-processamento baseados em vizinhos para problemas multiclasse complexos e dados com atributos mistos.

---

# 6. CONCEITOS IMPORTANTES
* **Pré-processamento de Dados:**
  * *Como define/utiliza:* Etapa de saneamento, filtragem, transformação e reamostragem que precede o treinamento indutivo.
  * *Localização:* Capítulo 1 e Capítulo 2 (Fundamentação).
  * *Importância:* Conceito central de toda a tese.
* **Classes Desbalanceadas (*Class Imbalance*):**
  * *Como define/utiliza:* Cenário em que uma ou mais classes possuem quantidade significativamente menor de instâncias no conjunto de dados.
  * *Localização:* Capítulo 4 e Capítulo 5.
  * *Importância:* Objeto empírico do trabalho.
* **SMOTE (Synthetic Minority Over-sampling Technique):**
  * *Como define/utiliza:* Algoritmo de interpolação no espaço de atributos para criar instâncias sintéticas ao longo dos segmentos de reta que unem vizinhos minoritários.
  * *Localização:* Capítulo 4.
  * *Importância:* Base dos métodos híbridos propostos.
* **Tomek Links & Edited Nearest Neighbor (ENN):**
  * *Como define/utiliza:* Métodos de identificação e remoção de pares de instâncias de classes opostas mais próximas entre si ou instâncias cuja classe diverge da maioria de seus vizinhos (filtragem de ruído).
  * *Localização:* Capítulo 4.
  * *Importância:* Instrumentos de limpeza de fronteira.
* **Curva ROC e AUC:**
  * *Como define/utiliza:* Representação gráfica da taxa de verdadeiros positivos versus taxa de falsos positivos e a métrica de desempenho invariante ao desbalanceamento de classes.
  * *Localização:* Capítulo 3.
  * *Importância:* Critério formal de avaliação.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelo autor
* O estudo concentrou-se em problemas de classificação binária para a etapa de desbalanceamento.
* Avaliação experimental restrita aos paradigmas vigentes em 2003 (árvores de decisão C4.5, regras simbólicas RIPPER/CN2 e Naive Bayes).

### Limitações observáveis (Interpretação da análise)
* A tese foi desenvolvida na era pré-Big Data e pré-Deep Learning; os experimentos processaram datasets tabulares de porte médio em memória local, sem considerar esteiras distribuídas de streaming ou pipelines conteinerizados modernos.

### Impacto das limitações
* Não afeta a validade conceitual e estatística dos algoritmos propostos (que continuam sendo o padrão da indústria, implementados em bibliotecas como ), mas exige que o TCC conecte esses métodos à moderna Engenharia de Dados.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Resultado negativo documentado:** O *Random Over-sampling* (duplicação simples de instâncias minoritárias), embora equalize a contagem de registros, causa severo sobreajuste (*overfitting*), fazendo o modelo memorizar pontos específicos sem melhorar a generalização.
* **Ressalva sobre Under-sampling:** O *Random Under-sampling* puro degrada a acurácia da classe majoritária ao descartar instâncias que continham conceitos importantes da distribuição global.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com máxima autoridade científica os elos: **Qualidade dos Dados $\rightarrow$ Preparação/Tratamento $\rightarrow$ Representatividade $\rightarrow$ Treinamento $\rightarrow$ Generalização**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que dados mal tratados induzem custos econômicos e operacionais em sistemas de decisão reais.

### 9.3 Qual parte ele não aborda?
* Não aborda viés sociocultural/racial em sistemas de IA, nem trata de *Data Drift* contínuo em tempo real.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; constitui a prova empírica de que o pré-processamento é mais determinante para o resultado final do que a sofisticação do algoritmo de aprendizado.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Provado extensivamente: a qualidade da matriz de entrada dita o conhecimento induzido. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Missing values e desbalanceamento deformam regras e árvores de decisão. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Aplicação de SMOTE+Tomek/ENN transforma o desempenho dos classificadores. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A sub-representação estatística leva o modelo a ignorar a classe minoritária. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | O viés para a classe majoritária nos dados é reproduzido pelo modelo. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Instâncias ruidosas na borda geram ramos espúrios nas árvores de decisão. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Acurácia de 99% esconde recall zero; validação com AUC comprova a falácia. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Trata da distribuição estática, sem focar em drift temporal contínuo. | **PARCIAL** |
| Qualidade dos dados influencia confiabilidade | Modelos com dados tratados tornam-se robustos em aplicações críticas. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Sistematiza formalmente as etapas de saneamento e reamostragem. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** Não abordados diretamente (dados consumidos em formato estático).
* **Limpeza:** **SIM** (filtragem de ruído com Tomek Links e ENN).
* **Transformação:** **SIM** (geração sintética de dados com SMOTE).
* **Qualidade:** **SIM** (tratamento rigoroso de incompletude e assimetria).
* **Validação / Preparação para Treinamento:** **SIM** (protocolo rigoroso de particionamento estratificado).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **PARCIAL** — O trabalho utiliza a denominação clássica de *KDD (Knowledge Discovery in Databases)* e *Pré-processamento de Dados*, que constitui a base histórica e metodológica direta do que hoje se denomina Engenharia de Dados aplicada a Machine Learning.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Uma vez que a maioria dos algoritmos de aprendizado induz conhecimento estritamente a partir de dados, a qualidade do conhecimento extraído é amplamente determinada pela qualidade dos dados de entrada."*  
  * *Localização:* p. 5 (Resumo).  
  * *Tipo:* Conclusão / Premissa teórica.  
  * *Uso no TCC:* Citação de abertura para a Introdução e Justificativa do TCC.
* **Trecho 2:** *"Diversos aspectos podem influenciar no desempenho de um sistema de aprendizado devido à qualidade dos dados. Em bases de dados reais, dois desses aspectos estão relacionados com a presença de valores desconhecidos e o desbalanceamento de classes."*  
  * *Localização:* p. 5 (Resumo).  
  * *Tipo:* Definição do problema.  
  * *Uso no TCC:* Estruturação do Capítulo 2 e 3 na discussão de anomalias de dados.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Chawla, N. V. et al. (2002):** *SMOTE: Synthetic Minority Over-sampling Technique*. (Base do algoritmo de oversampling).
* **Tomek, I. (1976):** *Two modifications of CNN*. (Origem do conceito de Tomek Links).
* **Wilson, D. L. (1972):** *Asymptotic Properties of Nearest Neighbor Rules Using Edited Data*. (Origem do ENN).
* **Provost, F. & Fawcett, T. (2001):** *Robust Classification for Imprecise Environments*. (Fundamentação da Curva ROC).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL**
* **Justificativa:** É o trabalho seminal da computação brasileira sobre pré-processamento de dados em AM, indispensável para fundamentar os métodos de limpeza e balanceamento de dados.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Seção sobre imperfeições em bases de dados.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Seções sobre Técnicas de Reamostragem (SMOTE, Tomek Links) e Métricas de Avaliação (ROC/AUC).
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Seção sobre Representatividade de Classes e viés indutivo.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** BATISTA, G. E. A. P. A. *Pré-processamento de Dados em Aprendizado de Máquina Supervisionado*. 2003. 232 f. Tese (Doutorado em Ciências de Computação) – Instituto de Ciências Matemáticas e de Computação, Universidade de São Paulo, São Carlos, 2003.
* **Problema:** Degradação de modelos de AM por missing values e classes desbalanceadas.
* **Objetivo:** Desenvolver e validar métodos de pré-processamento para otimização indutiva.
* **Metodologia:** Experimentação quantitativa comparativa com 10-fold cross-validation em bases UCI.
* **Principais resultados:** Criação e validação dos métodos SMOTE+Tomek e SMOTE+ENN; demonstração da falácia da acurácia global.
* **Principais conceitos:** Pré-processamento, Missing Values, Classes Desbalanceadas, SMOTE, Tomek Links, ENN, Curva ROC.
* **Conclusões dos autores:** A qualidade dos dados de entrada dita o limite de aprendizado dos algoritmos; o pré-processamento supera ajustes algorítmicos isolados.
* **Limitações:** Focado em classificação binária tabular clássica.
* **Contradições/ressalvas:** Random Over-sampling equilibra classes mas induz overfitting severo.
* **Contribuição para o TCC:** Base teórica e metodológica clássica para pré-processamento e balanceamento.
* **Capítulo provável:** Capítulo 2, Capítulo 3 e Capítulo 4.
* **Citação principal:** *"Uma vez que a maioria dos algoritmos de aprendizado induz conhecimento estritamente a partir de dados, a qualidade do conhecimento extraído é amplamente determinada pela qualidade dos dados de entrada."*
* **Palavras-chave:** Pré-processamento de Dados; Aprendizado Supervisionado; Desbalanceamento de Classes; Qualidade de Dados; SMOTE.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 10 / 10 |
| Relevância para Engenharia de Dados | 8.5 / 10 |
| Relevância para Qualidade de Dados | 10 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 9.5 / 10 |
| Atualidade | 7.5 / 10 (Obra clássica) |
* **Avaliação global:** 9.5 / 10 — Tese de doutorado de excelência internacional desenvolvida na USP, referência obrigatória.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É a obra fundacional brasileira sobre preparação de dados e qualidade amostral em Machine Learning, citada internacionalmente por suas contribuições algorítmicas (SMOTE+Tomek/ENN).
* **Função única:** Fornecer a base algorítmica e metodológica de técnicas de reamostragem e tratamento de dados faltantes.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A superioridade de SMOTE+Tomek/ENN sobre random over/under-sampling em bases da UCI e a falha da acurácia global em bases desbalanceadas.
* **O que é interpretação:** A transposição direta de seus achados para arquiteturas contemporâneas de Data Lakes e MLOps em nuvem.
* **O que não podemos afirmar com base neste artigo:** O comportamento específico dessas técnicas em modelos modernos de bilhões de parâmetros (LLMs).
