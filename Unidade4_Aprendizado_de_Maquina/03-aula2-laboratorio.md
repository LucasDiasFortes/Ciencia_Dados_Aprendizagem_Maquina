<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 2 — Registro do laboratório supervisionado

## Identificação

- Estudante ou equipe: **Lucas Dias Fortes de Andrade**
- Turma: **PREENCHER**
- Data de realização: **PREENCHER**
- Integrantes e contribuições (se em equipe): **PREENCHER**

## Percurso escolhido

- [ X] Python/Colab ou Jupyter.
- [ ] Orange Data Mining.

Use o [notebook de apoio](notebooks/laboratorio.ipynb) ou o [CSV sintético](dados/educacionais-sinteticos.csv). O CSV contém 600 registros fictícios. Atributos: `frequencia_sem4`, `nota_sem4`, `entregas_sem4`. Alvo: `evasao_fim_semestre` (0 permaneceu, 1 evadiu). As associações foram definidas pela simulação, sem validade empírica sobre estudantes reais.

## 1. Ambiente e reprodução

| Item | Registro |
| --- | --- |
| Ambiente e data | Colab|
| Versões das ferramentas/bibliotecas | Python: 3.13.18pandas: 2.2.3numpy: 2.4.6scikit-learn: 1.6.1 matplotlib: 3.10.0 |
| Semente aleatória | 42 |
| Caminho do notebook executado ou fluxo Orange | PREENCHER |
| Origem dos dados e condição sintética | PREENCHER |

## 2. Problema e preparação

- Pergunta de negócio: **quais estudantes têm maior risco de evadir até o fim do semestre, com base nos dados da semana 4?**
- Unidade de análise e horizonte: **cada linha é um estudante. Os atributos são medidos na semana 4 e o alvo é observado no fim do semestre.**
- Atributos disponíveis no instante da previsão: **frequencia_sem4, nota_sem4 e entregas_sem4**
- Variável-alvo e sua natureza: **evasao_fim_semestre, binária e categórica (0 permaneceu, 1 evadiu)**
- Ausências e outros problemas encontrados: **30 ausências em nota_sem4 (5%). Nas demais colunas, não há ausências.**
- Tratamentos e conjunto usado para aprendê-los: **Imputação das 30 ausências de nota_sem4 (5% dos registros) pela mediana. A mediana é aprendida apenas no conjunto de treino (480 registros, com 23 ausências) e aplicada ao treino e ao teste (7 ausências), por meio de um Pipeline com SimpleImputer(strategy="median").**

## 3. Desenvolvimento e teste

- Método de divisão e justificativa: **divisão holdout 80/20 com train_test_split, estratificada por evasao_fim_semestre e com random_state=SEED. A estratificação mantém a proporção de evasão (cerca de 41%) nos dois conjuntos, e a semente torna a divisão reproduzível.**
- Quantidades de treino e teste: **480 no treino e 120 no teste**
- Procedimento de validação no treino: **Validação cruzada estratificada com 5 folds (random_state=SEED) só nos 480 registros de treino, com acurácia como métrica. A mediana da imputação foi reaprendida em cada rodada, dentro do Pipeline.**
- Parâmetros da árvore e como foram escolhidos: **Comparei max_depth = 2, 3, 5 e None. Escolhi max_depth=[X] pela maior acurácia média de validação ([X]) com baixo desvio ([X]). Demais parâmetros no padrão.**
- Como o teste ficou fora da seleção: **A divisão foi feita antes de qualquer modelagem. Toda a seleção usou só o treino, e o teste foi usado uma única vez, no final.**

### Alternativa Orange

Confira o alvo como categórico. Registre as conexões: File/Select Columns → Test & Score (Data), Tree → Test & Score (Learner), Test & Score → Confusion Matrix (Evaluation Results). Data Table permite inspeção. Se usar Preprocess, conecte o preprocessor ao learner para ajustar transformações dentro do treino. Não use apenas `Test on train data` como avaliação final.

**Fluxo e método de avaliação realmente utilizados:** Não usei Orange. Usei Python no Colab

Se comparar configurações, use validação no treino e reserve teste independente. Documente em Test & Score as entradas Data e Test Data, quando utilizadas.

## 4. Resultados calculados de classificação

