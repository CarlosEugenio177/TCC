# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 04:** Ye et al. (2024/2025)  
**Arquivo Analisado:** `2402.12715v4.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** The Clever Hans Mirage: A Comprehensive Survey on Spurious Correlations in Machine Learning
* **Autores:** Wenqian Ye; Luyang Jiang; Eric Xie; Guangtao Zheng; Yunsheng Ma; Xu Cao; Dongliang Guo; Daiqing Qi; Zeyu He; Yijun Tian; Megan Coffee; Zhe Zeng; Sheng Li; Ting-hao (Kenneth) Huang; Ziran Wang; James M. Rehg; Henry Kautz; Aidong Zhang
* **Ano:** 2024 (Versão 4 atualizada: 2025)
* **Instituição/país:** University of Virginia, Purdue University, Pennsylvania State University, University of Rochester, University of Maryland, etc. (Estados Unidos).
* **Revista, congresso, repositório ou evento:** arXiv (`arXiv:2402.12715v4 [cs.LG]`).
* **Volume, número e páginas:** 30 páginas (formato conferência IEEE/ACM, duas colunas).
* **DOI:** `10.48550/arXiv.2402.12715`
* **URL:** `https://arxiv.org/abs/2402.12715`
* **Tipo de publicação:** *Survey* / Artigo de Revisão Sistemática e Proposição Taxonômica.
* **Idioma:** Inglês
* **Tipo de pesquisa:** Revisão sistemática de literatura, síntese taxonômica e meta-análise crítica de métodos de aprendizado de máquina.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A tendência sistemática de modelos de Machine Learning e Deep Learning de aprenderem **correlações espúrias** (*spurious correlations*) presentes nos dados de treinamento — o chamado "Efeito Clever Hans" —, no qual o modelo ancora suas predições em atalhos estatísticos (*shortcuts* ou variáveis de confusão contextuais) que coincidem com os rótulos no conjunto de treino, alcançando acurácia ilusoriamente perfeita em bancada, mas falhando de forma desastrosa quando implantados no mundo real ou avaliados fora da distribuição original (*Out-of-Distribution - OOD*).
* **Pergunta de pesquisa:** De onde se originam as correlações espúrias nos datasets, como diagnosticá-las em modelos já treinados e quais são as técnicas de intervenção no nível de dados (*data-level*), no algoritmo de treinamento e no pós-processamento mais eficazes para garantir a robustez causal e a generalização real?
* **Objetivo principal:** Fornecer o levantamento sistemático e a taxonomia mais abrangente da literatura sobre correlações espúrias em Machine Learning, cobrindo modalidades visuais, textuais, tabulares e grafos, mapeando causas nos dados, métodos de detecção, estratégias de mitigação e benchmarks de avaliação.
* **Hipóteses ou questões específicas:** Vieses de amostragem e co-ocorrências acidentais na coleta de dados são a principal raiz do aprendizado de atalhos; intervenções na curadoria e reponderação de dados de treino superam regularizações puramente algorítmicas na eliminação de atalhos espúrios.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa, taxonômica e sistemática.
* **Tipo de estudo:** *Survey* compreensivo com estruturação conceitual e análise de benchmarks empíricos.
* **Fonte dos dados:** Corpus exaustivo da literatura científica internacional (NeurIPS, ICML, ICLR, CVPR, ACL, KDD).
* **População/amostra:** Centenas de artigos seminais e dezenas de benchmarks de avaliação OOD (Waterbirds, CelebA, MultiNLI, CivilComments, Camelyon17, PACS).
* **Período analisado:** Artigos seminais de 2015 a 2025.
* **Métodos de coleta:** Busca sistemática em bases científicas e repositórios acadêmicos.
* **Métodos de análise:** Classificação taxonômica em 4 eixos estruturais: (1) Causas e Origens nos Dados; (2) Métodos de Detecção e Auditoria de Atalhos; (3) Estratégias de Mitigação (Nível de Dados, Nível de Modelo e Otimização); (4) Protocolos de Avaliação e Benchmarks de Robustez.
* **Modelos/algoritmos cobertos:** Redes Neurais Profundas (CNNs, Transformers, LLMs), Modelos Lineares, ERM (*Empirical Risk Minimization*), IRM (*Invariant Risk Minimization*), Group DRO (*Distributionally Robust Optimization*), Just Train Twice (JTT) e métodos de aumento de dados contrafactual.
* **Métricas analisadas:** Acurácia Padrão (*In-Distribution Accuracy*), Acurácia no Pior Grupo (*Worst-Group Accuracy - WGA*), Acurácia Fora da Distribuição (*OOD Accuracy*) e Invariância Causal.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Gênese das Correlações Espúrias na Coleta de Dados
* **O que foi encontrado:** Os autores identificam que a causa primária das correlações espúrias reside nos vieses de coleta e curadoria dos datasets. Fatores de confusão contextuais (ex.: pássaros aquáticos fotografados quase sempre com fundo de água; termos específicos correlacionados com toxicidade em NLP) são absorvidos pelas bases brutas e explorados pelos otimizadores como o caminho de menor esforço (*gradient shortcut*).
* **Evidência:** Mapeamento de benchmarks canônicos (ex.: no dataset *Waterbirds*, 95% das aves aquáticas aparecem sobre água, induzindo o classificador a reconhecer o fundo em vez do pássaro).
* **Interpretação dos autores:** Os autores concluem que os modelos não "entendem" semântica; eles são extratores estatísticos oportunistas que exploram qualquer correlação de alta frequência nos dados.
* **Grau de evidência:** **Direto** (comprovação empírica nos benchmarks levantados).

