# Fichamento e Análise de Artigo para o TCC

**Tema do TCC:** A Influência da Engenharia de Dados na Qualidade dos Dados para Treinamento de Modelos de Machine Learning: uma revisão bibliográfica  
**Narrativa Central:** Dados → Qualidade dos dados → Preparação/Tratamento → Representatividade → Viés → Treinamento → Generalização → Confiabilidade

---

## 1. Identificação
* **Título:** Viés racial em sistemas de inteligência artificial: desafios para a responsabilidade civil e a necessidade de parametrização do risco
* **Autores:** Gustavo Silveira Borges; José Luiz de Moura Faleiros Júnior
* **Ano:** 2023 (Maio/Ago. 2023)
* **Instituição/País:** Universidade do Extremo Sul Catarinense (UNESC) e Universidade de São Paulo (USP/UFMG), Brasil.
* **Local de publicação:** *Revista IBERC*, v. 6, n. 2, p. 100-128.
* **DOI / Link:** `https://doi.org/10.37963/iberc.v5i2.237` (ISSN: 2675-3979)
* **Tipo de publicação:** Artigo científico em periódico especializado.
* **Tipo de pesquisa/metodologia:** Pesquisa analítico-dedutiva e dogmática baseada em revisão bibliográfica e regulação normativa comparada (AI Act europeu).

---

## 2. Objetivo do artigo
* **Problema investigado:** A responsabilização civil por danos causados por sistemas automatizados de IA que operam com viés racial decorrente da **omissão ou negligência na adequada curadoria e preparação dos dados de treinamento**.
* **Objetivo principal:** Investigar os fundamentos da responsabilidade civil por atos discriminatórios de modelos de IA e sustentar que a curadoria ativa de dados é um dever técnico e jurídico inescusável para quem desenvolve e treina modelos preditivos.
* **Pergunta/Hipótese:** De que maneira a conduta omissiva de quem não realiza a devida preparação, limpeza e balanceamento dos dados de treinamento gera responsabilidade jurídica pelos erros discriminatórios do modelo?

---

## 3. Principais conceitos
* **Curadoria de Dados (*Data Curation*):** Processo estruturado de coleta seletiva, saneamento, validação e verificação ética dos dados destinados ao treinamento de algoritmos.
* **Dano por Conduta Omissiva na Preparação de Dados:** O entendimento de que a falha em tratar, auditar e balancear os dados de entrada constitui negligência técnica que gera o dever de indenizar.
* **Parametrização do Risco:** Metodologia de governança que classifica aplicações de IA por graduação de risco (inaceitável, alto, moderado e mínimo), impondo exigências estritas de qualidade de dados para sistemas de alto impacto.
* **Governança no Ciclo de Vida dos Dados:** Exigência de rastreabilidade, documentação (*Datasheets for Datasets*) e auditoria contínua desde a ingestão dos dados brutos.

---

## 4. Metodologia
* **Abordagem:** Dedutiva, analítica e dogmática no campo da responsabilidade civil comparada.
* **Fontes:** Doutrina de responsabilidade civil brasileira, regulamentações internacionais de IA (AI Act da União Europeia) e literatura técnica sobre aprendizado de máquina.
* **Procedimento:** Demonstração do nexo de causalidade entre a omissão na Engenharia e Curadoria de Dados e o dano provocado pela predição do modelo treinado.

---

## 5. Principais resultados
* **Resultado 1 (A Omissão na Camada de Dados):** O artigo demonstra que os algoritmos não possuem vontade própria nem preconceito inerente; os danos decorrem diretamente da conduta omissiva humana e institucional de desenvolvedores que treinam modelos com bases brutas sem a devida curadoria.
* **Resultado 2 (Dever de Diligência Técnica):** A preparação, o saneamento e o teste de representatividade nos dados de treinamento são caracterizados como deveres fundamentais de diligência em Engenharia de Software.
* **Resultado 3 (A Rastreabilidade como Salvaguarda):** A documentação rigorosa da esteira de Engenharia de Dados é o principal meio de demonstrar a conformidade e a confiabilidade de um sistema de IA.
* **Importância para o TCC:** Prova que a Engenharia de Dados e a Qualidade de Dados são requisitos de conformidade técnica e operacional indispensáveis, cuja negligência compromete a viabilidade e a segurança do software.

---

## 6. Relação com o meu TCC
* **Classificação:** **COMPLEMENTAR / IMPORTANTE**
* **Justificativa:** Fornece a justificativa institucional e de governança para o rigor técnico na Engenharia de Dados, demonstrando que a preparação de dados não é um mero passo preliminar, mas uma obrigação técnica e jurídica.

---

## 7. Em qual parte do TCC ele pode ser utilizado?
* **Capítulo 1 (Justificativa do TCC):** Para reforçar a relevância profissional e social da Engenharia de Dados na garantia de sistemas éticos e em conformidade regulatória.
* **Capítulo 2 & Capítulo 4:** Para justificar a importância da documentação e governança de dados de treinamento (*Datasheets for Datasets*).

