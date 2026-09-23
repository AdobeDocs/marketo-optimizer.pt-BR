---
title: Scoring Studio
description: Saiba mais sobre o Scoring Studio no Adobe Marketo Otimizer, incluindo a lista de modelos, a tela, as colunas de dimensão, os cartões de sinal, os segmentos de clientes potenciais e a publicação.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
source-git-commit: 7e3080b688415ef623cdbd57aa08ed43eb6fcd17
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 1%
---

# Scoring Studio

O Scoring Studio inclui uma lista de modelos, uma tela editável para cada modelo e a [Interface de chat do Colaborador](../agents/chat-interface.md). Use a tela para revisar ou ajustar dimensões e sinais diretamente, enquanto o Colaborador continua a propor alterações na linguagem natural ao seu lado. Para obter informações sobre como criar um modelo a partir de um prompt, consulte [_Criar modelos de pontuação personalizados_](../agents/lead-scoring-model.md).

## Lista de modelos {#model-list}

A lista de modelos é a exibição de aterrissagem do Scoring Studio. Ele mostra cada modelo de pontuação na sua instância do [!DNL Marketo Optimizer] como linhas em uma tabela ou como cartões, se você alternar para a exibição de grade.

![A lista de modelos do Scoring Studio mostra os modelos de pontuação ativos com suas dimensões, sinais e detalhes da última modificação.](./assets/scoring-studio-ui.png){width="800" zoomable="yes"}

| Coluna | Descrição |
| --- | --- |
| Nome | Selecione um nome de modelo para abri-lo na tela. |
| Status | _[!UICONTROL Ativo]_, _[!UICONTROL Rascunho]_ ou _[!UICONTROL Arquivado]_. |
| Dimensões | O número de dimensões no modelo. |
| Sinais | O número de sinais no modelo. |
| Última modificação | A data em que o modelo foi alterado pela última vez. |
| Última modificação feita por | A pessoa que alterou o modelo pela última vez. |
| Criado em | A data de criação do modelo. |
| Criado por | A pessoa que criou o modelo. |

Use o campo de pesquisa para localizar um modelo por nome ou filtrar a lista por status. Selecione o **[!UICONTROL Mais menu]** de uma linha para **[!UICONTROL Editar]**, **[!UICONTROL Duplicar]**, **[!UICONTROL Arquivar]** ou **[!UICONTROL Excluir]** um modelo.

Um modelo ativo é somente leitura. Para alterá-la, duplique-a e edite a duplicata. Em seguida, arquive o original e publique a cópia modificada.

## Tela do modelo {#model-canvas}

Selecionar um nome de modelo o abre na tela. Cada modelo aberto aparece como sua própria guia, para que você possa trabalhar em vários modelos. A tela é organizada em guias, incluindo **[!UICONTROL Regras]** e **[!UICONTROL Lead]**.

Na guia **[!UICONTROL Regras]**, cada dimensão no modelo é uma coluna na tela. Cada cabeçalho de coluna mostra o nome da dimensão e seu total de pontos em relação ao limite, por exemplo `20 / 30 pts`, com uma barra de progresso que é preenchida à medida que seus sinais contribuem com pontos.

![A tela da guia Regras mostra três colunas de dimensão, Envolvimento de email, Ajuste de perfil e Atividade recente, cada uma com cartões de sinal e pontos.](./assets/scoring-studio-model-rules-tab.png){width="700" zoomable="yes"}

Dentro de cada dimensão, cada sinal é exibido como um cartão mostrando seu nome, seu valor de ponto e sua frequência correspondente (por exemplo, `1 time / day`) ou `Static` para sinais baseados em atributos que não dependem da atividade.

Quando o Coworker detecta um padrão em várias atividades, ele pode combiná-los em uma única placa de sinal composta que resume cada condição.

## Configurar um sinal {#configure-signal}

Para revisar ou alterar um sinal, siga estas etapas.

1. Selecione **[!UICONTROL Editar rascunho]**.

1. Selecione um cartão de sinal na tela.

   O painel de propriedades é aberto no lado direito da tela.

   ![A tela da guia Regras mostra uma placa de sinal selecionada e seu painel de propriedades com tipo de sinal, tipo de atividade, condições e pontos.](./assets/scoring-studio-model-selected-signal.png){width="700" zoomable="yes"}

