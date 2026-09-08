# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 14:** Kapoor & Narayanan (2023)  
**Arquivo Analisado:** `Kapoor_Narayanan_2023_Data_Leakage_Reproducibility.pdf` *(originalmente `mmc2.pdf`)*

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Leakage and the reproducibility crisis in machine-learning-based science
* **Autores:** Sayash Kapoor; Arvind Narayanan
* **Ano:** 2023 (Publicado em 8 de setembro de 2023)
* **Instituição/país:** Department of Computer Science and Center for Information Technology Policy, Princeton University, Princeton, NJ, Estados Unidos
* **Revista, congresso, repositório ou evento:** *Patterns* (Periódico interdisciplinar de ciência de dados de alto impacto da Cell Press / Elsevier)
* **Volume, número e páginas:** Volume 4, Número 9, Artigo 100804, 16 páginas
* **DOI:** 10.1016/j.patter.2023.100804
* **URL:** https://doi.org/10.1016/j.patter.2023.100804
* **Tipo de publicação:** Artigo de pesquisa científica original e meta-revisão sistemática
* **Idioma:** Inglês
* **Tipo de pesquisa:** Meta-análise empírica e metodológica em larga escala, desenvolvimento de taxonomia formal, auditoria reprodutível e estudo de caso empírico de replicação computacional.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A proliferação descontrolada do problema de **Data Leakage (Vazamento de Dados)** em aplicações de Machine Learning, onde a separação conceitual entre dados de treinamento e dados de avaliação é violada durante o pipeline de engenharia e modelagem. Essa contaminação resulta em estimativas excessivamente otimistas e espúrias de acurácia em bancada, gerando artigos científicos não replicáveis e modelos corporativos que falham catastroficamente quando implantados no mundo real.
* **Pergunta de pesquisa:** Qual é a magnitude e extensão do vazamento de dados na produção científica contemporânea, quais são os modos fundamentais de falha de engenharia que o originam e de que maneira uma taxonomia estruturada e um protocolo de auditoria documental (*Model Info Sheets*) podem eliminar esse erro sistemático?
* **Objetivo principal:** Mapear a extensão do vazamento de dados em múltiplos campos do saber, categorizar taxonomicamente todos os tipos conhecidos de vazamento em 8 modalidades estruturadas, demonstrar experimentalmente o colapso de alegações de superioridade de modelos de ML quando o vazamento é removido e propor os *Model Info Sheets* como padrão de auditoria.
* **Hipóteses ou questões específicas:** Erros sutis de pré-processamento de dados (como imputar dados faltantes ou realizar seleção de variáveis antes do particionamento) falseiam o desempenho preditivo, dando a ilusão de que algoritmos complexos superam modelos estatísticos tradicionais.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Quantitativa, dedutiva, meta-analítica e experimental de replicação.
* **Corpus investigado:** Levantamento exaustivo de revisões de reprodutibilidade em 17 disciplinas científicas (incluindo medicina, bioinformática, visão computacional, finanças e sociologia), identificando e auditando **294 artigos científicos afetados por vazamento de dados**.
* **Taxonomia deduzida:** Classificação sistemática em três eixos macroestruturais e 8 subtipos operacionais:
  - *Eixo L1 (Separação Treino/Teste):* Sem teste independente `[L1.1]`, Pré-processamento conjunto `[L1.2]`, Seleção de atributos no todo `[L1.3]`, Duplicatas entre conjuntos `[L1.4]`;
  - *Eixo L2 (Legitimidade de Features):* Feature proxy da variável dependente `[L2.1]`, Atributos inacessíveis em produção (*look-ahead*) `[L2.2]`;
  - *Eixo L3 (Distribuição Alvo):* Vazamento temporal `[L3.1]`, Falta de separação por grupos/indivíduos `[L3.2]`, Viés de amostragem `[L3.3]`.
* **Replicação empírica:** Reexecução de estudos de previsão de eclosão de guerras civis, comparando modelos de Deep Learning e Random Forest com Regressão Logística sob condições com e sem vazamento de dados.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Taxonomia Canônica dos 8 Tipos de Vazamento de Dados
* **O que foi encontrado:** Os autores estruturaram a taxonomia definitiva do vazamento de dados em Machine Learning, demonstrando que o vazamento não ocorre apenas por má-fé, mas por desconhecimento técnico de boas práticas de Engenharia de Dados durante o pré-processamento e particionamento dos dados.
* **Evidência:** Mapeamento detalhado de 294 publicações afetadas ao longo de quase duas décadas.
* **Interpretação dos autores:** O vazamento de dados é o principal vetor técnico da crise de reprodutibilidade em inteligência artificial.
* **Grau de evidência:** **Direto** (meta-análise em larga escala).

