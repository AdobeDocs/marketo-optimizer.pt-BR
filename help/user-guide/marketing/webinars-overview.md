---
title: Webinários interativos
description: Saiba mais sobre os conceitos por trás dos Webinars interativos no Marketo Otimizer, incluindo o modelo de ativo do webinário, os estados membros, os tokens e as atividades.
keywords: 
role: User
feature: Channels
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# Webinários interativos

Os webinários interativos permitem planejar, promover, entregar e acompanhar um webinário ao vivo ou simulado sem sair do [!DNL Adobe Marketo Optimizer]. A entrega é executada no [!DNL Adobe Connect] automaticamente, para que você nunca precise trocar de produto para criar uma página de registro, hospedar a sessão em tempo real ou obter os dados de participação.

>[!NOTE]
>
>Este recurso requer uma licença e está sujeito a termos e condições adicionais. Para saber mais sobre os termos e condições adicionais, revise seu contrato ou entre em contato com a Adobe.

Você pode criar um webinário de duas maneiras:

* **Experiência de conversa** - Peça ao Colaborador para agendar, promover e relatar um webinário em linguagem natural. Consulte [Criar webinários com o Colaborador](../agents/webinar-creation.md).

* **Aponte e clique** - Use o espaço de trabalho _[!UICONTROL Programas]_ para adicionar um ativo de webinário, projetá-lo, adicionar co-hosts e apresentadores, criar jornadas de promoção e acompanhamento e revisar relatórios. Consulte [Criar e criar um webinário](create-webinar.md) e [Promoção de webinários e jornadas de acompanhamento](webinar-journeys.md).

## Webinário como um ativo

Um webinário é um ativo que pertence a um [programa](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs), da mesma forma que um email ou uma página de aterrissagem. Adicionar um webinário a um programa o registra lá e disponibiliza seus tokens, atributos e atividades para cada jornada e ativo nesse programa.

>[!IMPORTANT]
>
>Um programa pode possuir atualmente um ativo de webinário. O suporte para vários webinars por programa está planejado para uma versão futura.

## Estados-Membros

Para qualquer pessoa que seja membro de um programa que contenha um webinário, três estados independentes se aplicam ao mesmo tempo. Cada um deles pode ser referenciado separadamente em públicos-alvo e condições de jornada.

| Estado | Proprietário | Valores |
|---|---|---|
| Status do membro do programa | Programa | Configurável por [tipo de programa](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types) |
| Estado do webinário | Ativo do webinário | Convidado, Inscrito, Participou, Não compareceu, Participou sob demanda |
| Estado da jornada | Jornada | Estados atuais do nó, pausado, concluído e outros estados do tempo de execução do jornada |

### Status do webinário

O status do webinário tem cinco valores. [!DNL Adobe Connect] normalmente define o valor automaticamente, mas você também pode definir o status com uma ação de jornada se precisar substituí-lo. Para refletir a presença registrada em outro sistema, por exemplo, você pode definir o status em sua jornada.

| Status | Como é definido | Fonte |
|---|---|---|
| Convidado | Um nó de jornada _Realizar uma Ação_, normalmente quando o email de convite envia | Controlado por autor |
| Registrado | Um nó de jornada _Executar uma Ação_ quando a pessoa se registra. Isso também aciona [!DNL Adobe Connect] para gerar a URL de ingresso da pessoa | Controlado por autor |
| Participou | Um evento de [!DNL Adobe Connect] após a execução do webinário em tempo real | Controlado pelo sistema, com substituição de autor disponível por meio de uma jornada |
| No-Show | Um evento de [!DNL Adobe Connect] após a execução do webinário em tempo real | Controlado pelo sistema, com substituição de autor disponível por meio de uma jornada |
| Participou sob demanda | Um evento de [!DNL Adobe Connect] quando uma pessoa que não participou mais tarde assiste a gravação | Controlado pelo sistema, com substituição de autor disponível por meio de uma jornada |

