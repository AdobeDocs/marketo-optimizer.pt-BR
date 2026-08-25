---
title: Ativos
description: Gerencie ativos de imagem do Marketo Otimizer para emails, modelos e fragmentos visuais.
feature: Assets, Content
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 19%

---

# Ativos

No [!DNL Adobe Marketo Optimizer], os ativos são normalmente as imagens usadas ao criar conteúdo para oferecer suporte a jornadas. Você pode usar essas imagens em seus [emails](email-authoring.md), [modelos de email](templates.md) e [fragmentos visuais](email-authoring.md#visual-fragments) do seletor de ativos ou em uma interface simples de arrastar e soltar no espaço de design visual.

Formatos de arquivo compatíveis: JPG, JPEG, GIF, PNG, EPS, SVG e RGB

<!--

>In this Beta release, you can choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas. Modifying assets in Marketo Engage after the initial copy is **not** reflected in [!DNL Marketo Optimizer].

-->

>[!NOTE]
>
>Você pode carregar ativos de imagem da biblioteca _[!UICONTROL Assets]_ ou do espaço de design de conteúdo. Estes ativos carregados estão disponíveis para uso somente na instância [!DNL Marketo Optimizer].
>
>A importação de ativos de sistemas externos e o acesso a uma biblioteca de ativos pré-preenchida ainda não estão disponíveis. As versões futuras devem incluir a importação de ativos dos sistemas existentes, suporte a pastas e recursos ampliados de gerenciamento de ativos.

<!-- You can [edit these assets using Adobe Express](./image-edit-adobe-express.md), and move them into folders to organize them for use across your emails, templates, and fragments. -->

A biblioteca **Assets** fornece acesso ao repositório centralizado para armazenar e gerenciar imagens e outros ativos criativos. Ele inclui recursos alimentados por IA que geram metadados automaticamente e permitem a pesquisa em linguagem natural.

Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de conteúdo]** e selecione **[!UICONTROL Assets]**.

![exibição de lista da biblioteca do Assets mostrando colunas de metadados classificáveis](./assets/dam-asset-library-list-view.png){width="800" zoomable="yes"}

>[!BEGINSHADEBOX]

Na primeira vez que você acessar a biblioteca do _[!UICONTROL Assets]_, verifique os [_[!UICONTROL Termos de Uso da IA Gerativa &#x200B;]_](https://www.adobe.com/br/legal/licenses-terms/adobe-gen-ai-user-guidelines.html) e confirme seu contrato.

![Caixa de diálogo do contrato de Termos de Uso da IA de Geração na biblioteca da Assets](./assets/dam-asset-library-gen-ai-agree.png){width="500"}

>[!ENDSHADEBOX]

A biblioteca é compatível com duas opções de layout:

* **[!UICONTROL Lista]** — Clique no ícone _Exibição de lista_ ( ![Ícone de exibição de lista](../assets/do-not-localize/icon-falco-list-view.svg) ) para exibir ativos em uma tabela classificável com colunas de metadados.
* **[!UICONTROL Galeria]** — Clique no ícone _Modo de exibição de galeria_ ( ![Ícone de modo de exibição de galeria](../assets/do-not-localize/icon-falco-gallery-view.svg) ) para exibir ativos como uma grade de miniaturas visuais.

## Pesquisar por ativos {#find-assets}

Use o campo _[!UICONTROL Pesquisa]_ para localizar ativos descrevendo o que é necessário em linguagem natural. Os resultados da pesquisa se baseiam em metadados gerados por IA, portanto, você não está limitado a pesquisar por nome de arquivo.

**Exemplos:**

* `team members`
* `nature`
* `exercise`

![Imagem selecionada nos resultados da pesquisa na biblioteca Assets](./assets/dam-asset-library-select-image.png){width="700" zoomable="yes"}

## Exibir detalhes do ativo {#view-details}

Selecione qualquer ativo na exibição de lista ou galeria para abrir a exibição de detalhes à direita, que exibe uma descrição gerada por IA, tags, palavras-chave e campos de metadados adicionais. Essas informações são geradas automaticamente quando o ativo é carregado. Selecione a guia **[!UICONTROL Metadados de IA]** para revisar a descrição, as marcas e os metadados gerados.

![Exibição detalhada do ativo mostrando metadados e marcas gerados por IA](./assets/dam-asset-library-select-image-metadata.png){width="700" zoomable="yes"}

## Fazer upload de um ativo {#upload}

1. Clique em **[!UICONTROL Carregar]** na parte superior direita.

1. Na caixa de diálogo, arraste e solte um arquivo do seu sistema local.

   ![Carregar um ativo de imagem](./assets/dam-upload-assets-dialog.png){width="450"}

   Como alternativa, você pode clicar em **[!UICONTROL Selecionar arquivo do seu computador]** para usar o sistema de arquivos local para localizar e selecionar o arquivo.

1. Clique em **[!UICONTROL Carregar arquivo]** para confirmar e carregar o arquivo para o repositório.

Após a conclusão do upload, o sistema gera automaticamente uma descrição, atribui tags e palavras-chave e extrai atributos visuais, como assunto e configuração. Não é necessária nenhuma marcação manual. A nova imagem será exibida com o status _[!UICONTROL PROCESSING]_ até que o processo seja concluído.

![Novo ativo de imagem no status de processamento](./assets/dam-asset-library-upload-processing.png){width="700" zoomable="yes"}

## Usar ativos para criação de conteúdo {#assets-authoring}

Use ativos ao criar emails, modelos de email e fragmentos visuais. O editor de conteúdo visual fornece acesso às imagens na biblioteca _Assets_. Também é possível fazer upload de um ativo de imagem, que o coloca no repositório de ativos interno.

Você pode escolher o ativo de imagem ao editar as configurações de um componente de imagem ou diretamente na tela:

* **_Componente vazio_** - Quando você adiciona um componente de imagem à tela, ele fica vazio e fornece acesso fácil para selecionar ou importar um arquivo de imagem.

  ![Escolha uma fonte e selecione um arquivo de imagem para o componente de imagem vazio](./assets/dam-assets-image-component-empty.png){width="500"}

* **_Barra de ferramentas do componente de Imagem_** - Quando você tem um componente de Imagem selecionado na tela, a barra de ferramentas fornece acesso fácil para escolher uma fonte e selecionar o arquivo de imagem.

  ![Use a barra de ferramentas para escolher uma fonte e selecionar um arquivo de imagem para o componente de imagem](./assets/dam-assets-image-toolbar-settings.png){width="500"}

* **_Configurações do componente de imagem_** - Quando um componente de imagem está selecionado na tela, você pode exibi-las e editá-las no painel direito. Para adicionar ou alterar o arquivo de imagem exibido no componente, escolha o tipo de origem e selecione um arquivo de imagem.

  ![Editar as configurações do componente de imagem no painel direito](./assets/dam-assets-image-settings.png){width="350"}

Clique em **[!UICONTROL Selecionar ativo]** para abrir o seletor de ativos, onde é possível escolher uma imagem do repositório de ativos [!DNL Marketo Optimizer].

![Selecione um ativo de imagem](./assets/dam-assets-internal-image-selected.png){width="700" zoomable="yes"}

É possível usar a pesquisa e filtros para localizar o ativo de imagem desejado. Selecione o ativo e clique em **[!UICONTROL Selecionar]** para usá-lo no componente de imagem.

Você também pode escolher um ativo de imagem nas configurações de plano de fundo de um componente de estrutura.