### Resultado 2: O Pré-processamento Compartilhado como Armadilha Silenciosa `[L1.2]`
* **O que foi encontrado:** A prática de aplicar normalização Min-Max, padronização Z-score, imputação pela média/mediana ou técnicas de balanceamento de classes (como SMOTE) em todo o conjunto de dados antes de efetuar a divisão treino/teste vaza informações estatísticas globais para o modelo de treino, elevando artificialmente as métricas de teste.
* **Evidência:** Derivação da dependência indutiva entre os parâmetros amostrais da base completa e as instâncias de teste.
* **Interpretação dos autores:** Cada etapa de transformação de dados deve ser ajustada exclusivamente com base nas instâncias de treino e somente então aplicada aos dados de validação e teste.
* **Grau de evidência:** **Direto**.

### Resultado 3: O Desaparecimento da Superioridade do ML após a Correção do Vazamento
* **O que foi encontrado:** No estudo de replicação de predição de conflitos civis, modelos complexos de ML aparentavam superar largamente modelos estatísticos lineares. Ao corrigir o vazamento temporal `[L3.1]` e o vazamento de agrupamento por países `[L3.2]`, o desempenho de todos os modelos sofreu queda expressiva e a suposta superioridade dos modelos neurais/ensembles desapareceu, empatando com a regressão logística tradicional.
* **Evidência:** Comparação quantitativa rigorosa de curvas ROC/AUC e métricas Brier antes e após o saneamento das esteiras de dados.
* **Interpretação dos autores:** Resultados extraordinários de novos algoritmos de IA são frequentemente subprodutos de falhas elementares de Engenharia de Dados.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* A integridade de qualquer sistema baseado em aprendizado de máquina depende do rigor metodológico conferido ao isolamento dos dados de teste ao longo de todo o pipeline de engenharia.
* **Afirmações fortes:** "Data leakage is a flaw in machine learning that leads to overoptimistic results." Resultados científicos de ML não podem ser aceitos pelo seu valor aparente sem a demonstração formal de ausência de vazamento.
* **Afirmações condicionadas ao contexto:** Em problemas sem dependência temporal ou estruturas de agrupamento, a separação limpa clássica `[L1]` pode ser suficiente, mas dados do mundo real invariavelmente demandam atenção aos eixos `[L2]` e `[L3]`.
* **Hipóteses / Possibilidades:** Adoção compulsória de questionários formais de conformidade (*Model Info Sheets*) por periódicos científicos e esteiras industriais de validação de modelos.

---

# 6. CONCEITOS IMPORTANTES
* **Data Leakage:**
  * *Como define/utiliza:* Introdução espúria de informações sobre o conjunto de teste ou sobre a variável alvo no treinamento de um modelo preditivo.
  * *Localização:* Seções 1 e 2.
  * *Importância:* Objeto central do artigo.
* **Temporal Leakage (Vazamento Temporal):**
  * *Como define/utiliza:* Violação da ordem cronológica dos dados, permitindo que o modelo aprenda padrões do futuro para tentar prever o passado.
  * *Localização:* Seção 3 (`[L3.1]`).
  * *Importância:* Falha comum em dados financeiros e longitudinais.
* **Group Separation (Separação por Grupos):**
  * *Como define/utiliza:* Requisito de que instâncias correlacionadas a um mesmo sujeito/entidade fiquem confinadas estritamente a apenas uma das partições (treino ou teste).
  * *Localização:* Seção 3 (`[L3.2]`).
  * *Importância:* Crítico para validação médica e de biometria.
* **Model Info Sheets:**
  * *Como define/utiliza:* Protocolo de auditoria técnica composto por 21 questões destinadas a comprovar a ausência de vazamento em modelos de ML.
  * *Localização:* Seção 4.
  * *Importância:* Proposta de governança de dados.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* O levantamento quantitativo cobriu revisões anteriores e, portanto, 294 trabalhos é apenas um limite inferior (*lower bound*) do número real de artigos corrompidos na literatura.

