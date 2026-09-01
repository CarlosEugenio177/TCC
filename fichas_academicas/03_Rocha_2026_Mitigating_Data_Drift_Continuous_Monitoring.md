# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 03:** Rocha (2026)  
**Arquivo Analisado:** `LH_Masters.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Mitigating Drift in Machine Learning Systems through Continuous Input Monitoring: An Architectural Proposal and Empirical Evaluation of Detection Methods
* **Autor:** Lucas Helfstein Rocha
* **Orientadora:** Prof.ª Dr.ª Kelly Rosa Braghetto
* **Ano:** 2026 (Março de 2026)
* **Instituição/país:** Instituto de Matemática e Estatística – Universidade de São Paulo (IME-USP), São Paulo - SP, Brasil.
* **Revista, congresso, repositório ou evento:** Dissertação de Mestrado em Ciência da Computação (Programa de Pós-Graduação em Ciência da Computação).
* **Volume, número e páginas:** 98 páginas.
* **DOI:** Não informado / Em processo de depósito institucional (2026).
* **URL:** Biblioteca Digital de Teses e Dissertações do IME-USP (`https://teses.usp.br/`)
* **Tipo de publicação:** Dissertação de Mestrado
* **Idioma:** Inglês (com resumo em português)
* **Tipo de pesquisa:** Pesquisa aplicada de Engenharia de Software / Sistemas com experimentação empírica quantitativa.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que o autor investiga:** A degradação progressiva e silenciosa da precisão e confiabilidade de modelos de Machine Learning implantados em ambientes reais de produção (*silent failure*), provocada por mudanças na distribuição estatística dos dados de entrada (*Data Drift / Covariate Shift*) e nas relações funcionais de negócio (*Concept Drift*), em contextos críticos onde a verdade fundamental (*ground truth labels*) é inacessível ou possui longo tempo de maturação (*delayed feedback*).
* **Pergunta de pesquisa:** Como estruturar uma arquitetura de monitoramento contínuo em pipelines de Engenharia de Dados/MLOps capaz de detectar variações distribucionais nos dados de entrada de forma puramente não supervisionada, e quais métodos estatísticos e baseados em ML oferecem o melhor equilíbrio entre rapidez de detecção, baixa taxa de alarmes falsos e viabilidade computacional?
* **Objetivo principal:** Propor uma arquitetura de software para monitoramento contínuo de dados de entrada em sistemas de ML e realizar uma avaliação empírica comparativa do desempenho de diferentes métodos de detecção de *drift* não supervisionados.
* **Hipóteses ou questões específicas:** Métodos de detecção multivariados (como classificadores de domínio e erro de reconstrução por PCA) detectam drifts sutis na covariância entre múltiplos atributos mais rapidamente e com menos alarmes falsos do que conjuntos de testes univariados isolados (como Kolmogorov-Smirnov).

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Quantitativa, experimental e de engenharia de sistemas.
* **Tipo de estudo:** Proposta de arquitetura de software e avaliação empírica em bancada experimental.
* **Fonte dos dados:** Conjuntos de dados de benchmark sintéticos e bases reais com variações temporais naturais: dados de transações financeiras, sensores de qualidade do ar (*Air Quality*), consumo de energia e telecomunicações.
* **População/amostra:** Múltiplas séries temporais tabulares e matrizes de fluxo de dados sob regimes estacionários e não estacionários.
* **Período analisado:** Séries temporais históricas simulando meses de operação em produção.
* **Métodos de coleta:** Ingestão de dados em janelas temporais deslizantes (*sliding windows*) e janelas baseadas em contagem.
* **Métodos de análise:** Métodos Univariados: Teste Kolmogorov-Smirnov (KS), Distância de Wasserstein, Divergência Kullback-Leibler (KL) e Population Stability Index (PSI). Métodos Multivariados: *Domain Classifier* (classificador adversarial treino vs. produção), Erro de Reconstrução por PCA e *Maximum Mean Discrepancy* (MMD).
* **Modelos monitorados:** XGBoost, Random Forest e Regressão Logística.
* **Métricas:** Tempo de Atraso na Detecção (*Detection Delay/Latency*), Taxa de Falsos Alarmes (Falsos Positivos), Falsos Negativos, Throughput/Custo de Memória e Degradação de F1-Score do modelo preditivo principal.
* **Procedimentos experimentais:** Simulação de fluxos de produção com injeção controlada de desvios abruptos (*abrupt drift*), graduais (*gradual drift*) e sazonais, medindo a sensibilidade de cada detector na camada de dados.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: Superioridade dos Métodos Multivariados em Desvios de Covariância
* **O que foi encontrado:** Métodos baseados em *Domain Classifiers* (treinamento de um discriminador para separar dados de referência de treino e dados de produção) identificaram 100% dos drifts que envolviam mudanças conjuntas na correlação entre atributos com atraso médio significativamente menor que testes univariados.
* **Evidência:** O teste de Kolmogorov-Smirnov (KS), quando aplicado coluna por coluna, falhou em detectar desvios em que as distribuições marginais $P(X_i)$ permaneceram inalteradas mas a dependência conjunta $P(X_i, X_j)$ mudou.
* **Interpretação do autor:** Testes univariados fornecem uma falsa sensação de segurança; a Engenharia de Dados deve priorizar métodos que capturem a estrutura multidimensional do espaço de atributos.
* **Grau de evidência:** **Direto** (comprovação experimental rigorosa).

