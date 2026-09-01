# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Inteligência artificial, vieses algorítmicos e racismo: o lado desconhecido da justiça algorítmica
* **Autores:** Alexandre Morais da Rosa; Bárbara Guasque
* **Ano:** 2024 (Jul./Dez. 2024)
* **Instituição/País:** Universidade do Vale do Itajaí (UNIVALI), Itajaí - SC, Brasil.
* **Local de publicação:** *Opinión Jurídica*, v. 23, n. 50, a49, p. 1-23.
* **DOI / Link:** `https://doi.org/10.22395/ojum.v23n50a49` (ISSN online: 2248-4078)
* **Tipo de publicação:** Artigo científico em periódico internacional indexado.
* **Tipo de pesquisa/metodologia:** Pesquisa exploratória e descritiva com metodologia bibliográfica e estudo de casos judiciais e de segurança pública.

---

## 2. Objetivo do artigo
* **Problema investigado:** A aplicação acrítica de modelos de Machine Learning e pontuação algorítmica de risco no sistema judiciário penal e na segurança pública, onde os dados de treinamento carregam o histórico de racismo estrutural e distorções de amostragem policial, resultando em decisões discriminatórias disfarçadas de neutralidade matemática.
* **Objetivo principal:** Identificar os impactos negativos de modelos de IA enviesados na violação de direitos fundamentais e propor medidas rigorosas de controle e auditoria sobre os dados utilizados na construção de modelos preditivos.
* **Pergunta/Hipótese:** De que modo a negligência na verificação e curadoria dos dados de entrada em modelos de IA perpetua e potencializa o racismo institucional no âmbito das decisões judiciais?

---

## 3. Principais conceitos
* **Falsa Neutralidade Matemática:** A ilusão de que, por serem baseados em equações e algoritmos, os modelos de IA produzem decisões imunes a preconceitos e injustiças humanas.
* **Racismo Algorítmico:** A reprodução automatizada e em escala de estigmas e desvantagens históricas contra pessoas negras e periféricas através de algoritmos preditivos.
* **Dados Viciados de Treinamento (*Biased Training Data*):** Estatísticas policiais do passado que medem a seletividade da atuação repressiva do Estado, e não a distribuição real de crimes na sociedade.
* **Caso COMPAS (*Correctional Offender Management Profiling for Alternative Sanctions*):** Modelo de predição de reincidência criminal que apresentou taxas de falsos positivos desproporcionalmente maiores para indivíduos negros, mesmo quando controladas outras variáveis socioeconômicas.
* **Feedback Loop (Ciclo de Retroalimentação Viciada):** Mecanismo pelo qual predições enviesadas direcionam mais policiamento para bairros periféricos, gerando mais ocorrências nesses locais e alimentando a base de dados com ainda mais assimetria.

---

## 4. Metodologia
* **Abordagem:** Qualitativa, analítica e interdisciplinar.
* **Procedimento:** Pesquisa bibliográfica estruturada associada à análise documental de relatórios técnicos, auditorias algorítmicas (e.g., investigação da ProPublica) e casos de reconhecimento facial no Brasil e no exterior.
* **Critério de análise:** Avaliação do impacto das taxas assimétricas de erro (Falsos Positivos vs. Falsos Negativos) entre diferentes grupos raciais.

---

## 5. Principais resultados
* **Resultado 1 (Assimetria nas Taxas de Erro):** A falta de tratamento e curadoria nos dados de entrada faz com que os modelos calibrem seus parâmetros penalizando minorias raciais com erros do Tipo I (classificação errônea de alto risco para quem não reincidirá).
* **Resultado 2 (O Perigo da Caixa-Preta):** A ausência de governança de dados combinada com a opacidade dos algoritmos proprietários impede a ampla defesa e mascara as premissas preconceituosas aprendidas pelo modelo.
* **Resultado 3 (A Primazia da Auditoria de Dados):** Medidas puramente algorítmicas não resolvem o problema se os dados de treino mantiverem a distorção amostral de origem.
* **Importância para o TCC:** Prova que a confiabilidade de sistemas inteligentes não se resume a métricas estatísticas globais, exigindo auditoria na cadeia de custódia e amostragem dos dados na Engenharia de Dados.

---

