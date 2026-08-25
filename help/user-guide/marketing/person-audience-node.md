---
title: Nó de Jornada de público-alvo de pessoa
description: Configure o nó de público-alvo pessoa no Journey Optimizer B2B para especificar quais perfis entram em uma jornada usando listas de pessoas dinâmicas ou públicos-alvo baseados em eventos.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Nó de público-alvo de pessoa

O nó _person audience_ especifica quais perfis de pessoa entram na jornada. Quando você [cria uma jornada de pessoa](./person-journeys.md), a jornada sempre começa com um nó de público-alvo de pessoa que define sua entrada. O nó de público-alvo pessoa pode ter um dos dois tipos de entrada de público-alvo: uma lista dinâmica de pessoas ou um acionador de evento.

Se a lista dinâmica de pessoas de que você precisa para a jornada de pessoa ainda não existir, [crie a lista de pessoas](../audiences/people-lists.md#create-a-people-list) e configure o nó de público-alvo Pessoa.

_Para configurar o público-alvo da jornada :_

1. Clique no nó **[!UICONTROL Público-alvo de pessoa]**.

   Essa ação exibe as propriedades do nó à direita.

   ![Nó de jornada de público-alvo de pessoa](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. Use uma das seguintes opções de configuração de público-alvo para o público-alvo de pessoa:

   * **[!UICONTROL Lista dinâmica]** - Use uma lista dinâmica de pessoas baseada em regras. As regras de lista são avaliadas no tempo de execução da jornada para qualificar membros da jornada. As pessoas que depois se desqualificam para a lista dinâmica não são removidas da jornada. Consulte _[Listas dinâmicas](../audiences/people-lists.md#dynamic-lists)_.

   * **[!UICONTROL Público-alvo do evento]** - Use um público-alvo de evento para definir o público-alvo de jornada com base em eventos qualificados. Defina membros do público usando a filtragem de perfil de pessoa e acione a entrada de jornada usando critérios de evento. Consulte _[Públicos-alvo baseados em eventos](../audiences/event-based-audiences.md)_.