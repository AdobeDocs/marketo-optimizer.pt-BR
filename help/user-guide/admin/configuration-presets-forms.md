---
title: Configuração do Forms
description: Espaço reservado
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 16%

---

# Configurações do Forms

Para que os profissionais de marketing possam criar e publicar formulários para usar em suas páginas de aterrissagem, um administrador de produto deve criar uma ou mais predefinições dedicadas. Cada predefinição define o ponto de extremidade de conexão usado para enviar os dados de envio do formulário e o conjunto de dados usado para armazenar os dados capturados.

Quando os dados chegam ao endpoint de transmissão, eles são vinculados às informações do conjunto de dados. Usando as conexões de origem/destino geradas e o fluxo de origem, os dados são enviados para o conjunto de dados.

>[!BEGINSHADEBOX]

## Pré-requisitos

Para usar formulários web, você deve ter uma ou mais _&#x200B;**conexões de transmissão da API HTTP**&#x200B;_ definidas no Adobe Experience Platform. Verifique se cada conexão que você deseja usar atende aos seguintes requisitos:

* O tipo de dados deve ser definido como XDM (não dados brutos)
* A autenticação deve ser desabilitada (conexão não autenticada)

Para obter informações detalhadas sobre como criar conexões de origem de transmissão, consulte a [_documentação do Experience Platform_](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/streaming/http).

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../start/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## Diretrizes de configuração da predefinição de formulário

Ao criar uma predefinição:

* É possível configurar várias predefinições usando diferentes combinações de conjuntos de dados e conexões de transmissão.

* É possível reutilizar o mesmo conjunto de dados ou conexão de transmissão em várias predefinições.

* Cada conexão de transmissão gera recursos automaticamente, como:

  * _conexão Source_ - de onde os dados se originam.
  * _Conexão de destino_ - onde os dados são armazenados ou consumidos.
  * _Fluxo do Source_ - o pipeline que move dados da conexão de origem para o Experience Platform. Ela lida com mapeamento, transformação e validação.

## Criar uma predefinição de formulário {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="Selecionar o ponto de acesso a ser usado"
>abstract="Defina o ponto de acesso de transmissão para onde os dados serão mandados ao enviar o formulário."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="Criar uma conexão de transmissão com a API HTTP"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="Selecionar um conjunto de dados"
>abstract="Defina um conjunto de dados em que as respostas do formulário são armazenadas e refletidas. Insira texto para pesquisar um conjunto de dados específico ou selecioná-lo na lista."

1. Na navegação à esquerda, vá para **[!UICONTROL Administração]** > **[!UICONTROL Canais]**.

1. Em _[!UICONTROL Configurações de formulário]_, no painel de navegação, selecione **[!UICONTROL Predefinições de formulário]**.

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. Clique em **[!UICONTROL Criar predefinição de formulário]**.

1. Insira um **[!UICONTROL Nome]** exclusivo (obrigatório) e uma **[!UICONTROL Descrição]** (opcional) para a configuração.

   >[!NOTE]
   >
   >Os nomes devem começar com uma letra (A-Z) e podem conter apenas caracteres alfanuméricos. Você também pode usar sublinhado `_`, ponto `.` e hífen `-` caracteres.

1. Selecione a **[!UICONTROL Conexão de transmissão]**.

   Essa conexão é o ponto de extremidade de transmissão usado para enviar os dados quando um visualizador da Web envia um formulário. Se a conexão de transmissão necessária não for exibida na lista, verifique se os requisitos foram atendidos.

1. Clique no ícone _Selecionar conjunto de dados_ ( ![Selecionar ícone do conjunto de dados](../assets/do-not-localize/icon-select-data.svg) ) para vincular um conjunto de dados ao formulário.

   O conjunto de dados é onde as respostas do formulário são armazenadas e refletidas. Você pode inserir uma string de texto para procurar um conjunto de dados específico ou selecioná-lo na lista.

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >Atualmente, apenas os [conjuntos de dados do Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/catalog/datasets/overview) habilitados para perfil e não habilitados estão disponíveis para seleção. É possível selecionar um conjunto de dados por vez. Os conjuntos de dados do sistema não podem ser usados para salvar dados de formulário.

   Marque a caixa de seleção do conjunto de dados e clique em **[!UICONTROL Selecionar]**.

1. Clique em **[!UICONTROL Salvar como rascunho]**.

## Publicar uma predefinição de formulário

1. Clique no nome da predefinição do formulário para abrir a página de configuração.

   É possível fazer ajustes no rascunho, se necessário.

1. Clique em **[!UICONTROL Publicar]**.

   Quando a predefinição de formulário é listada com um status _Publicado_, ela está disponível para uso na criação de formulários.