### Resultado 2: A Miragem da Acurácia de Teste Padrão (Efeito Clever Hans)
* **O que foi encontrado:** A prática convencional de avaliar modelos através de particionamento aleatório de treino/teste (*random split i.i.d.*) perpetua as mesmas correlações espúrias no conjunto de teste, resultando em métricas de acurácia acima de 95% que escondem acurácias inferiores a 30% em grupos minoritários (onde a correlação espúria é invertida).
* **Evidência:** Discrepância sistemática documentada entre *Average Accuracy* e *Worst-Group Accuracy* em múltiplos domínios.
* **Interpretação dos autores:** Avaliar modelos com dados identicamente distribuídos mascara a falta de confiabilidade e a fragilidade do sistema para uso em cenários abertos.
* **Grau de evidência:** **Direto**.

### Resultado 3: A Superioridade das Intervenções no Nível de Dados (*Data-Level*)
* **O que foi encontrado:** Técnicas que atuam diretamente na esteira de Engenharia e Curadoria de Dados — como reponderação de grupos raros (*Group Reweighting*), aumento de dados contrafactual (*Counterfactual Data Augmentation*) e auditoria de atributos espúrios — produzem ganhos de robustez mais estáveis e generalizáveis do que modificações puramente arquiteturais ou hiperparametrizações no modelo.
* **Evidência:** Síntese comparativa de desempenho de métodos de mitigação na literatura.
* **Interpretação dos autores:** A intervenção na raiz do problema (a composição e representatividade do dataset) é mais eficiente do que tentar forçar o algoritmo a ignorar padrões presentes na base.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* Os autores concluem que as correlações espúrias constituem uma das maiores ameaças à confiabilidade, segurança e equidade dos sistemas de Machine Learning contemporâneos.
* **Afirmações fortes:** Modelos que alcançam métricas de desempenho aparentemente perfeitas em bancos de teste estáticos frequentemente operam como "Clever Hans", tomando decisões corretas pelos motivos errados; a acurácia média não é evidência de generalização real.
* **Afirmações condicionadas ao contexto:** O sucesso de algoritmos de mitigação (como Group DRO) depende da disponibilidade de anotações prévias sobre os atributos de confusão presentes nos dados.
* **Hipóteses / Possibilidades:** Apontam a inferência causal (*Causal Machine Learning*) e a geração de dados sintéticos balanceados como as fronteiras mais promissoras para a superação de atalhos espúrios.

---

# 6. CONCEITOS IMPORTANTES
* **Spurious Correlations (Correlações Espúrias):**
  * *Como define/utiliza:* Associação estatística espúria entre atributos de entrada não causais e a variável dependente.
  * *Localização:* Seção 1 (Introduction) e Seção 2 (Taxonomy).
  * *Importância:* Objeto central do survey.
* **Clever Hans Effect (Efeito Clever Hans):**
  * *Como define/utiliza:* Metáfora para o modelo de IA que finge raciocínio mas apenas explora atalhos de fundo ou pistas acidentais do conjunto de dados.
  * *Localização:* Seção 1.
  * *Importância:* Base conceitual e filosófica do artigo.
* **Shortcut Learning (Aprendizado de Atalhos):**
  * *Como define/utiliza:* Decisão do modelo orientada por características superficiais mais fáceis de otimizar via gradiente.
  * *Localização:* Seção 2.
  * *Importância:* Mecanismo algorítmico do erro.
* **Out-of-Distribution (OOD) Generalization:**
  * *Como define/utiliza:* Capacidade do modelo de prever corretamente quando as correlações espúrias do conjunto de treino são quebradas no ambiente de teste.
  * *Localização:* Seções 4 e 5.
  * *Importância:* Métrica definitiva de generalização.