1. Selecione o ícone **[!UICONTROL Editar]** ( ![Ícone Editar](../assets/do-not-localize/icon-react-edit.svg) ) e atualize as propriedades de sinal:

   * Em **[!UICONTROL Signal]**, confirme o tipo de sinal (uma atividade ou um atributo) e a atividade ou atributo específico que ela pontuar.

   * Em **[!UICONTROL Acionar este em]**, defina as condições que devem ser atendidas.

     Adicione os itens a serem usados, como páginas específicas, e se **[!UICONTROL Qualquer um de]** ou **[!UICONTROL Todas de]** as condições devem ser verdadeiras.

   * Em **[!UICONTROL Pontos]**, defina quantos pontos o sinal contribui.

     Opcionalmente, defina um **[!UICONTROL Limite]** para limitar quantos pontos ele pode contribuir por pessoa. O colega de trabalho mostra um intervalo de pontos sugerido com base nos outros sinais no modelo.

   * Para sinais baseados em atividade, defina a **[!UICONTROL Frequência]** necessária antes dos pontos de premiação do sinal.

     Opcionalmente, defina uma porcentagem de **[!UICONTROL Declínio]** que reduza os pontos do sinal após um número definido de dias.

   * Habilite a opção **[!UICONTROL Evitar pontuar as mesmas ações duas vezes]** para atribuir pontos apenas uma vez por pessoa, independentemente de quantas vezes a atividade ocorra.

     Em vez disso, desative a opção para atribuir pontos sempre que a atividade ocorrer. Essa configuração está ativada por padrão.

1. Selecione **[!UICONTROL Salvar]** para aplicar suas alterações e retornar à tela.

## Segmento de lead {#lead-segment}

Cada modelo de pontuação classifica um segmento de lead, uma referência a uma lista de pessoas existente em vez das regras definidas no Scoring Studio. Quando o Colaborador cria um modelo, ele seleciona uma lista correspondente ou cria uma nova.

Para alterar a lista, selecione a guia **[!UICONTROL Lead]** e selecione **[!UICONTROL Alterar]** ao lado do segmento de lead.

![A guia Cliente Potencial mostra o cartão de segmento de cliente potencial com uma lista de pessoas referenciadas, um link Exibir lista de pessoas e um link Alterar.](./assets/scoring-studio-model-lead-tab.png){width="700" zoomable="yes"}

Um segmento de lead usa um dos dois tipos de lista:

* **Lista estática** — um conjunto fixo de pessoas capturadas quando a lista foi criada.
* **Smart list** — uma lista que reavalia suas regras de associação sempre que o modelo é executado, de modo que o segmento sempre reflete os critérios da lista.

A visualização do modelo mostra o nome do segmento, sua contagem de membros e um link **[!UICONTROL Exibir lista de pessoas]** que abre a lista diretamente. Para obter mais informações sobre o gerenciamento de listas, consulte [_Listas de pessoas_](../audiences/people-lists.md).

Se a lista referenciada estiver vazia ou for removida posteriormente, o modelo para de pontuar em vez de cair para todo o público-alvo. Nenhum cliente potencial será pontuado até que você atribua uma lista válida e não vazia.

Abaixo do segmento de lead, o cartão **[!UICONTROL Nome do campo de pontuação]** mostra o atributo de lead no qual o modelo grava sua pontuação. Por padrão, o nome do campo corresponde ao nome do modelo. Selecione **[!UICONTROL Editar]** para renomeá-lo.

## Publicar e agendar {#publish-schedule}

Quando o modelo estiver pronto, clique em **[!UICONTROL Publicar]**.

![O botão Publicar é exibido para um modelo de pontuação de rascunho.](./assets/scoring-model-publish.png){width="700" zoomable="yes"}

Escolha a frequência com que o modelo classifica seu público-alvo: diariamente, semanalmente ou mensalmente. Você também pode escolher uma opção manual para executar o modelo.

![As opções de agendamento mostram as opções de recorrência diária, semanal, mensal e manual para executar o modelo de pontuação.](./assets/scoring-model-publish-schedule-options.png){width="420" zoomable="no"}

