# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Systematic review of data-centric approaches in artificial intelligence and machine learning
* **Autor:** Prerna Singh
* **Ano:** 2023 (Disponível online em 22 de junho de 2023; fascículo: Volume 6, Edição 3, pp. 144–157)
* **Instituição/País:** Wellington, Nova Zelândia
* **Local de publicação:** *Data Science and Management* (KeAi Publishing / Elsevier - ISSN: 2666-7649)
* **DOI / Link:** [https://doi.org/10.1016/j.dsm.2023.06.001](https://doi.org/10.1016/j.dsm.2023.06.001)
* **Tipo de publicação:** Artigo de revisão sistemática em periódico científico (*Review Article*)
* **Tipo de pesquisa/metodologia:** Revisão Sistemática da Literatura (RSL) seguindo protocolo PRISMA/rigor metodológico estruturado com análise qualitativa e comparativa de intervenções data-cêntricas.

---

## 2. Objetivo do artigo
* **Problema investigado:** Embora algoritmos sofisticados de IA de última geração (*State-of-the-Art - SOTA*) venham sendo exaustivamente desenvolvidos, sua eficácia prática atinge um platô decorrente da ausência de dados de treinamento de alta qualidade. Apesar de muitos pesquisadores aplicarem técnicas de manipulação e limpeza de dados, essas práticas ocorrem de maneira fragmentada, empírica e sem diretrizes ou documentação sistemática unificada.
* **Objetivo principal:** Conduzir uma revisão sistemática da literatura para documentar, consolidar e estruturar as principais abordagens de *Data-Centric AI* (DCAI) utilizadas para melhorar intencionalmente ou involuntariamente a qualidade de sistemas de IA e Machine Learning.
* **Pergunta/Hipótese:** Quais são os eixos operacionais fundamentais adotados por praticantes e pesquisadores para elevar sistematicamente a qualidade dos dados, como o aumento cego de dados pode prejudicar o desempenho dos modelos e de que forma ferramentas probabilísticas de reparo e MLOps contêm o débito técnico em inteligência artificial?

---

## 3. Principais conceitos
* **Data-Centric AI como Coleção Sistemática de Práticas:** Conjunto de técnicas de manipulação, curadoria e refinamento que capacita os profissionais a aprimorar deliberadamente a qualidade dos dados que alimentam a esteira de ML.
* **Big Data vs. Good Data:** Desmistificação da crença ingênua de que \"mais dados é sempre melhor\". O artigo contrapõe o volume bruto desordenado (*Big Data*) à integridade, representatividade e relevância das instâncias (*Good Data*).
* **Fenômeno \"Can Adding Data Hurt?\":** Demonstração documentada de que a inclusão acrítica de dados adicionais pode degradar ativamente o desempenho preditivo (acurácia e F1-score) caso introduza ruído de rótulos, desvios de distribuição (*distribution drift*) ou instâncias inconsistentes com a tarefa alvo.
* **Reparo de Dados (*Repairing Data*):** Emprego de ferramentas avançadas como o *HoloClean* (limpeza baseada em inferência estatística e restrições de negação) para restaurar valores corrompidos e preservar dependências funcionais sem introduzir artefatos espúrios.
* **Visão Data-Cêntrica do Débito Técnico:** Extensão das lições de Sculley et al. (2015), demonstrando que o débito técnico em IA é alimentado precipuamente por falhas na governança de dados na fase de implantação (*data in deployment*).
* **MLOps e Rastreabilidade de Experimentos (*Experiment Tracking*):** Necessidade de versionamento conjunto de código e dados (usando ferramentas como DVC, MLflow e Neptune.ai) para viabilizar auditoria e reprodutibilidade.

---

## 4. Metodologia
* **Abordagem:** Revisão Sistemática da Literatura (RSL) orientada a evidências.
* **Bases pesquisadas:** IEEE Xplore, ACM Digital Library, ScienceDirect, SpringerLink e Google Scholar.
* **Critérios de triagem:** Inclusão de estudos empíricos e teóricos focados em manipulação qualitativa de dados para aprendizado supervisionado, semi-supervisionado e por transferência.
* **Eixos analisados:** A autora sintetizou a literatura em seis eixos: (1) Avaliação de qualidade de Big Data; (2) Técnicas de pré-processamento (coleta, rotulagem, aumento sintético e feature engineering); (3) Aprendizado por transferência e adaptação de domínio; (4) Aprendizado semi-supervisionado; (5) MLOps e rastreamento; (6) Efeito deletério da adição de dados e reparo probabilístico.

---

## 5. Principais resultados
* **Resultado 1 (A Primazia do Good Data):** Conjuntos de dados menores, porém limpos e balanceados, produzem rotineiramente classificadores mais acurados, generalizáveis e computacionalmente eficientes do que conjuntos massivos repletos de inconsistências e ruídos de anotação.
* **Resultado 2 (Evidência Experimental de Degradação por Adição de Dados):** O levantamento compila evidências empíricas de que expandir a base de treino com dados de fontes não verificadas ou de baixa qualidade degrada o F1-score e gera correlações espúrias nos modelos induzidos.
* **Resultado 3 (Eficácia das Ferramentas de Reparo Estatístico):** A restauração de anomalias com ferramentas probabilísticas (como *HoloClean*) supera a imputação univariada ingênua (média/mediana), restaurando a consistência interna das matrizes tabulares e minimizando a perda de informação.
* **Importância para o TCC:** Fornece o compêndio mais atualizado de literatura empírica demonstrando que a qualidade do dado (e não seu mero volume) é a variável determinante para o sucesso do treinamento em Machine Learning.

---

## 6. Relação com o meu TCC
* **Classificação:** **CENTRAL / INTEGRATIVO**
* **Justificativa:** Conecta de forma harmoniosa o conceito de Débito Técnico (Sculley et al.), o paradigma Data-Centric (Jakubik et al. e Whang et al.) e os métodos empíricos de pré-processamento e reparo de dados.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 2 (Engenharia de Dados e Qualidade de Dados):** Para embasar o debate conceitual *Big Data vs. Good Data*, ferramentas de reparo (*HoloClean*) e dimensões de qualidade de dados.
* **Capítulo 3 (Machine Learning e Dados de Treinamento):** Para discutir o fenômeno *Can adding data hurt?*, *Feature Engineering* e os impactos de ruído no treinamento supervisionado.
* **Capítulo 5 (Análise Integrada da Literatura):** Como base comparativa para confrontar as conclusões dos trabalhos nacionais (Batista, Barros & Melo) com o estado da arte das abordagens data-cêntricas internacionais.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 144):** *"Model-centric approaches are limited by the absence of high-quality data. Data-centric AI is an emerging approach for solving machine learning (ML) problems. It is a collection of various data manipulation techniques that allow ML practitioners to systematically improve the quality of the data used in an ML pipeline."*  
  * *Uso no TCC:* Introdução e Capítulo 2 para caracterizar o Data-Centric AI como conjunto disciplinado de técnicas de Engenharia de Dados.
* **Trecho 2 (p. 146):** *"The transition from big data to good data signifies that rather than merely accumulating vast quantities of data, the focus should be on acquiring relevant, high-quality, and representative data."*  
  * *Uso no TCC:* Capítulo 2 na seção sobre dimensões de qualidade e governança.
* **Trecho 3 (p. 152):** *"Adding more data can inadvertently introduce noise, bias, or irrelevant information, leading to degraded model performance."*  
  * *Uso no TCC:* Capítulo 3 e 4 para comprovar que volume sem qualidade prejudica ativamente a generalização do modelo.
