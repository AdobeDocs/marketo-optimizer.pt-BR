---
title: Criação de fragmentos
description: Crie fragmentos de conteúdo reutilizáveis com ferramentas de design visual - adicione estrutura, ativos, personalização, conteúdo condicional e rastreamento de URL vinculado para emails e modelos no Marketo Otimizer.
TQID: 'https://experienceleague.adobe.com/KbnYkUMVfjBv5ST55WwAqYiMDkynwSw4BKIP0bsE-DI'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 3%

---

# Criação de fragmentos

Depois de [criar um fragmento](./fragments.md#create-fragments), use o espaço de design visual para criar os componentes de estrutura e conteúdo no fragmento.

## Adicionar estrutura e conteúdo {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## Adicionar ativos {#add-assets}

No espaço de design visual, selecione o ícone do _Assets_ ( ![Assets](../assets/do-not-localize/icon-assets-me.svg) ) na barra de navegação à esquerda para procurar e selecionar ativos de imagem da biblioteca de ativos [!DNL Marketo Optimizer].

Para obter as etapas para selecionar, substituir ou carregar ativos de imagem, consulte [Usar ativos para criação de conteúdo](./digital-asset-management.md#assets-authoring).

## Navegar pelas camadas, configurações e estilos {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## Personalizar conteúdo {#personalize-content}

[!DNL Marketo Optimizer] usa a sintaxe Handlebars para personalização. Os tokens são substituídos no momento do envio por valores dos dados de perfil de cada recipient.

_Para adicionar personalização :_

1. Selecione o componente de texto e clique no ícone _Adicionar personalização_ ( ![Ícone de personalização](../assets/do-not-localize/icon-personalize.svg) ) na barra de ferramentas.
1. Na caixa de diálogo de personalização, navegue na árvore do esquema à esquerda e selecione um atributo de perfil. O editor insere a expressão Handlebars correspondente — por exemplo, `{{profile.firstName}}`.
1. Adicione um valor de fallback para lidar com dados ausentes, se necessário — por exemplo, `{{profile.firstName | default: "there"}}`.
1. Clique em **[!UICONTROL Confirmar]** ou **[!UICONTROL Inserir]**. A expressão aparece em linha no campo.

Para obter detalhes sobre as ferramentas e a sintaxe do editor de expressões, consulte [editor do Personalization](./personalization-expressions.md).

## Editar rastreamento de URL vinculado {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
