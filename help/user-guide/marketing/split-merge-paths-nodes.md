---
title: Nós Dividir e Mesclar Caminhos
description: Saiba como usar nós de caminhos divididos e mesclados em jornadas de pessoas para segmentar pessoas em caminhos distintos com base em condições definidas e, em seguida, reuni-los em um ponto comum downstream.
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: 9d9f2ae1aafc5ffdc2bcc6546c7eb2ddcbaa4ab2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 6%
---
# Dividir e mesclar nós de caminhos

Use os nós dividir e mesclar caminhos nas jornadas de pessoa para segmentar pessoas em caminhos distintos com base nas condições definidas e, em seguida, mescle esses caminhos para que a jornada possa continuar. Os caminhos divididos permitem personalizar ações e eventos para segmentos de público-alvo específicos, enquanto os caminhos de mesclagem combinam esses segmentos em um ponto comum.

## Nós de caminhos divididos

Use nós divididos para segmentar pessoas de acordo com as condições definidas. Crie caminhos para a lista de público-alvo de acordo com as condições, defina cada caminho com nós de ação e evento para o segmento e, em seguida, combine os caminhos e continue a jornada.

Um nó Caminhos divididos define um ou mais caminhos segmentados com base em filtros de pessoas.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**Como funciona um nó de caminho dividido**_

* A avaliação de cada caminho é de cima para baixo. Se uma pessoa corresponder ao primeiro e ao segundo caminhos, ela continuará somente pelo primeiro caminho.
* O nó oferece suporte à definição de um caminho _Outras pessoas_, em que você pode adicionar ações ou eventos para pessoas que não correspondem a um dos segmentos/caminhos definidos.

### Filtros de pessoa correspondentes

Para cada caminho definido para o nó, use os seguintes tipos de filtro para corresponder pessoas de acordo com uma ou mais condições.

| Filtros | Descrição |
| ------- | ----------- |
| Histórico de atividades | Atividades com base em condições que são avaliadas usando um ou mais itens selecionados |
| Brand Concierge | Atividades para clientes potenciais envolvidos com [!DNL Brand Concierge]. |
| Atributos da empresa | Atributos do perfil da empresa/conta, incluindo: <li>Receita anual <li>Nome da empresa <li>País de cobrança <li>Setor <li>Número de funcionários <li>Código SIC <li>Estado |
| Dados de intenção | Atributos com base nos dados de intenção associados ao perfil da pessoa. |
| Oportunidades | Atributos com base nas oportunidades associadas ao perfil da pessoa. |
| Atributos da pessoa | Atributos do perfil de pessoa B2B, incluindo: <li>Cidade <li>País <li>Data de nascimento <li>Endereço de e-mail <li>Email inválido <li>Email suspenso <li>Nome <li>Região inferida<li>Nome do cargo <li>Sobrenome <li>Número do celular <li>Pontuação de engajamento de pessoa <li>Número de telefone <li>Código postal <li>Estado <li>Inscrição cancelada <li>Motivo do cancelamento de inscrição |
| Aplicativos de vendas | Atividades de cliente potencial relacionadas a [!DNL Sales Qualifier] ou [!DNL Marketo Sales Insights]. |
| Filtros especiais | Filtrar atributos que não se enquadram nas categorias predefinidas, fornecendo flexibilidade para critérios de filtro personalizados ou diversos. |

>[!BEGINSHADEBOX]

**Atividades [!DNL Marketo Optimizer] com suporte para filtros de condição**

Para condições de caminho, o [!DNL Marketo Optimizer] dá suporte a atividades da instância [!DNL Marketo Engage] que está conectada como fonte de dados.

>[!NOTE]
>
>Pode haver apenas uma instância [!DNL Marketo Engage] como fonte de dados e ela é pré-configurada no momento do provisionamento da instância [!DNL Marketo Optimizer].

Você pode criar condições em torno das [!DNL Marketo Engage] seguintes atividades:

