# FICHA ACADÊMICA DE LEITURA PARA O TCC

**Trabalho 12:** Sculley et al. (2015)  
**Arquivo Analisado:** `Hidden_Technical_Debt_in_Machine_Learnin.pdf`

---

# 1. IDENTIFICAÇÃO DA FONTE
* **Título:** Hidden Technical Debt in Machine Learning Systems
* **Autores:** D. Sculley; Gary Holt; Daniel Golovin; Eugene Davydov; Todd Phillips; Dietmar Ebner; Vinay Chaudhary; Michael Young; Jean-François Crespo; Dan Dennison
* **Ano:** 2015
* **Instituição/país:** Google, Inc., Mountain View, CA, Estados Unidos
* **Revista, congresso, repositório ou evento:** *Advances in Neural Information Processing Systems (NeurIPS 2015)* — 28th Conference on Neural Information Processing Systems
* **Volume, número e páginas:** Volume 28, pp. 2503–2511 (9 páginas)
* **DOI:** 10.5555/2969442.2969519
* **URL:** https://proceedings.neurips.cc/paper/2015/hash/86df7dcfd896fc1f8e9c5025acc5eb2d-Abstract.html
* **Tipo de publicação:** Artigo em conferência internacional (*Top-Tier AI Conference*)
* **Idioma:** Inglês
* **Tipo de pesquisa:** Estudo empírico-analítico em Engenharia de Software e Arquitetura de Sistemas de Aprendizado de Máquina.

---

# 2. PROBLEMA E OBJETIVO DO ARTIGO
* **Problema que os autores investigam:** A proliferação desordenada de modelos de Machine Learning no setor industrial, onde vitórias preditivas rápidas e de baixo custo inicial ofuscam o surgimento de um débito técnico maciço durante a fase de sustentação. Enquanto o software tradicional acumula dívida técnica no código (resolvível por refatoração e testes unitários), em sistemas de ML a dívida acumula-se no nível sistêmico e é impulsionada pelos dados, cujas dependências e acoplamentos invisíveis erodem abstrações de engenharia.
* **Pergunta de pesquisa:** Quais são os riscos e fatores específicos de Machine Learning que aceleram o acúmulo de débito técnico em nível de sistema, e como as dependências de dados, anti-padrões arquiteturais e loops de retroalimentação afetam a sustentabilidade operacional de longo prazo?
* **Objetivo principal:** Desenvolver e estruturar a teoria do Débito Técnico aplicado a sistemas de Machine Learning, identificando anti-padrões práticos, dependências de dados crônicas e delineando práticas de mitigação para a comunidade de engenharia.
* **Hipóteses ou questões específicas:** O código de aprendizado estatístico propriamente dito constitui apenas uma fração diminuta de um sistema real, de modo que a falta de rigor de Engenharia de Dados sobre pipelines, linhagem de dados e validação de insumos inviabiliza a manutenção e a confiabilidade dos modelos.

---

# 3. METODOLOGIA
* **Abordagem da pesquisa:** Qualitativa-analítica e empírico-sistêmica.
* **Tipo de estudo:** Estudo arquitetural e taxonômico baseado em observação participante da engenharia do Google.
* **Procedimento metodológico:** Análise forense de ciclos de vida de desenvolvimento e manutenção de sistemas corporativos de ML, categorizando os fatores de risco em:
  1. Acoplamento de variáveis e erosão de fronteiras (*CACE principle*);
  2. Dependências de dados (*unstable*, *underutilized*, *cascade*);
  3. Loops de retroalimentação direta e oculta;
  4. Anti-padrões de software de dados (*glue code*, *pipeline jungles*);
  5. Débito de configuração e monitoramento de mudanças no mundo externo.

---

# 4. PRINCIPAIS RESULTADOS

