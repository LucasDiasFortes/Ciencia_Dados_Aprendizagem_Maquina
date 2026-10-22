<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 1 — Conceitos e classificação de problemas

## Identificação

- Estudante ou equipe: Lucas Dias Fortes de Andrade
- Turma: Ciência de Dados e Aprendizagem de Máquina
- Data de realização: 21/10/2026
- Integrantes e contribuições (se em equipe): Lucas Dias

## Objetivos

Distinguir programação tradicional e Machine Learning, identificar atributos e alvo e diferenciar classificação, regressão e agrupamento.

## 1. Explicação com suas palavras

1. Como um modelo aprende com dados? Um modelo aprende analisando exemplos e identificando padrões nos dados durante o treinamento. Depois, usa esses padrões para fazer previsões ou tomar decisões sobre novos dados.
2. Qual diferença entre algoritmo e modelo? Um modelo aprende analisando exemplos e identificando padrões nos dados durante o treinamento. Depois, usa esses padrões para fazer previsões ou tomar decisões sobre novos dados.
3. Compare uma regra de bloqueio de palavra com um modelo de spam. Uma regra de bloqueio identifica palavras específicas e bloqueia mensagens que as contêm. Já um modelo de spam aprende com exemplos de mensagens para identificar padrões e classificar novas mensagens como spam ou não spam.
4. Dê um exemplo de atributo e alvo e defina o momento da previsão. para prever o preço de uma casa, os atributos podem ser o tamanho, a localização e o número de quartos. O alvo é o preço da casa. A previsão acontece quando o modelo recebe os atributos de uma casa nova e estima seu preço.

## 2. Quadro comparativo

| Critério | Supervisionado | Não supervisionado |
| --- | --- | --- |
| Presença de alvo no treino | os dados possuem alvo conhecido | os dados não possuem alvo definido |
| Pergunta que pode responder | Qual será o resultado? | Quais padrões existem nos dados? |
| Tipo de saída | Classe ou valor numérico | Grupos, padrões ou relações entre dados |
| Tarefas e exemplo | Classificação: identificar e-mails como spam ou não spam | Agrupamento: separar clientes em grupos com características semelhantes |
| Dados necessários | Dados de entrada com respostas corretas conhecidas | Dados de entrada sem rótulos ou respostas previamente definidas |
| Forma de avaliação | Comparar as previsões com os resultados reais, usando métricas como acurácia ou erro médio | Avaliar a qualidade dos grupos, sua separação e sua coerência |
| Limitação | Depende de dados rotulados, que podem ser caros ou difíceis de obter | Os grupos encontrados podem ser difíceis de interpretar e não representar categorias úteis |

## 3. Situações-problema

Os casos são cenários didáticos. Escolha **pelo menos cinco** e justifique sua classificação pelo significado do alvo ou por sua ausência.

| Caso | Situação-problema |
| --- | --- |
| 1 Educação | Prever evadiu/permaneceu com histórico rotulado de turmas anteriores. |
| 2 Saúde | Estimar o tempo de espera em minutos a partir de registros de atendimento. |
| 3 Comércio | Descobrir perfis de compra sem categorias prévias de clientes. |
| 4 Finanças | Prever inadimplente/adimplente com contratos e desfechos conhecidos. |
| 5 Segurança digital | Distinguir spam/legítima com mensagens já revisadas. |
| 6 Comércio | Estimar o total de vendas em reais na próxima semana. |
| 7 Educação | Agrupar perfis de acesso ao ambiente virtual sem rótulo de evasão. |
| 8 Saúde | Classificar exames em categorias previamente definidas por especialistas. |

| Caso escolhido | Alvo ou ausência de alvo | Categoria, quantidade ou grupos? | Abordagem e justificativa | Dados necessários e limitação |
| --- | --- | --- | --- | --- |
| Educação | Alvo | Categoria | Supervisionado — classificação, pois aprende com históricos de alunos cujo resultado já é conhecido. | Históricos rotulados de alunos. A qualidade depende dos dados e pode haver mudanças no perfil dos estudantes. |
| Saúde | Alvo: tempo de espera em minutos | Quantidade | 	
Supervisionado — regressão, pois prevê um valor numérico com base nos registros de atendimento | Dados de atendimentos anteriores com tempos registrados. A espera pode variar conforme a demanda e a equipe disponível |
| Comércio | Ausência de alvo: não existem categorias prévias de clientes | Grupos | Não supervisionado — agrupamento, pois identifica perfis de compra semelhantes sem rótulos definidos | Histórico de compras dos clientes. Os grupos encontrados podem não ser úteis para todas as decisões comerciais |
| Finanças | Alvo: inadimplente ou adimplente | Categoria | Supervisionado — classificação, pois utiliza contratos com desfechos conhecidos para classificar novos contratos | Dados de contratos anteriores e seus resultados. Dados desatualizados ou enviesados podem prejudicar as previsões |
| Comércio | Alvo: total de vendas em reais na próxima semana | Quantidade | Supervisionado — regressão, pois estima um valor numérico de vendas a partir de dados históricos | Registros de vendas anteriores. Promoções, sazonalidade e mudanças no mercado podem reduzir a precisão |

## 4. Raciocínio crítico

“Detectar fraude” define sozinho o tipo de aprendizado? Compare o uso de exemplos rotulados e a busca de operações atípicas sem rótulos. Detectar fraude pode ser supervisionado, quando o modelo aprende com exemplos rotulados de fraudes e operações legítimas, ou não supervisionado, quando identifica operações atípicas sem rótulos prévios

## Entrega

Salve este arquivo preenchido. Critérios: distinção conceitual, pertinência dos dados, justificativa e clareza. [Voltar ao início](README.md).
