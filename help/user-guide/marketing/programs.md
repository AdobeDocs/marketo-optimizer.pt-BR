---
title: Programas
description: Saiba como usar programas para organizar seus esforços de marketing e gerenciar material de apoio e jornadas de marketing em um único local.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 1%

---

# Programas

Os programas são projetados para fornecer contexto compartilhado para seu material de apoio e jornadas de marketing, para que você possa gerenciar todos os aspectos de um esforço de marketing em um único local. Use atributos de programa para descrever seu programa e use o filtro _Membro do Programa_ para segmentar os públicos com base na associação ao programa, no status dos membros e no sucesso. Na guia Tokens, é possível gerenciar _Meus Tokens_ locais e os tokens herdados na estrutura de pastas.

## Acessar programas {#access-programs}

Cada programa consta na estrutura de pastas de _[!UICONTROL Marketing]_ e pode conter jornadas, listas e outros recursos para organizar suas iniciativas de marketing.

1. Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de marketing]**.

1. À direita da lista de recursos de **[!UICONTROL Marketing]**, selecione **[!UICONTROL Programas]**.

1. Use as ferramentas de _Pesquisa_ e _Filtro_ para localizar itens dentro da estrutura.

1. Selecione um programa ou pasta na estrutura para abrir seus detalhes no espaço de trabalho central.

   ![Programa selecionado na estrutura de árvore Programas](./assets/programs-tree-select.png){width="800" zoomable="yes"}

   Selecione qualquer uma das guias para acessar detalhes ou conteúdo do programa ou da pasta.

## Criar um programa {#create-program}

>[!IMPORTANT]
>
>Cada programa é baseado em um [tipo de programa](../admin/program-types.md), que define aspectos importantes do programa e seus membros. Verifique se você tem um tipo de programa definido para dar suporte ao seu programa antes de criá-lo.

1. Clique em **[!UICONTROL Criar programa]** na parte superior da estrutura da árvore de programas.

1. Na caixa de diálogo, selecione o local **[!UICONTROL Pai]** na estrutura Programas.

   Pode ser a raiz, uma pasta ou um programa existente.

1. Insira um **[!UICONTROL Nome]** exclusivo (obrigatório).

   ![Caixa de diálogo Criar programa](./assets/program-create-dialog.png){width="400"}

1. Escolha o **[!UICONTROL Tipo de programa]**, que determina os atributos do programa e os status dos membros.

1. (Opcional) Insira uma **[!UICONTROL Descrição]** para o programa.

   >[!TIP]
   >
   >Incluir uma descrição é uma prática recomendada e torna seus programas mais acessíveis e detectáveis.

1. Clique em **[!UICONTROL Criar]**.

## Atributos {#attributes}

Cada programa herda um conjunto de atributos de seu [tipo de programa](../admin/program-types.md). Use atributos para descrever os aspectos importantes dos seus programas de marketing, como datas de evento e atributos de local.

>[!NOTE]
>
>Próximos passos do Beta: Atributos do programa como tokens e como membro de restrições do programa

## Status {#statuses}

Cada programa herda um conjunto de status de membro de seu tipo de programa. Esses status podem ser atribuídos a membros do programa para uso na segmentação de público com o filtro Membro do programa.

Cada status é atribuído a uma etapa no tipo de programa, como 1, 2 ou 3. Os membros de um programa só podem mover de um status com o mesmo número de etapa (por exemplo, de _Não exibido_ para _Participou_) ou para um status com um número de etapa superior (por exemplo, de _Convidado_ para _Registrado_).

No tipo de programa, os status com _[!UICONTROL Marcar como êxito]_ selecionados são considerados bem-sucedidos.

### Alterar o status do programa {#change-program-status}

Para adicionar uma pessoa a um programa ou alterar seu status, ela deve passar por uma ação **_[!UICONTROL Alterar status do programa]_** [em uma jornada](./action-nodes.md). Isso os torna membros do programa e atribui um status a eles nesse programa.

### Corrigir o status de um programa {#correct-program-status}

Se as pessoas foram atribuídas a um status por engano e não puderem ser movidas para frente ou para trás para o status correto, você pode corrigir isso definindo primeiro a pessoa como _Não no Programa_ e depois definindo-a para o status correto.

## Membros {#members}

A guia **Membros** mostra um inventário das pessoas que são membros do programa.

<!-- How do they get there? I don't see this populated for any of the programs that I have reviewd -->

## Tokens {#tokens}

Use _Meus Tokens_ para gerenciar facilmente os detalhes do programa que aparecem em vários lugares, como datas e locais do evento, rodapés de email, anos fiscais e trimestres e muito mais. Esses tokens específicos do programa são strings especiais projetadas para reutilização em jornadas ou ativos de marketing para substituir um valor predeterminado. Por exemplo:

_Você foi convidado a participar da nossa exposição em `{{my.Event Date}}`._

Se você enviar este email por meio de uma jornada em um programa com uma _Data do evento_ Meu token definido como `2026-01-01`, o destinatário verá:

_Você foi convidado a participar da nossa exposição em 1/01/2026._

Meus tokens também podem ser atribuídos no nível da pasta Pastas e programas herdam quaisquer Meus tokens definidos para um pai na árvore. Um token herdado poderá ser substituído se um valor diferente for para o mesmo token, definido em um nível inferior. Por exemplo, você pode definir um rodapé de email na parte superior da estrutura de pastas, mas alterar o idioma de direitos autorais de um evento de co-marketing com um parceiro ou alterar o URL de um banner promocional de um programa específico do produto.

Para obter mais informações sobre como definir e usar Meus Tokens, consulte [Tokens personalizados para personalização](./personalization-my-tokens.md).

## Filtro Membro de Programa {#member-of-program}

_Membro do Programa_ é um filtro que permite segmentar suas listas dinâmicas com base no fato de alguém ser membro de um programa, em que status ele está e se ele é bem-sucedido nesse programa. Tenha cuidado ao usar as restrições do **_Programa_** e do **_Status_** juntas; use tipos correspondentes com os programas que você usa para filtros; caso contrário, ele poderia criar inadvertidamente um público que não pode ter membros.
