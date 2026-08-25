---
title: Destinos
description: Saiba mais sobre as permissões necessárias, os destinos compatíveis e como conectar um destino no Marketo Otimizer para ativar listas de pessoas estáticas para plataformas sociais e de publicidade.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Destinos

Os destinos são integrações pré-criadas que permitem enviar [listas de pessoas estáticas](./people-lists.md#static-lists) de [!DNL Marketo Optimizer] para anúncios externos ou plataformas sociais, como um público de campanha do LinkedIn, um público de Correspondência de Cliente do Google ou um Público-alvo personalizado do Facebook. Ativar uma lista estática para um destino mantém a associação em sincronia: à medida que as pessoas são adicionadas ou removidas da lista, elas são correspondentemente adicionadas ou removidas do público-alvo de destino e, por extensão, de qualquer campanha que o público-alvo alimente.

Há duas maneiras de ativar pessoas para um destino conectado:

* **De uma lista estática** — Ative uma lista estática existente diretamente da guia **_[!UICONTROL Listas de pessoas]_**. Consulte [Ativar para um destino](./people-lists.md#static-list-activate).
* **De uma jornada de pessoa** — Adicione uma ação **_[!UICONTROL Ativar para destino]_** a um caminho de jornada para que qualquer pessoa que alcance esse nó seja adicionada a uma lista e enviada para o destino. Consulte [_Adicionar um nó de ação_](../marketing/action-nodes.md#add-an-action-node).

>[!BEGINSHADEBOX]

## Permissões necessárias {#required-permissions}

O recurso de destino completo requer que as seguintes [!DNL Adobe Experience Platform] permissões sejam habilitadas.

| Categoria | Permissão | Obrigatório |
|--- |--- |--- |
| Sandboxes | Acesso à sandbox _(habilitado por padrão)_ | Sim |
| Painéis | Ver Painéis de Controle Padrão | Sim |
| Painéis | Gerenciar painéis padrão | Sim |
| Destinos | Exibir destinos | Sim |
| Destinos | Gerenciar destinos | Sim |
| Destinos | Ativar destinos | Sim |
| Destinos | Ativar segmento sem mapeamento | Sim |
| Destinos | Gerenciar e ativar destino do conjunto de dados | Sim |
| Destinos | Criação de destino | Sim |
| Governança de dados | Exibir políticas de uso de dados | Sim |
| Governança de dados | Gerenciar políticas de uso de dados | Sim |
| Ingestão de dados | Exibir fontes | Sim |
| Ingestão de dados | Gerenciar fontes | Sim |
| Gerenciamento de perfil | Exibir configurações do perfil | Sim |
| Gerenciamento de perfil | Gerenciar configurações do perfil | Sim |

>[!ENDSHADEBOX]

## Destinos compatíveis {#supported-destinations}

Antes de ativar uma lista estática, um destino deve existir no catálogo de destinos. Na navegação à esquerda, expanda **[!UICONTROL Conexões]** e selecione **[!UICONTROL Destinos]**. Atualmente, o [!DNL Marketo Optimizer] oferece suporte aos seguintes destinos:

* **[!UICONTROL Correspondência de cliente do Google]** (Advertising)
* **[!UICONTROL Público-Alvo Personalizado Do Facebook]** (Social)
* **[!UICONTROL Público-alvo correspondente do LinkedIn]** (Social)

![Acessar os tipos de conectores disponíveis](./assets/destinations-catalog.png){width="800" zoomable="yes"}

>[!NOTE]
>
>Este catálogo não está completo para [!DNL Adobe Experience Platform] destinos. Se você acessar destinos diretamente do [!DNL Experience Platform], verá um catálogo maior, mas apenas esses destinos estarão disponíveis no momento para ativação no [!DNL Marketo Optimizer]. Destinos adicionais estão planejados para versões futuras.

## Configurar um destino {#set-up-destination}

Cada cartão de destino suportado mostra **[!UICONTROL Configurar novo destino]**. Configurar um destino é um pré-requisito para a ativação.

1. Na placa do conector, clique em **[!UICONTROL Configurar novo destino]**.

1. Selecione **[!UICONTROL Conta existente]** ou **[!UICONTROL Nova conta]** e insira os detalhes da conta, como o nome e a descrição da conta.

   ![Conectar uma nova conta de destino](./assets/destinations-configure-new.png){width="500"}

1. Clique em **[!UICONTROL Conectar ao destino]**.

   Um fluxo OAuth permite fazer logon na conta correspondente: LinkedIn, Google ou Facebook.

   >[!IMPORTANT]
   >
   >Neste ponto, **não** insira os _[!UICONTROL detalhes do Destino]_. Somente a conexão é necessária.

1. Preencha qualquer mapeamento de campo obrigatório entre os atributos de pessoas e os campos exigidos pelo destino.

1. Revise as configurações de governança de dados e ação de marketing e clique em **[!UICONTROL Salvar]**.

Para obter as etapas de instalação completas, consulte [Criar uma nova conexão de destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination){target="_blank"} na documentação de [!DNL Experience Platform].

Quando configurado, o destino estará disponível para ativação em todos os locais que você puder selecionar um destino em [!DNL Marketo Optimizer].

## Ativação e sincronização {#activation-sync}

A ativação é orientada por associação de lista estática, com uma sincronização bidirecional entre a lista e o público-alvo de destino:

* Adicionar uma pessoa à lista estática ativa-a no destino em 24 horas, adicionando-a ao público-alvo de destino e, subsequentemente, a qualquer campanha que o público-alvo alimente.
* Remover uma pessoa da lista estática desativa-a do destino — ela é removida do público-alvo de destino e de qualquer campanha conectada.
* A mesma lista pode ser ativada para vários destinos de uma só vez; a associação é sincronizada com todos eles.

>[!TIP]
>
>Para executar uma campanha do LinkedIn em relação a um segmento, ative a lista estática dessas pessoas para o destino do público-alvo correspondente do LinkedIn. Todos na lista são adicionados ao público-alvo correspondente no LinkedIn, onde uma campanha pode direcioná-los, e o público-alvo se mantém atualizado automaticamente à medida que a lista muda.