>[!IMPORTANT]
>
>Seja definido automaticamente ou definido de uma jornada, o status do webinário só se move em uma direção, da mesma forma que [o status do programa](./programs.md#statuses). Uma pessoa pode mudar para um estado posterior (por exemplo, _Registrada_ para _Participou_), mas não voltar para um estado anterior. Planeje qualquer substituição de autor tendo em mente essa progressão linear.

Para mover uma pessoa entre estados de uma jornada, use a ação **[!UICONTROL Alterar status do membro do webinário]**. Consulte [Promoção de webinários e jornadas de acompanhamento](webinar-journeys.md).

## Tokens de webinário

Os tokens de webinário estão disponíveis em qualquer lugar onde você personaliza o conteúdo de email (assunto, corpo, pré-cabeçalho e remetente). Encontre-os no editor de personalização em **_Contexto > Webinar_**.

Os tokens no nível do ativo ficam diretamente na pasta do webinário:

- Título
- Descrição
- Data e hora inicial e data e hora final
- Duração
- Fuso horário
- Apresentadores
- URL de Gravação

>[!NOTE]
>
>Os co-hosts são exibidos na seção Equipe de webinário da página do webinário, mas não estão disponíveis como um token de personalização.

Os tokens por destinatário residem em uma subpasta **Member**:

- **Status** - O status atual do webinário do destinatário (Convidado, Registrado, Participou, Não Compareceu ou Participou sob Demanda). Consulte [status do webinário](#webinar-status).
- **Ingressando na URL** - O link [!DNL Adobe Connect] pessoal do destinatário. Isso é resolvido somente depois que o estado do webinário do recipient é Registrado ou posterior. Resolve vazio para qualquer um em um estágio anterior.
- **URL de Gravação** - Resolve depois que a gravação é publicada após a sessão ao vivo e permanece vazia até lá. Use-o condicionalmente nos emails pós-webinário para que um link não apareça antes que haja uma gravação para mostrar.

>[!NOTE]
>
>Os tokens de webinário atualmente são renderizados somente no conteúdo do email (assunto, corpo, pré-cabeçalho e remetente). O suporte a tokens de webinário em páginas de aterrissagem e formulários está planejado para uma versão futura.
>
>Como esses tokens são resolvidos como vazios em vez de gerar um erro, um email ou página que os faz referência é renderizado com segurança em qualquer ponto do ciclo de vida do webinário. O conteúdo de pré-visualização antes e depois dos valores está disponível para confirmar se o layout parece correto de qualquer maneira.

## Atividades do webinário

Todo webinário relata automaticamente atividades que você pode usar como _Ouvir acionadores de Evento_, condições de _Caminho dividido_, filtros de público-alvo e métricas de relatório:

* Faz uma pergunta
* Responde a uma enquete
* Clica em um link
* Baixa um ativo
* Levanta a mão

>[!NOTE]
>
>As alterações de status do webinário (Convidado, Registrado, Presente, Não Apresentação, Presente sob Demanda) não estão disponíveis no momento como seu próprio gatilho ou filtro de atividade _Ouvir Evento_. Para ramificar uma jornada no status do webinário, use uma condição _Split path_ no estado do webinário diretamente (descrito em [_Criar uma jornada pós-webinário_](webinar-journeys.md#build-post-webinar-journey)) em vez de escutar uma atividade de alteração de estado.

O engajamento de pessoas que assistem à gravação depois que o evento ao vivo é assimilado como as mesmas atividades, marcadas com um modo de Sob demanda. Diferentemente das atividades, o envolvimento sob demanda cria um estado de webinário separado: uma pessoa que não participou e mais tarde assiste a gravação mudar de **No-Show** para **Participou sob demanda**.

## Pré-requisitos

Antes de começar a criar um webinário, verifique se os itens a seguir estão em vigor.

| Pré-requisito | Detalhes |
|---|---|
| Um programa | O webinário é adicionado dentro de um programa existente. Um analista de operações de marketing normalmente cria o programa primeiro. |
| Licença do webinário (capacidade) | Uma licença de webinário, também chamada de direito de capacidade, deve estar disponível antes que você possa agendar um webinário. Você escolhe uma capacidade no momento da configuração e complementos de maior capacidade podem estar disponíveis. Para aumentar sua capacidade disponível, entre em contato com a equipe de conta da Adobe. |
| [!DNL Adobe Connect] | A entrega é executada em [!DNL Adobe Connect]. O provisionamento ocorre automaticamente em segundo plano. Você não precisa sair de [!DNL Marketo Optimizer] para criar ou hospedar um webinário. |

### Permissões

O acesso aos recursos do webinário depende das permissões atribuídas para webinários.

| Função | O que concede |
|---|---|
| Exibir webinários B2B | Veja a lista de webinários e uma configuração, detalhes e relatórios do webinário. Os controles criar, projetar, editar e inserir não estão disponíveis por meio dessa permissão, e você não pode ser atribuído a um webinário como um co-host ou apresentador. |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