### Resultado 2: Impacto Crítico do Dimensionamento de Janelas na Ingestão de Dados
* **O que foi encontrado:** Janelas de dados curtas ($N < 500$) apresentaram alta taxa de falsos alarmes devido ao ruído estocástico amostral; janelas excessivamente longas ($N > 5000$) introduziram um atraso inaceitável na detecção do drift, permitindo que o modelo operasse degradado por semanas antes do disparo de retreinamento.
* **Evidência:** Curvas de trade-off entre Latência e Especificidade para diferentes tamanhos de janela temporal.
* **Interpretação do autor:** A parametrização do pipeline de ingestão de dados é tão decisiva quanto o próprio algoritmo estatístico de detecção.
* **Grau de evidência:** **Direto**.

### Resultado 3: O PCA-Reconstruction Error como Solução Eficiente de Baixa Latência
* **O que foi encontrado:** O método de erro de reconstrução via PCA apresentou sensibilidade próxima ao *Domain Classifier*, porém com consumo de CPU e latência até 80% inferiores, tornando-se a melhor alternativa para esteiras de alta vazão.
* **Evidência:** Benchmarks de tempo de execução por lote de dados.
* **Interpretação do autor:** É viável implementar monitoramento multivariado em produção com baixo overhead de infraestrutura.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* O autor conclui que a hipótese estatística fundamental do Machine Learning — de que os dados de treino e produção são independentes e identicamente distribuídos (*i.i.d.*) — é rotineiramente violada no mundo real, tornando o monitoramento contínuo da camada de dados um requisito essencial de Engenharia de Software.
* **Afirmações fortes:** Monitorar a qualidade dos dados de entrada sem rótulos (*unsupervised input monitoring*) é indispensável para evitar falhas silenciosas de sistemas inteligentes em produção.
* **Afirmações condicionadas ao contexto:** A escolha do método ótimo de detecção depende do perfil de latência do negócio (tempo real vs. lote) e da dimensionalidade dos dados.
* **Hipóteses / Possibilidades:** Sugere a integração de detecção de drift com esteiras automáticas de retreinamento (*Automated Continuous Training - CT*) e verificação de justiça algorítmica em tempo real.

---

# 6. CONCEITOS IMPORTANTES
* **Data Drift / Covariate Shift:**
  * *Como define/utiliza:* Mudança na distribuição de probabilidade das variáveis preditoras $P(X)$, mantendo a relação $P(Y|X)$ inalterada.
  * *Localização:* Capítulo 2 (Background).
  * *Importância:* Alvo primário do monitoramento de entrada.
* **Concept Drift:**
  * *Como define/utiliza:* Mudança na distribuição condicional do alvo $P(Y|X)$, indicando que as regras do fenômeno mudaram.
  * *Localização:* Capítulo 2.
  * *Importância:* Causa definitiva da obsolescência do modelo.
* **Input Monitoring (Monitoramento de Entrada):**
  * *Como define/utiliza:* Auditoria contínua das propriedades estatísticas dos dados antes de sua submissão ao modelo preditivo em produção.
  * *Localização:* Capítulo 3 (Arquitetura Proposta).
  * *Importância:* Objeto arquitetural central da dissertação.
* **Domain Classifier (Classificador de Domínio):**
  * *Como define/utiliza:* Modelo auxiliar treinado para predizer se uma instância pertence à distribuição de treino ($y=0$) ou à distribuição recente de produção ($y=1$).
  * *Localização:* Capítulo 3 e 4.
  * *Importância:* Algoritmo multivariado de melhor desempenho empírico.
