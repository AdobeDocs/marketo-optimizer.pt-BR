---
title: Ouvir um nó de evento
description: Configurar o Listen para nós de evento no Marketo Otimizer - defina acionadores de evento, aplique filtros opcionais e promova o avanço das pessoas quando ocorrerem atividades ou alterações de dados.
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 2%
---
# Ouvir um nó de evento

Para avançar seu público-alvo para a próxima etapa da jornada quando ocorrer um evento, adicione o nó _Ouvir um evento_.

## Acionadores de eventos {#event-triggers}

Defina os critérios do evento que acionam o nó de jornada e fazem o membro do público-alvo avançar.

| Acionadores | Descrição |
| -------- | ----------- |
| Brand Concierge | Atividades para clientes potenciais envolvidos com [!DNL Brand Concierge]. |
| Email | Atividades de email para clientes potenciais, incluindo envios, entrega e envolvimento. |
| Evento | Atividades de webinar interativo para clientes potenciais, incluindo registro, participação e interações. |
| Oportunidades | Atividades relacionadas a registros de oportunidade associados a clientes potenciais ou contas. |
| Aplicativos de vendas | Atividades de cliente potencial relacionadas a [!DNL Sales Qualifier] ou [!DNL Marketo Sales Insights]. |
| Outro | Atividades que não se enquadram nas categorias predefinidas, fornecendo flexibilidade para acionadores de eventos personalizados ou diversos. |

>[!BEGINSHADEBOX]

**Atividades do Marketo Engage com suporte para acionadores**

Ao disparar em eventos, o [!DNL Marketo Optimizer] dá suporte a atividades da instância [!DNL Marketo Engage] que está conectada como fonte de dados.

>[!NOTE]
>
>Pode haver apenas uma instância [!DNL Marketo Engage] como fonte de dados e ela é pré-configurada no momento do provisionamento da instância [!DNL Marketo Optimizer].

Você pode criar disparadores de eventos em torno das [!DNL Marketo Engage] seguintes atividades:

* **[!UICONTROL Preenche o formulário do Marketo Engage]** - Acionado quando um cliente potencial envia um formulário [!DNL Marketo Engage] especificado.
* **[!UICONTROL Visita a página da Web do Marketo Engage]** - Acionado quando um cliente potencial com um cookie de rastreamento do Munchkin visita uma página da Web especificada.
* **[!UICONTROL Link de cliques na página da Web do Marketo Engage]** - Acionado quando um cliente potencial clica em um hiperlink rastreado em uma página da Web que tem o código de rastreamento do Munchkin [!DNL Marketo Engage] instalado.
* **[!UICONTROL Email do Marketo Engage entregue]** - Acionado quando o servidor de email (MX) de um cliente potencial retorna uma resposta bem-sucedida (uma mensagem de 250 OK) ao servidor de envio [!DNL Marketo Engage].
* **[!UICONTROL Rejeições de email do Marketo Engage]** - Acionado quando um servidor de email de destino rejeita uma mensagem de email enviada [!DNL Marketo Engage] como um erro permanente, como um usuário inválido ou domínio desconhecido.
* **[!UICONTROL O email do Marketo Engage é rejeitado temporariamente]** - Acionado quando um servidor de email de destino rejeita uma mensagem de email [!DNL Marketo Engage] enviada como um problema temporário (como servidor ocupado ou caixa de correio cheia). O [!DNL Marketo Engage] tenta automaticamente rejeições temporárias até três vezes por meio de servidores MX antes de sinalizar problemas.
* **[!UICONTROL Cancelamentos de assinatura de email do Marketo Engage]** - Acionado quando um cliente potencial recusa emails de marketing não operacionais. Quando acionado, o [!DNL Marketo Engage] atualiza automaticamente o valor do campo `Unsubscribed` do cliente potencial para `true`, eliminando-o de futuros envios de emails padrão.
* **[!UICONTROL Abre o email do Marketo Engage]** - Acionado quando um cliente potencial abre um email [!DNL Marketo Engage] rastreado.
* **[!UICONTROL Link de cliques no email do Marketo Engage]** - Acionado quando um cliente potencial clica em qualquer link (ou em um link restrito específico) dentro de um email [!DNL Marketo Engage].

