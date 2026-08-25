---
title: Tipos de programas
description: Crie e gerencie tipos de programas que definem atributos e fluxos de status de membros para programas no Marketo Otimizer.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Tipos de programas

Os tipos de programas definem aspectos importantes de [programas](../marketing/programs.md) e seus membros, e distinguem tipos diferentes de programas de marketing entre si. Cada tipo de programa define as seguintes propriedades, que são herdadas para programas que usam o tipo de programa:

* **Atributos** - Os atributos descrevem os aspectos importantes do tipo de programa, como datas de evento e atributos de local.

* **Fluxo de status do programa** - Cada status é atribuído a uma etapa no tipo de programa (como 1, 2 ou 3). Os membros de um programa só podem mover de um status com o mesmo número de etapa (por exemplo, de _Não exibido_ para _Participou_) ou para um status com um número de etapa superior (por exemplo, de _Convidado_ para _Registrado_).

  Os status do programa são mutuamente exclusivos e lineares, portanto, uma pessoa só pode ter um valor de status por programa. Ao criar os status, pense em quais status você deseja permitir a movimentação entre eles. Por exemplo, se alguém não apareceu para um webinário, mas tem uma opção para participar sob demanda posteriormente, você gostaria que ele tivesse o mesmo número de status ou definisse sob demanda para um número de status mais alto, para que um membro do programa possa avançar para ele.

>[!NOTE]
>
>Se um tipo de programa for usado por pelo menos um programa, ele não poderá ser editado.

_Para definir um tipo de programa personalizado :_

1. Na navegação à esquerda [!DNL Adobe Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Tipos de programas]**.

   ![Acessar a lista de tipos de programas](./assets/program-types-list.png){width="800" zoomable="yes"}

1. Clique em **[!UICONTROL Criar tipo]** na parte superior direita.

1. Insira um **[!UICONTROL Nome]** exclusivo (obrigatório) e uma **[!UICONTROL Descrição]** (opcional).

   ![Criar tipo de programa](./assets/program-type-create.png){width="600" zoomable="yes"}

   >[!TIP]
   >
   >Incluir uma descrição é uma prática recomendada e torna a biblioteca de tipos de programa mais gerenciável.

1. Clique em **[!UICONTROL Criar tipo]**.

1. Adicione os **[!UICONTROL Atributos]** para o tipo de programa.

   Para cada atributo que você deseja adicionar:

   * Clique em **[!UICONTROL Adicionar atributo]**.
   * Escolha o **[!UICONTROL nome da API]** e insira o **[!UICONTROL Nome de exibição]**.
   * Clique em **[!UICONTROL Salvar]**.

   ![Atributos de tipo de programa](./assets/program-type-attributes.png){width="600" zoomable="yes"}

1. Defina as etapas para **[!UICONTROL Status do programa]**.

   Defina cada etapa que deseja incluir no fluxo:

   * Clique em **[!UICONTROL Adicionar etapa]**.
   * Insira um nome de status.
   * (Opcional) Clique em **[!UICONTROL Adicionar status]** e insira um nome de status adicional para incluir na etapa.

   Marque a caixa de seleção **[!UICONTROL Marcar como êxito]** para qualquer etapa que você deseja rastrear como uma execução de programa bem-sucedida.

   ![Status de tipo de programa](./assets/program-type-statuses.png){width="600" zoomable="yes"}

1. Clique em **[!UICONTROL Concluído]** para salvar suas alterações e retornar à lista de tipos de programas.