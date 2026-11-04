<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# PBL integrador — Apoio à Permanência

## Identificação

- Estudante ou equipe: **Lucas Dias Fortes de Andrade**
- Turma: **Sistemas de Informação**
- Data de realização: **30/10/26**
- Integrantes e contribuições (se em equipe): **PREENCHER**

## Contexto

Uma instituição quer compreender sinais associados à evasão e oferecer apoio antes do fim do semestre. Público-alvo: estudantes matriculados e equipe de apoio acadêmico. O cenário é didático e a prática usa dados sintéticos.

**Questão norteadora:** como identificar situações que merecem atenção e oferecer apoio, reconhecendo erros do modelo e dificuldades que os dados não capturam?

## Proposta da equipe

### 1. Delimitação

- Problema e público: **A instituição de ensino enfrenta dificuldades para identificar estudantes que abandonam o curso antes do final do semestre. Os principais envolvidos são os estudantes matriculados e a equipe de apoio acadêmico.**
- Decisão que o resultado pode apoiar: **Identificar estudantes que podem precisar de acompanhamento e oferecer apoio acadêmico, orientação e acolhimento antes do encerramento do semestre.**
- Definição de evasão, unidade e horizonte: ** é o estudante deixar o curso antes do fim do semestre. A unidade é um estudante. A previsão é feita na semana 4, para o desfecho no fim do semestre.**

### 2. Perguntas de negócio

1. **Quais sinais observados estão influenciando os estudantes a saírem antes fim do semestre?**
2. **Quais estudantes apresentam sinais de possível evasão e poderiam se beneficiar de acompanhamento acadêmico?**

### 3. Dados necessários

| Dado | Papel no projeto | Disponível quando? | Origem pretendida | Necessidade e risco |
| --- | --- | --- | --- | --- |
| Frequencia | Atributo | Durante as primeiras quatro semanas do semestre | Sistema acadêmico ou diário de classe | Identificar a participação dos estudantes. Pode não representar totalmente o interesse ou aprendizado. |
| Nota | Atributo | Após as primeiras avaliações |Sistema de notas da instituição| Identificar dificuldades no desempenho acadêmico. Notas baixas podem ter diferentes causas. |
| Entrega | Atributo | 	Durante as primeiras quatro semanas do semestre | Plataforma de ensino ou ambiente virtual | Verificar a realização das atividades. Atrasos podem ocorrer por motivos pessoais ou técnicos. |
| Evasão | Alvo | No final do semestre | Sistema acadêmico | Identificar se o estudante abandonou o curso. |



Diferencie dados usados na simulação e dados que seriam necessários para uma investigação real: **Na simulação foi utilizado 3 atributos e 1 alvo, eles são: frequência, nota e entrega de atividades como atributos, e evasão como alvo. Esses dados são sintéticos, criados para representar situações hipotéticas dos estudantes. Em uma investigação real, seriam necessários dados coletados dos sistemas acadêmicos da instituição, com informações reais sobre frequência, desempenho, entrega de atividades e situação de matrícula.**

### 4. Abordagem e algoritmo

- Classificação, regressão ou outra formulação, com justificativa: ** Classificação, pois o objetivo é identificar se o estudante apresenta situação de possível saida do curso**
- Algoritmo introdutório escolhido: **Árvore de Decisão, pois é simples de compreender e permite identificar padrões relacionados à frequência, notas e entrega de atividades.**
- Referência simples: **a classificação pela classe mais frequente como modelo de comparação**

### 5. Avaliação

- Preparação, divisão e validação: **Organizar os dados, verificar informações ausentes e duplicadas, separar os dados de treinamento e teste e utilizar somente informações disponíveis até a quarta semana do semestre para realizar as previsões.**
- Métricas e razão da escolha: **Acurácia mede a porcentagem de previsões corretas realizadas pelo modelo.
Recall mede quantos estudantes que realmente evadiram foram identificados corretamente pelo modelo. Essa métrica é importante para evitar deixar de identificar estudantes que precisam de apoio.**
- Resultados efetivamente calculados e link da evidência: **Serão apresentados após a execução do algoritmo com os dados sintéticos.**
- Erros relevantes e consequências: **O modelo pode não identificar alguns estudantes que realmente irão sair ou sinalizar estudantes que permanecerão no curso. Por isso, os resultados devem ser analisados pela equipe acadêmica, sem decisões automáticas.**

### 6. Limites e proteção

- Por que os resultados não demonstram causalidade? ** Porque frequência, notas e entrega de atividades podem estar relacionadas à saida, mas não significam que sejam as causas do abandono. Existem outros fatores, como problemas financeiros, pessoais e familiares, que também podem influenciar.**
- Por que dados sintéticos não validam uso institucional? **Porque são dados criados artificialmente e não representam necessariamente a realidade dos estudantes. Eles servem para testar o funcionamento do algoritmo, mas não garantem resultados corretos em uma instituição real.**
- Que grupos podem ser mal representados? Como investigar isso com evidências apropriadas? **Estudantes que trabalham, possuem dificuldades financeiras ou têm acesso limitado à internet podem ser mal representados. Para investigar isso, seria necessário considerar relatos dos próprios estudantes.**
- Como minimizar dados, restringir acesso e definir retenção? **Utilizar somente os dados necessários, substituir nomes por códigos, permitir acesso apenas às pessoas autorizadas e excluir os dados quando não forem mais necessários para o projeto.**
- Como garantir revisão humana e contestação? **As previsões do modelo devem servir apenas como alertas. A equipe acadêmica deverá analisar cada situação individualmente, conversar com o estudante e permitir que ele corrija informações incorretas ou apresente sua situação.**

### 7. Recomendações de apoio

- Ação voluntária proposta: ** Oferecer acompanhamento acadêmico, monitoria, orientação individual e apoio aos estudantes que apresentarem dificuldades durante o semestre.**
- Como acolher estudantes não sinalizados pelo modelo: **Manter canais de atendimento disponíveis para todos os estudantes, permitindo que qualquer um solicite ajuda, mesmo que não tenha sido identificado pelo algoritmo como possível caso de evasão.**
- O que precisa ser verificado antes de aplicação real: **Verificar a qualidade dos dados, o funcionamento do algoritmo, a precisão das previsões, possíveis erros e preconceitos nos resultados, além de garantir a privacidade dos estudantes e a autorização da instituição.**

Previsões não são certezas. Priorize apoio e revisão humana, sem punições ou decisões automáticas prejudiciais.

## Apresentação de cinco minutos

| Tempo | Conteúdo | Responsável |
| --- | --- | --- |
| 1 minuto | Problema e dados | Lucas Dias |
| 2 minutos | Método e resultados | Lucas Dias |
| 1 minuto | Limitações | Lucas Dias |
| 1 minuto | Recomendações de apoio | Lucas Dias |

## Contribuições

| Integrante | Contribuição verificável |
| --- | --- |
| Lucas Dias | Preenchimento de todo o trabalho |

[Voltar ao início](README.md).
