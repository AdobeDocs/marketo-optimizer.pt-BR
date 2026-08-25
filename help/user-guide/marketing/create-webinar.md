---
title: Criar um webinário
description: Adicione um ativo de webinário a um programa, crie-o em  [!DNL Adobe Connect], adicione co-hosts e apresentadores, execute uma sessão de teste e edite um webinário em tempo real em  [!DNL Marketo Optimizer].
keywords: null
role: User
feature: Channels
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---


# Criar um webinário

Adicione um webinário a um programa, crie seu registro e experiência de sala e equipe-o com coanfitriões e apresentadores no [!DNL Marketo Optimizer]. Antes de começar, revise a [Visão geral dos webinários interativos](webinars-overview.md) para conhecer os conceitos por trás dos estados, tokens e funções do webinário, e confirme se você tem a função **Criar e gerenciar webinars**.

## Adicionar um webinário a um programa

1. Localize o programa na estrutura de árvore _[!UICONTROL Programas]_ ou [crie um programa](./programs.md#create-program) primeiro.

1. Clique no ícone do _Mais menu_ ( **...** ) ao lado do nome do programa e selecione **[!UICONTROL Criar webinário]**.

1. Na caixa de diálogo, insira os detalhes principais do webinário:

   * **Título** e **Descrição**.
   * **Agendamento** - data e hora de início, fuso horário e duração.
   * **Público-alvo máximo** - a capacidade da licença de webinário a ser usada nesta sessão.

   ![A caixa de diálogo Agendar Webinar com campos do programa pai, nome, duração, fuso horário, hora de início e público máximo, além dos botões Cancelar e Criar.](assets/webinar-create-schedule-dialog.png){width="500" zoomable="yes"}

   >[!NOTE]
   >
   >A entrega de sessão única versus recorrente e as opções de áudio/vídeo não podem ser configuradas no momento. Cada webinário é uma única sessão com vídeo ativado.

1. Adicionar **Co-hosts** e **Apresentadores**.

   >[!NOTE]
   >
   >Na versão atual, adicione todos como contatos externos por nome e email, tenham ou não uma conta SSO do Adobe qualificada para função.<!-- See [Permissions](./webinars-overview.md#permissions) for what each role governs. --> Para obter as etapas completas, consulte [_Adicionar co-hosts e apresentadores_](#add-co-hosts-and-presenters).

1. (Opcional) Personalize o modelo da sala, a marca e o layout.

   Essas opções são gerenciadas em [!DNL Adobe Connect] e também podem ser refinadas posteriormente da superfície de design. Consulte [Criar o webinário](#design-the-webinar).

1. Clique em **[!UICONTROL Salvar]**.

   Salvar registra o webinário no programa e disponibiliza seus tokens, atributos e atividades para cada jornada e ativo nesse programa.

>[!NOTE]
>
>A criação do webinário é equivalente a _Webinars Interativos_ em [!DNL Marketo Engage]. Portanto, os campos são familiares se você tiver feito isso através desse aplicativo.

## Criar o webinário {#design-the-webinar}

Para abrir a superfície de design do [!DNL Adobe Connect], incorporada diretamente no [!DNL Marketo Optimizer], onde você configura a sala, a página de registro e os layouts, use o _[!UICONTROL Criar seu webinário]_.

1. Na página do webinário, clique em **Criar seu webinário**.

1. Escolha um **Modo de entrega**:

   &#x200B;- **Ao vivo** - Os apresentadores hospedam a sessão em tempo real.
   &#x200B;- **Simulado ao vivo** - O conteúdo pré-gravado é reproduzido no horário agendado, junto com bate-papo ao vivo, pesquisas e perguntas e respostas.

1. Escolha uma **sala de webinários**.

   Crie uma nova sala ou reutilize uma existente.

1. Selecione um **Modelo**, **Idioma** e **Tema** e, em seguida, visualize o layout.

1. Adicione e organize pods conforme necessário.

   Os pods disponíveis incluem compartilhamento, anotações, vídeo, bate-papo, lista de participantes, arquivos, links da Web, pesquisas, perguntas e respostas e pesquisas.

1. Entre na sala para analisar a experiência e saia quando terminar.

1. Salve as alterações.

   Uma confirmação é exibida para indicar que o webinário foi criado com êxito.

>[!TIP]
>
>Crie o webinário antes de adicionar coanfitriões e apresentadores, para que seu acesso e controles se apliquem à sala concluída.

A personalização da sala, como logotipo, cores e planos de fundo virtuais, é feita diretamente em [!DNL Adobe Connect].

## Adicionar co-hosts e apresentadores {#add-co-hosts-and-presenters}

1. Na página do webinário, acesse a seção **Equipe do webinário**.

1. Clique em **Adicionar co-host** ou **Adicionar apresentador**.

1. Na caixa de diálogo, digite o **[!UICONTROL Nome]**, **[!UICONTROL Sobrenome]** e o **[!UICONTROL Endereço de email]** da pessoa e clique em **[!UICONTROL Adicionar]**.

   >[!NOTE]
   >
   >Na versão atual, todos são adicionados da mesma forma, por nome e email, independentemente de terem ou não uma conta SSO do Adobe. Consulte [Permissões](webinars-overview.md#permissions) para saber o que as funções de **co-host do webinário** e **apresentador do webinário** regem depois que alguém é adicionado.

   Uma confirmação é exibida depois que a pessoa é adicionada e ela é listada em **Co-hosts** ou **Apresentadores** na seção Equipe do webinário.

## Testar o webinário {#test-the-webinar}

Antes de promover o webinário, execute uma sessão de teste para confirmar a sala, os pods e o acesso do apresentador, conforme esperado.

>[!NOTE]
>
>O modo de teste não afeta o status de membro do webinário de nenhuma pessoa. Você pode executar um teste quantas vezes precisar sem se registrar ou convidar ninguém.

## Editar um webinário ao vivo {#edit-a-live-webinar}

Você pode editar um webinário após o início dos registros, mas faça isso com cuidado:

&#x200B;- Editar o agendamento pode acionar notificações de atualização para pessoas já registradas. A capacidade de editar webinários agendados é configurável.
&#x200B;- Os campos referenciados por tokens em emails em tempo real exigem confirmação explícita para remoção, pois isso interrompe o conteúdo que já está agendado para envio.