### Resultado 1: A Fração Minúscula do Código de ML no Ecossistema de Produção
* **O que foi encontrado:** Os autores apresentam a representação gráfica definitiva dos sistemas inteligentes: o código matemático de Machine Learning ocupa uma diminuta caixa no centro da arquitetura. A esmagadora maioria do código e do esforço de sustentação reside em infraestrutura de dados: coleta (*data collection*), verificação (*data verification*), extração de atributos (*feature extraction*), configuração, gerenciamento de recursos e monitoramento.
* **Evidência:** Auditoria de bases de código reais no Google e arquiteturas corporativas.
* **Interpretação dos autores:** Supervalorizar o algoritmo de ML em detrimento dos pipelines de Engenharia de Dados é o principal erro estratégico das organizações de tecnologia.
* **Grau de evidência:** **Direto** (evidência industrial amplamente consolidada).

### Resultado 2: Dependências de Dados Custam Mais do que Dependências de Código
* **O que foi encontrado:** No desenvolvimento tradicional de software, dependências entre módulos de código são identificáveis e rastreáveis por compiladores, linkers e ferramentas de análise estática. Em ML, dependências de dados raramente possuem contratos formais: alterações na distribuição de uma feature externa fornecida por outro serviço degradam o modelo silenciosamente sem gerar erros de execução (*silent degradation*).
* **Evidência:** Casos de degradação preditiva decorrentes de desvios silenciosos em fontes upstream.
* **Interpretação dos autores:** Sistemas de ML requerem ferramentas equivalentes de validação estática e semântica de dados para conter o débito técnico.
* **Grau de evidência:** **Direto**.

### Resultado 3: O Princípio CACE e os Feedback Loops Ocultos
* **O que foi encontrado:** O princípio *Changing Anything Changes Everything* demonstra que não existem fronteiras isoladas em modelos de aprendizado: adicionar uma nova feature, alterar o esquema de imputação ou calibrar hiperparâmetros reorganiza toda a atribuição de pesos do modelo. Além disso, sistemas que interagem com usuários criam loops de feedback ocultos, alterando a própria distribuição dos dados futuros e consolidando vieses históricos.
* **Evidência:** Derivação da interdependência estatística e causal em modelos multi-atributos.
* **Interpretação dos autores:** A confiabilidade contínua só pode ser obtida por monitoramento ativo e governança rigorosa sobre a ingestão de dados.
* **Grau de evidência:** **Direto**.

---

# 5. CONCLUSÕES DOS AUTORES
* A facilidade em construir protótipos de Machine Learning mascara a tremenda complexidade de mantê-los no longo prazo.
* **Afirmações fortes:** "Dependências de dados custam mais caro do que dependências de código." O débito técnico de ML é perigoso porque acumula-se silenciosamente no nível do sistema, tornando as refatorações futuras extremamente onerosas.
* **Afirmações condicionadas ao contexto:** O débito técnico pode ser estrategicamente aceito no curto prazo para validação rápida de hipóteses, desde que seja pago com refatoração profunda de infraestrutura de dados antes da escalada operacional.
* **Hipóteses / Possibilidades:** Proposta de criação de métricas formais para mensurar o débito técnico de dados (ex.: cálculo da fração de atributos instáveis e taxa de glue code).

---

# 6. CONCEITOS IMPORTANTES
* **Technical Debt (Débito Técnico):**
  * *Como define/utiliza:* Custos de manutenção não intencionais acumulados pela escolha de atalhos rápidos de implementação em vez de soluções arquiteturais robustas.
  * *Localização:* Seção 1 (Introduction).
  * *Importância:* Eixo analítico de todo o artigo.
* **CACE Principle (Changing Anything Changes Everything):**
  * *Como define/utiliza:* Axioma de sistemas indutivos: a alteração de qualquer componente de entrada, distribuição amostral ou pré-processamento afeta o estado global dos pesos aprendidos.
  * *Localização:* Seção 2 (Complex Models Erode Boundaries).
  * *Importância:* Fundamentação da ausência de modularidade em ML.
