---
title: Módulos de conteúdo
description: Saiba como adicionar e personalizar módulos para emails, landing pages, fragmentos visuais e modelos de email. Use layouts preparados para criar designs de conteúdo consistentes.
feature: Content Design Tools
role: User
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: 73e54767086a103c11dce78a0295ad435c07f2c0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 0%
---
# Módulos de conteúdo

Use módulos em [!DNL Adobe Marketo Optimizer] para reunir conteúdo de layouts preparados. Cada módulo combina [estrutura](./structure-components.md) e [componentes de conteúdo](./content-components.md) com o conteúdo padrão que você substitui por seu próprio texto, imagens e links.

Ao contrário dos componentes de conteúdo individuais, os módulos fornecem seções completas como cabeçalhos, banners, cartões e rodapés. Adicione um módulo à tela e, em seguida, personalize seus componentes em vez de criar cada seção a partir de um espaço vazio.

Os módulos são diferentes de [fragmentos visuais](./fragments.md). Um módulo se torna parte do conteúdo que você está projetando. Um fragmento visual é um ativo de conteúdo salvo que pode ser reutilizado em emails e modelos de email.

## Guia Módulos

Use a guia **[!UICONTROL Módulos]** no espaço de design visual para qualquer um dos seguintes tipos de conteúdo:

* Email - Consulte [_Criação de conteúdo de email_](./email-authoring.md).
* Página de aterrissagem - Consulte [_Design da página de aterrissagem_](./landing-page-design.md).
* Fragmento visual - Consulte [_Criação de fragmentos_](./fragment-authoring.md).
* Modelo de email - Consulte [_Criar modelos de email_](./templates-create.md#build-new).

![Categorias de módulos exibidas ao lado da tela de design visual](../../assets/modules-left-panel.png){width="600" zoomable="yes"}

## Categorias de módulo

Expanda uma categoria para escolher um layout. Esses layouts fornecem disposições diferentes do conteúdo da seção, como uma, duas ou três colunas.

| Categoria | Usar |
| --- | --- |
| [!UICONTROL Cabeçalhos] | Apresente seu conteúdo com um logotipo, links de navegação e texto de introdução. |
| [!UICONTROL Herói] | Destaque um anúncio ou promoção com uma seção de banner. |
| [!UICONTROL Depoimento] | Apresentar as declarações do cliente em uma seção estilizada. |
| [!UICONTROL Cartões] | Organize produtos, artigos ou outros itens de conteúdo em uma grade. |
| [!UICONTROL Equipes] | Apresente membros da equipe, autores ou palestrantes com fotos, nomes e funções. |
| [!UICONTROL Rodapés] | Termine seu conteúdo com links de navegação, links sociais e texto legal. |

## Adicionar e personalizar módulos

Comece com um módulo que corresponda à seção que você deseja criar e, em seguida, adapte seu conteúdo e estilo. Substitua os links e o texto padrão pelo conteúdo apropriado para seu canal.

>[!NOTE]
>
>Para emails de marketing, inclua um link para opção de não participação e [verifique alertas por email](../marketing/email-channel.md#alerts) antes de publicar o email.

1. Abra email, página de aterrissagem, fragmento visual ou modelo de email no espaço de design visual.

   À esquerda da tela, a guia **[!UICONTROL Módulos]** é exibida por padrão.

1. Para revisar os layouts disponíveis, expanda uma categoria.

   Você também pode usar o campo de pesquisa para localizar um módulo por nome.

1. Arraste um módulo para a tela.

   ![A lista de módulos é filtrada por pesquisa e um módulo é arrastado para a tela.](../../assets/modules-search-drag.png){width="600" zoomable="yes"}

1. Revise os elementos no módulo.

   Cada módulo inclui conteúdo padrão que pode ser editado. Clique no ícone da _Árvore de navegação_ ( ![Ícone da árvore de navegação](../assets/do-not-localize/icon-navigation-tree.svg) ) à esquerda da tela para exibir a estrutura e os elementos no módulo.

   ![A árvore de navegação exibe a estrutura e os elementos do módulo selecionado.](./assets/modules-navigation-tree.png){width="600" zoomable="yes"}

1. Selecione um elemento no módulo para personalizá-lo.

   Você pode substituir o texto padrão, escolher imagens de seus ativos e atualizar links para seu conteúdo.

   Use as guias **[!UICONTROL Configurações]** e **[!UICONTROL Estilos]** para ajustar o componente selecionado.

   ![Componente de texto selecionado no módulo com opções de Estilos exibidas](../../assets/modules-select-element-styles.png){width="600" zoomable="yes"}

1. Para adicionar outro elemento, selecione a guia **[!UICONTROL Componentes]** e arraste um [componente de conteúdo](./content-components.md) para o módulo.

   Se você adicionar um componente à estrutura do módulo, ele herdará o estilo do módulo por padrão. Ajuste seus estilos conforme necessário.

   ![Um componente de texto arrastado para a estrutura do módulo com texto de espaço reservado formatado exibido](./assets/modules-select-element-add-component.png){width="800" zoomable="yes"}

1. Selecione **[!UICONTROL Salvar]** para salvar suas alterações.

>[!NOTE]
>
>Quando um tema de marca é aplicado ao conteúdo de email, os módulos herdam seus estilos. Escolha o modo de estilo ao [criar um email do zero](./email-authoring.md#design-from-scratch).

## Reutilizar conteúdo personalizado do módulo

Para criar conteúdo de módulo reutilizável, [crie um fragmento visual](./fragments.md#create-fragments) e adicione e personalize módulos no espaço de design do fragmento. Salve e publique o fragmento para disponibilizá-lo para uso em emails e modelos de email.

Em seguida, [insira o fragmento](./fragments.md#add-to-content) em outros emails ou modelos de email.
