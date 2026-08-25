---
title: Jornadas de promoção e acompanhamento de webinários
description: Crie jornadas de promoção, de dia de entrega e de nutrição pós-webinário em torno de um webinário no Marketo Otimizer e personalize o conteúdo com tokens de webinário.
keywords: null
role: User
feature: Person Journeys
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 0%

---


# Promoção do webinário e jornadas de acompanhamento

Depois de adicionar um webinário a um programa, crie uma ou mais [jornadas](./person-journeys.md) dentro desse mesmo programa para convidar pessoas, lembrá-las, entregar a sessão e acompanhar depois.

>[!NOTE]
>
>Esta página aborda a criação dessas jornadas manualmente. Para que o Colaborador crie as mesmas jornadas para você a partir de um modelo, consulte [Criar webinários com o Colaborador](../agents/webinar-creation.md).

## Criar uma jornada promocional {#build-promotion-journey}

Uma jornada de promoção típica convida as pessoas, rastreia seu registro e as lembra quando o webinário se aproxima.

1. [Criar a jornada de pessoa](./person-journeys.md#create-a-person-journey).

1. [Selecione um público para a jornada](./person-audience-node.md).

1. Adicione um nó **[!UICONTROL Enviar Email]** com um email de convite.

   Use tokens de webinário como _Título_ e _Data e hora de início_ no conteúdo e vincule à página de registro do webinário.

1. Adicione um nó **[!UICONTROL Realizar uma ação]**, selecione a ação **[!UICONTROL Alterar status do membro do webinário]**, selecione o webinário e defina o status como _Convidado_.

   Coloque-o imediatamente após o nó **[!UICONTROL Enviar email]** do convite.

   >[!NOTE]
   >
   >Normalmente, você só define _Convidado_ e _Registrado_ de uma jornada promocional. [!DNL Adobe Connect] normalmente define _Participou_, _Não apareceu_ e _Participou sob Demanda_ automaticamente. A mesma ação pode substituir esses status posteriores de uma jornada, se necessário, mas somente para frente, correspondendo à progressão linear descrita em [_Status do webinário_](webinars-overview.md#webinar-status).

1. Hospede o formulário de registro em uma [página de aterrissagem](../content/landing-pages.md).

1. Adicione um nó **[!UICONTROL Realizar uma ação]**, selecione a ação **[!UICONTROL Alterar status do membro do webinário]**, selecione o webinário e defina o status como _Registrado_ (acionado pelo envio do formulário).

   Mover alguém para _Registrado_ faz duas coisas automaticamente:

   * [!DNL Adobe Connect] gera a URL de Ingresso individual dessa pessoa.
   * Ele envia o email de confirmação, se você tiver configurado um, contendo o token de _URL de Ingresso_.

1. Crie uma cadência de lembrete usando os nós **[!UICONTROL Wait]** com tempo relativo para o token do _Start Datetime_ do webinário.

   Por exemplo, defina-o como uma semana antes, um dia antes e uma hora antes.

1. Adicione um nó **[!UICONTROL Wait]** ao token de _Data e hora de término_ do webinário, para que a jornada seja pausada até que a sessão ativa termine.

   Prossiga para [Criar uma jornada pós-webinário](#build-post-webinar-journey) aqui.

   >[!NOTE]
   >
   >As alterações no status do webinário não estão disponíveis no momento como um **[!UICONTROL Ouvir um gatilho de evento]**. Use um nó **[!UICONTROL Wait]** cronometrado seguido por um nó **[!UICONTROL Split paths]** no status do webinário, como mostrado abaixo, em vez de escutar a alteração de status propriamente dita.

## Personalizar emails

Os tokens do webinário são renderizados no conteúdo do email: assunto, corpo, pré-cabeçalho e remetente. Consulte [Tokens de webinário](webinars-overview.md#webinar-tokens) para obter a lista completa.

>[!NOTE]
>
>Os tokens do webinário não estão disponíveis atualmente na landing page de registro ou em formulários. Em vez disso, personalize aqueles com tokens de programa padrão e reserve a personalização específica do webinário (como o URL de associação e URL de gravação) para email.

>[!IMPORTANT]
>
>O token da **_URL de Ingresso_** resolve somente para pessoas cujo status do webinário é _Registrado_ ou posterior. O token da URL _**de**_ Gravação só é resolvido depois que a gravação é publicada. Ambos resolvem com antecedência um valor vazio em vez de um erro, portanto, verifique se seus emails são renderizados de forma aceitável antes da publicação.

## Realizar o webinário {#deliver-webinar}

No horário agendado, o webinário será executado em [!DNL Adobe Connect]:

* Apresentadores e co-anfitriões ingressam usando seu link individual na seção **Equipe de webinário** do webinário.
* Participantes ingressam usando seu token pessoal de **URL de Ingresso**.
* O [!DNL Adobe Connect] captura a atividade da sessão (perguntas, respostas de sondagem, cliques em links, downloads de ativos e chamadas manuais) e envia-a de volta para [!DNL Marketo Optimizer] como [atividades de webinário](webinars-overview.md#webinar-activities), disponíveis para qualquer jornada de escuta.

Se o webinário estiver definido como **Simulado ao vivo**, o conteúdo pré-gravado será reproduzido automaticamente no horário agendado, enquanto os apresentadores participarão ao vivo por meio de bate-papo, pesquisas e perguntas e respostas.

## Criar uma jornada pós-webinário {#build-post-webinar-journey}

Após o término da sessão ao vivo, [!DNL Adobe Connect] define o status do webinário de cada pessoa como _Participou_ ou _Não compareceu_. Quando o nó **[!UICONTROL Wait]** da jornada for liberado, ramifique usando esse status com um nó **[!UICONTROL Dividir caminhos]**.

1. Adicione um nó **[!UICONTROL Split paths]** com uma condição no status do webinário, como _Participou do webinário_.

1. No caminho _Participou_, envie um email de agradecimento.

   Por exemplo, enviar uma repetição e um acompanhamento de recursos. Em seguida, use um nó **[!UICONTROL Wait]** e um email call-to-action de próxima etapa.

1. No caminho _No-Show_, envie um email _nós sentimos sua falta_.

   No conteúdo do email, convide-os a assistir à gravação. Em seguida, use um nó **[!UICONTROL Wait]** e um email de acompanhamento resumindo os principais argumentos.

1. Personalize cada caminho usando outras atividades do webinário.

   Por exemplo, ramificar ou personalizar com base em _Responde a uma enquete_ com uma resposta específica.

1. Use o token de **_URL de Gravação_** em qualquer um dos caminhos depois de resolvê-lo, para que as pessoas possam assistir sob demanda.

   **_O envolvimento sob demanda_** (duração da observação, cliques em links de reprodução e downloads) é assimilado como as mesmas atividades do webinário, marcado com um modo de _Sob demanda_. Ao contrário dessas atividades, a exibição sob demanda também move uma pessoa _Sem apresentação_ para o status do webinário _Participou sob demanda_. Como resultado, um caminho de jornada _No-Show_ pode chegar às pessoas que assistem à gravação mais tarde. Divida mais no status do webinário ou verifique novamente depois de um atraso, se quiser um tratamento diferente para pessoas que assistem sob demanda.
