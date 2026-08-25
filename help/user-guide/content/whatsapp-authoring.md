---
title: Criação no WhatsApp
description: Crie mensagens de WhatsApp para jornadas de pessoas usando modelos aprovados do Meta, tokens de personalização e configurações de entrega no Marketo Otimizer.
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 1%

---

# Criação no WhatsApp

Use o [!DNL Adobe Marketo Optimizer] para enviar mensagens do WhatsApp para pessoas em seus dispositivos móveis. Você pode criar, personalizar e pré-visualizar mensagens usando modelos de mensagem aprovados do Meta no editor do WhatsApp.

Antes de criar mensagens do WhatsApp para jornadas de pessoas, verifique se você tem um [canal do WhatsApp configurado](../admin/configuration-channels-whatsapp.md) nas configurações do _[!UICONTROL Administrador]_.

>[!NOTE]
>
>Somente _elementos de mensagem de saída_ do WhatsApp têm suporte no [!DNL Marketo Optimizer].

+++ Elementos de mensagem compatíveis e opções do call-to-action

Use as tabelas desta seção como referência para conteúdo de saída do WhatsApp que pode ser incluído em modelos aprovados do Meta e para botões interativos que podem ser adicionados a mensagens.

A tabela a seguir resume os elementos de mensagem compatíveis e seus requisitos.

| Elemento de mensagem | Descrição |
| - | - |
| Cabeçalhos | Texto opcional que aparece acima do corpo da mensagem. |
| Texto | Aceita conteúdo dinâmico por meio de parâmetros. |
| Imagens (JPEG, PNG) | Deve estar no formato RGB de 8 bits ou RGBA e abaixo de 5 MB no tamanho. |
| Vídeos | Deve ser 3GPP ou MP4, com menos de 16 MB, e hospedado por URL. |
| Áudio | Disponível somente para mensagens de resposta. Deve ser o formato AAC, AMR, MP3, MP4 audio ou OGG, hospedado em um URL e menos de 16 MB. |
| Documentos | Deve ter menos de 100 MB, hospedado em uma URL e em um dos seguintes formatos: `.txt`, `.xls`/`.xlsx`, `.doc`/`.docx`, `.ppt`/`.pptx` ou `.pdf`. |
| Corpo de texto | Aceita conteúdo dinâmico por meio de parâmetros. |
| Texto do rodapé | Aceita conteúdo dinâmico por meio de parâmetros. |

A tabela a seguir lista os tipos de botão do call-to-action e como cada um se comporta na mensagem.

| Call to action | Descrição |
| - | - |
| Visitar site | Somente um botão é permitido, com parâmetros variáveis incluídos. |
| Chamar no WhatsApp | Fornece um botão que abre um bate-papo do WhatsApp com o número de telefone especificado diretamente da mensagem. |
| Telefonar para número | Fornece um botão que inicia uma chamada telefônica para o número especificado quando tocado pelo usuário. |

+++

## Adicionar uma ação do WhatsApp em uma jornada de pessoa {#add-whatsapp-journey-action}

>[!IMPORTANT]
>
>**Gerenciamento de consentimento do WhatsApp**: de acordo com as políticas e os regulamentos aplicáveis da Meta, todas as mensagens de marketing do WhatsApp devem ser enviadas apenas aos destinatários que optaram por receber comunicações. Os destinatários do WhatsApp podem recusar a qualquer momento respondendo com uma palavra-chave de recusa. As respostas de recusa são atendidas automaticamente e os perfis correspondentes são removidos dos futuros públicos-alvo de mensagens de marketing.

Você pode configurar entregas de mensagens do WhatsApp em uma jornada de pessoa quando [adicionar um nó _[!UICONTROL Executar uma ação]_](../marketing/action-nodes.md) e escolher **[!UICONTROL Enviar WhatsApp]** na lista de ações.

## Criar a mensagem do WhatsApp {#create-whatsapp-message}

1. Na parte inferior do painel _[!UICONTROL Realizar uma ação]_, clique em **[!UICONTROL Criar WhatsApp]**.