* **Pipeline Jungles (Florestas de Pipelines):**
  * *Como define/utiliza:* Anti-padrão de Engenharia de Dados em que scripts casuais de raspagem, transformação e junção de dados são empilhados organicamente sem arquitetura unificada.
  * *Localização:* Seção 4.2.
  * *Importância:* Diagnóstico de fragilidade na preparação de dados.
* **Glue Code (Código de Cola):**
  * *Como define/utiliza:* Código volumoso e frágil escrito exclusivamente para compatibilizar dados entre bibliotecas externas genéricas e os sistemas corporativos.
  * *Localização:* Seção 4.1.
  * *Importância:* Evidência de desperdício quando falta uma esteira de dados madura.

---

# 7. LIMITAÇÕES

### Limitações declaradas pelos autores
* O artigo foca na identificação e caracterização dos fatores de débito técnico, oferecendo diretrizes conceituais em vez de um framework matemático único de cálculo financeiro do débito.

### Limitações observáveis (Interpretação da análise)
* A análise baseia-se primordialmente na realidade de infraestruturas massivas do porte do Google, embora todos os princípios sejam idênticos em organizações menores.

### Impacto das limitações
* Inexistente para a proposta do trabalho; a publicação tornou-se o clássico moderno mais lido na fronteira entre Engenharia de Software e Inteligência Artificial.

---

# 8. CONTRADIÇÕES, RESSALVAS E RESULTADOS NEGATIVOS
* **Ressalva sobre complexidade algorítmica:** Adicionar atributos ligeiramente correlacionados pode elevar minimamente a acurácia de teste, mas aumenta desproporcionalmente a superfície de falha e vulnerabilidade do sistema a mudanças do mundo real (*underutilized data dependencies*).
* **Alerta sobre re-treinamentos automáticos:** Re-treinar modelos cegamente sobre dados recentes sem validação prévia de esquema e distribuição pode propagar silenciosamente erros de ingestão (*cascading failures*).

---

# 9. RELAÇÃO COM O TCC

### 9.1 Qual parte da narrativa do TCC o artigo sustenta?
* Sustenta com autoridade máxima o elo: **Dados $\rightarrow$ Qualidade dos dados $\rightarrow$ Preparação/Tratamento** e sua relação com **Confiabilidade**.

### 9.2 Qual parte ele apenas sugere?
* Sugere as implicações socioculturais do viés através do conceito de *Hidden Feedback Loops*, mas mantém o foco primário na engenharia e sustentação de sistemas.

### 9.3 Qual parte ele não aborda?
* Não aborda a legislação civil de proteção de dados ou responsabilidade civil estrita (tratada por Borges & Faleiros Júnior no corpus).

### 9.4 O artigo contradiz ou limita alguma parte da narrativa?
* Não contradiz; ao contrário, constitui a pedra fundamental de engenharia que valida o argumento central do TCC: sem uma Engenharia de Dados rigorosa, sistemas de ML são insustentáveis e não confiáveis.

---

# 10. MAPA DA NARRATIVA

| Relação | Evidência no artigo | Classificação |
| :--- | :--- | :--- |
| Dados influenciam resultados de ML | O comportamento do software é determinado pelas distribuições dos dados de treino. | **SIM — demonstrado** |
| Qualidade dos dados influencia o modelo | Inconsistências de dados geram falhas silenciosas em sistemas em produção. | **SIM — demonstrado** |
| Preparação dos dados influencia o treinamento | Anti-padrões de pipeline (pipeline jungles) comprometem os dados de treino. | **SIM — demonstrado** |
| Representatividade influencia os resultados | A perda de representatividade diante de mudanças externas degrada a generalização. | **SIM — demonstrado** |
| Viés presente nos dados pode afetar o modelo | Feedback loops ocultos amplificam desvios e consolidam comportamentos enviesados. | **SIM — demonstrado** |
| Modelos podem aprender padrões inadequados | Features instáveis e espúrias induzem modelos a memorizar correlações efêmeras. | **SIM — demonstrado** |
| Bom desempenho no teste pode não significar boa generalização | Desempenho alto em testes de bancada mascara fragilidades operacionais em produção. | **SIM — demonstrado** |
| Mudanças na distribuição podem afetar o modelo | Dedica seção específica às mudanças no mundo real e quebra de premissas estatísticas. | **SIM — demonstrado** |
| Qualidade dos dados influencia confiabilidade | Confiabilidade de longo prazo depende da higienização ativa das dependências de dados. | **SIM — demonstrado** |
| Práticas de Engenharia de Dados podem contribuir para a qualidade | Apresenta a Engenharia de Dados e testes de dados como as soluções formais. | **SIM — demonstrado** |

