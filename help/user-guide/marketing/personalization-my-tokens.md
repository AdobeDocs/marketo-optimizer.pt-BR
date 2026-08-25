---
title: Tokens personalizados para o Personalization
description: Crie e gerencie Meus tokens personalizados para a personalização dinâmica de seus artefatos de marketing - defina variáveis de texto e número para programas no Marketo Otimizer.
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: 629
ht-degree: 3%

---

# Tokens personalizados para personalização

A personalização de conteúdo usa tokens como espaços reservados ou variáveis que são preenchidas quando o artefato de conteúdo é gerado. Os tokens de personalização padrão estão disponíveis para emails, landing pages, fragmentos e templates. Você também pode definir um conjunto de tokens personalizados com valores específicos para o programa ou pasta. Este conjunto de tokens personalizados é chamado de _Meus tokens_ e qualquer um desses tokens personalizados serve para personalização.

Ao adicionar um token personalizado a um email, ele é exibido como `{{my.TokenName}}`. Por exemplo, você pode ter `{{my.EventDate}}` ou `{{my.WebinarSpeaker}}` tokens criados para gerenciar conteúdo de email relacionado a webinários futuros.

Além de _Meus tokens_, que são específicos do programa ou pasta, você pode usar qualquer um dos tokens padrão (integrados) para personalização.

>[!NOTE]
>
>No momento, _Meus tokens_ não estão habilitados no Editor do Personalization para esta versão do Beta.

## Tokens de acesso

1. Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de marketing]**.

1. À direita da lista de recursos de **[!UICONTROL Marketing]**, selecione **[!UICONTROL Programas]**.

1. Na estrutura de árvore, selecione o programa ou pasta para abrir os detalhes no espaço de trabalho central.

1. Clique na guia **[!UICONTROL Tokens]**.

   ![Guia Tokens no programa selecionado](./assets/program-tokens-tab.png){width="800" zoomable="yes"}

   A guia exibe todos os tokens personalizados definidos na pasta ou no programa e qualquer definido para pastas ou programas principais.

### Tipos de token {#my-tokens}

Os _Meus tokens_ são variáveis personalizadas que você cria ou modifica para um programa ou uma pasta. Esse conjunto de tokens personalizado oferece suporte aos seguintes tipos de token:

| Tipo de token | Descrição |
| ---------- | ----------- |
| Texto | Este tipo contém uma sequência de texto padrão. O limite de tamanho para tokens de texto é de 524.288 caracteres (UTF-8) ou 2 MB. |
| Data | Este tipo contém um valor de data. A data é exibida como mês-dia-ano (por exemplo, 09-23-2026). |
| Data e hora | Esse tipo contém um valor de data e hora. |
| Número | Este tipo contém um valor inteiro padrão. |
| Email | Esse tipo contém um endereço de email válido. |
| Pontuação | Use este token para alterar a pontuação de um nó de ação de jornada. |
| Booleano | Este tipo contém um valor booleano padrão, verdadeiro ou falso. |
| Rich text | Esse tipo contém texto formatado. |

### Aninhamento de token

Quando você cria um token em um programa ou pasta, ele fica disponível para referência por outros objetos secundários.

* Token local - O token é definido no mesmo programa ou pasta.
* Token herdado - O token é definido em um programa ou pasta pai, um ou mais níveis acima do programa ou da pasta atual.
* Token substituído - o token é definido em um programa ou pasta pai, mas um valor diferente é definido no programa ou pasta atual. O status do token é alterado para _Substituído_, e todas as pastas derivadas, programas e artefatos de marketing herdam o novo valor.

![Tipos de token e herança](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### Criar um token

1. Na guia _[!UICONTROL Tokens]_, clique em **[!UICONTROL Criar]**.

1. Na caixa de diálogo, digite o **[!UICONTROL Nome]** do token.

   ![Insira um nome e um valor para o token de texto](./assets/token-create-dialog.png){width="400"}

   Não é possível usar espaços ou caracteres especiais no nome do token. Você pode usar _camel case_, como `EventType`, para usar um nome com várias palavras que seja facilmente identificado.

1. Escolha o **[!UICONTROL Tipo]** para o token.

1. Defina o **[!UICONTROL Valor]** para o token.

1. Clique em **[!UICONTROL Criar]**.

### Editar um token

É possível editar o valor de qualquer um dos Meus tokens definidos. Faça isso para substituir o valor de um token herdado.

<!-- (How does this affect live person journeys? ) -->

1. Em _[!UICONTROL Tokens]_, clique no ícone _Editar_ ao lado do nome do token.

1. No campo, altere o valor conforme necessário.

   ![Alterar o nome e o valor do token](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. Clique no ícone _Salvar_.

### Excluir um token

Você pode excluir um token personalizado da lista se ele não estiver sendo usado no momento no conteúdo de email da jornada.

1. Em _[!UICONTROL Tokens]_, clique no ícone _Excluir_ ao lado do nome do token.

1. Na caixa de diálogo de confirmação, clique em **[!UICONTROL Excluir]**.

<!--

## Use custom tokens in your content

When you are authoring email content for your programs, you can use any of the tokens from the _My Tokens_ list when you use the personalization tools in the visual design space.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Add personalization icon](assets/email-personalize-text.png){width="600"}

   This action opens the _Edit Personalization_ dialog. The dialog includes a _[!UICONTROL My tokens]_ folder in the _[!UICONTROL Personalization Tokens]_ library if there are custom tokens defined for the account journey.

1. To add one of your custom tokens to the blank space, expand the **[!UICONTROL My tokens]** folder, then click **+** or **...**.

   You can add any additional static text as needed.

   ![Construct personalized text using My tokens](assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->