1. Na caixa de diálogo, insira um **[!UICONTROL Nome]** (obrigatório) e uma **[!UICONTROL Descrição]** (opcional) exclusivos para a mensagem do WhatsApp.

   ![Caixa de diálogo Criar nova mensagem do WhatsApp](assets/whatsapp-create-dialog.png){width="400"}

1. Clique em **[!UICONTROL Criar]**.

   O _espaço de design do WhatsApp_ é aberto, onde você pode definir as ações do WhatsApp e criar o conteúdo para enviar a mensagem.

### Selecionar a configuração de ações {#select-actions-configuration}

1. No _espaço de design do WhatsApp_, selecione a guia **[!UICONTROL Ações]**.

1. Para **[!UICONTROL configuração do WhatsApp]**, selecione a configuração que aceita as ações de marketing e as configurações de entrega de mensagens para suas necessidades.

   ![Criar WhatsApp - guia Ações](assets/whatsapp-create-actions-tab.png){width="700" zoomable="yes"}

1. Clique em **[!UICONTROL Editar conteúdo]** para continuar com os parâmetros e o texto da mensagem.

### Selecionar um modelo de mensagem {#select-message-template}

As mensagens do WhatsApp são enviadas usando modelos de mensagem pré-aprovados da sua conta comercial do Meta WhatsApp. **Os modelos devem ser revisados e aprovados pelo Meta** antes que você possa usá-los em [!DNL Marketo Optimizer]. Para gerenciar e enviar modelos para aprovação, trabalhe com o administrador da conta [!DNL Meta Business Manager].

1. Para **[!UICONTROL Selecionar categoria do modelo]**, escolha uma das seguintes opções:

   * Marketing
   * Utilitário
   * Autenticação

1. Para **[!UICONTROL Selecionar modelo de WhatsApp]**, escolha um modelo aprovado para a conta comercial configurada.

   O conteúdo do template é carregado no editor de mensagens, exibindo a estrutura do template e quaisquer campos de variável disponíveis para personalização.

   ![Modelo de mensagem do WhatsApp selecionado com mensagem carregada na janela de visualização](assets/whatsapp-create-select-template.png){width="700" zoomable="yes"}

   O sistema organiza modelos por categoria (_Marketing_, _Utilitário_ e _Autenticação_) e status. Somente modelos **_Aprovados_** estão disponíveis para seleção. Para obter mais informações sobre como criar modelos do WhatsApp, consulte [_Criar modelos de mensagem para sua conta do WhatsApp Business_](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343) na documentação do Meta.

### URLs de imagem {#image-urls}

Se o modelo incluir imagens, use o campo **[!UICONTROL URL da Imagem]** para adicionar URLs de mídia para substituir quaisquer espaços reservados no modelo. As mídias de modelo do Meta são apenas espaços reservados. Para exibir imagens, áudio ou vídeo corretamente, você deve usar URLs externos do Adobe Experience Manager ou de outras fontes.

### Personalizar o conteúdo da mensagem {#personalize-message-content}

Os modelos aprovados de WhatsApp podem incluir espaços reservados para variáveis definidos com o uso de dados de perfil ou valores dinâmicos.

Para cada campo de variável exibido no modelo, clique no ícone _Personalizar_ ( ![Ícone Personalizar](../assets/do-not-localize/icon-personalize.svg) ) ao lado do campo.

![Variáveis no modelo do WhatsApp](assets/whatsapp-create-variables.png){width="700" zoomable="yes"}

A caixa de diálogo fornece acesso a tokens de pessoas e tokens do sistema. Os tokens padrão e personalizados estão incluídos. Você pode usar a barra _Pesquisa_ para localizar o token necessário ou navegar pela árvore de pastas para localizar e selecionar qualquer um dos tokens.

Quando seus tokens de personalização forem definidos, clique em **[!UICONTROL Salvar]** para salvar as alterações e retornar ao espaço de trabalho principal da mensagem do WhatsApp.
