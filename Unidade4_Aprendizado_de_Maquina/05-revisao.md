<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Questões de revisão — Registro individual

## Identificação

- Estudante ou equipe: **Lucas Dias Fortes de Andrade**
- Turma: **Sistemas de informação**
- Data de realização: **04/11/26**
- Integrantes e contribuições (se em equipe): **PREENCHER**

Responda com suas palavras e apresente os cálculos quando solicitados. Os números dos exercícios manuais não são os resultados do laboratório.

## 1. Explique a diferença entre regra programada para bloquear uma palavra e modelo de spam treinado com exemplos.

**Resposta:** No boquear uma palavra é por ume pessoa que escreve o que quer que seja bloqueado, já o spam aprende com exemplos de mensagens classificadas como spam

## 2. Por que codificar evadiu/permaneceu como 1/0 não transforma classificação em regressão?

**Resposta:** Porque o objetivo continua sendo classificar o estudante em duas categorias: evadiu ou permaneceu. Os números 1 e 0 representam apenas os rótulos das classes, não valores numéricos que o modelo precisa prever continuamente.

## 3. Uma biblioteca quer estimar empréstimos e descobrir perfis. Que tarefas correspondem a cada pergunta?

**Resposta:** Estimar a quantidade de empréstimos é uma tarefa de regressão, pois envolve prever valores numéricos. Já descobrir perfis de usuários é uma tarefa de agrupamento, pois busca reunir pessoas com características semelhantes.

## 4. O que são atributo, alvo e unidade de análise no laboratório educacional?

**Resposta:** Atributos são as informações utilizadas pelo modelo, como frequência e notas. O alvo é aquilo que o modelo deseja prever, como evasão ou permanência. A unidade de análise é cada estudante observado.

## 5. Por que calcular a mediana antes de dividir os dados pode invalidar a avaliação?

**Resposta:** Porque calcular a mediana antes da divisão dos dados pode causar vazamento de informações do conjunto de teste para o treinamento, comprometendo a avaliação do modelo.

## 6. Em uma matriz didática com TN=80, FP=5, FN=10, TP=5, calcule acurácia e sensibilidade. O resultado é suficiente para aprovar o modelo?

**Resposta:** A acurácia é de 85% e a sensibilidade é de 33,33%. Esse resultado não é suficiente para aprovar o modelo, pois ele identifica poucos casos positivos e pode deixar muitos estudantes em risco sem identificação.

## 7. Valores reais 100, 120, 140 e previsões 110, 115, 130. Calcule MAE e informe a unidade se o alvo for vendas em reais.

**Resposta:** s erros absolutos são calculados pelas diferenças entre os valores reais e os previstos: |100 − 110| = 10, |120 − 115| = 5 e |140 − 130| = 10. Somando os resultados e dividindo pela quantidade de valores, temos: MAE = (10 + 5 + 10) ÷ 3 = 25 ÷ 3 ≈ R$ 8,33. Isso significa que o modelo apresenta um erro médio de aproximadamente R$ 8,33 nas previsões.
## 8. Um R² de -0,2 significa “20% de acertos negativos”? Explique.

**Resposta:** Não. Um R² de -0,2 significa que o modelo apresenta um desempenho pior do que utilizar a média dos valores reais para fazer as previsões. Não representa uma porcentagem de acertos negativos.

## 9. Uma árvore tem acurácia 1,00 no treino e 0,65 na validação. Que hipótese investigar e como?

**Resposta:** Deve-se investigar o sobreajuste (overfitting), pois o modelo pode ter aprendido muito bem os dados de treinamento, mas apresentar dificuldades com novos dados. Uma forma de verificar isso é limitar a profundidade da árvore e comparar os resultados na validação.

## 10. Por que escolher a profundidade pelo teste prejudica a estimativa final?

**Resposta:** Porque o conjunto de teste deve ser utilizado apenas na avaliação final. Escolher a profundidade utilizando esses dados pode comprometer a imparcialidade e a confiabilidade dos resultados.

## 11. Baixa frequência associada à evasão demonstra causa? Proponha explicação alternativa.

**Resposta:** Não, pois uma associação não significa necessariamente causa. Uma possível explicação é que dificuldades financeiras ou problemas familiares podem provocar tanto as faltas quanto a evasão escolar.

## 12. Um modelo sinaliza um estudante como possível evasão. Que ação responsável pode ser adotada?

**Resposta:** A instituição pode entrar em contato com o estudante para conversar, entender suas dificuldades e oferecer apoio pedagógico e social. O modelo deve servir como uma ferramenta de ajuda, e não como motivo para punição ou discriminação.

## Fontes adicionais consultadas

**Material da disciplina e ajuda de pesquisa em site do google e iA**

[Voltar ao início](README.md).
