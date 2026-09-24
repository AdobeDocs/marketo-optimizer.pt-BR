---
title: Tokens personalizados para o Personalization
description: Crie e gerencie Meus tokens personalizados para a personalização dinâmica de seus artefatos de marketing - defina variáveis de texto e número para programas no Marketo Otimizer.
TQID: 'https://experienceleague.adobe.com/utVM69g7aQSuF-V3XQIdVBqvBXyiDz1ZWr0WtE67UCg'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 177e7c3d0806febd730104b19787ba3cbea2914a
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%
---
# Tokens personalizados para personalização

A personalização de conteúdo usa tokens como espaços reservados ou variáveis que são preenchidas quando o artefato de conteúdo é gerado. Os tokens de personalização padrão estão disponíveis para emails, landing pages, fragmentos e templates. Você também pode definir um conjunto de tokens personalizados com valores específicos para o programa ou pasta. Este conjunto de tokens personalizados é chamado de _Meus tokens_ e qualquer um desses tokens personalizados está disponível para personalização.

<!-- 
When you add a custom token to an email, it is displayed as `{{my.TokenName}}`. For example, you might have `{{my.EventDate}}` or `{{my.WebinarSpeaker}}` tokens created to manage email content related to upcoming webinars in your program.
-->

Além de _Meus tokens_, que são específicos do programa ou pasta, você pode usar qualquer um dos tokens padrão (integrados) para personalização.

>[!IMPORTANT]
>
>Para a versão inicial do Marketo Optimizer, _Meus tokens_ são compatíveis com os nós de ação de jornada Alterar valor de dados e estão limitados ao uso em atributos de texto e sequência. _Meus Tokens_ estão **não** habilitados no editor do Personalization.

## Tokens de acesso {#access-tokens}

1. Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de marketing]**.

1. À direita da lista de recursos de **[!UICONTROL Marketing]**, selecione **[!UICONTROL Programas]**.

1. Na estrutura de árvore, selecione o programa ou a pasta para abrir os detalhes no espaço de trabalho central.

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

### Aninhamento de token {#nesting}

Quando você cria um token em um programa ou pasta, ele fica disponível para referência por objetos na hierarquia.

* **Token local** - O token está definido no mesmo programa ou pasta.
* **Token herdado** - O token é definido em um programa ou pasta pai, um ou mais níveis acima do programa ou pasta atual.
* **Token substituído** - O token está definido em um programa ou pasta pai, mas um valor diferente está definido no programa ou pasta atual. O status do token é alterado para _Substituído_, e todas as pastas derivadas, programas e artefatos de marketing herdam o novo valor.

![Tipos de token e herança](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### Criar um token {#create}

1. Na guia _[!UICONTROL Tokens]_, clique em **[!UICONTROL Criar]**.

1. Na caixa de diálogo, digite o **[!UICONTROL Nome]** do token.

   ![Insira um nome e um valor para o token de texto](./assets/token-create-dialog.png){width="400"}

   Não é possível usar espaços ou caracteres especiais no nome do token. Você pode usar _camel case_, como `EventType`, para usar um nome com várias palavras que seja facilmente identificado.

1. Escolha o **[!UICONTROL Tipo]** para o token.

1. Defina o **[!UICONTROL Valor]** para o token.

1. Clique em **[!UICONTROL Criar]**.

### Editar um token {#edit}

É possível editar o valor de qualquer um dos Meus tokens definidos, que substitui o valor de um token herdado.

<!-- (How does this affect live person journeys? ) -->

1. Em _[!UICONTROL Tokens]_, clique no ícone _Editar_ ao lado do nome do token.

1. No campo, altere o valor conforme necessário.

   ![Alterar o nome e o valor do token](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. Clique no ícone _Salvar_.

### Excluir um token {#delete}

Você pode excluir um token personalizado da lista se ele não estiver sendo usado no momento no conteúdo de email da jornada.

1. Em _[!UICONTROL Tokens]_, clique no ícone _Excluir_ ao lado do nome do token.

1. Na caixa de diálogo de confirmação, clique em **[!UICONTROL Excluir]**.

## Sugestão automática e visualização {#autosuggest}

Ao incluir um _Alterar valor de dados_ [nó de ação](./action-nodes.md) na jornada, você pode inserir `{{` no campo **[!UICONTROL Novo valor]** para revelar os tokens do menu _Sugestão Automática_. A lista exibida mostra namespaces e tokens individuais compatíveis. Somente os tokens de um tipo de dados compatível são listados.

Para _Meus tokens_, uma visualização do valor do token é exibida com o nome do token para facilitar a seleção do valor correto.

![Sintaxe no campo Novo valor para exibir o menu de autoutilização para tokens](./assets/program-tokens-change-data-value-autosuggest.png){width="500" zoomable="yes"}

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
