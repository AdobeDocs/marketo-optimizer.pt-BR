---
title: Webinars de criação e promoção
description: Use a interface de chat no Marketo Otimizer para agendar um webinário, adicionar coanfitriões e apresentadores, criar jornadas de promoção e promoção e verificar os relatórios, tudo em linguagem natural.
keywords: null
role: User
source-git-commit: bc9b09fe125aad1909864db4fa7fc7605bf86597
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---


# Criar e promover webinars

A [interface de chat](./chat-interface.md) pode realizar um webinário desde a criação até a promoção, a entrega, a criação pós-webinário e a geração de relatórios — inteiramente pelo painel de conversa. Tudo o que a interface de chat cria usa o mesmo ativo, jornadas e tokens do webinário descrito em [Visão geral de webinários interativos](../marketing/webinars-overview.md), para que você possa alternar entre o chat e a interface de design a qualquer momento.

## Pontos de entrada

Na saudação &quot;Bem-vindo ao gerenciamento de marketing&quot;, selecione o chip de categoria **[!UICONTROL Webinar]** para ver os prompts sugeridos, incluindo:

* *&quot;Agendar e entregar um webinário&quot;*
* *&quot;Mostre-me todos os meus próximos webinars&quot;*
* *&quot;Forneça os detalhes do [nome do webinário]&quot;*

![Iniciar o fluxo de trabalho de criação do webinário por meio da interface de chat](./assets/webinar-create-start.png){width="700" zoomable="yes"}

Quando você abre o painel de bate-papo de dentro de um programa, ele encaminha automaticamente os prompts para esse programa.

## Adicionar um webinário agendado {#add-webinar}

Descreva o webinário desejado em uma única mensagem, por exemplo:

*&quot;Crie um webinário interativo chamado &#39;Segurança cibernética 101: Protegendo seus dados contra ameaças modernas&#39; em 12 de outubro de 2026 às 16h América/Los_Angeles para o [programa].&quot;*

1. O painel de chat mostra uma lista de verificação do **Plano de Tarefa** e funciona através dela: resolva o programa, defina o nome, a hora de início, a hora de término, o fuso horário e a capacidade e, em seguida, confirme.

   ![Especifique o nome, a data e a hora do webinário na interface do chat](./assets/webinar-create-name-time.png){width="500" zoomable="yes"}

1. O painel de chat lista suas **licenças** do webinário disponíveis (por exemplo, um complemento de alta capacidade com seu valor de capacidade) e pergunta qual usar. Responda com a capacidade desejada, por exemplo *&quot;Use a capacidade do webinário em 1000.&quot;*

   ![Defina a licença do webinário de acordo com a capacidade](./assets/webinar-create-license-capacity.png){width="500" zoomable="yes"}

1. O painel de chat ecoa o programa, o nome, a hora de início, o fuso horário, a duração e a capacidade e solicita que você **confirme** antes de criar o webinário.

1. Depois de criar o webinário, a interface do chat exibe um **cartão de webinário** com hora de início e término, duração, host, capacidade, provedor (Adobe Connect), uma URL de configuração, uma URL de inicialização, um link do painel de envolvimento e metadados de criação.

1. A interface do chat oferece **as próximas melhores ações**: _Crie seu webinário_, _Adicione um co-host_, _Adicione um apresentador_, _Configure jornadas promocionais_ e _Configure a jornada de criação pós-webinário_.

   ![A interface do chat exibe as melhores próximas etapas para a criação do webinário](./assets/webinar-create-next-steps.png){width="500" zoomable="yes"}

### Adicionar co-hosts e apresentadores {#co-hosts-presenters}

Selecione **[!UICONTROL Adicionar um co-host]** ou **[!UICONTROL Adicionar um apresentador]** das próximas melhores ações, ou peça diretamente, por exemplo *&quot;Adicionar um co-host [nome] [sobrenome] [email].&quot;* A interface de bate-papo abre a mesma caixa de diálogo de adição usada no designer — digite um nome e um email, já que todos são atualmente adicionados da mesma forma, em vez de selecionados em um seletor de lista. Uma confirmação é exibida assim que a pessoa é adicionada.

![Adicionar um coanfitrião de webinário na interface do chat](./assets/webinar-create-add-co-host.png){width="500" zoomable="yes"}