Para obter o processo de publicação completo usando a [Interface de chat do colega](../agents/chat-interface.md), incluindo como [!DNL Marketo Optimizer] provisiona um campo de pontuação automaticamente, consulte [_Publicar um modelo de pontuação_](../agents/lead-scoring-model.md#publish-model).

As pontuações mais recentes são armazenadas em um campo provisionado que é sincronizado com sua instância [!DNL Marketo Engage].

![O campo de pontuação provisionado exibido no gerenciamento de campos do Marketo Engage](./assets/scoring-model-score-field-ame.png){width="800" zoomable="yes"}

## Usar pontuações em filtros {#filter-score}

Depois de [publicar um modelo](#publish-schedule), você poderá usar sua pontuação resultante como filtro ao criar públicos-alvo baseados em eventos e _Ouvir nós de um evento_, como uma condição de caminho dividido ou para associação à lista de pessoas.

A pontuação aparece no painel de filtro na categoria **[!UICONTROL Atributos da pessoa]**, rotulada com o nome do modelo ou com o [_Nome do campo de pontuação_](#lead-segment) personalizado que você atribuiu a ela. Insira esse nome no campo de pesquisa do painel de filtro para localizar a pontuação, arraste-o para a tela e defina seus critérios.

### Públicos-alvo e nós baseados em eventos {#scoring-model-event-audience}

Para usar um resultado de modelo de pontuação para filtrar um [público-alvo baseado em eventos](../audiences/event-based-audiences.md) ou [_Ouvir um nó_ de evento](../marketing/listen-for-event-nodes.md):

1. Clique em **[!UICONTROL Adicionar critérios de evento]**.

1. Na caixa de diálogo _[!UICONTROL Editar critérios do evento]_, selecione a guia **[!UICONTROL Filtros]**.

1. Insira o nome do modelo no campo de pesquisa e arraste a pontuação até a tela.

   ![A guia Filtros mostra um nome de modelo inserido no campo de pesquisa e a pontuação correspondente arrastada para a tela.](./assets/scoring-model-event-filter.png){width="700" zoomable="yes"}

1. Defina o operador e o valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Salvar]**.

### Condições de caminho dividido {#split-path-conditions}

Para usar um resultado de modelo de pontuação para definir condições de caminho para um [_nó](../marketing/split-merge-paths-nodes.md) de caminhos divididos_:

1. Clique em **[!UICONTROL Editar condição]** para o caminho do nó.

1. Na caixa de diálogo _[!UICONTROL Condições]_, digite o nome do modelo no campo de pesquisa e arraste a pontuação correspondente para a tela.

   ![A caixa de diálogo Condições mostra um nome de modelo inserido no campo de pesquisa e a pontuação correspondente arrastada para a tela.](./assets/scoring-model-split-path-condition.png){width="700" zoomable="yes"}

1. Defina o operador e o valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para salvar a condição do caminho.

### Associação à lista de pessoas {#scoring-model-people-lists}

Para gerenciar a associação de [lista de pessoas](../audiences/people-lists.md) usando um resultado de modelo de pontuação:

**Lista estática — Adicionar membros**

1. Abra a lista estática e clique em **[!UICONTROL Adicionar pessoas]**.

1. Na caixa de diálogo _[!UICONTROL Adicionar pessoas]_, digite o nome do modelo no campo de pesquisa e arraste a pontuação correspondente para a tela.

   ![A caixa de diálogo Adicionar pessoas mostra um nome de modelo inserido no campo de pesquisa e a pontuação correspondente arrastada para a tela.](./assets/scoring-model-static-list-add-people.png){width="700" zoomable="yes"}

1. Defina o operador e o valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para aplicar o filtro e qualificar as pessoas correspondentes na lista.

**Lista dinâmica — Definir regras de associação**

1. Abra a lista dinâmica e selecione a guia **[!UICONTROL Regras]**.

1. Clique em **[!UICONTROL Editar regras]**.

1. Na caixa de diálogo _[!UICONTROL Editar regras]_, digite o nome do modelo no campo de pesquisa e arraste o item de pontuação para a tela.

   ![A caixa de diálogo Editar regras mostra um nome de modelo inserido no campo de pesquisa e a pontuação correspondente arrastada para a tela.](./assets/scoring-model-dynamic-list-rules.png){width="700" zoomable="yes"}

1. Defina o operador e o valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para salvar a regra.

   A associação é atualizada automaticamente à medida que os registros de pessoa são avaliados em relação à regra.
