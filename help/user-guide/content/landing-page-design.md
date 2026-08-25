---
title: Design da landing page
description: Criar páginas de aterrissagem com ferramentas visuais - adicione componentes de conteúdo, formulários, CSS personalizado, personalização e pré-visualização de dispositivo para jornadas de pessoas no Marketo Otimizer.
feature: Landing Pages, Content Design Tools
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Design da página de destino

Depois de [criar uma página de aterrissagem](./landing-pages-create-publish.md#create-landing-page), use o espaço de design visual para criar os componentes estruturais e de conteúdo na sua página.

## Adicionar estrutura e conteúdo {#structure-content-landing-page}

{{$include /help/_includes/content-design-components-prime.md}}

### Adicionar CSS personalizado {#add-custom-css}

Você pode adicionar seu próprio CSS personalizado diretamente no espaço de design da página de destino. Use o CSS personalizado para aplicar um estilo avançado e específico, proporcionando maior flexibilidade e controle sobre a aparência do seu conteúdo. É uma prática recomendada adicionar esse estilo de mais alto nível antes de incluir componentes, como imagens, botões e texto.

Com pelo menos um componente de conteúdo na tela, selecione o componente **[!UICONTROL Corpo]** na árvore de navegação esquerda para acessar o editor de CSS personalizado.

![Acessar os estilos de corpo](assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

Consulte [Adicionar CSS personalizado para o seu conteúdo](./design-custom-css.md) para obter etapas, regras de sintaxe e solução de problemas.

### Adicionar ativos {#add-assets}

No espaço de design visual, selecione o ícone do _Assets_ ( ![Assets](../assets/do-not-localize/icon-assets-me.svg) ) na barra de navegação à esquerda para procurar e selecionar ativos de imagem da biblioteca de ativos [!DNL Marketo Optimizer].

Para obter as etapas para selecionar, substituir ou carregar ativos de imagem, consulte [Usar ativos para criação de conteúdo](./digital-asset-management.md#assets-authoring).

### Adicionar formulários {#add-forms}

{{$include /help/_includes/content-design-add-forms.md}}

### Navegar pelas camadas, configurações e estilos {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

### Personalizar conteúdo {#personalize-content}

[!DNL Marketo Optimizer] usa a sintaxe Handlebars para personalização. Os tokens são substituídos por valores dos dados de perfil de cada visitante quando a landing page é exibida.

_Para adicionar personalização :_

1. Selecione o componente de texto e clique no ícone _Adicionar personalização_ ( ![Ícone de personalização](../assets/do-not-localize/icon-personalize.svg) ) na barra de ferramentas.
1. Na caixa de diálogo de personalização, navegue na árvore de esquema à esquerda e selecione um atributo. O editor insere a expressão Handlebars correspondente.
1. Adicione um valor de fallback para lidar com dados ausentes, se necessário.
1. Clique em **[!UICONTROL Confirmar]** ou **[!UICONTROL Inserir]**. A expressão aparece em linha no campo.

Para obter detalhes sobre as ferramentas e a sintaxe do editor de expressões, consulte [editor do Personalization](./personalization-expressions.md).

### Editar rastreamento de URL vinculado {#linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}

![Clique no ícone Editar para acessar o rastreamento de links](assets/landing-page-link-tracking.png){width="400"}

Use o **[!UICONTROL Tipo de Rastreamento]** para controlar o rastreamento do link:

* **[!UICONTROL Rastreado]** - Ativa o rastreamento na URL do link.
* **[!UICONTROL Nunca]** - Nunca ativa o rastreamento da URL do link.

### Salve o trabalho {#save-your-work}

Clique em **[!UICONTROL Salvar]** a qualquer momento para salvar a landing page de rascunho.

Você pode continuar a fazer edições na página de rascunho. Quando estiver pronto para exibir a página e disponibilizá-la para vinculação em uma mensagem de email ou SMS, você poderá publicar a página.

### Exibir opções {#view-options}

Aproveite as opções de exibição e validação de conteúdo disponíveis no espaço de design visual.

* Aumentar/diminuir o zoom do conteúdo nas opções de zoom predefinidas.

* Alternar a exibição do conteúdo na área de trabalho, dispositivo móvel ou somente texto/texto sem formatação.
  * Clique no ícone _Exibir_ para visualizar o conteúdo entre dispositivos.
  * Selecione um dos dispositivos prontos para uso ou insira dimensões personalizadas para visualizar o conteúdo.

### Mais opções {#more-options}

No menu _[!UICONTROL Mais...]_, na parte superior do espaço de design visual, você pode realizar as seguintes ações:

![Clique em Mais para acessar ações de página de aterrissagem](assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL Redefinir página de aterrissagem]** - Clique nesta opção para limpar a tela de design visual para uma folha em branco e reiniciar a criação do conteúdo da página.
* **[!UICONTROL Alterar seu design]** - Retorne à _[!UICONTROL página inicial principal]_. A partir daí, você pode escolher outro modelo para reiniciar o processo de design ou optar por projetar a página do zero em uma tela em branco.
* **[!UICONTROL Exportar HTML]** - Baixe o conteúdo na tela visual para o sistema local no formato HTML empacotado como um arquivo zip.
