---
title: Fazer um nó de ação
description: Configurar um nó Realizar uma ação no Marketo Otimizer para adicionar, remover ou atualizar pessoas, listas, programas e destinos, ou enviar mensagens, quando eles atingirem o nó em uma jornada de pessoa.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 0%

---

# Executar um nó de ação

Em uma jornada de pessoa, use uma ação em pessoas quando quiser aplicar uma alteração a todas as pessoas no caminho do nó.

## Ações e restrições {#actions}

| Ação | Restrições |
| ------ | ----------- |
| **[!UICONTROL Ativar para destino]** | <li>Selecionar ou criar uma lista estática <li>Se a lista não tiver um destino ativado, ative-a para um ou mais destinos |
| **[!UICONTROL Adicionar pessoa à jornada]** | <li>Selecionar uma jornada agendada ou ativa <li>Os critérios de público-alvo da jornada de direcionamento não são aplicados |
| **[!UICONTROL Adicionar à lista]** | <li>Criar uma nova lista estática ou selecionar uma existente |
| **[!UICONTROL Adicionar à lista do Marketo Engage]** | <li>Selecionar uma lista estática no Marketo Engage |
| **[!UICONTROL Alterar valor de dados]** | <li>Selecionar atributo de pessoa <li>Definir novo valor |
| **[!UICONTROL Alterar status no programa]** | <li>Selecionar programa<li>Selecionar novo status |
| **[!UICONTROL Alterar status de membro do webinário]** | <li>Selecionar programa<li>Selecionar novo status |
| **[!UICONTROL Remover da lista]** | <li>Selecionar lista estática <li>Ignora a pessoa se não for um membro atualmente |
| **[!UICONTROL Remover da lista do Marketo Engage]** | <li>Selecionar uma lista estática no Marketo Engage <li>Ignora a pessoa se não for um membro atualmente |
| **[!UICONTROL Remover pessoa da jornada]** | <li>Selecionar uma jornada em tempo real <li>Ignora a pessoa se não for atualmente um membro da jornada do público alvo |
| **[!UICONTROL Solicitar campanha do Marketo Engage]** | <li>Selecionar uma campanha do Marketo Engage |
| **[!UICONTROL Enviar Email]** | <li>Criar, editar ou usar um email personalizado com IA <li>Otimização do tempo de envio (opcional) |
| **[!UICONTROL Enviar WhatsApp]** | <li>Selecionar uma mensagem do WhatsApp |

<!-- 
removed? | **[!UICONTROL Change Program Data]** | <li>Select program attribute <li>Set new value | 
-->

## Adicionar um nó de ação {#add-an-action-node}

1. Navegue até a tela de jornada.

1. Clique no ícone de adição ( **+** ) em um caminho e escolha **[!UICONTROL Executar uma ação]**.

   ![Clique em adicionar ícone no caminho da jornada](./assets/person-journey-canvas-add-node.png){width="200"}

1. Nas propriedades do nó à direita, selecione uma ação na lista e defina os valores para a ação.

+++Ativar para o destino

Use esta ação para adicionar pessoas a uma lista estática e ativar essa lista para um destino diretamente da sua jornada. Você pode usar uma lista estática existente ou criar uma especificamente para a jornada.

>[!PREREQUISITES]
>
>Você deve ter um ou mais [destinos configurados](../audiences/destinations.md) para sua sandbox [!DNL Marketo Optimizer] antes de configurar um nó de jornada _Ativar para destino_.

![Executar uma ação - Ativar para o destino](./assets/person-action-node-activate-to-destination.png){width="450"}

Em **[!UICONTROL Adicionar à lista]**, escolha uma das seguintes opções:

* **[!UICONTROL Criar]** — Crie uma nova lista estática e adicione pessoas a ela. A lista está disponível imediatamente em **[!UICONTROL Listas de pessoas]**.

  Selecione um programa pai para a lista e insira um **[!UICONTROL Nome]** (obrigatório) e uma **[!UICONTROL Descrição]** (opcional). Clique em **[!UICONTROL Criar]** para adicionar a nova lista do nó.

  ![Criar uma lista estática para usar no nó de jornada](./assets/person-action-node-destination-create-list.png){width="375"}

* **[!UICONTROL Selecionar]** — Selecione uma lista estática existente na qual você deseja adicionar pessoas que acessam o nó.

  Marque a caixa de seleção da lista estática existente e clique em **[!UICONTROL Salvar]**.

  ![Selecione uma lista estática para usar no nó de jornada](./assets/person-action-node-destination-select-list.png){width="700" zoomable="yes"}

Qualquer pessoa que alcançar o nó é adicionada à lista estática selecionada, mas a ação não é concluída até que a lista seja ativada para um destino:

* Se a lista selecionada já estiver ativada, seus destinos aparecerão em **[!UICONTROL Destinos]** e a ação estará pronta.
* Caso contrário, será exibida uma mensagem _No mínimo, um destino é necessário_. Clique em **[!UICONTROL Ativar lista para destino]**, selecione o destino e clique em **[!UICONTROL Salvar]**. Clique em **[!UICONTROL Ativar]** no diálogo de confirmação.