### Limitações observáveis (Interpretação da análise)
* A solução proposta via *Model Info Sheets* depende de preenchimento humano criterioso, exigindo que a comunidade combine formulários com ferramentas de análise estática de pipelines de software (*linters* de código/dados).

### Impacto das limitações
* Não afeta o mérito da contribuição; o artigo é amplamente aclamado como o estudo mais transformador sobre reprodutibilidade em ML da década atual.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Resultado negativo impactante:** Artigos premiados internacionalmente que alegavam precisões preditivas acima de 95% em diagnósticos de saúde tiveram seu desempenho reduzido para níveis próximos ao chute aleatório (50%) após a remoção de vazamento por separação de pacientes.
* **Ressalva sobre acurácias de bancada:** Métricas excepcionais obtidas em testes de laboratório são muitas vezes o principal sinal de alerta para a existência de vazamento de dados.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta de forma definitiva os elos: **Qualidade dos dados $\rightarrow$ Preparação/Tratamento $\rightarrow$ Treinamento $\rightarrow$ Generalização $\rightarrow$ Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere a conexão com viés ético e algorítmico, mas concentra seu núcleo duro na validade científica e estatística dos modelos.

### 9.3 Qual parte ele não aborda?
* Não trata da responsabilidade civil no direito positivo brasileiro nem de infraestrutura física de banco de dados.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz. Pelo contrário: valida com dados empíricos devastadores a hipótese central do TCC: a Engenharia de Dados (em especial o rigor no pré-processamento e na separação amostral) é o fator que determina se um modelo possui ou não capacidade de generalização real.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Provado: a forma como os dados são preparados e divididos dita a validade do modelo. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | O vazamento introduz uma qualidade ilusória que destrói a generalização. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Pré-processamento executado incorretamente contamina o aprendizado. | **SIM — demonstrado** |
| Representatividade influencia os resultados | Partições sem separação temporal ou de grupo destroem a representatividade. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Features de amostragem enviesada [L3.3] geram avaliações infladas. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Demonstração central: o modelo aprende atalhos gerados pelo vazamento de teste. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Tese mestra do artigo: acurácias de bancada altas eram puro artefato de vazamento. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | A quebra de hipóteses temporais e de grupo gera colapso de performance fora do treino. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade é rigorosamente definida como a ausência de vazamento de dados. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Propõe pipelines isolados e Model Info Sheets como solução técnica de engenharia. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** **SIM** (tratamento de amostragem e integridade na coleta).
* **Limpeza:** **SIM** (alerta para não aplicar limpeza/imputação sobre a base toda).
* **Transformação:** **SIM** (demonstra que transformação de features deve pertencer estritamente ao split de treino).
* **Qualidade:** **SIM** (qualidade metodológica e ausência de contaminação estatística).
* **Validação / Preparação para Treinamento:** **SIM** (objeto nuclear do estudo: técnicas de separação limpa).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM — Trata do coração metodológico da Engenharia de Dados para ML**, formalizando os protocolos obrigatórios de pré-processamento e particionamento de dados.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Data leakage is a widespread failure mode in machine-learning-based science. Based on a survey of past reviews, we find that it affects at least 294 papers across 17 disciplines."*  
  * *Localização:* p. 1 (In Brief).  
  * *Tipo:* Dimensão do impacto empírico.  
  * *Uso no TCC:* Introdução e Capítulo 3 para justificar o estudo do vazamento de dados.
* **Trecho 2:** *"Using the entire dataset for any pre-processing steps, such as imputation or over/under sampling, results in leakage. For instance, using oversampling before splitting the data into training and test sets leads to an imperfect separation..."*  
  * *Localização:* p. 4 (Section 3).  
  * *Tipo:* Regra de ouro de Engenharia de Dados.  
  * *Uso no TCC:* Capítulo 2 e Capítulo 3 ao conectar com Barros & Melo (imputação) e Batista (oversampling/SMOTE).
* **Trecho 3:** *"When leakage is fixed, the supposed superiority of ML models disappeared: they did not perform any better than older methods."*  
  * *Localização:* p. 1 (Abstract).  
  * *Tipo:* Conclusão científica de impacto.  
  * *Uso no TCC:* Capítulo 1 e Capítulo 5 para desmontar o mito da superioridade algorítmica desprovida de rigor de dados.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Kaufman, S. et al. (2012):** *Leakage in data mining: Formulation, detection, and avoidance* (Trabalho clássico pioneiro sobre vazamento).