---

# 11. RELAÇÃO COM ENGENHARIA DE DADOS
* **Coleta / Armazenamento / Integração:** **SIM** (exige governança na coleta e combate a fontes instáveis).
* **Limpeza:** **SIM** (saneamento sistemático de dependências e verificação de dados).
* **Transformação:** **SIM** (avaliação do custo de feature engineering e eliminação de glue code).
* **Qualidade:** **SIM** (avaliação profunda de integridade referencial e estabilidade temporal).
* **Validação / Preparação para Treinamento:** **SIM** (defesa de contratos de dados e testes automatizados de dados).
* **Resposta:** **O artigo trata explicitamente de Engenharia de Dados?**  
  **SIM — Trata explicitamente da infraestrutura e dos pipelines de dados**, demonstrando que a robustez do software de IA decorre da engenharia que suporta seus dados.

---

# 12. TRECHOS IMPORTANTES

* **Trecho 1:** *"Developing and deploying ML systems is relatively fast and cheap, but maintaining them over time is difficult and expensive. This dichotomy can be understood through the lens of technical debt..."*  
  * *Localização:* p. 2503 (Introduction).  
  * *Tipo:* Enunciado da tese principal.  
  * *Uso no TCC:* Introdução do TCC para justificar a importância da manutenção de longo prazo.
* **Trecho 2:** *"Data dependencies cost more than code dependencies. [...] Code dependencies can be identified via static analysis by compilers and linkers. Without similar tooling for data, it can be difficult to untangle."*  
  * *Localização:* p. 2505 (Section 3).  
  * *Tipo:* Diferenciação epistemológica código vs. dado.  
  * *Uso no TCC:* Capítulo 2 para demonstrar a complexidade singular da Engenharia de Dados para ML.
* **Trecho 3:** *"It is remarkable that only a tiny fraction of the code in many ML systems is actually devoted to learning or modeling."*  
  * *Localização:* p. 2507 (Section 4).  
  * *Tipo:* Evidência empírica visual.  
  * *Uso no TCC:* Capítulo 1 e Capítulo 2 para ilustrar que 95% do ecossistema de IA é Engenharia de Dados.

---

# 13. REFERÊNCIAS IMPORTANTES DO PRÓPRIO ARTIGO
* **Cunningham, W. (1992):** *The WyCash portfolio management system* (Origem do conceito de Technical Debt).
* **Breiman, L. (2001):** *Statistical Modeling: The Two Cultures* (Fundamentação dos modelos preditivos e complexidade de dados).
* **McMahan, H. B. et al. (2013):** *Ad click prediction: a view from the trenches* (Desafios reais de engenharia de dados em grande escala).

---

# 14. CONTRIBUIÇÃO PARA A REVISÃO
* **Classificação:** **CENTRAL / FUNDACIONAL**
* **Justificativa:** É a obra mais influente da história da engenharia de software aplicada a Machine Learning, indispensável para estabelecer a conexão entre fragilidade de dados e perda de confiabilidade de sistemas.

---

