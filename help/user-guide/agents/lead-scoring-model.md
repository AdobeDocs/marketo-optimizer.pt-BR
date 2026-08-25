---
title: Criar modelos de pontuação personalizados
description: Crie, visualize e publique modelos de pontuação de lead personalizados no Marketo Otimizer usando a habilidade do Scoring Studio na interface de bate-papo do Colaborador.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Criar modelos de pontuação personalizados

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="Use a habilidade Scoring Studio para criar, configurar e publicar modelos de pontuação de lead personalizados por meio da interface de bate-papo do Colaborador."

A habilidade [_Scoring Studio_](./skills.md#scoring-signals) em [!DNL Adobe Marketo Optimizer] fornece uma solução de pontuação de cliente potencial nativa de IA que permite criar, configurar e publicar modelos de pontuação de cliente potencial. O estúdio combina um fluxo de trabalho orientado por agentes com uma interface visual — é possível criar modelos de pontuação por meio de prompts de linguagem natural na [interface de chat do Coworker](./chat-interface.md) ou interagindo diretamente com os controles da interface.

* **Habilidade** - `scoring-studio`
* **Invocação** - Use um comando de barra para abrir o Scoring Studio. Por exemplo: _&quot;abrir Scoring Studio.&quot;_
* **Leituras/gravações em** - [!DNL Marketo Optimizer] serviço de pontuação; lê [!DNL Marketo Engage] campos de cliente potencial e tipos de atividade

No lançamento, o Colaborador busca automaticamente o contexto relevante — incluindo tipos de atividade, campos de cliente potencial, listas de pessoas e listas de pontuação existentes — para fundamentar suas sugestões em seus dados.

![Scoring Studio iniciado na interface de chat do Colaborador](./assets/scoring-studio.png){width="700" zoomable="yes"}

## Criar um modelo de pontuação {#create-model}

Quando você abre o Scoring Studio, o Colaborador propõe um modelo de pontuação de exemplo relevante pré-preenchido com uma lista estática e um conjunto de atividades pontuadas. Você pode aceitar esse ponto de partida sugerido ou fornecer seu próprio prompt para definir um modelo personalizado.

### Visualizar o modelo {#preview-model}

Depois de fornecer um prompt, o Coworker gera uma pré-visualização do modelo antes de fazer quaisquer alterações. A visualização é exibida:

* Dimensões de pontuação em uso
* Atributos e atividades que estão sendo pontuados
* Listas estáticas ou smart lists aplicadas como segmentos
* Um resumo da meta do modelo, do segmento alvo e dos sinais primários

Você pode revisar a visualização e optar por criar o modelo com base nele ou continuar refinando o chat antes de finalizar.

### Estrutura do modelo {#model-structure}

O modelo criado está organizado em _dimensões_ e _sinais_. Você pode configurar cada sinal usando o painel de propriedades na interface do usuário:

* **Tipo de sinal** — baseado em atividade ou em atributo
* **Atividade ou atributo** — O item específico a ser pontuado
* **Parâmetros de sinal** — Configurações ajustáveis para o sinal

Você pode construir e configurar modelos inteiramente por meio do Co-worker usando linguagem natural ou interagir diretamente com os controles da interface.

## Publicar um modelo de pontuação {#publish-model}

Quando seu modelo estiver finalizado, instrua o Colaborador a publicá-lo. O processo de publicação trata automaticamente do seguinte:

| Etapa | O que acontece |
|---|---|
| **Compilação de regras** | Todas as regras de pontuação são compiladas e validadas |
| **Criação da tarefa de pontuação** | Uma tarefa de pontuação programada é criada e configurada para ser executada diariamente |

Após a publicação, você também tem a opção de acionar uma execução manual para processar pontuações imediatamente.

## Exibir resultados de pontuação {#view-results}

Quando uma execução de pontuação é concluída, as pontuações são gravadas de volta em [!DNL Marketo Engage] por meio do processo de importação de clientes potenciais. Após a conclusão da importação, as pontuações atualizadas podem ser verificadas diretamente no [!DNL Marketo Engage].

Após cada execução, é possível exibir um resumo dos resultados que mostra:

* Quantas pessoas foram pontuadas
* A pontuação individual muda por pessoa

Um log de auditoria está disponível para revisar detalhes de execução adicionais.