* **Gebru, T. et al. (2021):** *Datasheets for Datasets* (Governança e documentação de datasets).
* **Mitchell, M. et al. (2019):** *Model Cards for Model Reporting* (Transparência de modelos).
* **Hand, D. J. (2006):** *Classifier technology and the illusion of progress* (A ilusão de progresso estatístico).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL / INDISPENSÁVEL**
* **Justificativa:** É a obra definitiva da literatura mundial contemporânea sobre *Data Leakage*, conectando diretamente os erros operacionais de pré-processamento de dados à perda de confiabilidade e à falácia das métricas de bancada em Machine Learning.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** O mito da alta acurácia em bancada e a crise de reprodutibilidade em inteligência artificial.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Protocolos de isolamento de pipelines de transformação e pré-processamento de dados.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** A taxonomia dos 8 tipos de Data Leakage na divisão treino/teste e cuidados mandatórios na aplicação de imputação e SMOTE.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Vazamento temporal e de agrupamento como destruidores da capacidade de generalização no mundo real.
* **Capítulo 6 (Considerações Finais):** Diretrizes de auditoria com Model Info Sheets para a prática profissional de engenharia.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** KAPOOR, S.; NARAYANAN, A. Leakage and the reproducibility crisis in machine-learning-based science. *Patterns*, v. 4, n. 9, p. 100804, 2023.
* **Problema:** Epidemia de data leakage gerando estimativas espúrias de acurácia e crise de reprodutibilidade em modelos de ML.
* **Objetivo:** Estabelecer a taxonomia definitiva de vazamento de dados em ML e fornecer protocolo de auditoria (Model Info Sheets).
* **Metodologia:** Meta-análise de 294 artigos em 17 áreas científicas e replicação experimental empírica.
* **Principais resultados:** Criação da taxonomia de 8 tipos de vazamento; demonstração de que a correção de vazamento elimina a falsa superioridade de modelos complexos de ML.
* **Principais conceitos:** Data Leakage, Train-Test Contamination, Look-Ahead Bias, Group Separation, Model Info Sheets.
* **Conclusões dos autores:** Resultados de ML não podem ser aceitos sem verificação do isolamento estrito de pipelines de dados.
* **Limitações:** O catálogo de 294 artigos é apenas uma estimativa inferior do volume real de pesquisas afetadas.
* **Contradições/ressalvas:** Acurácias extraordinárias de bancada são frequentemente consequência direta de vazamento no pré-processamento.
* **Contribuição para o TCC:** Prover a base teórica e taxonômica completa para o tópico de Data Leakage previsto no projeto.
* **Capítulo provável:** Capítulos 1, 2, 3 e 4.
* **Citação principal:** *"Data leakage is a flaw in machine learning that leads to overoptimistic results."*
* **Palavras-chave:** Data Leakage; Reprodutibilidade; Pré-processamento de Dados; Machine Learning; Validação de Modelos; Confiabilidade.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 10 / 10 |
| Relevância para Engenharia de Dados | 10 / 10 |
| Relevância para Qualidade de Dados | 10 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 10 / 10 |
| Atualidade | 10 / 10 (Cell Press - Setembro de 2023) |
* **Avaliação global:** 10 / 10 — Artigo de impacto histórico na ciência de dados internacional, indispensável para o TCC.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É a publicação definitiva sobre Data Leakage em toda a literatura acadêmica mundial de inteligência artificial.
* **Função única:** Fornecer a taxonomia dos 8 tipos de vazamento de dados e demonstrar a falácia das avaliações de bancada desconectadas de uma esteira rigorosa de Engenharia de Dados.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A contaminação de pelo menos 294 estudos científicos em 17 áreas, a taxonomia dos 8 tipos de vazamento e a perda de superioridade preditiva no estudo empírico de caso após o saneamento dos dados.
* **O que é interpretação:** A extrapolação de suas diretrizes como dever de diligência técnica perante o Código de Defesa do Consumidor ou LGPD no Brasil.
* **O que não podemos afirmar com base neste artigo:** Que todos os modelos complexos de ML na literatura são desprovidos de mérito (apenas aqueles cujas avaliações continham vazamento).