### Criar o webinário

Selecione **[!UICONTROL Criar seu webinário]** para abrir a página de configuração do webinário, onde você define as configurações de conteúdo, layout e registro na superfície de design [!DNL Adobe Connect] inserida. Conclua todas as alterações de design nessa interface; a interface do bate-papo vincula você, em vez de projetar a sala no bate-papo. Consulte [Criar o webinário](../marketing/create-webinar.md#create-and-design-a-webinar).

![Abrir o design do webinar do Adobe Connect na interface do chat](./assets/webinar-create-open-design.png){width="500" zoomable="yes"}

## Criar uma jornada promocional

1. Peça à interface do chat para configurar uma jornada promocional.

   Ele solicita que você escolha um modelo e nomeie a jornada, por exemplo *&quot;jornada de Convite/Registro.&quot;*

1. A interface do chat cria a jornada e vincula emails a seus nós, criando um fluxo de convite e lembrete com atualizações de status de membros do webinário.

1. A interface de chat lista o que resta para configurar na tela de jornada.

1. Clique em **[!UICONTROL Editar nós de jornada]** e responda a consultas sobre o que é necessário para concluir a jornada.

   Você pode fazer upload de um documento de campanha para fornecer detalhes ou continuar com o bate-papo para identificar o que é necessário.

   Ou você pode trabalhar diretamente na tela de jornada para abordar cada nó:

   * Selecione o primeiro nó de jornada e defina o público-alvo da jornada. [Saiba mais](../marketing/person-audience-node.md)
   * Selecione o nó do convite _Enviar email_ e clique em **[!UICONTROL Editar email]**. [Saiba mais](../marketing/email-channel.md)
   * Selecione a escuta de um nó de evento e clique em **[!UICONTROL Editar evento]**. Defina o filtro de eventos para o formulário de registro no evento _Preenche Formulário_. [Saiba mais](../marketing/listen-for-event-nodes.md#event-filters)
   * Verifique os campos **[!UICONTROL Alterar status do membro do webinário]** em cada nó de alteração de status. [Saiba mais](../marketing/action-nodes.md#actions-and-constraints)

1. Conclua a configuração dos outros nós e endereço

1. Quando terminar, clique em **[!UICONTROL Publicar agora]** para ativar a jornada e iniciar a promoção.

## Criar uma jornada pós-webinário

1. Peça à interface do chat uma jornada pós-webinário.

   Ele solicita um modelo e um nome.

1. A interface do chat cria um nó **Split Path** com caminhos e ações definidos:

   * Uma ramificação **_Presente_** (por exemplo, uma resposta e um nó _Enviar email_ de recursos)
   * Uma ramificação **_No-Show_** (por exemplo, uma ramificação &quot;perdeu? assistir novamente&quot; _Enviar email_ (nó)

   E cada um é seguido por um nó _Wait_ e um nó de acompanhamento _Enviar email_.

   A condição de divisão está definida para identificar o estado do webinário, usando _Participou do webinário_.

1. Clique em **[!UICONTROL Editar nós de jornada]** e responda a consultas sobre o que é necessário para concluir a jornada.

   Você pode fazer upload de um documento de campanha para fornecer detalhes ou continuar com o bate-papo para identificar o que é necessário.

   Ou você pode trabalhar diretamente na tela de jornada para abordar cada nó.

1. Conclua a configuração dos outros nós e endereço

1. Ao concluir, clique em **[!UICONTROL Publicar agora]** para ativar a jornada e iniciar a acompanhamento.

## Verificar relatório

Na interface do chat, você pode fazer perguntas de relatório, como *&quot;Mostrar todos os meus próximos webinários&quot;* ou *&quot;Fornecer detalhes do webinário [nome]&quot;*. Ele exibe o link do painel de envolvimento junto com as próximas melhores ações, como **Design**, **Adicionar co-host** ou **Publicar na data do webinário**.

Para análises mais detalhadas — desempenho de pesquisa, pesquisa e participação e dados por membro — a interface do chat é vinculada às guias **Analytics** e **Members** do webinário, e ao roll-up entre programas em **Gerenciamento de webinários**. <!-- See [Webinar reporting](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/webinars/webinar-reporting). -->