---

## 8. Evidências e citações úteis
* **Trecho 1 (p. 101):** *"O dano pode ocorrer pela ação omissiva de quem não realiza adequada curadoria de dados que conduzem ao viés algorítmico."*  
  * *Uso no TCC:* Destacar a responsabilidade do engenheiro de dados no tratamento prévio da base.
* **Trecho 2 (p. 115):** *"A qualidade dos dados de treinamento e a documentação do processo de governança são as principais salvaguardas para demonstrar a diligência técnica e a conformidade dos sistemas de inteligência artificial."*  
  * *Uso no TCC:* Vincular qualidade de dados à governança e confiabilidade de software.

---

## 9. Pontos de convergência com a narrativa do TCC
1. A qualidade dos dados influencia o sistema: **Sim** (dados mal curados tornam o sistema defeituoso).
2. Dados inadequados podem produzir modelos inadequados: **Sim** (indução de decisões discriminatórias).
3. A preparação dos dados influencia o treinamento: **Sim** (a curadoria ativa de dados é dever inescusável).
4. A representatividade dos dados influencia a generalização: **Sim** (bases assimétricas geram erros injustos).
5. Vieses presentes nos dados podem ser reproduzidos pelos modelos: **Sim** (o modelo reproduz a omissão da base).
6. Modelos podem aprender padrões inadequados ou correlações espúrias: **Sim** (discriminação estatística).
7. Um bom desempenho na avaliação não isenta responsabilidade: **Sim** (acurácia global com dano individual).
8. A qualidade dos dados influencia a confiabilidade dos sistemas: **Sim** (confiabilidade legal e funcional).
9. Processos de Engenharia de Dados melhoram a qualidade: **Sim** (governança e curadoria ativas).
10. Problemas nos dados permanecem mesmo não imediatamente visíveis: **Sim** (opacidade decisória sem rastreabilidade).

---

## 10. Limitações
* **Declaradas pelos autores:** Enfoque estrito na responsabilidade civil e nas diretrizes regulatórias europeias/brasileiras.
* **Para o TCC:** Artigo teórico-jurídico; deve ser utilizado para enriquecer a justificativa e as boas práticas de governança de dados.

---

## 11. Lacunas e oportunidades
* Como traduzir as obrigações regulatórias de curadoria em testes automatizados de qualidade de dados dentro de pipelines de CI/CD.

---

## 12. Comparação conceitual
| Conceito | O artigo aborda? | Como? |
| :--- | :--- | :--- |
| Qualidade dos dados | Sim | Requisito regulatório essencial para sistemas de alto impacto. |
| Preparação dos dados | Sim | Curadoria de dados como dever de conduta técnica diligente. |
| Engenharia de Dados | Parcialmente | Situada na esteira de governança, coleta e saneamento da base. |
| Viés | Sim | Viés racial e discriminação algorítmica. |
| Representatividade | Sim | Exigência de datasets inclusivos e balanceados. |
| Generalização | Parcialmente | Ausência de erros lesivos em subpopulações. |
| Confiabilidade | Sim | Parâmetro de conformidade e mitigação de risco civil. |
| Machine Learning | Sim | Sistemas preditivos e de decisão automatizada. |

---

## 13. Ficha de leitura final
* **Referência:** BORGES, G. S.; FALEIROS JÚNIOR, J. L. M. Viés racial em sistemas de inteligência artificial: desafios para a responsabilidade civil e a necessidade de parametrização do risco. *Revista IBERC*, v. 6, n. 2, p. 100-128, 2023.
* **Problema:** Responsabilização jurídica por danos discriminatórios causados por IA devido a falhas na curadoria de dados.
* **Objetivo:** Propor critérios de parametrização de risco e demonstrar o dever de curadoria de dados de treino.
* **Metodologia:** Pesquisa analítico-dedutiva no campo da responsabilidade civil comparada.
* **Principais resultados:** A omissão na preparação de dados de treinamento configura falha técnica geradora de responsabilidade civil.
* **Conceitos-chave:** Curadoria de Dados, Viés Algorítmico, Responsabilidade Civil, Parametrização do Risco, Governança.
* **Contribuição para o TCC:** Sustenta a curadoria e a Engenharia de Dados como dever de qualidade no desenvolvimento de software.
* **Capítulo provável:** Capítulo 1 (Justificativa) e Capítulo 4 (Confiabilidade e Governança).
* **Citação mais importante:** *"O dano pode ocorrer pela ação omissiva de quem não realiza adequada curadoria de dados que conduzem ao viés algorítmico."*
* **Palavras-chave:** Curadoria de Dados; Responsabilidade Civil; Viés Algorítmico; Governança de IA.

---

## 14. Avaliação final
* **Nota:** 8.0 / 10
* **Justificativa:** Excelente referência para a seção de Justificativa e Governança, ancorando a relevância da curadoria de dados sob uma ótica de responsabilidade técnica profissional.
* **Decisão:** **SIM** (Permanecer como referência complementar qualificada).