![Destinos configurados disponíveis para ativação](../audiences/assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

Quando a ativação for concluída, o destino aparecerá em **[!UICONTROL Destinos]** e a ação estará pronta. Você pode ativar a lista para destinos adicionais, se necessário.

Qualquer pessoa que alcançar o nó é adicionada à lista estática selecionada, que é ativada para o destino escolhido, para que seja adicionada a esse público-alvo de destino e, por sua vez, a qualquer campanha que o público-alvo alimente.

+++

+++[!UICONTROL Adicionar pessoa à jornada]

Use esta ação para adicionar pessoas a outras jornadas agendadas ou ativas. As pessoas adicionadas por meio dessa ação são imediatamente adicionadas ao público-alvo da jornada de destino; os critérios de público-alvo da jornada de destino não são aplicados.

![Realizar uma ação - Adicionar pessoa à jornada](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL Adicionar à lista]

Use esta ação para adicionar pessoas a uma lista estática no Marketo Otimizer.

![Realizar uma ação - Adicionar à lista](./assets/person-action-node-add-to-list.png){width="450"}

Escolha uma das seguintes opções:

* **[!UICONTROL Criar]** — Crie um novo ativo de lista estática e adicione pessoas a ele. A lista está imediatamente disponível para uso por outros ativos no Marketo Otimizer.
* **[!UICONTROL Selecionar]** — Selecione um ativo de lista estática existente no qual você deseja adicionar pessoas que chegam ao nó.

+++

+++[!UICONTROL Adicionar à lista do Marketo Engage]

Use esta ação para adicionar pessoas a uma lista estática no Marketo Engage.

![Realizar uma ação - Adicionar à lista do Marketo](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL Alterar valor de dados]

Use esta ação para atualizar o valor de um atributo em um registro de pessoa. Selecione o atributo e defina o novo valor.

>[!TIP]
>
>Para limpar o valor de um atributo, defina o valor como `NULL`.

![Realizar uma ação - Alterar valor de dados](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL Alterar status no programa]

Use esta ação para alterar o status de uma pessoa em um programa do Marketo Engage. Selecione o programa e o novo status.

![Realizar uma ação - Alterar status do programa](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL Alterar status de membro do webinário]

Use esta ação para alterar o status de uma pessoa em relação a um webinário interativo. Selecione o webinário e o novo status.

![Realizar uma ação - Alterar status do programa](./assets/person-action-node-change-webinar-status.png){width="450"}

+++

+++[!UICONTROL Remover da lista]

Use esta ação para remover pessoas de uma lista estática no Marketo Otimizer. Se uma pessoa não for membro da lista no momento, a ação será ignorada para ela.

![Realizar uma ação - Remover da lista](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL Remover da lista do Marketo Engage]

Use esta ação para remover pessoas de uma lista estática no Marketo Engage. Se uma pessoa não for membro da lista no momento, a ação será ignorada para ela.

![Realizar uma ação - Remover da lista do Marketo](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL Remover pessoa da jornada]

Use esta ação para remover pessoas de outras jornadas de pessoas ativas. A pessoa é imediatamente removida da jornada de destino e nenhuma ação adicional é tomada sobre ela. Se uma pessoa não for membro da jornada de destino no momento, a ação será ignorada para ela.

![Realizar uma ação - Remover pessoa da jornada](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL Solicitar campanha do Marketo Engage]

Use esta ação para adicionar pessoas a uma campanha de solicitação em uma instância conectada do Marketo Engage. Selecione a campanha do Marketo Engage que será solicitada.

![Realizar uma ação - Solicitar campanha do Marketo](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL Enviar Email]

Use esta ação para enviar um email para as pessoas que aceitaram. As pessoas que cancelaram a inscrição, estão na lista de bloqueios, têm emails suspensos ou têm marketing suspenso ignoram essa ação.

![Executar uma ação - Enviar email](./assets/person-action-node-send-email.png){width="450"}

Você pode criar um email, editar um email existente ou usar um email personalizado por IA. Para obter informações sobre como criar e editar emails, consulte [Canal de email](./email-channel.md). Para gerar variantes com base em persona para um email existente, consulte [Personalizar conteúdo de email por persona](../agents/personalize-content.md).

Você pode usar a [Otimização de hora de envio](./email-send-time-optimization.md) para personalizar o tempo de entrega de email prevendo quando cada perfil tem maior probabilidade de participar.

+++

+++[!UICONTROL Enviar WhatsApp]

Use esta ação para enviar uma mensagem de WhatsApp. Você pode criar, personalizar e visualizar mensagens do WhatsApp no espaço de design visual (consulte [Criação do WhatsApp](../content/whatsapp-authoring.md)).

![Executar uma ação - Enviar WhatsApp](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