* **MLOps / Engenharia de Sistemas de ML:**
  * *Como define/utiliza:* Conjunto de práticas e arquiteturas para automatizar o ciclo de vida completo de modelos em produção.
  * *Localização:* Capítulo 1 e 3.
  * *Importância:* Contexto de engenharia de software da pesquisa.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelo autor
* Não avaliou o comportamento de detectores sob dados de texto livre (NLP) ou dados de imagem de altíssima dimensionalidade.
* A abordagem de monitoramento não supervisionado de entrada assume que variações significativas em $P(X)$ representam risco potencial de degradação, mas nem todo *covariate shift* resulta obrigatoriamente em perda de acurácia (drifts em atributos irrelevantes).

### Limitações observáveis (Interpretação da análise)
* A avaliação empírica operou em ambiente controlado com datasets tabulares; em ecossistemas corporativos complexos, a latência de rede e a governança de esquemas (*schema drift*) introduzem ruídos adicionais na esteira.

### Impacto das limitações
* Não compromete a validade dos métodos, mas delimita o estudo à governança de dados tabulares em produção.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Resultado contra-intuitivo:** Testes univariados consagrados na indústria (como KS test aplicado campo a campo em ferramentas de monitoramento populares) falham completamente em acusar drifts quando ocorrem rotações no espaço de covariância dos dados.
* **Ressalva crítica:** Retreinar o modelo a cada alarme de drift pode ser contraproducente se o desvio for apenas um ruído temporário, gerando instabilidade operacional (*catastrophic forgetting*).

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com rigor de engenharia de ponta os elos: **Engenharia de Dados $\rightarrow$ Qualidade Contínua dos Dados $\rightarrow$ Data Drift $\rightarrow$ Generalização $\rightarrow$ Confiabilidade de Sistemas**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que a perda de representatividade temporal dos dados induz novos vieses de negócio e quebra de contratos de serviço (SLA).

### 9.3 Qual parte ele não aborda?
* Não trata de viés social/demográfico em datasets nem de métodos de imputação inicial de missing values.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; expande a narrativa do TCC ao demonstrar que a Qualidade de Dados não é uma foto estática tirada antes do treino, mas um filme contínuo que precisa de monitoramento em tempo de execução.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Dados com distribuição alterada em produção degradam imediatamente o F1-Score. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | A quebra de consistência e atualidade dos dados invalida predições. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | O janelamento e normalização na ingestão afetam a detecção do desvio. | **SIM — demonstrado** |
| Representatividade influencia os resultados | Modelos falham quando a base de treino deixa de representar o perfil atual. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Foca no viés amostral induzido pela defasagem temporal da base. | **PARCIAL** |
| Modelos podem aprender padrões inadequados | Padrões antigos continuam sendo aplicados a um contexto que mudou. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Modelo com 95% no teste offline colapsa em produção sob drift. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Foco total da dissertação (análise profunda de Data Drift). | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | A confiabilidade do sistema de ML depende do monitoramento de dados. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Proposta de arquitetura de dados e esteira de MLOps para mitigação. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Ingestão:** **SIM** (janelas deslizantes de dados em streaming).
* **Armazenamento / Integração:** **SIM** (arquitetura de pipelines integrados).
* **Limpeza e Transformação:** **SIM** (normalização contínua de features).
* **Qualidade e Validação:** **SIM** (auditoria estatística de distribuição).
* **Monitoramento e Governança:** **FOCO TOTAL DO TRABALHO** (Input Monitoring de ML).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM** — O trabalho propõe uma arquitetura explícita de Engenharia de Software e Engenharia de Dados voltada para MLOps e monitoramento de qualidade de fluxos de dados em produção.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"A suposição estatística fundamental de que os dados de teste e produção seguem a mesma distribuição dos dados de treinamento (i.i.d.) é frequentemente violada em ambientes reais, resultando em uma degradação silenciosa do desempenho dos modelos."*  
  * *Localização:* p. 15 (Capítulo 2).  
  * *Tipo:* Conclusão / Premissa teórica.  
  * *Uso no TCC:* Fundamentar no Capítulo 1 e Capítulo 4 a fragilidade da avaliação estática de modelos de ML.