* **Worst-Group Accuracy (Acurácia no Pior Grupo):**
  * *Como define/utiliza:* Acurácia do modelo avaliada exclusivamente no subgrupo mais desfavorecido ou raro do dataset (e.g., ave aquática na terra).
  * *Localização:* Seção 5 (Benchmarks).
  * *Importância:* Métrica de robustez contra atalhos.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* A maioria dos métodos de mitigação existentes assume que os grupos ou atributos espúrios são conhecidos e anotados previamente, o que raramente ocorre em datasets massivos da indústria.
* Há um *trade-off* frequente: métodos que maximizam a acurácia fora da distribuição (OOD) sofrem pequenas quedas na acurácia média dentro da distribuição (ID).

### Limitações observáveis (Interpretação da análise)
* O survey compila predominantemente literatura internacional de língua inglesa e benchmarks consolidados de visão/NLP; dados tabulares corporativos de pequeno porte possuem menor espaço dedicado, exigindo transposição conceitual para a Engenharia de Software convencional.

### Impacto das limitações
* Não afeta o valor da taxonomia, mas destaca o desafio prático de aplicar essas soluções em ambientes corporativos onde não há orçamento para rotulagem de variáveis de confusão.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Resultado perturbador:** Modelos maiores e mais complexos (como redes neurais profundas com centenas de milhões de parâmetros) tendem a memorizar e explorar correlações espúrias com mais facilidade e rapidez do que modelos lineares simples, devido à sua altíssima capacidade de ajuste (*capacity to memorize shortcuts*).
* **Ressalva crítica:** Aumentar puramente o volume de dados brutos sem curadoria (*scaling data*) não elimina correlações espúrias; se o processo de coleta for enviesado, o modelo maior apenas aprenderá o atalho com maior convicção.

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com autoridade máxima e exaustiva os elos: **Qualidade dos Dados → Representatividade → Viés → Treinamento → Correlações Espúrias → Generalização → Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere que a Engenharia de Dados deve incorporar auditorias causais antes de liberar datasets para treinamento.

### 9.3 Qual parte ele não aborda?
* Não aborda responsabilidade civil jurídica nem implementações de arquitetura de data lakes em nuvem.

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; derruba de forma categórica a premissa ingênua de que "alta acurácia no conjunto de teste prova que o modelo é confiável", alinhando-se à palestra motivadora do seu TCC.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | Co-ocorrências nos dados de treino ditam os atalhos aprendidos pelo modelo. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Fatores de confusão contextuais degradam a robustez semântica. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Intervenções de dados (reweighting/augmentation) eliminam atalhos espúrios. | **SIM — demonstrado** |
| Representatividade influencia os resultados | Falta de dados em combinações raras (pior grupo) gera colapso de predição. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | O viés de amostragem vira correlação espúria permanente no classificador. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Foco total do artigo (Efeito Clever Hans e Shortcut Learning). | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Acurácia média de 95% mascara acurácia de 30% em pior grupo sob random split. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | OOD shift quebra os atalhos aprendidos e colapsa a predição. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Modelos guiados por atalhos são perigosos em medicina e veículos autônomos. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Curadoria de amostragem e rebalanceamento causal de datasets. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta e Amostragem:** **FOCO DO ARTIGO** (identificada como a raiz primária das correlações espúrias).
* **Limpeza e Curadoria:** **SIM** (remoção de atalhos e variáveis de confusão).
* **Transformação / Data Augmentation:** **SIM** (aumento de dados contrafactual).
* **Qualidade:** Foco na dimensão de **representatividade semântica e imparcialidade contextual**.
* **Validação / Teste OOD:** **SIM** (criação de splits de validação fora da distribuição).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **PARCIAL** — O artigo discute exaustivamente a curadoria, amostragem e intervenções na matriz de dados de treino (*Data-Level Interventions*), embora utilize a terminologia da Ciência da Computação e Aprendizado de Máquina Teórico.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Models often achieve high standard accuracy by relying on 'shortcuts' or spurious correlations—patterns that hold in the training data but fail in unseen environments, mirroring the Clever Hans effect."*  
  * *Localização:* p. 1 (Introduction).  
  * *Tipo:* Conclusão / Tese central.  
  * *Uso no TCC:* Fundamentar a ilusão do desempenho de bancada no Capítulo 1 e Capítulo 4.