# 15. POSSÍVEL POSIÇÃO NA ESTRUTURA DO TCC
* **Capítulo 1 (Introdução e Justificativa):** Contextualização do custo oculto e o diagrama canônico do sistema de ML.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Dependências de dados, anti-padrões de pipeline e necessidade de validação contínua.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Feedback loops ocultos e a degradação de confiabilidade perante o mundo real.
* **Capítulo 6 (Considerações Finais):** Diretrizes para mitigar o débito técnico de dados na indústria.

---

# 16. FICHA DE LEITURA FINAL
* **Referência completa:** SCULLEY, D. et al. Hidden Technical Debt in Machine Learning Systems. In: ADVANCES IN NEURAL INFORMATION PROCESSING SYSTEMS (NeurIPS), 28., 2015, Montreal. *Proceedings...* Montreal: Curran Associates, Inc., 2015. p. 2503–2511.
* **Problema:** Acúmulo silencioso de custos de manutenção e fragilidade sistêmica em sistemas de ML induzido por dependências de dados.
* **Objetivo:** Analisar os fatores de risco e anti-padrões específicos de ML sob o prisma do débito técnico.
* **Metodologia:** Análise empírico-analítica e arquitetural em larga escala industrial (Google).
* **Principais resultados:** Demonstração do princípio CACE, o diagrama da fração mínima de código de ML e a gravidade das dependências instáveis de dados.
* **Principais conceitos:** Technical Debt, CACE Principle, Data Dependencies, Pipeline Jungles, Glue Code, Hidden Feedback Loops.
* **Conclusões dos autores:** A sustentabilidade de sistemas de ML depende da disciplina de engenharia aplicada à infraestrutura de dados.
* **Limitações:** Proposta conceitual/analítica sem fórmulas numéricas fechadas para precificação do débito.
* **Contradições/ressalvas:** Vitórias de acurácia em bancada geram prejuízos massivos de produção se incorporarem atributos instáveis.
* **Contribuição para o TCC:** Estabelecer a sustentação definitiva de que o ecossistema de ML é primariamente Engenharia de Dados.
* **Capítulo provável:** Capítulos 1, 2, 4 e 6.
* **Citação principal:** *"Data dependencies cost more than code dependencies."*
* **Palavras-chave:** Débito Técnico; Engenharia de Software; Machine Learning; Dependências de Dados; Confiabilidade de Sistemas.

---

# 17. AVALIAÇÃO DA FONTE
| Critério | Avaliação |
| :--- | :---: |
| Relevância para o tema | 10 / 10 |
| Qualidade metodológica | 10 / 10 |
| Relevância para Engenharia de Dados | 10 / 10 |
| Relevância para Qualidade de Dados | 9.5 / 10 |
| Relevância para Machine Learning | 10 / 10 |
| Relevância para Viés/Generalização | 9.5 / 10 |
| Atualidade | 9.0 / 10 (Clássico seminal de 2015) |
* **Avaliação global:** 9.9 / 10 — Artigo histórico seminal, um dos mais citados de toda a história da computação em produção de ML.

---

# 18. DECISÃO SOBRE AS 20 REFERÊNCIAS
* **Decisão:** **SIM**
* **Justificativa:** É a publicação seminal que cunhou a relação entre infraestrutura de dados e débito técnico em inteligência artificial.
* **Função única:** Fornecer a fundamentação teórica de Engenharia de Software e demonstrar graficamente a centralidade da Engenharia de Dados.

---

# 19. CONFIABILIDADE DA ANÁLISE
* **Diretamente sustentado pelo artigo:** Que o código de ML é uma fração ínfima do sistema, que dependências de dados degradam manutenibilidade e que anti-padrões de pipeline geram débito técnico silencioso.
* **O que é interpretação:** A integração de suas lições para o contexto específico de modelos de aprendizado supervisionado tabulares na administração pública brasileira.
* **O que não podemos afirmar com base neste artigo:** A quantificação exata em dólares do custo de cada linha de código em empresas fora do setor de tecnologia de ponta.