* **Trecho 2:** *"Detectar o desvio nos dados de entrada antes que ele se traduza em predições incorretas e prejuízos operacionais constitui um requisito de confiabilidade que depende diretamente da infraestrutura de engenharia de dados."*  
  * *Localização:* p. 42 (Capítulo 3).  
  * *Tipo:* Definição arquitetural.  
  * *Uso no TCC:* Vincular diretamente a infraestrutura de Engenharia de Dados à Confiabilidade do sistema.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Amershi, S. et al. (2019):** *Software engineering for machine learning: a case study*. (ICSE - Engenharia de Software para ML).
* **Gama, J. et al. (2014):** *A survey on concept drift adaptation*. (Pesquisa clássica de drift).
* **Rabanser, S. et al. (2019):** *Failing loudly: An empirical study of methods for detecting dataset shift*. (NeurIPS - Base comparativa de métodos).
* **Sculley, D. et al. (2015):** *Hidden technical debt in machine learning systems*. (Dívida técnica em dados).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL**
* **Justificativa:** É a dissertação mais recente da USP (2026) que conecta de forma estruturada a Engenharia de Dados, arquiteturas de monitoramento, *Data Drift* e Confiabilidade de Machine Learning.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Seção sobre MLOps, Pipelines de Ingestão e Monitoramento Contínuo.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Seção sobre Data Drift, Covariate Shift e Quebra da Hipótese *i.i.d.*
* **Capítulo 6 (Considerações Finais):** Diretrizes de Engenharia para sistemas de IA resilientes.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** ROCHA, L. H. *Mitigating Drift in Machine Learning Systems through Continuous Input Monitoring: An Architectural Proposal and Empirical Evaluation of Detection Methods*. 2026. 98 f. Dissertação (Mestrado em Ciência da Computação) – Instituto de Matemática e Estatística, Universidade de São Paulo, São Paulo, 2026.
* **Problema:** Falhas silenciosas em sistemas de ML em produção decorrentes de Data Drift sem rótulos imediatos.
* **Objetivo:** Propor uma arquitetura de monitoramento contínuo de dados de entrada e avaliar métodos não supervisionados de detecção de drift.
* **Metodologia:** Engenharia de software aplicada e avaliação experimental comparativa em fluxos de dados reais e sintéticos.
* **Principais resultados:** Métodos multivariados (Domain Classifier e PCA-reconstruction) superam testes univariados isolados; o tamanho da janela de ingestão determina o trade-off latência/falso alarme.
* **Principais conceitos:** Data Drift, Covariate Shift, Concept Drift, Input Monitoring, MLOps, Domain Classifier, Confiabilidade.
* **Conclusões dos autores:** A confiabilidade contínua de sistemas de ML exige auditoria não supervisionada dos dados de entrada na esteira de engenharia de dados.
* **Limitações:** Focado em dados tabulares estruturados.
* **Contradições/ressalvas:** Testes univariados convencionais (como KS) são cegos para drifts na covariância entre atributos.
* **Contribuição para o TCC:** Estabelece a ponte definitiva entre Engenharia de Dados, Data Drift e Confiabilidade em produção.
* **Capítulo provável:** Capítulo 2, Capítulo 4 e Capítulo 6.
* **Citação principal:** *"A suposição estatística fundamental de que os dados de teste e produção seguem a mesma distribuição dos dados de treinamento (i.i.d.) é frequentemente violada em ambientes reais..."*
* **Palavras-chave:** Data Drift; MLOps; Engenharia de Dados; Confiabilidade; Input Monitoring; Covariate Shift.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 10 / 10 |
| Relevância para Engenharia de Dados | 10 / 10 |
| Relevância para Qualidade de Dados | 9.5 / 10 |
| Relevância para Machine Learning | 9.5 / 10 |
| Relevância para Viés/Generalização | 9.5 / 10 |
| Atualidade | 10 / 10 (2026) |
* **Avaliação global:** 9.8 / 10 — Trabalho primoroso, de vanguarda e máxima aderência ao curso de Engenharia de Software.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** Fornece a base de Engenharia de Software e MLOps mais sólida e atualizada sobre monitoramento de qualidade de dados em produção e mitigação de drift.
* **Função única:** Trazer a perspectiva arquitetural de sistemas de dados em tempo de execução (*run-time data quality*).

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** O desempenho superior dos classificadores de domínio em drifts de correlação e a vulnerabilidade dos testes univariados isolados.
* **O que é interpretação:** A aplicação dos mesmos diagramas arquiteturais para esteiras exclusivas de processamento em lote em Data Warehouses legados.
* **O que não podemos afirmar com base neste artigo:** A eficiência desses detectores em fluxos multimídia (vídeo e áudio) não tabulares.