| Modelo | Configuração | Acurácia de treino | Acurácia de validação e dispersão | Acurácia de teste |
| --- | --- | --- | --- | --- |
| Referência | DummyClassifier(most_frequent) | 0,590 | 0,590 ± 0,005 | 0,592 |
| Árvore final | max_depth=3, imputação por mediana, random_state=SEED | 0,756 | 0,702 ± 0,028 | 0,733 |

Não invente valores. Se sua ferramenta não produziu uma medida, registre “não calculada” e explique.

**Matriz: linhas reais e colunas previstas; classe positiva = 1.**

| Real / previsto | Permaneceu (0) | Evadiu (1) |
| --- | --- | --- |
| Permaneceu (0) | 60 (TN) | 11 (FP) |
| Evadiu (1) | 21 (FN) | 28 (TP) |

- Acurácia calculada manualmente pela matriz: **(TP + TN) / total = (28 + 60) / 120 = 88 / 120 = 0,733. Confere com o Colab.**
- Sensibilidade da classe 1: **TP / (TP + FN) = 28 / (28 + 21) = 28 / 49 = 0,571 (cerca de 57%)**
- Comparação com referência: **A árvore obteve 0,733 de acurácia no teste contra 0,592 da referência, ganho de cerca de 14 pontos percentuais. A referência nunca identifica evasão (sensibilidade 0), enquanto a árvore identifica cerca de 57% dos evadidos. Treino (0,756), validação (0,702) e teste (0,733) são próximos, sem sinal forte de sobreajuste.**
- Consequências dos falsos positivos: **Falsos positivos (11): estudantes que permaneceriam, mas foram marcados como risco. Custo: apoio ou contato desnecessário, uso de recursos da equipe e possível rotulação indevida do estudante.**
- Consequências dos falsos negativos: **Falsos negativos (21): estudantes que evadiram sem serem identificados. É o erro mais grave aqui, porque eles não recebem apoio a tempo. Com 21 FN contra 28 TP, o modelo deixa passar cerca de 43% dos evadidos.**
- Interpretação do gráfico e da árvore: **A raiz da árvore usa nota_sem4 <= 6,207, indicando que a nota da semana 4 foi o atributo que mais separou evasão de permanência no treino. Notas baixas combinadas com frequência baixa (≤ 64,4%) e poucas entregas (≤ 3,5) formam a folha de maior risco (54 de 61 evadidos). Notas altas com frequência alta formam o grupo mais seguro (84 de 84 permaneceram). A folha de nota baixa com frequência alta é mista (87 e 58), o que explica parte dos falsos negativos.**

![Árvore de decisão](assets/arvore.png)


## 5. Experimentos no treino

Compare parâmetros usando apenas treino/validação. Após conhecer o teste, uma nova seleção exige novo teste independente para avaliação final.

| Experimento | Alteração | Resultado de validação | Interpretação |
| --- | --- | --- | --- |
| 1 | PREENCHER | PREENCHER | PREENCHER |
| 2 | PREENCHER | PREENCHER | PREENCHER |

Responda:

1. Como a profundidade e o tamanho das folhas podem afetar o sobreajuste? **PREENCHER**
2. Retirar um atributo e observar mudança no desempenho prova causalidade? **PREENCHER**
3. Se 95% permanecem, o que acontece com um modelo que sempre prevê permanência? **PREENCHER**

## 6. Regressão — seção independente

Execute a seção da biblioteca no notebook ou registre o procedimento equivalente em Orange. Dados também sintéticos. Alvo numérico: empréstimos por semana.

| Item | Registro |
| --- | --- |
| Atributos e alvo | PREENCHER |
| Divisão e preparação | PREENCHER |
| MAE do modelo e unidade | PREENCHER |
| MAE da referência | PREENCHER |
| R² do teste | PREENCHER |
| Interpretação do gráfico observado/previsto | PREENCHER |
| Interpretação dos resíduos | PREENCHER |
| Limitação de extrapolação | PREENCHER |

Explique por que R² não é porcentagem de acertos: **PREENCHER**

## 7. Evidências e conclusão

- Link relativo do notebook/fluxo: **PREENCHER**
- Links das imagens, se houver: **PREENCHER**
- Principal aprendizado: **PREENCHER**
- Limitações de generalização e vieses possíveis: **PREENCHER**
- Cuidados com privacidade e uso responsável: **PREENCHER**

Para inserir uma imagem salva, use `![Matriz de confusão](assets/minha-matriz.png)` e confira se o arquivo existe. Mostre apenas dados sintéticos.

[Voltar ao início](README.md).
