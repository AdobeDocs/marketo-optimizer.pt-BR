---
title: Nós Dividir e Mesclar Caminhos
description: Saiba como usar nós de caminhos divididos e mesclados em jornadas de pessoas para segmentar pessoas em caminhos distintos com base em condições definidas e, em seguida, reuni-los em um ponto comum downstream.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Dividir e mesclar nós de caminhos

Use os nós dividir e mesclar caminhos nas jornadas de pessoa para segmentar pessoas em caminhos distintos com base nas condições definidas e, em seguida, reúna esses caminhos novamente para que a jornada possa continuar. Caminhos divididos permitem personalizar ações e eventos para segmentos de público-alvo específicos, enquanto caminhos de mesclagem reúnem esses segmentos em um ponto comum downstream.

## Nós de caminhos divididos

Use nós divididos para segmentar pessoas de acordo com as condições definidas. Crie caminhos para a lista de público-alvo de acordo com as condições, defina cada caminho com nós de ação e evento para o segmento e, em seguida, combine os caminhos e continue a jornada.

Um nó Caminhos divididos define um ou mais caminhos segmentados com base em filtros de pessoas.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_&#x200B;**Como funciona um caminho dividido por nó de pessoas**&#x200B;_

* A avaliação de cada caminho é de cima para baixo. Se uma pessoa corresponder ao primeiro e ao segundo caminhos, ela continuará somente pelo primeiro caminho.
* O nó oferece suporte à definição de um caminho _Outras pessoas_, em que você pode adicionar ações ou eventos para pessoas que não correspondem a um dos segmentos/caminhos definidos.

### Filtros correspondentes

Para cada caminho definido para o nó, use os seguintes tipos de filtro para corresponder pessoas de acordo com uma ou mais condições:

* Histórico de atividades - Você pode definir um caminho de acordo com a atividade da pessoa relacionada a:

  * Mensagens de email
  * Alteração no valor dos dados

* Atributos de pessoa - Defina uma condição de acordo com os atributos de uma pessoa, como país, cargo, personalidade derivada ou associação a listas.

### Adicionar um nó de caminhos divididos

1. Navegue até a tela de jornada.

1. Clique no ícone de adição ( **+** ) em um caminho e escolha **[!UICONTROL Dividir caminhos]**.

   ![Clique em adicionar ícone no caminho da jornada](./assets/person-journey-canvas-add-node.png){width="200"}

1. Para definir uma condição aplicável ao _[!UICONTROL Caminho 1]_, clique em **[!UICONTROL Aplicar condição]**.

1. No editor de condições, adicione um ou mais filtros para definir o caminho dividido.

   * Arraste e solte qualquer um dos filtros de pessoas da navegação à esquerda e conclua a definição de correspondência.

   * Ajuste as condições aplicando a **[!UICONTROL lógica de Filtro]** na parte superior. Você escolhe corresponder todas as condições ou qualquer uma delas.

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * Clique em **[!UICONTROL Concluído]**.

1. Para adicionar mais caminhos, clique em **[!UICONTROL Adicionar caminho]** e repita as etapas anteriores para adicionar condições aplicáveis ao caminho.

   Você também pode rotular cada caminho com base nessas condições ou usar os rótulos padrão.

1. Se necessário, reordene os caminhos de acordo com a prioridade desejada para a divisão.

   A filtragem de caminho é avaliada em ordem decrescente. Cada pessoa continua pelo primeiro caminho que corresponde a.

   Clique nas setas para cima e para baixo na parte superior direita de cada cartão de caminho para movê-lo para cima ou para baixo na lista de caminhos.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Habilite a opção **[!UICONTROL Outras pessoas]** para adicionar um caminho padrão para pessoas que não correspondam aos caminhos definidos.

   Quando essa opção não está ativada, as pessoas que não correspondem a um segmento/caminho definido passam pela divisão e avançam para a próxima etapa da jornada.

Quando você tem condições definidas para cada caminho, pode adicionar nós de ação ou evento que deseja aplicar às pessoas em um caminho.

## Nós dos caminhos de mesclagem

1. Navegue até a tela de jornada e localize o nó dos caminhos divididos com dois ou mais caminhos.

   Cada caminho deve ter uma combinação de ações e eventos em cada caminho.

1. Clique no ícone de adição ( **+** ) ao final de qualquer um desses caminhos e escolha **[!UICONTROL Mesclar caminhos]** nas opções exibidas.

1. Nas propriedades do nó à direita, selecione os caminhos que deseja mesclar.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   Nesse ponto, os caminhos são mesclados para que as pessoas dos caminhos selecionados se combinem a um único caminho que possa continuar avançando pela jornada.

1. Se necessário, você pode desfazer a mesclagem de caminhos navegando de volta para as propriedades do nó dos caminhos de mesclagem e desmarcando a caixa de seleção de todos os caminhos que deseja remover.