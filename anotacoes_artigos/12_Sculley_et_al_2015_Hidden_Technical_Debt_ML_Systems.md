# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Hidden Technical Debt in Machine Learning Systems
* **Autores:** D. Sculley; Gary Holt; Daniel Golovin; Eugene Davydov; Todd Phillips; Dietmar Ebner; Vinay Chaudhary; Michael Young; Jean-François Crespo; Dan Dennison
* **Ano:** 2015
* **Instituição/País:** Google, Inc., Mountain View, CA, EUA
* **Local de publicação:** *Advances in Neural Information Processing Systems (NeurIPS 2015)*, pp. 2503–2511
* **DOI / Link:** [NeurIPS Proceedings](https://proceedings.neurips.cc/paper/2015/hash/86df7dcfd896fc1f8e9c5025acc5eb2d-Abstract.html)
* **Tipo de publicação:** Artigo científico em conferência de topo (*Core A\**)
* **Tipo de pesquisa/metodologia:** Estudo analítico-empírico de Engenharia de Software e Sistemas de Machine Learning em larga escala industrial.

---

## 2. Objetivo do artigo
* **Problema investigado:** A discrepância estrutural entre a rapidez e o baixo custo inicial de prototipar e treinar modelos de Machine Learning versus a extrema dificuldade e o elevado custo contínuo de mantê-los em operação ao longo do tempo. Em sistemas de ML, a presença de dependências de dados opacas e a ausência de fronteiras modulares estritas acumulam um débito técnico silencioso e exponencial.
* **Objetivo principal:** Aplicar a metáfora do Débito Técnico (*Technical Debt*) da Engenharia de Software a sistemas baseados em Machine Learning, mapeando sistematicamente os fatores de risco específicos impostos pelos dados, interfaces de sistemas, anti-padrões arquiteturais e dependências dinâmicas.
* **Pergunta/Hipótese:** Quais são os mecanismos específicos pelos quais os dados e pipelines de infraestrutura degradam a manutenibilidade, a robustez e a confiabilidade de longo prazo de sistemas de Machine Learning?

---

## 3. Principais conceitos
* **Débito Técnico em ML:** Metáfora introduzida por Ward Cunningham (1992) estendida a ML: custos de manutenção diferidos que se acumulam silenciosamente no nível de sistema devido à dependência comportamental dos dados.
* **A Fração Minúscula do Código de ML:** O código do algoritmo de aprendizado de máquina propriamente dito ocupa uma pequena caixa isolada no centro da arquitetura, cercada por uma infraestrutura massiva de *Data Collection*, *Feature Extraction*, *Data Verification*, *Configuration*, *Process Management* e *Monitoring*.
* **Princípio CACE (*Changing Anything Changes Everything*):** Erosão das fronteiras clássicas de abstração. Em sistemas de software tradicionais, componentes são isolados por interfaces estritas. Em ML, os dados correlacionam todas as variáveis: alterar uma única feature, um método de pré-processamento ou hiperparâmetro afeta a distribuição de pesos de todas as outras features.
* **Dependências de Dados (*Data Dependencies*):** Ao contrário de dependências de código (resolvíveis por linters e compiladores), dependências de dados são silenciosas. Dividem-se em:
  - *Unstable Data Dependencies:* Consumo de sinais externos que mudam sem aviso;
  - *Underutilized Data Dependencies:* Features que agregam ganho marginal ínfimo mas aumentam a fragilidade;
  - *Static Analysis of Data Dependencies:* Ausência histórica de ferramentas para rastrear linhagem de dados (*data lineage*).
* **Anti-padrões de Sistemas:** *Glue code* massivo para integrar bibliotecas genéricas, *pipeline jungles* (esteiras complexas de raspagem, junção e formatação sem governança formal) e *dead experimental codepaths*.
* **Feedback Loops Ocultos:** Sistemas preditivos cujo comportamento altera o comportamento dos usuários, gerando novos dados enviesados que realimentam o modelo nas iterações seguintes.

---

## 4. Metodologia
* **Abordagem:** Analítica, descritiva e orientada à Engenharia de Software empírica.
* **Base de observação:** Mais de uma década de experiência prática dos autores na construção, implantação e sustentação contínua de dezenas de sistemas de ML em escala massiva no Google.
* **Procedimento:** Categorização estruturada dos pontos de falha e custos de manutenção sistêmicos, decompondo o ciclo de software inteligente em dados, código, interfaces e configuração.

---

## 5. Principais resultados
* **Resultado 1 (Centralidade da Infraestrutura de Dados):** O código de Machine Learning representa frequentemente menos de 5% da base total de código de um sistema operacional; os outros 95% correspondem a esteiras de Engenharia de Dados (coleta, ingestão, limpeza, validação, verificação de consistência e monitoramento).
* **Resultado 2 (O Custo Superior das Dependências de Dados):** Dependências de dados são substancialmente mais perigosas do que dependências de código, pois desvios distributivos ou corrupções nos pipelines de entrada ocorrem silenciosamente sem que ocorram exceções de compilação ou execução (*silent failures*).
* **Resultado 3 (A Necessidade de Verificação e Monitoramento Ativo):** Sem testes automatizados de dados (integridade, distribuição e invariância) e monitoramento contínuo de desvios (*drift*), sistemas de ML inevitavelmente degradam sua capacidade de generalização no mundo real.
* **Importância para o TCC:** É o trabalho clássico definitivo que justifica academicamente e tecnicamente por que a Engenharia de Dados não é uma etapa acessória, mas o próprio alicerce estrutural de qualquer sistema inteligente confiável.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL / FUNDACIONAL**
* **Justificativa:** Fornece a justificativa de Engenharia de Software mais citada e respeitada da ciência da computação mundial para fundamentar a primazia da Engenharia de Dados sobre os algoritmos de aprendizado.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 1 (Introdução e Justificativa):** Para ilustrar a falácia do foco exclusivo no modelo e citar o diagrama clássico dos componentes de um sistema de ML.
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para discutir a importância de pipelines formais de ingestão, validação contínua e mitigação de *pipeline jungles*.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para fundamentar os *Feedback Loops* ocultos e a degradação de confiabilidade por dependências instáveis de dados.
* **Capítulo 6 (Considerações Finais):** Para propor diretrizes de boas práticas de Engenharia de Software e governança de dados para sistemas de IA.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 2503):** *"Developing and deploying ML systems is relatively fast and cheap, but maintaining them over time is difficult and expensive. This dichotomy can be understood through the lens of technical debt..."*  
  * *Uso no TCC:* Introdução e Justificativa para contextualizar o custo oculto de modelos sem engenharia de dados.
* **Trecho 2 (p. 2504):** *"We explore several ML-specific risk factors to account for in system design. These include boundary erosion, entanglement, hidden feedback loops, undeclared consumers, data dependencies, configuration issues, changes in the external world, and a variety of system-level anti-patterns."*  
  * *Uso no TCC:* Capítulo 2 e Capítulo 4 para elencar as causas de falha estrutural de sistemas de ML.
* **Trecho 3 (p. 2505):** *"Data dependencies cost more than code dependencies. [...] Code dependencies can be identified via static analysis by compilers and linkers. Without similar tooling for data, it can be difficult to untangle."*  
  * *Uso no TCC:* Capítulo 2 para demonstrar por que a Engenharia de Dados moderna requer linhagem e contratos de dados formais.