>[!ENDSHADEBOX]

## Filtros de evento {#event-filters}

Você pode incluir a filtragem para limitar acionadores de eventos correspondentes com base em vários critérios:

| Filtros | Descrição |
| ------- | ----------- |
| Histórico de atividades | Atividades com base em condições que são avaliadas usando um ou mais itens selecionados |
| Brand Concierge | Atividades para clientes potenciais envolvidos com [!DNL Brand Concierge]. |
| Atributos da empresa | Atributos do perfil da empresa/conta, incluindo: <li>[!UICONTROL Receita anual] <li>[!UICONTROL Nome da empresa] <li>[!UICONTROL País de cobrança] <li>[!UICONTROL Setor] <li>[!UICONTROL Número de funcionários] <li>[!UICONTROL Código SIC] <li>[!UICONTROL Estado] |
| Dados de intenção | Atributos com base nos dados de intenção associados ao perfil da pessoa. |
| Oportunidades | Status e atributos com base nas oportunidades associadas ao perfil da pessoa, incluindo: <li>[!UICONTROL Tem oportunidade] <li>[!UICONTROL Número de oportunidades] <li>[!UICONTROL Valor total da oportunidade] <li>[!UICONTROL Foi adicionado à oportunidade] <li>[!UICONTROL Foi removido da oportunidade] |
| Atributos da pessoa | Atributos do perfil de pessoa B2B, incluindo: <li>[!UICONTROL Cidade] <li>[!UICONTROL País] <li>[!UICONTROL Data de nascimento] <li>[!UICONTROL Endereço de email] <li>[!UICONTROL Email inválido] <li>[!UICONTROL Email suspenso] <li>[!UICONTROL Nome] <li>[!UICONTROL Região do estado inferido] <li>[!UICONTROL Cargo] <li>[!UICONTROL Sobrenome] <li>[!UICONTROL Número do celular] <li>[!UICONTROL Pontuação de engajamento de pessoa] <li>[!UICONTROL Número de telefone] <li>[!UICONTROL CEP] <li>[!UICONTROL Estado] <li>[!UICONTROL Cancelamento de assinatura] <li>[!UICONTROL Motivo do cancelamento da assinatura] |
| Aplicativos de vendas | Atividades de cliente potencial relacionadas a [!DNL Sales Qualifier] ou [!DNL Marketo Sales Insights]. |
| Filtros especiais | Filtrar atributos que não se enquadram nas categorias predefinidas, fornecendo flexibilidade para critérios de filtro personalizados ou diversos. |

>[!BEGINSHADEBOX]

**Atividades do Marketo Engage com suporte para filtros**

Ao filtrar eventos disparados, o [!DNL Marketo Optimizer] dá suporte a atividades da instância [!DNL Marketo Engage] que está conectada como fonte de dados.

>[!NOTE]
>
>Pode haver apenas uma instância [!DNL Marketo Engage] como fonte de dados e ela é pré-configurada no momento do provisionamento da instância [!DNL Marketo Optimizer].

Você pode criar filtros de eventos em torno das [!DNL Marketo Engage] seguintes atividades:

* **[!UICONTROL Formulário Marketo Engage preenchido]** - Corresponde a clientes potenciais que preencheram um formulário [!DNL Marketo Engage] específico em qualquer ponto de seu log de atividades não expirado.
* **[!UICONTROL Visitou a página da Web do Marketo Engage]** - Corresponde a clientes potenciais que visualizaram uma URL específica no seu site ou [!DNL Marketo Engage] páginas de aterrissagem. Ele depende diretamente do código de rastreamento do Munchkin instalado no site.
* **[!UICONTROL Link clicado na página da Web do Marketo Engage]** - Corresponde a clientes potenciais que clicaram em um link ou ativo específico em uma página rastreada.
* **[!UICONTROL Email do Marketo Engage enviado]** - Corresponde aos clientes potenciais para os quais [!DNL Marketo Engage] tentou enviar um email específico, considerando as ações de implantação anteriores às rejeições permanentes ou aceitações do servidor.
* **[!UICONTROL Email Marketo Engage entregue]** - Corresponde a clientes potenciais cujo servidor de email (MX) retornou uma resposta bem-sucedida (uma mensagem de 250 OK) para o servidor de envio [!DNL Marketo Engage].
* **[!UICONTROL Email do Marketo Engage rejeitado]** - Corresponde aos clientes potenciais que tiveram uma rejeição permanente (falha permanente de entrega) em um envio de email específico ou dentro de um período.
* **[!UICONTROL Email do Marketo Engage rejeitado suave]** - Corresponde a clientes potenciais cujos emails tiveram uma falha de entrega temporária (como uma caixa de entrada cheia ou um servidor offline) em vez de uma rejeição permanente.
* **[!UICONTROL Cancelar assinatura do email do Marketo Engage]** - Corresponde aos clientes potenciais que optaram por não participar de emails de marketing não operacionais. Quando isso ocorre, o [!DNL Marketo Engage] atualiza automaticamente o valor do campo `Unsubscribed` do cliente potencial para `true`, eliminando-o dos futuros envios de email padrão.
* **[!UICONTROL Email do Marketo Engage aberto]** - Corresponde aos clientes potenciais que abriram um email [!DNL Marketo Engage] rastreado.
* **[!UICONTROL Link clicado no email do Marketo Engage]** - Corresponde aos clientes potenciais que clicaram em qualquer link (ou em um link específico) dentro de um email [!DNL Marketo Engage].

>[!ENDSHADEBOX]

## Adicionar um nó de evento {#add-event-node}

1. Navegue até a tela de jornada.

1. Clique no ícone de adição ( **+** ) em um caminho e escolha **[!UICONTROL Ouvir um evento]**.

   ![Clique em adicionar ícone no caminho da jornada](./assets/person-journey-canvas-add-node.png){width="200"}

1. Nas propriedades do nó à direita, clique em **[!UICONTROL Adicionar critério de evento]**.

1. Na caixa de diálogo _[!UICONTROL Editar evento]_, adicione um evento e defina as restrições que deseja corresponder ao acionador.

   Arraste e solte o acionador de evento no espaço do construtor e defina a definição. Clique em **[!UICONTROL Adicionar restrição]** para cada restrição que você deseja usar para refinar a correspondência de eventos.

   ![Editar evento - acionadores de evento](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   É possível adicionar vários eventos para corresponder. O primeiro evento de qualificação avança o perfil da pessoa na jornada.

1. (Opcional) Selecione a guia **[!UICONTROL Filtros]** e adicione critérios de filtragem para os acionadores.

   Arraste e solte o filtro no espaço do construtor e defina a definição. Clique em **[!UICONTROL Adicionar restrição]** para cada restrição que você deseja usar para refinar a correspondência de filtro.

   ![Editar evento - filtragem de eventos](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. Clique em **[!UICONTROL Salvar]**.

   A qualquer momento, você pode clicar em **[!UICONTROL Editar evento]** para alterar os critérios de evento do nó.

1. Se necessário, defina a opção **[!UICONTROL Tempo limite]** para limitar o período de tempo para ouvir o evento.

   >[!NOTE]
   >
   >A jornada termina após um tempo limite, a menos que você defina um caminho de tempo limite, em que é possível adicionar outros nós.

   Habilite a opção **[!UICONTROL Tempo limite]** e selecione a duração pela qual a jornada aguarda a ocorrência de um evento antes de atingir o tempo limite.

   ![Opções de tempo limite habilitadas para o nó Escutar jornada de eventos](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   Você pode optar por finalizar o caminho aqui ou executar uma ação diferente definindo outro caminho. Para criar um novo caminho na jornada, onde você pode adicionar ações e eventos aplicáveis a perfis quando o evento não ocorrer, marque a caixa de seleção **[!UICONTROL Definir caminho de tempo limite]**.