* **Trecho 2:** *"The genesis of spurious correlation is predominantly rooted in data collection biases, where unrepresentative sampling and contextual confounding establish misleading statistical associations."*  
  * *Localização:* p. 6 (Section 2.1 - Origins in Data).  
  * *Tipo:* Resultado / Análise causal.  
  * *Uso no TCC:* Comprovar que a Engenharia de Dados e a coleta são a origem primária do viés no modelo.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Geirhos, R. et al. (2020):** *Shortcut learning in deep neural networks*. (Nature Machine Intelligence - Artigo fundador do conceito de atalhos).
* **Sagawa, S. et al. (2020):** *Distributionally robust neural networks for group shifts: On the importance of regularizations for worst-case generalization*. (ICLR - Proposição do Group DRO e dataset Waterbirds).
* **Arjovsky, M. et al. (2019):** *Invariant Risk Minimization*. (arXiv - Base do aprendizado invariante).
* **Ribeiro, M. T. et al. (2016):** *"Why Should I Trust You?": Explaining the Predictions of Any Classifier*. (KDD - LIME e o caso do lobo vs. husky na neve).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL**
* **Justificativa:** É a maior e mais completa revisão taxonômica internacional contemporânea sobre correlações espúrias, atalhos de dados e falhas de generalização, alinhada à motivação do TCC.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** Para conceituar o Efeito Clever Hans e justificar por que o foco deve sair do modelo isolado para a esteira de dados.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Seções sobre Correlações Espúrias, *Shortcut Learning* e Avaliação Fora da Distribuição (*OOD*).
* **Capítulo 5 (Análise da Literatura):** Como referência-chave na síntese internacional.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** YE, W. et al. The Clever Hans Mirage: A Comprehensive Survey on Spurious Correlations in Machine Learning. *arXiv preprint arXiv:2402.12715v4*, 2024. 30 p. DOI: 10.48550/arXiv.2402.12715.
* **Problema:** Modelos de ML que memorizam atalhos espúrios nos dados e colapsam fora da distribuição de treino.
* **Objetivo:** Estabelecer uma taxonomia sistemática de causas nos dados, diagnósticos e métodos de mitigação para correlações espúrias.
* **Metodologia:** Revisão sistemática e síntese conceitual exaustiva da literatura internacional.
* **Principais resultados:** Correlações espúrias nascem em vieses de amostragem na coleta; testes aleatórios tradicionais mascaram o problema; intervenções nos dados são a forma mais robusta de correção.
* **Principais conceitos:** Spurious Correlations, Clever Hans Effect, Shortcut Learning, OOD Generalization, Worst-Group Accuracy, Group DRO.
* **Conclusões dos autores:** A acurácia padrão em dados de teste correlacionados é uma miragem; o desenvolvimento confiável de ML requer auditoria de dados e validação OOD.
* **Limitações:** Métodos de mitigação dependem de anotação de atributos espúrios nos datasets.
* **Contradições/ressalvas:** Modelos maiores e com mais dados memorizam atalhos com mais facilidade se a base for desbalanceada.
* **Contribuição para o TCC:** Fundamentação definitiva de Correlações Espúrias, Generalização e Falácia da Acurácia.
* **Capítulo provável:** Capítulo 1, Capítulo 4 e Capítulo 5.
* **Citação principal:** *"The genesis of spurious correlation is predominantly rooted in data collection biases, where unrepresentative sampling and contextual confounding establish misleading statistical associations."*
* **Palavras-chave:** Correlações Espúrias; Clever Hans; Shortcut Learning; Generalização OOD; Engenharia de Dados.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 10 / 10 |
| Relevância para Engenharia de Dados | 9.0 / 10 |
| Relevância para Qualidade de Dados | 10 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 10 / 10 |
| Atualidade | 10 / 10 (2024/2025) |
* **Avaliação global:** 9.9 / 10 — Levantamento monumental e essencial para o estado da arte do TCC.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** Fornece a base teórica e taxonômica definitiva para o Capítulo 4 e 5 sobre Correlações Espúrias e avaliação de generalização fora da distribuição.
* **Função única:** Sistematizar taxonomicamente o Efeito Clever Hans e provar que a alta acurácia nos testes tradicionais é enganosa.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** A taxonomia das causas nos datasets, as definições de atalhos e os resultados de benchmarks internacionais com alta discrepância entre acurácia média e pior grupo.
* **O que é interpretação:** A aplicação direta das mesmas técnicas em pequenas bases tabulares corporativas sem infraestrutura especializada de anotação.
* **O que não podemos afirmar com base neste artigo:** Que exista um algoritmo universal capaz de resolver correlações espúrias de forma 100% não supervisionada sem qualquer intervenção humana na camada de dados.