## 6. Relação com o meu TCC
* **Classificação:** **IMPORTANTE**
* **Justificativa:** Fornece a melhor fundamentação crítica e empírica para o **Capítulo 4** ("Viés, Representatividade e Confiabilidade"), demonstrando como dados de treino distorcidos destroem a confiabilidade de sistemas inteligentes.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 1 (Introdução e Justificativa):** Para evidenciar que modelos podem apresentar acurácia matemática geral e ainda assim cometer violações graves e inaceitáveis.
* **Capítulo 4 (Viés, Representatividade e Confiabilidade):** Para fundamentar o conceito de *Feedback Loop* de dados viciados e o estudo de caso do COMPAS.

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 3):** *"A inteligência artificial não atua em um vácuo; ela é alimentada por dados que refletem as escolhas, preconceitos e injustiças históricas da sociedade em que foi gerada."*  
  * *Uso no TCC:* Sustentar a premissa de que a qualidade e imparcialidade do modelo dependem umbilicalmente dos dados de origem.
* **Trecho 2 (p. 11):** *"A aparência de objetividade matemática dos algoritmos esconde o fato de que eles operam como reprodutores e amplificadores da seletividade penal inscrita em seus dados de treinamento."*  
  * *Uso no TCC:* Alertar contra a confiança ingênua em métricas quantitativas de bancada.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o desempenho/justiça de ML: **Sim** (dados viciados corrompem a decisão).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (algoritmos discriminatórios).
3. A preparação dos dados influencia o treinamento: **Sim** (necessidade de curadoria para desviesamento).
4. A representatividade dos dados influencia a generalização: **Sim** (amostragem policial assimétrica distorce a base).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (tese central do artigo).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (associação de atributos raciais/geográficos à criminalidade).
7. Um bom desempenho na avaliação não garante boa generalização: **Sim** (acurácia média mascara taxas brutais de erro em minorias).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (confiabilidade em decisões que afetam a liberdade).
9. Processos de Engenharia de Dados melhoram a qualidade: **Sim** (governança, curadoria e auditoria rigorosa de dados).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (opacidade e complexidade algorítmica).

---

## 10. Limitações
* **Declaradas pelos autores:** Foco exclusivo no ramo da justiça criminal e direitos fundamentais, com abordagem predominantemente jurídica e social.
* **Para o TCC:** Não apresenta implementações de código ou derivações matemáticas; deve ser utilizado para fundamentação crítica e estudo de caso de impacto real.

---

## 11. Lacunas e oportunidades
* Como formalizar métricas computacionais de equidade (*fairness metrics*) como testes automatizados em pipelines de Engenharia de Dados.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Foca na veracidade, imparcialidade e representatividade amostral. |
| Preparação dos dados | Sim | Curadoria obrigatória e auditoria antes do treino. |
| Engenharia de Dados | Parcialmente | Enquadrada na etapa de governança e custódia de datasets. |
| Viés | Sim | Racismo estrutural convertido em viés algorítmico. |
| Representatividade | Sim | Super-representação de populações vulneráveis em registros punitivos. |
| Generalização | Sim | O modelo generaliza preconceitos históricos para indivíduos inocentes. |
| Confiabilidade | Sim | Requisito basal para a legitimidade de sistemas preditivos. |
| Machine Learning | Sim | Modelos de escore de risco e reconhecimento facial. |

---

## 13. Ficha de leitura final
* **Referência:** ROSA, A. M.; GUASQUE, B. Inteligência artificial, vieses algorítmicos e racismo: o lado desconhecido da justiça algorítmica. *Opinión Jurídica*, v. 23, n. 50, a49, p. 1-23, 2024.
* **Problema:** Reprodução de racismo estrutural por modelos de IA na justiça criminal.
* **Objetivo:** Analisar as causas e consequências de dados enviesados e propor auditoria e governança de IA.
* **Metodologia:** Pesquisa bibliográfica exploratório-descritiva e estudo de casos judiciais.
* **Principais resultados:** Algoritmos operam com assimetria severa de falsos positivos quando treinados com históricos de segurança viciados.
* **Conceitos-chave:** Racismo Algorítmico, Viés em Dados, COMPAS, Feedback Loop, Falsa Neutralidade.
* **Contribuição para o TCC:** Fornece sustentação crítica e estudo de caso emblemático sobre viés nos dados e perda de confiabilidade.
* **Capítulo provável:** Capítulo 1 e Capítulo 4.
* **Citação mais importante:** *"A inteligência artificial não atua em um vácuo; ela é alimentada por dados que refletem as escolhas, preconceitos e injustiças históricas..."*
* **Palavras-chave:** Inteligência Artificial; Viés Algorítmico; Racismo Estrutural; COMPAS; Confiabilidade.

---

## 14. Avaliação final
* **Nota:** 8.5 / 10
* **Justificativa:** Excelente para embasamento ético-crítico e contextualização de viés e confiabilidade no Capítulo 1 e Capítulo 4.
* **Decisão:** **SIM** (Permanecer entre as referências fundamentais de viés e confiabilidade).
