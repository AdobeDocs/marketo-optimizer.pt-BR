---
title: Controle de conteúdo para modelos
description: Use as configurações de governança no Marketo Otimizer para bloquear conteúdo em modelos de email no nível da estrutura ou do componente, controlando quais autores de email podem editar.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---


# Governança de conteúdo para modelos

O bloqueio de conteúdo permite que os autores de modelos definam regras de governança que restringem quais partes de um modelo de email podem ser modificadas quando o modelo for usado em um email. Isso ajuda as equipes de marca e conformidade a proteger os principais elementos de design — como cabeçalhos, logotipos e conteúdo legal — enquanto permite que as equipes de marketing personalizem a mensagem dentro da estrutura aprovada.

>[!NOTE]
>
>O bloqueio de conteúdo é um recurso de governança no nível do editor. Ele controla o que os autores podem editar no espaço de design de email, mas não impede alterações feitas por meio da API.

Somente usuários com a permissão **[!UICONTROL Gerenciar modelos de conteúdo]** podem definir configurações de governança.

## Habilitar governança {#enable}

>[!NOTE]
>
>Nesta versão do Beta, somente os modelos de email são compatíveis.

1. Abra o modelo no espaço de design.
1. Na tela, clique no componente **[!UICONTROL Corpo]** para selecioná-lo.
1. Selecione o ícone _Configurações_ para o painel direito,
1. Alternar **[!UICONTROL Governança]**.
1. Para o **[!UICONTROL Modo]**, selecione o tipo de governança que deseja aplicar:

   | Modo | Descrição |
   | ---- | ----------- |
   | **[!UICONTROL Bloqueio de conteúdo]** | Bloquear seletivamente estruturas ou componentes específicos. As áreas desbloqueadas permanecem editáveis para os autores. |
   | **[!UICONTROL Somente leitura]** | Bloquear o modelo inteiro. Os autores podem aplicá-la a um email, mas não podem modificar nenhuma parte de seu conteúdo. |

1. Se você selecionou o modo Bloqueio de conteúdo, é possível definir ainda mais como os usuários podem interagir com o modelo.

   Ative a opção Habilitar adição de conteúdo e escolha uma das seguintes opções:

   * **[!UICONTROL Permitir adição de estrutura e conteúdo]** - Os usuários podem adicionar estruturas entre as existentes e adicionar componentes ou fragmentos de conteúdo em estruturas editáveis.

   * **[!UICONTROL Permitir somente adição de conteúdo]** - Os usuários podem adicionar componentes ou fragmentos de conteúdo dentro de estruturas editáveis, mas não podem adicionar ou duplicar estruturas.

### Bloquear uma estrutura {#lock-structure}

1. Na tela de desenho, selecione a estrutura (layout da coluna) que deseja proteger.
1. No painel direito, habilite a opção de alternância **[!UICONTROL Estrutura de bloqueio]**.

Todo o conteúdo aninhado em uma estrutura bloqueada é bloqueado automaticamente. Para permitir que um componente específico dentro de uma estrutura bloqueada permaneça editável, selecione o componente e habilite **[!UICONTROL Editável]** no painel direito.

Por padrão, os autores não podem excluir uma estrutura bloqueada. Para permitir a exclusão, habilite a opção **[!UICONTROL Permitir exclusão]** no painel direito.

### Bloquear um componente {#lock-component}

Em uma estrutura editável, é possível bloquear componentes de conteúdo individuais.

1. Selecione o componente na tela.
1. No painel direito, habilite a opção **[!UICONTROL Bloquear conteúdo]** e escolha o tipo de bloqueio:

   | Tipo de bloqueio | Descrição |
   | --------- | ----------- |
   | **[!UICONTROL Bloqueado]** | Impede modificações de conteúdo e estilo. Os autores não podem editar o texto ou alterar a aparência do componente. |
   | **[!UICONTROL Somente conteúdo editável]** | Permite que os autores editem texto e conteúdo, mas impede alterações de estilo, como cores, fontes e espaçamento. |
   | **[!UICONTROL Editável]** | Permite modificações completas mesmo em uma estrutura bloqueada. |

Por padrão, os autores não podem excluir um componente bloqueado. Para permitir a exclusão, habilite a opção **[!UICONTROL Permitir exclusão]** no painel direito.

### Permitir adições de conteúdo {#allow-additions}

Ao usar o modo **[!UICONTROL Bloqueio de conteúdo]**, você pode permitir que os autores adicionem novo conteúdo ao modelo, mantendo os elementos bloqueados protegidos:

1. Habilitar **[!UICONTROL Permitir adição de conteúdo]**.
1. Escolha se os autores podem adicionar estruturas e componentes de conteúdo ou apenas componentes de conteúdo.

## Identificar elementos bloqueados {#identify}

A **[!UICONTROL árvore de navegação]** no painel esquerdo mostra ícones de bloqueio e lápis para ajudar os autores a identificar rapidamente o que podem ou não modificar:

* Um **ícone de bloqueio** indica um elemento bloqueado.
* Um **ícone de lápis** indica um elemento que é editável.

Para melhorar ainda mais a visibilidade, habilite o botão de alternância **[!UICONTROL Realçar áreas editáveis]** para distinguir visualmente as áreas editáveis das áreas bloqueadas na tela.

## Considerações

As configurações de governança são salvas com o modelo. Qualquer email criado a partir de um modelo controlado herda sua configuração de bloqueio no momento em que é aplicado. A atualização das configurações de governança em um modelo não afeta os emails criados anteriormente a partir dele.