* [!UICONTROL Formulário Marketo Engage preenchido] - Corresponde a clientes potenciais que preencheram um formulário [!DNL Marketo Engage] específico em qualquer ponto de seu log de atividades não expirado.
* [!UICONTROL Visitou a página da Web do Marketo Engage] - Corresponde a clientes potenciais que visualizaram uma URL específica no seu site ou [!DNL Marketo Engage] páginas de aterrissagem. Ele funciona diretamente usando o código de rastreamento do Munchkin instalado no site.
* [!UICONTROL Link clicado na página da Web do Marketo Engage] - Corresponde a clientes potenciais que clicaram em um link ou ativo específico em uma página rastreada.
* [!UICONTROL Email do Marketo Engage enviado] - Corresponde aos clientes potenciais para os quais [!DNL Marketo Engage] tentou enviar um email específico, considerando as ações de implantação anteriores às rejeições permanentes ou aceitações do servidor.
* [!UICONTROL Email Marketo Engage entregue] - Corresponde a um cliente potencial cujo servidor de email (MX) retornou uma resposta bem-sucedida (uma mensagem de 250 OK) para o servidor de envio [!DNL Marketo Engage].
* [!UICONTROL Email de Marketo Engage rejeitado] - Corresponde a clientes potenciais que tiveram uma rejeição permanente (falha permanente de entrega) em um envio de email específico ou dentro de um período.
* [!UICONTROL Email do Marketo Engage rejeitado suave] - Corresponde a clientes potenciais cujos emails tiveram uma falha de entrega temporária (como uma caixa de entrada cheia ou um servidor offline) em vez de uma rejeição permanente.
* [!UICONTROL Cancelar assinatura do email do Marketo Engage] - Corresponde aos clientes potenciais que optaram por não participar de emails de marketing não operacionais. Quando isso ocorre, o [!DNL Marketo Engage] atualiza automaticamente o valor do campo `Unsubscribed` do cliente potencial para `true`, eliminando-o dos futuros envios de email padrão.
* [!UICONTROL Email do Marketo Engage aberto] - Corresponde aos clientes potenciais que abriram um email [!DNL Marketo Engage] rastreado.
* [!UICONTROL Link clicado no email do Marketo Engage] - Corresponde aos clientes potenciais que clicaram em qualquer link (ou em um link específico) dentro de um email [!DNL Marketo Engage].

>[!ENDSHADEBOX]

### Adicionar um nó de caminhos divididos

1. Navegue até a tela de jornada.

1. Clique no ícone de adição ( **+** ) em um caminho e escolha **[!UICONTROL Dividir caminhos]**.

   ![Clique em adicionar ícone no caminho da jornada](./assets/person-journey-canvas-add-node.png){width="200"}

1. Para definir uma condição aplicável ao _[!UICONTROL Caminho 1]_, clique em **[!UICONTROL Aplicar condição]**.

1. Para definir o caminho dividido, adicione um ou mais filtros no editor de condições.

   * Arraste e solte qualquer um dos filtros de pessoas da navegação à esquerda e conclua a definição de correspondência.

   * Clique em **[!UICONTROL Adicionar restrição]** para cada restrição que você deseja usar para refinar a correspondência de filtro.

     ![Nó de caminho dividido - filtro de pessoa correspondente para a condição de caminho](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * Refine suas condições aplicando a **[!UICONTROL lógica de Filtro]** na parte superior. Você escolhe corresponder todas as condições ou qualquer uma delas.

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

   Cada caminho deve ter uma combinação de nós de ação e evento.

1. Clique no ícone de adição ( **+** ) ao final de qualquer um desses caminhos e escolha **[!UICONTROL Mesclar caminhos]** nas opções exibidas.

1. Nas propriedades do nó à direita, selecione os caminhos que deseja mesclar.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   Nesse ponto, os caminhos são mesclados para que as pessoas dos caminhos selecionados se combinem a um único caminho que possa continuar avançando pela jornada.

1. Se necessário, você pode desfazer a mesclagem de caminhos navegando de volta para as propriedades do nó dos caminhos de mesclagem e desmarcando a caixa de seleção de todos os caminhos que deseja remover.